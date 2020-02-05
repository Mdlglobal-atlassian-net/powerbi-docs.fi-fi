---
title: Raporttisivun porautumisen käyttäminen
description: Ohjeet raporttisivun porautumisen käyttämiseen.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2019
ms.author: v-pemyer
ms.openlocfilehash: 48942b30b84706c933ccef455129c84a67ac5a1b
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/04/2020
ms.locfileid: "76040372"
---
# <a name="use-report-page-drillthrough"></a>Raporttisivun porautumisen käyttäminen

Tämä artikkeli koskee raportin laatijaa, joka suunnittelee Power BI -raportteja. Siinä annetaan ehdotuksia ja suosituksia luotaessa [raporttisivun porautumista](../desktop-drillthrough.md).

On suositeltavaa, että suunnittelet raporttisi niin, että raportin käyttäjät voivat noudattaa seuraavaa työnkulkua:

1. Raporttisivun tarkasteleminen.
2. Sellaisten visualisointielementtien tunnistaminen, joita halutaan analysoida syvemmin.
3. Visualisointielementtiin porautuminen napsauttamalla sitä hiiren kakkospainikkeella.
4. Ilmaisen analyysin suorittaminen.
5. Palaaminen lähderaporttisivulle.

## <a name="suggestions"></a>Ehdotukset

Suosittelemme, että tarkastelet kahta porautumistilannetta:

- [Lisäsyvyys](#additional-depth)
- [Laajempi perspektiivi](#broader-perspective)

### <a name="additional-depth"></a>Lisäsyvyys

Kun raporttisivusi näyttää yhteenvedon tulokset, porautumissivu voi johtaa raportin käyttäjiä tapahtumatason tietoihin. Tämän suunnittelumenetelmän ansiosta he voivat (vain tarvittaessa) tarkastella tukevia tapahtumia.

Seuraavassa esimerkissä näytetään, mitä tapahtuu, kun raportin käyttäjä porautuu myynnin kuukausittaisen yhteenvedon kautta. Porautumissivu sisältää yksityiskohtaisen luettelon tietyn kuukauden tilauksista.

![Matriisivisualisointi otsikolla Myynnin yhteenveto ryhmittelee myynnin riveille vuoden ja kuukauden mukaan sekä sarakkeisiin maan mukaan. Myös porautumissivu näytetään.](media/report-drillthrough/suggestion-drillthrough-add-depth.png)

### <a name="broader-perspective"></a>Laajempi perspektiivi

Porautumissivua voidaan käyttää lisäsyvyyden vastakohtana. Tämä skenaario soveltuu erinomaisesti porautumiseen kokonaisvaltaiseen näkymään.

Seuraavassa esimerkissä näytetään, mitä tapahtuu, kun raportin käyttäjä porautuu postinumeron kautta. Porautumissivu näyttää postinumeron yleiset tiedot.

![Taulukon visualisoinnissa on kolme saraketta: postinumero, virhepisteen keskiarvo ja luokituksen keskiarvo. Myös porautumissivu näytetään.](media/report-drillthrough/suggestion-drillthrough-broader-perspective.png)

## <a name="recommendations"></a>Suositukset

Raportin suunnittelun aikana suosittelemme seuraavia käytäntöjä:

- **Tyyli:** Harkitse käyttäväsi porautumissivussa samaa teemaa ja tyyliä kuin raportissa. Tällä tavalla käyttäjät tuntevat olevansa samassa raportissa.
- **Porautumissuodattimet:** Valitse porautumiseen käytettävät suodattimet, jotta voit esikatsella realistista tulosta, kun suunnittelet porautumissivua. Varmista, että poistat nämä suodattimet ennen raportin julkaisemista.
- **Muut ominaisuudet:** Porautumissivu on kuin mikä tahansa raporttisivu. Voit myös parantaa sitä vuorovaikutteisten toimintojen avulla, mukaan lukien sektorit tai suodattimet.
- **Tyhjät:** Vältä lisäämästä visualisointeja, jotka voivat palauttaa tyhjän tai aiheuttaa virheitä, kun porautumissuodattimia otetaan käyttöön.
- **Sivun näkyvyys:** Harkitse porautumissivujen piilottamista. Jos päätät pitää porautumissivun näkyvissä, lisää painike, jonka avulla käyttäjät voivat tyhjentää mahdolliset aiemmin määritetyt porautumissuodattimet. Määritä painikkeeseen [kirjanmerkki](../desktop-bookmarks.md). Kirjanmerkki tulee määrittää poistamaan kaikki suodattimet.
- **Takaisin-painike:** Takaisin[-painike](../desktop-buttons.md) lisätään automaattisesti, kun määrität porautumissuodattimen. Se kannattaa säilyttää. Näin raporttisi käyttäjät voivat helposti palata lähdesivulle.
- **Löydettävyys:** Voit edistää porautumissivun tunnettuutta asettamalla visualisoinnin otsikolle kuvaketekstin tai lisäämällä ohjeita tekstiruutuun. Voit myös suunnitella peittokuvan, joka on kuvattu [tässä blogikirjoituksessa](https://alluringbi.com/2019/10/23/overlays-for-true-self-serve-reporting/).

> [!TIP]
> Voit myös määrittää porautumisen sivutettuihin Power BI -raportteihin. Voit tehdä tämän lisäämällä linkkejä Power BI -raportteihin. Linkit voivat määrittää [URL-parametreja](https://powerbi.microsoft.com/blog/url-parameters-for-paginated-reports-are-now-available/).

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Porautumisen käyttäminen Power BI Desktopissa](../desktop-drillthrough.md)
- Guy in a Cuben video: [Porautumiseen porautuminen Power BI Desktopissa](https://www.youtube.com/watch?v=2x9lLHDbtDk)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
