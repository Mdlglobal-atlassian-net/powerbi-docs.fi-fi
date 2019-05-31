---
title: 'Opetusohjelma: Excelin ja OData-syötteen tietojen yhdistäminen Power BI Desktopissa'
description: 'Opetusohjelma: Excelin ja OData-syötteen tietojen yhdistäminen'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 05/21/2018
ms.author: v-thepet
LocalizationGroup: Learn more
ms.openlocfilehash: 94e40681d065591db008f8a9062d851e0bd83f61
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61368340"
---
# <a name="tutorial-combine-sales-data-from-excel-and-an-odata-feed"></a>Opetusohjelma: Excelin ja OData-syötteen myyntitietojen yhdistäminen

On yleistä, että tiedot ovat hajallaan useissa tietolähteissä: esimerkiksi tuotetiedot voivat olla yhdessä tietokannassa ja myyntitiedot toisessa. **Power BI Desktopissa** voit yhdistää tietoja eri lähteistä ja luoda kiinnostavia tietojen analyysejä ja visualisointeja. 

Tässä opetusohjelmassa opit yhdistämään tietoja kahdesta tietolähteestä: Excel-työkirjasta, joka sisältää tuotetiedot, ja OData-syötteestä, joka sisältää tilausten tiedot. Kun olet tuonut kunkin tietojoukon ja suorittanut muuntamis- ja koostamisvaiheet, voit käyttää kummankin lähteen tietoja luodaksesi myyntianalyysiraportin, jossa on vuorovaikutteisia visualisointeja. Näitä menetelmiä voi käyttää myös SQL Server -kyselyitä, CSV-tiedostoja ja muita tietolähteitä varten Power BI Desktopissa.

>[!NOTE]
>Power BI Desktopissa tehtävä voidaan suorittaa usein monilla eri tavoilla. Esimerkiksi monet valintanauhan valinnat ovat käytettävissä myös hiiren kakkospainikkeella tai sarakkeen tai solun **Lisäasetukset**-valikosta. Useita vaihtoehtoisia menetelmiä on kuvattu alla olevissa vaiheissa. 

## <a name="import-the-product-data-from-excel"></a>Tuotetietojen tuominen Excelistä

Tuo ensin tuotetiedot Excelin Products.xlsx-työkirjasta Power BI Desktopiin.

1. [Lataa Products.xlsx-niminen Excel-työkirja](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx) ja tallenna se nimellä **Products.xlsx**.
   
2. Valitse avattavan valikon nuoli kohdassa **Nouda tiedot** **Aloitus**-välilehdellä Power BI Desktopin nauhassa, ja valitse sitten **Excel**-vaihtoehto avattavasta **Yleisin**-valikosta. 
   
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

Yhdistetty raportti käyttää vain Excel-työkirjan **ProductID**-, **ProductName**-, **QuantityPerUnit**-, ja **UnitsInStock**-sarakkeita , joten voit poistaa muut sarakkeet. 

1. Valitse **Power Query -editorissa** **ProductID**-, **ProductName**-, **QuantityPerUnit**- ja **UnitsInStock**-sarakkeet (voit valita useita sarakkeita painamalla **Ctrl**+**napsautus** tai useita vierekkäisiä sarakkeita painamalla **Vaihto**+**napsautus**).
   
2. Napsauta hiiren kakkospainikkeella jotakin valituista otsikoista ja valitse **Poista muut sarakkeet** avattavasta valikosta poistaaksesi taulukosta kaikki paitsi valitut sarakkeet. 
   Voit myös valita **Poista sarakkeet** > **Poista muut sarakkeet** **Hallitse sarakkeita** -ryhmässä **Aloitus**-valintanauhassa. 
   
   ![Poista muut sarakkeet](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_removeothercolumns.png)

## <a name="import-the-order-data-from-an-odata-feed"></a>Tilaustietojen tuominen OData-syötteestä

Tuo seuraavaksi tilaustiedot järjestelmästä mallin Northwind-myyntijärjestelmän OData-syötteestä. 

1. Valitse **Power Query -editorissa** **Uusi lähde** ja valitse sitten **OData-syöte avattavasta**  **Yleisin**-luettelosta. 
   
   ![Hanki OData](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata.png)
   
2. Liitä **OData-syöte**-valintaikkunaan Northwind OData -syötteen URL-osoite, `http://services.odata.org/V3/Northwind/Northwind.svc/`, ja valitse sitten **OK**.
   
   ![OData-syötteen valintaikkuna](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata2.png)
   
3. Valitse **siirtymisruudussa** **Orders**-taulukko, ja valitse sitten **OK** ladataksesi tiedot **Power Query -editoriin**.
   
   ![ODatan siirtymisruutu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_odatafeed.png)
   
   >[!NOTE]
   >**Siirtymisruudussa** voit nähdä esikatselun valitsemalla minkä tahansa taulukon nimen valintaruutua valitsematta.

## <a name="expand-the-order-data"></a>Laajenna tilaustiedot

Kun yhdistät tietolähteisiin, joissa on useita taulukoita, kuten relaatiotietokantoja tai Northwind OData -syöte, voit käyttää viittauksia taulukoiden välillä kyselyjen laatimiseksi. **Tilaukset**-taulukko sisältää viittauksia useisiin liittyviin taulukoihin. Voit lisätä **ProductID**-, **UnitPrice**- ja **Quantity**-sarakkeet liittyvästä **Order_Details**-taulukosta kohdetaulukkoon ( **Orders**) käyttämällä **Laajenna**-toimintoa. 

1. Vieritä oikealle **Orders**-taulukossa, kunnes näet **Order_Details**-sarakkeen. Huomaa, että tietojen sijaan se sisältää viittauksia toiseen taulukkoon.
   
   ![Order_Details-sarake](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)
   
2. Valitse **Laajenna**-kuvake (![Laajenna-kuvake](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)) **Order_Details**-sarakkeen otsikossa. 
   
3. Toimi avattavassa **Expand**-valikossa seuraavasti:
   
   1. Jos haluat tyhjentää kaikki sarakkeet, valitse **(Valitse kaikki sarakkeet)** .
      
   2. Valitse **ProductID**, **UnitPrice** ja **Quantity**, ja valitse sitten **OK**.
      
      ![Laajenna-valintaikkuna](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)

Kun olet laajentanut **Order_Details**-taulukon, **Order_Details**-sarake korvataan kolmella uudella sarakkeella sisäkkäisestä taulukosta ja taulukossa on uusia rivejä kunkin tilauksen lisättyjä tietoja varten. 

![Laajennetut sarakkeet](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

## <a name="create-a-custom-calculated-column"></a>Mukautetun lasketun sarakkeen luominen

Power Query -editorin avulla voit luoda laskutoimituksia ja täydentää tietoja mukautetuilla kentillä. Luo mukautettu sarake, joka laskee yhteen tilauksen kunkin rivinimikkeen hinnan kertomalla yksikköhinnan nimikemäärällä.

1. Valitse Power Query -editorin **Lisää sarake** -valintanauhavälilehdeltä **Mukautettu sarake**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
   
2. Kirjoita **Mukautettu sarake** -valintaikkunassa **LineTotal** **Uuden sarakkeen nimi** -kenttään.

3. **Mukautettu sarakkeen kaava** -kentässä, kohdan **=** jälkeen, syötä **[Order_Details.UnitPrice]** \* **[Order_ Details.Quantity]** . (Voit myös valita kenttien nimet **Käytettävissä olevat sarakkeet** -vieritysruudusta ja valita **<< Lisää** niiden kirjoittamisen sijaan.) 
3. Valitse **OK**.
   
   ![Mukautettu sarake -valintaikkuna](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)

Uusi **LineTotal**-kenttä näkyy viimeisenä sarakkeena **Tilaukset**-taulukossa.

## <a name="set-the-data-type-for-the-new-field"></a>Määritä uuden kentän tietotyyppi

Kun Power Query -editori muodostaa yhteyden tietoihin, se määrittää kullekin kentälle parhaan tietotyypin ja näyttää tiedot sen mukaisesti. Kentille määritetyt tietotyypit näkyvät otsikoiden kuvakkeina tai **Tietotyyppi**-kohdassa **Muunnos**-ryhmässä **Aloitus**-valintanauhassa. 

Uuden **LineTotal**-sarakkeen tietotyyppi on **Mikä tahansa**, mutta sen arvot ovat valuuttana. Voit määrittää tietotyypin napsauttamalla hiiren kakkospainikkeella **LineTotal**-sarakeotsikkoa, valitsemalla **Vaihda tietotyyppiä** -vaihtoehdon avattavasta valikosta ja valitsemalla sitten **Kiinteä desimaaliluku**. 

![Vaihda tietotyyppiä](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)

>[!NOTE]
>Voit myös valita **LineTotal**-sarakkeen ja painaa sitten alanuolipainiketta **Tietotyyppi**-kohdassa **Muunnos**-alueella **Aloitus**-valintanauhavälilehdessä, ja valita sitten **Kiinteä desimaaliluku** -vaihtoehdon.

## <a name="clean-up-the-orders-columns"></a>Puhdista tilaussarakkeet

Voit poistaa, nimetä uudelleen ja järjestää uudelleen muutamia sarakkeita, jotta malli toimii paremmin raporttien kanssa.

Raporttisi käyttää vain **OrderDate**-, **ShipCity**-, **ShipCountry**-, **Order_Details.ProductID**-, **Order_Details.UnitPrice**- ja **Order_Details.Quantity**-sarakkeita. Voit valita nämä sarakkeet ja käyttää **Poista muut sarakkeet** -toimintoa, kuten teit Excel-tietojen kanssa, tai voit valita kaikki muut paitsi nämä sarakkeet, napsauttaa niitä hiiren kakkospainikkeella ja poistaa ne kaikki valitsemalla **Poista sarakkeet**. 

Voit tehdä **Order_Details.ProductID**-, **Order_Details.UnitPrice**- ja **Order_Details.Quantity**-sarakkeista helpommin tunnistettavia poistamalla *Order_Details.* -etuliitteet sarakkeiden nimistä. Anna sarakkeille siten nimiksi **ProductID**, **UnitPrice** ja **Quantity**:

1. Kaksoisnapsauta tai napauta ja pidä painettuna kutakin sarakeotsikkoa, tai napauta hiiren kakkospainikkeella sarakeotsikkoa, ja valitse **Nimeä uudelleen** avattavasta valikosta. 
2. Poista *Order_Details.* -etuliite kunkin sarakkeen nimestä ja paina **Enter**.

Tee vielä lopuksi **LineTotal**-sarakkeesta helpommin käytettävä vetämällä ja pudottamalla se vasemmalle, aivan **ShipCountry**-sarakkeen oikealle puolelle.

![Puhdistettu taulukko](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

## <a name="review-the-query-steps"></a>Kyselyn vaiheiden tarkistaminen

Kun muotoilit ja muunsit tietoja Power Query -editorissa, kukin vaihe tallennettiin **Käytössä olevat vaiheet** -alueelle, joka on Power Query -editorin oikealla puolella olevassa **Kyselyasetukset**-ruudussa. Voit palata takaisin käytössä oleviin vaiheisiin, jos haluat nähdä, mitä muutoksia olet tehnyt, ja muokata tai poistaa niitä tai järjestää ne tarvittaessa uudelleen (vaikka tämä voi olla riskialtista, koska edeltävien vaiheiden muuttaminen voi haitata myöhempiä vaiheita). 

Valitse kaikki kyselyt **Kyselyt**-luettelossa Power Query -editorin vasemmalla puolella ja tarkista **Käytössä olevat vaiheet** kohdassa **Kyselyasetukset**. Kun olet ottanut aiemmat tietojen muunnokset käyttöön, kahden kyselyn käytössä olevien vaiheiden pitäisi näyttää seuraavalta:

![Tuotteiden kyselyn käytössä olevat vaiheet](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png) &nbsp;&nbsp; ![Tilausten kyselyn käytössä olevat vaiheet](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

>[!TIP]
>Käytössä olevien vaiheiden pohjana ovat **Power Query -kielellä** eli **M**-kielellä kirjoitetut kaavat. Voit tarkastella ja muokata kaavoja valitsemalla **Laajennettu editori** valintanauhan Aloitus-välilehden **Kysely**-ryhmästä. 

## <a name="import-the-transformed-queries"></a>Muunnettujen kyselyjen tuominen

Kun olet tyytyväinen muunnettuihin tietoihin, valitse **Sulje ja ota käyttöön** > **Sulje ja ota käyttöön** **Sulje**-ryhmässä valintanauhan **Aloitus**-välilehdeltä, jolloin tiedot tuodaan Power BI Desktopin raporttinäkymään. 

![Sulje ja ota käyttöön](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)

Kun tiedot on ladattu, kyselyt näkyvät Power BI Desktopin raporttinäkymän **Kentät**-luettelossa.

![Kyselyt Kentät-luettelossa](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="manage-the-relationship-between-the-datasets"></a>Tietojoukkojen välisen suhteen hallinta

Power BI Desktop ei vaadi kyselyiden yhdistämistä, jotta voit raportoida niistä. Voit kuitenkin käyttää tietojoukkojen välisiä suhteita niiden yhteisten kenttien perusteella raporttiesi laajentamiseksi ja täydentämiseksi. Power BI Desktop voi havaita suhteet automaattisesti tai voit luoda ne Power BI Desktopin **Suhteiden hallinta** -valintaikkunassa. Lisätietoja suhteista Power BI Desktopissa on artikkelissa [Suhteiden luominen ja hallinta](desktop-create-and-manage-relationships.md).

Tässä opetusohjelmassa tilausten ja tuotteiden tietojoukoilla on yhteinen *ProductID*-kenttä, joten niiden välillä on kyseiseen sarakkeeseen perustuva suhde. 

1. Valitse Power BI Desktopin raporttinäkymässä **Suhteiden hallinta** -vaihtoehto **Suhteet**-alueella **Aloitus**-välilehden valintanauhassa.
   
   ![Suhteiden hallinta -valintanauha](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
   
2. Huomaa **Suhteiden hallinta** -valintaikkunassa, että Power BI Desktop on jo havainnut ja listannut aktiiviset suhteet tuotteiden ja tilausten taulukoiden välillä. Jos haluat tarkastella suhdetta, valitse **Muokkaa**. 
   
   ![Suhteiden hallinta -valintaikkuna](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
   
   **Muokkaa suhdetta** -valintaikkuna avautuu ja näyttää kyseisen suhteen tiedot.  
   
   ![Muokkaa suhdetta -valintaikkuna](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
   
3. Power BI Desktop on havainnut suhteen oikein, joten voit valita **Peruuta** ja sitten **Sulje** poistuaksesi suhteen valintaikkunoista.

Voit myös tarkastella ja hallita suhteita kyselyiden välillä valitsemalla **Suhde**-näkymän Power BI Desktop -ikkunan vasemmassa reunassa. Kaksoisnapsauta nuolta rivillä, joka yhdistää kaksi kyselyä, niin **Muokkaa suhdetta** -valintaikkuna avautuu suhteen tarkastelua ja muokkausta varten. 

![Suhdenäkymä](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)

Voit palata raporttinäkymään Suhteet-näkymästä valitsemalla **Raporttinäkymä**-kuvakkeen. 

![Raporttinäkymäkuvake](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)

## <a name="create-visualizations-using-your-data"></a>Visualisointien luonti tietojen avulla

Power BI Desktopin raporttinäkymässä voit luoda useita erilaisia visualisointeja, joiden avulla voit analysoida tietojasi. Voit luoda raportteja, joissa on useita sivuja, joista jokainen voi sisältää useita visualisointeja. Visualisointien toimintojen avulla tietojasi voidaan analysoida ja tutkia. Lisätietoja raporttien tarkastelusta ja muokkauksesta Power BI -palvelussa (sivustosi) on kohdassa [Raportin muokkaaminen](service-interact-with-a-report-in-editing-view.md).

Voit käyttää kumpaakin tietojoukkoasi ja niiden välistä suhdetta myyntitietojesi visualisoinnin ja analysoinnin tukena. 

Luo ensin pinottu pylväskaavio, joka käyttää kummankin kyselyn kenttiä kunkin tilatun tuotteen määrän näyttämiseksi. 

1. Valitse **Quantity**-kenttä **Orders**-kohdasta oikealla olevassa **Fields**-ruudussa tai vedä se tyhjään tilaan pohjalla. Tämä luo pinotun pylväskaavion, joka näyttää kaikkien tilattujen tuotteiden kokonaismäärän. 
   
2. Valitse **ProductName**-kenttä **Products**-kohdasta **Fields**-ruudussa tai vedä se kaavioon kunkin tilatun tuotteen määrän näyttämiseksi. 
   
3. Lajittele tuotteet suurimmasta tilatusta määrästä pienimpään tilattuun määrään valitsemalla **Lisäasetukset** kolme pistettä ( **...** ) visualisoinnin oikeassa yläkulmassa ja valitsemalla sitten **Lajittele määrän mukaan**.
   
4. Käytä kaavion kulmissa olevia kahvoja kaavion suurentamiseksi, jotta enemmän tuotenimiä tulee näkyviin. 
   
   ![Määrän osoittava palkkikaavio ProductName-sarakkeen mukaan](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/19.png)

Luo seuraavaksi kaavio, joka näyttää tilauksen dollarisummat (**LineTotal**) ajanjaksolla (**OrderDate**). 

1. Kun mitään ei ole valittuna pohjalla, valitse **LineTotal** **Orders**-kohdasta **Fields**-ruudussa tai vedä se tyhjään kohtaan pohjalla. Pinottu pylväskaavio näyttää kaikkien tilausten dollarisumman. 
   
2. Kun kaavio on valittuna, valitse **OrderDate** kohteesta **Orders** tai vedä se kaavioon. Kaaviossa näkyvät nyt kunkin tilauspäivämäärän summat. 
   
3. Muuta visualisoinnin kokoa vetämällä sen kulmia, jotta näet enemmän tietoja. 
   
   ![Viivakaavio, joka näyttää LineTotals-arvot OrderDate-sarakkeen mukaan](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/20.png)
   
   >[!TIP]
   >Jos kaaviossa näkyy vain vuodet (vain kolme arvopistettä), paina nuolta kohdan **OrderDate** vieressä **Akseli**-kentässä **Visualisoinnit**-ruudussa ja valitse **OrderDate**-vaihtoehto **Date Hierarchyn** sijaan. 

Luo lopuksi kartta-visualisointi, joka näyttää kunkin maan tilausten summat. 

1. Kun mitään ei ole valittuna pohjalla, valitse **ShipCountry** **Orders**-kohdasta **Fields**-ruudussa tai vedä se tyhjään kohtaan pohjalla. Power BI Desktop havaitsee, että tiedot ovat maan nimiä, ja luo automaattisesti kartta-visualisoinnin, jossa on arvopiste kullekin maalle, jossa on tilauksia. 
   
2. Muuta arvopisteiden koot vastaamaan kunkin maan tilauksen summia vetämällä **LineTotal**-kenttä kartalle (tai vetämällä se **Vedä tietokentät tähän** -kohtaan **Koko**-ruudussa, **Visualisoinnit**-ruudun alaosassa). Kartalla olevien ympyröiden koot vastaavat nyt kunkin maan tilausten dollarisummia. 
   
   ![Kartta-visualisointi, joka näyttää LineTotals-arvot ShipCountry-sarakkeen mukaan](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/21.png)

## <a name="interact-with-your-report-visuals-to-analyze-further"></a>Analysoi tietoja tarkemmin raportin visualisointien avulla

Power BI Desktopissa voit tunnistaa trendejä käsittelemällä visualisointeja, jotka korostavat ja suodattavat toisiaan. Saat lisätietoja ohjeartikkelista [Suodattaminen ja korostaminen raporteissa](power-bi-reports-filters-and-highlighting.md). 

Kyselyjesi välisen suhteen vuoksi yhden visualisoinnin vuorovaikutukset vaikuttavat myös kaikkiin muihin sivulla oleviin visualisointeihin. 

Valitse kartta-visualisoinnissa ympyrä, joka on keskitetty **Kanadaan**. Huomaa, että kaksi muuta visualisointia suodattuvat korostamaan vain Kanadaan liittyvät rivisummat ja tilausmäärät.

![Kanadan suodatetut myyntitiedot](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/22.png)

Jos valitset jonkin tuotteen **Quantity by ProductName** -kaaviossa, kartta ja päivämääräkaavio suodattuvat kyseisen tuotteen mukaan, ja jos valitset jonkin päivämäärän **LineTotal by OrderDate** -kaaviossa, kartta ja tuotekaavio suodattuvat kyseisen päivämäärän mukaan. 
>[!TIP]
>Poista valinta valitsemalla se uudelleen tai valitse jokin muu visualisointi. 

## <a name="complete-the-sales-analysis-report"></a>Täydennä myyntianalyysiraportti

Valmis raportti yhdistää tiedot Excelin Products.xlsx-tiedostosta ja Northwind OData -syötteestä visualisointeihin, jotka auttavat analysoimaan eri maiden, aikavälien ja tuotteiden tilaustietoja. Kun raportti on valmis, voit [ladata sen Power BI -palveluun](desktop-upload-desktop-files.md) ja jakaa sen muiden Power BI -käyttäjien kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Lue muita Power BI Desktop -opetusohjelmia](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Katso Power BI Desktop -videoita](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Käy Power BI -keskustelupalstalla](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Lue Power BI -blogia](http://go.microsoft.com/fwlink/?LinkID=519327)