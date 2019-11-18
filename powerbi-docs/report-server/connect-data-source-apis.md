---
title: Tietolähteen yhteysmerkkijonon muuttaminen PowerShellin avulla
description: Muuta tietolähteen yhteysmerkkijonoja käyttämällä ohjelmointirajapintoja PowerShellissä – Power BI-raporttipalvelin.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 10/24/2019
ms.author: maggies
ms.openlocfilehash: 77716514ffbb6dc8d3f128ada85276b46bf7af05
ms.sourcegitcommit: 17f45a81b0dcbf9e3f1fb2a551584170baecd320
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/25/2019
ms.locfileid: "72923661"
---
# <a name="change-data-source-connection-strings-in-power-bi-reports-with-powershell---power-bi-report-server"></a>Muuta tietolähteen yhteysmerkkijonoja Power BI -raporteissa PowerShellillä – Power BI-raporttipalvelin

Voit muuttaa tietolähteen yhteysmerkkijonoja Power BI -raporttipalvelimen Power BI -raporteissa käyttämällä ohjelmointirajapintoja PowerShellissä. 

1. Asenna Power BI -raporttipalvelimen PowerShell-komentosovelmat. Komentosovelmat ja asennusohjeet ovat osoitteessa [https://github.com/Microsoft/ReportingServicesTools](https://github.com/Microsoft/ReportingServicesTools). 

2. Nouda Power BI -tiedoston olemassa olevat tietolähdetiedot PowerShell-komentosovelmilla:

    ```powershell
    Get-RsRestItemDataSource -RsItem '/MyPbixReport'
    ```

    Jos haluat tarkastella Power BI -raportin sisältämän ensimmäisen tietolähteen tietoja: 

    ```powershell
    $dataSources[0]
    ```

3. Päivitä tarvittaessa yhteyttä ja tunnistetietoja koskevat tiedot. Jos yhteysmerkkijonon ja tietolähteen päivityksessä käytetään tallennettuja tunnistetietoja, sinun on annettava tilin salasana. 

    Tietolähteen yhteysmerkkijonon päivittäminen:

    ```powershell
    $dataSources[0].ConnectionString = 'data source=myCatalogServer;initial catalog=ReportServer;persist security info=False' 
    ```

    Tietolähteen tunnistetietotyypin muuttaminen:

    ```powershell
    $dataSources[0].DataModelDataSource.AuthType = 'Integrated'
    ```

    Tietolähteen käyttäjänimen ja salasanan muuttaminen:

    ```powershell
    $dataSources[0].DataModelDataSource.Username = 'domain\user
    ```
    ```powershell
    $dataSources[0].DataModelDataSource.Secret = 'password'
    ```

4. Tallenna päivitetyt tunnistetiedot takaisin palvelimeen.

    ```powershell
    Set-RsRestItemDataSource -RsItem '/MyPbixReport' -RsItemType 'PowerBIReport' -DataSources $dataSources
    ```

## <a name="next-steps"></a>Seuraavat vaiheet

[Sivutetun raportin tietolähteet Power BI -raporttipalvelimessa](connect-data-sources.md) 

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

