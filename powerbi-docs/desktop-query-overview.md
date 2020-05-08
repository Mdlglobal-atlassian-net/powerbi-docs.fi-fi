---
title: Power BI Desktopin kyselyiden yleiskatsaus
description: Power BI Desktopin kyselyiden yleiskatsaus
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/11/2020
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: c8a27e8cc261d9b29222cfc7867f5376b29067e0
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "76753432"
---
# <a name="query-overview-in-power-bi-desktop"></a>Power BI Desktopin kyselyiden yleiskatsaus
Power BI Desktopilla voit muodostaa yhteyden tietoihin, luoda vaikuttavia ja perusteellisia raportteja ja jakaa työsi hedelmät muiden kanssa, jotka voivat taas hyödyntää niitä omassa työssään ja laajentaa liiketoimintatietojaan.

Power BI Desktopissa on kolme näkymää:

* **Raportti**näkymässä voit luomiesi kyselyjen avulla muodostaa vaikuttavia visualisointeja, jotka voit järjestää haluamallasi tavalla, jotka sisältävät useita sivuja ja jotka voit jakaa muiden kanssa.
* **Tieto**näkymässä voit tarkastella raportin tietoja tietomallin muodossa, jossa voit lisätä mittareita, luoda uusia sarakkeita ja hallita yhteyksiä
* **Yhteydet**-näkymässä näet graafisen esityksen yhteyksistä, jotka on otettu käyttöön tietomallissa, ja voit hallita tai muokata niitä tarpeen mukaan.

Käytä näitä näkymiä valitsemalla jokin kolmesta kuvakkeesta Power BI Desktopin vasemmassa reunassa. Seuraavassa kuvassa **Raportti**näkymä on valittuna, mistä on merkkinä kuvakkeen vieressä oleva keltainen viiva.  

![](media/desktop-query-overview/queryoverview_viewicons.png)

Power BI Desktopiin sisältyy myös Power Query -editori. Power Query -editorissa voit muodostaa yhteyden yhteen tai useaan tietolähteeseen, muotoilla ja muokata tietoja tarpeidesi mukaan ja ladata mallin Power BI Desktopiin.

Tämä asiakirja tarjoaa yleiskatsauksen tietojen käsittelemiseen Power Query -editorissa, mutta opittavaa on tietysti paljon enemmän. Tämän asiakirjan lopussa olevista linkeistä saat yksityiskohtaisia ohjeita tuetuista tietotyypeistä. Löydät lisätietoja myös yhteyden muodostamisesta tietoihin, tietojen muotoilemisesta, yhteyksien luomisesta ja aloittamisesta.

Tutustutaan kuitenkin ensin Power Query -editoriin.

## <a name="power-query-editor"></a>Power Query -editori
Siirry Power Query -editoriin valitsemalla **Muokkaa kyselyitä** Power BI Desktopin **Aloitus**-välilehdessä.  

![](media/desktop-query-overview/queryoverview_queryview.png)

Kun tietoyhteyksiä ei ole, Power Query -editori näkyy tyhjänä ruutuna valmiina vastaanottamaan tietoja.  

![](media/desktop-query-overview/queryoverview_blankpane.png)

Kun kysely on ladattu, Power Query -editorin näkymästä tulee kiinnostavampi. Jos yhteys muodostetaan seuraavaan verkkotietolähteeseen, Power Query -editori lataa datan tiedot, joiden muotoilemisen voit sitten aloittaa:

[*https://www.bankrate.com/retirement/best-and-worst-states-for-retirement/*](https://www.bankrate.com/retirement/best-and-worst-states-for-retirement/)

Power Query -editori näyttää seuraavanlaiselta, kun tietoyhteys on muodostettu:

1. Valintanauhassa on nyt useita aktiivisia painikkeita, joiden avulla kyselyn tietoja voi käsitellä.
2. Vasemmassa ruudussa on luettelo kyselyistä, jotka voi valita ja joita voi tarkastella ja muokata.
3. Keskimmäisessä ruudussa näkyvät valitun kyselyn tiedot, joita voi muokata.
4. **Kyselyasetukset**-ruudussa näkyy luettelo kyselyn ominaisuuksista ja käytössä olevista vaiheista.  
   
   ![](media/desktop-query-overview/queryoverview_withdataconnection.png)

Tutustumme seuraavaksi näihin neljään alueeseen – valintanauhaan, Kyselyt-ruutuun, tietonäkymään ja Kyselyasetukset-ruutuun.

## <a name="the-query-ribbon"></a>Kyselyn valintanauha
Power Query -editorin valintanauhassa on neljä välilehteä: **Aloitus**, **Muunna**, **Lisää sarake** ja **Näytä**.

**Aloitus**-välilehdellä on yleisiä kyselytehtäviä.

![](media/desktop-query-overview/queryoverview_ribbon.png)

Muodosta yhteys tietoihin ja aloita kyselyn muodostamisprosessi valitsemalla **Uusi lähde**. Näkyviin tulee valikko, jossa on yleisimmät tietolähteet.  

![](media/desktop-query-overview/query-overview-new-source-menu.png)

Lisätietoja käytettävissä olevista tietolähteistä on ohjeaiheessa **Tietolähteet**. Saat lisätietoja yhteyden muodostamisesta tietoihin, kuten esimerkkejä ja ohjeita, ohjeaiheesta **Yhdistä tietoihin**.

**Muunna**-välilehdessä voit tehdä yleisiä tietojen muuntamistehtäviä, kuten seuraavat:

* sarakkeiden lisääminen tai poistaminen
* tietotyyppien muuttaminen 
* sarakkeiden jakaminen 
* muut tietopohjaiset tehtävät.

![](media/desktop-query-overview/queryoverview_transformribbon.png)

Jos haluat saada lisätietoja ja nähdä esimerkkejä tietojen muuntamisesta, katso [Opetusohjelma: Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](https://docs.microsoft.com/power-bi/desktop-shape-and-combine-data).

**Lisää sarake** -välilehti sisältää muita tehtäviä, jotka liittyvät sarakkeen lisäämiseen, sarakkeen tietojen muotoiluun ja mukautettujen sarakkeiden lisäämiseen. Seuraavassa kuvassa näkyy **Lisää sarake** -välilehti.  

![](media/desktop-query-overview/queryoverview_addcolumnribbon.png)

Valintanauhan **Näkymä**-välilehdessä voidaan näyttää tai piilottaa tietyt ruudut tai ikkunat. Sen avulla voidaan myös näyttää laajennettu editori. Seuraavassa kuvassa näkyy **Näkymä**-välilehti.  

![](media/desktop-query-overview/queryoverview_viewribbon.png)

On hyödyllistä tietää, että monet valintanauhan kautta käytettävissä olevat tehtävät ovat käytettävissä myös napsauttamalla hiiren kakkospainikkeella saraketta tai muita tietoja keskimmäisessä ruudussa.

## <a name="the-left-queries-pane"></a>Vasen ruutu (Kyselyt)
Vasemmassa ruudussa eli **Kyselyt**-ruudussa näkyy aktiivisten kyselyiden määrä ja kyselyn nimi. Kun valitset kyselyn vasemmanpuoleisesta ruudusta, sen tiedot näytetään keskimmäisessä ruudussa, jossa voit muotoilla ja muuntaa tietoja tarpeidesi mukaan. Seuraavassa kuvassa näkyy vasen ruutu ja siinä oleva kysely.  

![](media/desktop-query-overview/queryoverview_theleftpane.png)

## <a name="the-center-data-pane"></a>Keskimmäinen ruutu (tietoruutu)
Keskimmäisessä ruudussa eli **tieto**ruudussa näkyvät valitun kyselyn tiedot. Tässä ruudussa tehdään suurin osa **kysely**näkymän työstä.

Seuraavassa kuvassa näkyy aiemmin muodostettu verkkotietoyhteys. **Tuote**-sarake on valittuna ja sen otsikkoa on napsautettu hiiren kakkospainikkeella, jolloin käytettävissä olevat valikkokohteet näkyvät. Huomaa, että monet näistä hiiren kakkospainikkeen valikkokohteista ovat samoja kuin valintanauhan välilehtien painikkeet.  

![](media/desktop-query-overview/queryoverview_thecenterpane.png)

Kun valitset hiiren kakkospainikkeen valikkokohteen (tai valintanauhan painikkeen), kysely suorittaa vaiheen tiedoissa. Se myös tallentaa vaiheen kyselyn osaksi. Vaiheet tallennetaan **Kyselyasetukset**-ruudussa järjestyksessä seuraavassa osassa kuvatulla tavalla.  

## <a name="the-right-query-settings-pane"></a>Oikea ruutu (Kyselyasetukset)
Oikeassa ruudussa eli **Kyselyasetukset**-ruudussa näkyvät kaikki kyselyyn liittyvät vaiheet. Esimerkiksi seuraavassa kuvassa **Käytössä olevat vaiheet** -osa **Kyselyasetukset**-ruudussa kuvastaa sitä, että olemme juuri muuttaneet **Yleinen pistemäärä** -sarakkeen tyyppiä.

![](media/desktop-query-overview/queryoverview_querysettingspane.png)

Kun kyselyssä suoritetaan lisämuokkausvaiheita, ne tallennetaan **Käytössä olevat vaiheet** -osaan.

On tärkeää tietää, että pohjana olevat tiedot *eivät* ole muuttuneet, sillä Power Query -editori säätää ja muokkaa vain omaa tietonäkymäänsä. Se säätää ja muokkaa myös pohjana olevien tietojen yhteydenpitonäkymää, joka perustuu Power Query -editorin näistä tiedoista muokkaamaan näkymään.

**Kyselyasetukset**-ruudussa voit nimetä vaiheita uudelleen, poistaa vaiheita tai järjestää vaiheet uudelleen tarpeen mukaan. Voit tehdä tämän napsauttamalla hiiren kakkospainikkeella vaihetta **Käytössä olevat vaiheet** -osassa ja valitse sitten valikosta, joka tulee näkyviin. Kaikki kyselyn vaiheet suoritetaan siinä järjestyksessä, jossa ne näkyvät **Käytössä olevat vaiheet** -ruudussa.

![](media/desktop-query-overview/queryoverview_querysettings_rename.png)

## <a name="advanced-editor"></a>Laajennettu editori
**Laajennetussa editorissa** näet koodin, jonka Power Query -editori luo kussakin vaiheessa. Sen avulla voit myös luoda oman muotoilukoodisi. Ota laajennettu editori käyttöön valitsemalla **Näkymä** valintanauhasta ja sitten **Laajennettu editori**. Näyttöön tulee ikkuna, jossa on aiemmin luotu kyselykoodi.  
![](media/desktop-query-overview/queryoverview_advancededitor.png)

Voit muokata koodia suoraan **Laajennettu editori** -ikkunassa. Sulje ikkuna valitsemalla **Valmis**- tai **Peruuta**-painike.  

## <a name="saving-your-work"></a>Työn tallentaminen
Kun kysely on sellainen kuin haluat, valitse **Sulje ja ota käyttöön** Power Query -editorin **Tiedosto**-valikosta. Tällöin muutokset otetaan käyttöön ja editori suljetaan.  
![](media/desktop-query-overview/queryoverview_closenload.png)

Edistymisen aikana Power BI Desktop näyttää tilansa valintaikkunassa.  
![](media/desktop-query-overview/queryoverview_loading.png)

Kun olet valmis, Power BI Desktop voi tallentaa työsi *.pbix*-tiedostona.

Tallenna työsi valitsemalla **Tiedosto** \> **Tallenna** (tai **Tiedosto** \> **Tallenna nimellä**) seuraavassa kuvassa esitetyllä tavalla.  
![](media/desktop-query-overview/queryoverview_savework.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Voit tehdä kaikenlaista Power BI Desktopilla. Saat lisätietoja sen toiminnoista seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietoihin yhdistäminen Power BI Desktopissa](desktop-connect-to-data.md)
* [Opetusohjelma: Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleisten kyselytehtävien suorittaminen Power BI Desktopissa](desktop-common-query-tasks.md)   

