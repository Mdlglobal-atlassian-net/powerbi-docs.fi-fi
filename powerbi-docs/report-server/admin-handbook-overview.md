---
title: Yleiskatsaus järjestelmänvalvojien oppaaseen, Power BI -raporttipalvelin
description: Tervetuloa käyttämään Microsoft Power BI -raporttipalvelimen järjestelmänvalvojien opasta. Power BI -raporttipalvelin on raporttien paikallinen tallennustila, jonka kautta voit hallita Power BI- ja mobiiliraportteja sekä sivutettuja raportteja.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 130a4264b2e8c4e511527f34088a580a7787673b
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2018
ms.locfileid: "30973147"
---
# <a name="administrator-handbook-overview-power-bi-report-server"></a>Yleiskatsaus järjestelmänvalvojien oppaaseen, Power BI -raporttipalvelin
Tervetuloa käyttämään Microsoft Power BI -raporttipalvelimen järjestelmänvalvojien opasta. Power BI -raporttipalvelin on raporttien paikallinen tallennustila, jonka kautta voit hallita Power BI- ja mobiiliraportteja sekä sivutettuja raportteja.

![](media/admin-handbook-overview/admin-handbook.png)

Tämä opas auttaa ymmärtämään Power BI -raporttipalvelimen suunnitteluun, käyttöönottoon ja hallintaan liittyviä käsitteitä.

## <a name="installing-and-migration"></a>Asentaminen ja siirto
Sinun on asennettava Power BI -raporttipalvelin, jotta voit aloittaa sen käyttämisen. Meillä on tietoja, joiden avulla voit käsitellä tämän tehtävän.

Ennen kuin aloitat asentamisen, päivittämisen tai siirtämisen Power BI -raporttipalvelimeen, tutustu raporttipalvelimen [järjestelmävaatimuksiin](system-requirements.md).

### <a name="installing"></a>Asentaminen
Jos olet ottamassa käyttöön uutta Power BI -raporttipalvelinta, voit käyttää apuna seuraavia asiakirjoja. Pikaoppaan avulla voit siirtyä suoraan asiaan. Voit myös tarkastella asennuksen asiakirjaa ja tutustua asiaan paremmin.

* [Pikaopas: Power BI -raporttipalvelimen asentaminen](quickstart-install-report-server.md)
* [Power BI -raporttipalvelimen asentaminen](install-report-server.md)

### <a name="migration"></a>Siirto
SQL Server Reporting Servicesille ei ole paikallista päivitystä. Jos sinulla on aiemmin luotu SQL Server Reporting Services -esiintymä, josta haluat tehdä Power BI -raporttipalvelimen, sinun on siirrettävä se. Saatat haluta suorittaa siirron myös muista syistä. Lisätietoja on siirtotiedostossa.

[Raporttipalvelimen asennuksen siirtäminen](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>Raporttipalvelimen määrittäminen
Sinulla on useita vaihtoehtoja raporttipalvelinta määritettäessä. Käytätkö SSL:ää? Oletko määrittämässä sähköpostipalvelinta? Haluatko integroida Power BI -palvelun kanssa visualisointien kiinnittämiseksi?

Suurin osa määrityksistäsi tapahtuu raporttipalvelimen määritysten hallinnassa. Lisätietoja on [määritysten hallinnan](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode) asiakirjassa.

## <a name="security"></a>Tietoturva
Tietoturva ja suojaus ovat tärkeitä jokaiselle organisaatiolle. Saat lisätietoja todentamisesta, käyttöoikeuksien myöntämisestä, rooleista ja oikeuksista [tietoturvaa](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection) käsittelevistä ohjeista.

## <a name="next-steps"></a>Seuraavat vaiheet
[Pikaopas: Power BI -raporttipalvelimen asentaminen](quickstart-install-report-server.md)  
[Raporttipalvelimen tuoteavaimen löytäminen](find-product-key.md)  
[Asenna Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)](install-powerbi-desktop.md)  
[Raportin muodostimen asentaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) -työkalujen lataaminen](http://go.microsoft.com/fwlink/?LinkID=616714)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

