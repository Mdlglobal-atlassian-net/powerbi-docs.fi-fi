---
title: Visualisointien toimintatavat raportissa
description: Ohje Power BI -käyttäjille, jossa kerrotaan visualisointien käsittelemisestä raporttisivulla.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 3a73656d8de462dfc7d1d9e7ac742d588cc8c810
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/04/2019
ms.locfileid: "71943904"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Visualisointien ristiinsuodatus keskenään Power BI -raportissa
Yksi Power BI:n mahtavista ominaisuuksista on se, että kaikki raporttisivun visualisoinnit on yhdistetty toisiinsa. Jos valitset jonkin visualisoinnin arvopisteen, myös sivun kaikki muut kyseisen tiedon sisältävät visualisoinnit muuttuvat valinnan perusteella. 

![video visualisointien käsittelystä](media/end-user-interactions/interactions.gif)

## <a name="how-visuals-interact-with-each-other"></a>Visualisointien keskinäinen vuorovaikutus

Jos valitset arvopisteen yhdessä raporttisivun visualisoinnissa, ristiinsuodatat tai ristiinkorostat oletusarvoisesti sivun muut visualisoinnit. Raporttien *suunnitteluohjelma* määrittää sen, miten sivun visualisoinnit vaikuttavat toisiinsa. *Suunnitteluohjelmassa* visualisointien vuorovaikutus voidaan esimerkiksi ottaa käyttöön tai poistaa käytöstä ja lisäksi voidaan muuttaa ristiinsuodatuksen, ristiinkorostuksen ja [porautumisen](end-user-drill.md) oletusarvoja. 

Jos et ole vielä käyttänyt hierarkioita tai porautumista, voit oppia niistä lukemalla [porautumisesta Power BI:ssä](end-user-drill.md). 

Ristiinsuodatus ja ristiinkorostus voivat olla hyödyllisiä tapoja selvittää, miten yksi arvo tiedoissasi vaikuttaa toisiin. Voit esimerkiksi valita rengaskaavion valvontaosion, jolloin korostat tämän osion vaikutusta jokaiseen sarakkeeseen kuukausittaisten yksiköiden kokonaismäärän kaaviossa ja suodatat oikeanpuoleisen viivakaavion.

![kuva visualisointien vuorovaikutuksesta](media/end-user-interactions/power-bi-interactions.png)

Katso [Tietoja suodattamisesta ja korostamisesta](end-user-report-filter.md). 


  
> [!NOTE]
> Termejä *ristiinsuodatus* ja *ristiinkorostus* käytetään tässä kuvatun toiminnan erottamiseksi siitä, mitä tapahtuu, kun käytät visualisointien suodattamiseen ja korostamiseen **Suodattimet**-ruutua.  

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
- Jos raportissasi on visualisointi, joka tukee [porautumista](end-user-drill.md), yhteen visualisointiin porautuminen ei oletusarvoisesti vaikuta muihin raporttisivun visualisointeihin.     
- Jos käytät visualisointi A:ta vuorovaikutukseen visualisointi B:n kanssa, visualisointi A:n visualisointitason suodattimia käytetään visualisointi B:ssä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Raporttisuodattimien käyttäminen](../power-bi-how-to-report-filter.md)
