---
title: Suorita R-komentosarjat Power BI Desktopissa
description: Suorita R-komentosarjat Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/14/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 358a61c13418bd29a9e83ed7029e8b90f9a5988e
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/17/2020
ms.locfileid: "76161517"
---
# <a name="run-r-scripts-in-power-bi-desktop"></a>Suorita R-komentosarjat Power BI Desktopissa

Voit suorittaa R-komentosarjat suoraan Power BI Desktopissa ja tuoda tuloksena saadut tietojoukot Power BI Desktop -tietomalliin.

## <a name="install-r"></a>Asenna R

Jos haluat suorittaa R-komentosarjoja Power BI Desktopissa, sinun on asennettava R paikalliseen tietokoneeseen. Voit ladata ja asentaa R:n maksutta useista eri paikoista, esimerkiksi [Microsoftin R-sovellusverkosta](https://mran.revolutionanalytics.com/download/) ja [CRAN-säilöstä](https://cran.r-project.org/bin/windows/base/). Nykyinen versio tukee Unicode-merkkejä ja välilyöntejä (tyhjiä merkkejä) asennuspolussa.

## <a name="run-r-scripts"></a>Suorita R-komentosarjat

Voit suorittaa R-komentosarjat ja luoda tietomallin helposti muutamassa vaiheessa Power BI Desktopissa. Tämän tietomallin avulla voit luoda raportteja ja jakaa niitä Power BI -palvelussa. R-komentosarjat Power BI Desktopissa tukee nyt lukumuotoja, jotka sisältävät desimaalilukuja (.) ja pilkkuja (,).

### <a name="prepare-an-r-script"></a>Valmistele R-komentosarja

R-komentosarjan suorittamiseksi Power BI Desktopissa on luotava komentosarja paikalliseen R-kehitysympäristöön ja varmistettava, että se suoritetaan onnistuneesti.

Jos haluat suorittaa komentosarjan Power BI Desktopissa, varmista, että komentosarjan suorittaminen onnistuu uudessa ja muokkaamattomassa työtilassa. Tämä edellytys tarkoittaa, että kaikki paketit ja niiden riippuvuudet on ladattava ja suoritettava eksplisiittisesti. Voit suorittaa riippuvaisia komentosarjoja `source()` -komennolla.

Kun valmistelet ja suoritat R-komentosarjaa Power BI Desktopissa, ota huomioon pari rajoitusta:

* Koska tuot vain tietokehykset, muista esittää Power BI:hin tuotavat tiedot tietokehyksessä.
* Sarakkeita, jotka on kirjoitettu monitasoiseen muotoon ja vektorimuotoon, ei tuoda, vaan ne korvataan virhearvoilla luodussa taulukossa.
* Arvot merkinnällä `N/A` käännetään Power BI Desktopissa arvoon `NULL`.
* Jos R-komentosarjaa suoritetaan yli 30 minuuttia, se aikakatkaistaan
* R-komentosarjan interaktiiviset kutsut, kuten käyttäjän syötteen odottaminen, pysäyttää komentosarjan suorittamisen.
* Työhakemistoa määritettäessä R-komentosarjan sisällä *pitää* koko polku määrittää työhakemistoon suhteellisen polun sijaan.

### <a name="run-your-r-script-and-import-data"></a>R-komentosarjan suorittaminen ja tietojen tuonti

Nyt voit suorittaa R-komentosarjan tuodaksesi tiedot Power BI Desktopiin:

1. Valitse Power BI Desktopissa **Nouda tiedot**, valitse **Muu** > **R-komentosarja**, ja valitse sitten **Yhdistä**:

    ![Yhdistä R-komentosarjaan, Muu-luokka, Nouda tiedot -valintaikkuna, Power BI Desktop](media/desktop-r-scripts/r-scripts-1.png)

2. Jos R on asennettu paikalliseen tietokoneeseen, kopioi komentosarja komentosarjaikkunaan ja valitse **OK**. Uusin asennettu versio näytetään R-moduulina.

    ![R-komentosarjat-valintaikkuna, Power BI Desktop](media/desktop-r-scripts/r-scripts-2.png)

3. Valitse **OK** R-komentosarjan suorittamiseen. Kun komentosarjan suorittaminen onnistuu, voit sitten valita saatavat tietokehykset Power BI -mallin lisäämiseksi.

Voit määrittää, mitä R-asennusta käytetään komentosarjan suorittamiseen. Määritä R-asennuksen asetukset valitsemalla **Tiedosto**  > **Vaihtoehdot ja asetukset** > **Vaihtoehdot**, ja valitse sitten **R-komentosarja**. **R-komentosarja-asetukset**-kohdassa avattava **Havaitut R-kotihakemistot** -luettelo näyttää nykyiset R-asennusvalinnat. Jos haluamaasi R-asennusta ei ole luettelossa, valitse **Muu**ja selaa sitten haluamaasi R-asennuskansioon tai syötä se **Aseta R-kotihakemisto** -kohdassa.

![R-komentosarja-asetukset, Asetukset-valintaikkuna, Power BI Desktop](media/desktop-r-scripts/r-scripts-4.png)

### <a name="refresh"></a>Päivitä

Voit päivittää Power BI Desktopin R-komentosarjan. Kun päivität R-komentosarjaa, Power BI Desktop suorittaa R-komentosarjan uudelleen Power BI Desktop -ympäristössä.

## <a name="next-steps"></a>Seuraavat vaiheet

Tutustu seuraaviin lisätietoihin, jotka koskevat R:ää Power BI:ssä.

* [Power BI -visualisointien luominen R:n avulla](desktop-r-visuals.md)
* [Ulkoisen R IDE:n käyttö Power BI:n kanssa](desktop-r-ide.md)
