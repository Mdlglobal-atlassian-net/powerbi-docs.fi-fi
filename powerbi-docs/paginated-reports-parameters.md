---
title: Sivutettujen raporttien parametrien luominen Power BI -palvelussa
description: Tässä artikkelissa opit luomaan sivutettujen raporttien parametreja Power BI -palvelussa.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 06/06/2019
ms.openlocfilehash: d1f23f52f484ec9e141b4870b50cc1b2758709d9
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874733"
---
# <a name="create-parameters-for-paginated-reports-in-the-power-bi-service"></a>Sivutettujen raporttien parametrien luominen Power BI -palvelussa

Tässä artikkelissa opit luomaan sivutettujen raporttien parametreja Power BI -palvelussa.  Raporttiparametrien avulla voit valita raportin tiedot ja muuttaa raportin esitystapaa. Voit antaa oletusarvon ja käytettävissä olevien arvojen luettelon, jolloin raportin lukijat voivat muuttaa valintaa.  

Seuraavassa kuvassa näkyy Power BI:n raportin muodostimen Suunnittelunäkymä, jossa parametrit ovat @BuyingGroup, @Customer, @FromDate ja @ToDate. 
  
![Parametrit Raportin muodostimessa](media/paginated-reports-parameters/power-bi-paginated-parameters-report-builder.png)
  
1.  Raporttiparametrit Raporttitietoruudussa.  
  
2.  Taulukko, jonka tietojoukossa on yksi parametri.  
  
3.  Parametriruutu. Voit mukauttaa parametrien asettelua parametriruudussa. 
  
4.  Parametrien @FromDate ja @ToDate tietotyyppi on **DateTime**. Kun tarkastelet raporttia, voit kirjoittaa päivämäärän tekstiruutuun tai valita päivämäärän kalenterista. 

5.  Yksi **Tietojoukon ominaisuudet** -valintaikkunan parametreista.  

  
## <a name="create-or-edit-a-report-parameter"></a>Raporttiparametrin luominen tai muokkaaminen  
  
1.  Avaa sivutettu raportti Power BI:n raportin muodostimessa.

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

Katso sivutetut raporttiparametreja koskevat lisätiedot kohdasta [Raporttiparametrit Power BI:n raportin muodostimessa](report-builder-parameters.md).
