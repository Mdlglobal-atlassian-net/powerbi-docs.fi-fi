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
ms.openlocfilehash: cb4fdeeea228d388197c35c69d934c0bf04c8033
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66374692"
---
# <a name="share-power-bi-dashboards-and-reports-with-coworkers-and-others"></a>Power BI -koontinäyttöjen ja -raporttien jakaminen työtovereiden ja muiden kanssa
*Jakaminen* on kätevä keino myöntää parille henkilölle käyttöoikeus luomiisi koontinäyttöihin ja raportteihin. Power BI tarjoaa myös [useita muita tapoja tehdä yhteistyötä ja jakaa koontinäyttöjä ja raportteja](service-how-to-collaborate-distribute-dashboards-reports.md).

![Kuvakkeen jakaminen suosituimpien koontinäyttöjen luettelossa](media/service-share-dashboards/power-bi-share-dash-report-favorites.png)

Kun jaat sisältöä organisaatiosi sisä- tai ulkopuolella, tarvitset jakamiseen [Power BI Pro -käyttöoikeuden](service-features-license-type.md). Vastaanottajasi tarvitsevat myös Power BI Pro-käyttöoikeudet, ellei sisältö [Premium-kapasiteettiin](service-premium-what-is.md). 

Voit jakaa koontinäyttöjä ja raportteja Power BI-palvelun useimmista paikoista: Suosikit, viimeisimmät, jaettu kanssani (Jos omistaja sallii sen), oma työtila tai muut työtilat. Kun jaat koontinäytön tai raportin, niiden vastaanottajat voivat tarkastella ja käsitellä niitä, mutta eivät voi muokata niitä. He näkevät samat tiedot kuin sinä koontinäytössä tai raportissa, ellei sovelleta [rivitason suojausta (RLS)](service-admin-rls.md). Työtoverit, joille tiedot jaat, voivat myös jakaa niitä omien työtovereidensa kanssa, jos sallit sen. Voit organisaation ulkopuolisille henkilöille myös tarkastella ja käsitellä koontinäyttöä tai raporttia, mutta eivät jakaa sitä. 

Voit myös [jakaa koontinäytön mistä tahansa Power BI -mobiilisovelluksesta](consumer/mobile/mobile-share-dashboard-from-the-mobile-apps.md). Voi kuitenkin jakaa koontinäyttöjä Power BI Desktop-kohteesta.

## <a name="video-share-a-dashboard"></a>Video: Jaa koontinäyttö
Katso, miten Amanda jakaa koontinäyttönsä työtovereiden kanssa yrityksensä sisä- ja ulkopuolella. Kokeile sitä itse noudattamalla videon alapuolella olevia vaiheittaisia ohjeita.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard-or-report"></a>Koontinäytön tai raportin jakaminen

1. Valitse koontinäyttöjen tai raporttien luettelossa tai avatussa koontinäytössä tai raportissa **Jaa** ![Jaa-kuvake](media/service-share-dashboards/power-bi-share-icon.png).

2. Kirjoita yläreunan ruutuun henkilöiden, jakeluryhmien tai käyttöoikeusryhmien koko sähköpostiosoitteet. Et voi jakaa sisältöä dynaamisten jakeluluetteloiden kanssa. 
   
   Voit jakaa sisältöä organisaatiosi ulkopuolisten henkilöiden kanssa, mutta näyttöön tulee varoitus.
   
   ![Varoitus jakamisesta ulkoisesti](media/service-share-dashboards/power-bi-share-dialog-warning.png) 
 
   >[!NOTE]
   >Tekstisyötteen ruutu tukee enintään 100 käyttäjille tai ryhmille. Jos haluat jakaa suurten kanssa, sinun kannattaa luoda koontinäytön työtilassa ja [sen jakamista sovelluksena](service-create-distribute-apps.md).
   > 
   > 


3. Voit lisätä halutessasi viestin, mutta se on valinnaista.
4. Jotta työtoverisi voivat jakaa sisältöäsi muiden kanssa, valitse **Salli vastaanottajien jakaa koontinäytön (tai raportin)** .
   
   Kun sallit muiden jakaa sisältöäsi, tätä kutsutaan *uudelleenjakamiseksi*. Jos sallit sen, he voivat jakaa sisältöäsi uudelleen Power BI -palvelusta ja -mobiilisovelluksista tai välittää sähköpostikutsun organisaation muille käyttäjille. Kutsu vanhenee kuukauden kuluttua. Organisaatiosi ulkopuoliset henkilöt eivät voi jakaa sisältöä uudelleen. Voit sisällön omistajana poistaa uudelleenjakamisen käytöstä tai palauttaa uudelleenjakamisen yksilökohtaisesti. Katso [jakamisen lopettaminen tai muiden jakamisen](#stop-sharing-or-stop-others-from-sharing).

5. Valitse **Jaa**.
   
   ![Jaa-painikkeen valitseminen](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Power BI lähettää sähköpostikutsun henkilöille, mutta ei ryhmien, jossa on linkki jaettua sisältöä. Näet **Onnistui**-ilmoituksen. 
   
   Kun organisaatiossasi olevat vastaanottajat napsauttavat linkkiä, Power BI lisää koontinäytön tai raportin vastaanottajien **Jaettu kanssani** -luettelosivulle. He voivat valita nimesi, jotta he näkevät kaiken sisällön, jonka olet jakanut heidän kanssaan. 
   
   ![Jaettu kanssani -luettelosivu](media/service-share-dashboards/power-bi-shared-with-me-dashboards-reports.png)
   
   Kun organisaatiosi ulkopuoliset vastaanottajat napsauttavat linkkiä, he näkevät koontinäytön tai raportin, mutta eivät tavallista Power BI -portaalia. Jos haluat lisätietoja, katso [koontinäytön tai raportin jakaminen organisaatiosi ulkopuolisten henkilöiden](#share-a-dashboard-or-report-with-people-outside-your-organization).

## <a name="who-has-access-to-a-dashboard-or-report-you-shared"></a>Kenellä on oikeus käyttää jakamaasi koontinäyttöä tai raporttia?
Joskus tarvitset henkilöt, joiden kanssa olet jakanut ja nähdä ne olet jakanut sen kanssa:

1. Valitse koontinäyttöjen ja raporttien luettelosta tai itse koontinäytöstä tai raportista **Jaa** ![Jaa-kuvake](media/service-share-dashboards/power-bi-share-icon.png). 
2. Tässä **Jaa koontinäyttö** tai **jakaa raportin** valintaikkunasta **Access**.
   
    ![Jaa koontinäyttö -valintaikkuna, Käytä-välilehti](media/service-share-dashboards/power-bi-share-dialog-access.png)

    Organisaatiosi ulkopuoliset henkilöt on lueteltu **vieraana**.

## <a name="stop-sharing-or-stop-others-from-sharing"></a>Jakamisen lopettaminen tai muiden jakamisen estäminen
Vain koontinäytön tai raportin omistaja voi ottaa uudelleenjakamisen käyttöön ja poistaa sen käytöstä.

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>Jos et ole lähettänyt vielä jakamiskutsua
* Tyhjennä **Salli vastaanottajien jakaa koontinäytön (tai raportin)** valintaruutu kutsun ennen sen lähettämistä alareunassa.

### <a name="if-youve-already-shared-the-dashboard-or-report"></a>Jos olet jo jakanut koontinäytön tai raportin
1. Valitse koontinäyttöjen ja raporttien luettelosta tai itse koontinäytöstä tai raportista **Jaa** ![Jaa-kuvake](media/service-share-dashboards/power-bi-share-icon.png). 
2. Tässä **Jaa koontinäyttö** tai **jakaa raportin** valintaikkunasta **Access**.
   
    ![Jaa koontinäyttö -valintaikkuna, Käytä-välilehti](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. Valitse kolme pistettä ( **...** ) kohdan **Lue ja jaa uudelleen** vierestä ja valitse:
   
   ![Lue ja jaa uudelleen, kolme pistettä](media/service-share-dashboards/power-bi-change-access.png)
   
   * **Lue**, jotta tämä henkilö ei voi jakaa sisältöä kenenkään muun kanssa.
   * **Poista käyttöoikeus** estää tätä henkilöä näkemästä jaettua sisältöä ollenkaan.

4. Tässä **poistaa käyttöoikeuden** valintaikkunassa päättää, jos haluat poistaa oikeuden liittyvään sisältöön, kuten raportteihin ja tietojoukkoihin. Jos poistat kohteet, joilla varoituskuvake ![Power BI-varoituskuvake](media/service-share-dashboards/power-bi-warning-icon.png), kannattaa poistaa liittyvä sisältö myös, koska se ei näy oikein.

    ![Power BI:n jakamisen varoitusvalintaikkuna](media/service-share-dashboards/power-bi-sharing-warning-dialog.png)

## <a name="share-a-dashboard-or-report-with-people-outside-your-organization"></a>Koontinäytön tai raportin jakaminen organisaatiosi ulkopuolisten henkilöiden kanssa
Kun jaat muille organisaatiosi ulkopuolella, he saavat sähköpostiviestin, jossa on linkki jaetun koontinäytön tai raportin, jossa ne on kirjauduttava sisään Power BI Nähdäksesi. Jos heillä ei ole Power BI Pro -käyttöoikeutta, he voivat rekisteröityä käyttöoikeuden saamiseksi napsautettuaan linkkiä.

Kun hän kirjautuu sisään, he näkevät jaetun koontinäytön tai raportin sen omassa selainikkunassa, eivät tavanomaisessa Power BI-portaalissaan. Jos haluat käyttää tämän koontinäytön tai raportin myöhemmin, ne on Lisää linkki kirjanmerkkeihin.

He eivät voi muokata mitään tämän koontinäytön tai raportin sisältöä. Vaikka he voivat käsitellä kaavioita ja muuttaa suodattimia tai osittajia, hän ei voi tallentaa tekemiään muutoksia. 

Vain suorat vastaanottajasi voivat nähdä jaetun koontinäytön tai raportin. Jos lähetit esimerkiksi sähköpostiviestin Vicki@contoso.comlle, vain Vicki voi nähdä koontinäytön. Kukaan muu ei voi nähdä koontinäytön, vaikka heillä olisi linkki. Vickin on käytettävä samaa sähköpostiosoitetta käyttämään sitä. Jos hän rekisteröityy jollakin muulla sähköpostiosoitteella, hän ei ole käyttää tätä koontinäyttöä.

Organisaatiosi ulkopuoliset eivät näe mitään tietoja, jos rooli - tai rivitason suojausta sovelletaan paikallisiin Analysis Services-taulukkomalleihin.

Jos lähetät linkin Power BI-mobiilisovelluksesta henkilöille organisaatiosi ulkopuolella, linkin napsauttaminen avaa koontinäytön selaimessa, eikä Power BI-mobiilisovelluksessa.

Jos olet [avulla ulkoinen vieraskäyttäjien muokkaaminen ja hallinta organisaatiossa](service-admin-portal.md#export-and-sharing-settings), vain kulutus oletuskokemuksen ei koske ne. [Lue lisää](service-admin-azure-ad-b2b.md).

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat
Kun jaat koontinäyttöjä ja raportteja, ota huomioon seuraavat seikat:

* Työtoverisi näkevät yleensä samat tiedot kuin sinä koontinäytössä ja raportissa. Näin ollen jos sinulla on käyttöoikeus nähdä enemmän tietoja kuin työtoverisi, he näkevät kaikki tietosi koontinäytössä tai raportissa. Kuitenkin jos [rivitason suojausta (RLS)](service-admin-rls.md) sovelletaan koontinäytön tai raportin pohjana olevaan tietojoukkoon, jokaisen henkilön tunnistetietoja käytetään sen määrittämiseen, mitä tietoja he voivat käyttää.
* Kaikki jakaisit koontinäyttösi ja tarkastella sitä ja käsitellä siihen liittyviä raportteja [lukunäkymässä](consumer/end-user-reading-view.md#reading-view). He eivät voi luoda raportteja tai tallentaa muutoksia aiemmin luotuihin raportteihin.
* Vaikka kukaan voit tarkastella tai ladata tietojoukon, he voivat käyttää tietojoukon suoraan avulla analysoi Excelissä-ominaisuuden. Järjestelmänvalvoja voi rajoittaa mahdollisuus käyttää analysoi Excelissä-kaikille ryhmän jäsenille. Rajoitus koskee kuitenkin kaikkia kyseisessä ryhmässä jokaisessa työtilassa, johon ryhmä kuuluu.
* Kaikki voivat manuaalisesti [päivittää tietoja](refresh-data.md).
* Jos käytät Office 365:n sähköpostia, voit jakaa tietoja jakeluryhmän jäsenten kanssa antamalla jakeluryhmään liittyvän sähköpostiosoitteen.
* Työtoverit, joilla jakaminen sähköpostisi toimialueeseen, ja työtoverit, joiden toimialue on erilainen, mutta se on rekisteröity samassa vuokraajassa, voit jakaa koontinäytön muiden kanssa. Esimerkiksi jos toimialueet contoso.com ja contoso2.com on rekisteröity samassa vuokraajassa ja sähköpostiosoitteesi on konrads@contoso.com, sekä ravali@contoso.com ja gustav@contoso2.com jakaa, kun olet antanut heille oikeuden jakamiseen.
* Jos työtovereillasi on jo käyttöoikeus tiettyyn koontinäyttöön tai raporttiin, voit lähettää suoran linkin kopioimalla URL-osoite, kun olet koontinäytössä tai raportissa. Esimerkiksi: `https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx`
* Samoin jos työtovereillasi on jo käyttöoikeus tiettyyn koontinäyttöön, voit [lähettää suoran linkin pohjana olevaan raporttiin](service-share-reports.md). 
* Voit jakaa, enintään 100 käyttäjät tai ryhmät yksittäisen jakamistoiminto. Voit kuitenkin antaa yli 500 käyttäjälle kohteen käyttöoikeuden. Voit tehdä jakaa useita kertoja määrittämällä käyttäjät erikseen tai jakaa käyttäjäryhmä, joka sisältää kaikkien käyttäjien kanssa.

## <a name="troubleshoot-sharing"></a>Jakamisen vianmääritys

### <a name="my-dashboard-recipients-see-a-lock-icon-in-a-tile-or-a-permission-required-message"></a>Koontinäyttöni vastaanottajat näkevät lukkokuvakkeen ruudussa tai ”Käyttöoikeus pakollinen” -viestin

Henkilöt, joiden kanssa jaat tietoja, saattavat nähdä lukitun ruudun koontinäytössä tai ”Käyttöoikeus pakollinen” -viestin, kun he yrittävät tarkastella raporttia.

![Power BI:n lukittu ruutu](media/service-share-dashboards/power-bi-locked_tile_small.png)

Jos siis haluat myöntää käyttöoikeudet pohjana olevaan tietojoukkoon:

1. Siirry sisältöluettelossa **Tietojoukot**-välilehteen.

1. Valitse kolme pistettä ( **...** ) tietojoukon, valitse **käyttöoikeuksien hallinta**.

    ![Käyttöoikeuksien hallinta](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

1. Valitse **Lisää käyttäjä**.

    ![Lisää käyttäjä -komennon valitseminen](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. Kirjoita henkilöiden, jakeluryhmien tai käyttöoikeusryhmien koko sähköpostiosoitteet. Et voi jakaa sisältöä dynaamisten jakeluluetteloiden kanssa.

    ![Sähköpostiosoitteiden lisääminen](media/service-share-dashboards/power-bi-add-user-dataset.png)


1. Valitse **Lisää**.

### <a name="i-cant-share-a-dashboard-or-report"></a>En voi jakaa koontinäyttöä tai raporttia

Jos haluat jakaa koontinäytön tai raportin, tarvitset käyttöoikeuden jakaa uudelleen pohjana olevaan sisältöön; eli kaikkia siihen liittyviä raportteja ja tietojoukkoja. Jos näyttöön sanoma, et voi jakaa, pyydä raportin antaa jakaa käyttöoikeutta näihin raportteihin ja tietojoukkoihin.

![Jakaminen ei onnistu -sanoma](media/service-share-dashboards/power-bi-sharing-unable-to-share.png)


## <a name="next-steps"></a>Seuraavat vaiheet
* Haluatko antaa palautetta? Anna ehdotuksia siirtymällä [Power BI -yhteisön sivustolle](https://community.powerbi.com/).
* [Miten voin työstää koontinäyttöjä ja raportteja yhdessä muiden kanssa sekä jakaa niitä?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Suodatetun Power BI-raportin jakaminen](service-share-reports.md).
* Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/).

