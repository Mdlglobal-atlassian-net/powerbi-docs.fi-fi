---
title: 'Järjestä uuden työtilakokemuksen - Power BI: ssä'
description: Lue lisää uuden työtilakokemuksen, joka on kokoelma koontinäyttöjä ja raportteja, joiden avulla voit kuvata organisaatiosi keskeisiä mittalukuja.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 9f5dfaa5a23ae46fef131a52355531b5fbde3051
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100681"
---
# <a name="organize-work-in-the-new-workspaces-in-power-bi"></a>Järjestä keskeneräisten uusi Power BI-työtiloissa

 *Työtilat* on paikkoja tehdä yhteistyötä työtovereiden kanssa kokoelmia koontinäyttöjen, raporttien ja Sivutettujen raporttien luomiseksi. Työtilan uuden kokemuksen avulla voit hallita paremmin käyttöoikeuden sisältöön. Tässä artikkelissa kuvataan uuden työtilakokemuksen ja miten ne eroavat perinteinen työtilat.  Kuin perinteinen työtilojen kanssa voit edelleen käyttää niitä sovellusten luominen ja jakeleminen. Lue lisää [luoda uuden kokemuksen työtilan](service-create-the-new-workspaces.md).

Uusi työtila-käyttökokemus on saavuttanut yleisesti käytettävissä (GA) ja on nyt oletustyötilaan. Voit kuitenkin edelleen luoda ja käyttää [perinteinen työtilat](service-create-workspaces.md) Office 365-ryhmien perusteella. 

> [!NOTE]
> Jos haluat ottaa rivitason suojaus (RLS) Power BI Pro käyttäjille selaamalla sisältöä työtilassa, edelleen käyttää [perinteinen työtilat](service-create-workspaces.md). Valitse **jäsenet voivat vain tarkastella Power BI-sisältöä** vaihtoehto. Vaihtoehtoisesti julkaista Power BI-sovelluksen näille käyttäjille tai sisällön jakamisen avulla. Tulevan Viewer-roolin mahdollistaa tämän skenaarion tulevaisuudessa työtiloissa uusi työtilan käyttökokemuksen.

Uusien työtilojen avulla voit tehdä seuraavaa:

- Työtilan roolien määrittäminen käyttäjäryhmille: käyttöoikeusryhmät, jakeluluettelot, Office 365 -ryhmiä ja henkilöt.
- Työtilan luominen Power BI:ssä luomatta Office 365 -ryhmää.
- Tarkempien työtilaroolien käyttäminen oikeuksien määrittämiseksi työtilassa entistä joustavammin.

Kun luot jonkin uusista työtiloista, et luo taustalla toimivaa, työtilaan liitettyä Office 365 -ryhmää. Työtilaa hallitaan Power BI:ssä Office 365:n sijasta. Työtilan uuden kokemuksen voit nyt lisätä Office 365-ryhmän työtilan käyttöoikeusluettelossa Jatka sisältöön Office 365-ryhmien avulla käyttöoikeuksien hallinnasta.

## <a name="administering-new-workspace-experience-workspaces"></a>Uusi työtilan kokemus työtilojen hallinta
Uusi työtila kokemus työtilojen hallinta on nyt Power BI-Power BI-järjestelmänvalvojat luettelonäkymässä kuka organisaatiossa voi luoda työtiloja. He voivat hallita ja palauttaa työtila. Voit tehdä tämän ne on käytettävä Power BI-hallintaportaalissa tai PowerShellin cmdlet-komennot. Työtilojen perinteinen Office 365-ryhmien perusteella hallinnan ilmenee edelleen Office 365-hallintaportaalissa ja Azure Active Directory.

- **Työtilan asetukset** hallintaportaalissa, järjestelmänvalvojat Luo työtiloja (uuden työtilan kokemuksen) asettaminen menevätkin tai ei salli organisaation avulla voit luoda uuden työtilan kokemus työtiloja. He voivat myös rajoittaa luomisen tiettyjen käyttöoikeusryhmien jäsenille.

> [!NOTE]
> Luo työtiloja (uuden työtilan kokemuksen), asetuksen oletusarvo on vain käyttäjät, jotka voit luoda uuden työtilakokemuksen luomiseen Power BI Office 365-ryhmiä. Muista määrittää arvon Power BI-hallintaportaalissa, jotta voit varmistaa asianmukaiset käyttäjät voivat luoda uusi työtila kokemus työtiloja.

![Työtilan asetukset hallintaportaalissa](media/service-new-workspaces/power-bi-workspace-admin-settings.png)

[Työtilat luettelo on käytettävissä](service-admin-portal.md#workspaces) Power BI-hallintaportaalissa. 

![Työtilojen luettelo](media/service-admin-portal/workspaces-list.png)

## <a name="new-workspaces-side-by-side-with-classic-workspaces"></a>Uusien työtilojen rinnakkain perinteinen työtilojen kanssa

Uusi työtiloja, päivitetty ja aiemmin perinteinen työtilat olla asennettuna rinnakkain ja voit luoda. Uusi työtila on työtilan oletustyyppi. Power BI jatkossakin luettelo kaikki Office 365-ryhmiä käyttäjä on välttämiseksi muuttaminen olemassa olevat työnkulut Power BI-jäsen. Lue miten voit luoda uuden työtilan [luoda uuden työtilakokemuksen](service-create-the-new-workspaces.md). Lue luominen perinteiseen työtilaan [perinteinen työtilan luominen](service-create-workspaces.md).

## <a name="roles-in-the-new-workspaces"></a>Roolit uusissa työtiloissa

Uusi työtila käyttöoikeus, Lisää käyttäjä- tai henkilöille työtilan rooleihin: jäsenet ja järjestelmänvalvojat osallistujia. Kaikki käyttäjäryhmän jäsenet saavat määrittämäsi roolin. Jos käyttäjä on useita käyttäjäryhmät, he saavat parhaan mahdollisen antama rooleja, ne on määritetty käyttöoikeus.

Roolien avulla voit hallita, kuka voi tehdä mitäkin työtilassa, joten ryhmät voivat tehdä yhteistyötä. Uusissa työtiloissa voit määrittää henkilöille ja käyttäjäryhmille rooleja. Voit käyttää käyttöoikeusryhmiä, Office 365 -ryhmiä ja jakeluluetteloita. 

Kun määrität rooleja käyttäjäryhmälle, ryhmän käyttäjät voivat käyttää sisältöä. Jos asetat sisäkkäin käyttäjäryhmiä, kaikilla ryhmien käyttäjillä on käyttöoikeus. Käyttäjä, joka on useissa käyttäjäryhmissä, joille on määritetty eri rooleja, saa parhaan myönnetyn käyttöoikeuden. 

Uusissa työtiloissa on kolme roolia: järjestelmänvalvojat, jäsenet ja osallistujat.

|Ominaisuuden   | Järjestelmänvalvoja  | Jäsen  | Osallistuja  | 
|---|---|---|---|
| Päivittää työtilaa ja poistaa sen.  | X  |   |   |
| Lisätä tai poistaa ihmisiä, myös muita järjestelmänvalvojia.  | X  |   |   |
| Lisätä jäseniä tai muita, joilla on vähäisemmät oikeudet.  |  X | X  |   |
| Julkaista ja päivittää sovelluksen. |  X | X  |   |
| Jakaa kohteen tai sovelluksen. |  X | X  |   |
| Sallia muille kohteiden jakaminen uudelleen. |  X | X  |   |
| Luoda, muokata ja poistaa työtilan sisältöä.  |  X | X  | X  |
| Julkaista raportteja työtilaan ja poistaa sisältöä. |  X | X  | X  |
 
 
## <a name="licensing"></a>Käyttöoikeudet
Jokainen työtilaan lisätty jäsen tarvitsee Power BI Pro -käyttöoikeuden. Työtilassa nämä käyttäjät voivat tehdä yhteistyötä niiden koontinäyttöjen ja raporttien parissa, jotka aiot julkaista laajemmalle lukijakunnalle tai jopa koko organisaatiolle. Jos haluat jakaa sisältöä muille organisaatiosi sisällä, voit määrittää Power BI Pro -käyttöoikeudet kyseisille käyttäjille tai sijoittaa työtilan Power BI Premium -kapasiteettiin.

> [!NOTE]
> Raporttien julkaiseminen työtilan uuden kokemuksen on tiukempia pakotukseen licensing-sääntöjä. Käyttäjä yrittää julkaista Power BI Desktop-tai muiden asiakkaiden Työkalut ilman Pro-käyttöoikeus nähdä virheilmoituksen ”vain käyttäjät, joilla on Power BI Pro-käyttöoikeuksia julkaista tähän työtilaan”.

## <a name="how-are-the-new-workspaces-different-from-current-workspaces"></a>Miten uudet työtilat eroavat nykyisistä työtiloista?

Uusien työtilojen myötä suunnittelemme joitakin ominaisuuksia uudelleen. Seuraavassa on aiot voi olla pysyvä muutokset. 

* Nämä työtilojen luominen ei luo Office 365-ryhmille, kuten perinteinen työtilat tekevät. Voit nyt käyttää Office 365-ryhmään antaa käyttäjille pääsy työtilaasi määrittämällä rooli. 
* Perinteiset työtilat voit lisätä vain yksittäisiä henkilöitä jäsenten ja järjestelmänvalvojien luetteloihin. Uusissa työtiloissa voit lisätä useita AD-suojausryhmiä, jakeluluetteloita tai Office 365 -ryhmiä näihin luetteloihin, mikä helpottaa käyttäjien hallintaa. 
- Voit luoda organisaation Sisältöpaketin perinteinen työtilasta. Et voi luoda sisältöpakettia uusista työtiloista.
- Voit käyttää organisaation Sisältöpaketin perinteinen työtilasta. Et voi käyttää sitä jostakin uudesta työtilasta.

## <a name="workspace-contact-list"></a>Työtilan yhteystietoluettelon
Uusi **yhteystietoluettelo** ominaisuuden avulla voit määrittää käyttäjät, jotka saat ilmoituksen kohteiden työtilan ongelmista. Oletusarvon mukaan kaikki käyttäjän tai ryhmän määritetty työtilan järjestelmänvalvojan ilmoitetaan, mutta voit mukauttaa luetteloa. Käyttäjille tai ryhmille, ota yhteyttä luettelossa näytetään käyttöliittymässä (UI), joiden avulla käyttäjät saavat työtilaan liittyviä ohjeita. 

Lue lisää [asetuksen työtilan yhteystietoluettelon](service-create-the-new-workspaces.md#workspace-contact-list).

## <a name="workspace-onedrive"></a>Workspace OneDrive
Työtilan OneDrive-ominaisuuden avulla voit määrittää Office 365-ryhmä SharePoint-tiedostokirjastoon jonka tiedostosäilö on työtilan käyttäjien käytettävissä. Ryhmä on luotava Power BI ulkopuolella. 

Power BI ei synkronoi käyttäjät tai ryhmät, jotka on määritetty työtila Office 365-ryhmän jäsenyys käytön käyttöoikeudet. Paras käytäntö on työtilan hallitsevat saman Office 365-ryhmän tiedostosäilöön, jonka voit määrittää asetuksen kautta. 

Lue lisää [Määritä ja käytä työtilan OneDrive](service-create-the-new-workspaces.md#workspace-onedrive).  
   
## <a name="auditing"></a>Valvonta
Seuraavat toiminnot ovat valvoo Power BI-työtilojen uusi työtilan käyttökokemuksen.

| Kutsumanimi |   Toiminnon nimi |
|---|---|
| Luotu Power BI -kansio | CreateFolder |
| Poistettu Power BI -kansio | DeleteFolder |
| Päivitetty Power BI -kansio | UpdateFolder |
| Päivitetty Power BI -kansion käyttöoikeus| UpdateFolderAccess |

Lue lisää [Power BI valvonta](service-admin-auditing.md#activities-audited-by-power-bi).

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Huomioitavia rajoituksia:

- Työtiloissa voi olla korkeintaan 1 000 tietojoukkoa tai 1 000 raporttia tietojoukkoa kohti. 
- Henkilö, jolla on Power BI Pro-käyttöoikeuden voi olla enintään 1 000 työtilat jäsen.
- Power BI publisher for Excelin ei tueta.

## <a name="workspace-features-that-work-differently"></a>Eri tavalla toimivat työtilan ominaisuudet

Jotkin ominaisuudet toimivat uusissa työtiloissa eri tavalla kuin nykyisissä työtiloissa. Nämä erot on tarkoituksellista, olemme olet saanut asiakkailta ja ota käyttöön joustavampi tapa yhteistyö työtilojen kanssa palautteen perusteella:

- Käyttöoikeuksien pakotukseen: Raporttien julkaiseminen työtilan uuden kokemuksen käyttää aiemmin käyttöoikeuksien sääntöjä, jotka edellyttävät Power BI Pro-käyttöoikeuden käyttäjille yhteistyö työtiloissa tai jakaminen muille Power BI-palvelussa. Pro-käyttöoikeus ilman käyttäjät näkevät virhe ”vain käyttäjät, joilla Powre BI Pro-käyttöoikeuksia julkaista tähän työtilaan”.
- Jäsenet voivat tai eivät voi jakaa uudelleen: korvataan osallistujan roolilla
- Vain luku -työtilat: Sen sijaan, että myöntäisit käyttäjille Vain luku -käyttöoikeuden työtilaan, määrität käyttäjille tulevan katselijan roolin, johon kuuluu samankaltainen Vain luku -käyttöoikeus työtilan sisältöön.
- Ei **Poistu työtilasta** -painiketta.

## <a name="frequently-asked-questions"></a>Usein kysyttyjä kysymyksiä

**Uusi työtila vaikuta olemassa oleva sisältö linkkejä kohdata GA ovat**

Ei. Aiemmin kohteet perinteisessä työtiloissa linkkejä ei vaikuta työtilan uuden kokemuksen. Työtilan uuden kokemuksen yleisesti käytettävissä (GA) muutokset oletustyötilaan, mutta ei muuta aiemmin työtilat. 

**On olemassa uusi työtilan kokemusta GA päivittää työtilat**

Ei. Uusi työtila-kokemus GA muuttuu työtilan oletustyyppi vain työtilan uuden käyttökokemuksen. Aiemmin perinteinen työtilat, jotka perustuvat Office 365-ryhmiä ei muuteta.

**Työtilat edelleen luodaan automaattisesti Office 365-ryhmiä**

Kyllä. Koska emme tue kummankin tyyppisiä työtilat rinnakkain, voimme jatkaa luettelo kaikki Office 365-ryhmiä käyttäjällä on käyttöoikeus työtilat-luettelossa.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Luo uusi työtilat Power BI](service-create-the-new-workspaces.md)
* [Perinteiset työtilan luominen](service-create-workspaces.md)
* [Asenna ja käytä sovelluksia Power BI:ssä](service-create-distribute-apps.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
