---
title: 'Opetusohjelma: Excelin ja OData-syötteen myyntitietojen analysointi Power BI Desktopissa'
description: 'Opetusohjelma: Excelin ja OData-syötteen myyntitietojen analysointi'
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
LocalizationGroup: Learn more
ms.openlocfilehash: aad93a6c636fb0d75ad89f9e3d9eb70ec203cc88
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/04/2018
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>Opetusohjelma: Excelin ja OData-syötteen myyntitietojen analysointi
**Power BI Desktopilla** voit muodostaa yhteyden kaikenlaisiin tietolähteisiin ja yhdistää sekä muokata sitten tietoja tavoin, joilla voit analysoida ja visualisoida tietoja mielenkiintoisesti sekä tehokkaasti. Tässä opetusohjelmassa opit yhdistämään tietoja kahdesta tietolähteestä. 

On yleistä, että tiedot ovat hajallaan useissa tietolähteissä: esimerkiksi tuotetiedot voivat olla yhdessä tietokannassa ja myyntitiedot toisessa. Opit tässä opetusohjelmassa käyttämään tietolähteenä Excel-työkirjaa ja OData-syötettä, mutta voit soveltaa näitä tekniikoita myös muiden tietolähteiden kanssa, esimerkiksi SQL Server -kyselyiden, CSV-tiedostojen ja minkä tahansa muun Power BI Desktopin tietolähteen kanssa.

Tässä opetusohjelmassa tuot tietoja Excelistä (tuotetietoja) ja OData-syötteestä (tilaustietoja). Suoritat muuntamis- ja koostamisvaiheet sekä yhdistät molempien lähteiden tiedot ja luot **Total Sales per Product and Year** -raportin, joka sisältää vuorovaikutteisia visualisointeja. 

Lopullinen raportti näyttää tältä:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

Tarvitset tämän opetusohjelman seuraamiseen Products-työkirjan, jonka voit ladata: **[lataa Products.xlsx napsauttamalla tätä](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**.

Anna **Tallenna nimellä** -valintaikkunassa tiedoston nimeksi **Products.xlsx**.

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>Tehtävä 1: tuotetietojen hakeminen Excel-työkirjasta
Tässä tehtävässä tuot tuotteet Products.xlsx-tiedostosta Power BI Desktopiin.

### <a name="step-1-connect-to-an-excel-workbook"></a>Vaihe 1: Excel-työkirjaan yhdistäminen
1. Käynnistä Power BI Desktop.
2. Valitse Aloitus-valintanauhasta **Nouda tiedot**. Excel on yksi **Yleisin**-tietolähteistä, joten voit valita sen suoraan **Nouda tiedot** -valikosta.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. Jos napsautat suoraan Nouda tiedot -painiketta, voit myös valita **Tiedosto \> Excel** ja valita sitten **Yhdistä**.
4. Valitse **Avaa tiedosto** -valintaikkunassa **Products.xlsx**-tiedosto.
5. Valitse **Siirtymistoiminto**-ruudussa **Products**-taulukko ja valitse sitten **Muokkaa**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>Vaihe 2: muiden sarakkeiden poistaminen vain tarvittavien sarakkeiden näyttämiseksi
Tässä vaiheessa poistat kaikki muut sarakkeet paitsi **ProductID**-, **ProductName**-, **UnitsInStock**- ja **QuantityPerUnit**-sarakkeet. Power BI Desktopissa on usein eri tapoja tehdä sama asia. Voit esimerkiksi tehdä samoja toimintoja kuin monilla valintanauhan painikkeilla napsauttamalla saraketta tai solua hiiren kakkospainikkeella ja valitsemalla sitten toiminnon.

Power BI Desktop sisältää kyselyeditorin, jolla voit muokata ja muuntaa tietoyhteyksiä. Kyselyeditori avautuu automaattisesti, kun valitset **siirtymistoiminnossa** **Muokkaa**. Voit avata kyselyeditorin myös valitsemalla Power BI Desktopin **Aloitus**-valintanauhasta **Muokkaa kyselyitä**. Seuraavat vaiheet suoritetaan kyselyeditorissa.

1. Valitse kyselyeditorissa **ProductID**-, **ProductName**-, **QuantityPerUnit**- ja **UnitsInStock** -sarakkeet (voit valita useita sarakkeita painamalla **Ctrl-näppäintä samalla, kun napsautat** sarakkeita, ja valita useita vierekkäisiä sarakkeita painamalla **Vaihto-näppäintä samalla, kun napsautat** sarakkeita).
2. Valitse valintanauhasta **Poista sarakkeet** \> **Poista muut sarakkeet** tai napsauta sarakeotsikkoa hiiren kakkospainikkeella ja valitse **Poista muut sarakkeet**.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>Vaihe 3: UnitsInStock-sarakkeen tietotyypin vaihtaminen
Kun kyselyeditori muodostaa yhteyden tietoihin, se tarkistaa jokaisen kentän ja määrittää parhaan tietotyypin. Excel-työkirjassa varastossa olevien tuotteiden arvo on kokonaisluku, joten tässä vaiheessa varmistat, että **UnitsInStock**-sarakkeen tietotyyppiasetus on Kokonaisluku.

1. Valitse **UnitsInStock**-sarake.
2. Valitse **Aloitus**-valintanauhan avattava **Tietotyyppi**-painike.
3. Jos tietotyyppinä ei ole jo kokonaisluku, valitse avattavasta painikkeesta **Kokonaisluku** (**Tietotyyppi:**-painike näyttää myös nykyisen valinnan tietotyypin).
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>Luodut Power BI Desktopin vaiheet
Kun suoritat kyselytoimintoja kyselyeditorissa, kyselyn vaiheet luodaan ja luetellaan **Kyselyasetukset**-ruudun **Käytössä olevat vaiheet** -luettelossa. Jokaisella kyselyn vaiheella on sitä vastaava kaava, jota kutsutaan M-kieleksi. Jos haluat lisätietoja M-kaavakielestä, lue ohjeartikkeli [Lisätietoja Power BI -kaavoista](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

| Tehtävä | Kyselyn vaihe | Kaava |
| --- | --- | --- |
| Excel-työkirjaan yhdistäminen |Source |Source{[Name="Products"]}[Data] |
| Ensimmäisen rivin ylentäminen taulukon sarakeotsikoiksi |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> (Products) |
| Muiden sarakkeiden poistaminen vain tarvittavien sarakkeiden näyttämiseksi |RemovedOtherColumns |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| Tietotyypin vaihtaminen |Changed Type |Table.TransformColumnTypes(\#"Removed Other Columns",{{"UnitsInStock", Int64.Type}}) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>Tehtävä 2: tilaustietojen tuominen OData-syötteestä
Tässä tehtävässä tuot tilaustiedot. Tässä vaiheessa muodostat yhteyden myyntijärjestelmään. Tuot tiedot Power BI Desktopiin OData-syötteestä (tässä esimerkissä sen nimi on Northwind), joka löytyy seuraavasta URL-osoitteesta ja jonka voit kopioida ja sitten liittää alla olevien vaiheiden avulla: <http://services.odata.org/V3/Northwind/Northwind.svc/> 

### <a name="step-1-connect-to-an-odata-feed"></a>Vaihe 1: OData-syötteeseen yhdistäminen
1. Valitse kyselyeditorin **Aloitus**-valintanauhavälilehdessä **Nouda tiedot**.
2. Siirry selaamalla tietolähteeseen **OData-syöte**.
3. Liitä **OData-syöte**-valintaikkunassa Northwind OData -syötteen **URL**-osoite.
4. Valitse **OK**.
5. Valitse **Siirtymistoiminto**-ruudussa **Orders**-taulukko ja valitse sitten **Muokkaa**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>Näet esikatselun napsauttamalla taulukon nimeä valitsematta valintaruutua.

### <a name="step-2-expand-the-orderdetails-table"></a>Vaihe 2: Order\_Details-taulukon laajentaminen
**Orders**-taulukko sisältää viittauksen **Details**-taulukkoon, joka sisältää kuhunkin tilaukseen sisältyneet yksittäiset tuotteet. Kun muodostat yhteyksiä tietolähteisiin, joissa on useita taulukoita (esimerkiksi relaatiotietokantaan), voit muodostaa kyselyn tällaisten viittausten avulla. 

Tässä vaiheessa laajennat **Order\_Details**-taulukon, joka liittyy **Orders**-taulukkoon, yhdistääksesi **ProductID**-, **UnitPrice**- ja **Quantity**-sarakkeet **Order\_Details**-taulukosta **Orders**-taulukkoon. Tässä esitetään näiden taulukoiden tiedot:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

**Laajenna**-toiminto yhdistää sarakkeet liittyvästä taulukosta aihetaulukkoon. Kun kysely suoritetaan, rivit liittyvästä taulukosta (**Order\_Details**) yhdistetään aihetaulukon (**Orders**) riveihin.

Kun laajennat **Order\_Details** -taulukon, kolme uutta saraketta ja lisärivejä lisätään **Orders**-taulukkoon, yksi kullekin riville sisäkkäisessä tai liittyvässä taulukossa.

1. Siirry **kyselynäkymässä** **Order\_Details**-sarakkeeseen.
2. Valitse **Order\_Details**-sarakkeen laajennuskuvake (![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)).
3. Toimi avattavassa **Expand**-valikossa seuraavasti:
   1. Jos haluat tyhjentää kaikki sarakkeet, valitse **(Valitse kaikki sarakkeet)**.
   2. Valitse **ProductID**, **UnitPrice** ja **Quantity**.
   3. Valitse **OK**.
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>Vaihe 3: muiden sarakkeiden poistaminen vain tarvittavien sarakkeiden näyttämiseksi
Tässä vaiheessa poistat kaikki muut sarakkeet paitsi **OrderDate-, ShipCity-**, **ShipCountry**-, **Order\_Details.ProductID**-, **Order\_Details.UnitPrice**- ja **Order\_Details.Quantity**-sarakkeet. Edellisessä vaiheessa käytit **Poista muut sarakkeet** -toimintoa. Tässä tehtävässä poista valitut sarakkeet.

1. Valitse **kyselynäkymässä** kaikki sarakkeet suorittamalla kohdat a. ja b. seuraavasti:
   1. Napsauta ensimmäistä saraketta (**OrderID**).
   2. Paina vaihtonäppäintä samalla, kun napsautat viimeistä saraketta (**Shipper**).
   3. Nyt kun kaikki sarakkeet on valittu, poista seuraavien sarakkeiden valinta painamalla Ctrl-näppäintä samalla, kun napautat sarakkeita **OrderDate**, **ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** ja **Order\_Details.Quantity**.
2. Nyt kun valittuna ovat vain sarakkeet, jotka haluamme poistaa, napsauta hiiren kakkospainikkeella minkä tahansa valitun sarakkeen otsikkoa ja valitse **Poista sarakkeet**.

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>Vaihe 4: jokaisen Order\_Details-rivin kokonaissumman laskeminen
Power BI Desktopilla voit luoda laskelmia sarakkeista, joita tuot. Näin voit monipuolistaa tietoja, joihin muodostat yhteyden. Tässä vaiheessa luot **mukautetun sarakkeen**, jolla lasket jokaisen **Order\_Details**-rivin kokonaissumman.

Voit laskea jokaisen **Order\_Details**-rivin kokonaissumman seuraavasti:

1. Valitse **Lisää sarake** -valintanauhavälilehdestä **Lisää** **mukautettu sarake**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Kirjoita **Lisää mukautettu sarake** -valintaikkunan **Mukautettu sarakekaava** -tekstiruutuun **[Order\_Details.UnitPrice]** \* **[Order\_Details.Quantity]**.
3. Kirjoita **Uuden sarakkeen nimi** -tekstiruutuun **LineTotal**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. Valitse **OK**.

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>Vaihe 5: LineTotal-kentän tietotyypin määrittäminen
1. Napsauta **LineTotal**-saraketta hiiren kakkospainikkeella.
2. Valitse **Muuta tyyppi** ja sitten **Desimaaliluku**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>Vaihe 6: kyselyn sarakkeiden uudelleennimeäminen ja -järjestäminen
Tässä vaiheessa viimeistelet mallin ja teet siitä helppokäyttöisemmän raporttien luomisen yhteydessä nimeämällä lopulliset sarakkeet uudelleen ja vaihtamalla niiden järjestystä.

1. Vedä **kyselyeditorissa** **LineTotal**-sarake vasemmalle **ShipCountry**-sarakkeen perään.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. Poista *Order\_Details.*-etuliite **Order\_Details.ProductID**-, **Order\_Details.UnitPrice**- ja **Order\_Details.Quantity**-sarakkeista kaksoisnapsauttamalla kutakin sarakeotsikkoa ja poistamalla sitten teksti sarakkeen nimestä.

### <a name="power-bi-desktop-steps-created"></a>Luodut Power BI Desktopin vaiheet
Kun suoritat kyselytoimintoja kyselyeditorissa, kyselyn vaiheet luodaan ja luetellaan **Kyselyasetukset**-ruudun **Käytössä olevat vaiheet** -luettelossa. Jokaisella kyselyvaiheella on sitä vastaava Power Query -kaava, jota kutsutaan M-kieleksi. Jos haluat lisätietoja M-kaavakielestä, lue ohjeartikkeli [Lisätietoja Power BI -kaavoista](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "Lisätietoja Power BI -kaavoista").

| Tehtävä | Kyselyn vaihe | Kaava |
| --- | --- | --- |
| OData-syötteeseen yhdistäminen |Source |Source{[Name="Orders"]}[Data] |
| Order\_Details-taulukon laajentaminen |Expand Order\_Details |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| Muiden sarakkeiden poistaminen vain tarvittavien sarakkeiden näyttämiseksi |RemovedColumns |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Expand Order\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| Jokaisen Order\_Details-rivin kokonaissumman laskeminen |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>Tehtävä 3: Products- ja Total Sales -kyselyiden yhdistäminen
Power BI Desktop ei vaadi kyselyiden yhdistämistä, jotta voit raportoida niistä. Voit sen sijaan luoda tietojoukkojen välille **suhteita**. Voit luoda näitä suhteita missä tahansa sarakkeessa, joka on yhteinen tietojoukoillesi. Saat lisätietoja ohjeartikkelista [Suhteiden luominen ja hallinta](desktop-create-and-manage-relationships.md).

Tässä opetusohjelmassa meillä on Orders- ja Products-tietoja, joilla on yhteinen ProductID-kenttä, joten meidän täytyy varmistaa, että niiden välillä on yhteys mallissa, jota käytämme Power BI Desktopissa. Määritä Power BI Desktopissa, että kummankin taulukon sarakkeet liittyvät toisiinsa (eli sarakkeet, joilla on samat arvot). Power BI Desktop määrittää suhteen suunnan ja kardinaliteetin puolestasi. Joissain tapauksissa se jopa tunnistaa suhteita automaattisesti.

Tässä tehtävässä varmistat, että Power BI Desktopissa on luotu suhde **Products**- ja **Total Sales**-kyselyiden välille.

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>Vaihe 1: Products- ja Total Sales -kyselyiden välisen suhteen vahvistaminen
1. Ensin meidän täytyy ladata kyselyeditorilla luomamme malli Power BI Desktopiin. Valitse kyselyeditorin **Aloitus**-valintanauhavälilehdessä **Sulje ja lataa**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Power BI Desktop lataa tiedot kahdesta kyselystä.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. Kun tiedot on ladattu, valitse **Aloitus**-valintanauhan **Suhteiden hallinta** -painike.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. Valitse **Uusi…**- painike
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. Kun yritämme luoda suhdetta, näemme, että sellainen on jo olemassa! Kuten **Luo suhde** -valintaikkunasta näkyy (himmennetyistä sarakkeista), kummankin kyselyn **ProductID**-kentille on jo luotu suhde.
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. Valitse **Peruuta** ja valitse sitten Power BI Desktopin **suhdenäkymä**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. Näemme seuraavan tapauksen, joka visualisoi kyselyiden välisen suhteen.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. Kun kaksoisnapsautat kyselyt yhdistävää viivaa, näyttöön avautuu **Muokkaa suhdetta** -valintaikkuna.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. Meidän ei tarvitse tehdä muutoksia, joten suljen **Muokkaa suhdetta** -valintaikkunan valitsemalla **Peruuta**.

## <a name="task-4-build-visuals-using-your-data"></a>Tehtävä 4: tietoihin perustuvien visualisointien luominen
Power BI Desktopissa voit luoda useita erilaisia visualisointeja, joiden avulla voit analysoida tietojasi. Voit luoda raportteja, joissa on useita sivuja, joista jokainen voi sisältää useita visualisointeja. Visualisointien toimintojen avulla voit analysoida ja tutkia tietojasi. Saat lisätietoja raporttien muokkaamisesta ohjeartikkelista [Raportin muokkaaminen](service-interact-with-a-report-in-editing-view.md).

Tässä tehtävässä luot raportin, joka perustuu aiemmin ladattuihin tietoihin. Valitset Kentät-ruudussa sarakkeet, joista luot visualisoinnit.

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>Vaihe 1: Units in Stock by Product- ja Total Sales by Year -tiedot näyttävien kaavioiden luominen
Vedä **UnitsInStock** kenttäruudusta (se on näytön oikeassa reunassa) tyhjään kohtaan alustalla. Ohjelma luo Taulukko-visualisoinnin. Vedä sitten ProductName Akseli-ruutuun, joka löytyy Visualisoinnit-ruudun alemmasta puoliskosta. Valitse **Lajitteluperuste \> UnitsInStock** visualisoinnin oikeasta yläkulmasta.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

Vedä **OrderDate** alustalle ensimmäisen kaavion alle ja vedä sitten LineTotal (taas Kentät-ruudusta) visualisointiin ja valitse sitten Viivakaavio. Ohjelma luo seuraavan visualisoinnin.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 Vedä sitten **ShipCountry** alustalle tyhjään kohtaan oikealle ylhäälle. Koska valitsit maantieteellisen kentän, ohjelma luo kartan automaattisesti. Vedä nyt **LineTotal** **Arvot**-kenttään. Kunkin maan ympyrät kartalla vastaavat suhteelliselta kooltaan **LineTotal**-rivin arvoa, joka kuvaa tiettyyn maahan toimitettujen tilausten kokonaismäärää.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>Vaihe 2: tarkemmat analyysit raportin visualisointien avulla
Power BI Desktopissa voit käyttää visualisointeja, jotka ristiinkorostavat ja suodattavat toisiaan, jotta voit tunnistaa tiedoista tärkeitä asioita ja suuntauksia. Saat lisätietoja ohjeartikkelista [Suodattaminen ja korostaminen raporteissa](power-bi-reports-filters-and-highlighting.md).

1. Napsauta vaaleansinistä ympyrää, joka on kartalla kohdassa **Canada.** Huomaatko, miten muut visualisoinnit suodatetaan näyttämään Stock-tiedot (**ShipCountry**) ja Total Orders -tiedot (**LineTotal**) vain Kanadasta.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>Kattava myyntianalyysiraportti
Kun olet suorittanut kaikki nämä vaiheet, sinulla on myyntiraportti, joka yhdistää tietoja Products.xlsx-tiedostosta ja Northwind OData -syötteestä. Raportista näet visualisointeja, joiden avulla voit analysoida eri maiden myyntitietoja. Voit ladata tämän opetusohjelman valmiin Power BI Desktop tiedoston [täältä](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix).

## <a name="next-steps"></a>Seuraavat vaiheet
* [Lue muita Power BI Desktop -opetusohjelmia](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Katso Power BI Desktop -videoita](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Käy Power BI -keskustelupalstalla](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Lue Power BI -blogia](http://go.microsoft.com/fwlink/?LinkID=519327)


