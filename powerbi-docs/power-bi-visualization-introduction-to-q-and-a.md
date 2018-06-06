---
title: 'Pikaopas: Power BI Q&A:n käytön aloittaminen'
description: 'Pikaopas: Q&A:n käytön aloittaminen Power BI -palvelussa, esimerkkinä Jälleenmyyntianalyysimalli'
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: ''
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/16/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 0f4f56431fd0c667411c302f4f30f0c395269e4a
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815389"
---
# <a name="get-started-with-power-bi-qa-quickstart"></a>Power BI Q&A:n käytön aloittaminen (pikaopas)
## <a name="use-power-bi-qa-with-the-retail-analysis-sample"></a>Power BI Q&A:n käyttäminen Jälleenmyyntianalyysimallin kanssa
Joskus nopein tapa saada vastauksia tiedoista on esittää kysymyksiä luonnollisella kielellä.  Tässä pikaoppaassa tarkastelemme kahta eri tapaa luoda sama visualisointi: ensin se luodaan raportissa ja sen jälkeen esittämällä kysymys Q&A:ssa. Käytämme Power BI -palvelua, mutta prosessi on lähes samanlainen Power BI Desktopissa.

Esimerkkien seuraaminen edellyttää, että käytössäsi on raportti, jota voit muokata, joten käytämme yhtä Power BI:hin sisältyvistä malleista.

## <a name="method-1-using-the-report-editor"></a>Menetelmä 1: raporttieditorin käyttäminen
1. Valitse Power BI -työtilassa **Nouda tiedot** \> **Mallit** \> **Jälleenmyyntianalyysimalli**  >   **Yhdistä**.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)
2. Koontinäyttö sisältää alueen kaavioruudun Viime vuoden myynti ja tämän vuoden myynti.  Valitse kyseinen ruutu. 
   
   * Jos tämä ruutu on luotu Q&A:lla, ruudun valitseminen avaa Q&A:n. 
   * Tämä ruutu on kuitenkin luotu raportissa, joten raportista avautuu sivu, joka sisältää tämän visualisoinnin.
3. Avaa raportti muokkausnäkymässä valitsemalla **Muokkaa raporttia**.  Jos et ole raportin omistaja, et voi avata raporttia muokkausnäkymässä.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Valitse aluekaavio ja tarkista **Kentät**-ruudun asetukset.  Raportin tekijä loi kaavion valitsemalla nämä kolme arvoa (**Aika > Tilikauden kuukausi**, **Myynti > Tämän vuoden myynti**, **Myynti > Viime vuoden myynti > Arvo**) ja järjestämällä ne **Akseli**- ja **Arvot**-lähteiden mukaan.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="method-2-using-qa"></a>Menetelmä 2: Q&A:n käyttäminen
Miten tämä sama viivakaavio luodaan käyttämällä Q&A:ta?

![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. Siirry takaisin Jälleenmyyntianalyysimallin koontinäyttöön.
2. Kirjoita käyttämällä luonnollista kieltä jotakin tällaista kysymysruutuun:
   
   **mikä oli tämän vuoden myynti ja edellisen vuoden myynti kuukauden mukaan aluekaaviona**
   
   Kun kirjoitat kysymystä, Q&A hakee parhaan visualisoinnin ja näyttää sen perusteella vastauksen; visualisointi muuttuu dynaamisesti kysymystä muokatessa. Q&A auttaa myös kysymyksen muotoilussa käyttämällä ehdotuksia, automaattista täydennystä ja oikeinkirjoituksen korjauksia.
   
   Kun olet kirjoittanut kysymyksen, tuloksena on täsmälleen sama kaavio kuin raportissa.  Tällä tavalla se kuitenkin syntyy paljon nopeammin!
   
   ![](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. Vastaavasti kuin raportteja käsiteltäessä Visualisoinnit-, Suodattimet- ja Kentät-ruudut ovat käytettävissä Q&A:ssa.  Avaamalla ruudut voit tutkia ja muokata visualisointia entisestään.
4. Jos haluat kiinnittää kaavion koontinäyttöösi, valitse Kiinnitä-kuvake ![](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png).

## <a name="next-steps"></a>Seuraavat vaiheet
[Q&A Power BI:ssä](power-bi-q-and-a.md)

[Tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa](service-prepare-data-for-q-and-a.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

