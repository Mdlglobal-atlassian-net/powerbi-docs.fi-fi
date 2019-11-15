---
title: Power BI-visualisoinnin luomiseen käytettyjen tietojen näyttäminen
description: Tässä asiakirjassa kerrotaan, miten voidaan näyttää visualisoinnin luomiseen käytetyt tiedot Power BI:ssä ja miten kyseiset tiedot viedään .csv-tiedostoon.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/4/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 5417511b12c85cb467c3613671a1e101541c9609
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880629"
---
# <a name="show-the-data-that-was-used-to-create-the-visualization"></a>Visualisoinnin luomiseen käytettyjen tietojen näyttäminen
## <a name="show-data"></a>Näytä tiedot
Power BI:n visualisointi rakentuu tietojoukoissasi olevista tiedoista. Jos olet kiinnostunut taustatoiminnoista, Power BI:n avulla voit *tarkastella* visualisoinnin luomiseen käytettyjä tietoja. Kun valitset **Näytä tiedot**, Power BI näyttää tiedot visualisoinnin alla (tai vieressä).

Voit myös viedä visualisoinnin luomiseen käytetyt tiedot .xlsx- tai .csv-tiedostona ja tarkastella tietoja Excelissä. Katso lisätietoja artikkelista [Tietojen vieminen Power BI -visualisoinneista](power-bi-visualization-export-data.md).

> [!NOTE]
> *Näytä tiedot* ja *Vie tiedot* ovat kumpikin käytettävissä Power BI -palvelussa ja Power BI Desktopissa. Power BI Desktop sisältää kuitenkin yhden lisäkerroksen: [*Näytä tietueet* näyttää tietojoukon todelliset rivit](../desktop-see-data-see-records.md).
> 
> 

## <a name="using-show-data"></a>*Näytä tiedot* -ominaisuuden käyttö 
1. Valitse Power BI Desktopista visualisointi, jotta siitä tulee aktiivinen.

2. Valitse **Lisää toimintoja** (...) ja valitse **Näytä tiedot**. 
    ![Näytä tiedot -näyttöasetus](media/service-reports-show-data/power-bi-more-action.png)


3. Tiedot näkyvät oletusarvoisesti visualisoinnin alla.
   
   ![visualisointi ja tietojen pystysuuntainen näyttö](media/service-reports-show-data/power-bi-show-data-below.png)

4. Jos haluat vaihtaa suuntaa, valitse pystysuuntainen asettelu ![pieni näyttökuva, jota käytetään muuttamaan pystysuuntaiseksi asetteluksi](media/service-reports-show-data/power-bi-vertical-icon-new.png) visualisoinnin oikeasta yläkulmasta.
   
   ![visualisointi ja tietojen vaakasuuntainen näyttö](media/service-reports-show-data/power-bi-show-data-side.png)
5. Jos haluat viedä tiedot .csv-tiedostona, valitse kolme pistettä ja valitse **Vie tiedot**.
   
    ![valitse Vie tiedot](media/service-reports-show-data/power-bi-export-data-new.png)
   
    Katso lisätietoja tietojen viemisestä Exceliin artikkelista [Tietojen vieminen Power BI -visualisoinneista](power-bi-visualization-export-data.md).
6. Jos haluat piilottaa tiedot, poista valinta kohdasta **Tutki** > **Näytä tiedot**.

## <a name="using-show-records"></a>Näytä tietueet- toiminnon käyttäminen
Voit myös keskittyä yhden tietueen visualisointiin ja porautua sen pohjana oleviin tietoihin. 

1. **Näytä tietueet** -käyttöä varten valitaan visualisointi, jotta siitä tulee aktiivinen. 

2. Valitse työpöydän valinta nauhasta **Visualisointityökalut** > **Tiedot/Poraudu** > **Näytä tietueet**. 

    ![Näyttökuva, jossa Näytä tietueet valittuna.](media/service-reports-show-data/power-bi-see-record.png)

3. Valitse arvopiste tai rivi visualisoinnissa. Tässä esimerkissä olemme valinneet neljännen sarakkeen vasemmalta. Power BI osoittaa meille tietojoukon tietueen tälle arvo pisteelle.

    ![Näyttökuva yhdestä tietueesta tietojoukossa.](media/service-reports-show-data/power-bi-row.png)

4. Palaa Desktop-raportin pohjaan valitsemalla **Takaisin raporttiin**. 

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

- Jos **Näytä tietueet** -painike on poistettu käytöstä ja himmennettynä valintanauhassa, se tarkoittaa, ettei valittu visualisointi tue Näytä tietueet -toimintoa.
- Et voi muuttaa tietoja Näytä tietueita -näkymässä ja tallentaa niitä takaisin raporttiin.
- Et voi käyttää Näytä tietueet -toimintoa, kun visualisointi käyttää laskettua mittaria.
- Et voi käyttää Näytä tietueet -toimintoa, kun olet yhteydessä reaaliaikaiseen MD-malliin.  

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietojen vieminen Power BI -visualisoinneista](power-bi-visualization-export-data.md)    

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

