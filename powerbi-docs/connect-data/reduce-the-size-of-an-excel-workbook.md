---
title: Excel-työkirjan koon pienentäminen Power BI:ssä tarkastelua varten
description: Excel-työkirjan koon pienentäminen Power BI:ssä tarkastelua varten
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/10/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 8c58c85ea46f9884586e1ff73f1ef9f7b1db9cdd
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83327227"
---
# <a name="reduce-the-size-of-an-excel-workbook-to-view-it-in-power-bi"></a>Excel-työkirjan koon pienentäminen Power BI:ssä tarkastelua varten
Voit ladata minkä tahansa, alle 1 Gt:n kokoisen Excel-työkirjan Power BI:hin. Excel-työkirjassa voi olla kaksi osaa: tietomalli ja raportin muut osat eli laskentataulukon ydinsisältö. Jos raportti täyttää seuraavat kokorajoitukset, voit tallentaa sen **OneDrive for Businessiin**. muodostaa siihen yhteyden Power BI:stä ja tarkastella sitä Excel Onlinessa:

* Työkirja kokonaisuutena voi olla enintään 1 Gt.
* Laskentataulukon ydinsisältö voi olla enintään 30 Mt.

## <a name="what-makes-core-worksheet-contents-larger-than-30-mb"></a>Mikä tekee laskentataulukon ydinsisällöstä yli 30 Mt:n suuruisen?
Seuraavassa on joitakin elementtejä, jotka voivat tehdä laskentataulukon ydinsisällöstä yli 30 Mt:n suuruisen:

* Kuvat.
* Sävytetyt solut. [Poista solujen sävytysmuoto](https://support.office.com/article/Add-or-change-the-background-color-of-cells-ac10f131-b847-428f-b656-d65375fb815e).
* Värilliset laskentataulukot. [Poista taulukon tausta](https://support.office.com/article/add-or-remove-a-sheet-background-3577a762-8450-4556-96a2-cc265abc00a8).
* Tekstiruudut.
* ClipArt-kuvat.

Harkitse näiden elementtien poistamista, jos se on mahdollista. 

Jos raportissa on tietomalli, sinulla on muita vaihtoehtoja: 

* Poista tietoja Excel-laskentataulukosta ja tallenna ne sen sijaan tietomalliin. Katso lisätietoja alta kohdasta ”Laskentataulukoiden tietojen poistaminen”. 
* [Luo muistia säästävä tietomalli](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70) pienentääksesi raportin kokonaiskokoa.

Jotta voit tehdä tällaisia muutoksia, sinun pitää muokata työkirjaa Excelissä.

Lue lisää [Excel-työkirjojen tiedostokokorajoituksista SharePoint Onlinessa](https://support.office.com/article/File-size-limits-for-workbooks-in-SharePoint-Online-9e5bc6f8-018f-415a-b890-5452687b325e).

## <a name="remove-data-from-worksheets"></a>Laskentataulukoiden tietojen poistaminen
Jos tuot tiedot Exceliin Power Query- tai Excel-tiedot-välilehdestä, työkirjassa saattaa olla samat tiedot Excel-taulukossa ja tietomallissa. Excel-laskentataulukoiden suuret taulukot voivat tehdä laskentataulukon ydinsisällöstä yli 30 Mt:n suuruisen. Poistamalla taulukon Excelistä ja säilyttämällä tiedot tietomallissa voit pienentää huomattavasti raportin laskentataulukon ydinsisällön kokoa. 

Kun tuot tiedot Exceliin, noudata seuraavia vihjeitä:

* **Power Query**: tyhjennä **Lataa laskentataulukkoon** -ruutu.
  
  Tiedot tuodaan vain tietomalliin, eikä Excel-laskentataulukoissa ole tietoja.
* **Excel-tiedot-välilehdestä**, jos aiemmin valitsit **Taulukko**-kohdan ohjatussa tuonnissa: Siirry kohtaan **Aiemmin luodut yhteydet**\> valitse yhteys \>**Luo vain yhteys**. Poista alkuperäinen taulukko tai alkuperäiset taulukot, jotka luotiin ensimmäisen tuonnin aikana.
* **Excel-tiedot-välilehdestä**: älä valitse **Taulukko**-kohtaa **Tuo tiedot** -ruudussa.

## <a name="workbook-size-optimizer"></a>Työkirjan koon optimointityökalu
Jos työkirja sisältää tietomallin, suorittamalla työkirjan koon optimointityökalun voit pienentää työkirjan kokoa. [Lataa Työkirjan koon optimointityökalu](https://www.microsoft.com/download/details.aspx?id=38793).

## <a name="related-info"></a>Aiheeseen liittyvät tiedot
[Luo muistia säästävä tietomalli](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)

[OneDrive for Business -linkkien käyttö Power BI Desktopissa](desktop-use-onedrive-business-links.md)

