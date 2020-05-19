---
title: Power BI:n visualisointien ohjelmointirajapinnan muutosloki
description: Tässä artikkelissa kuvataan Power BI -visualisointien ohjelmointirajapinnan eri versioiden tärkeimmät muutokset
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/13/2019
ms.openlocfilehash: fa8759d7edb519240140263bcd01bfdddd9c7d86
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83141065"
---
# <a name="power-bi-visuals-api-changelog"></a>Power BI:n visualisointien ohjelmointirajapinnan muutosloki
Tämä sivu sisältää pikayhteenvedon ohjelmointirajapinnan versioista. Tässä lueteltuja versioita pidetään vakaina, eikä niitä muuteta.

## <a name="api-v26"></a>API v2.6
  * Lisätään **isInFocus** päivitysvaihtoehdoksi ja **switchFocusModeState**-menetelmä visuaaliseen isäntään
  * Tukee **välisummien** mukauttamista

## <a name="api-v25"></a>API v2.5
  * Tukee **[Analytiikka-ruutua](./analytics-pane.md)**
  * Tukee `SelectionIdBuilder` **withMatrixNode**- ja **withTable** -menetelmiä
  * Ei enää tue `DataRepetitionSelector`-käyttöliittymää, korvattu `data.CustomVisualOpaqueIdentity`-käyttöliittymällä

## <a name="api-v23"></a>API v2.3
  * **[Aloitussivun ohjelmointirajapinta](./landing-page.md)**
  * **[Paikallisen tallennustilan ohjelmointirajapinta](./local-storage.md)**
  * **[Monikkosuodattimen ohjelmointirajapinta (monisarakesuodatin)](./filter-api.md#the-tuple-filter-api-multi-column-filter)**
  * **[Tapahtumien hahmontaminen](./event-service.md#render-events-in-power-bi-visuals)**

## <a name="api-v22"></a>API v2.2
  * Tukee **[JSON-suodattimen palautusta DataView-kohteesta](./filter-api.md#restore-the-json-filter-from-the-data-view)**
  * **[ContextMenu-ohjelmointirajapinta](./context-menu.md)**

## <a name="api-v21"></a>API v2.1
  * Suorituskykyyn tehtyjä parannuksia:
    * Nopeammat latausajat
    * Pienempi muistin jälki
    * Optimoidut tietojen ja tapahtumien transaktiot  

**Julkaisutiedot**
* Refakturoidun suodatuksen ohjelmointirajapinnat ovat käytettävissä API 2.2:ssa, eikä niitä tueta API 2.1:ssa.
* Visualisoinnit saavat vain niiden ominaisuuksille määritetyn dataView-tyypin. Visualisoinnit, jotka käyttivät useita dataView-tyyppejä, katkeavat tämän päivityksen seurauksena.
* Ei enää tue `DataViewScopeIdentity`-käyttöliittymää, korvattu `data.DataRepetitionSelector`-käyttöliittymällä. Jos olet käyttänyt `DataViewScopeIdentity`-käyttöliittymän avainominaisuutta, voit korvata sen `JSON.stringify(identity)`:lla
* `undefined` korvataan dataView:n sisällä olevalla kohteella`null`. Iteroitaessa matriisin yli käyttämällä `var item in myArray` se ohittaa `undefined`, mutta ei ohita `null`. Tämä päivitys saattaa rikkoa visualisointeja, jotka käyttävät tätä kaavaa. Varmista, että tarkistat `null` matriiseissa:
   ```typescript
   for (var item in myArray) {
     if (!item) {
       continue;
     }
     console.log(item);
   }
   ```
* `proto`-ominaisuus ei enää varastoi piilotettuja metadata\data-tietoja dataView-kohteen sisällä. Tämä päivitys voi rikkoa visualisointeja, jotka käyttävät ominaisuuksia `proto`:n kautta.

## <a name="api-v113"></a>API v1.13
* Tukee **[Synkronoi osittajat](./enable-sync-slicers.md)** -toimintoa, mutta huomaa, että tämä toimii vain yhden kentän osittajille PBI:n nykyisen kooditilan vuoksi, [lue lisää](/power-bi/desktop-slicers).
* Helppokäyttötoiminnot: [Suuren kontrastin tuki](./high-contrast-support.md) 
* Helppokäyttötoiminnot: Salli näppäimistö kohdistus -merkintä

## <a name="api-v112"></a>API v1.12
* Tukee teemoja
* Tukee **[fetchMoreData](./fetch-more-data.md)** , huomaa että **Lisätietojen noutamisen ohjelmointirajapinta** voittaa 30K-datapisteen kiinteän rajan
* **[Piirtoalustan työkaluvihjeiden ohjelmointirajapinta](./add-tooltips.md#add-report-page-tooltips)**

## <a name="api-v111"></a>API v1.11
* **[FilterManager-ohjelmointirajapinta](./filter-api.md)**
* Tukee **[kirjanmerkkejä](./bookmarks-support.md)** 

## <a name="api-v110"></a>API v1.10
* Lisää `ILocalizationManager`
* **Todentamisen ohjelmointirajapinta**

## <a name="api-v19"></a>API v1.9
* **[launchUrl-ohjelmointirajapinta](./launch-url.md)**

## <a name="api-v18"></a>API v1.8
* Tukee uutta tyyppiä **fillRule** (liukuväri) ominaisuusrakenteessa
* Tukee **suodattimen** ominaisuusrakennetta kohteiden ominaisuuksille

## <a name="api-v17"></a>API v1.7
* Tukee **[RESJSON](./localization.md#resource-file)**

## <a name="api-v162"></a>API v1.6.2
* Tukee **[Muokkaustilaa](./advanced-edit-mode.md)** visualisoinnille visuaaliseen muokkaustilaan siirtymistä varten
* Tukee **[vuorovaikutteisia (html) R Power BI -visualisointeja](https://microsoft.github.io/PowerBI-visuals/tutorials/building-r-powered-custom-visual/creating-r-visuals.md)** html-pohjaisena

## <a name="api-v150"></a>API v1.5.0
* Tukee **[Salli vuorovaikutteisuus](./visuals-interactions.md)** -ominaisuutta visuaalista vuorovaikutteisuutta varten

## <a name="api-v140"></a>API v1.4.0
* Tukee **[lokalisointia](./localization.md)**

## <a name="api-v130"></a>API v1.3.0
* Tukee **[työkaluvihjeitä](./add-tooltips.md)**

## <a name="api-v120"></a>API v1.2.0
* Lisää **colorPaletten** visualisoinnissa käytettävien värien hallintaa varten.
* Tukee **useita valintoja** - selectionManager voi hyväksyä `SelectionId`-matriisin.
* Tukee **[R-visualisointeja](https://microsoft.github.io/PowerBI-visuals/tutorials/building-r-powered-custom-visual/creating-r-visuals.md)** R-komentosarjojen avulla

## <a name="api-v110"></a>API v1.1.0
* Tukee virheenkorjausvisualisointia IFramessa
* Lisää kevyen eristyksen, jossa iFrame alustuu nopeammin
* [Capabilities.objects-korjaukset eivät tue “text”-tyypin](https://github.com/Microsoft/PowerBI-visuals-tools/issues/12) ongelmaa
* Tukee `pbiviz update` visuaalisen ohjelmointirajapinnan tyyppimääritysten ja rakenteen päivittämiseksi
* Tukee `--api-version`-merkintää `pbiviz new`:ssa visualisointien luomiseksi tietyllä ohjelmointirajapinnan versiolla
* Tukee API v1.2.0-alfaversiota

**Visuaalinen isäntä**
* Lisää **createSelectionIdBuilder**, jos haluat luoda yksilöiviä tunnisteita, joita käytetään tietojen valintaan
* Lisää **createSelectionManager**, jolla hallitaan visualisoinnin valintatilaa ja viestitään muutoksista visuaaliselle isännälle
* Lisää visualisointeihin käytettävän **väri**matriisin oletuksen

## <a name="api-v100"></a>API v1.0.0
* Alkuperäinen ohjelmointirajapinnan julkaisu
