---
title: Visualisointien mukauttaminen raportissa
description: Luo oma näkymä raportista ilman sen muokkaamista.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/09/2020
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 83f040fd021a3d3e1cd6ce344c84051c7ff58bb0
ms.sourcegitcommit: faa8cfb66e79ea16ba46605f752cc9ca57924d0e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83383153"
---
# <a name="personalize-visuals-in-a-report"></a>Visualisointien mukauttaminen raportissa

[!INCLUDE[consumer-appliesto-ynnn](../includes/consumer-appliesto-ynnn.md)]

On vaikea luoda visualisointi, joka täyttää kaikkien vaatimukset. Kun työtoverisi jakaa raportin kanssasi, haluat ehkä tehdä muutoksia visualisointeihin – mutta et halua pyytää työtoveriasi tekemään muutoksia puolestasi. 

Haluat ehkä vaihtaa akselin sisältöä, muuttaa visualisointityyppiä tai lisätä sisältöä työkaluvihjeeseen. **Mukauta tätä visualisointia** -ominaisuuden avulla voit tehdä muutokset itse, ja kun olet muokannut visualisointia haluamallasi tavalla, voit tallentaa sen kirjanmerkiksi ja palata siiten tarvittaessa. Et tarvitse edes raportin muokkausoikeutta.

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize.png" alt-text="Visualisoinnin mukauttaminen":::
 
## <a name="what-you-can-change"></a>Sallitut muutokset

Tämän ominaisuuden avulla voit saada merkityksellisiä tietoja Power BI -raportin visualisointien tapauskohtaisen tutkimisen kautta. Seuraavassa on joitakin muokkauksia, joita voit tehdä. Käytettävissä olevat vaihtoehdot vaihtelevat visualisointityypin mukaan. 

- Visualisointityypin muuttaminen
- Mittayksikön tai dimension vaihtaminen
- Selitteen lisääminen tai poistaminen
- Kahden tai useamman mittarin vertaileminen
- Koosteiden muuttaminen jne.

Uusien etsintäominaisuuksien lisäksi tämä ominaisuus sisältää muutakin. Se sisältää myös tapoja, joilla voit siepata ja jakaa tekemäsi muutokset:

- Muutosten tallentaminen
- Muutosten jakaminen
- Kaikkien raporttiin tekemiesi muutosten palauttaminen
- Kaikkien visualisointiin tekemiesi muutosten palauttaminen
- Viimeaikaisten muutosten tyhjentäminen


## <a name="personalize-visuals-in-the-power-bi-service"></a>Visualisointien mukauttaminen Power BI -palvelussa

Mukauttamalla visualisointia voit tutkia tietoja monella tavalla poistumatta raportin lukunäkymästä. Seuraavissa esimerkeissä näytetään eri tapoja, joilla voit muokata visualisointia vastaamaan omia tarpeitasi. 

1. Avaa raportti lukunäkymässä Power BI -palvelussa.

2. Valitse visualisoinnin valikkoriviltä **Mukauta tätä visualisointia** ![Mukauta tätä visualisointia -kuvake](media/end-user-personalize-visuals/power-bi-personalize-visual-icon.png) -kuvake. 

3. Jos haluat tyhjentää **Mukauta**-kenttiä, valitse **Lisää asetuksia (...)** ja valitse **Poista kenttä**.

### <a name="change-the-visualization-type"></a>Visualisointityypin muuttaminen

Näkyisivätkö tiedot mielestäsi paremmin pinottuna pylväskaaviona? Muuta **visualisointityyppiä**.

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize-change-visual-type.png" alt-text="Visualisointityypin vaihtaminen":::
 
### <a name="swap-out-a-measure-or-dimension"></a>Mittayksikön tai dimension vaihtaminen
Korvaa X-akselille käytettävä kenttä valitsemalla korvattava kenttä ja valitsemalla sitten toinen kenttä.

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize-change-axis.png" alt-text="Akselin muuttaminen":::
 
### <a name="add-or-remove-a-legend"></a>Selitteen lisääminen tai poistaminen
Lisäämällä selitteen voit värikoodata visualisoinnin luokan mukaan. Tässä esimerkissä värikoodaus tehdään yrityksen nimen perusteella. 

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize-change-legend.png" alt-text="Selitteen lisääminen tai poistaminen":::

### <a name="compare-two-or-more-different-measures"></a>Kahden tai useamman eri mittarin vertaileminen
Voit verrata eri mittareiden arvoja lisäämällä visualisointiin useita mittareita käyttämällä +-kuvaketta. Jos haluat poistaa mittarin arvon, valitse **Lisää asetuksia (...)** ja valitse **Poista kenttä**.

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize-compare-measures.png" alt-text="Mittareiden vertaaminen":::

### <a name="change-aggregations"></a>Koosteiden muuttaminen
Voit muuttaa mittareiden laskemistapaa muuttamalla koostetta **Mukauta**-ruudussa. Valitse **Lisää asetuksia (...)** ja valitse käytettävä kooste.

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize-change-aggregation.png" alt-text="Koosteiden muuttaminen":::

### <a name="capture-changes"></a>Muutosten sieppaaminen 
Voit siepata tekemäsi muutokset ja palata mukautettuun näkymään käyttämällä kirjanmerkkejä. Valitse **Kirjanmerkit** > **Omat kirjanmerkit** ja anna kirjanmerkille nimi. 

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize-bookmark.png" alt-text="Kirjanmerkin luominen":::
 
Voit myös tehdä kirjanmerkistä oletusnäkymän.

### <a name="share-changes"></a>Muutosten jakaminen 
Jos sinulla on luku- ja uudelleenjako-oikeudet, voit raporttia jakaessasi päättää, sisältääkö jako tekemäsi muutokset.

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize-share-changes.png" alt-text="Muutosten jakaminen":::
 
### <a name="reset-all-your-changes-to-a-report"></a>Kaikkien raporttiin tekemiesi muutosten palauttaminen

Valitse raporttipohjan oikeasta yläkulmasta **Palauta oletusasetukset**. Tämä poistaa kaikki raporttiin tekemäsi muutokset ja määrittää sen takaisin tekijän viimeiseen tallennettuun näkymään.

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize-reset-all.png" alt-text="Kaikkien muutosten palauttaminen":::
 
### <a name="reset-all-your-changes-to-a-visual"></a>Kaikkien visualisointiin tekemiesi muutosten palauttaminen

Valitse visualisoinnin valikkoriviltä **Palauta tämä visualisointi**, jos haluat poistaa kaikki tiettyyn visualisointiin tekemäsi muutokset ja määrittää sen takaisin visualisoinnin tekijän viimeiseen tallennettuun näkymään.

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize-reset-visual.png" alt-text="Visualisoinnin kaikkien muutosten palauttaminen":::
 
### <a name="clear-recent-changes"></a>Viimeaikaisten muutosten tyhjentäminen

Valitse pyyhinkuvake, jos haluat tyhjentää kaikki viimeaikaiset muutokset, jotka olet tehnyt **Mukauta**-ruudun avaamisen jälkeen.  

:::image type="content" source="media/end-user-personalize-visuals/power-bi-personalize-revert-changes.png" alt-text="Viimeaikaisten muutosten kumoaminen":::

## <a name="limitations-and-known-issues"></a>Rajoitukset ja tunnetut ongelmat

Tällä hetkellä ominaisuudessa on joitakin rajoituksia, jotka on otettava huomioon.

- **Mukauta tätä visualisointia** voidaan poistaa käytöstä koko raportissa tai tietyssä visualisoinnissa. Jos vaihtoehto visualisoinnin muokkaamiseen ei ole näkyvissä, kysy asiasta vuokraajan järjestelmänvalvojalta tai raportin omistajalta. Jos haluat näyttää raportin omistajan yhteystiedot, valitse raportin nimi Power BI:n valikkoriviltä.
- Käyttäjän tutkimukset eivät säily automaattisesti. Näkymä täytyy tallentaa henkilökohtaiseksi kirjanmerkiksi, jotta muutokset säilyvät.
- Visualisointeja ei voi muuttaa Power BI -mobiilisovelluksissa. Kaikkia Power BI -palvelussa henkilökohtaiseen kirjanmerkkiin tallennettuja visualisoinnin muutoksia noudatetaan kuitenkin myös mobiilisovelluksissa.

On myös joitakin tunnettuja ongelmia, joita käsitellään:

- Hierarkian lisäämistä ei tueta; sinun on lisättävä kukin erillinen alielementtikohde.
- Henkilökohtaisissa kirjanmerkeissä tulokset saattavat erota hieman valitsemasi jakson mukaan. Ristiriidat ovat mahdollisia, koska emme sieppaa raportin koko tilaa, vaan ainoastaan tehdyt muutokset. Voit kiertää ongelman valitsemalla ensin **Palauta oletusasetukset** ja sitten tarkasteltavan kirjanmerkin. 

## <a name="next-steps"></a>Seuraavat vaiheet
[Raportin visualisoinnin kopioiminen staattisena kuvana](../visuals/power-bi-visualization-copy-paste.md)    
Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

