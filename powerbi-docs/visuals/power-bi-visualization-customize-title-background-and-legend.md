---
title: Power BI -visualisointien muotoilun aloittaminen
description: Visualisoinnin otsikon, taustan ja selitteen muokkaaminen
author: mihart
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/04/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 1e2465273368c6b76e602e5ffbdf4ec3a1d121a3
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/04/2020
ms.locfileid: "75757826"
---
# <a name="customize-visualization-titles-backgrounds-and-legends"></a>Visualisoinnin otsikoiden, taustojen ja selitteiden mukauttaminen

Tässä opetusohjelmassa opit pari erilaista tapaa mukauttaa visualisointeja. Visualisointien mukauttamiseen on paljon vaihtoehtoja. Paras keino tutustua niihin kaikkiin on tarkastella **Muotoilu**-ruutua (valitse maalirullakuvake). Jotta pääset alkuun, tässä artikkelissa kerrotaan, miten voit mukauttaa visualisoinnin otsikkoa, selitettä ja taustaa sekä lisätä teeman.

Kaikkia visualisointeja ei voi mukauttaa. Katso lisätietoja visualisointien [täydellisestä luettelosta](#visualization-types-that-you-can-customize).


## <a name="prerequisites"></a>Edellytykset

- Power BI -palvelu tai Power BI Desktop

- Jälleenmyyntianalyysimallin raportti

## <a name="customize-visualization-titles-in-reports"></a>Visualisoinnin otsikoiden mukauttaminen raporteissa

Seuraa mukana kirjautumalla sisään Power BI Desktopiin ja avaamalla [Jälleenmyyntianalyysimalli](../sample-datasets.md)-raportin.

> [!NOTE]
> Kun kiinnität visualisoinnin raporttinäkymään, siitä tulee raporttinäkymän ruutu. Voit myös mukauttaa itse ruutuja [uusien otsikoiden ja alaotsikoiden sekä hyperlinkkien avulla, ja muuttaa niiden kokoa](../service-dashboard-edit-tile.md).

1. Siirry **Jälleenmyyntianalyysimalli**-raportin **Uudet myymälät** -sivulle.

1. Valitse klusteroitu **Avaa myymälöiden määrä kuukauden ja ketjun mukaan** -pylväskaavio.

1. Voit näyttää muotoiluvaihtoehdot valitsemalla maalirullakuvakkeen **Visualisoinnit**-ruudussa.

1. Valitse **Otsikko** tämän osion laajentamiseksi.

   ![Näyttökuva Muotoilu-ruudusta, jossa maalirullakuvake on korostettu ja jossa nuoli osoittaa avattavaan Otsikko-valikkoon.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-format-menu.png)

1. Siirrä **otsikon** liukusäädin tilaan **Käytössä**.

1. Voit muuttaa otsikkoa kirjoittamalla *Myymälöiden määrä kuukauden mukaan avattuna* **Otsikon teksti** -kenttään.

    ![Näyttökuva muotoruudusta, jossa on annettu otsikkoteksti.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-title.png)

1. Muuta **fonttiväri** valkoiseksi ja **taustaväri** siniseksi.    

    a. Valitse avattava luettelo ja valitse väri **teemaväreistä**, **viimeksi käytetyistä väreistä** tai **mukautetuista väreistä**.

        ![Screenshot of the Font color and Background color options.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-color.png)

    b. Valitse avattava luettelo väri-ikkunan sulkemiseksi.


1. Suurenna teksti kokoon **16 pt**.

1. Viimeinen mukautus, jonka teet kaavion otsikkoon, on sen tasaaminen visualisoinnin keskelle.

    ![Näyttökuva tasauksen ohjausobjekteista, joissa Keskitä-vaihtoehto on valittuna.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-align.png)

    Tässä vaiheessa opetusohjelmaa klusteroidun pylväskaavion otsikon pitäisi näyttää seuraavankaltaiselta:

    ![Näyttökuva äskettäin määritetystä klusteroidusta pylväskaaviosta.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-table.png)

Tallenna tekemäsi muutokset ja siirry seuraavaan osioon.

Jos haluat palauttaa kaikki muutokset, valitse **Palauta oletusasetukseen** **Otsikko**-mukauttamisruudun alareunassa.

![Näyttökuva Palauta oletusasetukseen -vaihtoehdosta.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-revert.png)

## <a name="customize-visualization-backgrounds"></a>Visualisoinnin taustojen mukauttaminen

Kun sama klusteroitu pylväskaavio on valittuna, laajenna **Tausta**-vaihtoehtoja.

1. Siirrä **taustan** liukusäädin tilaan **Käytössä**.

1. Valitse avattava valikko ja valitse harmaa väri.

1. Muuta **läpinäkyvyydeksi** **74 %** .

Tässä vaiheessa opetusohjelmaa klusteroidun pylväskaavion taustan pitäisi näyttää seuraavankaltaiselta:

![Näyttökuva klusteroidusta pylväskaaviosta, jossa taustaväri on päivitetty.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-background.png)

Tallenna tekemäsi muutokset ja siirry seuraavaan osioon.

Jos haluat palauttaa kaikki muutokset, valitse **Palauta oletusasetukseen** **Tausta**-mukauttamisruudun alareunassa.

## <a name="customize-visualization-legends"></a>Visualisoinnin selitteiden mukauttaminen

1. Avaa **Yleiskatsaus**-raporttisivu ja valitse **Kokonaismyynnin varianssi tilikauden ja aluejohtajan mukaan** -kaavio.

1. Voit avata Muotoilu-ruudun valitsemalla maalirullakuvakkeen **Visualisoinnit**-välilehdessä.

1. Laajenna **Selite**-vaihtoehdot:

    ![Näyttökuva Selite-kortista.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-legends.png)

1. Siirrä **selitteen** liukusäädin tilaan **Käytössä**.

1. Siirrä selite visualisoinnin vasemmalle puolelle.

1. Lisää selitteen otsikko vaihtamalla **otsikon** tilaksi **Käytössä**.

1. Kirjoita *Esimies* **Selitteen nimi** -kenttään.

1. Muuta **väri** mustaksi.

Tallenna tekemäsi muutokset ja siirry seuraavaan osioon.

Jos haluat palauttaa kaikki muutokset, valitse **Palauta oletusasetukseen** **Selite**-mukauttamisruudun alareunassa.

## <a name="customize-colors-using-a-theme"></a>Värien mukauttaminen teeman avulla

Raporttiteemojen avulla voit soveltaa rakennemuutoksia koko raporttiin, esimerkiksi käyttää yrityksen värejä, muuttaa kuvakejoukkoja tai ottaa käyttöön visualisointien uuden oletusarvoisen muotoilun. Kun otat käyttöön raporttiteeman, kaikissa raporttisi visualisoinneissa ja muotoiluissa käytetään valitun teeman värejä.

Jos haluat ottaa teeman käyttöön raportissasi, valitse **Vaihda teemaa** valikkoriviltä. Valitse teema.  Alla olevassa raportissa käytetään **Solar**-teemaa.

 
![Raportti, jossa käytetään keltaista, oranssia ja punaista Solar-teemaa](media/power-bi-visualization-customize-title-background-and-legend/power-bi-theme.png)

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
| Tärkein vaikuttaja | kyllä | kyllä | – |
| Suorituskykyilmaisin | kyllä | kyllä | – |
| Viiva | kyllä | kyllä | kyllä |
| Kartta | kyllä | kyllä | kyllä |
| Matriisi | kyllä | kyllä | – |
| Ympyrä | kyllä | kyllä | kyllä |
| Q&A | kyllä | kyllä | – |
| Piste | kyllä | kyllä | kyllä |
| Muoto | kyllä | kyllä | kyllä |
| Osittaja | kyllä | kyllä | – |
| Taulukko | kyllä | kyllä | – |
| Tekstiruutu | ei | kyllä | – |
| Puukartta | kyllä | kyllä | kyllä |
| Waterfall | kyllä | kyllä | kyllä |

## <a name="next-steps"></a>Seuraavat vaiheet

- [X- ja Y-akselin ominaisuuksien muokkaaminen](power-bi-visualization-customize-x-axis-and-y-axis.md)

- [Värimuotoilun ja akseliominaisuuksien käytön aloittaminen](service-getting-started-with-color-formatting-and-axis-properties.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
