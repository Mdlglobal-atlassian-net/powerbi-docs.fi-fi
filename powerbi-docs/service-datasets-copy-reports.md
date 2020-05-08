---
title: Raporttien kopioiminen muista sovelluksista tai työtiloista (esikatselu) – Power BI
description: Lue, miten voit luoda raportista kopion ja tallentaa sen omaan työtilaasi.
author: maggiesMSFT
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/16/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 8716a304e5b117c027d75db149ebcc8d95efebfe
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "76268947"
---
# <a name="copy-reports-from-other-workspaces-preview"></a>Raporttien kopioiminen muista työtiloista (esikatselu)

Kun löydät työtilasta tai sovelluksesta raportin, josta pidät, voit luoda siitä kopion ja tallentaa sen eri työtilaan. Tämän jälkeen voit muokata raportin kopiota ja lisätä sekä poistaa visualisointeja ja muita elementtejä. Sinun ei tarvitse huolehtia tietomallin luomisesta. Se on jo luotu sinulle. Lisäksi on paljon helpompaa muokata aiemmin luotua raporttia kuin aloittaa kokonaan alusta. Kun luot sovelluksen työtilastasi, et kuitenkaan voi aina julkaista raportin kopiota sovelluksessa. Lisätietoja on [artikkelin Käytä tietojoukkoja eri työtiloissa kohdassa Huomioitavat asiat ja rajoitukset](service-datasets-across-workspaces.md#considerations-and-limitations).

> [!NOTE]
> Jos haluat luoda kopion, tarvitset Pro-käyttöoikeuden, vaikka alkuperäinen raportti olisi Premium-kapasiteetin työtilassa.

## <a name="save-a-copy-of-a-report-in-a-workspace"></a>Tallenna kopio raportista työtilassa

1. Siirry työtilassa Raportit-luettelonäkymään.

    ![Raportit-luettelonäkymä](media/service-datasets-copy-reports/power-bi-report-list-view.png)

1. Valitse **Toiminnot**-kohdasta **Tallenna kopio**.

    ![Tallenna kopio raportista](media/service-datasets-copy-reports/power-bi-dataset-save-report-copy.png)

    Näet **Tallenna kopio** -kuvakkeen vain, jos raportti on uuden käyttöliittymän työtilassa ja sinulla on [muodostamisoikeus](service-datasets-build-permissions.md). Vaikka sinulla olisi työtilan käyttöoikeus, sinulla täytyy silti olla tietojoukon muodostamisoikeus.

3. Anna **Tallenna kopio tästä raportista** -kohdassa raportille nimi. Valitse myös kohdetyötila.

    ![Tallenna kopio -valintaikkuna](media/service-datasets-copy-reports/power-bi-dataset-save-report.png)

    Voit tallentaa raportin nykyiseen työtilaan tai toiseen työtilaan Power BI-palvelussa. Näet vain uutta käyttöliittymää käyttävät työtilat, joiden jäsen olet. 
  
4. Valitse **Tallenna**.

    Power BI luo raportin kopion automaattisesti ja merkinnän tietojoukkojen luetteloon, jos raportti perustuu työtilan ulkopuolella olevaan tietojoukkoon. Tämän tietojoukon kuvake on eri kuin työtilan tietojoukkojen kuvake: ![Jaettu tietojoukko -kuvake](media/service-datasets-discover-across-workspaces/power-bi-shared-dataset-icon.png)
    
    Näin työtilan jäsenet voivat päätellä, mitkä raportit ja koontinäytöt käyttävät työtilan ulkopuolella olevia tietojoukkoja. Tapahtuma näyttää tietojoukkoa koskevia tietoja ja valikoituja toimintoja.

    ![Tietojoukon toiminnot](media/service-datasets-across-workspaces/power-bi-dataset-actions.png)

    Lisätietoja raportista ja aiheeseen liittyvästä tietojoukosta on tämän artikkelin kohdassa [Raportin kopio](#your-copy-of-the-report).

## <a name="copy-a-report-in-an-app"></a>Kopioi raportti sovelluksessa

1. Avaa kopioitava raportti sovelluksessa.
2. Valitse valikkorivillä **Lisää vaihtoehtoja** ( **...** ) > **Tallenna kopio**.

    ![Tallenna kopio raportista](media/service-datasets-copy-reports/power-bi-save-copy.png)

    Näet **Tallenna kopio** -vaihtoehdon vain, jos raportti on uuden työtilan käyttökokemuksessa ja sinulla on [muodostamisoikeus](service-datasets-build-permissions.md).

3. Anna raportille nimi > **Tallenna**.

    ![Anna raportin kopiolle nimi](media/service-datasets-copy-reports/power-bi-save-report-from-app.png)

    Kopiosi tallennetaan automaattisesti omaan työtilaasi.

4. Avaa kopio valitsemalla **Siirry raporttiin**.

## <a name="your-copy-of-the-report"></a>Raportin kopio

Kun tallennat kopion raportista, luot reaaliaikaisen yhteyden tietojoukkoon. Lisäksi voit avata raportin luontitoiminnon ja koko käytettävissä olevan tietojoukon. 

![Muokkaa raportin kopiota](media/service-datasets-copy-reports/power-bi-edit-report-copy.png)

Et ole tehnyt kopiota tietojoukosta. Tietojoukko on yhä sen alkuperäisessä sijainnissa. Voit käyttää kaikkia tietojoukon taulukoita ja mittareita omassa raportissasi. Tietojoukossa on käytössä rivitason suojauksen (RLS) rajoitukset, joten näet vain tiedot, jotka sinulla on oikeus nähdä RLS-roolisi perusteella.

## <a name="view-related-datasets"></a>Näytä liittyvät tietojoukot

Kun sinulla on raportti yhdessä työtilassa toisen työtilan tietojoukon perusteella, sinun täytyy ehkä tietää enemmän tietojoukosta, johon se perustuu.

1. Valitse Raportit-luettelonäkymässä **Näytä aiheeseen liittyvät**.

    ![Näytä aiheeseen liittyvä kuvake](media/service-datasets-copy-reports/power-bi-dataset-view-related.png)

1. Näet kaikki liittyvät kohteet **aiheeseen liittyvän sisällön** valintaikkunasta. Tässä luettelossa tietojoukko näyttää samalta kuin kaikki muutkin. Et näe, että se on toisessa työtilassa. Tämä on tunnettu ongelma.
 
    ![Aiheeseen liittyvän sisällön valintaikkuna](media/service-datasets-copy-reports/power-bi-dataset-related.png)

## <a name="delete-a-report-and-its-shared-dataset"></a>Raportin ja sen jaetun tietojoukon poistaminen

Voit päättää, että et enää halua raporttia ja siihen liittyvää jaettua tietojoukkoa työtilaasi.

1. Poista raportti. Valitse työtilan raporttiluettelosta **Poista**-kuvake.

    ![Poista raportti -kuvake](media/service-datasets-across-workspaces/power-bi-datasets-delete-report.png)

2. Huomaat, että jaetuilla tietojoukoilla ei ole **Poista**-kuvaketta tietojoukkoluettelossa. Päivitä sivu tai siirry eri sivulle ja palaa sitten takaisin. Tietojoukko on poistettu. Jos tietojoukkoa ei ole poistettu, tarkista **Näytä aiheeseen liittyvät**. Tietojoukko saattaa liittyä työntilan toiseen taulukkoon.

    ![Näytä aiheeseen liittyvä kuvake](media/service-datasets-across-workspaces/power-bi-dataset-view-related-icon.png)

    > [!NOTE]
    > Jaetun tietojoukon poistaminen tässä työtilassa ei poista tietojoukkoa. Se poistaa vain viittauksen tietojoukkoon.


## <a name="next-steps"></a>Seuraavat vaiheet

- [Tietojoukkojen käyttö eri työtiloissa (esikatselu)](service-datasets-across-workspaces.md)
- Onko sinulla kysymyksiä? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
