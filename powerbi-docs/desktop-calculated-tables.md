---
title: Laskettujen taulukkojen käyttö Power BI Desktopissa
description: Lasketut taulukot Power BI Desktopissa
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 41017e1570a518e26305b6195531bcff889dbd9c
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/06/2018
ms.locfileid: "30976852"
---
# <a name="using-calculated-tables-in-power-bi-desktop"></a>Laskettujen taulukkojen käyttö Power BI Desktopissa
Lasketuilla taulukoilla voit lisätä malliin uuden taulukon. Sen sijaan, että hakisit ja lataisit arvoja uuden taulukkosi sarakkeisiin tietolähteestä, luot Data Analysis Expression (DAX) -kaavan, joka määrittelee taulukon arvot. Power BI Desktopissa laskettuja taulukoita luodaan uusi taulukko -toiminnolla raportti- tai tiedot-näkymässä.

Useimmissa tapauksissa tuot tietoja malliisi ulkoisesta tietolähteestä. Lasketut taulukot tarjoavat kuitenkin tiettyjä etuja. Lasketut taulukot ovat yleensä paras vaihtoehto välituloksien yhteydessä ja tiedoille, jotka haluat tallentaa osana mallia sen sijaan, että ne laskettaisiin uudelleen tai tallennettaisiin osana kyselyä.

Toisin kuin kyselyn osana luodut taulukot, raportti- tai tiedot-näkymässä luodut lasketut taulukot perustuvat tietoihin, jotka olet jo ladannut malliin. Saatat esimerkiksi yhdistää tai ristiliittää kaksi taulukkoa.

Samalla tavalla kuin normaaleilla taulukoilla, lasketuilla taulukoilla voi olla yhteyksiä toisiin taulukoihin. Lasketun taulukon sarakkeilla on tietotyypit, muotoiluja ja ne voivat kuulua tietoluokkaan. Voit nimetä sarakkeet miten haluat ja lisätä niitä raportin visualisointiin muiden kenttien tapaan. Lasketut taulukot lasketaan uudelleen, jos mikään niitä taulukoista, joista laskettu taulukko saa tietonsa, ladataan uudelleen tai päivitetään millään tavalla.

Lasketut taulukot laskevat tuloksia käyttämällä [Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) -kaavakieltä, joka on tarkoitettu käytettäväksi suhteellisten tietojen, kuten Power BI Desktopin tietojen, kanssa. DAX käsittää kirjaston, johon kuuluu yli 200 toimintoa, operaattoria ja rakennetta, mikä tarjoaa valtavan joustavuuden luotaessa kaavoja lähes minkä tahansa tietoanalyysitarpeen tulosten laskemista varten.

## <a name="lets-look-at-an-example"></a>Tarkastellaan esimerkkiä
Jeffillä, joka on Contoson projektipäällikkö, on taulukko, jossa näkyvät maan luoteisosassa olevat työntekijät, ja toinen, jossa näkyvät maan lounaisosassa olevat työntekijät. Jeff haluaa yhdistää nämä kaksi taulukkoa yhteen taulukkoon.

**LuoteisosanTyöntekijät**

 ![](media/desktop-calculated-tables/calctables_nwempl.png)

**LounaisosanTyöntekijät**

 ![](media/desktop-calculated-tables/calctables_swempl.png)

Näiden kahden taulukoiden yhdistäminen lasketun taulukon avulla on varsin helppoa. Jeff voi luoda lasketun taulukon sekä raporttinäkymässä että tietonäkymässä, mutta se on hieman helpompaa tietonäkymässä, koska hän voi nähdä uuden lasketun taulukkonsa välittömästi.

Jeff napsauttaa **Uusi taulukko** **Mallinnus**-välilehden **Tietonäkymässä**. Näyttöön avautuu kaavarivi.

 ![](media/desktop-calculated-tables/calctables_formulabarempty.png)

Jeff syöttää seuraavan kaavan:

 ![](media/desktop-calculated-tables/calctables_formulabarformula.png)

Luodaan uusi taulukko, jonka nimi on Länsialueen työntekijät.

 ![](media/desktop-calculated-tables/calctables_westregionempl.png)

Jeffin uusi Länsialueen työntekijät -taulukko näyttää Kentät-listassa täysin samalta kuin mikä tahansa muu taulukko. Hän voi luoda suhteita muihin taulukkoihin ja laskettuihin sarakkeisiin ja mittayksiköihin sekä lisätä taulukon kenttiä raportteihin, kuten missä tahansa taulukossa.

 ![](media/desktop-calculated-tables/calctables_fieldlist.png)

## <a name="functions-for-calculated-tables"></a>Laskettujen taulukoiden toiminnot
Lasketut taulukot voidaan määrittää millä tahansa DAX-lausekkeella, joka palauttaa taulukon, mukaan lukien yksinkertainen viite toiseen taulukkoon. Esimerkki:

 ![](media/desktop-calculated-tables/calctables_formulabarsimpleformula.png)

Voit käyttää DAX-lausekkeella laskettuja taulukoita ratkaistaksesi monia analyyttisia ongelmia. Olemme antaneet tässä vain lyhyen esittelyn laskettuihin taulukoihin. Tässä on joitakin tavallisimpia DAX-taulukkofunktioita, jotka saattavat olla hyödyllisiä, kun alat käyttämään laskettuja taulukoita:

* DISTINCT
* VALUES
* CROSSJOIN
* UNION
* NATURALINNERJOIN
* NATURALLEFTOUTERJOIN
* INTERSECT
* CALENDAR
* CALENDARAUTO

Katso [DAX-toimintojen viitemateriaaleista](https://msdn.microsoft.com/ee634396.aspx) nämä ja muut taulukon palauttavat DAX-funktioita.

