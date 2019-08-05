---
title: URL:n käynnistäminen
description: Power BI:n visualisoinnit voivat avata URL-osoitteen uudessa välilehdessä
author: Guy-Moses
ms.author: guymos
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 1a7002c3b45f341c0cbc0db683bc4f8a113e21f9
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424857"
---
# <a name="launch-url"></a>URL:n käynnistäminen

URL:n käynnistäminen sallii uuden selainvälilehden (tai ikkunan) avaamisen siirtämällä todellisen työn Power BI:hin.

## <a name="sample"></a>Malli

```typescript
   this.host.launchUrl('https://powerbi.microsoft.com');
```

## <a name="usage"></a>Käyttö

Käytä `host.launchUrl()`-ohjelmointirajapinnan kutsua ja välitä kohde-URL merkkijonoargumenttina:

```typescript
this.host.launchUrl('http://some.link.net');
```

## <a name="restrictions"></a>Rajoitukset

* Käytä vain absoluuttisia polkuja, älä suhteellisia. `http://some.link.net/subfolder/page.html` sopii hyvin, polkua `/page.html` ei avata.
* Vain `http`- ja `https`-protokollia tuetaan tällä hetkellä. Vältä protokollia `ftp`, `mailto` ja niin edelleen.

## <a name="best-practices"></a>Parhaat käytännöt

1. Useimmissa tapauksissa linkki on parasta avata vain silloin, kun käyttäjä nimenomaan niin haluaa. Varmista, että käyttäjän on helppo ymmärtää, että linkin tai painikkeen napsauttaminen aiheuttaa uuden välilehden avaamisen. `launchUrl()`-kutsun käynnistäminen ilman käyttäjän toimia tai muun toiminnon sivuvaikutuksena voi olla käyttäjälle hämmentävää tai turhauttavaa.
2. Jos linkki ei ole ratkaiseva visualisoinnin moitteettoman toiminnan kannalta, on suositeltavaa antaa raportin tekijälle tapa poistaa linkki käytöstä ja piilottaa se. Tämä on erityisen tärkeää Power BI:n erityiskäyttötavoissa, kuten raportin upottamisessa kolmannen osapuolen sovellukseen tai raportin julkaisemisessa verkossa.
3. Vältä käynnistämästä `launchUrl()`-kutsua silmukan sisältä, visualisoinnin `update`-toiminnosta tai mistä tahansa muusta usein toistuvasta koodista.

## <a name="step-by-step-example"></a>Esimerkki askel askeleelta

### <a name="adding-a-link-launching-element"></a>Linkin käynnistävän elementin lisääminen

Seuraavat rivit lisättiin visualisoinnin `constructor`-toimintoon:

```typescript
    this.helpLinkElement = this.createHelpLinkElement();
    options.element.appendChild(this.helpLinkElement);
```

Lisäksi lisättiin yksityinen funktio, joka luo ja liittää ankkuri-elementin:

```typescript
private createHelpLinkElement(): Element {
    let linkElement = document.createElement("a");
    linkElement.textContent = "?";
    linkElement.setAttribute("title", "Open documentation");
    linkElement.setAttribute("class", "helpLink");
    linkElement.addEventListener("click", () => {
        this.host.launchUrl("https://docs.microsoft.com/power-bi/developer/custom-visual-develop-tutorial");
    });
    return linkElement;
};
```

Lopuksi visual.less-tiedoston merkintä määrittää linkkielementin tyylin:

```less
.helpLink {
    position: absolute;
    top: 0px;
    right: 12px;
    display: block;
    width: 20px;
    height: 20px;
    border: 2px solid #80B0E0;
    border-radius: 20px;
    color: #80B0E0;
    text-align: center;
    font-size: 16px;
    line-height: 20px;
    background-color: #FFFFFF;
    transition: all 900ms ease;

    &:hover {
        background-color: #DDEEFF;
        color: #5080B0;
        border-color: #5080B0;
        transition: all 250ms ease;
    }

    &.hidden {
        display: none;
    }
}
```

### <a name="adding-a-toggling-mechanism"></a>Vaihtomekanismin lisääminen

Tämä edellyttää staattisen objektin lisäämistä (katso [opetus ohjelma staattisista objekteista](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties)), jotta raportin tekijä voi näyttää tai piilottaa linkkielementin (elementti on oletusarvoisesti piilotettu).
Staattinen `showHelpLink`-totuusarvo-objekti lisättiin `capabilities.json`-objektimerkintään:

```typescript
"objects": {
    "generalView": {
            "displayName": "General View",
            "properties":
                "showHelpLink": {
                    "displayName": "Show Help Button",
                    "type": {
                        "bool": true
                    }
                }
            }
        }
    }
```

![URL:n vaihdon käynnistäminen](./media/launchurl-toggle.png)

Seuraavat rivit lisättiin visualisoinnin `update`-funktioon:

```typescript
if (settings.generalView.showHelpLink) {
    this.helpLinkElement.classList.remove("hidden");
} else {
    this.helpLinkElement.classList.add("hidden");
}
```

Elementin näyttämistä hallitseva `hidden`-luokka on määritetty visual.less-tiedostossa.
