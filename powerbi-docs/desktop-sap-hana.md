---
title: SAP HANA -käyttö Power BI Desktopissa
description: SAP HANA -käyttö Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/21/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7c70c4f4e5fec55ffd98d0156944c9973cffdb2a
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/09/2020
ms.locfileid: "75760292"
---
# <a name="connect-to-sap-hana-databases-in-power-bi-desktop"></a>Yhteyden muodostaminen SAP HANA -tietokantoihin Power BI Desktopissa
Voit nyt käyttää **SAP HANA** -tietokantoja Power BI Desktopilla. Jotta voit käyttää **SAP HANA** -tietokantoja, täytyy SAP HANA ODBC -ohjain olla asennettuna paikallisessa asiakastietokoneessa, jotta Power BI Desktopin **SAP HANA** -tietoyhteys toimii oikein. Voit ladata SAP HANA -asiakastyökalut [SAP Development -työkaluista](https://tools.hana.ondemand.com/#hanatools), joka sisältää tarvittavan ODBC-ohjaimen. Vaihtoehtoisesti voit hankkia sen [SAP Software Download Centeristä](https://support.sap.com/swdc). Etsi sieltä Windows-koneille tarkoitettu SAP HANA CLIENT -asiakasohjelmisto. Koska **SAP-ohjelmiston latauskeskus** muuttaa rakennettaan usein, emme voi antaa tarkempia ohjeita kyseisellä sivulla navigoimiseen.

Muodostaaksesi yhteyden **SAP HANA** -tietokantaan, valitse **Nouda tiedot > Tietokanta > SAP HANA -tietokanta** seuraavassa kuvassa esitetyllä tavalla:

![](media/desktop-sap-hana/sap-hana-1.png)

Kun muodostat yhteyden SAP HANA -tietokantaan, määritä palvelimen nimi. Määritä sen jälkeen portti avattavasta luettelosta ja syöteruudusta.

Tässä julkaisussa **SAP HANA** -tietokannan [DirectQuery](desktop-directquery-sap-hana.md)-tila on tuettu Power BI Desktopissa ja Power BI -palvelussa, ja voit julkaista ja ladata raportteja, joissa käytetään **SAP HANA** -tietokannan DirectQuery -tilaa, Power BI -palveluun. Voit myös julkaista ja ladata raportteja Power BI -palveluun, kun **SAP HANA** -tietokanta ei ole DirectQuery-tilassa.

## <a name="supported-features-for-sap-hana"></a>SAP HANA -tietokannan tuetut ominaisuudet
Tässä julkaisussa hyödynnetään monia **SAP HANA** -tietokannan ominaisuuksia, kuten näkyy seuraavassa luettelossa:

* **SAP HANA** -tietokannan Power BI -liitäntä käyttää SAP ODBC -ohjainta antamaan parhaan mahdollisen käyttäjäkokemuksen.
* **SAP HANA** tukee sekä DirectQuery- että tuontivaihtoehtoja.
* Power BI tukee HANA-tietomalleja (kuten analyysi- ja laskelmanäkymät) ja sen navigointi on optimoitu
* Voit myös käyttää **SAP HANA** -tietokannan kanssa Direct SQL -toimintoa yhdistääksesi rivi- ja saraketaulukkoja.
* Sisältää HANA-mallien optimoidun selaamisen.
* Power BI tukee **SAP HANA** -muuttujia ja syöttöparametreja.
* HDI-säilöön perustuvat laskentanäkymät
  * HDI-säilöön perustuvien laskentanäkymien tuki on julkisessa esikatselussa Power BI Desktopin elokuun 2019 versiossa. Jos haluat käyttää HDI-säilöpohjaisia laskentanäkymiä Power BI:ssä, varmista, että Power BI:n kanssa käyttämiesi HANA-tietokantojen käyttäjillä on oikeus käyttää HDI-suorituspalvelusäilöä, joka sisältää käytettävät näkymät. Jotta voit myöntää tämän oikeuden, sinun on luotava rooli, joka sallii oikeuden HDI-säilöön ja määrittää roolin HANA-tietokantakäyttäjälle, jota käytät Power BI:n kanssa (käyttäjällä on myös oltava oikeudet lukea järjestelmätaulukoita \_SYS\_BI-rakenteessa tavalliseen tapaan). Lisätietoja tietokantaroolien luomisesta ja määrittämisestä on virallisissa SAP-ohjeissa. [Tämä SAP-blogikirjoitus](https://blogs.sap.com/2018/01/24/the-easy-way-to-make-your-hdi-container-accessible-to-a-classic-database-user/) voi olla hyvä paikka aloittaa.
  * Huomaa, että HDI-pohjaisiin laskentanäkymiin liitetyissä HANA-muuttujissa on tällä hetkellä joitakin rajoituksia. Nämä rajoitukset johtuvat HANA-puolen virheistä, ja ne käsitellään tulevissa SAP HANA -versioissa. HANA-muuttujaa ei ensinnäkään voi käyttää HDI-säilöpohjaisen laskentanäkymän jaetussa sarakkeessa. Tämä rajoitus voidaan korjata päivittämällä HANA 2 -versioon 37.02 tai uudempaan tai HANA 2 -versioon 42 tai uudempaan. Toiseksi muuttujien ja parametrien monimerkintäiset oletusarvot eivät näy tällä hetkellä Power BI:n käyttöliittymässä. Tämä johtuu myös SAP HANA -virheestä; SAP ei ole vielä julkistanut korjausta.

## <a name="limitations-of-sap-hana"></a>SAP HANA -tietokantojen rajoitukset
**SAP HANA** -tietokantojen käyttöön liittyy joitakin rajoituksia:

* NVARCHAR-merkkijonot lyhennetään enimmäispituuteen, joka on 4000 Unicode-merkkiä.
* SMALLDECIMAL-toimintoa ei tueta.
* VARBINARY-toimintoa ei tueta.
* Kelvolliset päivämäärät ovat väliltä 30.12.1899-31.12.9999.


## <a name="next-steps"></a>Seuraavat vaiheet
Lisätietoja DirectQuery-kyselystä ja SAP HANA -tietokannoista saat seuraavista lähteistä:

* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [Ota SAP HANAn salaus käyttöön](desktop-sap-hana-encryption.md)


