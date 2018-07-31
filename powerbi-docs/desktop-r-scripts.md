---
title: R-komentosarjojen suorittaminen Power BI Desktopissa
description: R-komentosarjojen suorittaminen Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6796de2b32061629e8f4fbcbc9b3311b5a95042d
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2018
ms.locfileid: "39327288"
---
# <a name="run-r-scripts-in-power-bi-desktop"></a>Suorita R-komentosarat Power BI Desktopissa
Voit suorittaa R-komentosarjoja suoraan **Power BI Desktopissa** ja tuoda tietojoukot Power BI Desktopin tietomallin.

## <a name="install-r"></a>Asenna R
Jos haluat ajaa R-komentosarjoja Power BI Desktopissa, sinun on asennettava **R**paikalliseen tietokoneeseen. Voit ladata ja asentaa **R:n** maksutta useista sijainneista, mukaan lukien [Revolution Open -lataussivulta](https://mran.revolutionanalytics.com/download/) ja [CRAN-säilöstä](https://cran.r-project.org/bin/windows/base/). Nykyinen R-komentosarjan versio Power BI Desktopissa tukee Unicode-merkkejä sekä välilyöntejä (tyhjiä merkkejä) asennuspolulla.

## <a name="run-r-scripts"></a>Suorita R-komentosarjat
Power BI Desktopin ensimmäisinä vaiheina voit suorittaa R-komentosarjoja ja luoda tietomallin, josta voit luoda raportteja ja jakaa niitä Power BI -palvelussa. R-komentosarjat Power BI Desktopissa tukee nyt lukumuotoja, jotka sisältävät desimaalilukuja (.) ja pilkkuja (,).

### <a name="prepare-an-r-script"></a>Valmistele R-komentosarja
R-komentosarjan suorittamiseksi Power BI Desktopissa on luotava komentosarja paikalliseen R-kehitysympäristöön ja varmistettava, että se suoritetaan onnistuneesti.

Jos haluat suorittaa komentosarjan Power BI Desktopissa, varmista, että komentosarjan suorittaminen onnistuu uudessa ja muokkaamattomassa työtilassa. Tämä tarkoittaa, että kaikki paketit ja niiden riippuvuudet on ladattava ja suoritettava eksplisiittisesti. Voit käyttää *lähdettä()* riippuvaisten komentosarjojen suorittamiseen.

Kun valmistellaan ja suoritetaan R-komentosarjaa Power BI Desktopissa, myös muutamia rajoituksia on otettava huomioon:

* Vain kehykset on tuotu, joten varmista, että Power BI:hin tuotavat tiedot esitetään tietokehyksessä
* Sarakkeita, jotka on kirjoitettu monimutkaisiksi ja vektoreiksi, ei tuota, vaan ne korvautuvat virhearvoilla luodussa taulukossa
* Arvot merkinnällä N/A käännetään Power BI Desktopissa arvoon NULL
* Kaikki R-komentosarjat, joita suoritetaan yli 30 minuuttia, aikakatkaistaan
* R-komentosarjan interaktiiviset kutsut kuten odottaminen käyttäjän syötettä pysäyttää komentosarjan suorittamisen
* Työhakemistoa määritettäessä R-komentosarjan sisällä *pitää* koko polku määrittää työhakemistoon suhteellisen polun sijaan

### <a name="run-your-r-script-and-import-data"></a>R-komentosarjan suorittaminen ja tietojen tuonti
1. Power BI Desktopissa R-komentosarjan dataliitin löytyy kohdasta **Nouda tiedot**. Voit suorittaa R-komentosarjan valitsemalla **Nouda tiedot &gt; Lisää...** , ja valitsemalla sitten **Muu &gt; R-komentosarja** seuraavassa kuvassa esitetyllä tavalla:
   
   ![](media/desktop-r-scripts/r-scripts-1.png)
2. Jos R on asennettu paikalliseen tietokoneeseen, uusin asennettu versio valitan R-moduuliksi. Kopioi komentosarja ikkunaan ja valitse **OK**.
   
   ![](media/desktop-r-scripts/r-scripts-2.png)
3. Jos R ei ole asennettu, sitä ei tunnistetta tai jos luettelossa on useita asennuksia paikallisella tietokoneella, laajenna **R-asennusasetuksia** asennusvalintojen näyttämiseksi tai valitaksesi, missä asennuksessa haluat suorittaa R-komentosarjan.
   
   ![](media/desktop-r-scripts/r-scripts-3.png)
   
   Jos R on asennettu eikä sitä tunnisteta, voit antaa sen sijainnin esiin tulevaan tekstiruutuun, kun laajennat **R-asennusasetuksia**. Yllä olevassa kuvassa polku *C:\Program Files\R\R-3.2.0* on nimenomaisesti tekstiruutua varten.
   
   R-asennusasetukset sijaitsevat keskitetysti R-komentosarjat-osassa Asetukset-valintaikkunassa. Määritä R-asennuksen asetukset valitsemalla **Tiedosto > Asetukset ja vaihtoehdot** ja valitse sitten **Asetukset > R-komentosarja**. Jos käytettävissä on useita R-asennuskertoja, esiin tulee pudotusvalikko, josta voit valita, mitä asennusta käyttää.
   
   ![](media/desktop-r-scripts/r-scripts-4.png)
4. Valitse **OK** R-komentosarjan suorittamiseen. Kun komentosarjan suorittaminen onnistuu, voit sitten valita saatavat tiedot kehykset, voit lisätä Power BI-malliin.

### <a name="refresh"></a>Päivitä
Voit päivittää Power BI Desktopin R-komentosarjan. Kun päivität R-komentosarjaa, Power BI Desktop suorittaa R-komentosarjan uudelleen Power BI Desktop -ympäristössä.

## <a name="next-steps"></a>Seuraavat vaiheet
Tutustu seuraaviin lisätietoihin, jotka koskevat R:ää Power BI:ssä.

* [R-visualisointien luominen Power BI Desktopissa](desktop-r-visuals.md)
* [Ulkoisen R IDE:n käyttö Power BI:n kanssa](desktop-r-ide.md)

