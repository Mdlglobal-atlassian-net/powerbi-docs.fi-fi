---
title: Power BI -palvelun käytön aloittaminen
description: Power BI -verkkopalvelun (app.powerbi.com) käytön aloittaminen
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/06/2019
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 007819ead82f558efa8179a49dfba9454558dfbb
ms.sourcegitcommit: d12bc6df16be1f1993232898f52eb80d0c9fb04e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/13/2019
ms.locfileid: "68995183"
---
# <a name="tutorial-get-started-with-the-power-bi-service-apppowerbicom"></a>Opetusohjelma: Power BI -palvelun (app.powerbi.com) käytön aloittaminen
Tämä opetusohjelma neuvoo *Power BI -palvelun* käytön aloittamisessa. Suosittelemme lukemaan [Mikä Power BI on](power-bi-overview.md) -ohjeartikkelin, jotta saat käsityksen, miten Power BI -palvelu sopii yhteen muiden Power BI -tuotteiden kanssa.

![Power BI Desktopin, palvelun ja mobiilisovelluksen suhde](media/service-get-started/power-bi-components.png)

Tässä opetusohjelmassa käyt läpi seuraavat vaiheet:

> [!div class="checklist"]
> * Etsi aloittamista käsittelevää sisältöä Power BI -palvelulle.
> * Kirjaudu sisään Power BI Online -tilillesi tai rekisteröi tili, jos sinulla ei vielä sitä ole.
> * Avaa Power BI -palvelu.
> * Hae tietoja ja avaa ne raporttinäkymässä.
> * Käytä näitä tietoja visualisointien luomiseksi ja tallenna ne raporttina.
> * Luo koontinäyttö kiinnittämällä ruudut raportista.
> * Lisää toinen visualisointi koontinäyttöön luonnollisenkielisen Q&A-työkalun avulla.
> * Tyhjennä resurssit poistamalla tietojoukko, raportti ja koontinäyttö.

## <a name="sign-up-for-the-power-bi-service"></a>Rekisteröidy Power BI -palveluun
Jos sinulla ei ole Power BI -tiliä, [rekisteröidy ilmaiseen Power BI Pro -kokeiluversioon](https://app.powerbi.com/signupredirect?pbi_source=web), ennen kuin aloitat.

Kun sinulla on tili, avaa Power BI -palvelu kirjoittamalla selaimeen *app.powerbi.com*. 

Jos etsit ohjeita Power BI Desktopin käyttöön, lue [Power BI Desktopin käytön aloittamisen](desktop-getting-started.md) ohjeet. Jos etsit ohjeita Power BI -mobiilisovelluksen käyttöön, katso [Power BI -sovellukset mobiililaitteille](consumer/mobile/mobile-apps-for-mobile-devices.md) -ohjeet.

> [!TIP]
> Haluaisitko mieluummin maksuttoman, omaan tahtiin käytävän harjoituskurssin? [Rekisteröidy Datan analysointi ja visualisointi -kurssille EdX:ssa](http://aka.ms/edxpbi).

Tutustu [YouTube-soittolistaamme](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP). Suosittelemme aloittamaan videosta, jonka nimi on *Johdanto Power BI -palveluun*:
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 

## <a name="what-is-the-power-bi-service"></a>Mikä Power BI -palvelu on?
Microsoft Power BI -palveluun viitataan joskus nimellä Power BI Online tai app.powerbi.com. Power BI auttaa sinua pysymään ajan tasalla sinua kiinnostavista asioista. Power BI -palvelun *raporttinäkymät* auttavat sinua pitämään yrityksesi langat käsissäsi. Koontinäytöissä näytetään *ruutuja*, jotka valitsemalla voit avata *raportteja* tarkempaa tutustumista varten. Yhdistä useisiin *tietojoukkoihin* ja kerää kaikki tarvittavat tiedot samaan paikkaan. Tarvitsetko apua Power BI:n rakenneosien kanssa? Lue [Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md).

Jos sinulla on tärkeitä tietoja Excel- tai CSV-tiedostoissa, voit luoda Power BI -koontinäytön, jotta voit jakaa merkityksellisiä tietoja muiden kanssa ja pysyä ajan tasalla missä ikinä oletkin.  Onko sinulla SaaS-sovellustilaus, kuten Salesforce?  Ota varaslähtö yhdistämällä Salesforceen ja luo koontinäyttö automaattisesti sen tiedoista tai [Tutustu muihin SaaS-sovelluksiin](service-get-data.md), joihin voit muodostaa yhteyden. Jos kuulut organisaatioon, katso, onko sinua varten julkaistu [sovelluksia](service-create-distribute-apps.md).

Lue muista tavoista, joilla voit [hakea tietoja Power BI:hin](service-get-data.md).

## <a name="step-1-get-data"></a>Vaihe 1: Nouda tiedot
Tämä on esimerkki tietojen hakemisesta CSV-tiedostosta. Haluatko noudattaa tätä opasohjelmaa? [Lataa talousmallin CSV-tiedosto](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Kirjaudu sisään Power BI:hin](http://www.powerbi.com/). Eikö sinulla ole tiliä? Ei huolta, voit rekisteröityä ilmaiseen kokeiluversioon.
2. Power BI avautuu selaimessa. Valitse vasemman siirtymisruudun alareunasta **Nouda tiedot**.

    **Nouda tiedot** -sivu avautuu.   

3. Valitse **Luo uutta sisältöä** -kohdasta **Tiedostot**. 
   
   ![Hae tiedostot](media/service-get-started/gs1.png)
4.  Valitse **Paikallinen tiedosto**.
   
     ![Hae tiedot > Tiedostot-näyttö](media/service-get-started/gs2.png)

5. Etsi tiedosto tietokoneeltasi ja valitse **Avaa**.

5. Tätä opetusohjelmaa varten lisäämme tietojoukkona käytettävän Excel-tiedoston, jota voimme käyttää raporttien ja koontinäyttöjen luomiseen. Aloitetaan valitsemalla **Tuo**. Jos valitset **Lataa**, koko Excel-työkirja ladataan Power BI:hin, jossa voit avata ja muokata sitä Excel Onlinella.
   
   ![Valitse Tuo](media/service-get-started/power-bi-import.png)
6. Kun tietojoukkosi on valmis, valitse **Tarkastele tietojoukkoa** avataksesi sen raporttieditorissa. 

    ![Tietojoukkosi on valmis -valintaikkuna](media/service-get-started/power-bi-gs.png)

    Koska emme ole vielä luoneet visualisointeja, raporttipohja on tyhjä.

    ![Tyhjä raporttipohja](media/service-get-started/power-bi-report-editor.png)

7. Huomaa, että yläreunan siirtymispalkissa on vaihtoehto **lukunäkymää** varten. Koska tämä vaihtoehto on käytettävissä, olet tällä hetkellä muokkausnäkymässä. 

    ![Lukunäkymä-vaihtoehto](media/service-get-started/power-bi-editing-view.png)

    Muokkausnäkymässä voit luoda ja muokata raportteja, sillä olet raportin *omistaja*. Olet siis *tekijä*. Kun jaat raportin työtovereiden kanssa, he voivat käsitellä raporttia ainoastaan lukunäkymässä; he ovat *kuluttajia*. Lue lisätietoja [Lukunäkymästä ja Muokkausnäkymästä](consumer/end-user-reading-view.md).
    
    Voit tutustua raporttieditoriin kätevästi [aloittamalla esittelyn](service-the-report-editor-take-a-tour.md).
 

## <a name="step-2-start-exploring-your-dataset"></a>Vaihe 2: Aloita tietojoukkoosi tutustuminen
Nyt kun olet muodostanut yhteyden tietoihin, voit aloittaa tutustumisen.  Kun olet löytänyt jotain mielenkiintoista, voit luoda koontinäytön valvoaksesi sitä ja nähdäksesi, miten se muuttuu ajan mittaan. Katsotaan, miten tämä toimii.
    
1. Käytämme raporttieditorissa **Kentät**-paneelia sivun oikealla puolella visualisoinnin muodostamiseen. Valitse **Bruttomyynti**- ja **Päivämäärä**-valintaruudut.
   
   ![Kentät-luettelo](media/service-get-started/fields.png)

    Power BI analysoi tiedot ja luo visualisoinnin. Jos valitsit ensin **Päivämäärä**, näet taulukon. Jos valitsit ensin **Bruttomyynti**, näet kaavion. 

2. Valitse erilainen tietojen esitystapa. Tarkastellaan näitä tietoja viivakaaviona. Valitse **Visualisoinnit**-ruudusta viivakaavion kuvake.
   
   ![Raporttieditori, jossa viivakaavio on valittuna](media/service-get-started/gettingstart5new.png)

3. Tämä kaavio näyttää mielenkiintoiselta, joten *kiinnitetään* se raporttinäkymään. Osoita kiinnitettävää visualisointia ja napsauta Kiinnitä-kuvaketta. Kun kiinnität visualisoinnin, se tallennetaan koontinäyttöön ja pidetään ajan tasalla, jotta voit seurata viimeisimpiä arvoja yhdellä silmäyksellä.
   
   ![Kiinnitä-kuvake](media/service-get-started/pinnew.png)

4. Koska kyseessä on uusi raportti, sinua pyydetään tallentamaan se, ennen kuin voit kiinnittää visualisoinnin koontinäyttöön. Anna raportille nimi (esimerkiksi *Myynti ajan kuluessa*) ja valitse **Tallenna ja jatka**. 
   
   ![Raportin tallentaminen -valintaikkuna](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
5. Kiinnitä viivakaavio uuteen koontinäyttöön ja anna sen nimeksi *Talousmalli opetusohjelmaa varten*. 
   
   ![Anna raportille nimi](media/service-get-started/power-bi-pin.png)
   
6. Valitse **Kiinnitä**.
   
    Onnistumisesta kertova ilmoitus (oikean yläkulman lähellä) ilmaisee, että visualisointi lisättiin ruutuna koontinäyttöön.
   
    ![Kiinnitetty koontinäyttöön -valintaikkuna](media/service-get-started/power-bi-pin-success.png)

7. Voit tarkastella uuteen koontinäyttöösi ruutuna kiinnitettyä viivakaaviota valitsemalla **Siirry koontinäyttöön**. Voit parantaa koontinäyttöä entisestään lisäämällä visualisointiruutuja ja [nimeämällä ruutuja uudelleen, muuttamalla niiden kokoa, linkittämällä niitä ja muuttamalla niiden sijaintia](service-dashboard-edit-tile.md).
   
   ![Koontinäyttö, johon on kiinnitetty visualisointi](media/service-get-started/power-bi-new-dashboard.png)
   
8. Voit palata raporttiin valitsemalla raporttinäkymän uuden ruudun. Power BI palauttaa sinut raporttieditorin lukunäkymään. Voit palata muokkausnäkymään valitsemalla **Muokkaa raporttia** yläreunan siirtymispalkista. Kun olet muokkausnäkymässä, voit jatkaa ruutujen tarkastelemista ja kiinnittämistä. 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>Vaihe 3:  Jatka tutustumista Q&A:lla (luonnollisella kielellä kirjoitettu kysely)
1. Voit tutkia tietoja nopeasti esittämällä kysymyksen Q&A-ruutuun. Q&A-kysymysruutu sijaitsee koontinäytön yläreunassa (**Kysy kysymys tiedoistasi**) ja raportin yläreunan siirtymispalkissa (**Kysy kysymys**). Kirjoita Q&A-ruutuun esimerkiksi *mistä segmentistä tuli paras tuotto*.
   
   ![Q&A-pohja](media/service-get-started/powerbi-qna.png)

2. Q&A etsii vastauksen ja näyttää sen visualisointina. Valitse Kiinnitä-kuvake ![Kiinnitä-kuvake](media/service-get-started/pbi_pinicon.png) näyttääksesi tämän visualisoinnin omalla koontinäytölläsi.
3. Kiinnitä visualisointi **Talousmalli opetusohjelmaa varten** -koontinäyttöön.
   
    ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-get-started/power-bi-pin2.png)

4. Palaa koontinäyttöön, jossa näet uuden ruudun.

   ![Koontinäyttö, jossa on kiinnitettynä kaavio](media/service-get-started/power-bi-final-dashboard.png)

## <a name="clean-up-resources"></a>Resurssien tyhjentäminen
Nyt kun olet suorittanut opetusohjelman, voit poistaa tietojoukon, raportin ja koontinäytön. 

1. Valitse vasemmassa siirtymispalkissa **Oma työtila**.
2. Valitse **Tietojoukot**-välilehti ja etsi tätä opetusohjelmaa varten tuotu tietojoukko.  
3. Valitse kolme pistettä (...) > **Poista**.

    ![Tietojoukon poistaminen](media/service-get-started/power-bi-delete.jpg)

    Kun poistat tietojoukon, Power BI poistaa myös raportin ja koontinäytön. 


## <a name="next-steps"></a>Seuraavat vaiheet

> [!div class="nextstepaction"]
> [Käyttämiesi online-palveluiden yhdistäminen Power BI:hin](service-connect-to-services.md)

