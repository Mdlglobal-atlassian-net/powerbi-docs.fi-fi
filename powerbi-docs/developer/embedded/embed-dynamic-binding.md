---
title: Raportin yhdistäminen tietojoukkoon dynaamisen sidonnan avulla
description: Lue tietoja siitä, miten voit upottaa raportin käyttäen dynaamista sidontaa.
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 11/07/2019
ms.openlocfilehash: e2c59ba84700aaf83c4cc9d16d009696c42dfc54
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80114585"
---
# <a name="connect-a-report-to-a-dataset-using-dynamic-binding"></a>Raportin yhdistäminen tietojoukkoon dynaamisen sidonnan avulla 

Kun raportti on yhdistetty tietojoukkoon, voit käyttää dynaamista sidontaa. Raportin ja tietojoukon välistä yhteyttä kutsutaan *sidonnaksi*. Kun sidonta määritetään upotuskohdassa sen sijaan, että se olisi esimääritetty aiemmin, sidontaa kutsutaan dynaamiseksi sidonnaksi.

Kun upotat Power BI -raportin käyttäen *dynaamista sidontaa*, voit yhdistää saman raportin eri tietojoukkoihin käyttäjän tunnistetietojen mukaan.

Tämä tarkoittaa, että voit käyttää yhtä raporttia eri tietojen näyttämiseen sen mukaan, mihin tietojoukkoon se on yhdistetty. Esimerkiksi raportti, joka näyttää jälleenmyynnin arvot, voidaan yhdistää eri jälleenmyyjätietojoukkoihin. Siten voidaan tuottaa eri tuloksia sen mukaan, mihin jälleenmyyjän tietojoukkoon se on yhdistetty.

Raportin ja tietojoukon ei tarvitse sijaita samassa työtilassa. Molemmat työtilat (raportin sisältävä ja tietojoukon sisältävä) on määritettävä [kapasiteetille](azure-pbie-create-capacity.md).

Varmista osana upottamista, että *luot tunnuksen, jolla on riittävät käyttöoikeudet*, ja *muokkaa määritysobjektia*.

## <a name="generating-a-token-with-sufficient-permissions"></a>Riittävät käyttöoikeudet sisältävän tunnuksen luominen

Dynaamista sidontaa tuetaan molemmissa upotustilanteissa: *upottaminen organisaation käyttöön* ja *upottaminen asiakkaiden käyttöön*. Alla olevassa taulukossa on kuvattu jokaisen skenaarion huomioon otettavat seikat.

|Skenaario  |Tietojen omistajuus  |Tunnus  |Vaatimukset  |
|---------|---------|---------|---------|
|*Upottaminen organisaation käyttöön*    |Käyttäjä omistaa tiedot         |Power BI -käyttäjien käyttöoikeustietue         |Käyttäjällä, jonka Azure AD -tunnusta käytetään, on oltava asianmukaiset käyttöoikeudet kaikkiin artefakteihin.         |
|*Upottaminen asiakkaiden käyttöön*     |Sovellus omistaa tiedot         |Muiden kuin Power BI -käyttäjien käyttöoikeustietue         |Tulee sisältää käyttöoikeudet sekä raportille että dynaamisesti sidotulle tietojoukolle. Käytä [useiden kohteiden upotustunnuksen luontiin tarkoitettua ohjelmointirajapintaa,](embed-sample-for-customers.md#multiEmbedToken), jos haluat luoda upotustunnuksen, joka tukee useita artefakteja.         |

## <a name="adjusting-the-config-object"></a>Määritysobjektin säätäminen
Lisää `datasetBinding` määritysobjektiin. Käytä alla olevaa esimerkkiä viitteenä.

```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    // -----  Adjustment required for dynamic binding ---- //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // ---- End of dynamic binding adjustment ---- //
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```

## <a name="next-steps"></a>Seuraavat vaiheet

Jos et ole ennen käyttänyt upottamista Power BI:ssä, tutustu näihin opetusohjelmiin, joissa kerrotaan, miten voit upottaa Power BI -sisältösi:
* [Opetusohjelma: Power BI -sisällön upottaminen sovellukseen asiakkaiden käyttöön](embed-sample-for-customers.md)
* [Opetusohjelma: Power BI -sisällön upottaminen sovellukseen organisaatiolle](embed-sample-for-your-organization.md)