---
title: Visualisointien toimintatavat raportissa
description: Ohje Power BI -käyttäjille, jossa kerrotaan visualisointien käsittelemisestä raporttisivulla.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 12/18/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: dc8dad0417ac2ed6498fb7612900ebdbb0ce2a18
ms.sourcegitcommit: 4359baa43ca01b179d28ec59f4e61ba8c07ee288
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/20/2019
ms.locfileid: "75303861"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Visualisointien ristiinsuodatus keskenään Power BI -raportissa
Yksi Power BI:n mahtavista ominaisuuksista on se, että kaikki raporttisivun visualisoinnit on yhdistetty toisiinsa. Jos valitset jonkin visualisoinnin arvopisteen, myös sivun kaikki muut kyseisen tiedon sisältävät visualisoinnit muuttuvat valinnan perusteella. 

![video visualisointien käsittelystä](media/end-user-interactions/interactions.gif)

## <a name="how-visuals-interact-with-each-other"></a>Visualisointien keskinäinen vuorovaikutus

Jos valitset arvopisteen yhdessä raporttisivun visualisoinnissa, ristiinsuodatat tai ristiinkorostat oletusarvoisesti sivun muut visualisoinnit. Raporttien *suunnitteluohjelma* määrittää sen, miten sivun visualisoinnit vaikuttavat toisiinsa. *Suunnitteluohjelmassa* visualisointien vuorovaikutus voidaan esimerkiksi ottaa käyttöön tai poistaa käytöstä ja lisäksi voidaan muuttaa ristiinsuodatuksen, ristiinkorostuksen ja [porautumisen](end-user-drill.md) oletusarvoja. 

Jos et ole vielä käyttänyt hierarkioita tai porautumista, voit oppia niistä lukemalla [porautumisesta Power BI:ssä](end-user-drill.md). 

### <a name="cross-filtering-and-cross-highlighting"></a>Ristiinkorostus ja ristiinsuodatus

Ristiinsuodatus ja ristiinkorostus voivat olla hyödyllisiä tapoja selvittää, miten yksi arvo tiedoissasi vaikuttaa toisiin. Termejä *ristiinsuodatus* ja *ristiinkorostus* käytetään tässä kuvatun toiminnan erottamiseksi siitä, mitä tapahtuu, kun käytät visualisointien suodattamiseen ja korostamiseen **Suodattimet**-ruutua.  

Määritellään nämä ehdot alla olevien raporttisivujen tarkastelua varten. Luokan volyymi yhteensä segmenteittäin -rengaskaaviossa on kaksi arvoa: Kohtuus ja Mukavuus. 

![Raporttisivu](media/end-user-interactions/power-bi-interactions-before.png)

1. Katsotaan, mitä tapahtuu, kun valitsemme vaihtoehdon **Kohtuus**.

    ![Raporttisivu rengaskaavion Kohtuus-segmentti valittuna](media/end-user-interactions/power-bi-interactions-after.png)

2. **Ristiinsuodatus** poistaa tiedot, joita ei käytetä. **Kohtuus**-vaihtoehdon valitseminen rengaskaaviosta ristiinsuodattaa viivakaavion. Viivakaavio näyttää nyt vain Kohtuus-segmenttiä koskevat arvopisteet. 

3. **Ristiinkorostus** säilyttää kaikki alkuperäiset arvopisteet, mutta himmentää osan, joka ei koske valintaasi. **Kohtuus**-vaihtoehdon valitseminen rengaskaaviosta ristiinkorostaa pylväskaavion. Pylväskaavio himmentää kaikki tiedot, jotka koskevat Mukavuus-segmenttiä, ja korostaa kaikki tiedot, jotka koskevat Kohtuus-segmenttiä. 


## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
- Jos raportissasi on visualisointi, joka tukee [porautumista](end-user-drill.md), yhteen visualisointiin porautuminen ei oletusarvoisesti vaikuta muihin raporttisivun visualisointeihin.     
- Visuaalisen tason suodattimet säilytetään, kun muita visualisointeja ristiinsuodatetaan ja ristiinkorostetaan raporttisivulla. Jos raportin suunnittelija on ottanut tai sinä itse olet ottanut käyttöön Visualisoinnissa A 2visuaalisen tason suodattimia ja käytät visualisoinnin A avulla visualisointia B, visualisointitason suodattimia visualisoinnista A käytetään visualisoinnissa B.

    ![Raporttisivu rengaskaavion Kohtuus-segmentti valittuna](media/end-user-interactions/power-bi-visual-filters.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Raporttisuodattimien käyttäminen](../power-bi-how-to-report-filter.md)    


[Tietoja suodattamisesta ja korostamisesta](end-user-report-filter.md). 
