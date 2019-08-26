---
title: Raportin lataaminen Power BI -palvelusta Power BI Desktopiin (esikatselu)
description: Raportin lataaminen Power BI -palvelusta Power BI Desktop -tiedostoon
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/12/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 61fc821e63889951aefd0ef815f885ffa8a880cf
ms.sourcegitcommit: d12bc6df16be1f1993232898f52eb80d0c9fb04e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/13/2019
ms.locfileid: "68994812"
---
# <a name="download-a-report-from-the-power-bi-service-to-power-bi-desktop-preview"></a>Raportin lataaminen Power BI -palvelusta Power BI Desktopiin (esikatselu)
Voit julkaista Power BI Desktopissa raportin ( *.pbix*-tiedoston) paikallisesta tietokoneesta Power BI -palveluun. Power BI -raportit voivat myös siirtyä toiseen suuntaan: Voit ladata raportin Power BI -palvelusta Power BI Desktop -tiedostoon. Power BI -raportin tiedostotunniste on kummassakin tapauksessa .pbix.

Tähän liittyy tiettyjä rajoituksia ja huomioitavia asioita, joita käsitellään tuonnempana tässä artikkelista.

![Tiedoston avattava valikko](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix-file"></a>Lataa raportti .pbix-tiedostona

Voit ladata vain raportteja, jotka on [luotu Power BI Desktopissa](guided-learning/publishingandsharing.yml?tutorial-step=2) 23.11.2016 jälkeen ja päivitetty sen jälkeen. Jos raportti on luotu tätä ennen, **Lataa raportti** -valikkovaihtoehto Power BI -palvelussa näkyy harmaana.

Lataa .pbix-tiedosto toimimalla seuraavasti:

1. Avaa Power BI -palvelussa raportti, jonka haluat ladata [muokkausnäkymässä](https://docs.microsoft.com/power-bi/service-interact-with-a-report-in-editing-view).

2. Valitse yläreunan siirtymispalkista **Tiedosto > Lataa raportti**.
   
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

## <a name="next-steps"></a>Seuraavat vaiheet
Näytä minuutin **Kaveri kuutiossa** -video tästä ominaisuudesta:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Seuraavassa on joitakin artikkeleita, jotka auttavat sinua käyttämään Power BI -palvelua:

* [Raportit Power BI:ssä](consumer/end-user-reports.md)
* [Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)

Kun olet asentanut Power BI Desktopin, seuraavan artikkelin avulla voit aloittaa sen käytön nopeasti:

* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/).

