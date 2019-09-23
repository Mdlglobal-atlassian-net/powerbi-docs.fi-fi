---
ms.openlocfilehash: cd6ea6fd52f929e2cd254214cf0e8c96e858f6c2
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61273398"
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

> Videon sisällön on luonut [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax).
> 
> 

