---
title: Laskettujen taulukkojen käyttö Power BI Desktopissa
description: Lasketut taulukot Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/02/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: c72387d40ddf4b193481a37dbcb40695668eab66
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/10/2020
ms.locfileid: "75837352"
---
# <a name="create-calculated-tables-in-power-bi-desktop"></a>Laskettujen taulukkojen luominen Power BI Desktopissa
Useimmissa tapauksissa luot taulukoita tuomalla tietoja malliisi ulkoisesta tietolähteestä. *Lasketuilla taulukoilla* voit kuitenkin lisätä uusia taulukoita perustuen tietoihin, jotka olet jo ladannut malliin. Sen sijaan, että hakisit ja lataisit arvoja uuden taulukkosi sarakkeisiin tietolähteestä, luot [Data Analysis Expression (DAX)](/dax/index) -kaavan, joka määrittää taulukon arvot.

DAX on kaavakieli relaatiotietojen käsittelyyn (esimerkiksi Power BI Desktopissa). DAX käsittää kirjaston, johon kuuluu yli 200 toimintoa, operaattoria ja rakennetta, mikä tarjoaa valtavan joustavuuden luotaessa kaavoja lähes minkä tahansa tietoanalyysitarpeen tulosten laskemista varten. Lasketut taulukot ovat paras vaihtoehto välituloksille ja tiedoille, jotka haluat tallentaa osana mallia sen sijaan, että ne laskettaisiin uudelleen tai kyselytuloksina. Voit esimerkiksi *yhdistää* tai *ristiliittää* kaksi olemassa olevaa taulukkoa.

Samalla tavalla kuin muissa Power BI Desktop -taulukoilla, lasketuilla taulukoillakin voi olla yhteyksiä toisiin taulukoihin. Lasketun taulukon sarakkeilla on tietotyypit ja muotoiluja – ja ne voivat kuulua tietoluokkaan. Voit nimetä sarakkeet miten haluat ja lisätä niitä raportin visualisointiin muiden kenttien tapaan. Lasketut taulukot lasketaan uudelleen, jos mikään niitä taulukoista, joista laskettu taulukko saa tietonsa, ladataan uudelleen tai päivitetään.

## <a name="create-a-calculated-table"></a>Lasketun taulukon luominen

Voit luoda laskettuja taulukoita Power BI Desktopin raportti- tai tietonäkymän **Uusi taulukko** -toiminnolla.

Kuvittele, että olet henkilöstöpäällikkö ja sinulla on kaksi työntekijätaulukkoa nimeltään **Northwest Employees** ja **Southwest Employees**. Haluat yhdistää nämä kaksi taulukkoa yhdeksi taulukoksi nimeltään **Western Region Employees**.

**Northwest Employees**

 ![](media/desktop-calculated-tables/calctables_nwempl.png)

**Southwest Employees**

 ![](media/desktop-calculated-tables/calctables_swempl.png)

Valitse Power BI Desktopin raportti- tai tietonäkymässä **Mallinnus**-välilehden **Laskutoimitukset**-ryhmästä **Uusi taulukko**. Tämä on hieman helpompaa tietonäkymässä, koska näet uuden lasketun taulukon heti.

 ![Uusi taulukko -toiminto tietonäkymässä](media/desktop-calculated-tables/calctables_formulabarempty.png)

Kirjoita kaavariville seuraava kaava:

```dax
Western Region Employees = UNION('Northwest Employees', 'Southwest Employees')
```

Uusi **Western Region Employees** -taulukko luodaan. Se näytetään samalla tavalla kuin muutkin taulukot **Kentät**-ruudussa. Voit luoda suhteita muihin taulukkoihin, lisätä mittareita ja laskettuja sarakkeista sekä lisätä taulukon kenttiä raportteihin samalla tavalla kuin missä tahansa taulukossa.

 ![Uusi laskettu taulukko](media/desktop-calculated-tables/calctables_westregionempl.png)

 ![Uusi taulukko -toiminto Kentät-ruudussa](media/desktop-calculated-tables/calctables_fieldlist.png)

## <a name="functions-for-calculated-tables"></a>Laskettujen taulukoiden toiminnot

Voit määrittää lasketun taulukon millä tahansa DAX-lausekkeella, joka palauttaa taulukon (mukaan lukien yksinkertainen viite toiseen taulukkoon). Esimerkki:

```dax
New Western Region Employees = 'Western Region Employees'
```

Tämä artikkeli sisältää vain lyhyen esittelyn lasketuista taulukoista. Voit käyttää DAX-lausekkeella laskettuja taulukoita ratkaistaksesi monia analyyttisia ongelmia. Tässä on joitakin tavallisimpia DAX-taulukkofunktioita, joita voit käyttää:

* DISTINCT
* VALUES
* CROSSJOIN
* UNION
* NATURALINNERJOIN
* NATURALLEFTOUTERJOIN
* INTERSECT
* CALENDAR
* CALENDARAUTO

[DAX-funktioviitteiden](/dax/dax-function-reference) ohjeartikkelissa voit tutustua näihin ja muihin DAX-funktioihin, jotka palauttavat taulukoita.

