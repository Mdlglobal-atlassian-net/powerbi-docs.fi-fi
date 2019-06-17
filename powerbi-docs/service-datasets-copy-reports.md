---
title: Raporttien kopioiminen muista työtiloista (esikatselu) – Power BI
description: Lue ohjeet siihen, miten voit jakaa tietojoukon koko organisaation käyttäjien kanssa. Tämän ansiosta he voivat luoda omissa työtiloissaan raportteja, jotka perustuvat sinun tietojoukkoosi.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 507af4de9d57d2d54fe3e28bca8b1aff7da5cf30
ms.sourcegitcommit: 7c426a5209d4fdd1360fc3d0442d57991be1984d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/03/2019
ms.locfileid: "66461461"
---
# <a name="copy-reports-from-other-workspaces-preview"></a>Raporttien kopioiminen muista työtiloista (esikatselu)

Lue ohjeet siihen, miten voit kopioida raportin yhdestä työtilasta ja tallentaa sen toiseen työtilaan. Tämän jälkeen voit muokata raporttia ja lisätä sekä poistaa visualisointeja ja muita elementtejä.

Kun löydät työtilasta tai sovelluksesta raportin, josta pidät, voit ottaa siitä kopion ja muokata sitä omiin tarpeisiisi. Sinun ei tarvitse huolehtia tietomallin luomisesta. Se on jo luotu sinulle. Lisäksi on paljon helpompaa muokata aiemmin luotua raporttia kuin aloittaa kokonaan alusta.

## <a name="save-a-copy-of-a-report"></a>Tallenna kopio raportista

1. Siirry sovelluksessa tai työtilassa Raportit-luettelonäkymään.

1. Valitse **Toiminnot**-kohdasta **Tallenna kopio**.

    ![Tallenna kopio raportista](media/service-datasets-copy-reports/power-bi-dataset-save-report-copy.png)

    Näet **Tallenna kopio** -kuvakkeen vain, jos raportti on uuden käyttöliittymän työtilassa ja sinulla on [muodostamiskäyttöoikeudet](service-datasets-build-permissions.md#build-permissions-for-shared-datasets). Vaikka sinulla olisi työtilan käyttöoikeus, sinulla täytyy silti olla tietojoukon muodostamisoikeudet.

3. Anna **Tallenna kopio tästä raportista** -kohdassa raportille nimi. Valitse myös kohdetyötila.

    ![Tallenna kopio -valintaikkuna](media/service-datasets-copy-reports/power-bi-dataset-save-report.png)

    Voit tallentaa raportin nykyiseen työtilaan tai toiseen työtilaan Power BI-palvelussa. Näet vain uutta käyttöliittymää käyttävät työtilat, joiden jäsen olet.
  
4. Valitse **Tallenna**.

    Kun tallennat kopion raportista, luot reaaliaikaisen yhteyden tietojoukkoon. Lisäksi voit avata raportin luontitoiminnon ja koko käytettävissä olevan tietojoukon. Et ole tehnyt kopiota tietojoukosta. Tietojoukko on yhä sen alkuperäisessä sijainnissa. Voit käyttää kaikkia tietojoukon taulukoita ja mittareita omassa raportissasi. Tietojoukossa on käytössä rivitason suojauksen (RLS) rajoitukset, joten näet vain tiedot, jotka sinulla on oikeus nähdä RLS-roolisi perusteella.

    Power BI luo automaattisesti merkinnän tietojoukkojen luetteloon, jos raportti perustuu työtilan ulkopuolella olevaan tietojoukkoon. Tämän tietojoukon kuvake on eri kuin työtilan tietojoukkojen kuvake: ![Jaettu tietojoukko -kuvake](media/service-datasets-discover-across-workspaces/power-bi-shared-dataset-icon.png)


    Näin työtilan jäsenet voivat päätellä, mitkä raportit ja koontinäytöt käyttävät työtilan ulkopuolella olevia tietojoukkoja. Tapahtuma näyttää tietojoukkoa koskevia tietoja ja valikoituja toimintoja.

    ![Tietojoukon toiminnot](media/service-datasets-across-workspaces/power-bi-dataset-actions.png)

## <a name="view-related-datasets"></a>Näytä liittyvät tietojoukot

Kun sinulla on työtilassasi raportti, sinun täytyy ehkä tietää, mihin tietojoukkoon se perustuu.

1. Valitse Raportit-luettelonäkymässä **Näytä aiheeseen liittyvät**.

    ![Näytä aiheeseen liittyvä kuvake](media/service-datasets-copy-reports/power-bi-dataset-view-related.png)

1. Näet kaikki liittyvät kohteet **aiheeseen liittyvän sisällön** valintaikkunasta. Tässä luettelossa tietojoukko näyttää samalta kuin kaikki muutkin. Et näe, että se on toisessa työtilassa. Tämä on tunnettu ongelma.
 
    ![Aiheeseen liittyvän sisällön valintaikkuna](media/service-datasets-copy-reports/power-bi-dataset-related.png)


## <a name="next-steps"></a>Seuraavat vaiheet

- [Tietojoukkojen käyttö eri työtiloissa (esikatselu)](service-datasets-across-workspaces.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
