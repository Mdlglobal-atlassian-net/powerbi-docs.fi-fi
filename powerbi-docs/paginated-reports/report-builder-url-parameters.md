---
title: URL-parametrit sivutetuissa raporteissa – Power BI:n raportin muodostin
description: Tässä aiheessa kuvataan Power BI:n raportin muodostimen raporttiparametrien yleisiä käyttötarkoituksia, määritettäviä ominaisuuksia ja paljon muuta.
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.custom: ''
ms.date: 05/01/2020
ms.openlocfilehash: 83de843ba640bc165e9a56450bc5539e8e433e78
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82692862"
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

## <a name="syntax-description"></a>Syntaksin kuvaus 

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

**Vientimuoto** Määrittää raportin hahmontamisen ja viennin muodon.

Esimerkki: rdl:format=PDF

Käytettävissä olevat arvot ovat:
 
- PPTX (PowerPoint)
- MHTML 
- KUVA 
- EXCELOPENXML (EXCEL) 
- WORDOPENXML (WORD) 
- CSV 
- PDF 
- XML 

**Parametripaneelin tila** Määrittää, onko parametripaneeli suljettuna vai avoimena, kun raportti latautuu, vai onko se piilotettu kokonaan.

-   rdl:parameterPanelState

    - 'collapsed': lataa raportti, kun parametripaneeli on suljettu. Parametripainike on käytössä, jolloin käyttäjät voivat laajentaa napsauttamalla painiketta;
    - 'hidden': lataa raportti parametripaneeli suljettuna ja parametripainike poistettuna käytöstä;
    - 'expanded' (oletus): lataa raportti parametripaneeli avoimena ja parametripainike käytössä;

**Laitteen tiedot** Voit määrittää lisää tulosparametreja seuraaville vientimuodoille. 

PDF:

- rdl:AccessiblePDF=true/false
- rdl:Columns=integer
- rdl:ColumnSpacing=decimal(in)
- rdl:DpiX=integer
- rdl:DpiY=integer
- rdl:EndPage=integer
- rdl:HumanReadablePDF=true/false
- rdl:MarginBottom=decimal(in)
- rdl:MarginLeft=decimal(in)
- rdl:MarginRight=decimal(in)
- rdl:MarginTop=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:PageWidth=decimal(in)
    - rdl:StartPage=integer
    
CSV:

- rdl:Encoding=string
- rdl:ExcelMode=true/false
- rdl:FieldDelimiter=string
- rdl:FileExtension=string
- rdl:NoHeader=true/false
- rdl:Qualifier=string
- rdl:RecordDelimiter=string
- rdl:SuppressLineBreaks=true/false
    - rdl:UseFormattedValues=true/false
    
WORDOPENXML (WORD):

- rdl:AutoFit=string -> True/False/Never/Default
- rdl:ExpandToggles=true/false
- rdl:FixedPageWidth=true/false
- rdl:OmitHyperlinks=true/false
- rdl:OmitDrillthroughs=true/false

EXCELOPENXML (EXCEL):

- rdl:OmitDocumentMap=true/false
- rdl:OmitFormulas=true/false
    - rdl:SimplePageHeaders=true/false
    
PPTX (PowerPoint):
 
- rdl:Columns=integer
- rdl:ColumnSpacing=decimal(in)
- rdl:DpiX=integer
- rdl:DpiY=integer
- rdl:EndPage=integer
- rdl:MarginBottom=decimal(in)
- rdl:MarginLeft=decimal(in)
- rdl:MarginRight=decimal(in)
- rdl:MarginTop=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:PageWidth=decimal(in)
- rdl:StartPage=integer
    - rdl:UseReportPageSize=true/false

XML:

- rdl:XSLT=string
- rdl:MIMEType=string
- rdl:UseFormattedValues=true/false
- rdl:Indented=true/false
- rdl:OmitNamespace=true/false
- rdl:OmitSchema=true/false
- rdl:Encoding=string
- rdl:FileExtension=string
- rdl:Schema=true/false

## <a name="next-steps"></a>Seuraavat vaiheet

- [Raporttiparametrin välittäminen URL-osoitteessa Power BI:n sivutetuissa raporteissa](report-builder-url-pass-parameters.md)
- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
