---
title: Oracle-tietokantaan yhdistäminen
description: Ohjeet ja Oracle-tietokannan Power BI Desktopiin yhdistämiseen tarvittavat ladattavat tiedostot
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/05/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f43981121211c900b3cb4506b830ce09da3b5e20
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83295487"
---
# <a name="connect-to-an-oracle-database"></a>Oracle-tietokantaan yhdistäminen
Yhteyden muodostaminen Oracle-tietokantaan Power BI Desktopilla edellyttää, että tietokoneessa on asennettuna Power BI Desktop ja oikea Oracle-asiakasohjelmisto. Käytettävä Oracle-asiakasohjelmisto määräytyy asennetun Power BI Desktop ‑version mukaan: se on joko 32- tai 64-bittinen.

Tuetut Oracle-versiot: 
- Oracle 9 ja uudemmat
- Oracle-asiakasohjelmisto 8.1.7 ja uudemmat

> [!NOTE]
> Jos määrität Oracle-tietokantaa Power BI Desktopia, paikallista tietoyhdyskäytävää tai Power BI -raporttipalvelinta varten, lue artikkeli [Oracle-yhteystyyppi](https://docs.microsoft.com/sql/reporting-services/report-data/oracle-connection-type-ssrs?view=sql-server-ver15). 


## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Asennettuna olevan Power BI Desktop -version selvittäminen
Voit selvittää, kumpi Power BI Desktop -versio sinulla on asennettuna, valitsemalla **Tiedosto** > **Ohje** > **Tietoja** ja tarkistamalla sitten tiedot **Versio**-riviltä. Seuraavassa kuvassa asennettuna on Power BI Desktopin 64-bittinen versio:

![Power BI Desktop ‑versio](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Oracle-asiakasohjelman asentaminen
- Jos sinulla on Power BI Desktopin 32-bittinen versio, [lataa ja asenna Oraclen 32-bittinen asiakasohjelma](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html).

- Jos sinulla on Power BI Desktopin 64-bittinen versio, [lataa ja asenna Oraclen 64-bittinen asiakasohjelma](https://www.oracle.com/database/technologies/odac-downloads.html).

> [!NOTE]
> Varmista Oracle-asiakasohjelman määrityksen aikana, että otat käyttöön asetuksen *Configure ODP.NET and/or Oracle Providers for ASP.NET at machine-wide level* (Määritä ODP-NET ja/tai Oracle-palveluntarjoajat ASP.NETiä varten) valitsemalla sitä vastaavan valintaruudun ohjatun määritystoiminnon aikana. Jotkin Oracle-asiakasohjelman ohjatun toiminnon versiot valitsevat valintaruudun oletusarvoisesti, toiset eivät. Varmista, että valintaruutu on valittuna, jotta Power BI voi muodostaa yhteyden Oracle-tietokantaasi.

## <a name="connect-to-an-oracle-database"></a>Oracle-tietokantaan yhdistäminen
Asennettuasi tietokoneeseen Oracle-asiakasohjelmaa vastaavan ohjaimen, voit muodostaa yhteyden Oracle-tietokantaan. Voit muodostaa yhteyden seuraavasti:

1. Valitse **Aloitus**-välilehdeltä **Nouda tiedot**. 

2. Valitse näytölle avautuvasta **Nouda tiedot**-ikkunasta tarvittaessa vaihtoehto **Lisää** ja valitse sitten **Tietokanta** > **Oracle-tietokanta** ja **Yhdistä**.
   
   ![Yhteyden muodostaminen Oracle-tietokantaan](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. Kirjoita avautuvaan **Oracle-tietokanta**-valintaikkunaan **Palvelin**-kohtaan palvelimen nimi ja valitse **OK**. Jos SID-tunnus vaaditaan, määritä se käyttämällä muotoa *PalvelimenNimi/SID*, jossa *SID* on tietokannan yksilöivä nimi. Jos *PalvelimenNimi/SID*-muoto ei toimi, kokeile *PalvelimenNimi/PalvelunNimi*-muotoa, jossa *PalvelunNimi* on yhteyden muodostuksessa käyttämäsi alias.


   ![Oracle-palvelimen nimen antaminen](media/desktop-connect-oracle-database/connect-oracle-database_3.png)

   > [!TIP]
   > Jos sinulla ilmenee tässä vaiheessa vaikeuksia yhteyden muodostamisessa, kokeile käyttää **Palvelin**-kentässä seuraavaa muotoa: *(DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=isäntänimi)(PORT=portin_nro))(CONNECT_DATA=(SERVICE_NAME=palvelun_nimi)))*
   
3. Jos haluat tuoda tietoja alkuperäisen tietokantakyselyn avulla, kirjoita kysely **SQL-lause**-ruutuun, jonka saa näkyviin laajentamalla **Oracle-tietokanta**-valintaikkunan **Lisäasetukset**-osion.
   
   ![Lisäasetukset-osion laajentaminen](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Kun olet kirjoittanut Oracle-tietokannan tiedot **Oracle-tietokanta**-valintaikkunaan (myös valinnaiset tiedot, kuten SID-tunnuksen tai alkuperäisen tietokantakyselyn), muodosta yhteys valitsemalla **OK**.
5. Jos Oracle-tietokanta edellyttää tietokannan käyttäjän tunnistetietoja, kirjoita kyseiset tiedot valintaikkunaan pyydettäessä.


## <a name="troubleshooting"></a>Vianmääritys

Jos olet ladannut Power BI Desktopin Microsoft Storesta, et ehkä pysty muodostamaan yhteyttä Oracle-tietokantoihin Oracle-ohjainongelman vuoksi. Jos kohtaat tämän ongelman, saat virheviestin: *Objektiviittausta ei ole määritetty.* Voit korjata ongelman jommallakummalla seuraavista tavoista:

* Lataa Power BI Desktop [Latauskeskuksesta](https://www.microsoft.com/download/details.aspx?id=58494) Microsoft Storen sijaan.

* Jos haluat käyttää Microsoft Store -versiota, kopioi paikallisessa tietokoneessa oraons.dll kohteesta _12.X.X\client_X_ kohteeseen _12.X.X\client_X\bin_, jossa _X_ tarkoittaa version ja hakemiston numeroa.

Jos näet Power BI Gatewayssä virhesanoman *Objektiviittausta ei ole määritetty*, kun muodostat yhteyttä Oracle-tietokantaan, noudata [Tietolähteen hallinta – Oracle](service-gateway-onprem-manage-oracle.md) -artikkelin ohjeita.

Jos käytät Power BI -raporttipalvelinta, lue ohjeet artikkelissa [Oracle-yhteystyyppi](https://docs.microsoft.com/sql/reporting-services/report-data/oracle-connection-type-ssrs?view=sql-server-ver15).
