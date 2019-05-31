---
title: Visualisointien toimintatavat raportissa
description: Ohje Power BI -käyttäjille, jossa kerrotaan visualisointien käsittelemisestä raporttisivulla.
author: mihart
manager: kvivek
ms.custom: seodec18
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 7148a52d7c7475fbe685f83b1e1cc325521460db
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413152"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Visualisointien ristiinsuodatus keskenään Power BI -raportissa
Yksi Power BI:n mahtavista ominaisuuksista on se, että kaikki raporttisivun visualisoinnit on yhdistetty toisiinsa. Jos valitset jonkin visualisoinnin arvopisteen, myös sivun kaikki muut kyseisen tiedon sisältävät visualisoinnit muuttuvat valinnan perusteella. 

![video visualisointien käsittelystä](media/end-user-interactions/interactions.gif)

Oletusarvon mukaan, valitsemalla tietopisteen yhdessä visualisoinnissa, raporttisivun ristisuodattaa ristiinkorostaa ja porautua sivun muita visualisointeja. 

Tämä on hyvä tunnistaa, miten yksi arvo tietojen osallistuu toiseen. Esimerkiksi valitsemalla Kohtuus-segmentissä rengaskaavion, korostaa kyseisen segmentistä edistää yksiköiden mukaan kuukauden kaavion sarakkeiden, ja se on suodatettu oikealla viivakaavio.

![Kuva visualisointien käyttäminen](media/end-user-interactions/power-bi-interactions.png)

Katso [Tietoja suodattamisesta ja korostamisesta](../power-bi-reports-filters-and-highlighting.md). 

Raporttien *suunnitteluohjelma* määrittää sen, miten sivun visualisoinnit vaikuttavat toisiinsa. Suunnitteluohjelmassa visualisointien vuorovaikutus voidaan esimerkiksi ottaa käyttöön tai poistaa käytöstä ja lisäksi voidaan muuttaa ristiinsuodatuksen, ristiinkorostuksen ja porautumisen oletusarvoja. 
  
> [!NOTE]
> Termejä *ristiinsuodatus* ja *ristiinkorostus* käytetään tässä kuvatun toiminnan erottamiseksi siitä, mitä tapahtuu, kun käytät visualisointien suodattamiseen ja korostamiseen **Suodattimet**-ruutua.  

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
- Jos raportissa on visualisointi, joka tukee [porautumista](../power-bi-visualization-drill-down.md), oletusarvoisesti yksi visualisointi porautuminen ei vaikuta muihin raporttisivun visualisointeihin.     
- Jos käytät visualA visualB käyttämiseksi, visuaalisen tason suodattimet visualA otetaan visualB.

## <a name="next-steps"></a>Seuraavat vaiheet
[Raporttisuodattimien käyttäminen](../power-bi-how-to-report-filter.md)
