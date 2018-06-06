---
title: Raportin vieminen Power BI -palvelusta työasemaan (esikatselu)
description: Raportin lataaminen Power BI -palvelusta Power BI Desktop -tiedostoon
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 0cda094f3104b32f9bad31bf5030e235eb7ce83d
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/09/2018
ms.locfileid: "30974732"
---
# <a name="export-a-report-from-power-bi-service-to-desktop-preview"></a>Raportin vieminen Power BI -palvelusta työasemaan (esikatselu)
Voit viedä (tai *ladata*) Power BI Desktopissa raportin Power BI -palveluun tallentamalla raportti ja valitsemalla **Julkaise**. Voit myös viedä toiseen suuntaan ja ladata raportin Power BI -palvelusta työpöydälle. Vietävien tiedostojen tiedostopääte kumpaankin suuntaan on *.pbix*.

Tähän liittyy tiettyjä rajoituksia ja huomioitavia asioita, joita käsitellään tuonnempana tässä artikkelista.

![Tiedoston avattava valikko](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix"></a>Lataa raportti .pbix-muodossa
Lataa .pbix-tiedosto toimimalla seuraavasti:

1. Avaa **Power BI-palvelussa** raportti, jonka haluat ladata [muokkausnäkymässä](service-reading-view-and-editing-view.md).
2. Valitse valikkorivistä **Tiedosto > Lataa raportti**.
   
   > [!NOTE]
   > Raportti on [luotava käyttäen Power BI Desktopia](guided-learning/publishingandsharing.yml#step-2) marraskuun 23. 2016 ja sen jälkeen tehdyissä päivityksissä raportin lataamiseksi. Jos näin ei ole, *Lataa raportti* -valikkovaihtoehto Power BI-palvelussa näkyy harmaana.
   > 
   > 
3. Kun .pbix-tiedostoa luodaan, edistyminen näkyy tilapalkissa. Kun tiedosto on valmis, sinua pyydetään avaamaan tai tallentamaan .pbix-tiedosto. Tiedoston nimi vastaa raportin otsikkoa.
   
    ![Avaa, tallenna tai peruuta](media/service-export-to-pbix/power-bi-save-pbix.png)
   
    Voit nyt halutessasi avata .pbix-tiedoston Power BI -palvelussa (app.powerbi.com) tai Power BI Desktopissa.     
4. Avaa raportti työpöydällä heti valitsemalla **Avaa**. Jos haluat tallentaa tiedoston tiettyyn sijaintiin, valitse **Tallenna > Tallenna nimellä**. Jos et ole vielä tehnyt sitä, [asenna Power BI Desktop](desktop-get-the-desktop.md).
   
    Kun avaat raportin Desktopissa, näet ehkä varoituksen siitä, että jotkin ominaisuudet, jotka ovat käytettävissä Power BI -palvelun raportissa, ei ole välttämättä käytettävissä Desktopissa.
   
    ![varoitus-valintaikkuna](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. Desktopin raporttieditori ja Power BI -palvelun raporttieditori ovat hyvin samankaltaisia.  
   
    ![Desktop -raporttieditori](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
On muutamia tärkeitä huomioon otettavia seikkoja ja rajoituksia, jotka liittyvät *.pbix* tiedoston lataamiseen (vientiin) Power BI -palvelusta.

* Jotta voit ladata tiedoston, sinulla on oltava muokkausoikeus raporttiin
* Raportti on pitänyt luoda käyttäen **Power BI Desktopia** ja *julkaista***Power BI -palveluun**, tai .pbix on pitänyt *ladata* palveluun.
* Raporttien on oltava julkaistu tai päivitetty 23. marraskuuta 2016 jälkeen. Ennen sitä julkaistut raportit eivät ole ladattavissa.
* Tämä ominaisuus ei toimi raporteissa, jotka on alun perin luotu **Power BI-palvelussa**, mukaan lukien sisältöpaketit.
* Sinun tulee aina käyttää **Power BI Desktopin** uusinta versiota, kun avaat ladattuja tiedostoja. Ladatut *.pbix*-tiedostot eivät välttämättä avaudu muissa kuin nykyisissä **Power BI Desktopin** versioissa.
* Jos järjestelmänvalvojasi on poistanut käytöstä mahdollisuuden viedä tietoja, tämä ominaisuus ei ole näkyvissä **Power BI-palvelussa**.

## <a name="next-steps"></a>Seuraavat vaiheet
Näytä minuutin **Kaveri kuutiossa** -video tästä ominaisuudesta:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Lisäksi seuraavassa on joitakin artikkeleita, jotka auttavat sinua käyttämään **Power BI -palvelua**:

* [Raportit Power BI:ssä](service-reports.md)
* [Power BI:n peruskäsitteet](service-basic-concepts.md)

Kun olet asentanut **Power BI Desktopin**, seuraavan sisällön avulla voit aloittaa sen käytön nopeasti:

* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)   

