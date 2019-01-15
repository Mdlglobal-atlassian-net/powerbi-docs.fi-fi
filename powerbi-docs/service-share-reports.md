---
title: Suodatetun Power BI -raportin jakaminen työtovereiden kanssa
description: Opi, miten voit suodattaa Power BI -raportin ja jakaa sen työtovereiden kanssa organisaatiossa.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 05bdb9ccca7715b74cb18462f215f7d1bf640526
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279744"
---
# <a name="share-a-filtered-power-bi-report-with-your-coworkers"></a>Suodatetun Power BI -raportin jakaminen työtovereiden kanssa
*Jakaminen* on kätevä keino myöntää parille henkilölle käyttöoikeus luomiisi koontinäyttöihin ja raportteihin. Power BI tarjoaa myös [useita muita tapoja tehdä yhteistyötä ja jakaa raportteja](service-how-to-collaborate-distribute-dashboards-reports.md).

Jakamisessa sinulla ja vastaanottajillasi on oltava myös [Power BI Pro -käyttöoikeudet](service-features-license-type.md) tai sisällön on oltava [Premium-kapasiteetissa](service-premium.md). 

Voit jakaa raportin kanssasi samassa sähköpostin toimialueessa oleville työtovereille Power BI -palvelun useimmista paikoista: Suosikit, Viimeisimmät, Jaettu kanssani (jos omistaja sallii sen), Oma työtila tai muut työtilat. Kun jaat raportin, työntekijät, joiden kanssa sen jaat, voivat tarkastella ja käsitellä sitä, mutta eivät voi muokata sitä. He näkevät samat tiedot kuin sinä raportissa, ellei sovelleta [rivitason suojausta (RLS)](service-admin-rls.md). 

Mitä tapahtuu, jos haluat jakaa raportista suodatetun version? Haluat kenties jakaa raportin, joka näyttää vain tietyn kaupungin, myyjän tai vuoden tiedot. Yritä luoda mukautettu URL-osoite. Raportti suodatetaan, kun vastaanottajat avaavat sen ensimmäisen kerran. He voivat poistaa suodattimen muokkaamalla URL-osoitetta.

## <a name="filter-and-share-a-report"></a>Raportin suodattaminen ja jakaminen

1. Avaa raportti [muokkausnäkymässä](consumer/end-user-reading-view.md), käytä suodatinta ja tallenna raportti.
   
   Tässä esimerkissä suodatamme [Jälleenmyyntianalyysimallin](sample-tutorial-connect-to-the-samples.md), jotta siinä näkyvät vain arvot, joissa **Alue** on yhtä kuin **NC**.
   
   ![Raportin suodatusruutu](media/service-share-reports/power-bi-filter-report2.png)
2. Lisää seuraava teksti raporttisivun URL-osoitteen loppuun:
   
   ?filter=*tablename*/*fieldname* eq *arvo*
   
    Kentän on oltava tyyppiä **merkkijono**. *Tablename*- tai *Fieldname*-arvot eivät voi sisältää välilyöntejä.
   
   Tässä esimerkissä taulukon nimi on **Kauppa**, kentän nimi on **Alue** ja suodatettava arvo on **NC**:
   
    ?filter=Store/Territory eq 'NC'
   
   ![Suodatetun raportin URL-osoite](media/service-share-reports/power-bi-filter-url3.png)
   
   Selain lisää erikoismerkit, jotka vastaavat kauttaviivoja, välilyöntejä ja heittomerkkejä, joten tulos on seuraava:
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

3. [Jaa raportti](service-share-dashboards.md), mutta tyhjennä **Lähetä sähköposti-ilmoitus vastaanottajille** -valintaruutu. 

    ![Jaa raportti -valintaikkuna](media/service-share-reports/power-bi-share-report-dialog.png)

4. Lähetä aiemmin luomasi suodattimen sisältävä linkki.

## <a name="next-steps"></a>Seuraavat vaiheet
* Haluatko antaa palautetta? Anna ehdotuksia siirtymällä [Power BI -yhteisön sivustolle](https://community.powerbi.com/).
* [Miten voin työstää koontinäyttöjä ja raportteja yhdessä muiden kanssa sekä jakaa niitä?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Jaa koontinäyttö](service-share-dashboards.md)
* Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/).

