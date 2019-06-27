---
title: Sivutettujen raporttien upotetut tietolähteet Power BI -palvelussa
description: Tässä artikkelissa opit luomaan upotetun tietolähteen sivutettuun raporttiin Power BI -palvelussa ja muokkaamaan sitä.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 06/06/2019
ms.openlocfilehash: 7b687fd67f844e000811ae00a53772ab9403ab90
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/12/2019
ms.locfileid: "66838929"
---
# <a name="create-an-embedded-data-source-for-paginated-reports-in-the-power-bi-service"></a>Upotetun tietolähteen luominen sivutettuun raporttiin Power BI -palvelussa

Tässä artikkelissa opit luomaan upotetun tietolähteen sivutettuun raporttiin Power BI -palvelussa ja muokkaamaan sitä. Määrität upotetun tietolähteen yhdessä raportissa, ja käytät sitä vain kyseisessä raportissa. Power BI -palveluun tällä hetkellä julkaistavat sivutetut raportit edellyttävät upotettuja tietojoukkoja ja upotettuja tietolähteitä, ja ne voidaan yhdistää seuraaviin tietolähteisiin:

- Azuren SQL-tietokanta ja tietovarasto
- SQL Server
- SQL Server Analysis Services
- Oracle 
- Teradata 

Käytä seuraavien tietolähteiden tapauksessa [SQL Server Analysis Services -yhteysvaihtoehtoa](service-premium-connect-tools.md):

- Azure Analysis Services
- Power BI Premium -tietojoukot

Sivutetut raportit yhdistetään paikallisiin tietolähteisiin [Power BI -yhdyskäytävän avulla](service-gateway-getting-started.md). Määrität yhdyskäytävän, kun olet julkaissut raportin Power BI -palveluun.

Katso lisätiedot kohdasta [Raporttitiedot Power BI:n raportin muodostimessa](report-builder-data.md).

## <a name="create-an-embedded-data-source"></a>Upotetun tietolähteen luominen
  
1. Avaa Power BI:n raportin muodostin.

1. Valitse raporttitietoruudun työkaluriviltä **Uusi** > **tietolähde**. **Tietolähteen ominaisuudet** -valintaikkuna avautuu.

    ![Uusi tietolähde](media/paginated-reports-embedded-data-source/power-bi-paginated-new-data-source.png)
  
2.  Kirjoita tietolähteen nimi **Nimi**-tekstiruutuun tai hyväksy oletusnimi.  
  
3.  Valitse **Käytä omaan raporttiin upotettua yhteyttä**.  
  
1.  Valitse tietolähteen tyyppi **Valitse yhteystyyppi** -luettelosta. 

1.  Määritä yhteysmerkkijono käyttämällä jotakin seuraavista menetelmistä:  
  
    -   Kirjoita yhteysmerkkijono suoraan **Yhteysmerkkijono**-tekstiruutuun. 
  
    -   Luo lauseke, joka antaa tulokseksi yhteysmerkkijonon, valitsemalla lausekepainike (**fx)** . Kirjoita lauseke Lauseke-ruutuun **Lauseke**-valintaikkunassa. Valitse **OK**. 
  
    -   Valitse **Muodosta**, niin vaiheessa 2 valitsemasi tietolähteen **Yhteyden ominaisuudet** -valintaikkuna avautuu.  
  
        Täytä **Yhteyden ominaisuudet** -valintaikkunan kentät tietolähdetyypin tiedoilla. Yhteyden ominaisuuksiin kuuluvat tietolähteen tyyppi, tietolähteen nimi ja tunnistetiedot. Kun olet määrittänyt arvot tässä valintaikkunassa, valitse **Testaa yhteyttä** varmistaaksesi, että tietolähde on käytettävissä ja että määrittämäsi tunnistetiedot ovat oikeat.  
  
4.  Valitse **Tunnistetiedot**.  
  
     Määritä tälle tietolähteelle käytettävät tunnistetiedot. Tietolähteen omistaja valitsee tuetun tunnistetietotyypin. Jos haluat lisätietoja, katso [Raportin tietolähteiden tunnistetietojen ja yhteystietojen määritys](https://docs.microsoft.com/sql/reporting-services/report-data/specify-credential-and-connection-information-for-report-data-sources).
  
5.  Valitse **OK**.  
  
     Tietolähde näkyy raporttitietoruudussa.  

## <a name="next-steps"></a>Seuraavat vaiheet

- [Upotetun tietojoukon luominen sivutettuun raporttiin Power BI -palvelussa](paginated-reports-create-embedded-dataset.md)
- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
