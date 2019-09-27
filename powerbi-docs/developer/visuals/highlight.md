---
title: Korostaminen
description: Arvopistevalintojen korostaminen Power BI:n visualisoinneissa
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 4ff2187dc99d4e790b08c11f55a37e31e85693ad
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/23/2019
ms.locfileid: "71193990"
---
# <a name="highlight-data-points-in-power-bi-visuals"></a>Korosta arvopisteitä Power BI:n visualisoinneissa

Oletusarvon mukaan aina, kun elementti valitaan, `values`-matriisi `dataView`-objektissa suodatetaan vain valittuihin arvoihin. Se saa kaikki muut sivun visualisoinnit näyttämään vain valitut tiedot.

![`tietonäkymän` korostaminen oletustoiminta](./media/highlight-dataview.png)

Jos määrität `supportsHighlight`-ominaisuuden arvoksi `true` kohteessa `capabilities.json`, saat täyden suodattamattoman `values`-matriisin sekä `highlights`-matriisin. `highlights`-matriisi on yhtä pitkä kuin arvomatriisi, ja valitsemattomat arvot asetetaan arvoon `null`. Kun tämä ominaisuus on käytössä, on visualisoinnin vastuulla korostaa asianmukaiset tiedot vertaamalla `values`-matriisia `highlights`-matriisiin.

![`tietonäkymän` korostaminen tukee korostamista](./media/highlight-dataview-supports.png)

Tässä esimerkissä huomaat valittuna olevan 1-palkin. Se on korostusmatriisin ainoa arvo. On myös tärkeää huomata, että käytössä voisi olla useita valintoja ja osittainen korostus. Vastaava numeerinen arvo arvo- ja korostusmatriiseissa on olemassa, mutta se ei ole sama.
