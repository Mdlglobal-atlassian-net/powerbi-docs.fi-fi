---
title: Työn järjestäminen uusiin työtiloihin Power BI:ssä
description: Lue uusista työtiloista, jotka ovat koontinäyttöjen ja raporttien kokoelmia. Voit niiden avulla kuvata organisaatiosi keskeisiä mittalukuja.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/07/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: c534a72594692c5cf404b095492e7d6425f23329
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83273657"
---
# <a name="organize-work-in-the-new-workspaces-in-power-bi"></a>Työn järjestäminen uusiin työtiloihin Power BI:ssä

*Työtilat* ovat paikkoja, joissa voit yhdessä työtovereiden kanssa luoda koontinäyttöjen, raporttien, tietojoukkojen ja sivutettujen raporttien kokoelmia. Uusi työtilakokemus auttaa sinua paremmin hallitsemaan sisältöä. Tässä artikkelissa kuvataan uusia työtiloja ja sitä, miten ne eroavat perinteisistä työtiloista.  Perinteisten työtilojen tavoin voit yhä käyttää niitä sovellusten luomiseen ja jakamiseen. Oletko valmis luomaan uuden työtilan? Lue lisää [uuden työtilakokemuksen luomisesta](service-create-the-new-workspaces.md).

Uudet päivitetyt työtilat ja aiemmat perinteiset työtilat ovat käytettävissä rinnakkain. Uusi työtilakokemus on työtilan oletustyyppi. Voit edelleen tarpeen mukaan luoda ja käyttää Office 365 -ryhmiin perustuvia [perinteisiä työtiloja](service-create-workspaces.md). Oletko valmis siirtämään perinteisen työtilasi? Lue lisätietoja kohdasta [Perinteisten työtilojen päivittäminen uusiksi työtiloiksi Power BI:ssä](service-upgrade-workspaces.md).

Uusien työtilojen avulla voit:

- Työtilan roolien määrittäminen käyttäjäryhmille: käyttöoikeusryhmät, jakeluluettelot, Office 365 -ryhmiä ja henkilöt.
- Luo työtila Power BI:ssä luomatta taustalla toimivaa, työtilaan liitettyä Office 365 -ryhmää. Työtilaa hallitaan Power BI:ssä Office 365:n sijasta.
- Jatka käyttäjien sisällön käyttöoikeuksien hallintaa Office 365 -ryhmän avulla, jos haluat. Lisää vain Office 365 -ryhmä työtilan käyttöoikeusluetteloon.
- Tarkempien työtilaroolien käyttäminen oikeuksien määrittämiseksi työtilassa entistä joustavammin.

Power BI luettelee jatkossakin kaikki Office 365 -ryhmät, joiden jäsen olet. Näin vältetään olemassa olevien työnkulkujen muuttaminen.

## <a name="new-and-classic-workspace-differences"></a>Uuden ja perinteisen työtilan erot

Uusien työtilojen myötä osa ominaisuuksista on suunniteltu uudelleen. Tässä ovat tärkeimmät erot.

* Näiden työtilojen luominen ei luo Office 365 -ryhmiä perinteisten työtilojen tavoin. Voit kuitenkin nyt käyttää Office 365 -ryhmää antamaan käyttäjille pääsyn työtilaasi myöntämälle tälle roolin. 
* Perinteisissä työtiloissa voit lisätä vain yksittäisiä henkilöitä jäsenten ja järjestelmänvalvojien luetteloihin. Uusissa työtiloissa voit lisätä useita Active Directory -suojausryhmiä, jakeluluetteloita tai Office 365 -ryhmiä näihin luetteloihin, mikä helpottaa käyttäjien hallintaa. 
- Voit luoda organisaation sisältöpaketin perinteisestä työtilasta. Et voi luoda sisältöpakettia uusista työtiloista.
- Voit käyttää organisaation sisältöpakettia perinteisestä työtilasta. Et voi käyttää sitä jostakin uudesta työtilasta.

### <a name="workspace-features-that-work-differently"></a>Eri tavalla toimivat työtilan ominaisuudet

Jotkin ominaisuudet toimivat uusissa työtiloissa eri tavalla kuin nykyisissä työtiloissa. Nämä erot on tehty tarkoituksella asiakkailta saadun palautteen perusteella. Ne mahdollistavat joustavamman tavan tehdä yhteistyötä työtilojen kautta.

- **Käyttöoikeuksien pakottaminen**: Nykyisiä käyttöoikeussääntöjä sovelletaan raporttien julkaisemiseen uuteen työtilakokemukseen. Käyttäjät, jotka tekevät yhteistyötä työtiloissa tai jakavat sisältöä muille Power BI -palvelussa, tarvitsevat Power BI Pro -käyttöoikeuden. Käyttäjät, joilla ei ole Pro-käyttöoikeutta, näkevät virheen ”Vain käyttäjät, joilla on Power BI Pro -käyttöoikeudet, voivat julkaista tähän työtilaan”.
- **Jäsenet voivat jakaa uudelleen tai eivät voi jakaa uudelleen**: Osallistujan rooli korvaa tämän asetuksen.
- **Vain luku -työtilat**: Sen sijaan, että myöntäisit käyttäjille vain luku -käyttöoikeudet työtilaan, määritä heille Katselija-rooli. Se sallii samanlaisen vain luku -käyttöoikeuden työtilan sisältöön.
- **Käyttäjät, joilla ei ole Pro-käyttöoikeutta**, voivat käyttää työtilaa, jos työtila on Power BI Premium -kapasiteetissa, vaikka heillä olisi vain Katselija-rooli.
- **Salli käyttäjien viedä tietoja**: Käyttäjät, joilla on Katselija-rooli, voivat viedä tietoja vain siinä tapauksessa, että heillä on Koontiversio-oikeus työtilan tietojoukoille. Lue lisää [tietojoukkojen muodostamisoikeuksista](../connect-data/service-datasets-build-permissions.md).
- Ei **Poistu työtilasta** -painiketta.

### <a name="workspace-contact-list"></a>Työtilan yhteystietoluettelo

Uuden **Yhteystietoluettelo**-ominaisuuden avulla voit määrittää käyttäjät, joille ilmoitetaan työtilassa esiintyneistä ongelmista. Oletusarvon mukaan ilmoitus annetaan kaikille käyttäjille tai ryhmille, jotka on määritetty työtilan järjestelmänvalvojiksi, mutta voit mukauttaa luetteloa. Yhteystietoluettelossa luetellut käyttäjät tai ryhmät näytetään käyttöliittymässä (UI), jotta käyttäjät saavat työtilaa koskevaa apua. 

Lue lisää [työtilan yhteystietoluettelon määrittämisestä](service-create-the-new-workspaces.md#workspace-contact-list).

### <a name="workspace-onedrive"></a>Työtilan OneDrive

Työtilan OneDrive -ominaisuuden avulla voit määrittää Office 365 -ryhmän, jonka SharePoint-tiedostokirjaston tiedostosäilö on työtilan käyttäjien käytettävissä. Luot ryhmän Power BI:n ulkopuolella.

Power BI ei synkronoi niiden käyttäjien tai ryhmien käyttöoikeuksia, joille on määritetty työtilan käyttöoikeus Office 365 -ryhmän jäsenyyden yhteydessä. Paras käytäntö on hallita työtilan käyttöoikeutta saman Office 365 -ryhmän kautta, jonka tiedostosäilön määritit tässä asetuksessa. 

Lue lisää siitä, miten [voit määrittää työtilan OneDriven ja käyttää sitä](service-create-the-new-workspaces.md#workspace-onedrive).  

## <a name="roles-in-the-new-workspaces"></a>Roolit uusissa työtiloissa

Voit myöntää käyttöoikeuden uuteen työtilaan lisäämällä käyttäjäryhmiä tai henkilöitä yhteen työtilarooliin: järjestelmänvalvojat, jäsenet, osallistujat tai katselijat. Kaikki käyttäjäryhmän jäsenet saavat määrittämäsi roolin. Jos henkilö on useissa käyttäjäryhmissä, hän saa hänelle myönnettyjen roolien antaman korkeimman käyttöoikeustason.

Roolien avulla voit hallita, kuka voi tehdä mitäkin työtilassa, joten ryhmät voivat tehdä yhteistyötä. Uusissa työtiloissa voit määrittää henkilöille ja käyttäjäryhmille rooleja. Voit käyttää käyttöoikeusryhmiä, Office 365 -ryhmiä ja jakeluluetteloita. 

Kun määrität rooleja käyttäjäryhmälle, ryhmän käyttäjät voivat käyttää sisältöä. Jos asetat sisäkkäin käyttäjäryhmiä, kaikilla ryhmien käyttäjillä on käyttöoikeus.

[!INCLUDE [power-bi-workspace-roles-table](../includes/power-bi-workspace-roles-table.md)]

> [!NOTE]
> Jotta voit ottaa käyttöön rivitason suojauksen (RLS) käyttäjille, jotka selaavat sisältöä työtilassa, käytä Katselija-roolia. Jos haluat ottaa RLS:n käyttöön antamatta työtilan käyttöoikeutta, julkaise Power BI -sovellus kyseisille käyttäjille tai jakele sisältö jakamisen avulla.

## <a name="licensing"></a>Käyttöoikeudet
Jokainen jäsen, jonka lisäät työtilaan jaetussa kapasiteetissa, tarvitsee Power BI Pro -käyttöoikeuden. Työtilassa nämä käyttäjät voivat tehdä yhteistyötä niiden koontinäyttöjen ja raporttien parissa, jotka aiot julkaista laajemmalle lukijakunnalle tai jopa koko organisaatiolle. 

Jos haluat jakaa sisältöä muille organisaatiosi sisällä, voit määrittää Power BI Pro -käyttöoikeudet kyseisille käyttäjille tai sijoittaa työtilan Power BI Premium -kapasiteettiin.

Kun työtila on Power BI Premium -kapasiteetissa, Katselija-roolin saaneet käyttäjät voivat käyttää työtilaa, vaikka heillä ei olisi Power BI Pro -käyttöoikeutta. Kuitenkin, jos määrität näille käyttäjille korkeamman roolin, kuten järjestelmänvalvoja, jäsen tai osallistuja, heitä kehotetaan aloittamaan Pro-kokeilu, kun he yrittävät käyttää työtilaa. Jos haluat käyttää Katselija-roolia käyttäjille, joilla ei ole Pro-käyttöoikeutta, varmista, että heillä ei ole muita työtilarooleja, joko yksittäin tai käyttäjäryhmän kautta.

> [!NOTE]
> Nykyisiä käyttöoikeussääntöjä sovelletaan tiukemmin raporttien julkaisemiseen uuteen työtilakokemukseen. Jos yrität julkaista raportteja Power BI Desktopista tai muista asiakastyökaluista ilman Pro-käyttöoikeutta, näet virheen ”Vain käyttäjät, joilla on Power BI Pro -käyttöoikeudet, voivat julkaista tähän työtilaan”.

## <a name="administering-new-workspace-experience-workspaces"></a>Uuden työtilakokemuksen työtilojen hallinta

Uuden työtilakokemuksen työtilojen järjestelmänvalvonta tapahtuu nyt Power BI -hallinta. Power BI -järjestelmänvalvojat päättävät, kuka organisaatiossa voi luoda työtiloja ja jakaa sovelluksia. Järjestelmänvalvojat voivat tarkastella organisaatiosi kaikkien työtilojen tilaa. Järjestelmänvalvojat voivat myös hallita ja palauttaa työtiloja. Lisätietoja on hallintaportaalin artikkelissa [Uusien työtilojen luominen](../admin/service-admin-portal.md#create-the-new-workspaces).

## <a name="guest-users"></a>Vieraskäyttäjät

Oletusarvo on, että [Azure AD B2B -vieraskäyttäjät](../admin/service-admin-azure-ad-b2b.md) eivät voi käyttää työtiloja. Power BI -järjestelmänvalvoja voi [sallia, että ulkoiset vieraskäyttäjät voivat muokata ja hallita sisältöä organisaatiossa](../admin/service-admin-azure-ad-b2b.md#guest-users-who-can-edit-and-manage-content). Tällöin vieraskäyttäjä pääsee käyttämään työtiloja, joihin hänellä on lupa.

## <a name="auditing"></a>Valvonta

Power BI valvoo seuraavia uuden työtilakokemuksen työtiloja.

| Kutsumanimi | Toiminnon nimi |
|---|---|
| Luotu Power BI -kansio | CreateFolder |
| Poistettu Power BI -kansio | DeleteFolder |
| Päivitetty Power BI -kansio | UpdateFolder |
| Päivitetty Power BI -kansion käyttöoikeus| UpdateFolderAccess |

Lue lisää [Power BI:n valvonnasta](../admin/service-admin-auditing.md).

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Huomioitavia rajoituksia:

- Työtiloissa voi olla korkeintaan 1 000 tietojoukkoa tai 1 000 raporttia tietojoukkoa kohti. 
- Henkilö, jolla on Power BI Pro -käyttöoikeus, voi olla korkeintaan 1 000 työtilan jäsen.
- Power BI Publisher for Exceliä ei tueta.

## <a name="frequently-asked-questions"></a>Usein kysyttyjä kysymyksiä

**Vaikuttaako uuden työtilakokemuksen yleinen käytettävyys linkkeihin olemassa olevaan sisältöön?**

Ei. Uusi työtilakokemus ei vaikuta linkkeihin olemassa oleviin kohteisiin perinteisissä työtiloissa. Uuden työtilakokemuksen yleinen käytettävyys (GA) muuttaa luomaasi oletustyötilaa, mutta ei muuta olemassa olevia työtiloja. 

**Päivitetäänkö olemassa olevat työtilat uuteen työtilakokemukseen, johon liittyy yleinen käytettävyys (GA)?**

Ei. Uuden työtilakokemuksen yleinen käytettävyys (GA) muuttaa vain oletustyötilan tyypin uudeksi työtilakokemukseksi. Office 365 -ryhmiin perustuvia olemassa olevia perinteisiä työtiloja ei muuteta.

**Luodaanko työtiloja edelleen automaattisesti Office 365 -ryhmille?**

Kyllä. Koska tuemme kummankin tyyppistä työtilaa rinnakkain, luettelemme edelleen työtilojen luettelossa kaikki Office 365 -ryhmät, joihin käyttäjällä on käyttöoikeus.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Luo uusia työtiloja Power BI:ssä](service-create-the-new-workspaces.md)
* [Luo perinteisiä työtiloja](service-create-workspaces.md)
* [Asenna ja käytä sovelluksia Power BI:ssä](service-create-distribute-apps.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

