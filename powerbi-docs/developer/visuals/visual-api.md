---
title: Visualisoinnin ohjelmointirajapinta
description: Tässä artikkelissa kuvataan, miten Power BI -visualisointien IVisual-ohjelmointirajapintaa käytetään
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/19/2020
ms.openlocfilehash: 6ec30fdd4812427ae855ff9a167d946d2a415c28
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83302962"
---
# <a name="visual-api"></a>Visualisoinnin ohjelmointirajapinta
Kaikki visualisoinnit alkavat luokalla, joka ottaa käyttöön `IVisual`-liittymän. Voit antaa luokalle minkä tahansa nimen, kunhan olemassa on täsmälleen yksi luokka, joka ottaa käyttöön `IVisual`-liittymän.

> [!NOTE]
> Visualisoinnin luokan nimen on vastattava *pbiviz.jso*-tiedostossa olevia määrityksiä.

Katso visualisointiluokan esimerkkiä, joka sisältää seuraavat käyttöön otettavat menetelmät:

* `constructor`, , vakiokonstruktori visualisoinnin tilan alustamista varten
* `update`, visualisoinnin tietojen päivittämiseen
* `enumerateObjectInstances`, objektien palauttamiseen ominaisuusruudun (muotoiluasetukset) täyttämistä varten; voit muuttaa asetuksia tarpeen mukaan
* `destroy`, vakiodestruktori tyhjentämistä varten

```typescript
class MyVisual implements IVisual {
    
    constructor(options: VisualConstructorOptions) {
        //one time setup code goes here (called once)
    }
    
    public update(options: VisualUpdateOptions): void {
        //code to update your visual goes here (called on all view or data changes)
    }

    public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration {
        //returns objects to populate the property pane (called for each object defined in capabilities)
    }
    
    public destroy(): void {
        //one time cleanup code goes here (called once)
    }
}
```

## <a name="constructor"></a>constructor

Visuaalisen luokan konstruktoria kutsutaan, kun visualisoinnin esiintymä luodaan. Sitä voi käyttää minkä tahansa visualisoinnin tarvitsemien toimintojen määrittämiseen.

```typescript
constructor(options: VisualConstructorOptions)
```

**VisualConstructorOptions**

* `element: HTMLElement`, viittaus DOM-elementtiin, joka sisältää visualisointisi
* `host: IVisualHost`, kokoelma ominaisuuksia ja palveluja, joita voidaan käyttää vuorovaikutuksessa visualisoinnin isännän (Power BI) kanssa

   `IVisualHost` sisältää seuraavat palvelut:

   ```typescript
   export interface IVisualHost extends extensibility.IVisualHost {
       createSelectionIdBuilder: () => visuals.ISelectionIdBuilder;
       : () => ISelectionManager;
       colorPalette: ISandboxExtendedColorPalette;
       persistProperties: (changes: VisualObjectInstancesToPersist) => void;
       applyJsonFilter: (filter: IFilter[] | IFilter, objectName: string, propertyName: string, action: FilterAction) => void;
       tooltipService: ITooltipService;
       telemetry: ITelemetryService;
       authenticationService: IAuthenticationService;
       locale: string;
       allowInteractions: boolean;
       launchUrl: (url: string) => void;
       fetchMoreData: () => boolean;
       instanceId: string;
       refreshHostData: () => void;
       createLocalizationManager: () => ILocalizationManager;
       storageService: ILocalVisualStorageService;
       eventService: IVisualEventService;
       switchFocusModeState: (on: boolean) => void;
   }
   ```
   * `createSelectionIdBuilder`, luo ja tallentaa metatietoja visualisoinnin valittavissa olevia kohteita varten
   * `createSelectionManager`, luo viestintäsillan, jonka kautta visualisoinnin isännälle ilmoitetaan valintatilan muutoksista; katso [Valinnan ohjelmointirajapinta](./selection-api.md).
   * `createLocalizationManager`, luo hallintatoiminnon [lokalisoinnin](./localization.md) tueksi
   * `allowInteractions: boolean`, totuusarvomerkintä, joka ilmaisee, pitääkö visualisoinnin olla vuorovaikutteinen
   * `applyJsonFilter`, ottaa käyttöön tietyt suodatintyypit; katso [Suodattimen ohjelmointirajapinta](./filter-api.md)
   * `persistProperties`, sallii käyttäjien säilyttää ominaisuudet ja tallentaa ne visualisoinnin määrityksen mukana, jolloin ne ovat käytettävissä seuraavassa uudelleenlatauksessa
   * `eventService`, palauttaa [tapahtumapalvelun](./event-service.md), joka tukee **Hahmonna**-tapahtumia
   * `storageService`, palauttaa palvelun, joka helpottaa [paikallisen tallennuksen](./local-storage.md) käyttöä visualisoinnissa
   * `authenticationService`, luo palvelun käyttäjien todentamisen avuksi
   * `tooltipService`, palauttaa [työkaluvihjepalvelun](./add-tooltips.md), joka helpottaa työkaluvihjeiden käyttöä visualisoinnissa
   * `launchUrl`, auttaa [käynnistämään URL-osoitteen](./launch-url.md) seuraavassa välilehdessä
   * `locale`, palauttaa aluekohtaisen merkki jonon; katso [Lokalisointi](./localization.md)
   * `instanceId`, palauttaa merkkijonon, jonka avulla visualisoinnin nykyinen esiintymä tunnistetaan
   * `colorPalette`, palauttaa värivalikoiman, jota tarvitaan värien käyttämiseen tiedoissa
   * `fetchMoreData`, tukee vakiorajaa (1 000 riviä) suuremman tietomäärän käyttämistä
   * `switchFocusModeState`, auttaa muuttamaan kohdistustilaa

## <a name="update"></a>update

Kaikkien visualisointien on käytettävä julkista päivitysmenetelmää, jota kutsutaan aina, kun tietoja tai isäntäympäristöä muutetaan.

```typescript
public update(options: VisualUpdateOptions): void
```

**VisualUpdateOptions**

* `viewport: IViewport`, sen näyttöikkunan mitat, jossa visualisointi tulisi hahmontaa
* `dataViews: DataView[]`, dataview-objekti, joka sisältää kaikki visualisoinnin hahmontamiseen tarvittavat tiedot (visualisoinnissa käytetään yleensä DataView-kohdan alla olevaa luokkaominaisuutta)
* `type: VisualUpdateType`, merkintä, joka ilmaisee tämän päivityksen tyypit (**Tiedot** | **Muuta kokoa** | **ViewMode** | **Tyyli** | **ResizeEnd**)
* `viewMode: ViewMode`, merkintä, joka ilmaisee visualisoinnin katselutilan (**Näytä** | **Muokkaa** | **InFocusEdit**)
* `editMode: EditMode`, merkintä, joka ilmaisee visualisoinnin muokkaustilan (**Oletus** | **Lisäasetukset**) (jos visualisointi tukee **AdvancedEditMode**-tilaa, sen pitäisi hahmontaa käyttöliittymän lisäohjausobjektit vain, kun **editMode**-asetuksena on **Lisäasetukset**, katso [AdvancedEditMode](./advanced-edit-mode.md))
* `operationKind?: VisualDataChangeOperationKind`, merkintä, joka ilmaisee tietomuutoksen tyypin (**Luo** | **Liitä**)
* `jsonFilters?: IFilter[]`, kokoelma käytettäviä json-suodattimia
* `isInFocus?: boolean`, merkintä, joka ilmaisee, onko visualisointi kohdistustilassa
    
## <a name="enumerateobjectinstances-optional"></a>enumerateObjectInstances `optional`

Tätä menetelmää kutsutaan kaikkia ominaisuuksissa mainittuja objekteja varten. Valintoja (tällä hetkellä vain nimeä käytettäessä) `VisualObjectInstanceEnumeration`-funktio palauttaa tiedon siitä, miten tämä ominaisuus näytetään.

```typescript
enumerateObjectInstances(options:EnumerateVisualObjectInstancesOptions):VisualObjectInstanceEnumeration
```

**EnumerateVisualObjectInstancesOptions**

* `objectName: string`, objektin nimi

## <a name="destroy-optional"></a>destroy `optional`

Destroy-funktiota kutsutaan, kun visualisointi puretaan, ja sitä voidaan käyttää tehtävien tyhjentämiseen, kuten tapahtumien kuuntelutoimintojen poistamiseen.

``` typescript
public destroy(): void
```

> [!Note]
> Power BI ei tavallisesti kutsu `destroy`-funktiota, sillä on nopeampaa poistaa koko IFrame,joka sisältää visualisoinnin.
