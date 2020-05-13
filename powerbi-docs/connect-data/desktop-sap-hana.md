---
title: SAP HANA -käyttö Power BI Desktopissa
description: SAP HANA -käyttö Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 9b205a0ae9b58acf054a9afe43196e77ee404c84
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83289116"
---
# <a name="connect-to-sap-hana-databases-in-power-bi-desktop"></a>Yhteyden muodostaminen SAP HANA -tietokantoihin Power BI Desktopissa

Voit nyt käyttää *SAP HANA* -tietokantoja Power BI Desktopilla. Jotta voit käyttää SAP HANA -tietokantoja, paikalliseen asiakastietokoneeseen on asennettava SAP HANA ODBC -ohjain, jotta Power BI Desktopin SAP HANA -tietoyhteys toimii oikein. Voit ladata SAP HANA -asiakastyökalut [SAP Development -työkaluista](https://tools.hana.ondemand.com/#hanatools), joka sisältää tarvittavan ODBC-ohjaimen. Voit myös hankkia sen [SAP-ohjelmiston latauskeskuksesta](https://support.sap.com/en/my-support/software-downloads.html). Etsi ohjelmistoportaalista Windows-tietokoneille tarkoitettu *SAP HANA CLIENT* -asiakasohjelmisto. Koska SAP-ohjelmiston latauskeskus muuttaa rakennettaan usein, emme voi antaa tarkempia ohjeita kyseisellä sivulla siirtymiseen.

Muodostaaksesi yhteyden SAP HANA -tietokantaan, valitse **Nouda tiedot**, valitse **Tietokanta** > **SAP HANA -tietokanta**, ja valitse sitten **Yhdistä**:

![SAP HANA -tietokanta, Nouda tiedot -valintaikkuna, Power BI Desktop](media/desktop-sap-hana/sap-hana-1.png)

Kun muodostat yhteyden SAP HANA -tietokantaan, määritä palvelimen nimi. Määritä sen jälkeen portti avattavasta luettelosta ja syöttöruudusta.

Tässä versiossa SAP HANA -tietokannan [DirectQuery](desktop-directquery-sap-hana.md) -tilaa tuetaan Power BI Desktopissa ja Power BI -palvelussa. Voit myös julkaista ja ladata raportteja, jotka käyttävät SAP HANA -tietokantaa, DirectQuery-tilassa Power BI -palveluun. Voit myös julkaista ja ladata raportteja Power BI -palveluun, kun et käytä SAP HANA -tietokantaa DirectQuery-tilassa.

## <a name="supported-features-for-sap-hana"></a>SAP HANA -tietokannan tuetut ominaisuudet

Tässä versiossa hyödynnetään monia SAP HANA -tietokannan ominaisuuksia, kuten näkyy seuraavassa luettelossa:

* SAP HANA -tietokannan Power BI -liitäntä käyttää SAP ODBC -ohjainta antamaan parhaan mahdollisen käyttäjäkokemuksen.

* SAP HANA tukee sekä DirectQuery- että tuontivaihtoehtoja.

* Power BI tukee HANA-tietomalleja, kuten analyysi- ja laskelmanäkymiä, ja sen selaus on optimoitu.

* Voit myös käyttää SAP HANA -tietokannan kanssa Direct SQL -toimintoa yhdistääksesi rivi- ja saraketaulukkoja.

* Power BI sisältää HANA-mallien optimoidun selauksen.

* Power BI tukee SAP HANA -muuttujia ja -syöttöparametreja.

* Power BI tukee HDI-säilöön perustuvia laskentanäkymiä.

  * HDI-säilöön perustuvien laskentanäkymien tuki on julkisessa esikatselussa Power BI Desktopin elokuun 2019 versiossa. Jos haluat käyttää HDI-säilöpohjaisia laskentanäkymiä Power BI:ssä, varmista, että Power BI:n kanssa käyttämiesi HANA-tietokantojen käyttäjillä on oikeus käyttää HDI-suorituspalvelusäilöä, joka sisältää käytettävät näkymät. Jos haluat myöntää tämän käyttöoikeuden, luo rooli, joka sallii käyttöoikeuden HDI-säilöön. Määritä sitten HANA-tietokannan käyttäjälle rooli, jota käytät Power BI:n kanssa. (Tällä käyttäjällä on myös oltava oikeudet lukea järjestelmätaulukoista \_SYS\_BI-rakenteessa tavalliseen tapaan.) Lisätietoja tietokantaroolien luomisesta ja määrittämisestä on virallisissa SAP-ohjeissa. [Tämä SAP-blogikirjoitus](https://blogs.sap.com/2018/01/24/the-easy-way-to-make-your-hdi-container-accessible-to-a-classic-database-user/) voi olla hyvä paikka aloittaa.

  * HDI-pohjaisiin laskentanäkymiin liitetyissä HANA-muuttujissa on tällä hetkellä joitakin rajoituksia. Nämä rajoitukset johtuvat HANA-tietokannan virheistä.
  
    HANA-muuttujaa ei ensinnäkään voi käyttää HDI-säilöpohjaisen laskentanäkymän jaetussa sarakkeessa. Voit korjata tämän rajoituksen päivittämällä HANA 2 -versioon 37.02 tai uudempaan tai HANA 2 -versioon 42 tai uudempaan. Toiseksi muuttujien ja parametrien monimerkintäiset oletusarvot eivät näy tällä hetkellä Power BI:n käyttöliittymässä. Tämä rajoitus johtuu SAP HANA -tietokannan virheestä, mutta SAP ei ole vielä julkistanut korjausta.

## <a name="limitations-of-sap-hana"></a>SAP HANA -tietokantojen rajoitukset

SAP HANA -tietokantojen käyttöön liittyy myös joitakin rajoituksia:

* NVARCHAR-merkkijonot lyhennetään enimmäispituuteen, joka on 4 000 Unicode-merkkiä.
* SMALLDECIMAL-toimintoa ei tueta.
* VARBINARY-toimintoa ei tueta.
* Kelvolliset päivämäärät ovat väliltä 30.12.1899–31.12.9999.

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja DirectQuery-kyselystä ja SAP HANA -tietokannoista saat seuraavista resursseista:

* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQueryn käyttö Power BI:ssä](desktop-directquery-about.md)
* [Power BI -tietolähteet](power-bi-data-sources.md)
* [Ota SAP HANAn salaus käyttöön](desktop-sap-hana-encryption.md)
