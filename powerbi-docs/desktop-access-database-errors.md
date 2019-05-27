---
title: Käyttöoikeuksien ja .XLS -tuontiongelmien ratkaiseminen Power BI Desktopissa
description: Access-tietokantojen ja .XLS -laskentataulukoiden tuomisen ongelmien korjaaminen Power BI Desktopissa ja Power Queryssa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/06/2019
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 6e504d472e4fabb5c336f36e1bef50ae4920ef17
ms.sourcegitcommit: b11e908650379913d00673215e3eaf25d712b122
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/07/2019
ms.locfileid: "65239772"
---
# <a name="resolve-issues-importing-access-and-xls-files-in-power-bi-desktop"></a>Ratkaise Käyttöoikeuksien ja .XLS-tiedostojen tuontiongelmat Power BI Desktopissa
**Power BI Desktopissa** sekä **Access-tietokannat** että **Excel-työkirjojen** aikaisemmat versiot (Excel 97-2003 -tyypin .XLS-tiedostot) käyttävät *Access-tietokantamoduulia*. On olemassa kolme yleistä tilannetta, jotka estävät käyttöoikeustietokantamoduulia toimimasta kunnolla:

## <a name="situation-1-no-access-database-engine-installed"></a>Esimerkki 1: Käyttöoikeustietokantamoduulia ei ole asennettu
Kun Power BI Desktop -virheilmoitus ilmaisee, ettei Access-tietokantamoduulia ole asennettu, tulee Access-tietokantamoduulista asentaa joko 32- tai 64-bittinen versio, joka vastaa käytössä olevaa Power BI Desktop -versiota. Voit asentaa Access-tietokantamoduulin [lataussivulta](http://www.microsoft.com/download/details.aspx?id=13255).

>[!NOTE]
>Jos asennettu käyttöoikeustietokantamoduulin versio on eri kuin Microsoft Officen asennettu bittiversio, Office-sovellukset eivät voi käyttää käyttöoikeustietokantamoduulia.

## <a name="situation-2-the-access-database-engine-bit-version-32-bit-or-64-bit-is-different-from-your-power-bi-desktop-bit-version"></a>Esimerkki 2: Käyttöoikeustietokantamoduulin bittiversio (32- tai 64-bittinen) on eri kuin käyttämäsi Power BI Desktopin bittiversio
Tässä tilanteessa on usein ongelmana, että Microsoft Officesta on asennettu 32-bittinen versio ja Power BI Desktopista 64-bittinen versio. Päinvastainen voi myös tapahtua, ja bittiversion ristiriita aiheutua kummassakin tapauksessa (jos käytössäsi on Office 365 -tilaus, katso **Esimerkki 3** toisenlaisen ongelman ratkaisemiseksi). Kaikki seuraavat ratkaisut korjaavat tämä bittiversio ristiriidan:

1. Muuta Power BI Desktopin versio vastaamaan Microsoft Office -asennuksesi bittiversiota. Muuttaaksesi Power BI Desktopin bittiversion, poista Power BI Desktopin asennus ja asenna sitten Power BI Desktopin bittiversio, joka vastaa käyttämääsi Office-versiota. Valitaksesi version Power BI Desktopille, valitse lataussivulta **Latauksen lisäasetukset**.
   
   ![](media/desktop-access-database-errors/desktop-access-errors-1.png)
   
   Valitse avautuvalta lataussivulta kielesi ja napauta sitten **Lataa**-painiketta. Valitse näkyviin tulevassa näytössä PBIDesktop.msi-valintaruutu 32-bittisen version tapauksessa tai PBIDesktop_x64.msi-valintaruutu 64-bittisen version tapauksessa. Seuraavassa ruudussa 64-bittinen versio on valittuna.
   
   ![](media/desktop-access-database-errors/desktop-access-errors-2.png)
   
   >[!NOTE]
   >Käytettäessä Power BI Desktopin 32-bittistä versiota ja erittäin suurten tietomallien ollessa kyseessä, muistin riittävyyden kanssa saattaa tulla ongelmia.
2. Muuta Microsoft Office bittiversiosi vastaamaan asennettua Power BI Desktop -versiota. Muuttaaksesi Microsoft Officen bittiversion, poista Officen asennus ja asenna sitten versio, joka vastaa Power BI Desktopin asennusta.
3. Jos virhe ilmeni yrittäessäsi avata .XLS-tiedostoa (Excel 97-2003 -työkirjaa), voit välttää Access-tietokantamoduulin käytön avaamalla .XLS-tiedoston Excelissä ja tallentamalla sen XLSX-tiedostona.
4. Jos kolme edellistä ratkaisua eivät ole toteutettavissa, on käyttöoikeustietokantamoduulista mahdollista asentaa sen molemmat versiot, mutta tämä *ei ole* suositeltu ratkaisu. Asentamalla molemmat versiot, ongelma ratkeaa Excelin Power Queryn ja Power BI Desktopin kohdalta, mutta johtaa virheisiin ja ongelmiin kaikissa niissä sovelluksissa, jotka käyttävät automaattisesta (oletuksena) ensimmäisenä asennettua käyttöoikeustietokantamoduulin versiota. Asentaaksesi molemmat käyttöoikeustietokantamoduulin bittiversiot [lataa](http://www.microsoft.com/download/details.aspx?id=13255) molemmat versiot ja asenna ne kummatkin käyttämällä */passiivista* -valitsinta. Esimerkki:
   
       c:\users\joe\downloads\AccessDatabaseEngine.exe /passive
   
       c:\users\joe\downloads\AccessDatabaseEngine_x64.exe /passive

## <a name="situation-3-trouble-using-access-or-xls-files-with-an-office-365-subscription"></a>Esimerkki 3: Ongelmia käyttöoikeuksien tai .XLS-tiedostojen kanssa yhdessä Office 365 -tilin kanssa
Jos käytät Office 365 -tiliä ja joko **Office 2013** tai **Office 2016** -versiota, käyttöoikeustietokantamoduulin tarjoaja on rekisteröity virtuaalisessa rekisterisijainnissa, jota voivat käyttää *vain* Officen prosessit. Tämän seurauksena koostemoduuli (joka on vastuussa ei-Office 365 Excelin ja Power BI Desktopin suorittamisesta), joka ei ole Office-prosessi, ei saa yhteyttä  Access-tietokantamoduulin tarjoajaan.

Korjataksesi tämän tilanteen, voit [ladata ja asentaa uudelleenjaetun Access-tietokantamoduulin](http://www.microsoft.com/download/details.aspx?id=13255), joka vastaa asennettua Power BI Desktopin bittiversiota (lisää tietoa bittiversioista ylempänä ).

## <a name="other-situations-that-cause-import-issues"></a>Muut ongelmia aiheuttavat tilanteet
Pyrimme kattamaan mahdollisimman monta Käyttöoikeuksien tai .XLS-tiedostojen kanssa ilmenevää ongelmaa. Jos kohtaat ongelman, jota ei tässä artikkelissa ole käsitelty, lähetä kysymyksesi ongelmasta [Power BI -tukeen](https://powerbi.microsoft.com/support/). Tutkimme säännöllisesti ongelmia, joita useilla asiakkailla saattaa ilmetä, ja lisäämme artikkeleihin niitä koskevat ohjeet.

