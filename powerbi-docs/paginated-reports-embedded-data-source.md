---
title: Sivutettujen raporttien upotetut tietolähteet Power BI -palvelussa (esikatselu)
description: Tässä artikkelissa opit luomaan upotetun tietolähteen sivutettuun raporttiin Power BI -palvelussa ja muokkaamaan sitä.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 11/05/2018
ms.openlocfilehash: 7f919234f7635c76ce50d0bfffa393498f141da8
ms.sourcegitcommit: 91ac6185f7026ddbaa925dc54057bb742b4fa411
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2019
ms.locfileid: "56324388"
---
# <a name="create-an-embedded-data-source-for-paginated-reports-in-the-power-bi-service-preview"></a>Upotetun tietolähteen luominen sivutettuun raporttiin Power BI -palvelussa (esikatselu)

Tässä artikkelissa opit luomaan upotetun tietolähteen sivutettuun raporttiin Power BI -palvelussa ja muokkaamaan sitä. Määrität upotetun tietolähteen yhdessä raportissa, ja käytät sitä vain kyseisessä raportissa. Power BI -palveluun tällä hetkellä julkaistavat sivutetut raportit edellyttävät upotettuja tietojoukkoja ja upotettuja tietolähteitä, ja ne voidaan yhdistää seuraaviin tietolähteisiin:

- Azuren SQL-tietokanta ja tietovarasto
- SQL Server
- SQL Server Analysis Services 

Sivutetut raportit yhdistetään paikallisiin tietolähteisiin yhdyskäytävän avulla. Määrität yhdyskäytävän, kun olet julkaissut raportin Power BI -palveluun. Lue lisätietoja [Power BI -yhdyskäytävistä](service-gateway-getting-started.md). 

## <a name="create-an-embedded-data-source"></a>Upotetun tietolähteen luominen
  
1. Avaa Raportin muodostin.

1. Valitse raporttitietoruudun työkaluriviltä **Uusi** > **tietolähde**. **Tietolähteen ominaisuudet** -valintaikkuna avautuu.

    ![Uusi tietolähde](media/paginated-reports-embedded-data-source/power-bi-paginated-new-data-source.png)
  
2.  Kirjoita tietolähteen nimi **Nimi**-tekstiruutuun tai hyväksy oletusnimi.  
  
3.  Valitse **Käytä omaan raporttiin upotettua yhteyttä**.  
  
1.  Valitse tietolähteen tyyppi **Valitse yhteystyyppi** -luettelosta. 

1.  Määritä yhteysmerkkijono käyttämällä jotakin seuraavista menetelmistä:  
  
    -   Kirjoita yhteysmerkkijono suoraan **Yhteysmerkkijono**-tekstiruutuun. 
  
    -   Luo lauseke, joka antaa tulokseksi yhteysmerkkijonon, valitsemalla lausekepainike (**fx)**. Kirjoita lauseke Lauseke-ruutuun **Lauseke**-valintaikkunassa. Valitse **OK**. 
  
    -   Valitse **Muodosta**, niin vaiheessa 2 valitsemasi tietolähteen **Yhteyden ominaisuudet** -valintaikkuna avautuu.  
  
        Täytä **Yhteyden ominaisuudet** -valintaikkunan kentät tietolähdetyypin tiedoilla. Yhteyden ominaisuuksiin kuuluvat tietolähteen tyyppi, tietolähteen nimi ja tunnistetiedot. Kun olet määrittänyt arvot tässä valintaikkunassa, valitse **Testaa yhteyttä** varmistaaksesi, että tietolähde on käytettävissä ja että määrittämäsi tunnistetiedot ovat oikeat.  
  
4.  Valitse **Tunnistetiedot**.  
  
     Määritä tälle tietolähteelle käytettävät tunnistetiedot. Tietolähteen omistaja valitsee tuetun tunnistetietotyypin. Jos haluat lisätietoja, katso [Raportin tietolähteiden tunnistetietojen ja yhteystietojen määritys](https://docs.microsoft.com/sql/reporting-services/report-data/specify-credential-and-connection-information-for-report-data-sources).
  
5.  Valitse **OK**.  
  
     Tietolähde näkyy raporttitietoruudussa.  

## <a name="next-steps"></a>Seuraavat vaiheet

- [Upotetun tietojoukon luominen sivutettuun raporttiin Power BI -palvelussa](paginated-reports-create-embedded-dataset.md)
- [Mitä ovat sivutetut raportit Power BI Premiumissa? (esikatselu)](paginated-reports-report-builder-power-bi.md)