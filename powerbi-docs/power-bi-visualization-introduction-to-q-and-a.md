---
title: Visualisoinnin luominen Power BI Q & A
description: Opi luomaan visualisoinnin Q & A Power BI-palvelussa, esimerkkinä jälleenmyyntianalyysimalli
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 580b387f8c763b0457bd32a71bfbccd90d4040a3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65625186"
---
# <a name="create-a-visual-with-power-bi-qa"></a>Visualisoinnin luominen Power BI Q & A

Joskus nopein tapa saada vastauksia tiedoista on esittää kysymyksiä luonnollisella kielellä.  Tässä artikkelissa tarkastellaan kahta eri tapaa luoda sama visualisointi: ensin kysymyksen Q & A ja kehittäminen toiseksi raportissa. Käytämme Power BI-palvelussa voit luoda raportin visualisoinnissa, mutta prosessi on lähes samanlainen Power BI Desktop.

![Power BI täytetty kaavio](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-create-visual.png)

Esimerkkien seuraaminen edellyttää, että käytössäsi on raportti, jota voit muokata, joten käytämme yhtä Power BI:hin sisältyvistä malleista.

## <a name="create-a-visual-with-qa"></a>Visualisoinnin luominen Q & A

Miten siirrymme luomisesta tämän viivakaavion avulla Q & A?

1. Valitse Power BI -työtilassa **Nouda tiedot** \> **Mallit** \> **Jälleenmyyntianalyysimalli**  >   **Yhdistä**.

1. Avaa Jälleenmyyntianalyysimalli-koontinäyttö ja Aseta hiiriosoitin Q & A-ruudusta, **esitä tietojasi koskeva kysymys**.

    ![Aseta kohdistin Q & A-ruudussa](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-cursor-in-qna-box.png)

2. Q & A-ruutu Kirjoita esimerkiksi tähän kysymykseen:
   
    **Tämän vuoden myynti ja edellisen vuoden myynti aluekaaviona kuukauden mukaan**
   
    Kun kirjoitat kysymystä, Q&A hakee parhaan visualisoinnin ja näyttää sen perusteella vastauksen; visualisointi muuttuu dynaamisesti kysymystä muokatessa. Q&A auttaa myös kysymyksen muotoilussa ehdotusten, automaattisen täydennyksen ja oikeinkirjoituksen korjausehdotusten avulla. Q & A: n suosittelee pieni teksti muutos ”: Tämän vuoden myynti ja edellisen vuoden myynti *kuukausi* aluekaaviona”.  

    ![Q & A: n korjattu teksti](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-corrected-create-filled-chart.png)

4. Valitse Hyväksy ehdotus lause. 
   
   Kun olet kirjoittanut kysymyksen, tuloksena on sama kaavio kuin sinä koontinäytössä.
   
   ![Q & A: n täytetty aluekaavio](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-create-filled-chart.png)

4. Jos haluat kiinnittää kaavion raporttinäkymään, valitse Kiinnitä-kuvake ![Kiinnitä-kuvake](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png) oikeassa yläkulmassa.

## <a name="create-a-visual-in-the-report-editor"></a>Visualisoinnin luominen raporttieditorissa

1. Siirry takaisin Jälleenmyyntianalyysimallin koontinäyttöön.
   
2. Koontinäyttö sisältää saman alueen kaavioruudun ”viime vuoden myynti ja tämän vuoden myynti”.  Valitse kyseinen ruutu. Älä valitse Q & a: n luotu ruutu Se valitseminen avaa Q & a: ta. Alkuperäinen alueen kaavioruudun on luotu raportissa, joten raportista avautuu sivu, joka sisältää tämän visualisoinnin.

    ![Jälleenmyyntianalyysimallin raporttinäkymä](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)

1. Avaa raportti muokkausnäkymässä valitsemalla **Muokkaa raporttia**.  Jos et ole raportin omistaja, et voi avata raporttia muokkausnäkymässä.
   
    ![Muokkaa raporttia -painike](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Valitse aluekaavio ja tarkista **Kentät**-ruudun asetukset.  Raportin tekijä loi kaavion valitsemalla nämä kolme arvoa (**viime vuoden myynti** ja **tämän vuoden myynti > arvo** - **myynti** taulukon ja  **Tilikauden kuukauden** - **aika** taulukon) ja järjestämällä ne **akselin** ja **arvot** lähteiden mukaan.
   
    ![Visualisoinnit-paneeli](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

    Näet ne pysähtyi samaan visualisointiin. Luodaan näin ei ole liian monimutkainen. Mutta luominen Q & A on helpompi!

## <a name="next-steps"></a>Seuraavat vaiheet

- [Koontinäyttöjen ja raporttien Q & A: n käyttäminen](power-bi-tutorial-q-and-a.md)  
- [Q & A kuluttajat](consumer/end-user-q-and-a.md)
- [Tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa](service-prepare-data-for-q-and-a.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

