---
title: Raportin lataaminen Power BI -palvelusta Power BI Desktopiin (esikatselu)
description: Raportin lataaminen Power BI -palvelusta Power BI Desktop -tiedostoon
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/01/2020
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 15a4d88ac9de5d50caeb975afa8ad1758246031f
ms.sourcegitcommit: 6e56d038280efab86521602cbc089b3989dddbd0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/02/2020
ms.locfileid: "80551077"
---
# <a name="download-a-report-from-the-power-bi-service-to-power-bi-desktop-preview"></a>Raportin lataaminen Power BI -palvelusta Power BI Desktopiin (esikatselu)
Voit julkaista Power BI Desktopissa raportin ( *.pbix*-tiedoston) paikallisesta tietokoneesta Power BI -palveluun. Power BI -raportit voivat myös siirtyä toiseen suuntaan: Voit ladata raportin Power BI -palvelusta Power BI Desktop -tiedostoon. Power BI -raportin tiedostotunniste on kummassakin tapauksessa .pbix.

Tähän liittyy tiettyjä rajoituksia, joita käsitellään tämän artikkelin [Huomioon otettavat seikat ja vianmääritys](#considerations-and-troubleshooting) -osiossa.

![Tiedoston avattava valikko](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix-file"></a>Lataa raportti .pbix-tiedostona

Voit ladata vain raportteja, jotka on [luotu Power BI Desktopissa](/learn/modules/publish-share-power-bi/2-publish-reports) 23.11.2016 jälkeen ja päivitetty sen jälkeen. Jos raportti on luotu tätä ennen, **Lataa raportti** -valikkovaihtoehto Power BI -palvelussa näkyy harmaana.

Lataa .pbix-tiedosto toimimalla seuraavasti:

1. Avaa Power BI -palvelussa raportti, jonka haluat ladata [muokkausnäkymässä](https://docs.microsoft.com/power-bi/service-interact-with-a-report-in-editing-view).

2. Valitse yläreunan siirtymisruudusta **Tiedosto > Lataa raportti**.
   
3. Kun raporttia ladataan, edistyminen näkyy tilapalkissa. Kun tiedosto on valmis, sinua pyydetään valitsemaan .pbix-tiedoston tallennuspaikka. Tiedoston oletusnimi on raportin otsikko.
   
4. Jos et ole vielä asentanut [Power BI Desktopia](desktop-get-the-desktop.md), asenna se ja avaa .pbix-tiedosto Power BI Desktopissa.
   
    Kun avaat raportin Power BI Desktopissa, näet ehkä varoituksen siitä, että jotkin ominaisuudet, jotka ovat käytettävissä Power BI -palvelun raportissa, eivät ole käytettävissä Power BI Desktopissa.
   
    ![Varoitusikkuna](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. Power BI Desktopin raporttieditori ja Power BI -palvelun raporttieditori ovat samankaltaisia.  
   
    ![Power BI Desktop -raporttieditori](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
On muutamia tärkeitä huomioon otettavia seikkoja ja rajoituksia, jotka liittyvät .pbix-tiedoston lataamiseen Power BI -palvelusta.

* Jotta voit ladata tiedoston, sinulla on oltava raportin muokkausoikeus.
* Raportti on pitänyt luoda käyttäen Power BI Desktopia ja *julkaista* Power BI -palveluun, tai .pbix-tiedosto on pitänyt *ladata* Power BI -palveluun.
* Raporttien on oltava julkaistu tai päivitetty 23. marraskuuta 2016 jälkeen. Aiemmin julkaistut raportit eivät ole ladattavissa.
* Tämä ominaisuus ei toimi raporteissa ja sisältöpaketeissa, jotka on alun perin luotu Power BI -palvelussa.
* Käytä aina Power BI Desktopin uusinta versiota, kun avaat ladattuja tiedostoja. Ladatut .pbix-tiedostot eivät välttämättä avaudu muissa kuin nykyisissä Power BI Desktopin versioissa.
* Jos järjestelmänvalvojasi on poistanut käytöstä mahdollisuuden ladata tietoja, tämä ominaisuus ei ole näkyvissä Power BI -palvelussa.
* Tietojoukkoa, jossa on lisäävä päivitys, ei voi ladata .pbix-tiedostoon.
* Jos luot Power BI raportin tietojoukon perusteella yhdessä työtilassa ja julkaiset sen eri työtilassa, sinä ja käyttäjäsi ette voi ladata sitä. Lataustoimintoa ei tällä hetkellä tueta tällaisessa tilanteessa.

## <a name="next-steps"></a>Seuraavat vaiheet
Näytä minuutin **Kaveri kuutiossa** -video tästä ominaisuudesta:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Seuraavassa on joitakin artikkeleita, jotka auttavat sinua käyttämään Power BI -palvelua:

* [Raportit Power BI:ssä](consumer/end-user-reports.md)
* [Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)

Kun olet asentanut Power BI Desktopin, seuraavan artikkelin avulla voit aloittaa sen käytön nopeasti:

* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/).

