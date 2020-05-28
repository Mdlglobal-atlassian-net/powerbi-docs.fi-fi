---
title: Visualisointien mukauttamisen salliminen raportin käyttäjille
description: Anna raportin lukijoiden luoda oma näkymä raportista ilman sen muokkaamista.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/09/2020
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: ab232d4e5b6d17e7f20ed8a41875ca47693eb285
ms.sourcegitcommit: 21b06e49056c2f69a363d3a19337374baa84c83f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/15/2020
ms.locfileid: "83407600"
---
# <a name="let-users-personalize-visuals-in-a-report"></a>Visualisointien mukauttamisen salliminen raportin käyttäjille

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Kun jaat raportin laajalle yleisölle, osa käyttäjistä haluaa ehkä tarkastella tiettyjä visualisointeja hieman eri näkymien kautta. He haluavat ehkä vaihtaa akselin sisältöä, muuttaa visualisointityyppiä tai lisätä sisältöä työkaluvihjeeseen. On vaikea luoda visualisointi, joka täyttää kaikkien vaatimukset. Tämän uuden ominaisuuden ansiosta voit antaa kuluttajille mahdollisuuden tutkia ja mukauttaa visualisointeja raportin lukunäkymässä. He voivat muokata visualisointia haluamallaan tavalla ja tallentaa sen kirjanmerkiksi, johon voi palata. He eivät tarvitse raportin muokkausoikeutta, eikä heidän tarvitse ottaa yhteyttä raportin tekijään muutosta varten.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-visual.png" alt-text="Visualisoinnin mukauttaminen":::
 
## <a name="what-report-consumers-can-change"></a>Mitä raportin kuluttajat voivat muuttaa

Tämän ominaisuuden avulla kuluttajat voivat saada merkityksellisiä tietoja Power BI -raportin visualisointien tapauskohtaisen tutkimisen kautta. Jos haluat oppia käyttämään tätä ominaisuutta kuluttajana, katso [Mukauta visualisointeja raporteissasi](../consumer/end-user-personalize-visuals.md). Ominaisuus sopii erinomaisesti raportin tekijöille, jotka haluavat tarjota raportin lukijoille perustutkimustilanteita. Tässä ovat muokkaukset, joita raportin lukijat voivat tehdä:

- Visualisointityypin muuttaminen
- Mittayksikön tai dimension vaihtaminen
- Selitteen lisääminen tai poistaminen
- Kahden tai useamman mittarin vertaileminen
- Koosteiden muuttaminen jne.

Uusien etsintäominaisuuksien lisäksi tämä ominaisuus sisältää muutakin. Se sisältää myös tapoja, joilla kuluttajat voivat siepata ja jakaa tekemänsä muutokset:

- Omien muutosten sieppaaminen
- Omien muutosten jakaminen
- Kaikkien raporttiin tehtyjen muutosten palauttaminen
- Kaikkien visualisointiin tehtyjen muutosten palauttaminen
- Omien viimeaikaisten muutosten tyhjentäminen

## <a name="turn-on-the-preview-feature"></a>Esikatselutoiminnon ottaminen käyttöön

Koska tämä ominaisuus on esikatselutilassa, sinun on ensin otettava käyttöön ominaisuusvalitsin. Valitse **Tiedosto** > **Asetukset ja vaihtoehdot** > **Asetukset**. Varmista kohdassa **Yleiset** asetukset > **Esikatselutoiminnot**, että **Mukauta visualisointeja** on valittuna.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-preview-personalize-visual.png" alt-text="Mukauta visualisointeja -asetuksen ottaminen käyttöön":::

Saatat joutua käynnistämään Power BI Desktopin uudelleen, jotta näet sen nykyisen tiedoston asetuksissa.

## <a name="enable-personalization-in-a-report"></a>Mukauttamisen ottaminen käyttöön raportissa

Kun olet ottanut esikatseluvalitsimen käyttöön, sinun on otettava se erityisesti käyttöön raporteissa, joissa kuluttajat voivat mukauttaa visualisointeja.

Voit kuitenkin ottaa tämän ominaisuuden käyttöön joko Power BI Desktopissa tai Power BI -palvelussa.

### <a name="in-power-bi-desktop"></a>Power BI Desktopissa

Jos haluat ottaa ominaisuuden käyttöön Power BI Desktopissa, siirry kohtaan **Tiedosto** > **Asetukset ja vaihtoehdot** > **Asetukset** > **Nykyinen tiedosto** > **Raporttiasetukset**. Varmista, että **Mukauta visualisointeja (esikatselu)** on käytössä.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-settings-personalize-visual.png" alt-text="Mukauttamisen ottaminen käyttöön raportissa":::

### <a name="in-the-power-bi-service"></a>Power BI -palvelussa

Jos haluat ottaa ominaisuuden käyttöön Power BI -palvelussa, siirry raporttisi **asetuksiin**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-service-settings-personalize-visual.png" alt-text="Raporttiasetukset Power BI -palvelussa":::

Ota käyttöön **Mukauta visualisointeja (esikatselu)**  > **Tallenna**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-service-personalize-visual.png" alt-text="Mukauta visualisointeja -asetuksen ottaminen käyttöön palvelussa":::

## <a name="select-visuals-that-can-be-personalized"></a>Valitse visualisoinnit, joita voidaan mukauttaa

Kun otat tämän asetuksen käyttöön raportissa, kaikkia raportin visualisointeja voidaan mukauttaa oletusarvoisesti. Jos haluat, että kaikkia visualisointeja ei voi mukauttaa, voit ottaa asetuksen käyttöön tai poistaa sen käytöstä visualisointikohtaisesti.

Valitse visualisointi > valitse **Muotoilu** **Visualisoinnit**-ruudussa > laajenna **Visualisoinnin otsikko**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-format-visual-header-personalize.png" alt-text="Valitse visuaalinen otsikko":::
 
Valitse **Mukauta visualisointia** -liukusäätimen arvoksi  >  **Käytössä** tai **Ei käytössä**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-format-visual-personalize-on-off.png" alt-text="Mukauta visualisointia -liukusäädintä käytössä tai ei käytössä":::


## <a name="limitations-and-known-issues"></a>Rajoitukset ja tunnetut ongelmat

Tällä hetkellä ominaisuudessa on joitakin rajoituksia, jotka on otettava huomioon.

- Tätä ominaisuutta ei tueta upotettavissa tilanteissa, kuten Julkaise verkkoon -toiminnossa.
- Käyttäjän tutkimukset eivät säily automaattisesti. Näkymä täytyy tallentaa henkilökohtaiseksi kirjanmerkiksi, jotta muutokset säilyvät.
- Visualisointeja ei voi muuttaa Power BI -mobiilisovelluksissa. Kaikkia Power BI -palvelussa henkilökohtaiseen kirjanmerkkiin tallennettuja visualisoinnin muutoksia noudatetaan kuitenkin myös mobiilisovelluksissa.

On myös joitakin tunnettuja ongelmia, joita käsitellään:

- Hierarkian lisäämistä ei tueta; sinun on lisättävä erilliset alielementtikohteet.
- Et voi muuttaa päivämäärähierarkiaa päivämääräksi tai päinvastoin. 
- Henkilökohtaisissa kirjanmerkeissä tulokset saattavat erota hieman valitsemasi jakson mukaan. Ristiriidat ovat mahdollisia, koska emme sieppaa raportin koko tilaa, vaan ainoastaan tehdyt muutokset. Voit kiertää ongelman valitsemalla ensin **Palauta oletusasetukset** ja sitten tarkasteltavan kirjanmerkin. 

## <a name="next-steps"></a>Seuraavat vaiheet

[Mukauta visualisointeja raporteissasi](../consumer/end-user-personalize-visuals.md).     

Kokeile uutta visualisoinnin mukautuskäyttökokemusta. Anna meille palautetta tästä ominaisuudesta ja siitä, miten voimme jatkaa sen parantamista, [Power BI:n ideat -sivustolla](https://ideas.powerbi.com/forums/265200-power-bi). 

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
