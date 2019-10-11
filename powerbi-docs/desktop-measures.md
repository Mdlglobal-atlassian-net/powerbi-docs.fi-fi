---
title: Käytä mittareita Power BI Desktopissa
description: Mittarit Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/29/2019
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: d5ada41ef4941f14118b777e37e731337a5282d0
ms.sourcegitcommit: d04b9e1426b8544ce16ef25864269cc43c2d9f7b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/01/2019
ms.locfileid: "71715389"
---
# <a name="measures-in-power-bi-desktop"></a>Mittarit Power BI Desktopissa

**Power BI Desktopin** avulla tiedoistasi voi saada paremman käsityksen muutamalla napsautuksella. Joskus nämä tiedot eivät kuitenkaan sisällä kaikkea sitä, mitä tarvitaan, jotta kaikkein tärkeimpiin kysymyksiin saataisiin vastauksia. Mittarit voivat auttaa tämän saavuttamisessa.

Mittareita käytetään joissakin yleisimmissä tietoanalyyseissa, Yksinkertaiset yhteenvedot, kuten summat, keskiarvot, pienimmät ja suurimmat arvot ja määrät, voidaan määrittää Kentät-ruudussa. Mittarien lasketut tulokset muuttuvat aina sen mukaan, miten raporttia käsitellään, mahdollistaen nopean ja dynaamisen tietojen tarkastelun. Menetelmien kuvailu on alla. Lisätietoja on kohdassa [Laskettujen mittarien luominen](/learn/modules/model-data-power-bi/4b-create-calculated-measures).

## <a name="understanding-measures"></a>Mittarien ymmärtäminen

**Power BI Desktopissa** mittareita luodaan ja näytetään **raporttinäkymässä** tai **tietonäkymässä**. Omat luodut mittarit näkyvät kentät-listassa laskin-kuvakkeen kanssa. Mittarit voit nimetä miten tahansa ja niitä voi lisätä uuteen tai jo olemassa olevan raportin visualisointiin muiden kenttien tapaan.

![](media/desktop-measures/measuresinpbid_measinfieldlist.png)

> [!NOTE]
> **Pikamittarit** ovat valmiiksi luotuja mittareita, jotka ovat valittavissa valintaikkunoista. Niiden avulla on helppo luoda mittareita nopeasti, sekä oppia DAX-syntaksi, sillä niiden automaattisesti luodut DAX-kaavat ovat tarkasteltavissa. Katso artikkeli: [pikamittarit](desktop-quick-measures.md).
> 
> 

## <a name="data-analysis-expressions"></a>Data Analysis Expressions

Mittarit laskevat lausekekaavasta tuloksen. Mittarin luomisessa käytetään [Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) -kaavakieltä. DAX sisältää kirjaston, jossa on yli 200 funktioita, operaattoria ja rakennetta. Sen kirjasto tarjoaa valtavan joustavuuden luotaessa mittareita lähes minkä tahansa tietoanalyysitarpeen tulosten laskemiseksi.

DAX-kaavat muistuttavat Excel-kaavoja. DAX sisältää jopa useita samoja toimintoja, kuten DATE, SUM ja LEFT. DAX-kaavat on kuitenkin tarkoitettu suhteellisten tietojen käsittelyyn, kuten mitä Power BI Desktop sisältää.

## <a name="lets-look-at-an-example"></a>Tarkastellaan esimerkkiä
Jan on Contoson myyntipäällikkö. Jania on pyydetty esittämään jälleenmyynnin seuraavan tilivuoden myyntiennusteet. Jan päättää perustaa ennusteensa viime vuoden myyntilukuihin, joihin lisätään kuuden prosentin vuosittainen lisä. Se perustuu erilaisille seuraavaksi kuudeksi kuukaudeksi suunnitelluille kampanjoille.

Arvioiden ilmoittamiseksi Jan tuo viime vuoden myyntitiedot Power BI Desktopiin. Jan huomaa jälleenmyyjän myyntitaulukossa myyntimäärä-kentän. Koska tuotavat tiedot sisältävät vain viime vuoden myyntimäärät, hän nimeää Myyntimäärä-kentän Viime vuoden myynti -kentäksi. Jan vetää sitten viime vuoden myynnit raporttipohjaan. Ne näytetään kaaviovisualisoinnissa yhtenä arvona, joka on kaikkien jälleenmyyjän viime vuoden myyntien summa.

Jan huomaa, että vaikka hän ei määrittänyt laskelmaa itse, se on annettu automaattisesti. Power BI Desktop loi oman mittarinsa laskemalla yhteen kaikki viime vuoden myyntiarvot.

Mutta Jan tarvitsee mittarin, jolla hän voi laskea tulevan vuoden myyntiennusteet, jotka perustuvat edellisen vuoden myyntiin kerrottuna 1.06:lla, joka vastaa odotettua kuuden prosentin nousua. Tätä laskentaa varten hän luo oman mittarinsa. Käyttämällä uusi mittari -toimintoa Jan luo uuden mittarin ja syöttää seuraavan DAX-kaavan:

    Projected Sales = SUM('Sales'[Last Years Sales])*1.06

Sitten Jan siirtää uuden ennustettu myynti -mittarinsa taulukkoon.

![](media/desktop-measures/measuresinpbid_lastyearsales.png)

Nopeasti ja pienellä vaivalla Janilla on nyt mittari, jolla hän voi laskea ennustetun myynnin. Jan voi edelleen analysoida ennusteitaan suodattamalla tiettyjä jälleenmyyjiä tai lisäämällä muita kenttiä raporttiinsa.

## <a name="data-categories-for-measures"></a>Mittarien tietoluokat

Voit myös valita mittarien tietoluokkia. 

Tämän ansiosta voit muun muassa mittarien avulla luoda dynaamisesti URL-osoitteita ja merkitä tietoluokan verkon URL-osoitteeksi. 

Voit luoda taulukoita, jotka näyttävät mittarit verkon URL-osoitteina, ja napsauttaa valintasi perusteella luotua URL-osoitetta. Tämä on erityisen hyödyllistä, kun haluat linkittää muihin Power BI -raportteihin [URL-suodattimen parametrien](service-url-filters.md) avulla.


## <a name="organizing-your-measures"></a>Mittarien järjestäminen

Mittarit sisältävät *aloitus*taulukon, joka määrittää, mistä kohtaa kenttäluetteloa ne löytyvät. Voit muuttaa niiden sijaintia valitsemalla sijainnin mallin taulukoista.

![Valitse mittari taulukolle](media/desktop-measures/measures-03.png)

Voit myös järjestää taulukon kenttiä *näyttökansioihin*. Valitse **mallinäkymä** Power BI Desktop -ikkunan vasemmasta reunasta ja valitse sitten kenttä, jonka haluat siirtää piirtoalustalla näkyvästä käytettävissä olevien kenttien luettelosta. Ominaisuusruutuun tulee näkyviin tekstiruutu **näyttökansiota** varten. Nimen kirjoittaminen **Näyttökansio**-kenttään luo kansion ja siirtää valitun kentän kyseiseen kansioon.

![Luo kenttä mittareita varten](media/desktop-measures/measures-04.gif)

Voit luoda alikansioita käyttämällä kenoviivaa. Esimerkiksi *Talous\Valuutat* luo *Talous*-kansion ja sen sisälle *Valuutat*-kansion.

Voit määrittää kentän näkymään useissa kansioissa käyttämällä puolipistettä kansioiden nimien erottamiseen. Esimerkiksi jos luot kohteen *Tuotteet\Nimet;Osastot*, kenttä näkyy sekä *Osastot*- että *Nimet*-kansiossa *Tuotteen*-kansiossa sisällä.

Voit myös luoda erikoistaulukon, joka sisältää vain mittareita, jotka näkyvät aina **kenttäluettelon** yläosassa. Voit tehdä tämän luomalla taulukon, jossa on vain yksi sarake. Voit luoda kyseisen taulukon käyttämällä **Anna tiedot** -toimintoa. Siirrä sitten mittarit kyseiseen taulukkoon. Piilota lopuksi luomasi sarake (ei taulukkoa). Sinun on suljettava **kenttäluettelo** ja avattava se uudelleen, jotta Power BI Desktop näyttää sen oikein. Voit tehdä tämän napsauttamalla **kenttäluettelon** yläosassa olevaa kaksoisnuolikuvaketta.

![Järjestä mittarit ja säilytä ne Kentät-luettelon päällä](media/desktop-measures/measures-05.png)

## <a name="learn-more"></a>Lisätietoja
Olemme antaneet lyhyen esittelyn mittareihin, mutta on olemassa paljon enemmän ohjeistuksia omien mittarien luontia varten. Tutustu [opetusohjelmaan: Omien mittarien luominen Power BI Desktopissa](desktop-tutorial-create-measures.md), josta voi ladata mallitiedoston ja saada vaiheittaiset ohjeet mittarien luomiseen.  

Sukeltaaksesi syvemmälle DAX:n maailmaan, katso [DAX-perusteet Power BI Desktopissa](desktop-quickstart-learn-dax-basics.md). [Data Analysis Expressions -viite](https://msdn.microsoft.com/library/gg413422.aspx) tarjoaa yksityiskohtaisia artikkeleita jokaisesta yksittäisestä funktiosta, syntaksista, operaattoreista sekä nimeämiskäytännöistä. DAX on ollut olemassa Excelin Power Pivotissa sekä SQL Server Analysis Servicessä useita vuosia, joten saatavilla on myös monia muita käteviä resursseja. Tutki esimerkiksi [DAX Resource Center Wikiä](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx), jonne BI-yhteisön vaikutusvaltaiset jäsenet ovat jakaneet DAX-tietojaan.



