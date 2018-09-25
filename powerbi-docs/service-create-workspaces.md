---
title: Työtilojen luominen työtovereiden kanssa Power BI:ssä
description: Lue, miten luodaan työtiloja, jotka ovat raporttinäkymien ja raporttien kokoelmia, joiden avulla voit kuvata organisaatiosi keskeisiä mittalukuja.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/06/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: b40933e085cf81528a28e9eedb4260351f657323
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/21/2018
ms.locfileid: "46548392"
---
# <a name="create-workspaces-with-your-colleagues-in-power-bi"></a>Työtilojen luominen työtovereiden kanssa Power BI:ssä

Voit luoda Power BI:ssä *työtiloja*. Ne ovat paikkoja, joissa voit yhteistyössä työtovereiden kanssa luoda ja tarkentaa raporttinäkymien ja raporttien kokoelmia. Sen jälkeen voit paketoit ne yhteen *sovelluksiksi*, jotka voit jakaa koko organisaatiolle tai tietyille henkilöille tai ryhmille. 

![Power BI -sovellukset](media/service-create-workspaces/power-bi-apps-left-nav.png)

Kun luot työtilan, luot taustalla toimivan, työtilaan liitetyn Office 365 -ryhmän. Työtilaa hallitaan Office 365:ssä. Voit lisätä työtovereita näihin työtiloihin jäseninä tai järjestelmänvalvojina. Työtilassa kaikki voivat tehdä yhteistyötä raporttinäkymien, raporttien tai muiden artikkeleiden parissa, jotka halutaan julkaista laajemmalle lukijakunnalle. Jokainen sovellustyötilaan lisätty jäsen tarvitsee Power BI Pro -käyttöoikeuden. 

**Tiesitkö?** Power BI:ssä esikatsellaan uutta työtilakokemusta. Lisätietoja työtilojen muuttumisesta tulevaisuudessa on artikkelissa [Uusien työtilojen luominen (esiversio)](service-create-the-new-workspaces.md). 

## <a name="video-apps-and-app-workspaces"></a>Video: Sovellukset ja sovelluksen työtilat
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="create-an-app-workspace-based-on-an-office-365-group"></a>Office 365 -ryhmään perustuvan sovellustyötilan luominen

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

Nykyisissä työtiloissa voit myös muodostaa yhteyden organisaation sisältöpaketteihin ja kolmannen osapuolen sisältöpaketteihin, kuten Microsoft Dynamics CRM:ään, Salesforceen tai Google Analyticsiin. Harkitse organisaation sisältöpakettien siirtämistä sovelluksiin.

## <a name="distribute-an-app"></a>Sovelluksen jakaminen

Kun sisältö on valmis, valitset, mitkä raporttinäkymät ja raportit haluat julkaista, ja sitten julkaiset sen *sovelluksena*. Työtoverisi saavat sovelluksesi käyttöönsä eri tavoin. Voit asentaa ne automaattisesti työtovereittesi Power BI -tileille, jos Power BI -järjestelmänvalvojasi antaa sinulle luvan. Muussa tapauksessa he voivat hakea ja asentaa sovelluksesi Microsoft AppSourcesta tai voit lähettää heille suoran linkin. He saavat päivitykset automaattisesti, ja sinä voit määrittää, kuinka usein tiedot päivitetään. Lisätietoja on artikkelissa [Raporttinäkymiä ja raportteja sisältävien sovellusten julkaiseminen Power BI:ssä](consumer/end-user-create-apps.md).

## <a name="power-bi-apps-faq"></a>Power BI -sovellusten usein kysytyt kysymykset

### <a name="how-are-apps-different-from-organizational-content-packs"></a>Miten sovellukset eroavat organisaation sisältöpaketeista?
Sovellukset ovat organisaation sisältöpakettien seuraava kehitysaste. Jos sinulla on jo organisaation sisältöpaketteja, ne toimivat edelleen rinnakkain sovellusten kanssa. Sovelluksilla ja sisältöpaketeilla on muutamia merkittäviä eroja. 

* Kun yrityskäyttäjät ovat asentaneet sisältöpaketin, se menettää ryhmäidentiteettinsä: se on vain luettelo koontinäyttöjä ja raportteja, jotka ovat sikin sokin muiden koontinäyttöjen ja raporttien keskellä. Sovellukset taas säilyttävätä ryhmityksensä ja identiteettinsä jopa asennuksen jälkeen. Tämän ansiosta yrityskäyttäjien on helpompi käyttää niitä myöhemminkin.
* Voit luoda useita sisältöpaketteja mistä tahansa työtilasta, mutta sovelluksella on 1:1-suhde työtilansa kanssa. 
* Ajan mittaan aiomme lakkauttaa organisaation sisältöpaketit, joten suosittelemme, että luot tästä lähtien sovelluksia.  
* Uuden työtilakokemuksen esiversion myötä siirrymme kohti organisaation sisältöpakettien poistamista käytöstä. Ei voi käyttää tai luoda niitä esiversion työtiloissa.

Voit verrata nykyisiä ja uusia sovellustyötiloja tutustumalla artikkeliin [Miten uudet sovellustyötilat eroavat nykyisistä sovellustyötiloista?](service-create-the-new-workspaces.md#how-are-the-new-app-workspaces-different-from-current-app-workspaces). 

## <a name="next-steps"></a>Seuraavat vaiheet
* [Asenna ja käytä sovelluksia Power BI:ssä](consumer/end-user-apps.md)
* [Power BI -sovellukset ulkoisille palveluille](consumer/end-user-connect-to-services.md)
- [Uusien työtilojen luominen (esiversio)](service-create-the-new-workspaces.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
