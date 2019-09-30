---
title: Visualisointien toimintatavat raportissa
description: Ohje Power BI -käyttäjille, jossa kerrotaan visualisointien käsittelemisestä raporttisivulla.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 09/24/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: b95df5c32d9058e4480d7af5e226a971ba581144
ms.sourcegitcommit: 02042995df12cc4e4b97eb8a369e62364eb5af36
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/25/2019
ms.locfileid: "71256289"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Visualisointien ristiinsuodatus keskenään Power BI -raportissa
Yksi Power BI:n mahtavista ominaisuuksista on se, että kaikki raporttisivun visualisoinnit on yhdistetty toisiinsa. Jos valitset jonkin visualisoinnin arvopisteen, myös sivun kaikki muut kyseisen tiedon sisältävät visualisoinnit muuttuvat valinnan perusteella. 

![video visualisointien käsittelystä](media/end-user-interactions/interactions.gif)

Jos valitset arvopisteen yhdessä raporttisivun visualisoinnissa, ristiinsuodatat ja ristiinkorostat oletusarvoisesti sivun muita visualisointeja ja poraudut niihin. 

Tämä voi olla hyödyllinen tapa selvittää, miten yksi arvo tiedoissasi vaikuttaa toiseen. Voit esimerkiksi valita rengaskaavion valvontaosion, jolloin korostat tämän osion vaikutusta jokaiseen sarakkeeseen kuukausittaisten yksiköiden kokonaismäärän kaaviossa, oikeanpuoleinen viivakaavio suodatettuna.

![kuva visualisointien vuorovaikutuksesta](media/end-user-interactions/power-bi-interactions.png)

Katso [Tietoja suodattamisesta ja korostamisesta](../power-bi-reports-filters-and-highlighting.md). 

Raporttien *suunnitteluohjelma* määrittää sen, miten sivun visualisoinnit vaikuttavat toisiinsa. Suunnitteluohjelmassa visualisointien vuorovaikutus voidaan esimerkiksi ottaa käyttöön tai poistaa käytöstä ja lisäksi voidaan muuttaa ristiinsuodatuksen, ristiinkorostuksen ja porautumisen oletusarvoja. 
  
> [!NOTE]
> Termejä *ristiinsuodatus* ja *ristiinkorostus* käytetään tässä kuvatun toiminnan erottamiseksi siitä, mitä tapahtuu, kun käytät visualisointien suodattamiseen ja korostamiseen **Suodattimet**-ruutua.  

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
- Jos raportissasi on visualisointi, joka tukee [porautumista](../power-bi-visualization-drill-down.md), yhteen visualisointiin porautuminen ei oletusarvoisesti vaikuta muihin raporttisivun visualisointeihin.     
- Jos käytät visualisointi A:ta vuorovaikutukseen visualisointi B:n kanssa, visualisointi A:n visualisointitason suodattimia käytetään visualisointi B:ssä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Raporttisuodattimien käyttäminen](../power-bi-how-to-report-filter.md)
