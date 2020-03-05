---
title: Visualisointien laajentaminen raporttisivun työkaluvihjeiden avulla
description: Ohjeet raporttisivun työkaluvihjeiden käyttämiseen.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/24/2019
ms.author: v-pemyer
ms.openlocfilehash: f86317b12e3637d6522eebc2f304786c1b39c083
ms.sourcegitcommit: b59ec11a4a0a3d5be2e4d91548d637d31b3491f8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/05/2020
ms.locfileid: "78290609"
---
# <a name="extend-visuals-with-report-page-tooltips"></a>Visualisointien laajentaminen raporttisivun työkaluvihjeiden avulla

Tämä artikkeli koskee raportin laatijaa, joka suunnittelee Power BI -raportteja. Siinä annetaan ehdotuksia ja suosituksia luotaessa [raporttisivun työkaluvihjeitä](../desktop-tooltips.md).

## <a name="suggestions"></a>Ehdotukset

Raporttisivun työkaluvihjeet voivat parantaa raporttikäyttäjiesi käyttökokemusta. Sivun työkaluvihjeiden avulla raporttisi käyttäjät voivat nopeasti ja tehokkaasti saada syvällisempää tietoa visualisoinnista. Ne voidaan liittää erilaisiin raporttiobjekteihin:

- **Visualisoinnit:** Voit määrittää visualisointikohtaisesti, mitkä niistä paljastavat sivun työkaluvihjeen. Voit visualisointikohtaisesti valita, näyttääkö se työkaluvihjeitä lainkaan, oletusarvoja visualisoinnin työkaluvihjeissä (määritetty visualisoinnin kentät-ruudussa) tai tietyn työkaluvihjeen.
- **Visualisointiotsikot:** Voit määrittää tietyt visualisoinnit näyttämään sivun työkaluvihjeen. Raporttisi käyttäjät voivat näyttää sivun työkaluvihjeen viemällä osoittimen visualisoinnin otsikon kuvakkeen päälle – muista mainita käyttäjille tästä kuvakkeesta.

> [!NOTE]
> Raportin visualisointi voi näyttää sivun työkaluvihjeen vain, kun työkaluvihjeen sivun suodattimet ovat yhteensopivia visualisoinnin rakenteen kanssa. Esimerkiksi visualisointi, joka ryhmittelee eri _tuotteita_, on yhteensopiva vain työkaluvihjeen sivun kanssa, joka suodattaa _tuotteittain_.
>
> Sivun työkaluvihjeet eivät tue vuorovaikutteisuutta. Jos haluat, että raporttisi käyttäjät voivat toimia vuorovaikutuksessa, luo [porautumissivu](../desktop-drillthrough.md) työkaluvihjeen sijaan.
>
> Mukautetut visualisoinnit eivät tue sivun työkaluvihjeitä.

Seuraavassa on joitakin ehdotettuja suunnittelutilanteita:

- [Eri perspektiivi](#different-perspective)
- [Lisätietoja](#add-detail)
- [Lisäohjeita](#add-help)

### <a name="different-perspective"></a>Eri perspektiivi

Sivun työkaluvihje voi visualisoida samat tiedot kuin lähteen visualisointi. Tämä tehdään käyttämällä samoja visualisoinnin ja pivotoinnin ryhmiä tai käyttämällä eri visualisointityyppejä. Sivun työkaluvihjeet voivat myös käyttää eri suodattimia kuin lähdevisualisoinnissa käytetyt suodattimet.

Seuraavassa esimerkissä näytetään, mitä tapahtuu, kun raportin käyttäjä siirtää osoittimen **EnabledUsers**-arvon kohdalle. Arvon suodatinkonteksti on Yammer marraskuussa 2018.

![Matriisin visualisointi näyttää rivien vuoden ja kuukauden mukaan ryhmiteltyjen arvojen ruudukon. Raportin käyttäjä on pitänyt osoittimen yksittäisen arvon päällä. Sivun työkalunvihje on tullut esiin.](media/report-page-tooltips/suggestion-different-perspective.png)

Sivun työkaluvihje on näkyvissä. Se esittelee erilaisen tietojen visualisoinnin (viivakaavion ja yhdistelmäpylväskaavion) ja ottaa käyttöön vastakkaisen ajan suodatuksen. Huomaa, että arvopisteen suodatinkonteksti on marraskuu 2018. Kuitenkin sivun työkaluvihje näyttää trendin _koko vuoden kuukausista_.

### <a name="add-detail"></a>Lisätietoja

Sivun työkaluvihje voi näyttää lisätietoja ja selventää asiayhteyttä.

Seuraavassa esimerkissä näytetään, mitä tapahtuu, kun raportin käyttäjä siirtää osoittimen postinumeron 98022 **Average of Violation Points** -arvon kohdalle.

![Taulukkovisualisointi näyttää arvoruudukon, ja taulukko sisältää kolme saraketta. Sivun työkalunvihje on tullut esiin.](media/report-page-tooltips/suggestion-add-details.png)

Sivun työkaluvihje on näkyvissä. Se esittelee postinumeron 98022 tiettyjä määritteitä ja tilastoja.

### <a name="add-help"></a>Lisäohjeita

Visualisoinnin otsikot voidaan määrittää näyttämään sivun työkaluvihjeet. Voit lisätä ohjeeseen sisältöä sivun työkaluvihjeessä käyttämällä monipuolisesti muotoiltuja tekstiruutuja. Kuvia ja muotoja voi myös lisätä.

Kiinnostavaa kyllä, painikkeet, kuvat, tekstiruudut ja muodot voivat myös paljastaa visualisoinnin otsikon sivun työkaluvihjeen.

Seuraavassa esimerkissä näytetään, mitä tapahtuu, kun raportin käyttäjä siirtää kohdistimen [visualisointiotsikon](../desktop-visual-elements-for-reports.md) kohdalle.

![Raportin käyttäjä on pitänyt osoittimen visualisoinnin otsikon kuvakkeen (kysymysmerkkikuvake) päällä. Esiin on tullut RTF-muotoiltu työkaluvihje.](media/report-page-tooltips/suggestion-add-help.png)

Sivun työkaluvihje tulee näkyviin. Se näyttää RTF-muotoista tekstiä neljässä tekstiruudussa ja muodon (viivan). Sivun työkaluvihje välittää ohjeet kuvailemalla kutakin visualisoinnissa näkyvää lyhennettä.

## <a name="recommendations"></a>Suositukset

Raportin suunnittelun aikana suosittelemme seuraavia käytäntöjä:

- **Sivun koko:** Määritä sivusi työkaluvihje pieneksi. Voit käyttää sisäänrakennettua **Työkaluvihje**-asetusta (320 kuvapistettä leveä, 240 kuvapistettä korkea). Voit myös valita mukautetut mitat. Varo käyttämästä liian suurta sivukokoa, sillä se voi peittää lähdesivun visualisoinnit.
- **Sivunäkymä:** Aseta raportin suunnitteluohjelmassa sivunäkymä **todelliseen kokoon** (sivunäkymän oletusarvo on **Sovita sivulle**). Näin voit tarkastella sivun työkaluvihjeen todellista kokoa, kun suunnittelet sitä.
- **Tyyli:** Harkitse käyttäväsi porautumissivussa samaa teemaa ja tyyliä kuin raportissa. Tällä tavalla käyttäjät tuntevat olevansa samassa raportissa. Voit myös suunnitella työkaluvihjeille ilmaisen tyylin ja käyttää tätä tyyliä kaikissa sivun työkaluvihjeissä.
- **Työkaluvihjesuodattimet:** Määritä suodattimia sivun työkaluvihjeelle, jotta voit esikatsella realistista tulosta, kun suunnittelet sitä. Varmista, että poistat nämä suodattimet ennen raportin julkaisemista.
- **Sivun näkyvyys:** Piilota työkaluvihjesivut aina – käyttäjien ei tule päästä niihin suoraan.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Power BI Desktopissa luotuihin raporttisivuihin perustuvien työkaluvihjeiden luominen](../desktop-tooltips.md)
- [Työkaluvihjeiden mukautus Power BI Desktopissa](../desktop-custom-tooltips.md)
- [Power BI -raporttien parantaminen visuaalisia elementtejä käyttämällä](../desktop-visual-elements-for-reports.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
