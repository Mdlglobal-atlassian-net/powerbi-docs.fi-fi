---
title: 'DAX: sarake- ja mittariviittaukset'
description: Ohjeita sarakkeisiin ja mittareihin viittaamiseksi DAX-lausekkeissa.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/18/2019
ms.author: v-pemyer
ms.openlocfilehash: 42d99c7139586a78565198b59bc74716261537e0
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279614"
---
# <a name="dax-column-and-measure-references"></a>DAX: sarake- ja mittariviittaukset

Tietojen mallintajana joudut tekemään DAX-lausekkeita, joissa viitataan mallin sarakkeisiin ja mittareihin. Sarakkeet ja mittarit liittyvät molemmat aina mallitaulukoihin, mutta niitä ei liitetä samalla tavalla. Seuraavassa esitetään niille kummallekin omat suosituksensa, miten niihin kannattaa viitata lausekkeissa.

## <a name="columns"></a>Sarakkeet

Sarake on taulukkotason objekti, ja sarakkeiden nimien on oltava yksilöllisiä saman taulukon sisällä. On siis mahdollista käyttää samaa sarakkeen nimeä useita kertoja samassa mallissa, kunhan ne vain kuuluvat eri taulukoihin. Toinen muistettava sääntö on, ettei sarakkeella saa olla sama nimi kuin samassa taulukossa olevalla mittarilla tai hierarkialla.

DAX ei yleensä pakota käyttämään _täydellistä_ viittausta sarakkeeseen. Täydellinen viittaus tarkoittaa, että sarakkeen nimen edessä on taulukon nimi.

Alla on esimerkki lasketun sarakkeen määrittämisestä käyttäen vain viittauksia sarakkeiden nimiin. **Sales**- ja **Cost**-sarakkeet kuuluvat samaan taulukkoon, jonka nimi on **Orders**.

```dax
Profit = [Sales] - [Cost]
```

Sama määritelmä voidaan kirjoittaa myös käyttämällä täydellisiä viittauksia sarakkeisiin.

```dax
Profit = Orders[Sales] - Orders[Cost]
```

Joskus on kuitenkin käytettävä täydellisiä viittauksia sarakkeisiin, jos Power BI havaitsee monitulkintaisuuden. Tällöin saat kaavan kirjoittamisen aikana virheilmoituksen, ja punainen aaltoviiva merkitsee ongelmakohdan. Lisäksi jotkin DAX-funktiot, kuten [LOOKUPVALUE](/dax/lookupvalue-function-dax)-DAX-funktio, edellyttävät täydellisten sarakkeiden käyttämistä.

Suosittelemme käyttämään aina täydellisiä viittauksia sarakkeisiin. Perustelut annetaan kohdassa [Suositukset](#recommendations).

## <a name="measures"></a>Mittarit

Mittari on mallitason objekti. Sen vuoksi mittarien nimien on oltava yksilöllisiä saman mallin sisällä. Raportin tekijät näkevät kuitenkin **Kentät**-ruudussa mittarit niin, että kuhunkin mittariin liittyy yksi mallitaulukko. Tämä yhdistely on tehty kosmeettisista syistä, ja voit muuttaa sitä määrittämällä mittarille **Aloitustaulukko**-ominaisuuden. Lisätietoja saat kohdasta [Mittarit Power BI Desktopissa (Mittarien järjestäminen)](../transform-model/desktop-measures.md#organizing-your-measures).

Lausekkeissa on mahdollista käyttää täydellisiä viittauksia mittareihin. DAX intellisense tarjoaa niistä jopa ehdotuksia. Se ei kuitenkaan ole tarpeen eikä suositeltu käytäntö. Jos päätätkin myöhemmin muuttaa mittarin aloitustaulukkoa, täydellisiä mittariviittauksia käyttävät lausekkeet hajoavat. Sitten sinun on muokattava erikseen kutakin rikkoutunutta kaavaa poistaaksesi (tai korjataksesi) mittariviittaukset.

Suosittelemme, että et koskaan käytä täydellisiä viittauksia mittareihin. Perustelut annetaan kohdassa [Suositukset](#recommendations).

## <a name="recommendations"></a>Suositukset

Suosituksemme ovat yksinkertaisia ja helppoja muistaa:

- Käytä aina täydellisiä viittauksia sarakkeisiin.
- Älä koskaan käytä täydellisiä viittauksia mittareihin.

Perustelut:

- **Kaavan kirjoittaminen**: Lausekkeet hyväksytään, sillä niissä ei ole monitulkintaisia viittauksia, jotka pitäisi ratkaista. Samalla täytät vaatimukset sellaisten DAX-funktioiden osalta, jotka edellyttävät täydellisiä sarakeviittauksia.
- **Kestävyys**: Lausekkeet toimivat edelleen, vaikka muuttaisit mittarin Aloitustaulukko-ominaisuutta.
- **Luettavuus**: Lausekkeet ovat nopeita ja helppoja ymmärtää – tunnistat nopeasti, onko kyseessä sarake vai mittari sen perusteella, onko viittaus täydellinen.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Data Analysis Expressions (DAX) -viittaukset](/dax/)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

