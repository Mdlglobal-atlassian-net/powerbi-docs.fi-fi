---
title: Upotetun tietojoukon luominen sivutettuun Power BI -raporttiin | Microsoft Docs
description: Tässä artikkelissa opit luomaan upotettuun tietolähteeseen perustuvan upotetun tietojoukon sivutettuun raporttiin Power BI -palvelussa.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: report-builder
ms.topic: conceptual
ms.date: 11/5/2018
ms.author: maggies
ms.openlocfilehash: 4362633f705d412749e1146417a48cd61d47743c
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/07/2018
ms.locfileid: "51267223"
---
# <a name="create-an-embedded-dataset-for-a-paginated-report-in-the-power-bi-service"></a>Upotetun tietojoukon luominen sivutettuun raporttiin Power BI -palvelussa
Tässä artikkelissa opit luomaan upotettuun tietolähteeseen perustuvan upotetun tietojoukon sivutettuun raporttiin Power BI -palvelussa. Upotetut tietojoukot lisätään yksittäiseen sivutettuun raporttiin kyseisessä raportissa käytettäväksi. Power BI -palveluun tällä hetkellä julkaistavat sivutetut raportit edellyttävät upotettuja tietojoukkoja ja upotettuja tietolähteitä. Voit luoda upotetun tietolähteen ja tietojoukon raportin muodostimessa samalla, kun luot raportin. 

Ennen kuin luot tietojoukon, sinun on luotava tietolähde. Ohjeet ovat kohdassa [Sivutettujen raporttien upotetut tietolähteet](paginated-reports-embedded-data-source.md) Power BI -palvelussa.
  
## <a name="create-an-embedded-dataset"></a>Upotetun tietojoukon luominen
  
1. Valitse raportin muodostimen raporttitietoruudussa **Uusi** > **Tietojoukko**.

1. Anna tietojoukolle nimi **Tietojoukon ominaisuudet** -valintaikkunan **Kysely**-välilehdellä. Upotettu tietolähde on jo **Tietolähde**-ruudussa tai voit luoda uuden upotetun tietolähteen valitsemalla **Uusi**.
 
   ![Uusi tietojoukko](media/paginated-reports-create-embedded-dataset/power-bi-paginated-new-dataset.png)  

3. Valitse **Kyselyn tyyppi**, valitse tietojoukossa käytettävä komennon tai kyselyn tyyppi. 
    - **Teksti** suorittaa kyselyn tietojen hakemiseksi tietokannasta. Se on oletusarvo, ja sitä käytetään useimmissa kyselyissä. Kirjoita kysely tai tuo aiemmin luotu kysely valitsemalla **Tuo**. Voit luoda kyselyn graafisesti valitsemalla **Kyselyjen suunnittelutyökalu**. Jos luot kyselyn kyselyjen suunnittelutyökalun avulla, kyselyn teksti näkyy tässä ruudussa. Luo kysely dynaamisesti lausekkeen avulla valitsemalla **Lauseke** (**fx**) -painike. 
    - **Taulukko** valitsee kaikki taulukon kentät. Kirjoita sen taulukon nimi, jota haluat käyttää tietojoukkona.
    - **Tallennettu toimintosarja** suorittaa tallennetun toimintosarjan nimen mukaan.

4. Kyselyjen suunnittelutyökalussa voit tarkastella ja käsitellä tietojoukon taulukoita ja kenttiä, tuoda kyselyn tai muokata tekstinä. Siellä voit myös lisätä suodattimia ja parametreja. 

    ![Kyselyjen suunnittelutyökalu](media/paginated-reports-create-embedded-dataset/power-bi-paginated-embedded-dataset-edit-query.png)

5. Testaa kysely valitsemalla kyselyjen suunnittelutyökalussa **Suorita kysely** ja sitten **OK**.

1. Kirjoita Tietojoukon ominaisuudet -valintaikkunan **Aikakatkaisu (sekunteina)** -ruutuun, kuinka monen sekunnin kuluttua kysely aikakatkaistaan. Oletusarvo on 30 sekuntia. **Aikakatkaisu**-arvon on oltava tyhjä tai suurempi kuin nolla. Jos se on tyhjä, kyselyä ei aikakatkaista.

7.  Voit määrittää muita ominaisuuksia tietojoukolle muilla välilehdillä:
    - Luo laskettuja kenttiä **Kentät**-välilehdellä.
    - Määritä lisäasetuksia **Asetukset**-välilehdellä.
    - Lisää tai päivitä **suodattimia** ja **parametreja** niitä vastaavilla välilehdillä.

8. Valitse **OK**.
 
   Raportti avautuu raportin suunnittelunäkymässä. Tietolähde, tietojoukko ja tietojoukon kenttäkokoelma näkyvät raporttitietoruudussa, ja voit jatkaa sivutetun raportin suunnittelemista.  

    ![Tietojoukko raportin suunnittelunäkymässä](media/paginated-reports-create-embedded-dataset/power-bi-paginated-embedded-dataset-report-design-view.png) 
 
## <a name="next-steps"></a>Seuraavat vaiheet 

- [Mitä ovat sivutetut raportit Power BI Premiumissa? (esikatselu)](paginated-reports-report-builder-power-bi.md)  
- [Opetusohjelma: Sivutetun raportin luominen ja lataaminen Power BI -palveluun](paginated-reports-quickstart-aw.md)
- [Sivutetun raportin julkaiseminen Power BI -palveluun](paginated-reports-save-to-power-bi-service.md)

