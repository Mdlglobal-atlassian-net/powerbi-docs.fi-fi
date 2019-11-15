---
title: Visualisoinnin luominen Power BI:n Q&A:n avulla
description: Opi luomaan visualisointi Q&A:n avulla Power BI -palvelussa, esimerkkinä Jälleenmyyntianalyysimalli
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 817ce82b94817530854d85c7dbcca17a313fc438
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874450"
---
# <a name="create-a-visual-with-power-bi-qa"></a>Visualisoinnin luominen Power BI:n Q&A:n avulla

Joskus nopein tapa saada vastauksia tiedoista on esittää kysymyksiä luonnollisella kielellä.  Tässä artikkelissa tarkastelemme kahta eri tapaa luoda sama visualisointi: ensin esittämällä kysymys Q&A:ssa ja sitten luomalla se raportissa. Käytämme Power BI -palvelua visualisoinnin luomiseen raportissa, mutta prosessi on lähes samanlainen Power BI Desktopissa.

![Power BI:n täytetty kaavio](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-create-visual.png)

Esimerkkien seuraaminen edellyttää, että käytössäsi on raportti, jota voit muokata, joten käytämme yhtä Power BI:hin sisältyvistä malleista.

## <a name="create-a-visual-with-qa"></a>Visualisoinnin luominen Q&A:n avulla

Miten tämä viivakaavio luodaan käyttämällä Q&A:ta?

1. Valitse Power BI -työtilassa **Nouda tiedot** \> **Mallit** \> **Jälleenmyyntianalyysimalli**  >   **Yhdistä**.

1. Avaa Jälleenmyyntianalyysimalli-koonti näyttö, siirrä sijoita kohdistin Q&A-ruutuun ja **esitä tietojasi koskeva kysymys**.

    ![Siirrä kohdistin Q&A-ruutuun](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-cursor-in-qna-box.png)

2. Kirjoita Q&A-ruutuun tämän tyyppinen kysymys:
   
    **tämän vuoden myynti ja edellisen vuoden myynti kuukauden mukaan aluekaaviona**
   
    Kun kirjoitat kysymystä, Q&A hakee parhaan visualisoinnin ja näyttää sen perusteella vastauksen; visualisointi muuttuu dynaamisesti kysymystä muokatessa. Q&A auttaa myös kysymyksen muotoilussa ehdotusten, automaattisen täydennyksen ja oikeinkirjoituksen korjausehdotusten avulla. Q&A ehdottaa vähäistä muutosta sanamuotoon: tämän vuoden myynti ja edellisen vuoden myynti *aika kuukauden* mukaan aluekaaviona.  

    ![Q&A:n korjaama sanamuoto](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-corrected-create-filled-chart.png)

4. Hyväksy ehdotus valitsemalla lause. 
   
   Kun olet kirjoittanut kysymyksen, tuloksena on sama kaavio kuin koontinäytössä.
   
   ![Q&A:n täytetty aluekaavio](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-create-filled-chart.png)

4. Jos haluat kiinnittää kaavion raporttinäkymään, valitse Kiinnitä-kuvake ![Kiinnitä-kuvake](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png) oikeassa yläkulmassa.

## <a name="create-a-visual-in-the-report-editor"></a>Visualisoinnin luominen raporttieditorissa

1. Siirry takaisin Jälleenmyyntianalyysimallin koontinäyttöön.
   
2. Koontinäyttö sisältää saman alueen kaavioruudun Viime vuoden myynti ja tämän vuoden myynti.  Valitse kyseinen ruutu. Älä valitse Q&A:lla luomaasi ruutua. Sen valitseminen avaa Q&A:n. Alkuperäinen aluekaavioruutu on kuitenkin luotu raportissa, joten raportista avautuu sivu, joka sisältää tämän visualisoinnin.

    ![Jälleenmyyntianalyysimallin raporttinäkymä](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)

1. Avaa raportti muokkausnäkymässä valitsemalla **Muokkaa raporttia**.  Jos et ole raportin omistaja, et voi avata raporttia muokkausnäkymässä.
   
    ![Muokkaa raporttia -painike](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Valitse aluekaavio ja tarkista **Kentät**-ruudun asetukset.  Raportin tekijä loi kaavion valitsemalla nämä kolme arvoa (**Viime vuoden myynti** ja **Tämän vuoden myynti > Arvo** **Myynti**-taulukosta ja **Tilikauden Kuukausi** **Aika**-taulukosta) ja järjestämällä ne **Akseli**- ja **Arvot**-säilöjen mukaan.
   
    ![Visualisoinnit-paneeli](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

    Näet, että päädyttiin samaan visualisointiin. Luominen tällä tavalla ei ollut kovin monimutkaista. Silti luominen Q&A:lla oli helpompaa!

## <a name="next-steps"></a>Seuraavat vaiheet

- [Q&A:n käyttäminen koontinäyttöissä ja raporteissa](power-bi-tutorial-q-and-a.md)  
- [Q&A kuluttajille](consumer/end-user-q-and-a.md)
- [Tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa](service-prepare-data-for-q-and-a.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

