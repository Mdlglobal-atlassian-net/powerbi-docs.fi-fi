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
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 43046a5fab33f384a6d9f573a992843fa84a0713
ms.sourcegitcommit: a054782370dec56d49bb205ee10b7e2018f22693
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/22/2019
ms.locfileid: "56662223"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Visualisointien ristiinsuodatus keskenään Power BI -raportissa
Yksi Power BI:n mahtavista ominaisuuksista on se, että kaikki raporttisivun visualisoinnit on yhdistetty toisiinsa. Jos valitset jonkin visualisoinnin arvopisteen, myös sivun kaikki muut kyseisen tiedon sisältävät visualisoinnit muuttuvat valinnan perusteella. 

![video visualisointien käsittelystä](media/end-user-interactions/interactions.gif)

Raporttisivun visualisoinneilla voi oletusarvoisesti ristiinsuodattaa ja ristiinkorostaa sivun muita visualisointeja ja porautua niihin. Esimerkiksi osavaltion valitseminen karttavisualisoinnissa voi korostaa sarakekaavion ja suodattaa viivakaavion näyttämään vain yhtä osavaltiota koskevat tiedot.

Katso [Tietoja suodattamisesta ja korostamisesta](../power-bi-reports-filters-and-highlighting.md). Jos sinulla on visualisointi, joka tukee [porautumista](../power-bi-visualization-drill-down.md), yhteen visualisointiin porautuminen ei oletusarvoisesti vaikuta muihin raporttisivun visualisointeihin. 

Raporttien *suunnitteluohjelma* määrittää sen, miten sivun visualisoinnit vaikuttavat toisiinsa. Suunnitteluohjelmassa visualisointien vuorovaikutus voidaan esimerkiksi ottaa käyttöön tai poistaa käytöstä ja lisäksi voidaan muuttaa ristiinsuodatuksen, ristiinkorostuksen ja porautumisen oletusarvoja.
  
> [!NOTE]
> Termejä *ristiinsuodatus* ja *ristiinkorostus* käytetään tässä kuvatun toiminnan erottamiseksi siitä, mitä tapahtuu, kun käytät visualisointien suodattamiseen ja korostamiseen **Suodattimet**-ruutua.  

### <a name="next-steps"></a>Seuraavat vaiheet
[Raporttisuodattimien käyttäminen](../power-bi-how-to-report-filter.md)
