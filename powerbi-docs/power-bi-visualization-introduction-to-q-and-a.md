---
title: Power BI Q&A:n käytön aloittaminen
description: Q&A:n käytön aloittaminen Power BI -palvelussa, esimerkkinä Jälleenmyyntianalyysimalli
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 87783b928fdec1cadf5318ae184858c37daa4acc
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279247"
---
# <a name="get-started-with-power-bi-qa"></a>Power BI Q&A:n käytön aloittaminen

Joskus nopein tapa saada vastauksia tiedoista on esittää kysymyksiä luonnollisella kielellä.  Tässä pikaoppaassa tarkastelemme kahta eri tapaa luoda sama visualisointi: ensin se luodaan raportissa ja sen jälkeen esittämällä kysymys Q&A:ssa. Käytämme Power BI -palvelua, mutta prosessi on lähes samanlainen Power BI Desktopissa.

Esimerkkien seuraaminen edellyttää, että käytössäsi on raportti, jota voit muokata, joten käytämme yhtä Power BI:hin sisältyvistä malleista.

## <a name="create-a-visual-in-the-report-editor"></a>Visualisoinnin luominen raporttieditorissa

1. Valitse Power BI -työtilassa **Nouda tiedot** \> **Mallit** \> **Jälleenmyyntianalyysimalli**  >   **Yhdistä**.
   
2. Koontinäyttö sisältää alueen kaavioruudun Viime vuoden myynti ja tämän vuoden myynti.  Valitse kyseinen ruutu. Jos tämä ruutu on luotu Q&A:lla, ruudun valitseminen avaa Q&A:n. Tämä ruutu on kuitenkin luotu raportissa, joten raportista avautuu sivu, joka sisältää tämän visualisoinnin.

    ![Jälleenmyyntianalyysimallin raporttinäkymä](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)

1. Avaa raportti muokkausnäkymässä valitsemalla **Muokkaa raporttia**.  Jos et ole raportin omistaja, et voi avata raporttia muokkausnäkymässä.
   
    ![Muokkaa raporttia -painike](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Valitse aluekaavio ja tarkista **Kentät**-ruudun asetukset.  Raportin tekijä loi kaavion valitsemalla nämä kolme arvoa (**Aika > Tilikauden Kuukausi**, **Myynti > Tämän vuoden myynti**, **Myynti > Viime vuoden myynti > Arvo**) ja järjestämällä ne **Akseli**- ja **Arvot**-lähteiden mukaan.
   
    ![Visualisoinnit-paneeli](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="create-the-same-visual-with-qa"></a>Saman visualisoinnin luominen Q&A:n avulla

Miten tämä sama viivakaavio luodaan käyttämällä Q&A:ta?

![Esitä kysymys -ruutu](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. Siirry takaisin Jälleenmyyntianalyysimallin koontinäyttöön.
2. Kirjoita luonnollista kieltä käyttämällä tämänkaltainen kysymys kysymysruutuun:
   
   **mikä oli tämän vuoden myynti ja edellisen vuoden myynti kuukauden mukaan aluekaaviona**
   
   Kun kirjoitat kysymystä, Q&A hakee parhaan visualisoinnin ja näyttää sen perusteella vastauksen; visualisointi muuttuu dynaamisesti kysymystä muokatessa. Q&A auttaa myös kysymyksen muotoilussa ehdotusten, automaattisen täydennyksen ja oikeinkirjoituksen korjausehdotusten avulla.
   
   Kun olet kirjoittanut kysymyksen, tuloksena on täsmälleen sama kaavio kuin raportissa.  Tällä tavalla se kuitenkin syntyy paljon nopeammin!
   
   ![Esimerkkikysymys](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. Visualisoinnit-, Suodattimet- ja Kentät-ruudut ovat käytettävissä Q&A:ssa aivan kuten raportteja käsiteltäessäkin.  Avaamalla ruudut voit tutkia ja muokata visualisointia entisestään.
4. Jos haluat kiinnittää kaavion raporttinäkymään, valitse Kiinnitä-kuvake ![Kiinnitä-kuvake](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png).

## <a name="next-steps"></a>Seuraavat vaiheet
[Q&A Power BI:ssä](consumer/end-user-q-and-a.md)

[Tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa](service-prepare-data-for-q-and-a.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

