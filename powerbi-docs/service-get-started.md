---
title: Power BI -palvelun käytön aloittaminen
description: Power BI -palvelun käytön aloittaminen
author: adamw
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: d66653ebe9232cb6da2f3c53b01e791ca9966db9
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34310126"
---
# <a name="get-started-with-power-bi-service-apppowerbicom"></a>Power BI -palvelun (app.powerbi.com) käytön aloittaminen
Tämä opasohjelma auttaa ***Power BI -palvelun*** aloittamisessa. Suosittelemme lukemaan [Mikä Power BI on](guided-learning/gettingstarted.yml?tutorial-step=1) -ohjeartikkelin, jotta saat käsityksen, miten Power BI -palvelu sopii yhteen muiden Power BI -tuotteiden kanssa.

![Desktopin, palvelun ja mobiilisovelluksen eroja esittävä kuva](media/service-get-started/power-bi-components.png)

Power BI -palvelusta on maksuton versio ja Pro-versio. *Jos sinulla on jo tili*, avaa Power BI -palvelu avaamalla selain ja kirjoittamalla app.powerbi.com käyttämästäsi versiosta riippumatta. Jos olet uusi käyttäjä, suosittelemme aloittamaan osoitteesta www.powerbi.com. Se sisältää lisätietoja Power BI:stä ennen palveluun kirjautumista.  Kun olet valmis kokeilemaan palvelua, napsauta oikeassa yläkulmassa näkyvää **Ilmainen rekisteröityminen** -linkkiä. Jos järjestelmänvalvoja on jo ottanut Power BI:n käyttöön puolestasi, älä käytä Ilmainen rekisteröityminen -painiketta, vaan siirry suoraan osoitteeseen app.powerbi.com. 

![Kirjautuminen tai Ilmainen rekisteröityminen](media/service-get-started/power-bi-sign-up.png)

Jos etsit ohjeita Power BI Desktopin käyttöön, lue [Desktopin käytön aloittamisen](desktop-getting-started.md) ohjeet. Jos etsit ohjeita Power BI -mobiilisovelluksen käyttöön, katso [Power BI -sovellukset mobiililaitteille](mobile-apps-for-mobile-devices.md) -ohjeet.

> [!TIP]
> Haluaisitko mieluummin maksuttoman, omaan tahtiin käytävän harjoituskurssin? [Rekisteröidy Datan analysointi ja visualisointi -kurssille EdX:ssa](http://aka.ms/edxpbi).

Tutustu [YouTube-soittolistaamme](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP). Suosittelemme aloittamaan videosta, jonka nimi on Johdanto Power BI -palveluun:
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 
> 
> 

Microsoft Power BI auttaa sinua pysymään ajan tasalla sinua kiinnostavista asioista.  Power BI -palvelun ***koontinäytöt*** auttavat sinua pitämään yrityksesi langat käsissäsi.  Koontinäytöissä näytetään ***ruutuja***, joita napsauttamalla voit avata ***raportteja*** tarkempaa tutustumista varten.  Yhdistä useisiin ***tietojoukkoihin*** ja kerää kaikki tarvittavat tiedot samaan paikkaan. Tarvitsetko apua Power BI:n rakenneosien kanssa?  Katso [Power BI - peruskäsitteet](service-basic-concepts.md).

Jos sinulla on tärkeitä tietoja Excel- tai CSV-tiedostoissa, voit luoda Power BI -koontinäytön, jotta voit jakaa merkityksellisiä tietoja muiden kanssa ja pysyä ajan tasalla missä ikinä oletkin.  Onko sinulla SaaS-sovellustilaus, kuten Salesforce?  Ota varaslähtö yhdistämällä Salesforceen ja luo koontinäyttö automaattisesti sen tiedoista tai [Tutustu muihin SaaS-sovelluksiin](service-get-data.md), joihin voit muodostaa yhteyden. Jos kuulut johonkin organisaatioon, katso, onko sinua varten julkaistu [sovelluksia](service-create-distribute-apps.md).

Lue muista tavoista, joilla voit [hakea tietoja Power BI:hin](service-get-data.md).

## <a name="step-1-get-data"></a>Vaihe 1: Tietojen hakeminen
Tämä on esimerkki tietojen hakemisesta CSV-tiedostosta. Haluatko noudattaa tätä opasohjelmaa? [Lataa CSV-esimerkkitiedosto](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Kirjaudu sisään Power BI:hin](http://www.powerbi.com/). Eikö sinulla ole tiliä? Ei huolta, voit rekisteröityä maksutta.
2. Power BI avautuu selaimessa. Valitse vasemman siirtymisruudun alareunasta **Hae tiedot**.
   
   ![hae tiedot](media/service-get-started/getdata3.png)
3. Valitse **Tiedostot**. 
   
   ![hae tiedostot](media/service-get-started/gs1.png)
4. Etsi tiedosto tietokoneeltasi ja valitse **Avaa**. Jos tallensit sen OneDrive for Businessiin, valitse kyseinen vaihtoehto. Jos tallensit sen paikallisesti, valitse **Paikallinen tiedosto**. 
   
   ![Hae tiedot > Tiedostot-näyttö](media/service-get-started/gs2.png)
5. Tätä opasohjelmaa varten lisäämme tietojoukkona käytettävän Excel-tiedoston jota voimme käyttää raporttien ja koontinäyttöjen luomiseen. Aloitetaan valitsemalla **Tuo**. Jos valitset **Lataa**, koko Excel-työkirja ladataan Power BI:hin, jossa voit avata ja muokata sitä Excel Onlinella.
   
   ![valitse Tuo](media/service-get-started/power-bi-import.png)
6. Kun tietojoukkosi on valmis, valitse **Tarkastele tietojoukkoa** avataksesi sen raporttieditorissa. 

    ![Tietojoukkosi on valmis -valintaikkuna](media/service-get-started/power-bi-gs.png)

    Koska emme ole vielä luoneet visualisointeja, raporttipohja on tyhjä.

    ![tyhjä raporttipohja](media/service-get-started/power-bi-report-editor.png)

6. Tutustu yläreunan valikkoriviin. Huomaa siellä oleva **Lukunäkymä**-vaihtoehto. Lukunäkymä-vaihtoehdon näkyminen tarkoittaa, että olet tällä hetkellä **Muokkausnäkymässä**. 

    ![Lukunäkymä-vaihtoehto](media/service-get-started/power-bi-editing-view.png)

    Muokkausnäkymässä voit luoda ja muokata raportteja, sillä raportin *omistajana* olet myös raportin *luoja*. Kun jaat raportin työtovereiden kanssa, he voivat käsitellä raporttia ainoastaan lukunäkymässä; he ovat *kuluttajia*. Lue lisätietoja [Lukunäkymästä ja Muokkausnäkymästä](service-reading-view-and-editing-view.md).
    
    Voit tutustua raporttieditoriin kätevästi [aloittamalla esittelyn](service-the-report-editor-take-a-tour.md)
   > 
 

## <a name="step-2-start-exploring-your-dataset"></a>Vaihe 2: Aloita tietojoukkoosi tutustuminen
Nyt kun olet muodostanut yhteyden tietoihin, voit aloittaa tutustumisen.  Kun olet löytänyt jotain mielenkiintoista, voit luoda koontinäytön valvoaksesi sitä ja nähdäksesi, miten se muuttuu ajan mittaan. Katsotaan, miten tämä toimii.
    
1. Käytämme raporttieditorissa **Kentät**-paneelia sivun oikealla puolella visualisoinnin muodostamiseen.  Valitse vieressä oleva valintaruutu **Bruttomyynti**- ja **Päivämäärä**-kohdan vierestä.
   
   ![Kentät-luettelo](media/service-get-started/fields.png)

2. Power BI analysoi tiedot ja luo visualisoinnin.  Jos valitsit ensin **Päivämäärä**, näet taulukon.  Jos valitsit ensin **Bruttomyynti**, näet taulukon. Valitse erilainen tietojen esitystapa. Tarkastellaan näitä tietoja viivakaaviona. Valitse viivakaaviokuvake (tunnetaan myös mallina) **Visualisoinnit-ruudusta**.
   
   ![raporttieditori, jossa kuvake on valittuna](media/service-get-started/gettingstart5new.png)

3. Tämä näyttää mielenkiintoiselta, joten *kiinnitetään* se koontinäyttöön. Osoita kiinnitettävää visualisointia ja napsauta **Kiinnitä**-kuvaketta.  Kun kiinnität visualisoinnin, se tallennetaan koontinäyttöön ja pidetään ajan tasalla, jotta voit seurata viimeisimpiä arvoja yhdellä silmäyksellä.
   
   ![kiinnitä-kuvake](media/service-get-started/pinnew.png)

5. Koska kyseessä on uusi raportti, sinua pyydetään tallentamaan se ennen kuin voit kiinnittää visualisoinnin koontinäyttöön. Anna raportille nimi (esim. *Myynti ajan kuluessa*) ja valitse **Tallenna ja jatka**. 
   
   ![Raportin tallentaminen -valintaikkuna](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
6. Kiinnitetään viivakaavio uuteen koontinäyttöön ja annetaan sen nimeksi ”Talousmalli opetusohjelmaa varten”. 
   
   ![anna raportille nimi](media/service-get-started/power-bi-pin.png)
   
 1. Valitse **Kiinnitä**.
   
    Onnistumissanoma (oikean yläkulman lähellä) ilmaisee, että visualisointi lisättiin ruutuna koontinäyttöön.
   
    ![Kiinnitetty koontinäyttöön -valintaikkuna](media/service-get-started/power-bi-pin-success.png)

8. Voit tarkastella uuteen koontinäyttöösi ruutuna kiinnitettyä viivakaaviota valitsemalla **Siirry koontinäyttöön**. Voit parantaa koontinäyttöä entisestään lisäämällä visualisointiruutuja ja [nimeämällä ruutuja uudelleen, muuttamalla niiden kokoa, linkittämällä niitä ja muuttamalla niiden sijaintia](service-dashboard-edit-tile.md).
   
   ![koontinäyttö, johon on kiinnitetty visualisointi](media/service-get-started/power-bi-new-dashboard.png)
   
   Voit palata raporttiin milloin tahansa valitsemalla koontinäytön uuden ruudun. Power BI palauttaa sinut raporttieditorin lukunäkymään. Voit palata muokkausnäkymään valitsemalla **Muokkaa raporttia** yläreunan valikkorivistä. Kun olet muokkausnäkymässä, jatka tutkimista ja ruutujen kiinnittämistä. 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>Vaihe 3: Jatka tutustumista Q&A:lla (luonnollisenkielinen kysely)
1. Voit tutkia tietoja nopeasti esittämällä kysymyksen Q&A-ruutuun. Q&A-kysymysruutu sijaitsee koontinäytön yläreunassa (**Kysy kysymys tiedoistasi**) ja raportin yläreunan valikkorivissä (**Kysy kysymys**). Yritä esimerkiksi kirjoittaa ”mistä segmentistä tuli paras tuotto”.
   
   ![Q&A-pohja](media/service-get-started/powerbi-qna.png)

2. Q&A etsii vastauksen ja näyttää sen visualisointina. Valitse Kiinnitä-kuvake ![kiinnitä-kuvake](media/service-get-started/pbi_pinicon.png) näyttääksesi tämän visualisoinnin myös omalla koontinäytölläsi.
3. Kiinnitä visualisointi ”Talousmalli opetusohjelmaa varten” -koontinäyttöön.
   
    ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-get-started/power-bi-pin2.png)

4. Palaa koontinäytön, jossa näet uuden ruudun.

   ![koontinäyttö, jossa on kiinnitettynä kaavio](media/service-get-started/power-bi-final-dashboard.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Oletko valmis kokeilemaan lisää?  Alla on joitakin käteviä tapoja tutkia Power BI:tä.

* [Yhteyden muodostaminen toiseen tietojoukkoon](service-get-data.md).
* [Koontinäytön jakaminen](service-share-dashboards.md) työtovereidesi kanssa.
* [Vinkkejä koontinäyttöjen suunnitteluun](service-dashboards-design-tips.md).
* Koontinäyttöjen tarkastelu [Power BI -mobiilisovelluksessa](mobile-apps-for-mobile-devices.md)

Etkö ole vielä valmis hyppäämään mukaan? Aloita näistä otsikoista, jotka on suunniteltu tutustuttamaan Power BI:hin.

* [Lue, miten raportit, tietojoukot, koontinäytöt ja ruudut sopivat yhteen](service-basic-concepts.md)
* Tutustu [Power BI:n ohjattu oppiminen](guided-learning/index.md) -sivustoon ja käy muutamia (hyvin lyhyitä) kursseja
* Katso joitakin [Power BI -videoita](videos.md)
* [Katso, millaisia malleja käytössäsi on](sample-datasets.md)

### <a name="stay-in-touch-with-power-bi"></a>Pidä yhteyttä Power BI:n avulla
* Seuraa [@MSPowerBI Twitterissä](https://twitter.com/mspowerbi)
* Tilaa Microsoftin [YouTube-videokanava](https://www.youtube.com/channel/UCy--PYvwBwAeuYaR8JLmrfg)
* Katso Microsoftin [Power BI:n Aloitusopas -webinaari](webinars.md) suoratoistona
* Etkö ole varma, mistä hakea apua? Tutustu [10 vinkkiä ohjeiden hakemiseen](service-tips-for-finding-help.md) -sivuumme

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

