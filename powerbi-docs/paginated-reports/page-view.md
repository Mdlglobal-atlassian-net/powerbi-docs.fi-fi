---
title: Sivutettujen raporttien raporttinäkymien määrittäminen – Power BI
description: Tässä artikkelissa kerrotaan eri raporttinäkymistä, joita voi käyttää sivutetuissa raporteissa Power BI -palvelussa.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: ''
ms.topic: conceptual
ms.date: 05/14/2020
ms.openlocfilehash: 3816cfe4e1b61b9445e16d7c322c5ba19aa2bc3d
ms.sourcegitcommit: 21b06e49056c2f69a363d3a19337374baa84c83f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/15/2020
ms.locfileid: "83407928"
---
# <a name="set-report-views-for-paginated-reports-in-the-power-bi-service"></a>Sivutettujen raporttien raporttinäkymien määrittäminen Power BI -palvelussa

Kun hahmonnat sivutetun raportin Power BI -palvelussa, oletusnäkymä on HTML-pohjainen ja vuorovaikutteinen. Toinen raporttinäkymä, jota käytetään PDF-tiedostoja ja muita kiinteitä sivumuotoja varten, on uusi Sivunäkymä-vaihtoehto.

**Vuorovaikutteinen oletusnäkymä**

![Oletusnäkymä](media/page-view/power-bi-paginated-default-view.png)

**Sivunäkymä**

![Sivunäkymä](media/page-view/power-bi-paginated-page-view.png)

Sivunäkymässä hahmonnettu raportti näyttää erilaiselta verrattuna oletusnäkymään. Jotkin sivutettujen raporttien ominaisuudet ja käsitteet koskevat vain kiinteitä sivuja. Näkymä on samankaltainen kuin silloin, kun raportti tulostetaan tai viedään. Voit edelleen muuttaa joitakin elementtejä, kuten parametriarvoja, mutta raportissa ei ole muita vuorovaikutteisia ominaisuuksia, kuten sarakkeiden lajittelua ja vaihtoja.

Sivunäkymä tukee kaikkia ominaisuuksia, joita selaimen PDF-katseluohjelma tukee, kuten lähentämistä, loitontamista ja sovittamista sivulle.

## <a name="switch-to-page-view"></a>Sivunäkymään vaihtaminen

Kun avaat sivutetun raportin, se hahmonnetaan oletusarvoisesti vuorovaikutteiseen näkymään. Jos raportissa on parametreja, valitse parametrit ja näytä sitten raportti.

1. Valitse työkalurivillä **Näytä** > **Sivunäkymä**.

    ![Sivunäkymään vaihtaminen](media/page-view/power-bi-paginated-page-view-dropdown.png)

2. Voit muuttaa sivunäkymän asetuksia valitsemalla **Sivun asetukset** työkalurivin **Näytä**-valikossa. 

    ![Valitse Sivun asetukset](media/page-view/power-bi-paginated-page-settings-dropdown.png)
    
    **Sivun asetukset** -valintaikkunassa on asetukset, joiden avulla voit määrittää sivunäkymän **sivun koon** ja **suunnan**. Kun olet ottanut asetukset käyttöön, samat asetukset ovat käytössä, kun tulostat sivun myöhemmin.
   
    ![Sivun asetukset -valintaikkuna](media/page-view/power-bi-paginated-page-settings-dialog.png)

3. Kun haluat vaihtaa takaisin vuorovaikutteiseen näkymään, valitse **Oletus** avattavassa **Näytä**-luetteloruudussa.

## <a name="browser-support"></a>Selaintuki

Sivunäkymää tuetaan Google Chrome- ja Microsoft Edge -selaimissa. Varmista, että PDF-tiedostojen tarkastelu on käytössä selaimessa. Se on oletusasetus näissä selaimissa.

Sivunäkymää ei tueta Internet Explorerissa eikä Safarissa, joten asetus on poistettu käytöstä. Sitä ei tueta myöskään mobiililaitteiden selaimissa eikä alkuperäisissä Power BI -mobiilisovelluksissa.  


## <a name="next-steps"></a>Seuraavat vaiheet

- [Sivutetun raportin tarkasteleminen Power BI -palvelussa](../consumer/paginated-reports-view-power-bi-service.md)
- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
