---
title: Aliraporttien vianmääritys Power BI:n sivutetuissa raporteissa
description: Tässä artikkelissa kerrotaan Power BI -palvelun sivutetuissa raporteissa tuetuista tietolähteistä ja siitä, miten yhteys muodostaa yhteyden Microsoft Azuren SQL-tietokannan tietolähteisiin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 04/29/2020
ms.openlocfilehash: 6de85f6dda69e902a98d6ee63d1fc4b86fb4180b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82615630"
---
# <a name="troubleshoot-subreports-in-power-bi-paginated-reports"></a>Aliraporttien vianmääritys Power BI:n sivutetuissa raporteissa

Joskus käytettäessä aliraportteja sivutetuissa raporteissa voidaan saada odottamattomia tuloksia tai ominaisuus toimii odottamattomalla tavalla. Tämä artikkeli antaa ratkaisuja yleisiin ongelmiin käytettäessä aliraportteja. *Aliraportti* on raporttikohde, joka näyttää toisen raportin pääsivutetun raportin rungon sisällä. [Aliraporttien vianmääritys Power BI:n sivutetuissa raporteissa](subreports.md) on annettu lisää taustatietoa.

## <a name="subreport-couldnt-be-found"></a>Aliraporttia ei löytynyt

**Kuvaus:** Aliraporttia ei voi hahmontaa. Saat sen sijaan virheilmoituksen.

### <a name="message"></a>Viesti

"Aliraporttia “Subreport1” ei löytynyt määritetystä sijainnista 'CustomerDetails'. Varmista, että aliraportti on julkaistu ja että nimi on oikein."

### <a name="possible-reasons"></a>Mahdolliset syyt

- Määritettyä nimeä käyttävä aliraportti ei ole samassa työtilassa tai sovelluksessa kuin pääraportti.
- Käyttäjällä ei ole aliraportin käyttöoikeutta.
- Pääraportin aliraporttien määrä on saavuttanut aliraportin enimmäismäärän (50 aliraporttia).

### <a name="troubleshooting-steps"></a>Vianmäärityksen vaiheet

**Työtilassa**

- Varmista, että raportti, jonka nimi virhesanomassa on, on olemassa. Nimen kirjainkoolla ei ole merkitystä.

**Sovelluksessa**

- Varmista, että raportti, jonka nimi virhesanomassa on, on sovelluksessa. Pyydä lisäohjeita sovelluksen tekijältä.

**Jos raportti on jaettu**

1. Varmista, että raportti, jonka nimi virhesanomassa on, on jaettu sinulle.
2. Jos raportti on olemassa, tarkista, että pääraportin ja aliraportin omistajan nimi on sama. Ota sitten yhteyttä pääraportin omistajaan näillä tiedoilla.

## <a name="subreport-renders-with-unexpected-content"></a>Aliraportti hahmontaa odottamattomalla sisällöllä

### <a name="possible-reason"></a>Mahdollinen syy

Power BI mahdollistaa käyttäjille useita samannimisiä raportteja samassa työtilassa

### <a name="troubleshooting-steps-for-report-authors"></a>Vianmääritysvaiheet (raportin tekijöille)

1. Avaa pääraportti Power BI -raportin muodostimessa ja määritä aliraportin nimi.
2. Etsi raportteja, joilla on sama nimi työtilassa.
3. Etsi odotettu raportti ja nimeä loput uudelleen.

**Muille kuin tekijöille:** Ota yhteyttä tekijään.

## <a name="data-retrieval-fails"></a>Tietojen nouto epäonnistuu

**Kuvaus:** Tietojen noutaminen epäonnistuu hahmonnettaessa aliraporttia. Aliraporttia ei voi hahmontaa. Saat sen sijaan virheilmoituksen.

### <a name="message"></a>Viesti

"Tietojen nouto epäonnistui aliraportille 'Subreport1', joka sijaitsee kohteessa: 'InvoiceDetails'. Saat lisätietoja lokitiedostosta."

### <a name="troubleshooting-steps"></a>Vianmäärityksen vaiheet

Sama kuin tietojen käyttöongelmia koskevien raporttien yleiset vianmääritysvaiheet.

## <a name="rendering-fails-unspecified-parameters"></a>Hahmontaminen epäonnistuu: Määrittämättömät parametrit

**Kuvaus:** Aliraportin muodostaminen epäonnistuu määrittämättömien parametrien vuoksi. Aliraportissa on pakollisia parametreja, mutta pääraportissa ei ole kaikkia niitä.

### <a name="message"></a>Viesti 
"Vähintään yhtä parametria ei määritetty aliraportille'Subreport1', joka sijaitsee kohteessa: 'SubreportAWithDS'."

### <a name="troubleshooting-steps-for-the-report-author"></a>Vianmääritysvaiheet (raportin tekijöille)

1. Avaa pääraportti Power BI:n raportin muodostimessa.
2. Avaa aliraportti Power BI:n raportin muodostimessa.
3. Varmista, että pääraportin aliraporttikohteen sisällä välitetyn parametrin arvo vastaa aliraportin parametrien joukkoa.

**Muille kuin tekijöille:** Ota yhteyttä tekijään.

## <a name="rendering-fails-recursion-limit"></a>Hahmontaminen epäonnistuu: Rekursioraja

**Kuvaus:** Aliraportin muodostaminen epäonnistuu rekursiorajan vuoksi. Aliraportteja ei voi asettaa sisäkkäin syvemmälle kuin 20 tasoa.

### <a name="message"></a>Viesti

"Raportilla tai aliraportilla on rekursiivinen aliraportti 'Subreport1', joka ylitti suurimman sallitun rekursiorajan."

### <a name="troubleshooting-steps-for-report-authors"></a>Vianmääritysvaiheet (raportin tekijöille)

- Pienennä sisäkkäisyyttä.
- Uudista raportin rakenne.

## <a name="other-errors"></a>Muut virheet

**Kuvaus:** Virheet, jotka eivät kuulu mihinkään edelliseen luokkaan.

### <a name="message"></a>Viesti

"Virhe: Aliraporttia ei voi näyttää."

### <a name="possible-reasons"></a>Mahdolliset syyt

- Useita virheitä aliraportin hahmontamisen aikana, esimerkiksi parametriristiriita tietojen nouto-ongelmien kanssa.
- Odottamattomia virheitä.

### <a name="troubleshooting-steps-for-report-authors"></a>Vianmääritysvaiheet (raportin tekijöille)

1. Varmista, että aliraportin voi hahmontaa suoraan.
2. Jos aliraportin voi hahmontaa, tarkista sekä aliraportin että pääraportin parametrit.
3. Varmista, että pääraportissa ei ole enempää kuin 50 yksilöllistä aliraporttia, eikä aliraportissa ole sisäkkäin yli 20 tasoa.
4. Jos et pysty ratkaisemaan ongelmaa, ota yhteyttä Power BI -tukeen.

**Muille kuin tekijöille:** Ota yhteyttä tekijään.

## <a name="next-steps"></a>Seuraavat vaiheet

[Aliraportit Power BI:n sivutetuissa raporteissa](subreports.md)

[Sivutetun raportin tarkasteleminen Power BI -palvelussa](../consumer/paginated-reports-view-power-bi-service.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
