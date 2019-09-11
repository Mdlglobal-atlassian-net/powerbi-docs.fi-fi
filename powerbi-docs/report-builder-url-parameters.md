---
title: URL-parametrit sivutetuissa raporteissa – Power BI:n raportin muodostin
description: Tässä aiheessa kuvataan Power BI:n sivutetun raportin muodostimen raporttiparametrien yleisiä käyttötarkoituksia, määritettäviä ominaisuuksia ja paljon muuta.
ms.service: powerbi
ms.subservice: report-builder
ms.custom: ''
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.date: 08/29/2019
ms.openlocfilehash: bda35bfb4690d8109f7bd611e3d319278d235f33
ms.sourcegitcommit: 09ee1b4697aad84d8f4c9421015d7e4dbd3cf25f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/04/2019
ms.locfileid: "70302661"
---
# <a name="url-parameters-in-paginated-reports-in-power-bi"></a>URL-parametrit Power BI:n sivutetuissa raporteissa

Voit lähettää komentoja Power BI:n sivutettuihin raportteihin lisäämällä parametrin URL-osoitteeseen. Olet esimerkiksi saattanut tarkastella raporttia käyttämällä tiettyä raporttiparametriarvojen joukkoa. Kapseloit nämä tiedot URL-osoitteeseen käyttämällä esimääritettyjä URL-yhteysparametreja. Voit mukauttaa myös sitä, miten Power BI käsittelee raporttia upottamalla muotojen hahmontamisen tai raporttityökalurivin ulkoasun parametreja. Sen jälkeen liität tämän URL-osoitteen suoraan sähköpostiviestiin tai verkkosivulle, jotta muut kokevat raporttisi samalla tavalla selaimessa. 

Voit suorittaa seuraavia toimintoja URL-yhteysparametrien avulla: 

- Raporttiparametrien lähettäminen raporttiin. 
- Raportin sisällön viennin aloittaminen tuetussa tiedostomuodossa. 
- Parametriruudun näyttäminen tai piilottaminen. 
- DeviceInfo-asetuksen määrittäminen. 

Täydellisen luettelon URL-yhteyden kautta käytettävissä olevista komennoista ja asetuksista näet tämän artikkelin myöhemmässä kohdassa  [URL-yhteysparametriohje](#url-access-parameter-reference). 

## <a name="url-access-concepts"></a>URL-yhteyden käsitteet 

Power BI:n URL-pyynnöt sisältävät palvelun käsittelemiä parametreja. Se, miten palvelu käsittelee URL-pyyntöjä, riippuu URL-osoitteeseen sisältyvistä parametreista, parametrien etuliitteistä ja kohdetyypeistä. Sivutetun raportin URL-toiminto on yhteensopiva useimpien URL-osoitteiden vakiomääritystä tukevien selainten ja sovellusten kanssa. 

## <a name="url-access-syntax"></a>URL-yhteyden syntaksi 

URL-pyynnöt voivat sisältää useita parametreja, jotka luetellaan missä tahansa järjestyksessä. Parametrit erotetaan toisistaan et-merkillä (&). Nimi-arvoparit erotetaan toisistaan yhtäläisyysmerkillä (=). Esimerkki:

```
powerbiserviceurl?rp:parametervalueh&rdl:parameter=value  
```

## <a name="syntax-description"></a>syntaksin kuvaus 

### <a name="powerbiserviceurl"></a>powerbiserviceurl 

Power BI -vuokraajasi verkkopalvelun URL-osoite. Esimerkki: 

**&** Käytetään erottamaan URL-yhteysparametrien nimi-arvoparit.

**etuliite** URL-parametrin etuliite (esimerkiksi rp: tai rdl:), joka määrittää toiminnon Power BI -palvelussa. 

> [!NOTE]
> Raporttiparametrit edellyttävät parametrin etuliitettä, ja kirjainkoko on niissä merkitsevä. 

**parametri** Parametrin nimi. 

### <a name="value"></a>arvo 

Käytettävän parametrin arvoa vastaava URL-teksti. 

Katso esimerkkejä raporttiparametrien välittämisestä URL-osoitteessa kohdasta  [Raporttiparametrin välittäminen URL-osoitteessa](report-builder-url-pass-parameters.md).

## <a name="url-access-parameter-reference"></a>URL-yhteysparametriohje

Voit käyttää seuraavia parametreja URL-osoitteen osana ja määrittää niiden avulla sivutettujen raporttien ulkoasun Power BI:ssä. Yleisimmät parametrit luetellaan tässä osassa. Parametrien kirjainkoko ei ole merkitsevä, ja ne alkavat parametrin etuliitteellä, `rdl:` jos ne liittyvät tulostusmuotoon.  

### <a name="report-commands-rdl"></a>Raportin komennot (`rdl:`) 

**Vientimuoto** Määrittää raportin hahmontamisen ja viennin muodon. Käytettävissä olevat arvot ovat: 
- PPTX (PowerPoint)
- MHTML 
- KUVA 
- EXCELOPENXML (EXCEL) 
- WORDOPENXML (WORD) 
- CSV 
- PDF 
- XML 

## <a name="next-steps"></a>Seuraavat vaiheet

- [Raporttiparametrin välittäminen URL-osoitteessa Power BI:n sivutetuissa raporteissa](report-builder-url-pass-parameters.md)
- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
