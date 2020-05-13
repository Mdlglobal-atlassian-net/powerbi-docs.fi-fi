---
title: 'Opetusohjelma: Omien mittarien luominen Power BI Desktopissa'
description: Power BI Desktopin mittarit auttavat suorittamalla tiedoillesi laskutoimituksia samalla, kun käsittelet raporttejasi.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 11/08/2019
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 91b0bba3b8e3fc221a05e6ccb2de1ec9b888d1ef
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83349306"
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>Opetusohjelma: Omien mittarien luominen Power BI Desktopissa
Mittareiden avulla voit luoda tehokkaimpiin kuuluvia tietojen analysointiratkaisuja Power BI Desktopissa. Mittarit auttavat suorittamalla tiedoillesi laskutoimituksia samalla, kun käsittelet raporttejasi. Tässä opetusohjelmassa kerrotaan Power BI Desktopin mittareista ja siitä, kuinka voit luoda omia perusmittareita.

## <a name="prerequisites"></a>Edellytykset

- Tämä opetusohjelma on tarkoitettu kehittyneempien mallien luomiseen Power BI -käyttäjille, joille Power BI Desktopin käyttö on jo tuttua. Edellytyksenä on, että osaat jo tuoda tietoja Nouda tiedot -toiminnon ja kyselyeditorin avulla, työskennellä useiden toisiinsa liitettyjen taulukoiden kanssa ja lisätä kenttiä raporttipohjaan. Jos olet vasta aloittamassa Power BI Desktopin käyttöä, muista tutustua [Power BI Desktopin käytön aloittaminen](../fundamentals/desktop-getting-started.md) -resurssiin.
  
- Tässä opetusohjelmassa käytetään [Contoso-myyntimalli Power BI Desktopille](https://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) -tiedostoa, joka sisältää fiktiivisen Contoso, Inc. -yrityksen verkkomyyntitietoja. Koska nämä tiedot on tuotu tietokannasta, et voi muodostaa yhteyttä tietolähteeseen tai tarkastella niitä kyselyeditorissa. Lataa tiedosto omaan tietokoneeseesi ja pura se.

## <a name="automatic-measures"></a>Automaattiset mittarit

Kun Power BI Desktop luo mittarin, usein se luodaan automaattisesti puolestasi. Jos haluat nähdä, miten Power BI Desktop luo mittarin, toimi seuraavasti:

1. Valitse Power BI Desktopissa **Tiedosto** > **Avaa**, etsi *Contoso-myyntimalli Power BI Desktopille.pbix* -tiedosto selaamalla ja valitse sitten **Avaa**.

2. Laajenna **Kentät**-ruudun **Myynti**-taulukko. Valitse sitten **SalesAmount**-kenttä tai vedä **SalesAmount** raporttipohjaan.

    Näyttöön tulee uusi pylväskaaviovisualisointi, joka näyttää **Sales**-taulukon **SalesAmount**-sarakkeen kaikkien arvojen kokonaissumman.

    ![SalesAmount-pylväskaavio](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

Mikä tahansa kenttä (sarake) **Kentät**-ruudussa, jossa on Sigma-kuvake ![Sigma-kuvake](media/desktop-tutorial-create-measures/meastut_sigma.png), on numeerinen. Näiden kenttien arvoja voi koostaa. Sen sijaan, että Power BI Desktop näyttäisi paljon arvoja (kaksi miljoonaa **SalesAmount**-riviä) sisältävän taulukon, se luo ja laskee automaattisesti mittarin tietojen koostamiseksi, jos se havaitsee numeerisen tietotyypin. Summa on numeerisen tietotyypin oletuskooste, mutta voit helposti käyttää eri koosteita, kuten keskiarvo tai määrä. Koosteiden ymmärtäminen on keskeistä mittarien ymmärtämiselle, koska jokainen mittari suorittaa jonkinlaisen koostamisen. 

Voit muuttaa kaavion koostamista seuraavasti:

1. Valitse **SalesAmount**-visualisointi raporttipohjassa.  

1. Valitse **Visualisoinnit**-ruudun **Arvo**-alueelta alaspäin osoittava nuoli **SalesAmount**-kohdan oikealta puolelta. 

1. Valitse näkyviin tulevasta valikosta **Keskiarvo**. 

    Visualisointi muuttuu kaikkien **SalesAmount**-kentän myyntiarvojen keskiarvoksi.

    ![SalesAmount-keskiarvokaavio](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

Voit muuttaa koostetyyppiä haluamasi tuloksen mukaan. Kaikki koostetyypit eivät kuitenkaan sovellu kaikille numeerisille tietotyypeille. **SalesAmount**-kentässä hyödyllisiä ovat esimerkiksi Summa ja Keskiarvo – ja myös Pienin arvo sekä Suurin arvo voivat olla hyödyllisiä. Määrä taas ei ole kovinkaan järkevä **SalesAmount**-kentässä, sillä vaikka sen arvot ovatkin numeerisia, ne ilmaisevat todellisuudessa valuuttaa.

Mittareista lasketut arvot muuttuvat vastauksena raportin kanssa tekemiesi toimien kanssa. Jos vedät esimerkiksi **RegionCountryName**-kentän **Geography**-taulukosta olemassa olevaan **SalesAmount**-kaavioon, se muuttuu näyttämään kunkin maan keskimääräiset myyntimäärät.

![Myyntimäärät maittain](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

Kun mittarin tulos muuttuu raportissa tekemiesi toimien vuoksi, toimesi ovat vaikuttaneet mittarin *kontekstiin*. Aina tehdessäsi toimia raportin visualisoinneille muutat kontekstia, jossa mittari laskee ja näyttää tuloksensa.

## <a name="create-and-use-your-own-measures"></a>Omien mittarien luonti ja käyttö

Useimmissa tapauksissa Power BI Desktop laskee ja palauttaa arvoja automaattisesti valitsemiesi kenttien ja koosteiden tyyppien mukaan. Joissakin tapauksissa haluat ehkä luoda omia mittareita, jotka suorittavat monimutkaisempia ja yksilöllisempiä laskutoimituksia. Power BI Desktopilla voit luoda omia mittareita Data Analysis Expressions (DAX) -kaavan kielellä. 

DAX-kaavat käyttävät monia samoja funktioita, operaattoreita ja syntakseja kuin Excel-kaavat. DAX-funktiot on kuitenkin suunniteltu toimimaan relaatiotietojen kanssa ja suorittamaan dynaamisempia laskutoimituksia, kun teet toimia raporteissasi. DAX-funktioita on yli 200, ja ne tekevät kaikkea yksinkertaisista koosteista, kuten summa ja keskiarvo, monimutkaisiin tilasto- ja suodatusfunktioihin. Saatavilla on useita resursseja, joista saat lisätietoja DAX-kaavasta. Kun olet suorittanut tämän opetusohjelman, muista tutustua [Power BI Desktopin DAX-perusteisiin](desktop-quickstart-learn-dax-basics.md).

Kun luot oman mittarin, sitä kutsutaan *mallimittariksi*. Se myös lisätään valitsemasi taulukon **Kentät**-luetteloon. Mallimittarien etuja ovat muun muassa se, että voit nimetä ne haluamallasi tavalla, jolloin ne ovat paremmin tunnistettavissa. Lisäksi voit käyttää niitä argumentteina muissa DAX-lausekkeissa ja laatia ne suorittamaan monimutkaisia laskutoimituksia nopeasti.

### <a name="quick-measures"></a>Pikamittarit

Power BI Desktopin helmikuun 2018 versiosta alkaen monet yleiset laskutoimitukset ovat saatavilla *pikamittareina*, jotka kirjoittavat DAX-kaavat puolestasi ikkunassa antamiesi tietojen perusteella. Nämä nopeat ja tehokkaat laskutoimitukset sopivat erinomaisesti myös DAX:n opetteluun tai omien mittariesi alkuarvojen sijoittamiseen. 

Voit luoda pikamittarin seuraavin tavoin: 
 - Napsauta **Kentät**-ruudun taulukossa hiiren kakkospainiketta tai valitse **Enemmän vaihtoehtoja** ( **...** ) ja valitse sitten luettelosta **Uusi pikamittari**.

 - Valitse Power BI Desktopin valintanauhan **Aloitus**-välilehden **Laskutoimitukset**-kohdasta **Uusi pikamittari**.

Lisätietoja pikamittareiden luonnista ja käytöstä saat artikkelista [Pikamittareiden käyttö](desktop-quick-measures.md).

### <a name="create-a-measure"></a>Mittarin luominen

Oletetaan, että haluat analysoida nettomyyntiäsi vähentämällä alennukset ja palautukset myynnin kokonaismääristä. Olipa visualisointisi konteksti mikä tahansa, tarvitset mittarin, joka vähentää DiscountAmount- ja ReturnAmount-arvojen summan SalesAmount-summasta. Nettomyynnille ei ole kenttää **Kentät**-luettelossa, mutta käytössäsi on elementtejä, joilla voit luoda oman mittarin nettomyynnin laskemista varten. 

Voit luoda mittarin seuraavasti:

1. Napsauta **Kentät**-ruudun **Sales**-taulukkoa hiiren kakkospainikkeella tai pidä hiiren osoitinta taulukon päällä ja valitse **Enemmän vaihtoehtoja** ( **...** ). 

1. Valitse näkyviin tulevasta valikosta **Uusi mittari**. 

    Tämä tallentaa uuden mittarin **Sales**-taulukkoon, josta se on helppo löytää.
    
    ![Uusi mittari luettelosta](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    Voit luoda uuden mittarin myös valitsemalla Power BI Desktopin valintanauhan **Aloitus**-välilehden **Laskutoimitukset**-ryhmästä **Uusi mittari**.
    
    ![Uusi mittari valintanauhasta](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    
    >[!TIP]
    >Kun luot mittarin valintanauhan kautta, sen voi luoda missä tahansa taulukossa, mutta se on helpompi löytää, jos luot sen paikkaan, jossa aiot käyttää sitä. Valitse tässä tapauksessa ensin **Sales**-taulukko, jotta se aktivoituu, ja valitse sitten **Uusi mittari**. 
    
    Raporttipohjan yläosaan tulee näkyviin kaavarivi, johon voit nimetä mittarin ja kirjoittaa DAX-kaavan.
    
    ![Kaavarivi](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
1. Uuden mittarin oletusnimeksi annetaan *Mittari*. Jos et nimeä sitä uudelleen, sitä seuraavat uudet mittarit saavat nimen *Mittari 2*, *Mittari 3* jne. Koska haluamme mittarien olevan paremmin tunnistettavissa, joten korosta kaavarivin *Mittari*-kohta ja kirjoita sitten nimeksi *Net Sales*.
    
1. Aloita nyt kaavan kirjoittaminen. Ala kirjoittamaan yhtäläisyysmerkin jälkeen sanaa *Sum*. Kirjoittaessasi näkyviin tulee ehdotusluettelo, jossa näkyvät kaikki DAX-funktiot, jotka alkavat kirjoittamillasi kirjaimilla. Vieritä tarvittaessa alaspäin, valitse luettelosta **SUM** ja paina lopuksi **Enter**-näppäintä.
    
    ![Valitse luettelosta SUM](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    Näkyviin tulee vasen sulkumerkki ja avautuva ehdotusluettelo kaikista saatavilla olevista sarakkeista, jotka voit välittää SUM-funktioon.
    
    ![Valitse sarake](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
1. Lausekkeet näkyvät aina vasemman ja oikean sulkumerkin välissä. Tässä esimerkissä lauseke sisältää yhden argumentin välitettäväksi SUM-funktioon: **SalesAmount**-sarakkeen. Ala kirjoittaa *SalesAmount*, kunnes luettelossa on jäljellä vain yksi arvo: **Sales(SalesAmount)** . 

    Taulukon nimen edessä olevaa sarakkeen nimeä kutsutaan sarakkeen täydelliseksi nimeksi. Sarakkeiden täydelliset nimet helpottavat kaavojen lukemista.
    
    ![Valitse SalesAmount](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
1. Valitse **Sales[SalesAmount]** luettelosta ja kirjoita loppusulje.
    
    > [!TIP]
    > Syntaksivirheiden syynä on useimmiten puuttuvat tai väärin sijoitetut loppusulkeet.
    
    
    
1. Vähennä kaksi muuta saraketta kaavasta:

    a. Kirjoita ensimmäisen lausekkeen loppusulkeen jälkeen välilyönti, miinusoperaattori (-) ja sitten toinen välilyönti. 

    b. Anna toinen SUM-funktio ja ala kirjoittaa *DiscountAmount*, kunnes voit valita **Sales[DiscountAmount]** -sarakkeen argumentiksi. Lisää loppusulje. 

    c. Kirjoita välilyönti, miinusoperaattori, välilyönti, toinen SUM-funktio, jonka argumenttina on **Sales[ReturnAmount]** ja sitten loppusulje.
    
    ![Valmis kaava](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
1. Vahvista valmis kaava painamalla **Enter**-näppäintä tai napsauttamalla kaavarivin **vahvistuskohtaa**  (valintamerkkikuvaketta). 

    Vahvistettu **Net Sales** -mittari on nyt valmis käytettäväksi **Sales**-taulukon **Kentät**-luettelossa.
    
    ![Net Sales -mittari Sales-taulukon kenttäluettelossa](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
1. Jos kaavan kirjoittamista varten tarkoitettu tila on loppumassa tai haluat kaavan erillisille riveille, valitse kaavarivin oikeassa sivussa näkyvä alaspäin osoittava nuoli, jolloin saat lisää tilaa. 

    Alaspäin osoittava nuoli muuttuu ylöspäin osoittavaksi nuoleksi ja näyttöön avautuu suuri ruutu.

    ![Kaavan ylänuoli](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)

1. Erota kaavan osat lisäämällä rivivaihto painamalla **Alt** + **Enter** tai lisäämällä sarkainväli painamalla **Sarkain**-näppäintä.

   ![Laajennettu kaava](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)

### <a name="use-your-measure-in-the-report"></a>Oman mittarin käyttö raportissa
Lisää uusi **Net Sales** -mittari raporttipohjaan ja laske nettomyynti mille tahansa muille kentille, jotka lisäät raporttiin. 

Voit tarkastella maakohtaista nettomyyntiä seuraavasti:

1. Valitse **Net Sales** -mittari **Sales**-taulukosta tai vedä se raporttipohjaan.
    
1. Valitse **Geography**-taulukosta **RegionCountryName**-kenttä tai vedä se **Net Sales** -kaavioon.
    
    ![Maakohtainen nettomyynti](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
1. Kun haluat nähdä maakohtaisen nettomyynnin ja kokonaismyynnin välisen eron, valitse **SalesAmount**-kenttä tai vedä se kaavioon. 

    ![Maakohtainen Sales Amount (Myynnin määrä) ja Net Sales (Nettomyynti)](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)

    Kaaviossa käytetään nyt kahta mittaria: **SalesAmount**-mittaria, joka laskettiin yhteen automaattisesti, ja manuaalisesti luomaasi **Net Sales** -mittaria. Kumpikin mittari laskettiin toisen kentän, **RegionCountryName**-kentän, kontekstissa.
    
### <a name="use-your-measure-with-a-slicer"></a>Mittarin käyttäminen osittajan kanssa

Lisää osittaja suodattaaksesi lisää kalenterivuosittaista nettomyyntiä ja myyntimäärää:
    
1. Valitse tyhjä kohta kaavion vierestä. Valitse **Visualisoinnit**-ruudusta **Taulukko**-visualisointityyppi. 

    Tämä luo tyhjän taulukkovisualisoinnin raporttipohjaan.
    
    ![Uusi tyhjä taulukkovisualisointi](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
1. Vedä **Calendar**-taulukon **Year**-kenttä uuteen tyhjään taulukkovisualisointiin. 
    
    Koska **Year**-kenttä on numeerinen, Power BI Desktop laskee sen arvot yhteen. Tämä ei kuitenkaan toimi hyvin koosteena. Käsittelemme tätä tarkemmin seuraavassa vaiheessa.

    ![Vuosikooste](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
3. Valitse **Visualisoinnit**-ruudun **Arvot**-ruudusta **Year**-kohdan vieressä näkyvä alaspäin osoittava nuoli ja valitse luettelosta **Älä tee yhteenvetoa**. Taulukko näyttää nyt vuodet erikseen lueteltuina.
    
    ![Valitse Älä tee yhteenvetoa](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
4.  Valitse **Visualisoinnit**-ruudun **Osittaja**-kuvake, jolloin taulukko muuttuu osittajaksi. Jos visualisointi näyttää liukusäätimen luettelon sijaan, valitse liukusäätimen alanuolesta **Luettelo**.

    ![Muunna taulukko osittajaksi](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
5.  Valitse mikä tahansa arvo **Year**-osittajasta, jolloin **Net Sales and Sales Amount by RegionCountryName** -kaavio suodattuu sen mukaisesti. **Net Sales**- ja **SalesAmount**-mittarit laskevat tulokset uudestaan ja näyttävät ne valitun **Year**-kentän kontekstissa. 
    
    ![Kaavio ositettuna vuoden mukaan](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

### <a name="use-your-measure-in-another-measure"></a>Oman mittarin käyttö toisessa mittarissa

Oletetaan, että haluat selvittää, minkä tuotteiden nettomyyntimäärä myytyä yksikköä kohti on korkein. Tarvitset tähän mittarin, joka jakaa nettomyynnin myytyjen yksiköiden määrällä. Luo uusi mittari, joka jakaa **Net Sales**-mittarin **Sales[SalesQuantity]** -mittarin summalla.

1.  Luo **Kentät**-ruudussa **Sales**-taulukkoon uusi mittari nimeltä **Net Sales per Unit**.
    
1. Ala kirjoittaa kaavariville *Net Sales* -sanaa. Ehdotusluettelo näyttää, mitä voit lisätä. Valitse **[Net Sales]** .
    
    ![Kaava, jossa käytetään Net Sales -mittayksikköä](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
1. Voit viitata mittareihin myös vain kirjoittamalla avaavan hakasulkeen ( **[** ). Ehdotusluettelossa näkyvät vain kaavaan lisättävät mittarit.
    
    ![Hakasulje näyttää vain mittarit](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
1. Lisää välilyönti, jako-operaattori (/), toinen välilyönti, SUM-funktio ja kirjoita sitten *Quantity*. Ehdotusluettelo näyttää kaikki sarakkeet, joiden nimessä on sana *Quantity*. Valitse **Sales[SalesQuantity]** , kirjoita loppusulje ja vahvista kaava painamalla **ENTER**-näppäintä napsauttamalla kaavarivin **vahvistuskohtaa** (valintamerkkikuvaketta). 

    Kaavan pitäisi näkyvä seuraavasti:
    
    `Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])`
    
1. Valitse **Net Sales per Unit** -mittari **Sales**-taulukosta tai vedä se raporttipohjan tyhjään alueeseen. 

    Kaavio näyttää nettomyyntimäärän yksikköä kohti kaikkien myytyjen tuotteiden osalta. Tämä ei ole kovin informatiivista, mutta käsittelemme tätä tarkemmin seuraavassa vaiheessa.
    
    ![Kokonaisnettomyynti yksikköä kohti](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
1. Voit muuttaa kaavion ulkoasua muuttamalla visualisointityypiksi **puukartan**.
    
    ![Muuttaminen puukartaksi](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
1. Valitse **Product Category**-kenttä tai vedä se puukarttaan tai **Visualisoinnit**-ruudun **Ryhmä**-kenttään. Nyt käytössäsi on hyödyllisiä tietoja!
    
    ![Tuoteluokan mukainen puukartta](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
7. Yritä poistaa **ProductCategory**-kenttä ja vetää **ProductName**-kenttä kaavioon sen tilalle. 
    
    ![Tuotenimen mukainen puukartta](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
   Ok, nyt vain leikimme, mutta lienet samaa mieltä, että tämä on hauskaa! Kokeile myös muita tapoja suodattaa ja muotoilla visualisointia.

## <a name="what-youve-learned"></a>Opitut asiat
Mittarien avulla saat paljon merkityksellisiä tietoja omista tiedoistasi. Olet oppinut, kuinka voit luoda mittareita käyttämällä kaavariviä, miten voit nimetä ne järkevimmäksi havaitsemallasi tavalla ja kuinka voit hakea ja valita oikeat kaavan osat käyttämällä DAX-ehdotusluetteloita. Lisäksi olet tutustunut kontekstiin, jossa laskutoimitusten tulokset mittareissa muuttuvat muiden kenttien tai kaavan muiden lausekkeiden mukaan.

## <a name="next-steps"></a>Seuraavat vaiheet
- Lisätietoja Power BI Desktopin pikamittareista, jotka tekevät puolestasi monia yleisiä mittarilaskutoimituksia, saat artikkelista [Pikamittareiden avulla voit suorittaa helposti yleisiä ja tehokkaita laskutoimituksia](desktop-quick-measures.md).
  
- Jos haluat tutustua tarkemmin DAX-kaavoihin ja siihen, miten voit luoda edistyneempiä mittareita, lue [DAX-perusteet Power BI Desktopissa](desktop-quickstart-learn-dax-basics.md). Tässä artikkelissa keskitytään DAX-peruskäsitteisiin, kuten syntaksiin ja funktioihin, ja annetaan tarkempaa tietoa kontekstista.
  
- Muista lisätä [Data Analysis Expressions (DAX) -viite](https://docs.microsoft.com/dax/index) suosikkeihin. Sieltä saat tarkempia tietoja DAX-syntaksista ja -operaattoreista sekä yli 200 DAX-funktiosta.
