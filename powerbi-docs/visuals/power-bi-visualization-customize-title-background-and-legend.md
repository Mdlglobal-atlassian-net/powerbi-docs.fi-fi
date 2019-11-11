---
title: Power BI -visualisointien muotoilun aloittaminen
description: Visualisoinnin otsikon, taustan ja selitteen muokkaaminen
author: mihart
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 011e2b6d3bf5cc998f7db76e96536d2ddab09888
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880862"
---
# <a name="customize-visualization-titles-legends-and-backgrounds"></a>Mukauta visualisoinnin otsikoita, selitteitä ja taustoja

Tässä opetusohjelmassa opit pari erilaista tapaa mukauttaa visualisointeja. Visualisointien mukauttamiseen on paljon vaihtoehtoja. Paras keino tutustua niihin kaikkiin on tarkastella **Muotoilu**-ruutua (valitse maalirullakuvake). Jotta pääset alkuun, tässä artikkelissa kerrotaan, miten voit mukauttaa visualisoinnin otsikkoa, selitettä ja taustaa.

Kaikkia visualisointeja ei voi mukauttaa. Katso lisätietoja visualisointien [täydellisestä luettelosta](#visualization-types-that-you-can-customize).

Pikakelaa kohtaan 4:50 videossa, jossa on esittely visualisointien mukauttamisesta:

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

noudata sitten alla olevia ohjeita ja kokeile samaa itse omilla tiedoillasi.

## <a name="prerequisites"></a>Edellytykset

- Power BI -palvelu tai Power BI Desktop

- Jälleenmyyntianalyysimallin raportti

## <a name="customize-visualization-titles-in-reports"></a>Visualisoinnin otsikoiden mukauttaminen raporteissa

Seuraa mukana kirjautumalla sisään [Power BI -palveluun](https://app.powerbi.com)ja avaamalla [Jälleenmyyntianalyysimalli](../sample-datasets.md)-raportti [Muokkaa raporttia](../service-interact-with-a-report-in-editing-view.md) -näkymässä.

> [!NOTE]
> Kun kiinnität visualisoinnin raporttinäkymään, siitä tulee raporttinäkymän ruutu. Voit myös mukauttaa itse ruutuja [uusien otsikoiden ja alaotsikoiden sekä hyperlinkkien avulla, ja muuttaa niiden kokoa](../service-dashboard-edit-tile.md).

1. Siirry **Jälleenmyyntianalyysimalli**-raportin **Uudet myymälät** -sivulle.

1. Valitse klusteroitu **Avaa myymälöiden määrä kuukauden ja ketjun mukaan** -pylväskaavio.

1. Voit näyttää muotoiluvaihtoehdot valitsemalla maalirullakuvakkeen **Visualisoinnit**-ruudussa.

1. Valitse **Otsikko** tämän osion laajentamiseksi.

   ![Näyttökuva Muotoilu-ruudusta, jossa maalirullakuvake on korostettu ja jossa nuoli osoittaa avattavaan Otsikko-valikkoon.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-formatting-menu.png)

1. Siirrä **otsikon** liukusäädin tilaan **Käytössä**.

   ![Näyttökuva Käytössä-liukusäätimestä.](media/power-bi-visualization-customize-title-background-and-legend/onoffslider.png)

1. Voit muuttaa otsikkoa kirjoittamalla *Myymälöiden määrä kuukauden mukaan avattuna* **Otsikon teksti** -kenttään.

1. Muuta **fonttiväri** oranssiksi ja **taustaväri** keltaiseksi.

    1. Valitse avattava luettelo ja valitse väri **teemaväreistä**, **viimeksi käytetyistä väreistä** tai **mukautetuista väreistä**.

        ![Näyttökuva fonttivärin ja taustavärin vaihtoehdoista.](media/power-bi-visualization-customize-title-background-and-legend/customizecolorpicker.png)

    1. Valitse avattava luettelo väri-ikkunan sulkemiseksi.

       Tallenna tekemäsi muutokset.

       Jos haluat palauttaa kaikki muutokset, voit siirtyä takaisin oletusväreihin valitsemalla **Palauta oletusasetukseen** väri-ikkunassa.

1. Suurenna tekstikooksi **12 pt**.

1. Viimeinen mukautus, jonka teet kaavion otsikkoon, on sen tasaaminen visualisoinnin keskelle.

    ![Näyttökuva tasauksen ohjausobjekteista, joissa Keskitä-vaihtoehto on valittuna.](media/power-bi-visualization-customize-title-background-and-legend/customizealign.png)

Tässä vaiheessa opetusohjelmaa klusteroidun pylväskaavion otsikon pitäisi näyttää seuraavankaltaiselta:

![Näyttökuva äskettäin määritetystä klusteroidusta pylväskaaviosta.](media/power-bi-visualization-customize-title-background-and-legend/tutorialprogress1.png)

Tallenna tekemäsi muutokset ja siirry seuraavaan osioon.

Jos haluat palauttaa kaikki muutokset, valitse **Palauta oletusasetukseen** **Otsikko**-mukauttamisruudun alareunassa.

![Näyttökuva Palauta oletusasetukseen -vaihtoehdosta.](media/power-bi-visualization-customize-title-background-and-legend/revertall.png)

## <a name="customize-visualization-backgrounds"></a>Visualisoinnin taustojen mukauttaminen

Kun sama klusteroitu pylväskaavio on valittuna, laajenna **Tausta**-vaihtoehtoja.

1. Siirrä **taustan** liukusäädin tilaan **Käytössä**.

1. Valitse avattava valikko ja valitse harmaa väri.

1. Muuta **läpinäkyvyydeksi** **74 %** .

Tässä vaiheessa opetusohjelmaa klusteroidun pylväskaavion taustan pitäisi näyttää seuraavankaltaiselta:

![Näyttökuva klusteroidusta pylväskaaviosta, jossa taustaväri on päivitetty.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-customize-background.png)

Tallenna tekemäsi muutokset ja siirry seuraavaan osioon.

Jos haluat palauttaa kaikki muutokset, valitse **Palauta oletusasetukseen** **Tausta**-mukauttamisruudun alareunassa.

## <a name="customize-visualization-legends"></a>Visualisoinnin selitteiden mukauttaminen

1. Avaa **Yleiskatsaus**-raporttisivu ja valitse **Kokonaismyynnin varianssi tilikauden ja aluejohtajan mukaan** -kaavio.

1. Voit avata Muotoilu-ruudun valitsemalla maalirullakuvakkeen **Visualisoinnit**-välilehdessä.

1. Laajenna **Selite**-vaihtoehtoja:

      ![Näyttökuva Selite-vaihtoehdosta.](media/power-bi-visualization-customize-title-background-and-legend/legend.png)

1. Siirrä **selitteen** liukusäädin tilaan **Käytössä**.

1. Siirrä selite visualisoinnin vasemmalle puolelle.

1. Lisää selitteen otsikko vaihtamalla **otsikon** tilaksi **Käytössä**.

1. Kirjoita *Esimiehet* **Selitteen nimi** -kenttään.

Tässä vaiheessa opetusohjelmaa klusteroidun pylväskaavion selitteen pitäisi näyttää seuraavankaltaiselta:

![Näyttökuva päivitetystä selitteestä klusteroidussa pylväskaaviossa.](media/power-bi-visualization-customize-title-background-and-legend/legend-move.png)

Tallenna tekemäsi muutokset ja siirry seuraavaan osioon.

Jos haluat palauttaa kaikki muutokset, valitse **Palauta oletusasetukseen** **Selite**-mukauttamisruudun alareunassa.

## <a name="visualization-types-that-you-can-customize"></a>Visualisointityypit, joita voit mukauttaa

Seuraavassa on luettelo visualisointi- ja mukautusvaihtoehdoista, jotka ovat käytettävissä kullekin:

| Visualisointi | Nimi | Tausta | Selite |
|:--- |:--- |:--- |:--- |
| Alue | kyllä | kyllä |kyllä |
| Palkki | kyllä | kyllä |kyllä |
| Kortti | kyllä | kyllä |– |
| Monirivinen kortti | kyllä | kyllä | – |
| Sarake | kyllä | kyllä | kyllä |
| Yhdistelmä | kyllä | kyllä | kyllä |
| Ympyrä | kyllä | kyllä | kyllä |
| Täytetty kartta | kyllä | kyllä | kyllä |
| Suppilo | kyllä | kyllä | – |
| Mittari | kyllä | kyllä | – |
| Suorituskykyilmaisin | kyllä | kyllä | – |
| Viiva | kyllä | kyllä | kyllä |
| Kartta | kyllä | kyllä | kyllä |
| Matriisi | kyllä | kyllä | – |
| Ympyrä | kyllä | kyllä | kyllä |
| Piste | kyllä | kyllä | kyllä |
| Osittaja | kyllä | kyllä | – |
| Taulukko | kyllä | kyllä | – |
| Tekstiruutu | ei | kyllä | – |
| Puukartta | kyllä | kyllä | kyllä |
| Waterfall | kyllä | kyllä | kyllä |

## <a name="next-steps"></a>Seuraavat vaiheet

- [X- ja Y-akselin ominaisuuksien muokkaaminen](power-bi-visualization-customize-x-axis-and-y-axis.md)

- [Värimuotoilun ja akseliominaisuuksien käytön aloittaminen](service-getting-started-with-color-formatting-and-axis-properties.md)

- [Peruskäsitteet Power BI -palvelun kuluttajille](../consumer/end-user-basic-concepts.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
