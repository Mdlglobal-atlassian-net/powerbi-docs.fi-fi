---
title: Sivutettujen raporttien kuvien käytön ohjeet
description: Ohjeita kuvien käyttämiseen Power BI:n sivutetuissa raporteissa.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 02/16/2020
ms.author: v-pemyer
ms.openlocfilehash: d2f3f36911c72df1b95ceb5bd90043870559cc62
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "78920718"
---
# <a name="image-use-guidance-for-paginated-reports"></a>Sivutettujen raporttien kuvien käytön ohjeet

Tämä artikkeli koskee raportin laatijaa, joka suunnittelee Power BI:n [sivutettuja raportteja](../paginated-reports/paginated-reports-report-builder-power-bi.md). Se sisältää ehdotuksia kuvien käsittelyyn. Yleensä raportin asetteluissa olevat kuvat voivat näyttää grafiikkaa, kuten yrityksen logon, tai valokuvia.

Kuvia voidaan tallentaa kolmeen eri sijaintiin:

- Raporttiin (upotettuna)
- WWW-palvelimelle
- Tietokantaan, joka voidaan noutaa tietojoukon mukaan

Niitä voidaan käyttää erilaisissa skenaarioissa raportin asetteluissa:

- Erillinen logo tai kuva
- Tietoriveihin liittyvät kuvat
- Tiettyjen raporttikohteiden tausta:
  - Raportin leipäteksti
  - Tekstiruutu
  - Suorakulmio
  - Tablix-tietoalue (taulukko, matriisi tai luettelo)

## <a name="suggestions"></a>Ehdotukset

Tutustu seuraaviin ehdotuksiin, joiden avulla voit laatia ammattimaisia raportin asetteluja, helpottaa ylläpitoa ja optimoida raportin suorituskyvyn:

- **Käytä pienintä mahdollista kokoa**: Suosittelemme valmistelemaan kuvia, jotka ovat pieniä mutta näyttävät silti teräviltä ja selkeiltä. Kyse on laadun ja koon tasapainosta. Harkitse grafiikkaeditorin (kuten MS Paint) käyttämistä kuvan tiedostokoon pienentämiseksi.
- **Vältä upotettuja kuvia**: Upotetut kuvat voivat paisuttaa raportin tiedostokokoa, mikä voi hidastaa raportin hahmontamista. Upotetuista kuvista voi myös tulla nopeasti ylläpidon painajainen, jos sinun täytyy päivittää monta raportin kuvaa (kuten voi käydä, jos yrityksesi logo muuttuu).
- **Käytä tallennusta WWW-palvelimelle**: Kuvien tallentaminen WWW-palvelimelle on hyvä vaihtoehto erityisesti yrityksen logolle, joka saattaa olla peräisin yrityksen sivustolta. Ole kuitenkin tarkkana, jos raporttisi käyttäjät käyttävät raportteja verkkosi ulkopuolelta. Varmista tällöin, että kuvat ovat käytettävissä Internetissä.

    Kun kuvat liittyvät tietoihisi (kuten myyjien valokuvat), nimeä kuvatiedostot niin, että raporttilauseke voi tuottaa kuvan URL-polun dynaamisesti. Voit esimerkiksi nimetä myyjien kuvat käyttämällä kunkin myyjän työntekijänumeroa. Jos raportin tietojoukko hakee työntekijänumeron, voit kirjoittaa lausekkeen, joka tuottaa koko kuvan URL-polun.
- **Käytä tietokantasäilöä**: Kun kuvatietoja on tallennettu relaatiotietokantaan, on järkevää hakea kuvatiedot suoraan tietokantataulukoista, etenkin silloin, kun kuvat eivät ole liian suuria.
- **Asianmukaiset taustakuvat**: Jos päätät käyttää taustakuvia, huolehdi siitä, etteivät ne vie raportin käyttäjän huomiota raportin tiedoista. 

    Muista myös käyttää _vesileimakuvia_. Yleensä vesileimakuvissa on läpinäkyvä tausta (tai sama taustaväri kuin raportissa). Niissä käytetään myös vaaleita värejä. Yleisiä esimerkkejä vesileimakuvista ovat yrityksen logo tai luottamuksellisuustunnisteet, kuten ”luonnos” tai ”luottamuksellinen”.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Mitä ovat sivutetut raportit Power BI Premiumissa?](../paginated-reports/paginated-reports-report-builder-power-bi.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
