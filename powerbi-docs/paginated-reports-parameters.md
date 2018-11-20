---
title: Sivutettujen raporttien parametrien luominen Power BI -palvelussa | Microsoft Docs
description: Tässä artikkelissa opit luomaan sivutettujen raporttien parametreja Power BI -palvelussa.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: report-builder
ms.topic: conceptual
ms.date: 11/05/2018
ms.author: maggies
ms.openlocfilehash: 3a1d497f112e84aeb958b86658ee3ffae3e87c6d
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/07/2018
ms.locfileid: "51267205"
---
# <a name="create-parameters-for-paginated-reports-in-the-power-bi-service"></a>Sivutettujen raporttien parametrien luominen Power BI -palvelussa

Tässä artikkelissa opit luomaan sivutettujen raporttien parametreja Power BI -palvelussa.  Raporttiparametrien avulla voit valita raportin tiedot ja muuttaa raportin esitystapaa. Voit antaa oletusarvon ja käytettävissä olevien arvojen luettelon, jolloin raportin lukijat voivat muuttaa valintaa.  

Seuraavassa kuvassa näkyy Raportin muodostimen Suunnittelunäkymä, jossa parametrit ovat @BuyingGroup, @Customer, @FromDate ja @ToDate. 
  
![Parametrit Raportin muodostimessa](media/paginated-reports-parameters/power-bi-paginated-parameters-report-builder.png)
  
1.  Raporttiparametrit Raporttitietoruudussa.  
  
2.  Taulukko, jonka tietojoukossa on yksi parametri.  
  
3.  Parametriruutu. Voit mukauttaa parametrien asettelua parametriruudussa. 
  
4.  Parametrien @FromDate ja @ToDate tietotyyppi on **DateTime**. Kun tarkastelet raporttia, voit kirjoittaa päivämäärän tekstiruutuun tai valita päivämäärän kalenterista. 

5.  Yksi **Tietojoukon ominaisuudet** -valintaikkunan parametreista.  

  
## <a name="create-or-edit-a-report-parameter"></a>Raporttiparametrin luominen tai muokkaaminen  
  
1.  Avaa sivutettu raportti Raportin muodostimessa.

1. Napsauta **Raporttitiedot**-ruudussa olevaa **Parametrit**-solmua hiiren kakkospainikkeella > **Lisää parametri**. **Raporttiparametrin ominaisuudet** -valintaikkuna avautuu.  
  
2.  Kirjoita **Nimi**-parametrin nimi tai hyväksy oletusnimi.  
  
3.  Kirjoita **Kehote**-kohtaan teksti, joka näytetään parametri-tekstiruudun vieressä, kun käyttäjä suorittaa raportin.  
  
4.  Valitse **Tietotyyppi**-kohtaan parametriarvon tietotyyppi.  
  
5.  Jos parametri voi sisältää tyhjän arvon, valitse **Salli tyhjä arvo**.  
  
6.  Jos parametri voi sisältää nolla-arvon, valitse **Salli nolla-arvo**.  
  
7.  Jotta käyttäjä voi valita useamman kuin yhden parametriarvon, valitse **Salli useita arvoja**.  
  
8.  Valitse näkyvyysasetus.  
  
    -   Voit näyttää parametrin raportin yläreunan työkalurivissä valitsemalla **Näkyvissä**.  
  
    -   Voit piilottaa parametrin niin, että sitä ei näytetä työkalurivissä, valitsemalla **Piilotettu**.  
  
    -   Valitsemalla **Sisäinen** voit piilottaa parametrin ja estää sen muokkauksen raporttipalvelimella raportin julkaisun jälkeen. Raporttiparametria voidaan tämän jälkeen tarkastella vain raportin määrityksessä. Sinun on määritettävä asetukselle oletusarvo tai sallittava parametrille nolla-arvo.  
  
9. Valitse **OK**. 
  
## <a name="next-steps"></a>Seuraavat vaiheet

Katso [Sivutettujen raporttien parametrien tarkastelu](paginated-reports-view-parameters.md) -artikkelista, miltä parametrit näyttävät Power BI -palvelussa.

Katso sivutettujen raporttien parametrien yksityiskohtaiset tiedot SQL Server Reporting Services -palveluiden [Raporttiparametrit (Raportin muodostin ja Report Designer)](https://docs.microsoft.com/sql/reporting-services/report-design/report-parameters-report-builder-and-report-designer) -artikkelista.  
