---
title: Power BI -raporttien suodatintyypit
description: Sivu-, visualisointi- tai raporttisuodattimen lisääminen raporttiin Power BI:ssä
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 499a4f3be9f153a1994802e9707f855b71d2a506
ms.sourcegitcommit: 58c649ec5fd2447a0f9ca4c4d45a0e9fff2f1b6a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/27/2019
ms.locfileid: "67409841"
---
# <a name="types-of-filters-in-power-bi-reports"></a>Power BI -raporttien suodatintyypit

Suodattimet eivät toimi kaikki samalla tavalla, koska niitä ei ole luotu samalla tavalla. Niiden luontitapa vaikuttaa siihen, miten ne toimivat uudessa suodatinruudussa muokkaustilassa. Tässä artikkelissa kuvataan erityyppisiä suodattimia: niiden erilaisia luontitapoja ja hyödyllisiä toimintoja. Lue lisää [suodattimien lisäämisestä raportteihin](power-bi-report-add-filter.md). 

![Suodatusruutu](media/power-bi-report-filter-types/power-bi-filter-pane.png)

Aloitetaanpa kahdesta yleisimmästä suodatintyypistä: manuaalisesta ja automaattisesta.

## <a name="manual-filters"></a>Manuaaliset suodattimet 

Manuaaliset suodattimet ovat suodattimia, jotka raportin luojat vetävät ja pudottavat uuden suodatinruudun johonkin kohtaan. Käyttäjät, joilla on oikeus muokata raporttia, voivat muokata, poistaa, tyhjentää, piilottaa, lukita, nimetä uudelleen tai lajitella tämän suodattimen uudessa ruudussa.

## <a name="automatic-filters"></a>Automaattiset suodattimet 

Automaattiset suodattimet ovat suodattimia, jotka lisätään automaattisesti suodatinruudun visualisointitasolle visualisoinnin luonnin yhteydessä. Nämä suodattimet perustuvat kenttiin, jotka muodostavat visualisoinnin. Käyttäjät, joilla on oikeus muokata raporttia, voivat muokata, tyhjentää, piilottaa, lukita, nimetä uudelleen tai lajitella tämän suodattimen uudessa ruudussa. He eivät voi poistaa automaattisia suodattimia, koska visualisointi viittaa näihin kenttiin.

## <a name="more-advanced-filters"></a>Lisäsuodattimet

Nämä seuraavat suodatintyypit ovat harvinaisempia, mutta on kuitenkin tärkeää ymmärtää niitä, jos ne näkyvät raportissa. Niistä voi olla myös hyötyä luomisen aikana, jotta löydät sopivan suodattimen raportille.

## <a name="include-and-exclude-filters"></a>Sisällytä tai jätä pois suodattimet

Sisällytä ja jätä pois suodattimet -toiminto lisätään automaattisesti suodatinruutuun, kun käytät Sisällytä tai jätä pois -toimintoa visualisoinnille. Käyttäjät, joilla on raportin muokkausoikeus, voivat poistaa, lukita, piilottaa tai lajitella tämän suodattimen uudessa ruudussa. He eivät voi muokata, tyhjentää tai nimetä uudelleen sisällytettyä tai pois jätettyä suodatinta, koska se liittyy visualisointien Sisällytä tai jätä pois -toimintoon.

![Jätä pois suodatin](media/power-bi-report-filter-types/power-bi-filters-exclude.png)

## <a name="drill-down-filters"></a>Porautumissuodattimet

Porautumissuodattimet lisätään automaattisesti suodatinruutuun, kun käytät visualisoinnin porautumistoimintoa raportissa. Käyttäjät, joilla on raportin muokkausoikeus, voivat muokata tai tyhjentää suodattimen uudessa ruudussa. He eivät voi poistaa, piilottaa, lukita, nimetä uudelleen tai lajitella tätä suodatinta, koska se liittyy visualisointien porautumistoimintoon. Voit poista porautumissuodattimen napsauttamalla visualisoinnin Poraudu ylöspäin -painiketta.

![Alaspäin porautumisen suodatin](media/power-bi-report-filter-types/power-bi-filters-drill-down.png)

## <a name="cross-drill-filters"></a>Ristiporautumisen suodattimet

Ristiporautumisen suodattimet lisätään automaattisesti uuteen ruutuun, kun alaspäin porautumisen suodatin siirretään toiseen visualisointiin raporttisivulla ristisuodatus- tai ristikorostus-toiminnon kautta. Käyttäjät eivät voi poistaa, tyhjentää, piilottaa, lukita, nimetä uudelleen tai lajitella tätä suodatinta, koska se liittyy visualisointien alaspäin porautumisen toimintoon. He eivät voi myöskään muokata tätä suodatinta, koska se on peräisin alaspäin porautumisesta toisessa visualisoinnissa. Voit poistaa alaspäin porautumisen suodattimen napsauttamalla visualisoinnin, joka siirtää suodattimen, Poraudu ylöspäin -painiketta.

## <a name="drillthrough-filters"></a>Porautumissuodattimet

Porautumissuodattimet siirretään yhdeltä sivulta toiselle porautumisominaisuuden kautta. Ne näkyvät porautumisruudussa. Porautumissuodattimia on kahdentyyppisiä. Ensimmäinen tyyppi kutsuu porautumisen. Raportin muokkaajat voivat muokata, poistaa, tyhjentää, piilottaa tai lukita tämän tyyppisen suodattimen. Toinen tyyppi on porautumissuodatin, joka siirretään kohteeseen lähdesivun sivutason suodattimien mukaan. Raportin muokkaajat voivat muokata, poistaa tai tyhjentää tämän tilapäisen porautumissuodattimen tyypin. He eivät voi lukita tai piilottaa tätä suodatinta loppukäyttäjille.

## <a name="url-filters"></a>URL-suodattimet

URL-suodattimet lisätään uuteen ruutuun lisäämällä URL-osoitteen kyselyparametrin. Käyttäjät, joilla on raportin muokkausoikeus, voivat muokata, poistaa tai tyhjentää suodattimen uudessa ruudussa. He eivät voi piilottaa, lukita, nimetä uudelleen tai lajitella tätä suodatinta, koska se liittyy URL-parametriin. Voit poistaa suodattimen poistamalla parametrin URL-osoitteesta. Tässä on esimerkki URL-osoitteesta, jossa on parametri:

app.powerbi.com/groups/me/apps/*app-id*/reports/*report-id*/ReportSection?filter=Stores~2FStatus%20eq%20'Off'

![URL-suodatin](media/power-bi-report-filter-types/power-bi-filter-url.png)

Lue lisää [URL-suodattimista](service-url-filters.md).

## <a name="pass-through-filters"></a>Läpivientikyselyn suodattimet

Läpivientikyselyn suodattimet ovat Q&A:n kautta luotuja visualisointitason suodattimia. Tekijät voivat poistaa, piilottaa tai lajitella näitä suodattimia uudessa ruudussa. He eivät kuitenkaan voi nimetä uudelleen, muokata, tyhjentää tai lukita näitä suodattimia.

![Läpivientikyselyn suodatin, jossa on Q&A](media/power-bi-report-filter-types/power-bi-filters-qna.png)

## <a name="comparing-filter-types"></a>Suodatintyyppien vertaileminen

Tässä taulukossa vertaillaan sitä, mitä tekijät voit tehdä erityyppisillä suodattimilla.

| Suodatintyyppi | Muokkaa | Tyhjennä | Poista | Piilota | Lukitse | Lajittele | Nimeä uudelleen |
|----|----|----|----|----|----|----|----|
| Manuaaliset suodattimet | Y | Y | Y | Y | Y | Y | Y |
| Automaattinen suodattimet | Y | Y | N | Y | Y | Y | Y |
| Sisällytä / Jätä pois -suodattimet | N | N | Y | Y | Y | Y | N |
| Porautumissuodattimet | Y | Y | N | N | N | N | N |
| Ristiporautumisen suodattimet | N | N | N | N | N | N | N |
| Porautumissuodattimet (kutsuu porautumisen) | Y | Y | Y | Y | Y | N | N |
| Porautumissuodattimet (tilapäiset) | Y | Y | Y | N | N | N | N |
| URL-suodattimet - tilapäiset | Y | Y | Y | N | N | N | N |
| Läpivientikyselyn suodattimet | N | N | Y | Y | N | Y | N |



## <a name="next-steps"></a>Seuraavat vaiheet

[Lisää suodattimet raportteihin](power-bi-report-add-filter.md)

[Aloita raportin Suodattimet-ruudun esittely](consumer/end-user-report-filter.md)

[Suodattimet ja korostaminen raporteissa](power-bi-reports-filters-and-highlighting.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

