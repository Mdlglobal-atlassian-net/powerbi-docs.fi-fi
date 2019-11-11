---
ms.openlocfilehash: 679c3e8c3d94c93899e9dcfae1e57f4b678fb218
ms.sourcegitcommit: a5853ef44ed52e80eabee3757bb6887fa400b75b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799805"
---
Power BI:llä voit luoda suhteita useiden taulukoiden välille, mukaan lukien taulukot, jotka ovat peräisin täysin eri tietolähteistä. Näet minkä tahansa tietomallin tällaiset suhteet Power BI Desktopin **Suhteet**-näkymässä.

![](media/7-5-table-relationships-and-dax/dax-relationships_1.png)

## <a name="dax-relational-functions"></a>DAX:n relaatiofunktiot
DAX:ssä on **relaatiofunktioita**, joilla voit hyödyntää taulukoita, joille on määritetty suhteita.

DAX-funktioilla voit palauttaa sarakkeen arvon tai kaikki suhteen rivit.

Esimerkiksi **RELATED**-funktio seuraa suhteita ja palauttaa sarakkeen arvon, kun taas **RELATEDTABLE** seuraa suhteita ja palauttaa koko taulukon, joka on suodatettu sisältämään vain liittyvät rivit.

![](media/7-5-table-relationships-and-dax/dax-relationships_2.png)

**RELATED**-funktio käyttää *monesta yhteen* -suhteita, kun taas **RELATEDTABLE**-funktio käyttää *yhdestä moneen* -suhteita.

Relaatiofunktioiden avulla voit luoda lausekkeita, jotka sisältävät arvoja useista taulukoista. DAX palauttaa tuloksen näillä funktioilla riippumatta suhdeketjun pituudesta.

> Videon sisällön on luonut [Alberto Ferrari, SQLBI](https://www.sqlbi.com/learning-dax).
> 
> 

