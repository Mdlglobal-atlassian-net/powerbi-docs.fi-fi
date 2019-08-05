---
title: Korostaminen
description: Arvopistevalintojen korostaminen Power BI:n visualisoinneissa
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 1ee45781ddc29eee9eeab23a5d748fb7752fe907
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424811"
---
# <a name="highlight-data-points-in-power-bi-visuals"></a>Korosta arvopisteitä Power BI:n visualisoinneissa

Oletusarvon mukaan aina, kun elementti valitaan, `values`-matriisi `dataView`-objektissa suodatetaan vain valittuihin arvoihin. Se saa kaikki muut sivun visualisoinnit näyttämään vain valitut tiedot.

![`tietonäkymän` korostaminen oletustoiminta](./media/highlight-dataview.png)

Jos määrität `supportsHighlight`-ominaisuuden arvoksi `true` kohteessa `capabilities.json`, saat täyden suodattamattoman `values`-matriisin sekä `highlights`-matriisin. `highlights`-matriisi on yhtä pitkä kuin arvomatriisi, ja valitsemattomat arvot asetetaan arvoon `null`. Kun tämä ominaisuus on käytössä, on visualisoinnin vastuulla korostaa asianmukaiset tiedot vertaamalla `values`-matriisia `highlights`-matriisiin.

![`tietonäkymän` korostaminen tukee korostamista](./media/highlight-dataview-supports.png)

Tässä esimerkissä huomaat valittuna olevan 1-palkin. Se on korostusmatriisin ainoa arvo. On myös tärkeää huomata, että käytössä voisi olla useita valintoja ja osittainen korostus. Vastaava numeerinen arvo arvo- ja korostusmatriiseissa on olemassa, mutta se ei ole sama.
