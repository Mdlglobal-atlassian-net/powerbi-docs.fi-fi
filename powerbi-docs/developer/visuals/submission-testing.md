---
title: Power BI -visualisoinnin lähetyksen testaaminen
description: Tässä artikkelissa kuvataan testitapauksia, jotka visualisointisi on läpäistävä ennen julkaisemista Appsourceen. Käytettävissä on myös valinnaisia testitapauksia.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 04/15/2020
ms.openlocfilehash: 65e00fa5311ea12c9fe0011c6aa7c3e779f33dc5
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83131126"
---
# <a name="submission-testing-of-a-power-bi-visual"></a>Power BI -visualisoinnin lähetyksen testaaminen

Ennen kuin julkaiset visualisointisi [AppSourceen](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals), sen on läpäistävä nämä testitapaukset. Testaa visualisointisi ennen sen lähettämistä. Jos visualisointi ei läpäise vaadittuja testitapauksia, se hylätään.

Jos haluat lisätietoja julkaisuprosessista, katso [Power BI -visualisointien julkaiseminen Kumppanikeskukseen](./office-store.md).

## <a name="general-test-cases"></a>Yleiset testitapaukset

| Testitapaus | Odotetut tulokset
| --------- | ----------------
| Luo **Pinottu pylväskaavio**, jossa on **Luokka** ja **Arvo**. Muunna se visualisoinniksesi ja sitten takaisin pylväskaavioksi. | Näiden muunnosten jälkeen ei näy virheitä. |
| Luo **Mittari** kolmella mittayksiköllä. Muunna se visualisoinniksesi ja sitten takaisin **Mittariksi**. | Näiden muunnosten jälkeen ei näy virheitä. |
| Tee valintoja visualisoinnissasi. | Valinnat näkyvät muissa visualisoinneissa. |
| Valitse elementtejä muissa visualisoinneissa. | Visualisoinnissasi näkyy suodatettuja tietoja sen mukaan, mitä muissa visualisoinneissa on valittu. |
| Tarkista **dataViewMappings**-ehtojen minimi ja maksimi. | Säilöt voivat hyväksyä useita kenttiä tai yhden kentän, tai muut säilöt voivat määrittää ne. **DataViewMapping**-ehtojen minimi ja maksimi on määritettävä oikein visualisointisi ominaisuuksissa. |
| Poista kaikki kentät eri järjestyksissä. | Visualisointi tyhjentää oikein, koska kentät poistetaan mielivaltaisessa järjestyksessä. Konsolissa tai selaimessa ei ole virheitä. |
| Avaa kaikkien mahdollisten säilömääritysten **Muoto**-ruutu. | Tämä testi ei käynnistä tyhjäarvoviittaus-poikkeuksia. |
| Suodata tiedot käyttämällä **Suodatin**-ruutua visualisointi-, sivu- ja raporttitasolla. | Työkaluvihjeet ovat oikeat suodattimien käytön jälkeen. Työkaluvihjeet näyttävät suodatetun arvon. |
| Suodata tiedot **Osittajan** avulla. | Työkaluvihjeet ovat oikeat suodattimien käytön jälkeen. Työkaluvihjeet näyttävät suodatetun arvon. |
| Suodata tiedot julkaistun visualisoinnin avulla. Valitse esimerkiksi ympyräkaavion sektori tai sarake. | Työkaluvihjeet ovat oikeat suodattimien käytön jälkeen. Työkaluvihjeet näyttävät suodatetun arvon. |
| Jos ristiinsuodatusta tuetaan, tarkista, että suodattimet toimivat oikein. | Käytössä oleva valinta suodattaa muut visualisoinnit raportin tällä sivulla. |
| Valitse Ctrl-, Alt- ja vaihtonäppäimillä. | Odottamattomia toimintoja ei ilmene. |
| Muuta **Näyttötila**-asetukseksi **Todellinen koko**, **Sovita sivulle** ja **Sovita leveyteen**. | Hiiren koordinaatit ovat tarkkoja. |
| Muuta visualisointisi kokoa. | Visualisointi reagoi oikein koon muuttamiseen. |
| Määritä raportin koko vähimmäisarvoon. | Näyttövirheitä ei ole. |
| Varmista, että vierityspalkit toimivat oikein. | Vierityspalkkien on oltava olemassa tarvittaessa. Tarkista vierityspalkkien koko. Vierityspalkit eivät saa olla liian leveitä tai pitkiä. Vierityspalkkien sijainnin ja koon on oltava sopusoinnussa visualisoinnin muiden elementtien kanssa. Varmista, että vierityspalkit tarvitaan visualisoinnin eri kokoja varten. |
| Kiinnitä visualisointisi **koontinäyttöön**. | Visualisoinnin pitäisi näkyä oikein. |
| Lisää useita visualisointisi versioita yhteen raportti sivuun. | Kaikki visualisoinnin versiot näkyvät ja toimivat oikein. |
| Lisää useita visualisointisi versioita useisiin raporttisivuihin. | Kaikki visualisoinnin versiot näkyvät ja toimivat oikein. |
| Siirry raporttisivulta toiselle. | Visualisointi näkyy oikein. |
| Testaa visualisointisi luku- ja muokkausnäkymiä. | Kaikki toiminnot toimivat oikein. |
| Jos visualisointiisi sisältyy animaatioita, lisää, muuta ja poista visualisoinnin elementtejä. | Visuaalisten elementtien animaatio toimii oikein. |
| Avaa **Ominaisuus**-ruutu. Ota ominaisuudet käyttöön ja poista ne käytöstä, kirjoita mukautettua tekstiä, painota käytettävissä olevia vaihtoehtoja ja anna virheellisiä tietoja. | Visualisointi reagoi oikein. |
| Tallenna raportti ja avaa se uudelleen. | Kaikki ominaisuuksien asetukset säilyvät. |
| Siirry raportissa toiselle sivulle ja siirry sitten takaisin. | Kaikki ominaisuuksien asetukset säilyvät. |
| Testaa visualisoinnin kaikki toiminnot, mukaan lukien visualisoinnin sisältämät eri vaihtoehdot. | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| Testaa kaikki luku-, päivämäärä- ja merkkitietotyypit, kuten seuraavissa testeissä. | Kaikki tiedot on muotoiltu oikein. |
| Tarkista muotoiltujen työkaluvihjeiden arvojen, akselien otsikoiden, arvopisteiden otsikoiden ja muiden visualisoinnin elementtien muotoilu. | Kaikki elementit on muotoiltu oikein. |
| Varmista, että arvopisteet käyttävät muotoilumerkkijonoa. | Kaikki arvopisteiden otsikot on muotoiltu oikein. |
| Ota työkaluvihjeiden lukuarvojen automaattinen muotoilu käyttöön tai pois käytöstä. | Arvot näkyvät oikein työkaluvihjeissä. |
| Testaa tietomerkinnät, joissa on erityyppisiä tietoja, kuten lukuja, tekstiä, päivämäärä ja aika sekä erilaisia muotoilumerkkijonoja mallista. Testaa eri tietomääriä, kuten tuhansia rivejä, yksi rivi ja kaksi riviä. | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| Anna visualisoinnille virheellisiä tietoja, kuten tyhjiä arvoja, ääretön arvo, negatiivisia arvoja ja vääriä arvotyyppejä. | Kaikki näytöt ja ominaisuudet toimivat oikein. |

## <a name="optional-browser-testing"></a>Valinnainen selaintestaus

AppSource-ryhmä tarkistaa visualisoinnin Google Chrome-, Microsoft Edge- ja Mozilla Firefox -selainten nykyisissä Windows-versioissa.
Voit vaihtoehtoisesti testata visualisointisi seuraavissa selaimissa.

| Testitapaus | Odotetut tulokset
| --------- | ----------------
| **Windows** |
| Google Chrome (aiempi versio) | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| Mozilla Firefox (aiempi versio) | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| Microsoft Edge (aiempi versio) | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| Microsoft Internet Explorer 11 (valinnainen) | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| **macOS** |
| Chrome (aiempi versio) | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| Firefox (aiempi versio) | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| Safari (aiempi versio) | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| **Linux** |
| Firefox (uusin ja aiemmat versiot) | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| **Mobiili iOS** |
| Apple Safari iPad (aiempi Safari-versio) | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| Chrome iPad (uusin Safari-versio) | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| **Mobiili Android** |
| Chrome (uusin ja aiemmat versiot) | Kaikki näytöt ja ominaisuudet toimivat oikein. |

## <a name="desktop-testing"></a>Työpöytätestaus

Testaa visualisointiasi [Power BI Desktopin](https://powerbi.microsoft.com/en-us/desktop/) nykyisessä versiossa.

| Testitapaus | Odotetut tulokset
| --------- | ----------------
| Testaa visualisointisi kaikkia ominaisuuksia. | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| Tuo, tallenna, avaa tiedosto ja julkaise Power BI -verkkopalveluun käyttämällä **Julkaise**-painiketta Power BI Desktopissa. | Kaikki näytöt ja ominaisuudet toimivat oikein. |
| Muuta numeerista muotoilumerkkijonoa niin, että desimaaleja ei ole lainkaan tai desimaaleja on kolme, lisäämällä tai vähentämällä tarkkuutta. | Visualisointi näkyy oikein. |

## <a name="performance-testing"></a>Suorituskykytestaus

Visualisointisi suosituskyvyn tulee olla hyväksyttävällä tasolla. Tarkista suorituskyky kehittäjätyökalujen avulla. Älä luota vain visuaalisien vihjeisiin ja konsolin aikalokeihin.

| Testitapaus | Odotetut tulokset
| --------- | ----------------
| Luo visualisointi, jossa on monia visuaalisia elementtejä. | Visualisoinnin suorituskyvyn tulisi olla hyvä, eikä se saa jumiuttaa sovellusta. Suorituskykyongelmia ei saa olla esimerkiksi animaation nopeudessa, koon muuttamisessa, suodatuksessa eikä ja valitsemisessa.

## <a name="next-steps"></a>Seuraavat vaiheet

Jos haluat lisätietoja julkaisuprosessista, katso [Power BI -visualisointien julkaiseminen Kumppanikeskukseen](./office-store.md).

Onko sinulla kysyttävää? [Kysy Power BI -yhteisössä](https://community.powerbi.com/).
