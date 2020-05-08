---
title: Excel-työkirjojen tuominen Power BI Desktopiin
description: Voit tuoda Power BI Desktopiin Excel-työkirjoja, joihin sisältyy Power Query -kyselyitä, Power Pivot -malleja ja Power View -laskentataulukoita.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/22/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 0a9880eea0511b942c3c7310a059caf5cd9415e1
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "77496838"
---
# <a name="import-excel-workbooks-into-power-bi-desktop"></a>Excel-työkirjojen tuominen Power BI Desktopiin
Power BI Desktopin avulla voit tuoda Power BI Desktopiin helposti Excel-työkirjoja, joihin sisältyy Power Query -kyselyitä, Power Pivot -malleja ja Power View -laskentataulukoita. Power BI Desktop luo automaattisesti raportteja ja visualisointeja Excel-työkirjan perusteella. Kun raportit on tuotu, voit parantaa ja tarkentaa niitä Power BI Desktopin avulla käyttämällä olemassa olevia ominaisuuksia ja uusia ominaisuuksia, jotka julkaistaan Power BI Desktopin kunkin kuukausipäivityksen yhteydessä.

## <a name="how-do-i-import-an-excel-workbook"></a>Miten Excel-työkirja tuodaan?
1. Jos haluat tuoda Excel-työkirjan Power BI Desktopiin, valitse **Tiedosto** > **Tuo** > **Power Query, Power Pivot, Power View**.

   ![Excel-työkirjan tuonti](media/desktop-import-excel-workbooks/importexceltopbi_1.png)


2. Valitse tuotava Excel-työkirja **Avaa**-ikkunasta. 

   Vaikka työkirjan objektien kokoa tai määrää ei ole tällä hetkellä rajoitettu, Power BI Desktopilla kestää kauemmin suurien työkirjojen analysoinnissa ja tuonnissa.

   > [!NOTE]
   > Voit ladata tai tuoda Excel-tiedostoja jaetuista OneDrive for Business -kansioista tai Office 365 -ryhmän kansioista käyttämällä Excel-tiedoston URL-osoitetta ja syöttämällä sen Power BI Desktopin Verkko-tietolähteeseen. Sinun on suoritettava muutama vaihe, jotta OneDrive for Business -URL-osoitteen muotoilu olisi oikein. Katso lisätietoja ja oikeat vaiheet kohdasta [OneDrive for Business -linkkien käyttö Power BI Desktopissa](desktop-use-onedrive-business-links.md).
   > 
   > 

3. Valitse esiin tulevasta valintaikkunasta **Aloita**.

   ![Excel-työkirjan sisällön tuonti](media/desktop-import-excel-workbooks/import-excel-power-bi-5.png)


   Power BI Desktop analysoi työkirjan ja muuntaa sen Power BI Desktop -tiedostoksi (.pbix). Tämä toiminto on kertaluonteinen tapahtuma: kun Power BI Desktop -tiedosto on näiden vaiheiden myötä luotu, Power BI Desktop -tiedoston ja alkuperäisen Excel-työkirjan välillä ei ole riippuvuutta, ja uutta tiedostoa voi muokata ja sen voi tallentaa ja jakaa vaikuttamatta alkuperäiseen työkirjaan.

   Kun tuonti on tehty, esiin tulee yhteenvetosivu, jossa kuvataan muunnetut kohteet sekä luetellaan mahdolliset kohteet, joita ei voitu tuoda.

   ![Yhteenvetosivun tuonti](media/desktop-import-excel-workbooks/importexceltopbi_3.png)

4. Valitse **Sulje**. 

   Power BI Desktop tuo Excel-työkirjan ja lataa raportin työkirjan sisällön perusteella.

   ![Ladattu tuontiraportti](media/desktop-import-excel-workbooks/importexceltopbi_4.png)

Kun työkirja on tuotu, voit jatkaa raportin käsittelemistä. Voit luoda uusia visualisointeja, lisätä tietoja tai luoda uusia raporttisivuja käyttämällä mitä tahansa Power BI Desktopiin sisältyviä ominaisuuksia ja toimintoja.

## <a name="which-workbook-elements-are-imported"></a>Mitkä työkirjan elementit tuodaan?
Power BI Desktop voi tuoda seuraavat elementit, joita kutsutaan Excelissä yleisesti nimellä *objektit*.

| Objekti Excel-työkirjassa | Lopullinen tulos Power BI Desktop -tiedostossa |
| --- | --- |
| Power Query -kyselyt |Kaikki Excelin Power Query -kyselyt muunnetaan kyselyiksi Power BI Desktopissa. Jos Excel-työkirjaan on määritetty kyselyryhmiä, sama organisaatio replikoidaan Power BI Desktopiin. Kaikki kyselyt ladataan, ellei niitä ole määritetty Excelin **Tuo tiedot** -valintaikkunassa **Luo vain yhteys** -tilaan. Lataustoimintaa voi mukauttaa valitsemalla **Ominaisuudet** Power Query -editorin **Aloitus**-välilehdellä Power BI Desktopissa. |
| Power Pivotin ulkoiset tietoyhteydet |Kaikki Power Pivotin ulkoiset tietoyhteydet muunnetaan kyselyiksi Power BI Desktopissa. |
| Linkitetyt taulukot tai nykyisen työkirjan taulukot |Jos Excelissä on laskentataulukon taulukko, joka on linkitetty tietomalliin tai kyselyyn (käyttämällä *Taulukosta*-toimintoa tai *Excel.CurrentWorkbook()* -funktiota M:ssä), näytetään seuraavat vaihtoehdot: <ol><li><b>Tuo taulukko Power BI Desktop -tiedostoon</b>. Tämä taulukko on kertaluonteinen tilannevedos tiedoista, jonka jälkeen taulukon tiedot ovat vain luku -muodossa Power BI Desktopissa. Tämän vaihtoehdon avulla luotujen taulukoiden kokorajoitus on miljoona merkkiä (yhteensä, kaikki sarakeotsikot ja solut yhteen laskettuina).</li><li><b>Säilytä yhteys alkuperäiseen työkirjaan</b>. Vaihtoehtoisesti voit säilyttää yhteyden alkuperäiseen Excel-työkirjaan, ja Power BI Desktop noutaa kyseisen taulukon uusimman sisällön kunkin päivityksen yhteydessä samaan tapaan kuin mikä tahansa muu kysely, joka on luotu Excel-työkirjaa vasten Power BI Desktopissa.</li></ul> |
| Tietomallin lasketut sarakkeet, mittarit, suorituskykyilmaisimet, tietoluokat ja suhteet |Nämä tietomallin objektit muunnetaan Power BI Desktopin vastaaviksi objekteiksi. Huomaa, että on tiettyjä tietoluokkia, jotka eivät ole käytettävissä Power BI Desktopissa, kuten Kuva. Näissä tapauksissa tietoluokkaa koskevat tiedot palautetaan kyseessä olevien sarakkeiden osalta. |
| Power View -laskentataulukot |Uusi raporttisivu luodaan jokaiselle Excelin Power View -laskentataulukolle. Näiden raporttisivujen nimi ja järjestys vastaavat alkuperäistä Excel-työkirjaa. |

## <a name="are-there-any-limitations-to-importing-a-workbook"></a>Onko työkirjan tuomiselle rajoituksia?
Työkirjan tuomiselle Power BI Desktopiin on joitakin rajoituksia:

* **Ulkoiset yhteydet SQL Server Analysis Servicesin taulukkomalleihin:** Excel 2013:ssa on mahdollista luoda yhteys SQL Server Analysis Servicesin taulukkomalleihin ja luoda Power View -raportteja näiden mallien lisäksi ilman, että tietoja tarvitsee tuoda. Tätä yhteystyyppiä ei tällä hetkellä tueta osana Excel-työkirjojen tuomista Power BI Desktopiin. Vaihtoehtoisena menetelmänä sinun on luotava nämä ulkoiset yhteydet uudelleen Power BI Desktopissa.
* **Hierarkiat:** Tämäntyyppistä tietomalliobjektia ei tällä hetkellä tueta Power BI Desktopissa. Näin ollen hierarkiat ohitetaan osana Excel-työkirjan tuomista Power BI Desktopiin.
* **Binaarista tietoa sisältävät sarakkeet:** Tämäntyyppistä tietomallisaraketta ei tällä hetkellä tueta Power BI Desktopissa. Binaarista tietoa sisältävät sarakkeet poistetaan tuloksena olevasta taulukosta Power BI Desktopissa.
* **Power View -elementit, joita ei tueta:** On joitakin Power View -ominaisuuksia, jotka eivät ole käytettävissä Power BI Desktopissa, kuten teemat tai tietyntyyppiset visualisoinnit (pistekaavio, jossa on PlayAxis, porautumistoiminnot jne.). Visualisoinnit, joita ei tueta, johtavat sanomiin *Visualisointia ei tueta* niitä vastaavissa Power BI Desktop -raportin sijainneissa; voit poistaa tai määrittää ne uudelleen tarpeen mukaan.
* **Nimetyt alueet, jotka käyttävät** ***Taulukosta***-toimintoa **Power Queryssä tai** ***Excel.CurrentWorkbook***-funktiota **M:ssä:** Näiden nimetyn alueen tietojen tuomista Power BI Desktopiin ei tueta tällä hetkellä, mutta se on suunniteltu päivitys. Tällä hetkellä nämä nimetyt alueet ladataan Power BI Desktopiin yhteytenä ulkoiseen Excel-työkirjaan.
* **PowerPivot SSRS:ään:** PowerPivotin ulkoisia yhteyksiä SQL Server Reporting Servicesiin (SSRS) ei tueta tällä hetkellä, koska kyseinen tietolähde ei ole käytettävissä Power BI Desktopissa.

