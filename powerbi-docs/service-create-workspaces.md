---
title: Perinteisten työtilojen luominen Power BI:ssä
description: Lue, miten luodaan työtiloja, raporttinäkymien kokoelmia, raportteja ja sivutettuja raportteja, joiden avulla voit kuvata organisaatiosi keskeisiä mittalukuja.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/12/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 0bb8d796af5139cd89f4bdfa0a8da10603acb2ed
ms.sourcegitcommit: 4d5166944fcc6fe4666cab055ae75e7a0a77866d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2019
ms.locfileid: "69530574"
---
# <a name="create-classic-workspaces-in-power-bi"></a>Perinteisten työtilojen luominen Power BI:ssä

Voit luoda Power BI:ssä *työtiloja*. Ne ovat paikkoja, joissa voit yhteistyössä työtovereiden kanssa luoda ja tarkentaa raporttinäkymien, raporttien ja sivutettujen raporttien kokoelmia. Niputa sitten kokoelma yhteen *sovelluksiin*, joita voit jakaa koko organisaatiolle tai tietyille henkilöille tai ryhmille. 

**Tiesitkö?** Power BI tarjoaa uuden työtilakokemuksen, jota käytetään nyt oletuksena. Katso lisätietoja uusista työtiloista artikkelista [Työn järjestäminen uusissa työtiloissa](service-new-workspaces.md). 

Kun luot perinteisen työtilan, luot taustalla toimivan, työtilaan liitetyn Office 365 -ryhmän. Työtilaa hallitaan Office 365:ssä. Voit lisätä työtovereita näihin työtiloihin jäseninä tai järjestelmänvalvojina. Työtilassa kaikki voivat tehdä yhteistyötä koontinäyttöjen, raporttien tai muiden artikkeleiden parissa, jotka haluat julkaista laajemmalle lukijakunnalle. Jokainen sovellustyötilaan lisätty jäsen tarvitsee Power BI Pro -käyttöoikeuden. 

## <a name="video-apps-and-app-workspaces"></a>Video: Sovellukset ja sovelluksen työtilat
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-classic-app-workspace-based-on-an-office-365-group"></a>Office 365 -ryhmään perustuvan perinteisen sovellustyötilan luominen

Kun luot sovellustyötilan, se perustuu Office 365 -ryhmään.

[!INCLUDE [powerbi-service-create-app-workspace](./includes/powerbi-service-create-app-workspace.md)]

Kun luot sen, saatat joutua odottamaan noin tunnin verran, että työtila välittää sen Office 365:een. 

### <a name="add-an-image-to-your-office-365-app-workspace-optional"></a>Kuvan lisääminen Office 365:n sovellustyötilaan (valinnainen)
Oletusarvoisesti Power BI luo sovelluksellesi pienen värillisen ympyrän, jossa näkyy sovelluksen nimikirjaimet. Saatat kuitenkin haluta mukauttaa sitä käyttämällä jotain kuvaa. Kuvan lisäämiseksi tarvitset Exchange Online -käyttöoikeuden.

1. Valitse **Työtilat**, valitse työtilan nimen vierestä kolme pistettä (...), ja valitse sitten **Jäsenet**. 
   
     ![Työtilan jäsenten valitseminen](media/service-create-distribute-apps/power-bi-apps-workspace-members.png)
   
    Työtilan Office 365 Outlook -tili aukeaa uuteen selainikkunaan.
2. Kun pidät hiiren osoitinta vasemman yläkulman värillisen ympyrän päällä, se muuttuu kynäkuvakkeeksi. Valitse se.
   
     ![Office 365:n kynäkuvake](media/service-create-distribute-apps/power-bi-apps-workspace-edit-image.png)
3. Valitse kynäkuvake uudelleen, ja etsi kuva, jota haluat käyttää.
   
     ![Valitse kynä uudelleen](media/service-create-distribute-apps/power-bi-apps-workspace-edit-group.png)

     Kuvat voivat olla .png-, .jpg- tai .bmp-tiedostoja. Tiedostokoko voi olla suuri, enintään 3 megatavua. 

4. Valitse **Tallenna**.
   
     ![Valitse Tallenna](media/service-create-distribute-apps/power-bi-apps-workspace-save-image.png)
   
    Kuvan korvaa värillisen ympyrän Office 365:n Outlook-ikkunassa. 
   
     ![Mukautettu kuva](media/service-create-distribute-apps/power-bi-apps-workspace-image-in-office-365.png)
   
    Muutaman minuutin kuluttua se näkyy myös sovelluksessa Power BI:ssä.
   
     ![Mukautettu kuva](media/service-create-distribute-apps/power-bi-apps-image.png)

## <a name="add-content-to-your-app-workspace"></a>Sisällön lisääminen sovellustyötilaan

Kun olet luonut sovellustyötilan, on aika lisätä siihen sisältöä. Lisääminen toimii samaan tapaan kuin sisällön lisääminen Omaan työtilaan, paitsi että myös työtilan muut ihmiset pystyvät näkemään sen ja työstämään sitä. Suurin ero on, että kun saat sen valmiiksi, voit julkaista sisällön sovelluksena. Kun sisältöä tarkastellaan sovellustyötilan sisältöluettelossa, sovellustyötilan nimenä näkyy omistajan nimi.

### <a name="connect-to-third-party-services-in-app-workspaces"></a>Yhteyden muodostaminen kolmannen osapuolen palveluihin sovellustyötiloissa

Sovellukset toimitetaan kaikille kolmannen osapuolen palveluille, joita Power BI tukee. Sen ansiosta saat helposti tiedot käyttämistäsi palveluista, kuten Microsoft Dynamics CRM:stä, Salesforcesta tai Google Analyticsista. Voit julkaista organisaation sovellukset, jotta käyttäjät pääsevät käyttämään tarvitsemiansa tietoja.

Nykyisissä työtiloissa voit myös muodostaa yhteyden käyttämällä organisaation sisältöpaketteja ja kolmannen osapuolen sisältöpaketteja, kuten Microsoft Dynamics CRM, Salesforce tai Google Analytics. Harkitse organisaation sisältöpakettien siirtämistä sovelluksiin.

## <a name="distribute-an-app"></a>Sovelluksen jakaminen

Jos haluat levittää virallista sisältöä suurelle yleisölle organisaatiossasi, voit julkaista sovelluksen työtilasta.  Kun sisältö on valmis, valitse julkaistaviksi haluamasi raporttinäkymät ja raportit ja julkaise se *sovelluksena*. Voit luoda yhden sovelluksen kustakin työtilasta.

Vasemman navigoinnin sovellusluettelossa näkyvät kaikki asentamasi sovellukset. Työtoverisi voivat saada sovelluksesi käyttöönsä eri tavoin. 
- He voivat etsiä ja asentaa sovelluksen Microsoft AppSourcesta
- Voit lähettää heille suoran linkin. 
- Voit asentaa sen automaattisesti työtovereittesi Power BI -tileille, jos Power BI -järjestelmänvalvojasi antaa sinulle luvan. 

Käyttäjät näkevät päivitetyn sovellussisällön automaattisesti sen jälkeen, kun olet julkaissut päivityksen työtilasta. Voit määrittää, kuinka usein tiedot päivitetään. Määritä päivitysaikataulu tietojoukoille, joita sovellussisältö käyttää työtilassa. Lisätietoja on kohdassa [Sovelluksen julkaiseminen uusista työtiloista Power BI:ssä](service-create-distribute-apps.md).

## <a name="power-bi-classic-apps-faq"></a>Power BI:n perinteisten sovellusten usein kysytyt kysymykset

### <a name="how-are-apps-different-from-organizational-content-packs"></a>Miten sovellukset eroavat organisaation sisältöpaketeista?
Sovellukset ovat organisaation sisältöpakettien seuraava kehitysaste. Jos sinulla on jo organisaation sisältöpaketteja, ne toimivat edelleen rinnakkain sovellusten kanssa. Sovelluksilla ja sisältöpaketeilla on muutamia merkittäviä eroja. 

* Kun yrityskäyttäjät ovat asentaneet sisältöpaketin, se menettää ryhmäidentiteettinsä: se on vain luettelo koontinäyttöjä ja raportteja, jotka ovat sikin sokin muiden koontinäyttöjen ja raporttien keskellä. Sovellukset taas säilyttävätä ryhmityksensä ja identiteettinsä jopa asennuksen jälkeen. Tämän ryhmityksen ansiosta yrityskäyttäjien on helpompi siirtyä niihin myöhemminkin.
* Voit luoda useita sisältöpaketteja mistä tahansa työtilasta, mutta sovelluksella on 1:1-suhde työtilansa kanssa. 
* Ajan mittaan aiomme lakkauttaa organisaation sisältöpaketit, joten suosittelemme, että luot tästä lähtien sovelluksia.  
* Uuden työtilan kokemuksen esikatselun myötä siirrymme kohti organisaation sisältöpakettien poistamista käytöstä. Ei voi käyttää tai luoda niitä esiversion työtiloissa.

Voit verrata näitä kahta tutustumalla artikkeliin [Miten uudet sovellustyötilat eroavat nykyisistä sovellustyötiloista?](service-new-workspaces.md#how-the-new-workspaces-are-different). 

## <a name="next-steps"></a>Seuraavat vaiheet
* [Asenna ja käytä sovelluksia Power BI:ssä](service-create-distribute-apps.md)
- [Uusien työtilojen luominen (esiversio)](service-create-the-new-workspaces.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
