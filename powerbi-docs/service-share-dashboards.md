---
title: Power BI -koontinäyttöjen ja -raporttien jakaminen työtovereiden ja muiden kanssa
description: Miten voit jakaa Power BI -koontinäytöt ja -raportit työtovereiden kanssa organisaatiosi sisä- ja ulkopuolella ja mitä sinun pitää tietää jakamisesta.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/24/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d82b03325991276924f25da5511baadfe53127e1
ms.sourcegitcommit: f05ba39a0e46cb9cb43454772fbc5397089d58b4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/26/2019
ms.locfileid: "68522992"
---
# <a name="share-power-bi-dashboards-and-reports-with-coworkers-and-others"></a>Power BI -koontinäyttöjen ja -raporttien jakaminen työtovereiden ja muiden kanssa
*Jakaminen* on kätevä keino myöntää parille henkilölle käyttöoikeus luomiisi koontinäyttöihin ja raportteihin. Power BI tarjoaa myös [useita muita tapoja tehdä yhteistyötä ja jakaa koontinäyttöjä ja raportteja](service-how-to-collaborate-distribute-dashboards-reports.md).

![Kuvakkeen jakaminen suosituimpien koontinäyttöjen luettelossa](media/service-share-dashboards/power-bi-share-dash-report-favorites.png)

Kun jaat sisältöä organisaatiosi sisä- tai ulkopuolella, tarvitset jakamiseen [Power BI Pro -käyttöoikeuden](service-features-license-type.md). Vastaanottajasi tarvitsevat myös Power BI Pro -käyttöoikeudet, ellei sisältö ole [Premium-tasoista](service-premium-what-is.md). 

Voit jakaa koontinäyttöjä ja raportteja useimmista paikoista Power BI -palvelussa: Suosikit, Viimeaikaiset, Jaettu kanssani (jos omistaja sallii sen), Oma työtila tai muut työtilat. Kun jaat koontinäytön tai raportin, niiden vastaanottajat voivat tarkastella ja käsitellä niitä, mutta eivät voi muokata niitä. He näkevät samat tiedot kuin sinä koontinäytössä tai raportissa, ellei sovelleta [rivitason suojausta (RLS)](service-admin-rls.md). Työtoverit, joille tiedot jaat, voivat myös jakaa niitä omien työtovereidensa kanssa, jos sallit sen. Organisaatiosi ulkopuoliset henkilöt voivat myös tarkastella ja käsitellä koontinäyttöä tai raporttia, mutta eivät voi jakaa sitä. 

Voit myös [jakaa koontinäytön mistä tahansa Power BI -mobiilisovelluksesta](consumer/mobile/mobile-share-dashboard-from-the-mobile-apps.md). Koontinäyttöjä ei kuitenkaan voi jakaa Power BI Desktopista.

## <a name="video-share-a-dashboard"></a>Video: Jaa koontinäyttö
Katso, miten Amanda jakaa koontinäyttönsä työtovereiden kanssa yrityksensä sisä- ja ulkopuolella. Kokeile sitten itse noudattamalla videon alapuolella olevia vaiheittaisia ohjeita.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard-or-report"></a>Koontinäytön tai raportin jakaminen

1. Valitse koontinäyttöjen tai raporttien luettelossa tai avatussa koontinäytössä tai raportissa **Jaa** ![Jaa-kuvake](media/service-share-dashboards/power-bi-share-icon.png).

2. Kirjoita yläreunan ruutuun henkilöiden, jakeluryhmien tai käyttöoikeusryhmien koko sähköpostiosoitteet. Et voi jakaa sisältöä dynaamisten jakeluluetteloiden kanssa. 
   
   Voit jakaa sisältöä organisaatiosi ulkopuolisten henkilöiden kanssa, mutta näyttöön tulee varoitus.
   
   ![Varoitus jakamisesta ulkoisesti](media/service-share-dashboards/power-bi-share-dialog-warning.png) 
 
   >[!NOTE]
   >Syöteruutu tukee enintään 100 käyttäjää tai ryhmää. Jos haluat jakaa useille käyttäjille, voit luoda koontinäytön työtilaan ja [jakaa sen sovelluksena](service-create-distribute-apps.md).
   > 
   > 


3. Voit lisätä halutessasi viestin, mutta se on valinnaista.
4. Jotta työtoverisi voivat jakaa sisältöäsi muiden kanssa, valitse **Salli vastaanottajien jakaa koontinäyttösi (tai raporttisi)** .
   
   Kun sallit muiden jakaa sisältöäsi, tätä kutsutaan *uudelleenjakamiseksi*. Jos sallit sen, he voivat jakaa sisältöäsi uudelleen Power BI -palvelusta ja -mobiilisovelluksista tai välittää sähköpostikutsun organisaation muille käyttäjille. Kutsu vanhenee kuukauden kuluttua. Organisaatiosi ulkopuoliset henkilöt eivät voi jakaa sisältöä uudelleen. Voit sisällön omistajana poistaa uudelleenjakamisen käytöstä tai palauttaa uudelleenjakamisen yksilökohtaisesti. Katso [Jakamisen lopettaminen tai muiden jakamisen estäminen](#stop-sharing-or-stop-others-from-sharing).

5. Valitse **Jaa**.
   
   ![Jaa-painikkeen valitseminen](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Power BI lähettää sähköpostikutsun henkilöille, mutta ei ryhmien, yhdessä linkin kanssa jaettuun sisältöön. Näet **Onnistui**-ilmoituksen. 
   
   Kun organisaatiossasi olevat vastaanottajat napsauttavat linkkiä, Power BI lisää koontinäytön tai raportin vastaanottajien **Jaettu kanssani** -luettelosivulle. He voivat valita nimesi, jotta he näkevät kaiken sisällön, jonka olet jakanut heidän kanssaan. 
   
   ![Jaettu kanssani -luettelosivu](media/service-share-dashboards/power-bi-shared-with-me-dashboards-reports.png)
   
   Kun organisaatiosi ulkopuoliset vastaanottajat napsauttavat linkkiä, he näkevät koontinäytön tai raportin, mutta eivät tavallista Power BI -portaalia. Lisätietoja on kohdassa [Koontinäytön tai raportin jakaminen organisaatiosi ulkopuolisten henkilöiden kanssa](#share-a-dashboard-or-report-with-people-outside-your-organization).

## <a name="who-has-access-to-a-dashboard-or-report-you-shared"></a>Kenellä on oikeus käyttää jakamaasi koontinäyttöä tai raporttia?
Toisinaan sinun on nähtävä henkilöt, joiden kanssa olet jakanut sisältöä, sekä se, kenen kanssa he ovat jakaneet sisältöä:

1. Valitse koontinäyttöjen ja raporttien luettelosta tai itse koontinäytöstä tai raportista **Jaa** ![Jaa-kuvake](media/service-share-dashboards/power-bi-share-icon.png). 
2. Valitse **Jaa koontinäyttö** tai **Jaa raportti** -valintaikkunassa **Käytä**.
   
    ![Jaa koontinäyttö -valintaikkuna, Käytä-välilehti](media/service-share-dashboards/power-bi-share-dialog-access.png)

    Organisaatiosi ulkopuoliset henkilöt on lueteltu **vieraana**.

## <a name="stop-sharing-or-stop-others-from-sharing"></a>Jakamisen lopettaminen tai muiden jakamisen estäminen
Vain koontinäytön tai raportin omistaja voi ottaa uudelleenjakamisen käyttöön ja poistaa sen käytöstä.

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>Jos et ole lähettänyt vielä jakamiskutsua
* Tyhjennä **Salli vastaanottajien jakaa koontinäyttösi (tai raporttisi)** -valintaruutu kutsun alareunasta ennen sen lähettämistä.

### <a name="if-youve-already-shared-the-dashboard-or-report"></a>Jos olet jo jakanut koontinäytön tai raportin
1. Valitse koontinäyttöjen ja raporttien luettelosta tai itse koontinäytöstä tai raportista **Jaa** ![Jaa-kuvake](media/service-share-dashboards/power-bi-share-icon.png). 
2. Valitse **Jaa koontinäyttö** tai **Jaa raportti** -valintaikkunassa **Käytä**.
   
    ![Jaa koontinäyttö -valintaikkuna, Käytä-välilehti](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. Valitse kolme pistettä ( **...** ) kohdan **Lue ja jaa uudelleen** vierestä ja valitse:
   
   ![Lue ja jaa uudelleen, kolme pistettä](media/service-share-dashboards/power-bi-change-access.png)
   
   * **Lue**, jotta tämä henkilö ei voi jakaa sisältöä kenenkään muun kanssa.
   * **Poista käyttöoikeus** estää tätä henkilöä näkemästä jaettua sisältöä ollenkaan.

4. Voit **Poista käyttöoikeus** -valintaikkunassa päättää, haluatko poistaa käyttöoikeuden myös liittyvään sisältöön, kuten raportteihin ja tietojoukkoihin. Jos poistat kohteet, joissa on ![Power BI -varoituskuvake](media/service-share-dashboards/power-bi-warning-icon.png), sinun kannattaa poistaa myös liittyvä sisältö, koska se ei näy oikein.

    ![Power BI:n jakamisen varoitusvalintaikkuna](media/service-share-dashboards/power-bi-sharing-warning-dialog.png)

## <a name="share-a-dashboard-or-report-with-people-outside-your-organization"></a>Koontinäytön tai raportin jakaminen organisaatiosi ulkopuolisten henkilöiden kanssa
Kun jaat sisältöä organisaatiosi ulkopuolisten henkilöiden kanssa, he saavat sähköpostiviestin ja linkin jaettuun koontinäyttöön tai raporttiin. Jos he haluavat tarkastella tätä sisältöä, heidän on kirjauduttava sisään Power BI -palveluun. Jos heillä ei ole Power BI Pro -käyttöoikeutta, he voivat rekisteröityä käyttöoikeuden saamiseksi napsautettuaan linkkiä.

Kun he ovat kirjautuneet sisään, he näkevät jaetun koontinäytön tai raportin sen omassa selainikkunassa, eivät tavanomaisessa Power BI -portaalissaan. Jos haluat myöhemmin käyttää tätä koontinäyttöä tai raporttia, heidän on lisättävä linkki kirjanmerkkeihin.

He eivät voi muokata mitään tämän koontinäytön tai raportin sisältöä. Vaikka he voivat käsitellä kaavioita ja muuttaa suodattimia tai osittajia, he eivät voi tallentaa tekemiään muutoksia. 

Vain suorat vastaanottajasi voivat nähdä jaetun koontinäytön tai raportin. Jos lähetit esimerkiksi sähköpostiviestin Vicki@contoso.comlle, vain Vicki voi nähdä koontinäytön. Kukaan muu ei voi tarkastella koontinäyttöä, vaikka hänellä olisi linkki. Vickin on käytettävä sitä samalla sähköpostiosoitteella. Jos joku rekisteröityy käyttäen jotakin toista sähköpostiosoitetta, hänellä ei ole käyttöoikeutta koontinäyttöön.

Organisaatiosi ulkopuoliset henkilöt eivät näe mitään tietoja, jos rooli - tai rivitason suojausta sovelletaan paikallisiin Analysis Services -taulukkomalleihin.

Jos lähetit linkin Power BI -mobiilisovelluksesta organisaatiosi ulkopuolisille henkilöille, linkkiä napsauttamalla koontinäyttö avautuu selaimessa eikä Power BI -mobiilisovelluksessa.

Jos [sallit ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa](service-admin-portal.md#export-and-sharing-settings), vain kuluttajakokemuksen salliva oletusasetus ei koske heitä. [Lue lisää](service-admin-azure-ad-b2b.md).

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat
Kun jaat koontinäyttöjä ja raportteja, ota huomioon seuraavat seikat:

* Työtoverisi näkevät yleensä samat tiedot kuin sinä koontinäytössä ja raportissa. Näin ollen jos sinulla on käyttöoikeus nähdä enemmän tietoja kuin työtoverisi, he näkevät kaikki tietosi koontinäytössä tai raportissa. Kuitenkin jos [rivitason suojausta (RLS)](service-admin-rls.md) sovelletaan koontinäytön tai raportin pohjana olevaan tietojoukkoon, jokaisen henkilön tunnistetietoja käytetään sen määrittämiseen, mitä tietoja he voivat käyttää.
* Kaikki, joiden kanssa jaat koontinäyttösi, voivat tarkastella sitä ja käsitellä siihen liittyviä raportteja [lukunäkymässä](consumer/end-user-reading-view.md#reading-view). He eivät voi luoda raportteja tai tallentaa muutoksia aiemmin luotuihin raportteihin.
* Vaikka kukaan ei voi tarkastella tai ladata tietojoukkoa, he voivat käyttää tietojoukkoa suoraan Analysoi Excelissä -ominaisuuden avulla. Järjestelmänvalvoja voi rajoittaa käyttäjien kykyä käyttää Analysoi Excelissä -ominaisuutta ryhmän kaikkien jäsenten osalta. Rajoitus koskee kuitenkin kaikkia kyseisessä ryhmässä jokaisessa työtilassa, johon ryhmä kuuluu.
* Kaikki voivat manuaalisesti [päivittää tietoja](refresh-data.md).
* Jos käytät Office 365:n sähköpostia, voit jakaa tietoja jakeluryhmän jäsenten kanssa antamalla jakeluryhmään liittyvän sähköpostiosoitteen.
* Työtoverit, joilla on sama sähköpostin toimialue kuin sinulla, ja työtoverit, joiden toimialue on erilainen, mutta joka on rekisteröity samassa vuokraajassa, voivat jakaa koontinäytön muiden kanssa. Jos esimerkiksi contoso.com-ja contoso2.com-toimialueet on rekisteröity samassa vuokraajassa ja sähköpostiosoitteesi on konrads@contoso.com, molemmat ravali@contoso.com ja gustav@contoso2.com voivat jakaa samaa, kunhan annoit heille luvan jakamiseen.
* Jos työtovereillasi on jo käyttöoikeus tiettyyn koontinäyttöön tai raporttiin, voit lähettää suoran linkin kopioimalla URL-osoitteen, kun olet koontinäytössä tai raportissa. Esimerkiksi: `https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx`
* Samoin jos työtovereillasi on jo käyttöoikeus tiettyyn koontinäyttöön, voit [lähettää suoran linkin pohjana olevaan raporttiin](service-share-reports.md). 
* Yhdellä jakamistoiminnolla voit jakaa enintään 100 käyttäjälle tai ryhmälle. Voit kuitenkin antaa yli 500 käyttäjälle kohteen käyttöoikeuden. Voit tehdä tämän joko jakamalla useita kertoja, niin että määrität käyttäjät yksitellen, tai jakamalla käyttäjäryhmälle, joka sisältää kaikki käyttäjät.

## <a name="troubleshoot-sharing"></a>Jakamisen vianmääritys

### <a name="my-dashboard-recipients-see-a-lock-icon-in-a-tile-or-a-permission-required-message"></a>Koontinäyttöni vastaanottajat näkevät lukkokuvakkeen ruudussa tai ”Käyttöoikeus pakollinen” -viestin

Henkilöt, joiden kanssa jaat tietoja, saattavat nähdä lukitun ruudun koontinäytössä tai ”Käyttöoikeus pakollinen” -viestin, kun he yrittävät tarkastella raporttia.

![Power BI:n lukittu ruutu](media/service-share-dashboards/power-bi-locked_tile_small.png)

Jos ruutu on lukittu, sinun on myönnettävä käyttöoikeus pohjana olevaan tietojoukkoon:

1. Siirry sisältöluettelossa **Tietojoukot**-välilehteen.

1. Valitse kolme pistettä ( **...** ) tietojoukon vieressä ja valitse sitten **Käyttöoikeuksien hallinta**.

    ![Käyttöoikeuksien hallinta](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

1. Valitse **Lisää käyttäjä**.

    ![Lisää käyttäjä -komennon valitseminen](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. Kirjoita henkilöiden, jakeluryhmien tai käyttöoikeusryhmien koko sähköpostiosoitteet. Et voi jakaa sisältöä dynaamisten jakeluluetteloiden kanssa.

    ![Sähköpostiosoitteiden lisääminen](media/service-share-dashboards/power-bi-add-user-dataset.png)


1. Valitse **Lisää**.

### <a name="i-cant-share-a-dashboard-or-report"></a>En voi jakaa koontinäyttöä tai raporttia

Jotta voit jakaa koontinäytön tai raportin, tarvitset käyttöoikeuden jakaa uudelleen pohjana olevaa sisältöä eli kaikkia siihen liittyviä raportteja ja tietojoukkoja. Jos näyttöön tulee viesti, jonka mukaan et voi jakaa tietoja, pyydä raportin laatijaa myöntämään sinulle käyttöoikeus näihin raportteihin ja tietojoukkoihin.

![Jakaminen ei onnistu -sanoma](media/service-share-dashboards/power-bi-sharing-unable-to-share.png)


## <a name="next-steps"></a>Seuraavat vaiheet
* Haluatko antaa palautetta? Anna ehdotuksia siirtymällä [Power BI -yhteisön sivustolle](https://community.powerbi.com/).
* [Miten voin työstää koontinäyttöjä ja raportteja yhdessä muiden kanssa sekä jakaa niitä?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Suodatetun Power BI -raportin jakaminen](service-share-reports.md)
* Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/).

