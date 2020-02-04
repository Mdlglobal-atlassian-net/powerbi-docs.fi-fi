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
ms.openlocfilehash: 826af7b224b901b6dc9f3926260b1d920836a792
ms.sourcegitcommit: 0ae9328e7b35799d5d9613a6d79d2f86f53d9ab0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/16/2020
ms.locfileid: "76040345"
---
# <a name="extend-visuals-with-report-page-tooltips"></a>Visualisointien laajentaminen raporttisivun työkaluvihjeiden avulla

Tämä artikkeli koskee raportin laatijaa, joka suunnittelee Power BI -raportteja. Siinä annetaan ehdotuksia ja suosituksia luotaessa [raporttisivun työkaluvihjeitä](../desktop-tooltips.md).

## <a name="suggestions"></a>Ehdotukset

Raporttisivun työkaluvihjeet voivat parantaa raporttikäyttäjiesi käyttökokemusta. Sivun työkaluvihjeiden avulla raporttisi käyttäjät voivat nopeasti ja tehokkaasti saada syvällisempää tietoa visualisoinnista. Ne voidaan liittää erilaisiin raporttiobjekteihin:

- **Visualisoinnit:** Visualisoinnin perusteella voit määrittää, mitkä visualisoinnit paljastavat sivusi työkaluvihjeen. Visualisoinnissa voi visualisointikohtaisesti näyttää ei työkaluvihjeitä, oletusarvoja visualisoinnin työkaluvihjeissä (määritetty visualisoinnin kentät-ruudussa) tai käyttää tiettyä sivun työkaluvihjettä.
- **Visualisointiotsikot:** Voit määrittää tietyt visualisoinnit näyttämään sivun työkaluvihjeen. Raporttisi käyttäjä pääsee näkemään sivun työkaluvihjeen, kun hän vie kohdistimen visuaalisen otsikon kuvakkeen päälle – muista kouluttaa käyttäjiäsi tästä kuvakkeesta.

> [!NOTE]
> Raportin visualisointi voi näyttää sivun työkaluvihjeen vain, kun työkaluvihjeen sivun suodattimet ovat yhteensopivia visualisoinnin rakenteen kanssa. Esimerkiksi visualisointi, jonka _tuote_ ryhmittelee, on yhteensopiva työkaluvihjeen sivun kanssa, joka suodattaa _tuotteittain_.
>
> Sivun työkaluvihjeet eivät tue vuorovaikutteisuutta. Jos haluat, että raporttisi käyttäjät voivat toimia vuorovaikutuksessa, luo [porautuva sivu](../desktop-drillthrough.md) sen sijaan.
>
> Mukautetut visualisoinnit eivät tue sivun työkaluvihjeitä.

Seuraavassa on joitakin ehdotettuja suunnittelutilanteita:

- [Eri perspektiivi](#different-perspective)
- [Lisää tiedot](#add-detail)
- [Lisää ohje](#add-help)

### <a name="different-perspective"></a>Eri perspektiivi

Sivun työkaluvihje voi visualisoida samat tiedot kuin lähteen visualisointi. Se tehdään käyttämällä samoja visualisointi- ja pivot-ryhmätyyppejä tai käyttämällä eri visualisointityyppejä. Sivun työkaluvihjeet voivat myös käyttää eri suodattimia kuin lähdevisualisoinnissa käytetyt suodattimet.

Seuraavassa esimerkissä näytetään, mitä tapahtuu, kun raportin käyttäjä siirtää kohdistimen **EnabledUsers**-arvon kohdalle. Arvon suodatinkonteksti on Yammer marraskuussa 2018.

![Matriisin visualisointi näyttää rivien vuoden ja kuukauden mukaan ryhmiteltyjen arvojen ruudukon. Raportin käyttäjä on pitänyt kohdistimen yksittäisen arvon päällä. Sivun työkalunvihje on tullut esiin.](media/report-page-tooltips/suggestion-different-perspective.png)

Sivun työkaluvihje on näkyvissä. Se esittelee erilaisen tietojen visualisoinnin (viivan ja klusteroidun pylväskaavion) ja ottaa käyttöön vastakkaisen ajan suodatuksen. Huomaa, että arvopisteen suodatinkonteksti on marraskuu 2018. Kuitenkin sivun työkaluvihje näyttää trendin _koko vuoden kuukausista_.

### <a name="add-detail"></a>Lisää tiedot

Sivun työkaluvihje voi näyttää lisätietoja ja lisätä kontekstin.

Seuraavassa esimerkissä näytetään, mitä tapahtuu, kun raportin käyttäjä siirtää kohdistimen **EnabledUsers**-arvon kohdalle, pistonumeron ollessa 98022.

![Taulukkovisualisointi näyttää arvoruudukon, ja taulukko sisältää kolme saraketta. Sivun työkalunvihje on tullut esiin.](media/report-page-tooltips/suggestion-add-details.png)

Sivun työkaluvihje on näkyvissä. Se esittelee postinumeron 98022 tiettyjä määritteitä ja tilastoja.

### <a name="add-help"></a>Lisää ohje

Visuaaliset otsikot voidaan määrittää näyttämään sivun työkaluvihjeet visuaalisiin otsikoihin. Voit lisätä ohjeeseen sisältöä sivun työkaluvihjeessä käyttämällä monipuolisesti muotoiltuja tekstiruutuja. Kuvia ja muotoja voi myös lisätä.

Kiinnostavaa kyllä, painikkeet, kuvat, teksti ruudut ja muodot voivat myös paljastaa visuaalisen otsikkosivun työkaluvihjeen.

Seuraavassa esimerkissä näytetään, mitä tapahtuu, kun raportin käyttäjä siirtää kohdistimen [visualisointiotsikon](../desktop-visual-elements-for-reports.md) kohdalle.

![Raportin käyttäjä on pitänyt osoittimen visualisointiotsikon kuvakkeen (kysymysmerkkikuvake) päällä. Esiin on tullut runsaasti muotoiltu työkaluvihje.](media/report-page-tooltips/suggestion-add-help.png)

Sivun työkaluvihje on näkyvissä. Se näyttää RTF-muotoista tekstiä neljässä tekstiruudussa ja muodon (viivan). Sivun työkaluvihje välittää ohjeet kuvailemalla kutakin visualisoinnissa näkyvää lyhennettä.

## <a name="recommendations"></a>Suositukset

Raportin suunnittelun aikana suosittelemme seuraavia käytäntöjä:

- **Sivun koko:** Määritä sivusi työkaluvihje pieneksi. Voit käyttää sisäänrakennettua **Tooltip-** asetusta (320 kuvapistettä leveää 240 kuvapistettä korkeaa). Voit myös valita mukautetut mitat. Varo, että et käytä liian suurta sivukokoa, sillä se voi peittää lähdesivun visualisoinnit.
- **Sivunäkymä:** Aseta raportin suunnitteluohjelmassa sivunäkymä **todelliseen kokoon** (sivunäkymän oletusarvo on **Sovita sivulle**). Näin voit tarkastella sivun työkaluvihjeen todellista kokoa, kun suunnittelet sitä.
- **Tyyli:** Harkitse käyttäväsi poraussivussasi samaa teemaa ja tyyliä kuin raportissa. Tällä tavalla käyttäjät tuntevat olevansa samassa raportissa. Voit myös suunnitella työkaluvihjeille ilmaisen tyylin ja käyttää tätä tyyliä kaikissa sivun työkaluvihjeissä.
- **Työkaluvihjekentät:** Määritä suodattimia sivun työkaluvihjeelle, jotta voit esikatsella realistista tulosta, kun suunnittelet sitä. Varmista, että poistat nämä suodattimet ennen raportin julkaisemista.
- **Sivun näkyvyys:** Piilota työkaluvihjesivut aina – käyttäjät eivät saa siirtyä niihin suoraan.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Power BI Desktopissa luotuihin raporttisivuihin perustuvien työkaluvihjeiden luominen](../desktop-tooltips.md)
- [Työkaluvihjeiden mukautus Power BI Desktopissa](../desktop-custom-tooltips.md)
- [Power BI -raporttien parantaminen visuaalisia elementtejä käyttämällä](../desktop-visual-elements-for-reports.md)
- Kaveri kuutiossa -video: [Power BI -raporttisivun työkaluvihje – näin voit luoda sellaisen Power BI Desktopissa](https://www.youtube.com/watch?v=URTA7JZsAtw)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
