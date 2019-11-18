---
title: Dynaaminen sidonta
description: Lue tietoja siitä, miten voit upottaa raportin käyttäen dynaamista sidontaa.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 09/25/2019
ms.openlocfilehash: 8b42b397f726e492eda80a99eb730c215eb17ccb
ms.sourcegitcommit: 23ad768020a9daf129f69a462a2d46d59d2349d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/22/2019
ms.locfileid: "72776233"
---
# <a name="dynamic-binding"></a>Dynaaminen sidonta

Dynaamista sidontaa voidaan käyttää myös tietojoukon dynaamiseen valitsemiseen raportin upottamisen aikana. Raportin ja tietojoukon ei tarvitse sijaita samassa työtilassa. Loppukäyttäjät näkevät eri tuloksia valitun tietojoukon mukaan.

Molemmat työtilat (raportin sisältävä ja tietojoukon sisältävä) on määritettävä kapasiteetille.

Raportin upottaminen dynaamisen sidonnan avulla sisältää kaksi vaihetta:
1. tunnuksen luominen
2. määritysobjektin säätäminen

## <a name="generating-a-token"></a>Tunnuksen luominen
Luo tunnus käyttämällä [ohjelmointirajapintaa, joka on tarkoitettu useiden kohteiden upotustunnuksen luontiin](embed-sample-for-customers.md#multiEmbedToken).

Dynaamista sidontaa tuetaan molemmissa upotustilanteissa: *upottaminen organisaation käyttöön* ja *upottaminen asiakkaiden käyttöön*.

| Ratkaisu                   | Tunnus                               | Vaatimukset                                                                                                                                                  |
|---------------------------------|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *Upottaminen organisaation käyttöön* | Power BI -käyttäjien käyttöoikeustietue     | Käyttäjällä, jonka Azure AD -tunnusta käytetään, on oltava asianmukaiset käyttöoikeudet kaikkiin artefakteihin.                                                                    |
| *Upottaminen asiakkaiden käyttöön*    | Muiden kuin Power BI -käyttäjien käyttöoikeustietue | Tulee sisältää käyttöoikeudet sekä raportille että dynaamisesti sidotulle tietojoukolle. Luo uuden ohjelmointirajapinnan avulla upotettava tunnus, joka tukee useita artefakteja. |

## <a name="adjusting-the-config-object"></a>Määritysobjektin säätäminen
Lisää `datasetBinding` määritysobjektiin. Käytä sivun alaosassa olevaa esimerkkiä viitteenä.

Jos et ole ennen käyttänyt upottamista Power BI:ssä, tutustu näihin opetusohjelmiin, joissa kerrotaan, miten voit upottaa Power BI -sisältösi:
* [Power BI -sisällön upottaminen sovellukseen asiakkaille](embed-sample-for-customers.md)
* [Opetusohjelma: Power BI -sisällön upottaminen sovellukseen organisaatiolle](embed-sample-for-your-organization.md)

 ### <a name="example"></a>Esimerkki
```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    /////////////////////////////////////////////
    // Adjustment required for dynamic binding //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // End of dynamic binding adjustment            //
    /////////////////////////////////////////////
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```