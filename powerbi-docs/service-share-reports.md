---
title: Power BI -raportin suodattaminen ja jakaminen
description: Opi, miten voit suodattaa Power BI -raportin ja jakaa sen työtovereiden kanssa organisaatiossa.
author: maggiesMSFT
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 16041ebc9ba293ab166178e008b12277d94e89c3
ms.sourcegitcommit: 64a270362c60581a385af7fbc31394e3ebcaca41
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/31/2020
ms.locfileid: "76894797"
---
# <a name="filter-and-share-a-power-bi-report"></a>Power BI -raportin suodattaminen ja jakaminen
*Jakaminen* on kätevä keino myöntää parille henkilölle käyttöoikeus luomiisi koontinäyttöihin ja raportteihin. Mitä tapahtuu, jos haluat jakaa raportista suodatetun version? Haluat kenties, että raportti näyttää vain tietyn kaupungin, myyjän tai vuoden tiedot. Tässä artikkelissa kerrotaan, miten raportti suodatetaan ja miten sen suodatettu versio jaetaan. Toinen tapa jakaa suodatettu raportti on [lisätä kyselyparametreja raportin URL-osoitteeseen](service-url-filters.md). Molemmissa tapauksissa raportti suodatetaan, kun vastaanottajat avaavat sen ensimmäisen kerran. He voivat poistaa suodatinvalinnat raportissa.

![Raportti suodatettu](media/service-share-reports/power-bi-share-filter-pane-report.png)

Power BI sisältää myös [muita tapoja tehdä yhteistyötä ja jakaa raportteja](service-how-to-collaborate-distribute-dashboards-reports.md). Jakamisessa sinulla ja vastaanottajillasi on oltava myös [Power BI Pro -käyttöoikeudet](service-features-license-type.md) tai sisällön on oltava [Premium-kapasiteetissa](service-premium-what-is.md). 

## <a name="follow-along-with-sample-data"></a>Kokeile mallitietojen avulla

Tässä artikkelissa käytetään Markkinointi ja myynti -mallisovellusta. Haluatko kokeilla sitä? 

1. Asenna [Markkinointi ja myynti ‑mallisovellus](https://appsource.microsoft.com/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample?tab=Overview).
2. Valitse sovellus ja sitten **Tutustu sovellukseen**.

   ![Tutustu mallitietoihin](media/service-share-reports/power-bi-sample-explore-data.png)

3. Avaa sovelluksen mukana asennettu työtila valitsemalla kynäkuvake.

    ![Sovelluksen muokkauskynä](media/service-share-reports/power-bi-edit-pencil-app.png)

4. Valitse työtilan sisältöluettelosta **Raportit** ja sitten raportin **Myynti- ja markkinointimalli PBIX**.

    ![Avaa malliraportti](media/service-share-reports/power-bi-open-sample-report.png)

    Nyt olet valmis kokeilemaan.

## <a name="set-a-filter-in-the-report"></a>Suodattimen asettaminen raportissa

Voit käyttää suodatinta avaamalla raportin [Muokkausnäkymässä](consumer/end-user-reading-view.md).

Tässä esimerkissä suodatamme Markkinointi ja myynti ‑mallisovelluksen vuodenalusta-luokkasivun niin, että siinä näytetään vain ne arvot, joissa **Alue** on **Keski**. 
 
![Raportin suodatusruutu](media/service-share-reports/power-bi-share-report-filter.png)

Tallenna raportti.

## <a name="share-the-filtered-report"></a>Suodatetun raportin jakaminen

1. Valitse **Jaa**.

   ![Valitse jaa](media/service-share-reports/power-bi-share.png)

2. Tyhjennä **Lähetä sähköposti-ilmoitus vastaanottajille** -kohta, jotta voit lähettää suodatetun linkin sen sijaan. Valitse **Jaa raportti käyttäen nykyisiä suodattimia ja osittajia** ja sitten **Jaa**.

    ![Raportin jakaminen suodattimien kanssa](media/service-share-reports/power-bi-share-with-filters.png)

4. Valitse **Jaa** uudelleen.

   ![Valitse jaa](media/service-share-reports/power-bi-share.png)

5. Valitse **Käyttö**-välilehti ja sitten **Jaettujen raporttinäkymien hallinta**.

    ![Jaettujen raporttinäkymien hallinta](media/service-share-reports/power-bi-manage-shared-report-views.png)

6. Napsauta haluamaasi URL-osoitetta hiiren kakkospainikkeella ja valitse **Kopioi linkki**.

    ![Kopioi suodatettu linkki](media/service-share-reports/power-bi-copy-filtered-link.png)

7. Kun jaat tämän linkin, vastaanottajat näkevät suodatetun raporttisi. 


## <a name="next-steps"></a>Seuraavat vaiheet
* [Töiden jakamistavat Power BI:ssä](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Koontinäytön jakaminen](service-share-dashboards.md)
* Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/).
* Haluatko antaa palautetta? Anna ehdotuksia siirtymällä [Power BI -yhteisön sivustolle](https://community.powerbi.com/).

