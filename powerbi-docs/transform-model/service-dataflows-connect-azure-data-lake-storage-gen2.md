---
title: Lue, miten voit yhdistää Azure Data Lake Storage Gen 2:n Power BI:hin tietovuon tallennusta varten
description: Tuo omat tietosi tietovoihin käyttämällä Azure Data Lake Storage Gen2:ta
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/22/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: e24888d4be0a527bd7af6a28fd28795b516b2020
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83309264"
---
# <a name="connect-azure-data-lake-storage-gen2-for-dataflow-storage"></a>Azure Data Lake Storage Gen2:n yhdistäminen tietovuon tallentamiseksi

Power BI:n työtilat voidaan määrittää tallentamaan tietovuot organisaatiosi Azure Data Lake Storage Gen2 -tilille. Tässä artikkelissa kuvataan yleisiä vaiheita tämän tekemiseksi sekä annetaan samalla ohjeita ja parhaita käytäntöjä. Työtilojen määrittämisessä on joitakin etuja tietovuon määritelmien ja tietotiedostojen tallentamiseksi Data Lakeen, kuten seuraavat:

* Azure Data Lake Storage Gen2 tarjoaa valtavan skaalattavan tallennusvälineen tiedoille
* IT-osaston kehittäjät voivat hyödyntää tietovuon tietoja ja määritelmätiedostoja Azure-tietojen ja tekoälyn (AI) palvelujen hyödyntämiseksi, kuten [Azure-tietopalvelujen GitHub-malleissa](https://aka.ms/cdmadstutorial) on näytetty.
* Organisaatiosi kehittäjät voivat integroida tietovuon tiedot sisäisiin sovelluksiin ja tärkeisiin liiketoimintaratkaisuihin käyttämällä tietovoiden ja Azuren kehittäjäresursseja

Jos haluat käyttää Azure Data Lake Storage Gen2:ta tietovoita varten, tarvitset seuraavat:

* **Power BI -vuokraaja:** – vähintään yhden tilin Azure Active Directory (AAD) -vuokraajassa on oltava rekisteröinyt Power BI:hin
* **Yleinen järjestelmänvalvoja -tili** – tätä tiliä vaaditaan yhdistämiseen ja Power BI:n määrittämiseen tietovuon määritelmän ja tietojen tallentamiseksi Azure Data Lake Storage Gen2 -tilille
* **Azure-tilaus** – tarvitset Azure-tilauksen Azure Data Lake Storage Gen2:n käyttämiseksi
* **Resurssiryhmä** – käytä olemassa olevaa resurssiryhmää tai luo uusi
* **Azure-tallennustili, jossaa on Data Lake Storage Gen2 -ominaisuus käytössä** 

> [!TIP]
> Jos sinulla ei ole Azure-tilausta, luo [ilmainen tili](https://azure.microsoft.com/free/) ennen aloittamista.

> [!WARNING]
> Kun tietovuon tallennussijainti on määritetty, sitä ei voi muuttaa. Lisätietoja muista tärkeistä seikoista on tämän artikkelin lopussa olevassa [huomioon otettavia seikkoja ja rajoituksia](#considerations-and-limitations) käsittelevässä osassa.

## <a name="prepare-your-azure-data-lake-storage-gen2-for-power-bi"></a>Azure Data Lake Storage Gen2:n valmisteleminen Power BI:tä varten

Ennen kuin voit määrittää Power BI:hin Azure Data Lake Storage Gen2 -tilin, sinun on luotava ja määritettävä tallennustili. Tarkastellaanpa Power BI:n vaatimuksia:

1. Sinun on oltava ADLS-tallennustilin omistaja. Tämä asetus on määritettävä resurssitasolla, eikä se saa olla peritty tilaustasolta.
2. Tallennustili on luotava samassa AAD-vuokraajassa kuin Power BI -vuokraajasi.
3. Tallennustili on luotava samalla alueella kuin Power BI -vuokraajasi. Jos haluat tietää, missä Power BI -vuokraajasi sijaitsee, katso artikkelia [Missä Power BI -vuokraajani sijaitsee](../admin/service-admin-where-is-my-tenant-located.md).
4. Tallennustilillä on oltava käytössä *Hierarkkinen nimitila* -ominaisuus.

Seuraavissa osioissa käydään tarkemmin läpi vaiheita, joita tarvitaan Azure Data Lake Storage Gen2 -tilisi määrittämiseen.

### <a name="create-the-storage-account"></a>Tallennustilin luominen

Noudata artikkelin [Azure Data Lake Storage Gen2 -tallennustilin luominen](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account) ohjeita.

1. Varmista, että valitset saman sijainnin kuin Power BI -vuokraajasi, ja määritä tallennustilaksi **StorageV2 (yleinen tarkoitus v2)**
2. Varmista, että otat käyttöön Hierarkkinen nimitila -ominaisuuden
3. Suosittelemme, että määrität replikoinnin asetukseksi **Maantieteellisesti vikasietoiseksi hajautetun tallennuksen (RA-GRS) lukijaoikeudet**

### <a name="grant-permissions-to-power-bi-services"></a>Käyttöoikeuksien myöntäminen Power BI -palveluille

Seuraavaksi sinun on myönnettävä Power BI -palvelulle lukija- ja tietoyhteysroolit luomallesi tallennustilille. Ne molemmat ovat sisäänrakennettuja rooleja, joten vaiheet ovat yksinkertaisia. 

Noudata [Sisäisen RBAC-roolin määrittäminen](https://docs.microsoft.com/azure/storage/common/storage-auth-aad-rbac#assign-a-built-in-rbac-role) -artikkelin ohjeita.

Valitse **Lisää roolimääritys** -ikkunasta **Lukija- ja Tietoyhteys** -roolit. Etsi sitten haun avulla **Power BI -palvelu** ‑sovellus.
Toista samat vaiheet **Säilön Blob-tietojen omistaja** ‑roolille ja määritä rooli sekä **Power BI ‑palvelulle** että **Power BI Premium** ‑sovelluksille.

> [!NOTE]
> Odota käyttöoikeuden välittymistä Power BI:hin portaalista vähintään 30 minuuttia. Aina kun muutat käyttöoikeuksia portaalissa, kyseisten käyttöoikeuksien näkyminen Power BI:ssä voi kestää 30 minuuttia. 

## <a name="connect-your-azure-data-lake-storage-gen2-to-power-bi"></a>Azure Data Lake Storage Gen2:n yhdistäminen Power BI:hin 

Kun olet määrittänyt Azure Data Lake Storage Gen2 -tilisi Azure-portaalissa, yhdistät sen Power BI:hin **Power BI -hallintaportaalissa**. Hallitset myös Power BI -tietovuon tallennusta Power BI -hallintaportaalin **Tietovuon tallennus** -asetusosiossa. Katso tarkempia ohjeita käynnistyksestä ja perustason käytöstä artikkelista [Siirtyminen hallintaportaaliin](../admin/service-admin-portal.md).

Voit yhdistää **Azure Data Lake Storage Gen2** -tilisi seuraavasti:

1. Siirry **Power BI -hallintaportaalin** **Tietovuon asetukset** -välilehteen.

    ![Power BI -hallintaportaali](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-08b.png) 

2. Valitse **Yhdistä Azure Data Lake Storage Gen2** -painike. Näyttöön avautuu seuraava ikkuna.

    ![Azure Data Lake Storage Gen2](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_09.jpg) 

3. Anna **tilaustunnus** tallennustilille.
4. Anna **resurssiryhmän nimi**, johon tallennustilisi luotiin.
5. Anna **tallennustilin nimi**.
6. Valitse **Muodosta yhteys**.

Kun nämä vaiheet on suoritettu, Azure Data Lake Storage Gen2 -tilisi on yhdistetty Power BI:hin. 

> [!NOTE]
> Jotta voit määrittää yhteyden Azure Data Lake Storage Gen2:een Power BI -hallintaportaalissa, tarvitset yleisen järjestelmänvalvojan oikeudet. Yleiset järjestelmänvalvojat eivät kuitenkaan voi muodostaa yhteyttä ulkoiseen säilöön hallintaportaalissa.  

Sinun on seuraavaksi sallittava organisaatiosi työntekijöiden määrittää työtilansa, jotta ne voivat käyttää tallennustiliä tietovuon määritykseen ja tietojen tallennukseen. Tehdään se seuraavassa osiossa. 


## <a name="allow-admins-to-assign-workspaces"></a>Salli järjestelmänvalvojien määrittää työtiloja

Tietovuon määritys ja tietotiedostot tallennetaan oletusarvoisesti Power BI:n tarjoamaan tallennustilaan. Jotta työtilan järjestelmänvalvojat voivat käyttää tietovuon tiedostoja omalla tallennustililläsi, heidän on ensin määritettävä työtila sallimaan tietovoiden määritys ja tallennus uudella tallennustilillä. Ennen kuin työtilan järjestelmänvalvojat voivat määrittää tietovuon tallennusasetukset, järjestelmänvalvojan on myönnettävä tallennustilan määrityksen käyttöoikeudet **Power BI -hallintaportaalissa**.

Jotta voit myöntää tallennustilan määrityksen käyttöoikeudet, siirry **Tietovuon asetukset** -välilehteen **Power BI -hallintaportaalissa**. Täällä on valintanappi *Salli työtilan järjestelmänvalvojien määrittää työtilat tälle tallennustilille*, jonka arvoksi on määritettävä **Salli**. Kun olet ottanut liukusäätimen käyttöön, valitse **Käytä**-painike, jotta muutos tulee voimaan. 

![Salli järjestelmänvalvojien määrittää työtiloja](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_10.jpg) 

Siinä kaikki! Power BI -työtilan järjestelmänvalvojat voivat nyt määrittää työnkulkuja luomaasi tiedostojärjestelmään.


## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

Tämä ominaisuus on esikatseluominaisuus, ja sen toiminta saattaa muuttua ennen sen julkaisua. Ota huomioon seuraavat seikat ja rajoitukset tietovuon tallennustilan käytön aikana:

* Kun tietovuon tallennussijainti on määritetty, sitä ei voi muuttaa.
* Vain Azure Data Lake Storage Gen2:een tallennetun tietovuon omistajat voivat käyttää sen tietoja oletusarvoisesti. Jotta muut henkilöt voivat käyttää Azureen tallennettuja tietovoita, sinun on lisättävä heidät tietovuon CDM-kansioon. 
* Tietovoiden luominen linkitettyjen entiteettien kanssa on mahdollista vain, kun ne on tallennettu samalle tallennustilille.
* Power BI:n jaettujen kapasiteettien paikallisia tietolähteitä ei tueta tietovoissa, jotka on tallennettu organisaatiosi Data Lake-järjestelmään.
* Tilannevedoksia ei poisteta automaattisesti ADLS Gen 2:ssa. Jos haluat vapauttaa tilaa, voit luoda Azure-funktion, joka poistaa vanhat tilannevedokset säännöllisesti.

Tähän liittyy myös joitakin tunnettuja ongelmia, kuten tässä osiossa on kuvattu.

Power BI Desktop -asiakkaat eivät voi käyttää **Azure Data Lake Storage -tilille** tallennettuja tietovoita, elleivät ne ole tietovuon omistajia tai niille ei ole myönnetty valtuutta käyttää CDM-kansiota Lake-järjestelmässä. Skenaario on seuraava:

1. Anna on luonut uuden työtilan ja määrittänyt sen tallentamaan tietovuot organisaation Data Lake -järjestelmään. 
2. Ben, joka on myös Annan luoman työtilan jäsen, haluaa noutaa tietoja Annan luomasta tietovuosta Power BI Desktopin ja tietovuon liittimen avulla.
3. Ben saa samankaltaisen virheen, koska häntä ei ole lisätty tietovuon CDM-kansion valtuutetuksi käyttäjäksi Lake-järjestelmässä.

Yleisiä kysymyksiä ja vastauksia ovat muun muassa seuraavat:

**Kysymys:** Entä jos olen aiemmin luonut tietovoita työtilassa ja haluan muuttaa niiden tallennussijaintia?

**Vastaus**: Et voi muuttaa tietovuon tallennussijaintia sen luomisen jälkeen. 

**Kysymys:** Milloin voin muuttaa työtilan tietovuon tallennussijaintia?

**Vastaus**: Voit muuttaa työtilan tietovuon tallennussijaintia vain, jos työtila ei sisällä mitään tietovoita.


## <a name="next-steps"></a>Seuraavat vaiheet

Tässä artikkelissa annetaan ohjeita siitä, miten voit yhdistää Azure Data Lake Gen2:n tietovuon tallennustilaan. Lisätietoja saat seuraavista artikkeleista:

Lisätietoja tietovoista, CDM:stä ja Azure Data Lake Storage Gen2:sta on seuraavissa artikkeleissa:

* [Tietovuot ja Azure Data Lake -integrointi (esikatselu)](service-dataflows-azure-data-lake-integration.md)
* [Määritä työtilan tietovuoasetukset (esikatselu)](service-dataflows-configure-workspace-storage-settings.md)
* [Lisää CDM-kansio Power BI:hin tietovuona (esikatselu)](service-dataflows-add-cdm-folder.md)

Lisätietoja tietovoista yleisesti on seuraavissa artikkeleissa:

* [Tietovoiden luominen ja käyttäminen Power BI:ssä](service-dataflows-create-use.md)
* [Laskettujen entiteettien käyttäminen Power BI Premiumissa](service-dataflows-computed-entities-premium.md)
* [Tietovoiden käyttö paikallisiin tietolähteisiin](service-dataflows-on-premises-gateways.md)
* [Kehittäjien resurssit Power BI -tietovoille](service-dataflows-developer-resources.md)

Lisätietoja Azure-tallennustilasta on seuraavissa artikkeleissa:
* [Azure-tallennuksen suojausopas](https://docs.microsoft.com/azure/storage/common/storage-security-guide)

Lisätietoja Common Data Modelista on sen yleiskatsauksen sisältävässä artikkelissa:
* [Common Data Model – yleiskatsaus](https://docs.microsoft.com/powerapps/common-data-model/overview)
* [CDM-kansiot](https://go.microsoft.com/fwlink/?linkid=2045304)
* [CDM-mallitiedoston määritys](https://go.microsoft.com/fwlink/?linkid=2045521)

Voit myös yrittää [esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/).
