---
title: Käytä mittayksiköitä Power BI Desktopissa
description: Mittayksiköt Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/08/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 56935d4c4c30e759056f3d383e40d570bfd81ae8
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/13/2019
ms.locfileid: "56215346"
---
# <a name="measures-in-power-bi-desktop"></a>Mittayksiköt Power BI Desktopissa

**Power BI Desktopin** avulla tiedoistasi voi saada paremman käsityksen muutamalla napsautuksella. Joskus nämä tiedot eivät kuitenkaan sisällä kaikkea sitä, mitä tarvitaan, jotta kaikkein tärkeimpiin kysymyksiin saataisiin vastauksia. Mittayksiköt voivat auttaa tämän saavuttamisessa.

Mittayksiköitä käytetään joissakin yleisimmissä tietoanalyyseissa, kuten summat, keskiarvot, minimi- tai maksimiarvot, määrät tai monimutkaisemmat laskutoimitukset, jotka luot itse DAX-kaavan avulla. Mittayksikköjen lasketut tulokset muuttuvat aina sen mukaan, miten raporttia käsitellään, mahdollistaen nopean ja dynaamisen tietojen tarkastelun. Menetelmien kuvailu on alla.

## <a name="understanding-measures"></a>Mittayksikköjen ymmärtäminen

**Power BI Desktopissa** mittayksiköitä luodaan ja käytetään **raporttinäkymässä** tai **tietonäkymässä**. Omat luodut mittayksiköt näkyvät kentät-listassa laskin-kuvakkeen kanssa. Mittayksiköt voit nimetä miten tahansa ja niitä voi lisätä uuteen tai jo olemassa olevan raportin visualisointiin muiden kenttien tapaan.

![](media/desktop-measures/measuresinpbid_measinfieldlist.png)

> [!NOTE]
> **Pikamittarit** ovat valmiiksi luotuja mittayksikköjä, jotka ovat valittavissa valintaikkunoista. Niiden avulla on helppo luoda mittayksikköjä nopeasti, sekä oppia DAX-syntaksi, sillä niiden automaattisesti luodut DAX-kaavat ovat tarkasteltavissa. Katso artikkeli: [pikamittarit](desktop-quick-measures.md).
> 
> 

## <a name="data-analysis-expressions"></a>Data Analysis Expressions

Mittayksiköt laskevat lausekekaavasta tuloksen. Mittayksikön luomisessa käytetään [Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) -kaavakieltä. DAX sisältää kirjaston, jossa on yli 200 funktioita, operaattoria ja rakennetta. Sen kirjasto tarjoaa valtavan joustavuuden luotaessa mittayksikköjä lähes minkä tahansa tietoanalyysitarpeen tulosten laskemiseksi.

DAX-kaavat muistuttavat Excel-kaavoja. DAX sisältää jopa useita samoja toimintoja, kuten DATE, SUM ja LEFT. DAX-kaavat on kuitenkin tarkoitettu suhteellisten tietojen käsittelyyn, kuten mitä Power BI Desktop sisältää.

## <a name="lets-look-at-an-example"></a>Tarkastellaan esimerkkiä
Jan on Contoson myyntipäällikkö. Häntä on pyydetty esittämään jälleenmyynnin seuraavan tilivuoden myyntiennusteet. Jan päättää perustaa ennusteensa viime vuoden myyntilukuihin, joihin lisätään kuuden prosentin vuosittainen lisä. Se perustuu erilaisille seuraavaksi kuudeksi kuukaudeksi suunnitelluille kampanjoille.

Arvioiden ilmoittamiseksi Jan tuo viime vuoden myyntitiedot Power BI Desktopiin. Jan huomaa jälleenmyyjän myyntitaulukossa myyntimäärä-kentän. Koska tuotavat tiedot sisältävät vain viime vuoden myyntimäärät, hän nimeää Myyntimäärä-kentän Viime vuoden myynti -kentäksi. Jan vetää sitten viime vuoden myynnit raporttipohjaan. Ne näytetään kaaviovisualisoinnissa yhtenä arvona, joka on kaikkien jälleenmyyjän viime vuoden myyntien summa.

Hän huomaa, että vaikka hän ei määrittänyt laskelmaa itse, se on annettu automaattisesti. Power BI Desktop loi oman mittayksikkönsä laskemalla yhteen kaikki viime vuoden myyntiarvot.

Mutta Jan tarvitsee mittayksikön, jolla hän voi laskea tulevan vuoden myyntiennusteet, jotka perustuvat edellisen vuoden myyntiin kerrottuna 1.06:lla, joka vastaa odotettua kuuden prosentin nousua. Tätä laskentaa varten hän luo oman mittayksikkönsä. Käyttämällä uusi mittayksikkö -toimintoa, hän luo uuden mittayksikön, ja syöttää seuraavan DAX-kaavan:

    Projected Sales = SUM('Sales'[Last Years Sales])*1.06

Sitten Jan siirtää uuden ennustettu myynti -mittayksikkönsä taulukkoon.

![](media/desktop-measures/measuresinpbid_lastyearsales.png)

Nopeasti ja pienellä vaivalla Janilla on nyt mittayksikkö, millä hän voi laskea ennustetun myynnin. Jan voi edelleen analysoida ennusteitaan suodattamalla tiettyjä jälleenmyyjiä tai lisäämällä muita kenttiä raporttiinsa.

## <a name="data-categories-for-measures"></a>Mittayksikköjen tietoluokat

Voit myös valita mittayksiköiden tietoluokkia. 

Tämän ansiosta voit muun muassa mittayksiköiden avulla luoda dynaamisesti URL-osoitteita ja merkitä tietoluokan verkon URL-osoitteeksi. 

Voit luoda taulukoita, jotka näyttävät mittayksiköt verkon URL-osoitteina, ja klikata valintasi perusteella luotua URL-osoitetta. Tämä on erityisen hyödyllistä, kun haluat linkittää muihin Power BI -raportteihin [URL-suodattimen parametrien](service-url-filters.md) avulla.

## <a name="learn-more"></a>Lisätietoja
Olemme antaneet lyhyen esittelyn mittayksikköihin, mutta on olemassa paljon enemmän ohjeistuksia omien mittayksikköjen luontia varten. Tutustu [opetusohjelmaan: Omien mittayksiköiden luominen Power BI Desktopissa](desktop-tutorial-create-measures.md), josta voi ladata mallitiedoston ja saada vaiheittaiset ohjeet mittayksiköiden luomiseen.  

Sukeltaaksesi syvemmälle DAX:n maailmaan, katso [DAX-perusteet Power BI Desktopissa](desktop-quickstart-learn-dax-basics.md). [Data Analysis Expressions -viite](https://msdn.microsoft.com/library/gg413422.aspx) tarjoaa yksityiskohtaisia artikkeleita jokaisesta yksittäisestä funktiosta, syntaksista, operaattoreista sekä nimeämiskäytännöistä. DAX on ollut olemassa Excelin Power Pivotissa sekä SQL Server Analysis Servicessä useita vuosia, joten saatavilla on myös monia muita käteviä resursseja. Tutki esimerkiksi [DAX Resource Center Wikiä](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx), jonne BI-yhteisön vaikutusvaltaiset jäsenet ovat jakaneet DAX-tietojaan.



