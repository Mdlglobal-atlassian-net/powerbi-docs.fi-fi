---
title: Suhteellisen aikaosittajan tai -suodattimen käyttö Power BI:ssä
description: Opi miten osittajaa tai suodatinta käytetään rajoittamaan suhteellisia aikavälijoukkoja Power BI:ssä.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/22/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 31563e5bb5b91468b8913c3204e9d27607716c77
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279200"
---
# <a name="use-a-relative-time-slicer-and-filter-in-power-bi"></a>Suhteellisen aikaosittajan ja -suodattimen käyttö Power BI:ssä

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Nopean päivityksen tilanteissa mahdollisuudesta suodattaa lyhyempi ajanjakso voi olla hyötyä. Suhteellisen aikaosittajan tai suhteellisen aikasuodattimen avulla voit käyttää aikasidonnaisia suodattimia missä tahansa tietomallisi päivämäärä- tai aikasarakkeessa. Suhteellisen aikaosittajan avulla voit esimerkiksi näyttää vain videon katselukerrat edelliseltä minuutilta tai tunnilta. 

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time.gif" alt-text="Suhteellisen ajan esimerkki":::

Ominaisuutta ei tarvitse käyttää yhdessä [automaattisen sivun päivitysominaisuuden](../create-reports/desktop-automatic-page-refresh.md) kanssa. Kuitenkin monet suhteelliset aikatapaukset sopivat hyvin yhteen automaattisen sivun päivitysominaisuuden kanssa.  

> [!NOTE]
> Kun otat suhteellisen aikasuodattimen tai -osittajan käyttöön sivun tai raportin tasolla, kaikki kyseisen sivun tai raportin visualisoinnit suodatetaan samalla aikavälillä ja niissä käytetään jaettua *ankkuriaikaa*. Koska visualisointien suoritusajat saattavat olla hieman erilaiset, tämä jaettu ankkuriaika varmistaa, että visualisoinnit synkronoidaan koko sivulla tai raportissa. Tässä artikkelissa on lisätietoja [ankkuriajasta](#understanding-anchor-time).

## <a name="turn-on-relative-time-preview"></a>Ota suhteellisen ajan esikatselu käyttöön

Suhteellisen ajan suodatin on esikatselussa, joten sinun on otettava käyttöön ominaisuusvalitsin. Valitse **Tiedosto** > **Asetukset ja vaihtoehdot** > **Asetukset**. Varmista kohdassa **Yleiset asetukset** > **Esikatselutoiminnot**, että **Suhteellinen aikasuodatin** on valittuna.

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-set-preview.png" alt-text="Suhteellisen ajan esikatseluvaihtoehdon asettaminen":::

## <a name="create-a-relative-time-slicer-or-filter"></a>Suhteellisen aikaosittajan tai -suodattimen luominen

Kun olet ottanut ominaisuuden käyttöön, voit vetää ja pudottaa päivämäärä- tai aikakentän osittajan kenttään tai pudotusalueelle Suodattimet-ruudussa. 

### <a name="create-a-slicer"></a>Osittajan luominen

1. Vedä päivämäärä- tai aikakenttä pohjaan.

2. Valitse visualisointityypiksi **Osittaja**.

    :::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-create-slicer.png" alt-text="Aikaosittajan luominen":::

### <a name="create-a-filter"></a>Suodattimen luominen
 
- Vedä päivämäärä- tai aikakenttä Suodattimet-ruutuun **tätä visualisointia**, **tätä sivua** tai **kaikkia sivuja** varten.

### <a name="set-relative-time"></a>Suhteellisen ajan asettaminen 

Vaihda seuraavaksi suodattimen tyypiksi **Suhteellinen aika**.

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-set.png" alt-text="Suhteelliseen aikaan vaihtaminen":::
 
Tältä se näyttää osittajassa:

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-slicer.png" alt-text="Suhteellinen aika osittajassa":::

Tältä se näyttää suodatinkortissa: 

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-filter.png" alt-text="Suhteellinen aika suodattimessa":::
 
Tämän uuden suodatintyypin ansiosta voit käyttää suodatinperustetta **Viimeinen**, **Seuraava** tai **Tämä ajanjakso**: 

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-last-next.png" alt-text="Valitse Viimeinen, Seuraava tai Tämä ajanjakso":::
 
Voit määrittää aikaikkunan käyttämällä kokonaislukua ja ajan yksikköä: **Minuutit** tai **Tunnit**.
 
:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-minutes-hours.png" alt-text="Valitse minuutit tai tunnit":::

Jos haluat säästää tilaa pohjassa, voit myös luoda suhteellisen aikasuodattimen suodatinkorttina Suodattimet-ruudussa.

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-set-filter.png" alt-text="Suhteellisen ajan asettaminen suodattimessa sen sijaan":::
 
## <a name="understanding-anchor-time"></a>Perustietoja ankkuriajasta

Kun suodatinta käytetään sivun tai raportin tasolla, kaikki kyseisen sivun tai raportin visualisoinnit synkronoidaan samalle aikavälille. Nämä kyselyt esitetään kaikki suhteessa aikaan, jota kutsutaan *ankkuriajaksi*. Ankkuriaika päivittyy automaattisesti seuraavien ehtojen mukaisesti:

- Sivun alkuperäinen lataus.
- Manuaalinen päivitys.
- Automaattinen tai muutoksen havaitsemisen sivupäivitys.
- Mallin muutos.

### <a name="anchor-time-exceptions"></a>Ankkuriajan poikkeukset

- Suhteellinen aikasuodatus käyttäen Q&A-visualisointia ei ole suhteessa tähän ankkuriaikaan ennen kuin muunnat Q&A-visualisoinnin vakiovisualisointiin. Muut tekoälyvisualisoinnit, kuten keskeiset vaikuttajat ja hajotuspuu, synkronoidaan kuitenkin ankkuriajan kanssa. 
- Lisäksi suhteelliset päivämääräsuodattimet tai -osittajat eivät ole suhteessa ankkuriaikaan, ellei suhteellisia aikasuodattimia ole olemassa. Jos suhteellinen päivämääräsuodatin ja suhteellinen aikasuodatin ovat samalla sivulla, suhteellinen päivämääräsuodatin noudattaa ankkuriaikaa.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Suhteellisen ajan osittajaa ja suodatinta koskevat tällä hetkellä seuraavat rajoitukset ja huomioon otettavat seikat.

- **Aikavyöhykkeeseen huomioitavia seikkoja**: Power BI:n tietomallit eivät sisällä aikavyöhyketietoja. Mallit voivat tallentaa aikoja, mutta niistä ei selviä mistä aikavyöhykkeestä on kyse. Osittaja ja suodatin perustuvat aina UTC-aikaan. Jos siis muokkaat suodatinta raportissa ja lähetät sen toisella aikavyöhykkeellä olevalle kollegalle, näette molemmat saman ajan. Jos sinä tai työtoverisi ette ole UTC-aikavyöhykkeellä, teidän molempien täytyy huomioida aikaero. Voit muuntaa paikallisen aikavyöhykkeen ajan mukaisesti talletetut tiedot UTC-ajaksi kyselyeditorilla.
- Tätä uutta suodatintyyppiä tuetaan Power BI Desktopissa, Power BI -palvelussa, Power BI Embeddedissä ja Power BI -mobiilisovelluksissa. Joitakin tunnettuja tukirajoituksia on kuitenkin olemassa:

    - Sitä ei tueta upotetun ohjelmointirajapinnan kautta.
    - Julkaisemista verkkoon ei tueta.

- **Kyselyn tallentaminen välimuistiin**: Käytämme asiakasvälimuistia. Oletetaan siis, että määrität vaihtoehdot "viimeinen 1 minuutti", sitten "viimeiset 5 minuuttia" ja sitten uudelleen "viimeinen 1 minuutti". Tässä vaiheessa näet samat tulokset kuin ensimmäisellä kerralla, ellet päivitä sivua tai sivu päivittyy automaattisesti.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Suhteellisen päivämääräosittajan ja -suodattimen käyttö Power BI:ssä](../visuals/desktop-slicer-filter-date-range.md)
- [Osittajat Power BI:ssä](../visuals/power-bi-visualization-slicers.md)
