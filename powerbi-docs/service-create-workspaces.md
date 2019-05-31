---
title: Luo perinteinen työtilat Power BI
description: Lue, miten voit luoda työtiloja, kokoelmia koontinäyttöjen, raporttien ja Sivutettujen raporttien, joiden avulla voit kuvata organisaatiosi keskeisiä mittalukuja.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: dcf9b8befabfec98fcae154e6276f8e698b3ddc2
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61150830"
---
# <a name="create-classic-workspaces-in-power-bi"></a>Luo perinteinen työtilat Power BI

Voit luoda Power BI *työtilat*, voit tehdä yhteistyötä työtovereiden, voit luoda ja tarkentaa koontinäytöt, raportit, kokoelmia sijoittaa ja sivutetut raportit. Sitten voit niputtaa kokoelman yhdessä *sovelluksia* , jotka voit jakaa koko organisaatiolle tai tietyille henkilöille tai ryhmille. 

**Tiesitkö?** Power BI tarjoaa työtilan uuden kokemuksen, joka on nyt oletusarvo. Lue [järjestää työ uuden työtilakokemuksen](service-new-workspaces.md) uuden työtilakokemuksen lisätietoja. 

Kun luot perinteiseen työtilaan, olet luomassa pohjana, liittyvät Office 365-ryhmään. Työtilaa hallitaan Office 365:ssä. Voit lisätä työtovereita näihin työtiloihin jäseninä tai järjestelmänvalvojina. Työtilassa kaikki voivat tehdä yhteistyötä koontinäyttöjen, raporttien tai muiden artikkeleiden parissa, jotka haluat julkaista laajemmalle lukijakunnalle. Jokainen sovellustyötilaan lisätty jäsen tarvitsee Power BI Pro -käyttöoikeuden. 

## <a name="video-apps-and-app-workspaces"></a>Video: Sovellukset ja sovelluksen työtilat
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-classic-app-workspace-based-on-an-office-365-group"></a>Luo Office 365-ryhmän perusteella perinteinen sovellustyötila

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

     Kuvien tyyppi voi olla .png tai .jpg .bmp tiedostoja. Koosta voivat olla suuria-3 Mt ylös. 

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

Jos haluat virallinen sisältöä organisaation sisällä suuri yleisö, voit julkaista sovelluksen työtilasta.  Kun sisältö on valmis, valitse, mitkä koontinäytöt ja raportit haluat julkaista ja julkaise se *sovelluksen*. Voit luoda yhden sovelluksen kustakin työtilasta.

Sovellukset-luettelossa vasemmassa siirtymisruudussa näkyy asentamiasi sovelluksia. Työtoverisi voivat saada sovelluksesi käyttöönsä eri tavoin. 
- He voivat etsiä ja asentaa sovelluksesi Microsoft AppSource
- Voit lähettää heille suoran linkin. 
- Voit asentaa sen automaattisesti työtovereittesi Power BI -tileille, jos Power BI -järjestelmänvalvojasi antaa sinulle luvan. 

Käyttäjät näkevät päivitetyt sovelluksen sisältö automaattisesti, kun olet julkaissut päivitys työtilasta. Voit määrittää, kuinka usein tiedot päivitetään asettamalla päivitysaikataulu käyttää sovelluksen sisällön työtilan tietojoukot. Katso [Julkaise Power BI-sovelluksen uuden työtilakokemuksen](service-create-distribute-apps.md) lisätietoja.

## <a name="power-bi-classic-apps-faq"></a>Power BI perinteinen sovellusten usein kysytyt kysymykset

### <a name="how-are-apps-different-from-organizational-content-packs"></a>Miten sovellukset eroavat organisaation sisältöpaketeista?
Sovellukset ovat organisaation sisältöpakettien seuraava kehitysaste. Jos sinulla on jo organisaation sisältöpaketteja, ne toimivat edelleen rinnakkain sovellusten kanssa. Sovelluksilla ja sisältöpaketeilla on muutamia merkittäviä eroja. 

* Kun yrityskäyttäjät ovat asentaneet sisältöpaketin, se menettää ryhmäidentiteettinsä: se on vain luettelo koontinäyttöjä ja raportteja, jotka ovat sikin sokin muiden koontinäyttöjen ja raporttien keskellä. Sovellukset taas säilyttävätä ryhmityksensä ja identiteettinsä jopa asennuksen jälkeen. Tämän ryhmityksen ansiosta yrityskäyttäjien on helpompi siirtyä niihin myöhemminkin.
* Voit luoda useita sisältöpaketteja mistä tahansa työtilasta, mutta sovelluksella on 1:1-suhde työtilansa kanssa. 
* Ajan mittaan aiomme lakkauttaa organisaation sisältöpaketit, joten suosittelemme, että luot tästä lähtien sovelluksia.  
* Uuden työtilan kokemuksen esikatselun myötä siirrymme kohti organisaation sisältöpakettien poistamista käytöstä. Ei voi käyttää tai luoda niitä esiversion työtiloissa.

Voit verrata näitä kahta tutustumalla artikkeliin [Miten uudet sovellustyötilat eroavat nykyisistä sovellustyötiloista?](service-new-workspaces.md#how-are-the-new-workspaces-different-from-current-workspaces). 

## <a name="next-steps"></a>Seuraavat vaiheet
* [Asenna ja käytä sovelluksia Power BI:ssä](service-create-distribute-apps.md)
- [Uusien työtilojen luominen (esiversio)](service-create-the-new-workspaces.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
