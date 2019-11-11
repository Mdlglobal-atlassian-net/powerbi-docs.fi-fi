---
title: Laskettujen sarakkeiden käyttäminen Power BI Desktopissa
description: Lasketut sarakkeet Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 10c6f9f512c1b8c837842247d9dc928e8e065451
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73876623"
---
# <a name="using-calculated-columns-in-power-bi-desktop"></a>Laskettujen sarakkeiden käyttäminen Power BI Desktopissa
Laskettujen sarakkeiden avulla voit lisätä uutta tietoa taulukkoon, joka on jo mallissasi. Sen sijaan, että hakisit ja lataisit arvoja uuteen sarakkeeseen tietolähteestä, luot Data Analysis Expressions (DAX) -kaavan, joka määrittää sarakkeen arvot. Power BI Desktopissa lasketut sarakkeet luodaan käyttämällä raporttinäkymän Uusi sarake -toimintoa.

Toisin kuin mukautetut sarakkeet, jotka on luotu osana kyselyä käyttämällä kyselyeditorin toimintoa Lisää mukautettu sarake, raporttinäkymässä tai tietonäkymässä luodut lasketut sarakkeet perustuvat tietoihin, jotka olet jo ladannut malliin. Saatat esimerkiksi päättää liittää yhteen arvoja kahdessa erillisessä mutta toisiinsa liittyvässä taulukossa olevista kahdesta eri sarakkeesta, tehdä lisäyksen tai poimia alimerkkijonoja.

Luomasi lasketut sarakkeet tulevat näkyviin Kentät-luettelossa niin kuin mikä tahansa muu kenttä, mutta niillä on erityinen kuvake, josta näkyy niiden arvojen olevan kaavan tulos. Voit nimetä sarakkeet miten haluat ja lisätä niitä raportin visualisointiin muiden kenttien tapaan.

![](media/desktop-calculated-columns/calccolinpbid_fields.png)

Lasketut sarakkeet laskevat tuloksia käyttämällä [Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) -kaavakieltä, joka on tarkoitettu käytettäväksi suhteellisten tietojen, kuten Power BI Desktopin tietojen, kanssa. DAX käsittää kirjaston, johon kuuluu yli 200 toimintoa, operaattoria ja rakennetta, mikä tarjoaa valtavan joustavuuden luotaessa kaavoja lähes minkä tahansa tietoanalyysitarpeen tulosten laskemista varten. Lisätietoja DAX-kielestä on tämän artikkelin lopussa olevassa osassa Lue lisää.

DAX-kaavat ovat samankaltaisia kuin Excel-kaavat. DAX käsittää itse asiassa monia samoja funktioita kuin Excel. DAX-funktiot on kuitenkin tarkoitettu sellaisten tietojen käsittelyyn, jotka on vuorovaikutteisesti viipaloitu tai suodatettu raportissa, kuten Power BI Desktopin tiedot. Toisin kuin Excelissä, jossa kaava voi olla erilainen jokaiselle taulukon riville, luodessasi uuden DAX-kaavan uudelle sarakkeelle se laskee tuloksen taulukon jokaiselle riville. Sarakkeen arvot lasketaan uudelleen tarpeen mukaan esimerkiksi silloin, kun pohjana olevat tiedot päivitetään ja arvot ovat muuttuneet.

## <a name="lets-look-at-an-example"></a>Tarkastellaan esimerkkiä
Jeff on Contoson kuljetuspäällikkö ja haluaa luoda raportin, jossa näkyy eri kaupunkeihin tehtyjen toimitusten määrä. Hänellä on maantiedetaulukko, jossa on erilliset kentät kaupungille ja osavaltiolle. Jeff haluaa kuitenkin, että City ja State näkyvät raporteissa yksittäisenä arvona samalla rivillä. Tällä hetkellä Jeffin maantiedetaulukossa ei ole hänen haluamaansa kenttää.

![](media/desktop-calculated-columns/calccolinpbid_cityandstatefields.png)

Lasketun sarakkeen avulla Jeff voi kuitenkin yhdistää tai liittää yhteen City-sarakkeen kaupungit ja State-sarakkeen osavaltiot.

Jeff napsauttaa hiiren kakkospainikkeella maantiedetaulukkoa ja napsauttaa sitten kohtaa Uusi sarake. Sitten Jeff syöttää seuraavan DAX-kaavan kaavariville:

![](media/desktop-calculated-columns/calccolinpbid_formula.png)

Tämä kaava luo yksinkertaisesti uuden CityState-nimisen sarakkeen, ja se ottaa maantiedetaulukon jokaisen rivin osalta arvot City-sarakkeesta, lisää pilkun ja välilyönnin ja liittää sitten yhteen State-sarakkeen arvot.

Nyt Jeffillä on haluttu kenttä.

![](media/desktop-calculated-columns/calccolinpbid_citystatefield.png)

Jeff voi nyt lisätä sen raporttipohjaansa yhdessä toimitusten määrän kanssa. Jeff sai hyvin nopeasti ja vaivattomasti kentän City, State, joka voidaan lisätä lähes minkätyyppiseen visualisointiin tahansa. Jeff huomaa, että kun hän luo kartan visualisoinnin, Power BI Desktop tietää jo, miten uudessa sarakkeessa olevat City, State -arvot luetaan.

![](media/desktop-calculated-columns/calccolinpbid_citystatemap.png)

## <a name="learn-more"></a>Lisätietoja
Tässä on vain lyhyt esittely lasketuista sarakkeista. Tutustu [opetusohjelmaan: Laskettujen sarakkeiden luominen Power BI Desktopissa](desktop-tutorial-create-calculated-columns.md), josta voit ladata mallitiedoston ja saada vaiheittaiset ohjeet siitä, miten luodaan lisää sarakkeita. 

Lisätietoja DAX-kielestä on kohdassa [DAX-perusteet Power BI Desktopissa](desktop-quickstart-learn-dax-basics.md).

Lisätietoja kyselyn osana luotavista sarakkeista saat osasta Mukautettujen sarakkeiden luominen, joka kuuluu artikkeliin [Tavalliset kyselyn tehtävät Power BI Desktopissa.](desktop-common-query-tasks.md)  

