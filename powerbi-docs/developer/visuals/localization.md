---
title: Power BI -visualisointien tietonäkymän yhdistämismääritykset
description: Tässä artikkelissa kerrotaan, miten Power BI muuntaa tiedot ennen niiden välittämistä visualisointeihin.
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 85cfa292055f7db96dcb714ec8c4dd78fe75ee67
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700290"
---
# <a name="add-the-locale-in-power-bi-for-custom-visuals"></a>Alueen lisääminen Power BI:n mukautetuille visualisoinneille

Visualisoinnit voivat noutaa Power BI:n aluekohtaiset asetukset sisällön lokalisoimiseksi kyseiselle kielelle.

Lue lisää kohdasta [Power BI:n tuetut kielet ja maat tai alueet](./../../supported-languages-countries-regions.md)

Esimerkiksi kieliasetuksen hakeminen mallipalkkikaavion visualisoinnissa.

![Mallipalkkikaavion visualisoinnin lokalisointi](media/locale-in-samplebarchart.png)

Jokainen näistä palkkikaavioista luotiin eri kieliasetuksen (englanti, baski ja hindi) alle, ja ne näytetään työkaluvihjeessä.

> [!NOTE]
> Visualisoinnin koodin lokalisoinnin hallintaa tuetaan ohjelmointirajapinnasta 1.10.0 ja uudemmista.

## <a name="get-the-locale"></a>Hae aluekohtaiset asetukset

`locale` välitetään merkkijonona visualisoinnin alustuksen aikana. Jos aluekohtaisia asetuksia muutetaan Power BI:ssa, visualisointi luodaan uudelleen käyttäen uusia aluekohtaisia asetuksia. Koko mallikoodi on SampleBarChart with Localessa

Barchart-konstruktorilla on nyt Aluekohtaiset asetukset -jäsen, joka on muodostettu konstruktorilla, jolla on aluekohtaiset asetukset -isäntäesiintymä.

```typescript
private locale: string;
...
this.locale = options.host.locale;
```

Tuetut kieliasetukset:

Aluekohtaiset merkkijonot | Kieli
--------------|----------------------
ar-SA | العربية (arabia)
bg-BG | български (bulgaria)
ca-ES | català (katalaani)
cs-CZ | čeština (tsekki)
da-DK | dansk (tanska)
de-DE | Deutsche (saksa)
el-GR | ελληνικά (kreikka)
en-US | English (englanti)
es-ES | español service (espanja)
et-EE | eesti (viro)
eU-ES | Euskal (baski)
fi-FI | suomi (suomi)
fr-FR | Français (ranska)
gl-ES | galego (galicia)
he-IL | עברית (heprea)
hi-IN | हिन्दी (hindi)
hr-HR | hrvatski (kroatia)
hu-HU | magyar (unkari )
id-ID | Bahasa Indonesia (indonesia)
it-IT | italiano (italia)
ja-JP | 日本の (japani)
kk-KZ | Қазақ (kazakki)
ko-KR | 한국의 (korea)
lt-LT | Lietuvos (liettua)
lv-LV | Latvijas (latvia)
ms-MY | Bahasa Melayu (malaiji)
nb-NO | norsk (norja)
nl-NL | Nederlands (hollanti)
pl-PL | polski (puola)
pt-BR | português (portugali)
pt-PT | português (portugali)
ro-RO | românesc (romania)
ru-RU | русский (venäjä)
sk-SK | slovenský (slovakki)
sl-SI | slovenski (sloveeni)
sr-Cyrl-RS | cрпски (serbia)
sr-Latn-RS | srpski (serbia)
sv-SE | svenska (ruotsi)
th-TH | ไทย (thai)
tr-TR | türk (turkki)
uk-UA | український (ukraina)
vi-VN | tiếng Việt (vietnam)
zh-CN | 中国 (kiina, yksinkertaistettu)
zh-TW | 中國 (kiina, perinteinen)

> [!NOTE]
> PowerBI Desktopissa aluekohtaiset asetukset -ominaisuus sisältää asennetun PowerBI Desktopin kielen.

## <a name="localizing-the-property-pane-for-custom-visuals"></a>Mukautettujen visualisointien ominaisuusruudun lokalisointi

Ominaisuusruudun kentät voidaan lokalisoida entistä yhtenäisemmän ja yhdenmukaisemman käyttökokemuksen tarjoamiseksi. Se tekee mukautetusta visualisoinnista samankaltaista kuin mikä tahansa muu Power BI -ydinvisualisointi.

Esimerkiksi `pbiviz new`-komennolla luodun mukautetun visualisoinnin, jota ei voi lokalisoida, ominaisuusruudussa näkyvät seuraavat kentät:

![Lokalisointiominaisuus ruudussa](media/property-pane.png)

sekä luokkatiedot että mittaritiedot on määritetty capabilities.json -tiedostossa muodossa `displayName`.

## <a name="how-to-localize-capabilities"></a>Kuinka ominaisuuksia lokalisoidaan

Lisää ensin näyttönimiavain jokaiseen näyttönimeen, jonka haluat lokalisoida ominaisuuksiisi. Tässä esimerkissä:

```json
{
    "dataRoles": [
        {
            "displayName": "Category Data",
            "displayNameKey": "VisualCategoryDataNameKey1",
            "name": "category",
            "kind": "Grouping"
        },
        {
            "displayName": "Measure Data",
            "displayNameKey": "VisualMeasureDataNameKey2",
            "name": "measure",
            "kind": "Measure"
        }
    ]
}
```

Lisää sitten hakemisto nimeltä stringResources. Hakemisto sisältää kaikki eri merkkijonojen resurssitiedostot niiden aluekohtaisten asetusten perusteella, joita haluat visualisoinnin tukevan. Tämän hakemiston alla sinun on lisättävä JSON-tiedosto jokaiselle alueellesi, jota haluat tukea. Nämä tiedostot sisältävät aluekohtaisia tietoja ja lokalisoituja merkkijonoarvoja kullekin korvattavalle displayNameKey-kohteelle.

Tässä esimerkissä sanotaan, että haluamme tukea arabiaa ja hepreaa. Meidän on lisättävä kaksi JSON-tiedostoa seuraavalla tavalla:

![Kieliresurssikansion lokalisointien merkkijonot](media/stringresources-files.png)

Jokainen JSON-tiedosto määrittää yksittäisen kieliasetuksen (tämän tiedoston on oltava jokin yllä olevasta tuetuista alueista) käyttäen haluamiesi näyttönimiavainten merkkijonoarvoja. Tässä esimerkissä hepreankielinen merkkijonoresurssitiedosto näyttää seuraavalta:

```json
{
    "locale": "he-IL",
    "values": {
        "VisualCategoryDataNameKey1": "קטגוריה",
        "VisualMeasureDataNameKey2": "יחידות מידה"
    }
}
```

Kaikki lokalisointipäällikön käyttöön tarvittavat vaiheet on kuvattu alla.

> [!NOTE]
> Lokalisointia ei tueta tällä hetkellä dev-visualisoinnin virheen korjauksessa

## <a name="setup-environment"></a>Asetusympäristö

### <a name="desktop"></a>Työpöytä

Lataa työpöytäkäyttöön Power BI Desktopin lokalisoitu versio osoitteesta https://powerbi.microsoft.com.

### <a name="web-service"></a>Verkkopalvelu

Jos käytät verkkoasiakasta (selainta) palvelussa, vaihda kieli asetuksissa:

![Lokalisointi verkkopalvelussa](media/webservice-settings.png)

## <a name="resource-file"></a>Resurssitiedosto

Lisää resources. resjson-tiedosto kansioon, joka on nimetty sen alueen mukaan, jota aiot käyttää stringResources-kansion sisällä. Esimerkkinä mainittakoon en-US ja ru-RU.

![Uusi resjson-tiedosto](media/new-resjson.png)

Lisää sen jälkeen kaikki lokalisointimerkkijonot, joita aiot käyttää edellisessä vaiheessa lisäämässäsi resources.resjson-tiedostossa.

```json
{
    ...
    "Role_Legend": "Обозначения",
    "Role_task": "Задача",
    "Role_StartDate": "Дата начала",
    "Role_Duration": "Длительность"
    ...
}
```

Tämä malli on resources.resjson-tiedoston en-US-versio:

```json
{
    ...
    "Role_Legend": "Legend",
    "Role_task": "Task",
    "Role_StartDate": "Start date",
    "Role_Duration": "Duration"
    ...
}
```

Uusi localizationManager-esiintymä luo localizationmanager-esiintymän visualisoinnin koodissa seuraavasti

```typescript
private localizationManager: ILocalizationManager;

constructor(options: VisualConstructorOptions) {
    this.localizationManager = options.host.createLocalizationManager();
}
```

## <a name="localizationmanager-usage-sample"></a>localizationManager-käyttömalli

Nyt voit kutsua lokalisointihallinnan getDisplayName-funktiota käyttäen resources. resjson-kohteessa määritettyä merkkijonoavainargumenttia, jotta saat tarvittavan merkkijonon minne tahansa koodisi sisällä:

```typescript
let legend: string = this.localization.getDisplayName("Role_Legend");
```

Se palauttaa "Legend" kielelle en-US ja "Обозначения" kielelle ru-RU

## <a name="next-steps"></a>Seuraavat vaiheet

* [Lue, miten voit käyttää muotoilun apuohjelmia lokalisoitujen muotoilujen tarjoamiseen](utils-formatting.md)
