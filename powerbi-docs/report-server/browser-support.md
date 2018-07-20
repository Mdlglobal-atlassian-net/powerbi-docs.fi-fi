---
title: Power BI -raporttipalvelimen selaintuki
description: Tietoa siitä, mitä selainversioita tuetaan Power BI -raporttipalvelimen ja raporttien katseluohjelman ohjausobjektien hallintaan ja tarkasteluun.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 01/25/2018
ms.author: maghan
ms.openlocfilehash: b340ba2f2798c518d1705c03f7ec526a43bc019d
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721773"
---
# <a name="browser-support-for-power-bi-report-server"></a>Power BI -raporttipalvelimen selaintuki
Tietoa siitä, mitä selainversioita tuetaan Power BI -raporttipalvelimen ja raporttien katseluohjelman ohjausobjektien hallintaan ja tarkasteluun.

## <a name="browser-requirements-for-the-web-portal"></a>Verkkoportaalin selainvaatimukset
Seuraavassa on ajantasainen luettelo verkkoportaalin tukemista selaimista.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9–10.11*

* Apple Safari (+)
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple iOS**  
*iPhonet ja iPadit, joissa on iOS 10*

* Apple Safari (+)

**Google Android**  
*Puhelimet ja tabletit, joissa on Android 4.4 (KitKat) tai uudempi versio*

* Google Chrome (+)
  
  **(+)**  Viimeisin suurelle yleisölle julkaistu versio

## <a name="browser-requirements-for-the-report-viewer-web-control-2015"></a>Raporttien katseluohjelman verkko-ohjausobjektin (2015) selainvaatimukset
Seuraavassa on ajantasainen luettelo raporttien katseluohjelman verkko-ohjausobjektin tukemista selaimista. Raporttien katseluohjelma tukee raporttien katselua verkkoportaalista.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9–10.11*

* Apple Safari (+)
  
  **(+)**  Viimeisin suurelle yleisölle julkaistu versio

### <a name="authentication-requirements"></a>Todentamisen vaatimukset
Selaimet tukevat tiettyjä todennusmalleja, jotka raporttipalvelin käsittelee voidakseen sallia asiakkaan pyynnön. Seuraavassa taulukossa kerrotaan Windows-käyttöjärjestelmässä käytettävien eri selainten oletusarvoiset todennustyypit.

| **Selain** | **Tuki** | **Selaimen oletusasetus** | **Palvelimen oletusasetus** |
| --- | --- | --- | --- |
| **Microsoft Edge** (+) |Negotiate, Kerberos, NTLM, perustodennus |Negotiate |On. Oletusarvoiset todennusasetukset toimivat Edgen kanssa. |
| **Microsoft Internet Explorer** |Negotiate, Kerberos, NTLM, perustodennus |Negotiate |On. Oletusarvoiset todennusasetukset toimivat Internet Explorerin kanssa. |
| **Google Chrome**(+) |Negotiate, NTLM, perustodennus |Negotiate |On. Oletusarvoiset todennusasetukset toimivat Chromen kanssa. |
| **Mozilla Firefox**(+) |NTLM, perustodennus |NTLM |On. Oletusarvoiset todennusasetukset toimivat Firefoxin kanssa. |
| **Apple Safari**(+) |NTLM, perustodennus |Perustodennus |On. Oletusarvoiset todennusasetukset toimivat Safarin kanssa. |

 **(+)**  Viimeisin suurelle yleisölle julkaistu versio

### <a name="script-requirements-for-viewing-reports"></a>Raporttien tarkastelun edellyttämät komentosarjavaatimukset
Voidaksesi käyttää raporttien katseluohjelmaa, sinun on määritettävä selaimesi suorittamaan komentosarjoja.

Jos komentosarjat eivät ole käytössä, raportin avaamisen yhteydessä näytölle tulee seuraavankaltainen virheilmoitus:

```
Your browser does not support scripts or has been configured to not allow scripts to run. Click here to view this report without scripts
```

 Jos päätät tarkastella raportteja ilman komentosarjojen tukea, raportti muodostetaan HTML:llä ilman raportin katseluohjelman ominaisuuksia, kuten raporttityökaluriviä tai asiakirjan rakenneruutua.

> [!NOTE]
> Raporttityökalurivi on osa HTML-katseluohjelmakomponenttia. Oletusarvoisesti työkalurivi näkyy jokaisen selainikkunassa muodostetun raportin yläreunassa. Raporttien katseluohjelman tarjoamiin ominaisuuksiin sisältyvät muun muassa hakujen tekeminen raportissa, siirtyminen tietylle sivulle ja sivun koon säätäminen katselun helpottamiseksi. Lisätietoja raporttityökalurivistä ja HTML-katseluohjelmasta saat ohjeaiheesta [HTML-katseluohjelma ja raporttityökalurivi](https://docs.microsoft.com/sql/reporting-services/html-viewer-and-the-report-toolbar).
> 
> 

## <a name="browser-support-for-report-viewer-web-server-controls-in-visual-studio"></a>Raporttien katseluohjelman verkkopalvelinohjausobjektien selaintuki Visual Studiossa
Raporttien katseluohjelman verkkopalvelinohjausobjektia käytetään raporttitoiminnallisuuksien upottamiseen ASP.NET-verkkosovellukseen. Lisätietoja raporttien katseluohjelman ohjausobjektin hankkimisesta saat ohjeaiheesta [Reporting Services ‑palvelun integrointi raporttien katseluohjelman ohjausobjektin avulla – aloittaminen](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started).

Käytä selainta, jossa on käytössä komentosarjojen tuki. Jos selain ei voi suorittaa komentosarjoja, et voi tarkastella raporttia.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)
  
  **(+)**  Viimeisin suurelle yleisölle julkaistu versio

## <a name="next-steps"></a>Seuraavat vaiheet
[Järjestelmänvalvojan yleiskatsaus](admin-handbook-overview.md)  
[Power BI -raporttipalvelimen asentaminen](install-report-server.md)  
[Raportin muodostimen asentaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) -työkalujen lataaminen](http://go.microsoft.com/fwlink/?LinkID=616714)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

