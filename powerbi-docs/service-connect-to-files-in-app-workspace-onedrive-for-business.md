---
title: Yhteyden muodostaminen Power BI-sovellustyötilasta OneDrivessa oleviin tiedostoihin
description: Ohjeet siitä, miten Excel-, CSV- ja Power BI Desktop ‑tiedostot tallennetaan OneDriveen ja miten niihin muodostetaan yhteys Power BI ‑sovellustyötilassa käyttöä varten.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukasz
ms.service: powerbi
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 52b7748b6b634caf87de01ddc965576339a04b8b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61174994"
---
# <a name="connect-to-files-stored-in-onedrive-for-your-power-bi-app-workspace"></a>Yhteyden muodostaminen Power BI-sovellustyötilasta OneDriveen tallennettuihin tiedostoihin
[Luotuasi Power BI:hin sovellustyötilan](service-create-distribute-apps.md) voit tallentaa Excel-, CSV- ja Power BI Desktop ‑tiedostosi OneDrive for Business ‑palveluun ja käyttää niitä sieltä Power BI ‑sovellustyötilassa. Voit jatkaa päivitetään tiedostoja onedriveen. Kyseiset päivitykset automaattisesti myös Power BI-raportteja ja koontinäyttöjä, jotka perustuvat tiedostoja. 

> [!NOTE]
> Työtilan uuden kokemuksen muuttuu Power BI-työtilat ja Office 365-ryhmille välisen suhteen. Office 365-ryhmän ei luo automaattisesti aina, kun luot uuden työtilakokemuksen. Lue [uusi työtilojen luominen](service-create-the-new-workspaces.md)

Tiedostojen lisääminen sovellustyötilaan on kaksivaiheinen prosessi: 

1. Ensin sinun on [ladattava tiedostot sovellustyötilasi OneDrive for Business ‑tallennustilaan](service-connect-to-files-in-app-workspace-onedrive-for-business.md#1-upload-files-to-the-onedrive-for-business-for-your-app-workspace).
2. Sitten sinun on [muodostettava tiedostoihin yhteys Power BI:stä](service-connect-to-files-in-app-workspace-onedrive-for-business.md#2-import-excel-files-as-datasets-or-as-excel-online-workbooks).

> [!NOTE]
> Sovellustyötilat ovat käytettävissä vain [Power BI Pro:ssa](service-features-license-type.md).
> 

## <a name="1-upload-files-to-the-onedrive-for-business-for-your-app-workspace"></a>1. Tiedostojen lataaminen sovellustyötilasi OneDrive for Business ‑tallennustilaan
1. Valitse Power BI -palvelussa kohdan Työtilat vieressä oleva nuoli > valitse työtilasi nimen vierestä kolme pistettä ( **…** ). 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-ellipsis.png)
2. Valitse **Tiedostot**, niin näytölle avautuu Office 365:ssä sovellustyötilasi OneDrive for Business ‑tallennustila.
   
   > [!NOTE]
   > Jos sovellustyötilan valikossa ei näy vaihtoehtoa **Tiedostot**, avaa sovellustyötilasi OneDrive for Business valitsemalla **Jäsenet**. Valitse sitten sieltä **Tiedostot**. Office 365 ottaa sovelluksesi ryhmätyötilatiedostoille käyttöön OneDrive-tallennussijainnin. Siihen voi kestää jonkin aikaa. 
   > 
   > 
3. Tästä näkymästä voit ladata tiedostot sovellustyötilasi OneDrive for Business ‑tallennustilaan. Valitse **Lataa** ja siirry tiedostoihin.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grpfilesonedrive.png)

## <a name="2-import-excel-files-as-datasets-or-as-excel-online-workbooks"></a>2. Excel-tiedostojen tuonti tietojoukkoina tai Excel Online ‑työkirjoina
Nyt kun tiedostosi ovat sovellustyötilasi OneDrive for Business ‑tallennustilassa, voit valita kahdesta vaihtoehdosta, miten haluat jatkaa. Vaihtoehdot ovat: 

* [Tuo Excel-työkirjan tietojoukkona](service-get-data-from-files.md). Luoda raportteja ja koontinäyttöjä, voit tarkastella verkkoselaimessa ja mobiililaitteilla tietojen avulla.
* Tai voit [muodostaa Power BI:ssä yhteyden koko Excel-työkirjaan](service-excel-workbook-files.md), jolloin se näytetään tismalleen samanlaisena kuin se näkyisi Excel Onlinessa.

### <a name="import-or-connect-to-the-files-in-your-app-workspace"></a>Tiedostojen tuonti sovellustyötilaan tai yhteyden muodostaminen tiedostoihin
1. Vaihda Power BI:ssä sovellustyötilaan, jolloin sovellustyötilan nimi näkyy vasemmassa yläkulmassa. 
2. Valitse vasemman siirtymisruudun alareunasta **Hae tiedot**. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-get-data-button.png)
3. Valitse **Tiedostot**-ruudusta **Nouda**.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_getfiles.png)
4. Valitse **OneDrive** - *sovellustyötilasi nimi*.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grp_one_drive_shrpt.png)
5. Valitse haluamasi tiedosto > **Yhdistä**.
   
    Päätät tässä vaiheessa, [tuoda tiedot Excel-työkirjan](service-get-data-from-files.md), tai [muodostaa yhteyden Excel-työkirjoihin kokonaisuudessaan](service-excel-workbook-files.md).
6. Valitse joko **Tuo** tai **Yhdistä**.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_importexceldataorwholecrop.png)
7. Jos valitset **Tuo**, työkirja ilmestyy **Tietojoukot**-välilehdelle. 
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-import.png)
   
    Jos valitset **Yhdistä**, työkirja tulee näkyviin **Työkirjat**-välilehdelle.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-connect.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Sovellusten ja sovellustyötilojen luominen Power BI:ssä](service-create-distribute-apps.md)
* [Tietojen tuominen Excel-työkirjoista](service-get-data-from-files.md)
* [Yhteyden muodostaminen kokonaisiin Excel-työkirjoihin](service-excel-workbook-files.md)
* Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
* Haluatko antaa palautetta? Siirry [Power BI:n ideasivulle](https://ideas.powerbi.com/forums/265200-power-bi)

