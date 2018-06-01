---
title: SAP HANA -käyttö Power BI Desktopissa
description: SAP HANA -käyttö Power BI Desktopissa
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 03/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1c8f3bfc64c6ab895d62749d4d4bc0d2d70d0a9b
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2018
ms.locfileid: "30975332"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>SAP HANA -käyttö Power BI Desktopissa
Voit nyt käyttää **SAP HANA** -tietokantoja Power BI Desktopilla. Jotta voit käyttää **SAP HANA** -tietokantoja, täytyy SAP HANA ODBC -ohjain olla asennettuna paikallisessa asiakastietokoneessa, jotta Power BI Desktopin **SAP HANA** -tietoyhteys toimii oikein. Voit ladata SAP HANA ODBC -ohjaimen [SAP-ohjelmiston latauskeskuksesta](https://support.sap.com/swdc). Etsi sieltä Windows-koneille tarkoitettu SAP HANA CLIENT -asiakasohjelmisto. Koska **SAP-ohjelmiston latauskeskus** muuttaa rakennettaan usein, emme voi antaa tarkempia ohjeita kyseisellä sivulla navigoimiseen.

Muodostaaksesi yhteyden **SAP HANA** -tietokantaan, valitse **Nouda tiedot > Tietokanta > SAP HANA -tietokanta** seuraavassa kuvassa esitetyllä tavalla:

![](media/desktop-sap-hana/sap-hana-1.png)

Kun yhteys SAP HANA -tietokantaan muodostetaan, määritä palvelimen nimi ja portti muodossa *palvelin:portti* – seuraavassa kuvassa on esimerkki, jossa palvelimen nimi on *ServerXYZ* ja porti on *30015*.

![](media/desktop-sap-hana/sap-hana-2.png)

Tässä julkaisussa **SAP HANA** -tietokannan [DirectQuery](desktop-directquery-sap-hana.md)-tila on tuettu Power BI Desktopissa ja Power BI -palvelussa, ja voit julkaista ja ladata raportteja, joissa käytetään **SAP HANA** -tietokannan DirectQuery -tilaa, Power BI -palveluun. Voit myös julkaista ja ladata raportteja Power BI -palveluun, kun **SAP HANA** -tietokanta ei ole DirectQuery-tilassa.

### <a name="supported-features-for-sap-hana"></a>SAP HANA -tietokannan tuetut ominaisuudet
Tässä julkaisussa hyödynnetään monia **SAP HANA** -tietokannan ominaisuuksia, kuten näkyy seuraavassa luettelossa:

* **SAP HANA** -tietokannan Power BI -liitäntä käyttää SAP ODBC -ohjainta antamaan parhaan mahdollisen käyttäjäkokemuksen.
* **SAP HANA** tukee sekä DirectQuery- että tuontivaihtoehtoja.
* Power BI tukee HANA-tietomalleja (kuten analyyttinen ja laskelmanäkymä) ja sen navigointi on optimoitu.
* Voit myös käyttää **SAP HANA** -tietokannan kanssa Direct SQL -toimintoa yhdistääksesi rivi- ja saraketaulukkoja.
* Sisältää HANA-mallien optimoidun selaamisen.
* Power BI tukee **SAP HANA** -muuttujia ja syöttöparametreja.

### <a name="installing-the-sap-hana-odbc-driver"></a>SAP HANA ODBC -ohjaimen asentaminen
### <a name="limitations-of-sap-hana"></a>SAP HANA -tietokantojen rajoitukset
**SAP HANA** -tietokantojen käyttöön liittyy joitakin rajoituksia:

* NVARCHAR-merkkijonot lyhennetään enimmäispituuteen, joka on 4000 Unicode-merkkiä.
* SMALLDECIMAL-toimintoa ei tueta.
* VARBINARY-toimintoa ei tueta.
* Kelvolliset päivämäärät ovat väliltä 30.12.1899-31.12.9999.


## <a name="next-steps"></a>Seuraavat vaiheet
Saat lisätietoja DirectQuerystä seuraavista resursseista:

* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)

