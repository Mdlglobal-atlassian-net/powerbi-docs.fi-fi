---
title: SAP HANA -käyttö Power BI Desktopissa
description: SAP HANA -käyttö Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f40ed1b3950ace0b3cb362a22670e98c3ef83112
ms.sourcegitcommit: e62889690073626d92cc73ff5ae26c71011e012e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/23/2019
ms.locfileid: "69985673"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>SAP HANA -käyttö Power BI Desktopissa
Voit nyt käyttää **SAP HANA** -tietokantoja Power BI Desktopilla. Jotta voit käyttää **SAP HANA** -tietokantoja, täytyy SAP HANA ODBC -ohjain olla asennettuna paikallisessa asiakastietokoneessa, jotta Power BI Desktopin **SAP HANA** -tietoyhteys toimii oikein. Voit ladata SAP HANA ODBC -ohjaimen [SAP-ohjelmiston latauskeskuksesta](https://support.sap.com/swdc). Etsi sieltä Windows-koneille tarkoitettu SAP HANA CLIENT -asiakasohjelmisto. Koska **SAP-ohjelmiston latauskeskus** muuttaa rakennettaan usein, emme voi antaa tarkempia ohjeita kyseisellä sivulla navigoimiseen.

Muodostaaksesi yhteyden **SAP HANA** -tietokantaan, valitse **Nouda tiedot > Tietokanta > SAP HANA -tietokanta** seuraavassa kuvassa esitetyllä tavalla:

![](media/desktop-sap-hana/sap-hana-1.png)

Kun yhteys SAP HANA -tietokantaan muodostetaan, määritä palvelimen nimi ja portti muodossa *palvelin:portti* – seuraavassa kuvassa on esimerkki, jossa palvelimen nimi on *ServerXYZ* ja porti on *30015*.

![](media/desktop-sap-hana/sap-hana-2.png)

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
  * HDI-säilöön perustuvien laskentanäkymien tuki on julkisessa esikatselussa Power BI Desktopin elokuun 2019 versiossa. Jos haluat käyttää HDI-säilöpohjaisia laskentanäkymiä Power BI:ssä, varmista, että Power BI:n kanssa käyttämiesi HANA-tietokantojen käyttäjillä on oikeus käyttää HDI-suorituspalvelusäilöä, joka sisältää käytettävät näkymät. Jotta voit myöntää tämän oikeuden, sinun on luotava rooli, joka sallii oikeuden HDI-säilöön ja määrittää roolin HANA-tietokantakäyttäjälle, jota käytät Power BI:n kanssa (käyttäjällä on myös oltava oikeudet lukea järjestelmätaulukoita \_SYS\_BI-rakenteessa tavalliseen tapaan). Lisätietoja tietokantaroolien luomisesta ja määrittämisestä on virallisissa SAP-ohjeissa. [Tämä SAP-blogikirjoitus](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fblogs.sap.com%2F2018%2F01%2F24%2Fthe-easy-way-to-make-your-hdi-container-accessible-to-a-classic-database-user%2F&data=02%7C01%7Cv-adbold%40microsoft.com%7Cf7e0a405fe334598ba0608d7096ef5b4%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636988244476739316&sdata=PuRu61GPRYp34mLuGbQk6gdbRikdgbxfqo8q1RBQtm0%3D&reserved=0) voi olla hyvä paikka aloittaa.
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


