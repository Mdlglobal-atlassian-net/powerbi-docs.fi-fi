---
title: Muotoiluasetusten lisääminen Power BI:n mukautettuun visualisointiin
description: Opetusohjelma Power BI:n mukautetun visualisoinnin muotoiluasetusten kehittämisestä
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 11/21/2018
ms.openlocfilehash: 5fa14e3aa8a303206d52359d04db05850e096d81
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/23/2019
ms.locfileid: "71194593"
---
# <a name="tutorial-adding-formatting-options-to-a-power-bi-visual"></a>Opetusohjelma: Muotoiluasetusten lisääminen Power BI -visualisointiin

Tässä opetusohjelmassa opetellaan lisäämään visualisointiin yleisiä ominaisuuksia.

Tässä opetusohjelmassa opit:
> [!div class="checklist"]
> * Visualisoinnin ominaisuuksien lisääminen
> * Visualisoinnin paketointi
> * Mukautetun visualisoinnin tuominen Power BI Desktop -raporttiin

## <a name="adding-formatting-options"></a>Muotoiluasetusten lisääminen

1. Valitse **Power BI:ssä** **Muoto-sivu**.

    Sinun tulisi nähdä viesti *Muotoiluasetukset eivät ole käytettävissä tälle visualisoinnille*.

    ![Muotoilusivellin](media/custom-visual-develop-tutorial-format-options/format-paintbrush.png)

2. Avaa *capabilities.json*-tiedosto **Visual Studio Codessa**.

3. Lisää **objektit** rivin 8 jälkeen ennen **dataViewMappings**-matriisia.

    ```json
    "objects": {},
    ```
    ![Lisää objektit](media/custom-visual-develop-tutorial-format-options/add-objects.png)

4. Tallenna **capabilities.json**-tiedosto.

5. Tarkista **Power BI:ssä** muotoilun asetukset uudelleen.

    > [!Note]
    > Jos et näe muotoiluasetukset eivät ole muuttuneet, valitse **Lataa mukautettu visualisointi uudelleen**.

    ![Näytä muotoiluasetukset](media/custom-visual-develop-tutorial-format-options/view-formatting-options.png)

6. Valitse **Otsikko**-asetukseksi *Ei käytössä*. Huomaa, että visualisointi ei enää näytä mittarin nimeä vasemmassa yläkulmassa.

    ![Ruutu-asetus ei ole käytössä](media/custom-visual-develop-tutorial-format-options/tile-option-off.png)

    ![Ei nimiruutua](media/custom-visual-develop-tutorial-format-options/no-name-tile.png)

### <a name="adding-custom-formatting-options"></a>Mukautettujen muotoiluasetusten lisääminen

Voit lisätä mukautettuja ominaisuuksia, joiden avulla voit määrittää ympyrän värin ja reunan leveyden.

1. Pysäytä mukautettu visualisointi PowerShellissä.

2. Lisää Visual Studio Codessa **capabilities.json**-tiedostoon seuraava JSON-koodipätkä **objects**-tunnisteella merkittyyn objektiin.

    ```json
    "circle": {
     "displayName": "Circle",
     "properties": {
         "circleColor": {
             "displayName": "Color",
             "description": "The fill color of the circle.",
             "type": {
                 "fill": {
                     "solid": {
                         "color": true
                     }
                 }
             }
         },
         "circleThickness": {
             "displayName": "Thickness",
             "description": "The circle thickness.",
             "type": {
                 "numeric": true
                 }
             }
         }
     },
    ```

    JSON-koodipätkä kuvaa ryhmän nimeltä ympyrä, joka koostuu kahdesta asetuksesta nimeltä circleColor ja circleThickness.

   ![Ympyrän paksuuskoodi](media/custom-visual-develop-tutorial-format-options/circle-thickness-code.png)

3. Tallenna **capabilities.json**-tiedosto.

4. Laajenna **resurssienhallintaruudussa** **src**-kansio ja valitse kansiosta **settings.ts**. *Tämä tiedosto edustaa aloitusvisualisoinnin asetuksia*.

5. Korvaa **settings.ts**-tiedostossa kaksi luokkaa seuraavalla koodilla.

    ```typescript
    export class CircleSettings {
     public circleColor: string = "white";
     public circleThickness: number = 2;
    }
    export class VisualSettings extends DataViewObjectsParser {
     public circle: CircleSettings = new CircleSettings();
    }
    ```

    ![Moduulin luokat](media/custom-visual-develop-tutorial-format-options/module-classes.png)

    Tämä moduuli määrittää kaksi luokkaa. **CircleSettings**-luokka määrittää kaksi ominaisuutta, joiden nimet vastaavat **capabilities.json**-tiedostossa määritettyjä objekteja (**circleColor** ja **circleThickness**), ja asettaa myös oletusarvot. **VisualSettings**-luokka perii **DataViewObjectParser**-luokan ja lisää ominaisuuden nimeltä **circle**, joka vastaa *capabilities.json*-tiedostossa määritettyä objektia, ja palauttaa **CircleSettings**-luokan esiintymän.

6. Tallenna **settings.ts**-tiedosto.

7. Avaa **visual.ts**-tiedosto.

8. Lisää seuraava ominaisuus **Visual**-luokkaan.

    ```typescript
    private visualSettings: VisualSettings;
    ```
    Tämä ominaisuus sisältää viittauksen **VisualSettings**-objektiin, joka kuvaa visualisoinnin asetuksia.

    ![Lisää visualisoinnin luokka](media/custom-visual-develop-tutorial-format-options/visual-class-add-on.png)

9. Lisää **Visual**-luokassa seuraava menetelmä ennen **päivitysmenetelmää**. Tätä menetelmää käytetään muotoiluasetusten täyttämiseen.

    ```typescript
    public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration {
     const settings: VisualSettings = this.visualSettings ||
    VisualSettings.getDefault() as VisualSettings;
     return VisualSettings.enumerateObjectInstances(settings, options);
    }
    ```
    Tätä menetelmää käytetään muotoiluasetusten täyttämiseen.

    ![Visualisoinnin asetusobjekti](media/custom-visual-develop-tutorial-format-options/visual-settings-object.png)

10. Lisää seuraava koodi **päivitysmenetelmään** **radius**-sädemuuttujan esittelyn jälkeen.

    ```typescript
    this.visualSettings = VisualSettings.parse<VisualSettings>(dataView);

    this.visualSettings.circle.circleThickness = Math.max(0, this.visualSettings.circle.circleThickness);

    this.visualSettings.circle.circleThickness = Math.min(10, this.visualSettings.circle.circleThickness);
    ```
    Tämä koodi noutaa muotoiluasetukset. Se säätää mitä tahansa **circleThickness**-ominaisuuteen välitettyä arvoa. Se muuttaa sen arvoksi 0, jos se on negatiivinen, tai arvoksi 10, jos se on suurempi kuin 10.

    ![Sädemuuttuja](media/custom-visual-develop-tutorial-format-options/radius.png)

11. Muokkaa **täyttötyyliin** välitettyä arvoa seuraavaksi lausekkeeksi **ympyräelementtiä** varten.

    ```typescript
    this.visualSettings.circle.circleColor
    ```

    ![Täyttää ympyräelementin](media/custom-visual-develop-tutorial-format-options/circle-element-fill.png)

12. Muokkaa **viivanleveystyyliin** välitettyä arvoa seuraavaksi lausekkeeksi **ympyräelementtiä** varten.

    ```typescript
    this.visualSettings.circle.circleThickness
    ```

    ![Ympyrän viivanleveys](media/custom-visual-develop-tutorial-format-options/circle-stroke-width.png)

13. Tallenna visual.ts-tiedosto.

14. Käynnistä visualisointi PowerShellissä.

    ```powershell
    pbiviz start
    ```

15. Valitse **Power BI:ssä** visualisoinnin päällä olevalta irralliselta työkaluriviltä **Automaattinen uudelleenlataus käytössä tai ei käytössä**.

16. Laajenna **Ympyrä**-kohta **visualisoinnin muotoiluasetuksissa**.

    ![Ympyrän muoto](media/custom-visual-develop-tutorial-format-options/circle-format.png)

    Muokkaa **väri**- ja **paksuusasetuksia**.

    Anna **paksuusasetuksen** arvoksi on pienempi kuin nolla ja arvo, joka on suurempi kuin 10. Huomaa, että visualisointi päivittää arvon toteutettavaksi enimmäis- tai vähimmäisarvoksi.

## <a name="packaging-the-custom-visual"></a>Mukautetun visualisoinnin pakkaaminen

Anna mukautetun visualisointiprojektin ominaisuusarvot, päivitä kuvaketiedosto ja pakkaa mukautettu visualisointi.

1. Pysäytä mukautettu visualisointi **PowerShellissä**.

2. Avaa **pbiviz.json**-tiedosto **Visual Studio Codessa**.

3. Vaihda **visual**-objektiin **displayName**-ominaisuudeksi *Circle Card*.

    Näet näyttönimen viemällä hiiren **Visualisoinnit**-ruudussa kuvakkeen päälle.

    ![Visualisoinnin näyttönimi](media/custom-visual-develop-tutorial-format-options/display-name-viz.png)

4. Kirjoita seuraava teksti **description**-ominaisuutta varten.

    *Näyttää muotoillun mittariarvon ympyrän sisällä*

5. Voit halutessasi kirjoittaa omat tietosi **author**-objektiin.

6. Tallenna **pbiviz.json**-tiedosto.

7. Huomaa, että asiakirja määrittää polun kuvakkeeseen **assets**-objektissa. Kuvake on kuva, joka näkyy **_Visualisoinnit_** -ruudussa. Sen on oltava **PNG**-tiedosto, jonka koko on *20 × 20 kuvapistettä*.

8. Kopioi Windowsin Resurssienhallinnassa icon.png-tiedosto ja korvaa sillä assets-kansiossa oleva oletustiedosto.

9. Laajenna assets-kansio Visual Studio Coden resurssienhallintaruudussa ja valitse icon.png-tiedosto.

10. Tarkista kuvake.

    ![Visualisointiruudun kuva](media/custom-visual-develop-tutorial-format-options/viz-pane-image.png)

11. Varmista Visual Studio Codessa, että kaikki tiedostot on tallennettu.

12. Pakkaa mukautettu visualisointi PowerShellissä seuraavalla komennolla.

    ```powershell
    pbiviz package
    ```

    ![Dist-kansio](media/custom-visual-develop-tutorial-format-options/dist-folder.png)

Paketti on nyt tulostettu projektin **dist**-kansioon. Paketti sisältää kaiken tarvittavan mukautetun visualisoinnin tuomiseen joko Power BI -palveluun tai Power BI Desktopin raporttiin. Olet nyt paketoinut mukautetun visualisoinnin, ja se on nyt valmis käytettäväksi.

## <a name="importing-the-custom-visual"></a>Mukautetun visualisoinnin tuominen

Voit nyt avata Power BI Desktop -raportin ja tuoda mukautetun Circle Card -visualisoinnin.

1. Avaa **Power BI Desktop** ja luo uusi raportti millä tahansa *mallitietojoukolla*.

2. Valitse **_Visualisoinnit_** -ruudussa **pistekuvake** ja valitse sitten **Tuo tiedostosta**.

    ![Lisää mukautettu visualisointi Desktop-raporttiin](media/custom-visual-develop-tutorial-format-options/add-custom-viz-to-desktop.png)

3. Valitse **tuonti-ikkunassa** **Tuo**.

4. Siirry Avaa ikkuna -kohdassa projektihakemiston **dist**-kansioon.

5. Valitse **circleCard.pbiviz**-tiedosto ja sitten **Avaa**.

6. Kun visualisointi on tuotu onnistuneesti, valitse **OK**.

7. Varmista, että visualisointi on lisätty **_Visualisoinnit_** -ruutuun.

    ![Tarkastele PBI Desktopin Visualisoinnit-ruudussa](media/custom-visual-develop-tutorial-format-options/view-in-desktop-viz-pane.png)

8. Vie hiiri **Circle Card** -kuvakkeen päälle, niin näet työkaluvihjeen.

## <a name="debugging"></a>Virheenkorjaus

Katso vihjeitä mukautetun visualisoinnin virheenkorjauksesta [virheenkorjauksen oppaasta](https://microsoft.github.io/PowerBI-visuals/docs/how-to-guide/how-to-debug/).

## <a name="next-steps"></a>Seuraavat vaiheet

Voit antaa luomasi visualisoinnin muiden käyttöön lähettämällä sen **AppSourceen**. Lisätietoja tästä prosessista on artikkelissa [Power BI -visualisointien julkaiseminen AppSourceen](office-store.md).