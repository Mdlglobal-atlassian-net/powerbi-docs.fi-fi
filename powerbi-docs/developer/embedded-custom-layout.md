---
title: Mukautetut asettelut, joissa on Power BI:n upotettua sisältöä
description: Lue lisää mukautetuista asetteluista, kun sovellukseen upotetaan Power BI -sisältöä.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/19/2017
ms.author: maghan
ms.openlocfilehash: 351cfa27cc092af4bc5650a09730bc8a2661abbc
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2018
ms.locfileid: "30973122"
---
# <a name="custom-layouts"></a>Mukautetut asettelut


Mukautetun asettelun avulla voit upottaa raportin, jossa on eri asettelu kuin alkuperäisessä raportissa. Uuden asettelun määrittäminen vaihtelee vain sivun koon määrittämisen sekä visualisointien koon, sijainnin ja näkyvyyden hallinnan välillä.

Jos haluat määrittää mukautetun asettelun, määritä mukautetun asettelun objekti ja välitä se asetusten objektiin upotetussa kokoonpanossa. Määritä lisäksi LayoutType-arvoksi Mukautettu. Lisätietoja on artikkelissa [Kokoonpanotietojen upottaminen](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details).

```javascript
var embedConfig = {
    ...
    settings: {
            layoutType: models.LayoutType.Custom
    customLayout: {...}
    }
};
```

## <a name="object-definition"></a>Objektin määritelmät

```javascript
interface ICustomLayout {
  pageSize?: IPageSize;
  displayOption?: DisplayOption;
  pagesLayout?: PagesLayout;
}

enum PageSizeType {
  Widescreen,
  Standard,
  Cortana,
  Letter,
  Custom
}
interface IPageSize {
  type: PageSizeType;
}
interface ICustomPageSize extends IPageSize {
  width?: number;
  height?: number;
}

enum DisplayOption {
  FitToPage,
  FitToWidth,
  ActualSize
}
```

- `pageSize`: Hallitse piirtoalustan alueen kokoa (eli raportin valkoista aluetta) sivun koon avulla.
- `displayOptions`: Mahdollisia arvoja ovat FitToWidth, FitToPage tai ActualSize. Objekti määrittää sen, miten piirtoalusta skaalataan, jotta se sopii iframe-kehykseen.
- `pagesLayout`: Määrittää jokaisen visualisoinnin asettelun. lisätietoja on kohdassa PagesLayout.

## <a name="pages-layout"></a>Sivujen asettelu

Sivujen asettelun objektin määrittäminen tarkoittaa periaatteessa kunkin sivun asettelun määrittämistä. Visualisointien asettelut määritetään jokaisella sivulla.
PageLayout on valinnainen. Jos et määritä sivun asettelua, käytetään oletusasettelua (joka on tallennettu raporttiin).

PagesLayout on kartta sivulta, jonka nimi on PageLayout-objekti. Määritelmä:

```javascript
type PagesLayout = { [key: string]: IPageLayout; };
```

PageLayout sisältää visualisoinnin asettelun kartan, joka yhdistää jokaisen visualisoinnin nimen visualisoinnin asettelun objektiin:

```javascript
interface IPageLayout {
  visualsLayout: { [key: string]: IVisualLayout; };
}
```

## <a name="visual-layout"></a>Visualisoinnin asettelu

Voit määrittää visualisoinnin asettelun välittämällä uuden sijainnin ja koon sekä uuden näkyvyyden tilan.

```javascript
interface IVisualLayout {
  x?: number;
  y?: number;
  z?: number;
  width?: number;
  height?: number;
  displayState?: IVisualContainerDisplayState;
}

interface IVisualContainerDisplayState {
  mode: VisualContainerDisplayMode;
}

enum VisualContainerDisplayMode {
  Visible,
  Hidden
}
```

- `x,y,z`: Määrittää visualisoinnin uuden sijainnin.
- `width`, korkeus: Määrittää visualisoinnin uuden koon.
- `displayState`: Määrittää visualisoinnin näkyvyyden.


## <a name="update-layout"></a>Asettelun päivittäminen

Voit päivittää raportin asettelun updateSettings-menetelmän avulla milloin tahansa raportin latauksen aikana. Katso [Asetusten päivittäminen](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Update-Settings).

## <a name="code-example"></a>Esimerkkikoodi

```javascript
// Get models. models contains enums that can be used.
var models = window['powerbi-client'].models;
    
var embedConfiguration = {
    type: 'report',
    id: '5dac7a4a-4452-46b3-99f6-a25915e0fe55',
    embedUrl: 'https://app.powerbi.com/reportEmbed',
    tokenType: models.TokenType.Embed,
    accessToken: 'H4...rf',
    settings: {
            layoutType: models.LayoutType.Custom
        customLayout: {
            pageSize: {
                type: models.PageSizeType.Custom,
                width: 1600,
                height: 1200
            },
            displayOption: models.DisplayOption.ActualSize,
            pagesLayout: {
                "ReportSection1" : {
                    visualsLayout: {
                        "VisualContainer1": {
                            x: 1,
                            y: 1,
                            z: 1,
                            width: 400,
                            height: 300,
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Visible
                            }
                        },
                        "VisualContainer2": {
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Hidden
                            }
                        },
                    }
                }
            }
        }
    }
};
     
// Get a reference to the embedded report HTML element
var embedContainer = document.getElementById('embedContainer');
 
// Embed the report and display it within the div container.
var report = powerbi.embed(embedContainer, embedConfiguration);

```


## <a name="see-also"></a>Katso myös

[Power BI:n koontinäyttöjen, raporttien ja ruutujen upottaminen](embedding-content.md)   
[Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

