---
title: PDF-hahmontamislaajennuksen määritystenmukaisuus standardiin ISO 14289-1 nähden – Power BI -raporttipalvelin ja SSRS
description: Tässä asiakirjassa kuvataan Power BI -raporttipalvelimen ja SQL Server Reporting Servicesin PDF-hahmontamislaajennuksen määritystenmukaisuus ISO 14289-1 (PDF/UA) -määrityksiin nähden.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/04/2019
ms.author: maggies
ms.openlocfilehash: bfefcef18b8cd92a5c3b15c2dcbd4653a6c7c9cd
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819510"
---
# <a name="pdf-rendering-extension-conformance-to-iso-14289-1---power-bi-report-server--ssrs"></a>PDF-hahmontamislaajennuksen määritystenmukaisuus standardiin ISO 14289-1 nähden – Power BI -raporttipalvelin ja SSRS

Koskee seuraavia: Power BI -raporttipalvelin ja SQL Server Reporting Services (SSRS)

Tässä asiakirjassa kuvataan Power BI -raporttipalvelimen ja SQL Server Reporting Servicesin PDF-hahmontamislaajennuksen määritystenmukaisuus [ISO 14289-1 (PDF/UA)](https://www.pdfa.org/publication/pdfua-in-a-nutshell/) -määrityksiin nähden.

> [!NOTE]
> Voit tallentaa tai tulostaa tämän teknisen raportin valitsemalla selaimessa **Tulosta** ja valitsemalla sitten **Tallenna PDF-tiedostona**.

## <a name="1--scope"></a>1.  Vaikutusalue

Ei käytettävissä

## <a name="2--normative-references"></a>2.  Normatiiviset viittaukset

Ei käytettävissä

## <a name="3--terms-and-definitions"></a>3.  Ehdot ja määritelmät

Ei käytettävissä

## <a name="4--notation"></a>4.  Merkintä

Ei käytettävissä

## <a name="5-version-identification"></a>5. Version tunnus

PDF-hahmontamislaajennus tarjoaa PDF/UA-tuen tässä asiakirjassa kuvatulla tavalla. Joissakin tapauksissa, kuten seuraavassa on mainittu, käyttäjän velvollisuutena on ryhtyä toimiin sen varmistamiseksi, että PDF-tiedosto on täysin PDF/UA-yhteensopiva.  Oletamme, että käyttäjä lisää asianmukaisen PDF/UA-version ja määritystenmukaisuustunnisteen tämän prosessin viimeisenä vaiheena sen osoitukseksi, että PDF-tiedoston PDF/UA-yhteensopivuus on pyritty varmistamaan.

Kaikki tässä asia kirjassa luetellut tiedot perustuvat PDF-tiedoston hahmontamiseen, kun laitetietojen asetuksen AccessiblePdf arvona on `true`. Joissakin tapauksissa yhteensopivuuden rajoitukset johtuvat RDL-kielen rajoituksista.

## <a name="6--conformance-requirements"></a>6.  Määritystenmukaisuusvaatimukset

|     Ehdot     |     Tukeva ominaisuus     |     Huomautukset      |
|----|--------|--------|
|    6.1 Yleistä    |                 Tuetaan    |    PDF-hahmontamislaajennus luo PDF-version 1.7.    |
|    6.2 Vaatimusten mukaiset tiedostot    |                 Tuettu poikkeuksin    |    Katso huomautukset osassa 7 – Tiedostomuotovaatimukset.    |
|    6.3 Vaatimusten mukainen lukuohjelma    |     Ei käytettävissä     |         |
|    6.4 Vaatimusten mukaiset käyttöä helpottavat toiminnot    |     Ei käytettävissä     |         |

## <a name="7--file-format-requirements"></a>7.  Tiedostomuotovaatimukset

|     Ehdot     |     Tukeva ominaisuus     |     Huomautukset      |
|-----|-------|------------------------|
|    7.1 Yleistä    |                 Tuettu poikkeuksin    |    Kaikki todellinen sisältö on merkittävä tavalla, joka on määritetty standardissa ISO 32000-1:2008, 14.8. Artefakteja (ISO 32000-1:2008, 14.8.2.2.2) ei tule merkitä rakennepuuhun. <li> PDF-hahmontamislaajennus ei sisällä mahdollisuutta merkitä yksittäisiä kohteita artefakteiksi, joten se merkitsee sen sijaan artefakteiksi kaikki kohteet, jotka täyttävät standardissa ISO 32000-1:2008, 14.8.2.2.2 määritetyt ehdot.<br>Sisältö on merkittävä rakennepuuhun semanttisesti sopivilla tunnisteilla loogisessa lukemisjärjestyksessä. <br> **Huomautus** 4 Verkkosisällön saavutettavuusohjeiden (WCAG) version 2.0 ohjeessa 1.4 selostetaan helppokäyttöisyysongelmia, jotka liittyvät kontrastin, värin ja muiden muotoilujen käyttöön. <br><li> Käyttäjän on varmistettava, ettei asiakirjaa ole näitä ongelmia. <br>Standardissa ISO 32000-1:2008, 14.8.4 määritettyjä vakiotunnisteita ei määritetä uudelleen. <li> PDF-hahmontamislaajennus ei määritä uudelleen vakiotunnisteita. Asiakirjojen alussa on asiakirjan pääelementti. <br>Tämän kansainvälisen standardin määritysten mukaiseksi merkityn tiedoston Suspects-arvon on oltava False (ISO 32000-1:2008, taulukko 321). <li> PDF-hahmontamislaajennuksessa ei ole Suspects-merkintää. Tämä ominaisuus on valinnainen.    |
|    7.2 Teksti    |                 Tuettu poikkeuksin    |    Sisältö merkitään loogisessa lukemisjärjestyksessä. Semanttisesti sopivinta merkintää on käytettävä jokaiselle asiakirjan sisällön loogiselle osalle. <br><li> PDF-hahmontamislaajennus merkitsee sisällön mahdollisimman paljon loogisessa lukemisjärjestyksessä.<br>Merkkikoodien on oltava standardissa ISO 32000-1:2008, 14.8.2.4.2 määritetyn Unicode-määrityksen mukaisia. Merkit, jotka eivät sisälly Unicode-määritykseen, saattavat käyttää Unicode-yksityiskäyttöaluetta tai esitellä muun merkkikoodauksen. <br>Luonnollinen kieli on esiteltävä standardissa ISO 32000-1:2008, 14.9.2 mainitulla tavalla ja/tai standardissa ISO 32000-1:2008, 7.9.2 kuvatulla tavalla. Luonnollisen kielen muutokset on esiteltävä. Luonnollisen kielen muutokset tekstimerkkijonojen sisällä (esimerkiksi vaihtoehtoisten kuvausten sisällä) on esiteltävä standardissa ISO 32000-1:2008, 14.9.2.2 kuvatun kielitunnisteen avulla. <br><li> PDF-hahmontamislaajennus esittelee luonnollisen kielen vain asiakirjatasolla    |
|    7.3 Grafiikka    |                 Tuettu poikkeuksin    |    Grafiikkaobjektit, jotka eivät ole tekstiobjekteja, on merkittävä Figure-tunnisteella, joka on kuvattu standardissa ISO 32000-1:2008, 14.8.4.5, taulukko 340. Jos jompikumpi seuraavista poikkeuksista on tosi, kuva on merkittävä artefaktiksi: <br><li> kuva ei esitä merkityksellistä sisältöä, tai <li>  kuva näkyy linkkihuomautuksen taustana, jolloin linkin vaihtoehtoisen tekstin tulee kuvata sekä kuvaa että linkkiä. <li> PDF-hahmontamislaajennus merkitsee grafiikkaobjektit Figure-tunnisteella. <br>Kuvaan liittyvä kuvateksti on merkittävä Caption-tunnisteella. <li> PDF-hahmontamislaajennus ei tällä hetkellä merkitse kuvatekstiä kuviin Caption-tunnisteella. <br>Figure-tunnisteiden on sisällettävä vaihtoehtoinen esitys tai korvaava teksti, joka esittää Figure-tunnisteella merkittyä sisältöä standardissa ISO 32000-1:2008, 14.7.2, taulukko 323,kuvatulla tavalla. <br>**Huomautus** 1 Katso myös verkkosisällön saavutettavuusohjeiden (WCAG) version 2.0 ohjetta 1.1. <br>Jos kuvassa näkyvä teksti ei ole ihmislukijan luettavaksi tarkoitettua luonnollista kieltä, on annettava kuvan luonnetta tai tarkoitusta kuvaava vaihtoehtoinen teksti. <br>**Huomautus** 2 Teksti, joka on kirjoitusmalli tai malli kielessä käytettävästä kirjoitusjärjestelmästä, on esimerkki tekstistä, joka ei ole kirjoitettu luonnollisella kielellä.   PDF-hahmontamislaajennus tukee kuvien vaihtoehtoista tekstiä, vaikkakin käyttäjän on lisättävä vaihtoehtoinen teksti. <br>BBox-määritettä koskeva lisähuomautus: <br><li> PDF-hahmontamislaajennus ei tällä hetkellä kirjoita BBox-määritettä. <li> Vaihtoehtoinen menetelmä on kuvien merkitseminen uudelleen uusiksi kuviksi tai artefakteiksi.    |
|    7.4 Otsikot    |                 Ei käytettävissä    |    RDL ei tue otsikoiden merkitsemistä millään tavalla. Käyttäjän on merkittävä ne tarvittavalla tavalla.    |
|    7.5 Taulukot    |                 Tuettu poikkeuksin    |    Taulukoissa on oltava otsikoita. Taulukon otsikot on merkittävä tavalla, joka on standardin ISO 32000-1:2008, taulukko 337 ja taulukko 349, mukainen. <br>**Huomautus** 1 Taulukot voivat sisältää sarakeotsikoita, riviotsikoita tai molempia. <br>**Huomautus** 2 Taulukoiden rakenteesta on oltava käytettävissä mahdollisimman paljon tietoja, kun käytetään käyttöä helpottavia toimintoja. Otsikoilla on tärkeä rooli rakenteellisten tietojen antamisessa. <br><li> Käyttäjän on sisällytettävä otsikot taulukoihin. RDL ja PDF-hahmontamislaajennus tukevat riviotsikoita. <br>  TH-tyyppisissä rakenneosissa on oltava Scope-määrite.   <li> PDF-hahmontamislaajennukseen sisältyy Scope-määrite sarake- ja rivijäsenille, mutta ei kulmasoluille.<br>Taulukon tunnisterakenteita tulee käyttää vain loogisissa rivi- ja/tai sarakesuhteissa esitettyjen sisältöjen merkitsemiseen.   <li> Tämä riippuu siitä, miten käyttäjä on käyttänyt taulukoita RDL:ssä.    |
|    7.6 Luettelot    |                 Ei käytettävissä    |    RDL ei tue luetteloiden merkitsemistä. RDL:ssä ne ovat rakenteellisesti taulukko, joka sijaitsee yksittäisessä taulukon solussa. <br>Käyttäjän on merkittävä ne uudelleen tarvittavalla tavalla.    |
|    7.7 Matemaattiset lausekkeet    |                 Tuettu poikkeuksin    |    Kaikki matemaattiset lausekkeet on sisällytettävä Formula-tunnisteeseen, joka on kuvattu standardissa ISO 32000-1:2008, 14.8.4.5, ja niissä on oltava Alt-määrite. <br><li> PDF-hahmontamislaajennus ei tällä hetkellä sisällytä matemaattisia lausekkeita Formula-tunnisteeseen. <br>Matemaattisten lausekkeiden on oltava niiden merkkien Unicode-määritystä koskevien vaatimusten mukaisia, jotka on mainittu standardissa ISO 32000-1:2008, 9.10.2 and 14.8.2.4. <br><li> PDF-hahmontamislaajennus tukee tätä.    |
|    7.8 Sivun ylä-ja alatunnisteet    |                 Tuetaan    |    Ylä- ja alatunnisteet on määritettävä Pagination-artefakteiksi, ja ne on luokiteltava joko  Header- tai Footer-alatyypeiksi standardin ISO 32000-1:2008, 14.8.2.2.2, taulukko 330, mukaisesti. <br><li> Ylä- tai alatunnisteita käsitellään ja ne merkitään artefakteiksi.    |
|    7.9 Muistiinpanot ja viittaukset    |                 Ei käytettävissä    |    PDF-hahmontamislaajennus ei tue muistiinpanojen ja viittausten merkintää. <br>Käyttäjän on merkittävä ne tarvittavalla tavalla.    |
|    7.10 Valinnainen sisältö    |                 Ei käytettävissä    |         |
|    7.11 Upotetut tiedostot    |                 Ei käytettävissä    |         |
|    7.12 Artikkeliketjut    |                 Ei käytettävissä    |         |
|    7.13 Digitaaliset allekirjoitukset    |                 Ei käytettävissä    |         |
|    7.14 Ei-vuorovaikutteiset lomakkeet    |                 Ei käytettävissä    |         |
|    7.15 XFA    |                 Ei käytettävissä    |         |
|    7.16 Tietoturva    |                 Ei käytettävissä    |         |
|    7.17 Siirtyminen    |                 Tuetaan    |    Asiakirjan tulee sisältää asiakirjan jäsennys, joka vastaa lukemisjärjestystä ja siirtymiskohteiden tasoa (ISO 32000-1:2008, 12.3.3). <br><li> RDL tukee raporttikohteen kirjanmerkkejä, mutta käyttäjän on valittava tämä vaihtoehto. Sen jälkeen PDF-hahmontamislaajennus hahmontaa nämä kirjanmerkit asiakirjan jäsennykseksi. <br>Jos PageLabels-numeropuun (ISO 32000-1:2008, 7.7.2, taulukko 28) merkinnät ovat käytettävissä, niiden on oltava semanttisesti asianmukaisia. <br><li> PDF-hahmontamislaajennus ei sisällä PageLabels-numeropuuta.    |
|    7.18 Huomautukset    |                 Ei käytettävissä    |    RDL ei tue merkintöjä    |
|    7.21 Fontit    |                 Tuetaan    |         |
|    7.21.1 Yleistä    |                 Tuetaan    |         |
|    7.21.2 Fontti tyypit    |                 Tuetaan    |         |
|    7.21.3 Yhdistelmäfontti    |                 Tuetaan    |         |
|    7.21.3.1 Yleistä    |                 Tuetaan    |         |
|    7.21 3.2 CID-fontit    |                 Tuetaan    |         |
|    7.21.3.3 CMap-fontit    |                 Tuetaan    |         |
|    7.21.4 Upottaminen    |                 Tuetaan    |         |
|    7.21.4.1 Yleistä    |                 Tuetaan    |         |
|    7.21.4.2 Alijoukon upottaminen    |                 Tuetaan    |         |
|    7.21.5 Fonttimääritykset    |                 Tuetaan    |         |
|    7.21.6 Merkkikoodaukset    |                 Tuetaan    |         |
|    7.21.7 Unicode-merkistöt    |                 Tuetaan    |         |
|    7.21.8 .notdef-merkin käyttö    |                 Tuetaan    |         |

## <a name="8--conforming-reader-requirements"></a>8.  Vaatimusten mukaisen lukuohjelman vaatimukset

Ei käytettävissä

## <a name="9--at-requirements"></a>9.  Käyttöä helpottavien toimintojen vaatimukset

Ei käytettävissä

## <a name="disclaimer"></a>Disclaimer

© 2017 Microsoft Corporation. All rights reserved. The names of actual companies and products mentioned herein may be the trademarks of their respective owners. The information contained in this document represents the current view of Microsoft Corporation on the issues discussed as of the date of publication. Microsoft cannot guarantee the accuracy of any information presented after the date of publication. Microsoft regularly updates its websites with new information about the accessibility of products as that information becomes available.

Customization of the product voids this conformance statement from Microsoft. Please consult with Assistive Technology (AT) vendors for compatibility specifications of specific AT products.

This document is for informational purposes only. MICROSOFT MAKES NO WARRANTIES, EXPRESS OR IMPLIED, IN THIS DOCUMENT.


## <a name="next-steps"></a>Seuraavat vaiheet
[Järjestelmänvalvojan yleiskatsaus](admin-handbook-overview.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

