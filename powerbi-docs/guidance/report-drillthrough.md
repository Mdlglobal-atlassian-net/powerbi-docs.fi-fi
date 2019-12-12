---
title: Raporttisivun porautuminen
description: Ohjeet raporttisivun porauksen käyttämiseen.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2019
ms.author: v-pemyer
ms.openlocfilehash: b674c621c30491a00c529af7f2fcd9eb87f3ecfa
ms.sourcegitcommit: e492895259aa39960063f9b337a144a60c20125a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/05/2019
ms.locfileid: "74834766"
---
# <a name="report-page-drillthrough"></a>Raporttisivun porautuminen

Tämä artikkeli koskee raportin laatijaa, joka suunnittelee Power BI -raportteja. Siinä annetaan ehdotuksia ja suosituksia luotaessa [raporttisivun porautumista](../desktop-drillthrough.md).

On suositeltavaa, että suunnittelet raporttisi niin, että raportin käyttäjät voivat saavuttaa seuraavan työnkulun:

1. Tarkastele raporttisivua.
2. Tunnista visualisointielementit, joita analysoidaan syvemmin.
3. Napsauta hiiren kakkospainikkeella porautumisen siirtymisosaa.
4. Suorita ilmainen analyysi.
5. Palaa lähderaporttisivulle.

## <a name="suggestions"></a>Ehdotukset

Suosittelemme, että tarkastelet kahta porautumistilannetta:

- [Lisäsyvyys](#additional-depth)
- [Laajempi perspektiivi](#broader-perspective)

### <a name="additional-depth"></a>Lisäsyvyys

Kun raporttisivusi näyttää yhteenvedon tulokset, porautumissivu voi johtaa raportin käyttäjiä tapahtumatason tietoihin. Tämän suunnittelumenetelmän avulla he voivat tarkastella tukitapahtumia ja vain tarvittaessa.

Seuraavassa esimerkissä näytetään, mitä tapahtuu, kun raportin käyttäjä porautuu kuukausittaisen myyntiyhteenvedon kautta. Porautuva sivu sisältää yksityiskohtaisen luettelon tietyn kuukauden tilauksista.

![Matriisi visualisointi otsikolla Myynnin yhteenveto" ryhmittelee myynnit vuoden ja kuukauden mukaan riveille ja maasarakkeisiin. Myös poraussivu näytetään.](media/report-drillthrough/suggestion-drillthrough-add-depth.png)

### <a name="broader-perspective"></a>Laajempi perspektiivi

Porautuva sivu voi saavuttaa lisäsyvyyden vastakohdan. Tämä skenaario soveltuu erinomaisesti porautumiseen kokonaisvaltaiseen näkymään.

Seuraavassa esimerkissä näytetään, mitä tapahtuu, kun raportin käyttäjä porautuu postinumeron kautta. Porautuva sivu näyttää postinumeron yleiset tiedot.

![Taulukon visualisoinnissa on kolme saraketta: postinumero, virhepisteen keskiarvo ja luokituksen keskiarvo. Myös poraussivu näytetään.](media/report-drillthrough/suggestion-drillthrough-broader-perspective.png)

## <a name="recommendations"></a>Suositukset

Raportin suunnittelun aikana suosittelemme seuraavia käytäntöjä:

- **Tyyli:** Harkitse käyttäväsi poraussivussasi samaa teemaa ja tyyliä kuin raportissa. Tällä tavalla käyttäjät tuntevat olevansa samassa raportissa.
- **Porautumissuodattimet:** Valitse porautumiseen käytettävät suodattimet, jotta voit esikatsella realistista tulosta, kun suunnittelet porautumissivua. Varmista, että poistat nämä suodattimet ennen raportin julkaisemista.
- **Muut ominaisuudet:** Porautuva sivu on kuin mikä tahansa raporttisivu. Voit myös parantaa sitä vuorovaikutteisten toimintojen avulla, mukaan lukien sektorit tai suodattimet.
- **Tyhjät:** Vältä lisäämästä visualisointeja, jotka voivat näyttää tyhjää, tai aiheuttamasta virheitä, kun porautuvia suodattimia otetaan käyttöön.
- **Sivun näkyvyys:** Harkitse porautumissivujen piilottamista. Jos päätät pitää porautuvan sivun näkyvissä, lisää painike, jonka avulla käyttäjät voivat tyhjentää aiemmin määritetyt porautumissuodattimet. Määritä painikkeeseen [kirjanmerkki](../desktop-bookmarks.md). Kirjanmerkki tulee määrittää poistamaan kaikki suodattimet.
- **Takaisin-painike:** Takaisin[-painike](../desktop-buttons.md) lisätään automaattisesti, kun määrität porautuvan suodattimen. Se kannattaa säilyttää. Näin raporttisi käyttäjät voivat helposti palata lähdesivulle.
- **Discovery:** Voit edistää porautumissivun tunnettuutta asettamalla visuaalisen otsikon kuvaketekstin tai lisäämällä ohjeita tekstiruutuun. Voit myös suunnitella peittokuvan, joka on kuvattu [tässä blogikirjoituksessa](https://alluringbi.com/2019/10/23/overlays-for-true-self-serve-reporting/).

> [!TIP]
> Voit myös määrittää porautumiseen Power BI -sivutettuihin raportteihisi. Voit tehdä tämän lisäämällä linkkejä Power BI -raportteihin. Linkit voivat määrittää [URL-parametreja](/blog/url-parameters-for-paginated-reports-are-now-available/).

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Porautumisen käyttäminen Power BI Desktopissa](../desktop-drillthrough.md)
- Kaveri kuutiossa -video: [Porautumiseen porautuminen Power BI Desktopissa](https://www.youtube.com/watch?v=2x9lLHDbtDk)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
