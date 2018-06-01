---
title: Power BI Desktopin kyselyiden yleiskatsaus
description: Power BI Desktopin kyselyiden yleiskatsaus
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 937cbf39d08bd830c16e9b2634f3d5a747689f54
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/09/2018
ms.locfileid: "30975097"
---
# <a name="query-overview-in-power-bi-desktop"></a>Power BI Desktopin kyselyiden yleiskatsaus
**Power BI Desktopilla** voit muodostaa yhteyden kasvavaan tietomäärään, luoda houkuttelevia ja perustavanlaatuisia raportteja ja jakaa työsi hedelmät muiden kanssa, jotka voivat taas hyödyntää niitä omassa työssään ja laajentaa liiketoimintatietojaan.

Power BI Desktopissa on kolme näkymää:

* **Raportti**näkymässä voit luomiesi kyselyjen avulla muodostaa vaikuttavia visualisointeja, jotka voit järjestää haluamallasi tavalla, jotka sisältävät useita sivuja ja jotka voit jakaa muiden kanssa.
* **Tieto**näkymässä voit tarkastella raportin tietoja tietomallin muodossa, jossa voit lisätä mittayksiköitä, luoda uusia sarakkeita ja hallita yhteyksiä.
* **Yhteydet**-näkymässä näet graafisen esityksen yhteyksistä, jotka on otettu käyttöön tietomallissa, ja voit hallita tai muokata niitä tarpeen mukaan.

Näitä näkymiä voi käyttää valitsemalla jonkin seuraavista kolmesta kuvakkeista Power BI Desktopin vasemmassa reunassa. Seuraavassa kuvassa Raporttinäkymä on valittuna, mistä on merkkinä kuvakkeen vieressä oleva keltainen nauha.  

![](media/desktop-query-overview/queryoverview_viewicons.png)

Power BI Desktopiin sisältyy myös **kyselyeditori**, jossa voit muodostaa yhteyden yhteen tai useaan tietolähteeseen, muotoilla ja muokata tietoja tarpeidesi mukaan ja sitten ladata mallin Power BI Desktopiin.

Tässä asiakirjassa on yleiskatsaus tietojen käsittelemiseen **kyselyeditorissa**. Opittavaa on tietysti paljon enemmän, ja tämän asiakirjan lopusta löydätkin linkit yksityiskohtaisiin ohjeisiin tuetuista tietotyypeistä, yhteyden muodostamisesta tietoihin, tietojen muotoilemisesta, yhteyksien luomisesta ja aloittamisesta.

Mutta tutustumaan kuitenkin ensin **kyselyeditoriin**.

## <a name="the-query-editor"></a>Kyselyeditori
Voit siirtyä **kyselyeditoriin** valitsemalla **Muokkaa kyselyitä** Power BI Desktopin **Aloitus**-välilehdessä.  

![](media/desktop-query-overview/queryoverview_queryview.png)

Kun tietoyhteyksiä ei ole, **kyselyeditorin** näkyy tyhjänä ruutuna valmiina tiedoille.  

![](media/desktop-query-overview/queryoverview_blankpane.png)

Kun kysely on ladattu, **Kyselyeditori**-näkymästä tulee kiinnostavampi. Jos yhteys muodostetaan seuraavaan verkkotietolähteeseen, **Kyselyeditori** lataa datan tiedot, joiden muotoilemisen voit sitten aloittaa.

[*http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx*](http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx)

**Kyselyeditori** näyttää seuraavanlaiselta, kun tietoyhteys on muodostettu:

1. Valintanauhassa on nyt useita aktiivisia painikkeita, joiden avulla kyselyn tietoja voi käsitellä.
2. Vasemmassa ruudussa on luettelo kyselyistä, ja ne valitaan siitä tarkasteltaviksi tai muovattaviksi.
3. Keskiruudussa näkyvät valitun kyselyn tiedot valmiina muovattavaksi.
4. **Kyselyasetukset**-ikkunassa näytetään luettelo kyselyn ominaisuuksista ja käytössä olevista vaiheista.  
   
   ![](media/desktop-query-overview/queryoverview_withdataconnection.png)

Tutustumme näihin neljään alueeseen – valintanauhaan, Kyselyt-ruutuun, tietonäkymään ja Kyselyasetukset-ruutuun – seuraavissa osissa.

## <a name="the-query-ribbon"></a>Kyselyn valintanauha
**Kyselyeditorin** valintanauha koostuu neljästä välilehdestä – **Aloitus**, **Muunna**, **Lisää sarake** ja **Näkymä**.

**Aloitus**-välilehti sisältää yleisiä kyselytehtäviä, mukaan lukien kaikkien kyselyiden ensimmäisen vaiheen, joka on **Nouda tiedot.** Seuraavassa kuvassa näkyy **Aloitus**-valintanauha.  

![](media/desktop-query-overview/queryoverview_ribbon.png)

Voit muodostaa yhteyden tietoihin ja aloittaa kyselyn muodostamisprosessin valitsemalla **Nouda tiedot** -painikkeen. Näkyviin tulee valikko, jossa on yleisimmät tietolähteet.  

![](media/desktop-query-overview/queryoverview_getdatamenu.png)

Lisätietoja käytettävissä olevista tietolähteistä on ohjeaiheessa **Tietolähteet**. Saat lisätietoja yhteyden muodostamisesta tietoihin, kuten esimerkkejä ja ohjeita, ohjeaiheesta **Yhdistä tietoihin**.

**Muunna**-välilehden avulla voit käyttää yleisiä tietojen muuntamistehtäviä. Voit esimerkiksi lisätä tai poistaa sarakkeita, muuttaa tietotyyppejä, jakaa sarakkeita ja tehdä muita tietopohjaisia tehtäviä. Seuraavassa kuvassa näkyy **Muunna**-välilehti.  

![](media/desktop-query-overview/queryoverview_transformribbon.png)

Lisätietoja tietojen muuntamisesta, kuten esimerkkejä, on ohjeaiheessa **Yhdistä ja muotoile tietoja**.

**Lisää sarake** -välilehti sisältää muita tehtäviä, jotka liittyvät sarakkeen lisäämiseen, sarakkeen tietojen muotoiluun ja mukautettujen sarakkeiden lisäämiseen. Seuraavassa kuvassa näkyy **Lisää sarake** -välilehti.  

![](media/desktop-query-overview/queryoverview_addcolumnribbon.png)

Valintanauhan **Näkymä**-välilehdessä voidaan näyttää tai piilottaa tietyt ruudut tai ikkunat. Sen avulla voidaan myös näyttää laajennettu editori. Seuraavassa kuvassa näkyy **Näkymä**-välilehti.  

![](media/desktop-query-overview/queryoverview_viewribbon.png)

On hyödyllistä tietää, että monet valintanauhan kautta käytettävissä olevat tehtävät ovat käytettävissä myös napsauttamalla hiiren kakkospainikkeella saraketta tai muita tietoja keskimmäisessä ruudussa.

## <a name="the-left-pane"></a>Vasen ruutu
Vasemmassa ruudussa näkyy aktiivisten kyselyiden määrä sekä kyselyn nimi. Kun valitset kyselyn vasemmanpuoleisesta ruudusta, sen tiedot näytetään keskimmäisessä ruudussa, jossa voit muotoilla ja muuntaa tietoja tarpeidesi mukaan. Seuraavassa kuvassa on näkyvissä vasemmanpuoleinen ruutu ja useita kyselyjä.  

![](media/desktop-query-overview/queryoverview_theleftpane.png)

## <a name="the-center-data-pane"></a>Keskimmäinen (tieto)ruutu
Keskimmäisessä tai tietoruudussa näkyvät valitun kyselyn tiedot. Täällä tehdään suurin osa kyselynäkymän työstä.

Seuraavassa kuvassa näytetään aiemmin muodostettu verkkotietoyhteys, **Yleinen pistemäärä** -sarake valitaan ja sen otsikkoa napsautetaan hiiren kakkospainikkeella, jolloin käytettävissä olevat valikkovaihtoehdot tulevat näkyviin. Huomaa, että monet näistä hiiren kakkospainikkeen valikkokohteista ovat samoja kuin valintanauhan välilehtien painikkeet.  

![](media/desktop-query-overview/queryoverview_thecenterpane.png)

Kun valitset hiiren kakkospainikkeen valikkokohteen (tai valintanauhan painikkeen), kysely käyttää tiedoissa vaihetta ja tallentaa ne itse kyselyn osana. Vaiheet tallennetaan **Kyselyasetukset**-ruudussa järjestyksessä seuraavassa osassa kuvatulla tavalla.  

## <a name="the-query-settings-pane"></a>Kyselyasetukset-ruutu
**Kyselyasetukset**-ruutu on paikka, jossa kaikki kyselyyn liittyvät vaiheet näytetään. Esimerkiksi seuraavassa kuvassa **Käytössä olevat vaiheet** -osa **Kyselyasetukset**-ruudussa kuvastaa sitä, että olemme juuri muuttaneet **Yleinen pistemäärä** -sarakkeen tyyppiä.

![](media/desktop-query-overview/queryoverview_querysettingspane.png)

Kun kyselyssä otetaan käyttöön lisämuokkausvaiheita, ne tallennetaan **Käytössä olevat vaiheet** -osaan.

On tärkeää tietää, että pohjana olevat tiedot *eivät* ole muuttuneet, vaan sen sijaan kyselyeditori säätää ja muokkaa tietonäkymäänsä, ja yhteydenpito pohjana oleviin tietoihin tehdään kyselyeditorin näiden tietojen muokatun näkymän perusteella.

**Kyselyasetukset**-ruudussa voit nimetä vaiheita uudelleen, poistaa vaiheita tai järjestää vaiheet uudelleen tarpeen mukaan. Voit tehdä tämän napsauttamalla hiiren kakkospainikkeella vaihetta **Käytössä olevat vaiheet** -osassa ja valitse sitten valikosta, joka tulee näkyviin. Kaikki kyselyn vaiheet suoritetaan siinä järjestyksessä, jossa ne näkyvät **Käytössä olevat vaiheet** -ruudussa.

![](media/desktop-query-overview/queryoverview_querysettings_rename.png)

## <a name="the-advanced-editor"></a>Laajennettu editori
Jos haluat nähdä koodin, jonka kyselyeditori luo jokaisessa vaiheessa, tai jos haluat luoda oman muotoilukoodin, voit käyttää **laajennettua editoria**. Ota laajennettu editori käyttöön valitsemalla **Näkymä** valintanauhasta ja sitten **Laajennettu editori**. Näyttöön tulee ikkuna, jossa on aiemmin luotu kyselykoodi.  
![](media/desktop-query-overview/queryoverview_advancededitor.png)

Voit muokata koodia suoraan **Laajennettu editori** -ikkunassa. Sulje ikkuna valitsemalla **Valmis**- tai **Peruuta**-painike.  

## <a name="saving-your-work"></a>Työn tallentaminen
Kun kysely on haluamassasi paikassa, voit antaa kyselyeditorin käyttää tietomallin muutoksia Power BI Desktopissa ja sitten sulkea kyselyeditorin. Voit tehdä tämän valitsemalla **Sulje ja ota käyttöön** Kyselyeditorin **Tiedosto**-valikosta.  
![](media/desktop-query-overview/queryoverview_closenload.png)

Edistymisen aikana Power BI Desktop näyttää tilansa valintaikkunassa.  
![](media/desktop-query-overview/queryoverview_loading.png)

Kun kysely on oikeassa paikassa, tai jos haluat vain varmistaa, että työsi tallennetaan, Power BI Desktop voi tallentaa työsi .pbix-tiedostomuodossa.

Voit tallentaa työsi valitsemalla **Tiedosto \> Tallenna** (tai **Tiedosto \> Tallenna nimellä**) seuraavassa kuvassa esitetyllä tavalla.  
![](media/desktop-query-overview/queryoverview_savework.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Voit tehdä kaikenlaista Power BI Desktopilla. Saat lisätietoja sen toiminnoista seuraavista resursseista:

* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietoihin yhdistäminen Power BI Desktopissa](desktop-connect-to-data.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](desktop-common-query-tasks.md)   

