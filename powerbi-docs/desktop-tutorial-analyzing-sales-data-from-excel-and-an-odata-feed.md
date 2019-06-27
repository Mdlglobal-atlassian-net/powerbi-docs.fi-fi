---
title: 'Opetusohjelma: Excelin ja OData-syötteen tietojen yhdistäminen Power BI Desktopissa'
description: 'Opetusohjelma: Excelin ja OData-syötteen tietojen yhdistäminen'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 05/31/2019
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 757a2ca5a88e8ee98aa1c460c30e001f14bc6789
ms.sourcegitcommit: 88e2a80b95b3e735689e75da7c35d84e24772e13
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/07/2019
ms.locfileid: "66814349"
---
# <a name="tutorial-combine-sales-data-from-excel-and-an-odata-feed"></a>Opetusohjelma: Excelin ja OData-syötteen myyntitietojen yhdistäminen

Tiedot ovat usein monessa tietolähteessä. Sinulla voi olla esimerkiksi kaksi tietokantaa: yksi tuotetietoja ja toinen myyntitietoja varten. **Power BI Desktopissa** voit yhdistää tietoja eri lähteistä ja luoda kiinnostavia tietojen analyysejä ja visualisointeja. 

Tässä opetusohjelmassa yhdistät tietoja kahdesta tietolähteestä: 

1. Excel-työkirjasta, joka sisältää tuotetiedot
2. OData-syötteestä, joka sisältää tilaustiedot

Tuot kunkin tietojoukon ja teet niille muuntamis- ja koostamistoimintoja. Sen jälkeen tuotat kahden lähteen tiedoista myyntianalyysiraportin, joka sisältää vuorovaikutteisia visualisointeja. Voit soveltaa näitä menetelmiä myöhemmin myös SQL Server -kyselyihin, CSV-tiedostoihin ja muihin tietolähteisiin Power BI Desktopissa.

>[!NOTE]
>Power BI Desktopissa tehtävä voidaan suorittaa usein monilla eri tavoilla. Voit esimerkiksi napsauttaa hiiren kakkospainikkeella tai käyttää **Lisäasetukset**-valikkoa sarakkeeseen tai soluun, nähdäksesi lisää valintanauhan vaihtoehtoja. Useita vaihtoehtoisia menetelmiä on kuvattu alla olevissa vaiheissa. 

## <a name="import-excel-product-data"></a>Excel-tuotetietojen tuominen

Tuo ensin tuotetiedot Excelin Products.xlsx-työkirjasta Power BI Desktopiin.

1. [Lataa Products.xlsx-niminen Excel-työkirja](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx) ja tallenna se nimellä **Products.xlsx**.
   
2. Valitse avattavan valikon nuoli kohdassa **Nouda tiedot** **Aloitus**-välilehdellä ja valitse sitten **Excel**-vaihtoehto avattavasta **Yleisin**-valikosta. 
   
   ![Nouda tiedot](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
   
   >[!NOTE]
   >Voit myös valita **Nouda tiedot** -kohteen itse tai valita **Nouda tiedot** Power BI:n **Aloittaminen**-valintaikkunasta. Valitse sitten **Excel** tai **Tiedosto** > **Excel** **Nouda tiedot** -valintaikkunassa, ja valitse sitten **Yhdistä**.
   
3. Siirry **Avaa**-valintaikkunassa tiedoston **Products.xlsx** kohdalle, ja valitse sitten **Avaa**.
   
4. Valitse **Siirtymistoiminto**-ruudussa **Products**-taulukko ja valitse sitten **Muokkaa**.
   
   ![Excelin siirtymisruutu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)
   
Taulukon esikatselu avautuu **Power Query -editoriin**, jonka avulla voit muokata ja puhdistaa tietoja.
   
![Power Query -editori](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_3.png)
   
>[!NOTE]
>Voit avata **Power Query -editorin** myös valitsemalla **Muokkaa kyselyitä** > **Muokkaa kyselyitä** Power BI Desktopin **Aloitus**-valintanauhasta tai napsauttamalla sitä hiiren kakkospainikkeella tai valitsemalla **Lisäasetukset** minkä tahansa kyselyn kohdalla **raporttinäkymässä**, ja valitsemalla sitten **Muokkaa kyselyä**.

## <a name="clean-up-the-products-columns"></a>Tuotesarakkeiden siistiminen

Yhdistetty raportti käyttää Excel-työkirjan **ProductID**-, **ProductName**-, **QuantityPerUnit**-, ja **UnitsInStock**-sarakkeita. Voit poistaa muut sarakkeet. 

1. Valitse **Power Query -editorissa** **ProductID**-, **ProductName**-, **QuantityPerUnit**- ja **UnitsInStock**-sarakkeet. Voit valita useamman kuin yhden sarakkeen **Ctrl**+**Napsautus** -yhdistelmällä tai valitse vierekkäisiä sarakkeita painamalla **Vaihto**+**Napsautus**.
   
2. Napsauta hiiren kakkospainikkeella jotakin valituista otsikoista. Valitse avattavasta valikosta **Poista muut sarakkeet**. 
   Voit myös valita **Poista sarakkeet** > **Poista muut sarakkeet** **Hallitse sarakkeita** -ryhmässä **Aloitus**-valintanauhassa. 
   
   ![Poista muut sarakkeet](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_removeothercolumns.png)

## <a name="import-the-odata-feeds-order-data"></a>OData-syötteen tilaustietojen tuominen

Tuo seuraavaksi tilaustiedot järjestelmästä mallin Northwind-myyntijärjestelmän OData-syötteestä. 

1. Valitse **Power Query -editorissa** **Uusi lähde** ja valitse sitten **Yleisin**-luettelosta **OData-syöte**. 
   
   ![Hanki OData](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata.png)
   
2. Liitä **OData-syöte**-valintaikkunassa Northwind OData -syötteen URL-osoite, `http://services.odata.org/V3/Northwind/Northwind.svc/`. Valitse **OK**.
   
   ![OData-syötteen valintaikkuna](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata2.png)
   
3. Valitse **siirtymisruudussa** **Orders**-taulukko, ja valitse sitten **OK** ladataksesi tiedot **Power Query -editoriin**.
   
   ![ODatan siirtymisruutu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_odatafeed.png)
   
   >[!NOTE]
   >**Siirtymisruudussa** voit nähdä esikatselun valitsemalla minkä tahansa taulukon nimen valintaruutua valitsematta.

## <a name="expand-the-order-data"></a>Laajenna tilaustiedot

Voit käyttää viittauksia taulukoiden välillä kyselyjen laatimiseksi yhdistäessäsi tietolähteisiin, joissa on useita taulukoita, kuten relaatiotietokantoja tai Northwind OData -syöte. **Tilaukset**-taulukko sisältää viittauksia useisiin liittyviin taulukoihin. Voit lisätä **Laajenna**-toiminnon avulla **ProductID**-, **UnitPrice**- ja **Quantity**-sarakkeet liittyvästä **Order_Details**-taulukosta kohdetaulukkoon ( **Orders**). 

1. Vieritä oikealle **Orders**-taulukossa, kunnes näet **Order_Details**-sarakkeen. Tietojen sijaan se sisältää viittauksia toiseen taulukkoon.
   
   ![Order_Details-sarake](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)
   
2. Valitse **Laajenna**-kuvake (![Laajenna-kuvake](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)) **Order_Details**-sarakkeen otsikossa. 
   
3. Toimi avattavassa **Expand**-valikossa seuraavasti:
   
   1. Jos haluat tyhjentää kaikki sarakkeet, valitse **(Valitse kaikki sarakkeet)** .
      
   2. Valitse **ProductID**, **UnitPrice** ja **Quantity**, ja valitse sitten **OK**.
      
      ![Laajenna-valintaikkuna](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)

Kun olet laajentanut **Order_Details**-taulukon, kolme uutta sisäkkäistä taulukon saraketta korvaa **Order_Details**-sarakkeen. Taulukossa on uusia, kuhunkin tilaukseen lisättyjä tietoja sisältäviä rivejä. 

![Laajennetut sarakkeet](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

## <a name="create-a-custom-calculated-column"></a>Mukautetun lasketun sarakkeen luominen

Power Query -editorin avulla voit luoda laskutoimituksia ja täydentää tietoja mukautetuilla kentillä. Luot mukautetun sarakkeen, joka laskee yhteen tilauksen kunkin rivinimikkeen hinnan kertomalla yksikköhinnan nimikemäärällä.

1. Valitse Power Query -editorin **Lisää sarake** -valintanauhavälilehdeltä **Mukautettu sarake**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
   
2. Kirjoita **Mukautettu sarake** -valintaikkunassa **LineTotal** **Uuden sarakkeen nimi** -kenttään.

3. **Mukautettu sarakkeen kaava** -kentässä, kohdan **= jälkeen **[Order_Details.UnitPrice]** \* **[Order_ Details.Quantity]** . (Voit myös valita kenttien nimet **Käytettävissä olevat sarakkeet** -vieritysruudusta ja valita **<< Lisää** niiden kirjoittamisen sijaan.) 

4. Valitse **OK**.
   
   ![Mukautettu sarake -valintaikkuna](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)

   Uusi **LineTotal**-kenttä näkyy viimeisenä sarakkeena **Tilaukset**-taulukossa.

## <a name="set-the-new-fields-data-type"></a>Uuden kentän tietotyypin määrittäminen

Kun Power Query -editori muodostaa yhteyden tietoihin, se olettaa kunkin kentän tietotyypin tietojen esittämistä varten. Otsikkokuvake ilmaisee kunkin kentän määritetyn tietotyypin. Voit katsoa tietotyypin myös valintanauhan **Aloitus**-välilehden **Muunto**-ryhmän **Tietotyyppi**-kohdasta. 

Uuden **LineTotal**-sarakkeen tietotyyppi on **Mikä tahansa**, mutta se sisältää valuutta-arvoja. Voit määrittää tietotyypin napsauttamalla hiiren kakkospainikkeella **LineTotal**-sarakeotsikkoa, valitsemalla **Vaihda tyyppiä** -vaihtoehdon avattavasta valikosta ja valitsemalla sitten **Kiinteä desimaaliluku**. 

![Vaihda tietotyyppiä](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)

>[!NOTE]
>Voit myös valita **LineTotal**-sarakkeen ja painaa sitten alanuolipainiketta **Tietotyyppi**-kohdassa **Muunnos**-alueella **Aloitus**-valintanauhavälilehdessä, ja valita sitten **Kiinteä desimaaliluku** -vaihtoehdon.

## <a name="clean-up-the-orders-columns"></a>Puhdista tilaussarakkeet

Voit poistaa, nimetä uudelleen ja järjestää uudelleen muutamia sarakkeita, jotta malli toimii paremmin raporttien kanssa.

Raporttisi käyttää seuraavia sarakkeita:

* **OrderDate**
* **ShipCity**
* **ShipCountry**
* **Order_Details.ProductID**
* **Order_Details.UnitPrice**
* **Order_Details.Quantity**
* **LineTotal**

Valitse nämä sarakkeet ja **Poista muut sarakkeet** aivan kuten teit Excel-tiedoille. Vaihtoehtoisesti voit valita luetteloimattomat sarakkeet, napsauttaa niistä yhtä hiiren kakkospainikkeella ja valita **Poista sarakkeet**. 

Voit nimetä uudelleen sarakkeet, joiden nimi alkaa ”**Order_Details.** ”, jotta niiden lukeminen olisi helpompaa:

1. Kaksoisnapsauta tai napauta ja pidä painettuna kutakin sarakeotsikkoa, tai napauta hiiren kakkospainikkeella sarakeotsikkoa, ja valitse **Nimeä uudelleen** avattavasta valikosta. 

2. Poista **Order_Details.** -etuliite kunkin sarakkeen nimestä ja paina **Enter**.

Tee vielä lopuksi **LineTotal**-sarakkeesta helpommin käytettävä vetämällä ja pudottamalla se vasemmalle, aivan **ShipCountry**-sarakkeen oikealle puolelle.

![Puhdistettu taulukko](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

## <a name="review-the-query-steps"></a>Kyselyn vaiheiden tarkistaminen

Power Query -editorin toiminnot muotoilevat ja muuntavat tietojen tallennusta. Kukin toiminto näkyy oikealla **Kyselyasetukset**-ruudun **Käytössä olevat vaiheet** -kohdassa. Voit vaihe palata takaisin **Käytössä olevat vaiheet** -kohtaan, jos haluat tarkastella, muokata, poistaa tai järjestää niitä uudelleen. Edeltävien vaiheiden muokkaamisessa on kuitenkin riskejä, sillä se voi aiheuttaa virheitä myöhemmissä vaiheissa.

Valitse kaikki kyselyt **Kyselyt**-luettelossa Power Query -editorin vasemmalla puolella ja tarkista **Käytössä olevat vaiheet** kohdassa **Kyselyasetukset**. Kun olet ottanut aiemmat tietojen muunnokset käyttöön, kahden kyselyn **käytössä olevien vaiheiden** pitäisi näyttää seuraavalta:

![Tuotteiden kyselyn käytössä olevat vaiheet](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png) &nbsp;&nbsp; ![Tilausten kyselyn käytössä olevat vaiheet](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

>[!TIP]
>Käytössä olevien vaiheiden pohjana ovat **Power Query -kielellä** eli [**M**-kielellä](https://docs.microsoft.com/powerquery-m/power-query-m-reference) kirjoitetut kaavat. Voit tarkastella ja muokata kaavoja valitsemalla **Laajennettu editori** valintanauhan Aloitus-välilehden **Kysely**-ryhmästä. 

## <a name="import-the-transformed-queries"></a>Muunnettujen kyselyjen tuominen

Kun olet tyytyväinen muunnettuihin tietoihin ja olet valmis tuomaan ne Power BI Desktopin raporttinäkymään, valitse **Sulje ja ota käyttöön** > **Sulje ja ota käyttöön** **Aloitus**-välilehden **Sulje**-ryhmästä. 

![Sulje ja ota käyttöön](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)

Kun tiedot on ladattu, kyselyt näkyvät Power BI Desktopin raporttinäkymän **Kentät**-luettelossa.

![Kyselyt Kentät-luettelossa](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="manage-the-relationship-between-the-datasets"></a>Tietojoukkojen välisen suhteen hallinta

Power BI Desktop ei vaadi kyselyiden yhdistämistä, jotta voisit raportoida niistä. Voit kuitenkin käyttää tietojoukkojen välisiä suhteita niiden yhteisten kenttien perusteella raporttiesi laajentamiseksi ja täydentämiseksi. Power BI Desktop voi havaita suhteet automaattisesti tai voit luoda ne Power BI Desktopin **Suhteiden hallinta** -valintaikkunassa. Saat lisätietoja ohjeartikkelista [Suhteiden luominen ja hallinta Power BI Desktopissa](desktop-create-and-manage-relationships.md).

Jaettu **ProductID**-kenttä luo suhteen tämän opetusohjelman tilaus- ja tuotetietojoukkojen välille. 

1. Valitse Power BI Desktopin raporttinäkymässä **Suhteiden hallinta** -vaihtoehto **Aloitus**-välilehden valintanauhan **Suhteet**-alueella.
   
   ![Suhteiden hallinta -valintanauha](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
   
2. Huomaa **Suhteiden hallinta** -valintaikkunassa, että Power BI Desktop on jo havainnut ja luetellut aktiiviset suhteet tuote- ja tilaustaulukoiden välillä. Jos haluat tarkastella suhdetta, valitse **Muokkaa**. 
   
   ![Suhteiden hallinta -valintaikkuna](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
   
   **Muokkaa suhdetta** -valintaikkuna avautuu ja näyttää kyseisen suhteen tiedot.  
   
   ![Muokkaa suhdetta -valintaikkuna](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
   
3. Power BI Desktop on havainnut suhteen automaattisesti oikein, joten voit valita **Peruuta** ja sitten **Sulje**.

Valitse Power BI Desktopin vasemmasta reunasta **Malli**, jotta voit tarkastella ja hallita kyselyn suhteita. Kaksoisnapsauta nuolta rivillä, joka yhdistää kaksi kyselyä, niin **Muokkaa suhdetta** -valintaikkuna avautuu suhteen tarkastelua ja muokkausta varten. 

![Suhdenäkymä](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)

Voit palata raporttinäkymään Suhteet-näkymästä valitsemalla **Raportti**-kuvakkeen. 

![Raporttinäkymäkuvake](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)

## <a name="create-visualizations-using-your-data"></a>Visualisointien luonti tietojen avulla

Voit luoda erilaisia visualisointeja Power BI Desktopin tarkistusnäkymässä saadaksesi merkityksellisiä tietoja. Raporteissa voi olla useita sivuja, joista jokainen voi sisältää useita visualisointeja. Visualisointien toimintojen avulla tietoja voidaan analysoida ja tutkia. Katso lisätietoja kohdasta [Raportin käsittely Power BI -palvelun muokkausnäkymässä](service-interact-with-a-report-in-editing-view.md).

Voit käyttää kumpaakin tietojoukkoasi ja niiden välistä suhdetta myyntitietojesi visualisoinnin ja analysoinnin tukena. 

Luo ensin pinottu pylväskaavio, joka käyttää kummankin kyselyn kenttiä kunkin tilatun tuotteen määrän näyttämiseksi. 

1. Valitse **Quantity**-kenttä **Orders**-kohdasta oikealla olevassa **Fields**-ruudussa tai vedä se tyhjään tilaan pohjalla. Tämä luo pinotun pylväskaavion, joka näyttää kaikkien tilattujen tuotteiden kokonaismäärän. 
   
2. Valitse **ProductName**-kenttä **Products**-kohdasta **Fields**-ruudussa tai vedä se kaavioon kunkin tilatun tuotteen määrän näyttämiseksi. 
   
3. Lajittele tuotteet suurimmasta tilatusta määrästä pienimpään tilattuun määrään valitsemalla **Lisäasetukset**-kohdan kolme pistettä ( **...** ) visualisoinnin oikeassa yläkulmassa ja valitsemalla sitten **Lajittele määrän mukaan**.
   
4. Käytä kaavion kulmissa olevia kahvoja kaavion suurentamiseksi, jotta enemmän tuotenimiä tulee näkyviin. 
   
   ![Määrän osoittava palkkikaavio ProductName-sarakkeen mukaan](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/19.png)

Luo seuraavaksi kaavio, joka näyttää tilauksen dollarisummat (**LineTotal**) ajanjaksolla (**OrderDate**). 

1. Kun mitään ei ole valittuna pohjalla, valitse **LineTotal** **Orders**-kohdasta **Fields**-ruudussa tai vedä se tyhjään kohtaan pohjalla. Pinottu pylväskaavio näyttää kaikkien tilausten dollarisumman. 
   
2. Valitse pinottu kaavio ja valitse sitten **Orders**-kohdasta **OrderDate** tai vedä se kaavioon. Kaaviossa näkyvät nyt kunkin tilauspäivämäärän summat. 
   
3. Muuta visualisoinnin kokoa vetämällä sen kulmia, jotta näet enemmän tietoja. 
   
   ![Viivakaavio, joka näyttää LineTotals-arvot OrderDate-sarakkeen mukaan](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/20.png)
   
   >[!TIP]
   >Jos kaaviossa näkyy vain vuodet (vain kolme arvopistettä), paina nuolta kohdan **OrderDate** vieressä **Akseli**-kentässä **Visualisoinnit**-ruudussa ja valitse **OrderDate**-vaihtoehto **Date Hierarchyn** sijaan. 

Luo lopuksi kartta-visualisointi, joka näyttää kunkin maan tilausten summat. 

1. Kun mitään ei ole valittuna pohjalla, valitse **ShipCountry** **Orders**-kohdasta **Fields**-ruudussa tai vedä se tyhjään kohtaan pohjalla. Power BI Desktop havaitsee, että tiedot ovat maiden nimiä. Se luo sitten automaattisesti karttavisualisoinnin, jossa on arvopiste sellaisten maiden kohdalla, joista on saatu tilauksia. 
   
2. Jotta tietojen arvopisteiden koko vastaa kunkin maan tilausmääriä, vedä **LineTotal**-kenttä kartalle. Voit myös vetää sen **Vedä tietokentät tähän** -kohtaan, joka sijaitsee **Visualisoinnit** ruudun **Koko**-kohdassa. Kartalla olevien ympyröiden koot vastaavat nyt kunkin maan tilausten dollarisummia. 
   
   ![Kartta-visualisointi, joka näyttää LineTotals-arvot ShipCountry-sarakkeen mukaan](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/21.png)

## <a name="interact-with-your-report-visuals-to-analyze-further"></a>Analysoi tietoja tarkemmin raportin visualisointien avulla

Power BI Desktopissa voit käyttää visualisointeja, jotka ristiinkorostavat ja suodattavat toisiaan. Näin voit tunnistaa tiedoista uusia suuntauksia. Saat lisätietoja kohdasta [Suodattaminen ja korostaminen Power BI -raporteissa](power-bi-reports-filters-and-highlighting.md). 

Kyselyjesi välisen suhteen vuoksi yhden visualisoinnin vuorovaikutukset vaikuttavat myös kaikkiin muihin sivulla oleviin visualisointeihin. 

Valitse kartta-visualisoinnissa ympyrä, joka on keskitetty **Kanadaan**. Kaksi muuta visualisointia suodattuvat korostamaan vain Kanadaan liittyvät rivisummat ja tilausmäärät.

![Kanadan suodatetut myyntitiedot](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/22.png)

Valitse **Quantity by ProductName**-kaaviosta tuote, niin kartan ja päivämäärän kaaviosuodatus vastaa kyseisen tuotteen tietoja. Valitse **LineTotal by OrderDate**-kaaviopäivä, niin kartan ja tuotteen kaaviosuodatus näyttää kyseisen päivämäärän tiedot. 
>[!TIP]
>Poista valinta valitsemalla se uudelleen tai valitse jokin muu visualisointi. 

## <a name="complete-the-sales-analysis-report"></a>Täydennä myyntianalyysiraportti

Valmis raportti yhdistää tiedot Excelin Products.xlsx-tiedostosta ja Northwind OData -syötteestä visualisointeihin, jotka auttavat analysoimaan eri maiden, aikavälien ja tuotteiden tilaustietoja. Kun raportti on valmis, voit [ladata sen Power BI -palveluun](desktop-upload-desktop-files.md) ja jakaa sen muiden Power BI -käyttäjien kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Lue muita Power BI Desktop -opetusohjelmia](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Katso Power BI Desktop -videoita](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Käy Power BI -keskustelupalstalla](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Lue Power BI -blogia](http://go.microsoft.com/fwlink/?LinkID=519327)
