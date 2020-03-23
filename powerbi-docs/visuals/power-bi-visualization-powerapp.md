---
title: Upota uusi Power-sovellus Power BI -raporttiin
description: Upota sovellus, joka käyttää samaa tietolähdettä ja voidaan suodattaa samalla tavalla kuin muut raporttikohteet
author: mihart
manager: kvivek
ms.reviewer: tapan maniar
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 03/17/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3be5f9efe3a6e18ba46f6990b09952d37b967e16
ms.sourcegitcommit: 646d2de454a2897dc52cbc02b7743aaa021bac04
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/18/2020
ms.locfileid: "79525932"
---
# <a name="tutorial-embed-a-power-apps-visual-in-a-power-bi-report"></a>Opetusohjelma: Upota Power Apps -visualisointi Power BI -raporttiin

Tässä opetusohjelmassa luomme Power Apps -visualisoinnilla uuden Power BI -malliraporttiin upotetun sovelluksen. Tämä sovellus on vuorovaikutuksessa kyseisen raportin muiden visualisointien kanssa.

Jos sinulla ei ole Power Apps -tilausta, [luo ilmainen tili](https://web.powerapps.com/signup?redirect=marketing&email=) ennen aloittamista.

Tässä opetusohjelmassa opit:
> [!div class="checklist"]
> * Power Apps -visualisoinnin lisääminen Power BI -raporttiin
> * Luomaan Power Appsissa työskennellen uuden sovelluksen, joka käyttää Power BI -raportin tietoja
> * Tarkastelemaan ja käsittelemään raportin Power Apps -visualisointia

## <a name="prerequisites"></a>Edellytykset

* [Google Chrome](https://www.google.com/chrome/browser/)- tai [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) -selain
* [Power BI -tilaus](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi), jossa on [mahdollisuusanalyysimalli](https://docs.microsoft.com/power-bi/sample-opportunity-analysis#get-the-content-pack-for-this-sample) asennettuna
* Käsitys siitä, miten [sovelluksia luodaan Power Appsissa](https://docs.microsoft.com/powerapps/maker/canvas-apps/data-platform-create-app-scratch) ja [Power BI -raportteja](https://docs.microsoft.com/power-bi/service-the-report-editor-take-a-tour) muokataan



## <a name="create-a-new-app"></a>Luo uusi sovellus
Kun lisäät Power Apps -visualisoinnin raporttiisi, se käynnistää Power Apps Studion Power Appsin ja Power BI:n välisellä reaaliaikaisella tietoyhteydellä.

1. Avaa mahdollisuusanalyysimallin raportti ja valitse *Tulevia mahdollisuuksia* -sivu. 


2. Siirtämällä raporttiruutuja ja muuttamalla niiden kokoa voit tehdä tilaa uudelle visualisoinnille.

    ![Siirrä raporttiruutuja ja muuta niiden kokoa](media/power-bi-visualization-powerapp/power-bi-report-page.jpg)

2. Valitse Visualisoinnit-ruudusta Power Apps -kuvake ja muuta sitten visualisoinnin kokoa, kunnes se mahtuu luomaasi tilaan.

    ![Visualisointiruutu, jossa on valittuna Power Apps -kuvake](media/power-bi-visualization-powerapp/power-bi-powerapps-icon.jpg)

3. Valitse **Kentät**-ruudussa **Nimi**, **Tuotekoodi** ja **Myyntivaihe**. 

    ![valitse kentät](media/power-bi-visualization-powerapp/power-bi-fields.jpg)

4. Valitse Power Apps -visualisoinnissa Power Apps -ympäristö, johon haluat luoda sovelluksen, ja napsauta tai napauta sitten **Luo uusi**.

    ![Luo uusi sovellus](media/power-bi-visualization-powerapp/power-bi-create-new-powerapp.png)

    Näet Power Apps Studiossa luodun perussovelluksen sekä *valikoiman*, jossa näkyy jokin Power BI:ssä valitsemistasi kentistä.

    ![Power Apps avautuu](media/power-bi-visualization-powerapp/power-bi-power-app.png)

5.  Muuta valikoiman kokoa siten, että se vie vain puolet näytöstä. 

6. Valitse vasemmassa ruudussa **Screen1** ja määritä sitten näytön **Täyttö**-ominaisuudeksi ”LightBlue” (jotta se erottuu paremmin raportissa).

    ![värivalikoima](media/power-bi-visualization-powerapp/power-bi-powerapps-fill.png)

6. Tee tilaa otsikko-ohjausobjektille. 

    ![muuta valikoiman mittoja](media/power-bi-visualization-powerapp/power-bi-powerapps-gallery.png)


8. Lisää kohdassa **valikoima** tekstiotsikko-ohjausobjekti.

   ![otsikko-ohjausotsikko](media/power-bi-visualization-powerapp/power-bi-label.png)

7. Vedä otsikko visualisoinnin alareunaan. Aseta **Teksti**-ominaisuudeksi `"Opportunity Count: " & CountRows(Gallery1.AllItems)`. Näet nyt tietojoukon mahdollisuuksien kokonaismäärän.

    ![Sovellus ja valikoima, jonka kokoa on muutettu](media/power-bi-visualization-powerapp/power-bi-power-app-label.png)

    ![Sovellus, jonka otsikkoa on päivitetty](media/power-bi-visualization-powerapp/power-bi-label-live.png)

7. Tallenna sovellus nimellä ”Mahdollisuudet-sovellus”. 

    ![tallenna sovellus](media/power-bi-visualization-powerapp/power-bi-save-powerapp.png)


## <a name="view-the-app-in-the-report"></a>Sovelluksen tarkasteleminen raportissa
Sovellus on nyt käytettävissä Power BI -raportissa, ja se on vuorovaikutuksessa muiden visualisointien kanssa, koska se jakaa saman tietolähteen.

![Sovellus Power BI -raportissa](media/power-bi-visualization-powerapp/power-bi-powerapps-visual.png)

Valitse Power BI -raportin osittajassa **Jan**. Näin koko raportti suodatetaan, mukaan lukien sovelluksen tiedot.

![suodatettu raportti](media/power-bi-visualization-powerapp/power-bi-last.png)

Huomaa, että mahdollisuuksien lukumäärä sovelluksessa vastaa raportin vasemmassa yläkulmassa olevaa lukua. Voit valita muita raportin kohteita; sovelluksen tiedot päivitetään.


## <a name="clean-up-resources"></a>Puhdista resurssit
Jos et enää halua käyttää mahdollisuusanalyysimallia, voit poistaa koontinäytön, raportin ja tietojoukon.


## <a name="next-steps"></a>Seuraavat vaiheet
[Q&A-visualisointi](power-bi-visualization-types-for-reports-and-q-and-a.md)    
[Opetusohjelma: Power Apps -visualisoinnin upottaminen Power BI -raporttiin](https://docs.microsoft.com/powerapps/maker/canvas-apps/powerapps-custom-visual)