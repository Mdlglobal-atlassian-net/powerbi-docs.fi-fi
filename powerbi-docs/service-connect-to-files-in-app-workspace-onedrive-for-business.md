---
title: Yhteyden muodostaminen Power BI-sovellustyötilasta OneDrivessa oleviin tiedostoihin
description: Ohjeet siitä, miten Excel-, CSV- ja Power BI Desktop ‑tiedostot tallennetaan OneDriveen ja miten niihin muodostetaan yhteys Power BI ‑sovellustyötilassa käyttöä varten.
author: maggiesMSFT
manager: kfile
ms.reviewer: ajayan
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/12/2017
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: e1161e5e461b3b32e549c69cfa7987c8f799e0fd
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34245335"
---
# <a name="connect-to-files-stored-in-onedrive-for-your-power-bi-app-workspace"></a>Yhteyden muodostaminen Power BI-sovellustyötilasta OneDriveen tallennettuihin tiedostoihin
[Luotuasi Power BI:hin sovellustyötilan](service-create-distribute-apps.md) voit tallentaa Excel-, CSV- ja Power BI Desktop ‑tiedostosi OneDrive for Business ‑palveluun ja käyttää niitä sieltä Power BI ‑sovellustyötilassa. Voit päivittää OneDriveen tallentamiasi tiedostoja, jolloin päivitykset tulevat automaattisesti esiin myös kyseisiin tiedostoihin perustuvissa Power BI ‑raporteissa ja koontinäytöissä. 

Tiedostojen lisääminen sovellustyötilaan on kaksivaiheinen prosessi: 

1. Ensin sinun on [ladattava tiedostot sovellustyötilasi OneDrive for Business ‑tallennustilaan](service-connect-to-files-in-app-workspace-onedrive-for-business.md#1-upload-files-to-the-onedrive-for-business-for-your-app-workspace).
2. Sitten sinun on [muodostettava tiedostoihin yhteys Power BI:stä](service-connect-to-files-in-app-workspace-onedrive-for-business.md#2-import-excel-files-as-datasets-or-as-excel-online-workbooks).

> [!NOTE]
> Sovellustyötilat ovat käytettävissä vain [Power BI Pro:ssa](service-free-vs-pro.md).
> 
> 

## <a name="1-upload-files-to-the-onedrive-for-business-for-your-app-workspace"></a>1. Tiedostojen lataaminen sovellustyötilasi OneDrive for Business ‑tallennustilaan
1. Valitse Power BI -palvelussa kohdan Työtilat vieressä oleva nuoli > valitse työtilasi nimen vierestä kolme pistettä (**…**). 
   
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

* Voit [tuoda Excel-työkirjan tiedot tietojoukkona](service-get-data-from-files.md) ja käyttää tietoja sellaisten raporttien ja koontinäyttöjen luomiseen, joita voi tarkastella verkkoselaimessa ja mobiililaitteilla.
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
   
    Tässä vaiheessa sinun on päätettävä, haluatko [tuoda tiedot Excel-työkirjasta](service-get-data-from-files.md) vai [muodostaa yhteyden Excel-työkirjoihin kokonaisuudessaan](service-excel-workbook-files.md).
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

