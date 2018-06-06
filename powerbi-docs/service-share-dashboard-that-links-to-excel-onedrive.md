---
title: Excel-tiedostoon OneDrivessa linkitetyn koontinäytön jakaminen – Power BI
description: Lue lisätietoja OneDrive for Businessissa olevaan Excel-työkirjaan yhdistettyjen koontinäyttöjen jakamisesta, kun niihin on kiinnitetty ruutuja kyseisestä työkirjasta.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 56dec052240c60543831ef05624943e3d71f953a
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815364"
---
# <a name="share-a-power-bi-dashboard-that-links-to-an-excel-file-in-onedrive"></a>Jaa Power BI -koontinäyttö, joka on linkitetty Excel-tiedostoon OneDrivessa
Voit Power BI:ssä [muodostaa yhteyden Excel-työkirjoihin OneDrive for Businessissa](service-excel-workbook-files.md) ja kiinnittää ruutuja koontinäyttöihin kyseisestä työkirjasta. Kun jakaa tämän koontinäytön tai luot sisältöpaketin, joka sisältää kyseisen koontinäytön:

* Työtoverisi voivat tarkastella ruutuja tarvitsematta itselleen kyseisen työkirjan käyttöoikeuksia. Voit siis luoda sisältöpaketin ja tiedät, että työtoverisi näkevät OneDrivessa olevasta Excel-työkirjasta luodut ruudut.
* Ruudun napsauttaminen avaa työkirjan Power BI:ssä. Työkirja avautuu vain, jos työtoverillasi on vähintään OneDrive for Businessissa olevan työkirjan [lukuoikeudet](https://support.office.com/en-us/article/Share-documents-or-folders-in-Office-365-1fe37332-0f9a-4719-970e-d2578da4941c).

## <a name="share-a-dashboard-that-contains-workbook-tiles"></a>Työkirjan ruutuja sisältävän koontinäytön jakaminen
Jos haluat jakaa koontinäytön, joka linkittyy takaisin OneDrive for Businessiin tallennettuun Excel-työkirjaan, katso [Jaa koontinäyttö](service-share-dashboards.md). Ero on siinä, että voit muokata linkitetyn Excel-työkirjan käyttöoikeuksia ennen jakamista.

  ![Jaa koontinäyttö -valintaikkuna](media/service-share-dashboard-that-links-to-excel-onedrive/pbi_share_workbk.png)

1. Anna työtovereidesi sähköpostiosoitteet.
2. Jotta työtoverisi voivat tarkastella Excel-työkirjaa Power BI:ssä, valitse **Aseta työkirjan käyttöoikeudet siirtymällä OneDrive for Businessiin**.
3. Kun olet OneDrivessa, [muokkaa käyttöoikeuksia](https://support.office.com/en-US/article/Share-files-and-folders-and-change-permissions-9fcc2f7d-de0c-4cec-93b0-a82024800c07) tarpeen mukaan.
4. Valitse **Jaa**.

>[!NOTE]
>Työtoverisi eivät voi kiinnittää muita ruutuja kyseisestä työkirjasta tai tehdä muutoksia Excel-työkirjaan Power BI:ssä.
> 
> 

## <a name="create-an-organizational-content-pack-with-a-dashboard-that-contains-workbook-tiles"></a>Luo organisaation sisältöpaketti ja koontinäyttö, joka sisältää työkirjan ruutuja
Kun [julkaiset sisältöpaketin](service-organizational-content-pack-create-and-publish.md), annat käyttöoikeuden yksittäisille työtovereille tai ryhmille. Kun julkaiset sisältöpaketin, joka sisältää työkirjalinkkejä, voit muokata linkitetyn Excel-työkirjan käyttöoikeuksia ennen julkaisemista.

1. Anna **Luo sisältöpaketti** -ruudussa sähköpostiosoitteet, anna sisältöpaketin otsikko ja kuvaus ja lataa kuva.
2. Valitse haluamasi koontinäyttö ja/tai raportti, joka on linkitetty Excel-työkirjaan OneDrive for Businessissa.
   
    ![Excel-työkirja sisältöpaketissa](media/service-share-dashboard-that-links-to-excel-onedrive/pbi_contpack_workbk.png)
3. Valitse **Aseta työkirjan käyttöoikeudet siirtymällä OneDrive for Businessiin**.
4. Kun olet OneDrivessa, [muokkaa käyttöoikeuksia](https://support.office.com/en-US/article/Share-files-and-folders-and-change-permissions-9fcc2f7d-de0c-4cec-93b0-a82024800c07) tarpeen mukaan.
5. Valitse **Julkaise**.

## <a name="share-a-dashboard-from-a-power-bi-workspace"></a>Koontinäytön jakaminen Power BI -työtilasta
Koontinäytön jakaminen Power BI -työtilasta tapahtuu samankaltaisesti kuin koontinäytön jakaminen omasta työtilasta lukuun ottamatta sitä, että tiedostot sijaitsevat Office 365 -työtilasivustossa sen sijaan, että ne olisivat yksityisessä OneDrive for Businessissa. Muokkaa Excel-työkirjan käyttöoikeuksia ennen koontinäytön jakamista työtilan ulkopuolisten henkilöiden kanssa.

![Jaa OneDrivesta](media/service-share-dashboard-that-links-to-excel-onedrive/pbi_onedriveshare.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Ruudun kiinnittäminen Power BI:n koontinäyttöön Excelistä](service-dashboard-pin-tile-from-excel.md)
* [Power BI:n peruskäsitteet](service-basic-concepts.md)
* Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

