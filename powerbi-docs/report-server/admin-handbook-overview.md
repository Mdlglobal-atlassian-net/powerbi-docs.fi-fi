---
title: Hallinnan yhteenveto, Power BI -raporttipalvelin
description: Tämä on Power BI -raporttipalvelimen hallinnan yhteenveto. Power BI -raporttipalvelin on raporttien paikallinen tallennustila, jonka kautta voit hallita Power BI- ja mobiiliraportteja sekä sivutettuja raportteja.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: maggies
ms.openlocfilehash: a93b3def115aaadbc33f6d0985aeea424558f248
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "73860217"
---
# <a name="admin-overview-power-bi-report-server"></a>Hallinnan yhteenveto, Power BI -raporttipalvelin
Tämä on Power BI -raporttipalvelimen hallinnan yhteenveto. Power BI -raporttipalvelin on raporttien paikallinen tallennustila, jonka kautta voit hallita Power BI- ja mobiiliraportteja sekä sivutettuja raportteja. Tässä artikkelissa esitellään Power BI -raporttipalvelimen suunnittelu, käyttöönotto ja hallinta sekä tarjotaan linkkejä lisätietoihin.

![](media/admin-handbook-overview/admin-handbook.png)

## <a name="installing-and-migration"></a>Asentaminen ja siirto
Sinun on asennettava Power BI -raporttipalvelin, jotta voit aloittaa sen käyttämisen. Tämä tehtävä on esitelty muissa artikkeleissa.

Ennen kuin aloitat asentamisen, päivittämisen tai siirtämisen Power BI -raporttipalvelimeen, tutustu raporttipalvelimen [järjestelmävaatimuksiin](system-requirements.md).

### <a name="installing"></a>Asennetaan
Jos olet ottamassa käyttöön uutta Power BI -raporttipalvelinta, voit käyttää apuna seuraavaa asiakirjaa. 

[Power BI -raporttipalvelimen asentaminen](install-report-server.md)

### <a name="migration"></a>Siirto
SQL Server Reporting Servicesille ei ole paikallista päivitystä. Jos sinulla on aiemmin luotu SQL Server Reporting Services -esiintymä, josta haluat tehdä Power BI -raporttipalvelimen, sinun on siirrettävä se. Saatat haluta suorittaa siirron myös muista syistä. Lisätietoja on siirtotiedostossa.

[Raporttipalvelimen asennuksen siirtäminen](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>Raporttipalvelimen määrittäminen
Sinulla on useita vaihtoehtoja raporttipalvelinta määritettäessä. Käytätkö SSL:ää? Oletko määrittämässä sähköpostipalvelinta? Haluatko integroida Power BI -palvelun kanssa visualisointien kiinnittämiseksi?

Suurin osa määrityksistäsi tapahtuu raporttipalvelimen määritysten hallinnassa. Lisätietoja on [määritysten hallinnan](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode) asiakirjassa.

## <a name="security"></a>Tietoturva
Tietoturva ja suojaus ovat tärkeitä jokaiselle organisaatiolle. Saat lisätietoja todentamisesta, käyttöoikeuksien myöntämisestä, rooleista ja oikeuksista [tietoturvaa](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection) käsittelevistä ohjeista.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI -raporttipalvelimen asentaminen](install-report-server.md)  
[Raporttipalvelimen tuoteavaimen löytäminen](find-product-key.md)  
[Asenna Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)](install-powerbi-desktop.md)  
[Raportin muodostimen lataaminen](https://www.microsoft.com/download/details.aspx?id=53613)  
[SQL Server Data Tools (SSDT) -työkalujen lataaminen](https://go.microsoft.com/fwlink/?LinkID=616714)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

