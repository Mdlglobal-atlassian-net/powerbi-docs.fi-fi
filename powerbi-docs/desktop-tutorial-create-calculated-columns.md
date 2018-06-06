---
title: 'Opetusohjelma: laskettujen sarakkeiden luominen Power BI Desktopissa'
description: 'Opetusohjelma: laskettujen sarakkeiden luominen Power BI Desktopissa'
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
LocalizationGroup: Learn more
ms.openlocfilehash: acdaa95908cd03006170eb06ddfc780c836c64ac
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973972"
---
# <a name="tutorial-create-calculated-columns-in-power-bi-desktop"></a>Opetusohjelma: laskettujen sarakkeiden luominen Power BI Desktopissa
Joskus analysointisi kohteena olevat tiedot eivät vain sisällä tiettyä kenttää, jota tarvitsisit saadaksesi haluamiasi tuloksia. Tässä vaiheessa mukaan kuvaan tulevat lasketut sarakkeet. Laskettujen sarakkeiden arvojen laskemiseen käytetään Data Analysis Expressions (DAX) -kaavoja. Nämä arvot voivat olla lähes mitä vain, olipa kyseessä mallin eri sarakkeiden tekstiarvojen yhdistäminen tai numeerisen arvon laskeminen muista arvoista. Tiedoissasi voi olla esimerkiksi Kaupunki- ja Osavaltio-sarakkeet (kenttinä Kentät-luettelossa), mutta haluat yhden Sijainti-kentän, jossa nämä kumpikin ilmoitetaan yhtenä arvona, kuten Miami, FL. Lasketut sarakkeet on tarkoitettu juuri tähän tarkoitukseen.

Lasketut sarakkeet muistuttavat mittayksiköitä siinä, että molemmat perustuvat DAX-kaavaan, mutta niiden käyttötavat ovat erilaiset. Mittayksiköitä käytetään useimmiten visualisoinnin Arvot-alueella, kun halutaan laskea tuloksia taulukon rivillä olevien muiden kenttien perusteella, tai visualisoinnin Akseli-, Selite- tai Ryhmä-alueilla. Laskettuja sarakkeita puolestaan käytetään, kun sarakkeen tulokset halutaan sijoittaa taulukon kyseiselle riville, tai Akseli-, Selite- tai Ryhmä-alueella.

Tässä opetusohjelmassa kerrotaan Power BI Desktopin lasketuista sarakkeista ja siitä, kuinka voit luoda omia laskettuja sarakkeita. Se on tarkoitettu kehittyneempien mallien luomiseen Power BI -käyttäjille, joille Power BI Desktopin käyttö on jo tuttua. Edellytyksenä on, että osaat jo tuoda tietoja kyselyn avulla, työskennellä useiden toisiinsa liitettyjen taulukoiden kanssa ja lisätä kenttiä raporttipohjaan. Jos olet vasta aloittamassa Power BI Desktopin käyttöä, muista tutustua [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md) -resurssiin.

Jotta voit suorittaa tämän opetusohjelman vaiheet, sinun on ladattava [Contoso Sales Sample for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) -tiedosto. Tämä on sama mallitiedosto kuin se, jota käytetään [Omien mittayksiköiden luominen Power BI Desktopissa](desktop-tutorial-create-measures.md) -opetusohjelmassa. Se sisältää kuvitteellisen yrityksen, Contoso, Inc:n, myyntitietoja. Koska tiedoston tiedot on tuotu tietokannasta, et voi muodostaa yhteyttä tietolähteeseen tai tarkastella niitä kyselyeditorissa. Kun tiedosto on tallennettu omalle tietokoneellesi, voit avata sen Power BI Desktopissa.

## <a name="lets-create-a-calculated-column"></a>Lasketun sarakkeen luominen
Otetaan esimerkiksi tilanne, jossa haluamme tuoteluokat näkyviin yhdessä tuotealiluokkien kanssa yhtenä arvona riveillä, kuten Matkapuhelimet – Lisävarusteet, Matkapuhelimet – Älypuhelimet ja PDA-laitteet, ja niin edelleen. Jos tarkastelemme raportti- tai tietonäkymässä (käytämme tässä raporttinäkymää) Kentät-luettelon tuotetaulukoita, huomaamme, että mikään kenttä ei tarjoa haluamaamme. Saatavilla on kuitenkin ProductCategory- ja ProductSubcategory-kentät, kumpikin omassa taulukossaan.

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_nonewcol.png)

Luomme uuden lasketun sarakkeen, jossa yhdistämme näiden kahden sarakkeen arvot uusiksi arvoiksi. Mielenkiintoiseksi tämän tekee se, että meidän on yhdistettävä tietoja kahdesta eri taulukosta yhteen sarakkeeseen. Koska aiomme käyttää uuden sarakkeen luomiseen DAX-kaavaa, voimme hyödyntää täydellisesti meillä jo ennestään olevan mallia, mukaan lukien jo olemassa olevien taulukoiden väliset suhteet.

### <a name="to-create-a-productfullcategory-column"></a>ProductFullCategory-sarakkeen luominen
1.  Napsauta hiiren kakkospainikkeella Kentät-luettelon **ProductSubcategory**-taulukkoa tai napsauta alaspäin osoittavaa nuolta ja valitse **Uusi sarake**. Tällä varmistetaan, että uusi sarake lisätään ProductSubcategory-taulukkoon.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumn.png)
    
    Kaavarivi näkyy raporttipohjan tai tietoruudukon yläosassa. Tällä rivillä voimme nimetä sarakkeen uudelleen ja antaa DAX-kaavan.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumnformula.png)
    
    Uuden sarakkeen nimi on oletusarvoisesti vain Sarake. Jos saraketta ei nimetä uudelleen ja luomme uusia sarakkeita, niiden nimeksi annetaan Sarake 2, Sarake 3 ja niin edelleen. Haluamme sarakkeiden olevan paremmin tunnistettavissa, joten annamme uudelle sarakkeelle uuden nimen.
    
2.  Koska **sarakkeen** nimi näkyy jo korostettuna kaavarivillä, sinun tarvitsee kirjoittaa siihen vain **ProductFullCategory**.
    
    Nyt voimme aloittaa kaavan kirjoittamisen. Haluamme uudessa sarakkeessa olevien arvojen alkavan ProductCategory-nimellä, joka on saatu ProductCategory-taulukosta. Koska tämä sarake on erilaisessa, mutta liittyvässä taulukossa, käytämme apuna sen hakemisessa [RELATED](https://msdn.microsoft.com/library/ee634202.aspx) (SUHTEET) -funktiota.
    
3.  Kirjoita yhtäläisyysmerkkien jälkeen kirjain **R**. Näkyviin tulee ehdotettujen kohteiden pudotusluettelo, joka sisältää kaikki R-kirjaimella alkavat DAX-funktiot. Mitä enemmän kirjoitamme, sitä lähemmäs etsimäämme funktiota ehdotusluettelo siirtyy. Funktion vieressä näkyy funktion kuvaus. Valitse **RELATED** (SUHTEET) selaamalla alaspäin ja painamalla Enter-näppäintä.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_1.png)
    
    Näkyviin tulee vasen sulkumerkki ja toinen ehdotusluettelo kaikista saatavilla olevista sarakkeista, jotka voimme välittää RELATED (SUHTEET) -funktioon. Lisäksi näkyvissä on kuvaus ja tietoja odotetuista parametreista.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_2.png)
    
    Lauseke näkyy aina vasemman ja oikean sulkumerkin välissä. Tässä tapauksessa lauseke tulee sisältämään yhden RELATED (SUHTEET) -funktioon välitetyn argumentin; liittyvä sarake, josta arvot palautetaan. Sarakeluettelo pienenee automaattisesti ja näyttää vain liittyvät sarakkeet. Tässä tapauksessa haluamme ProductCategory-taulukon ProductCategory-sarakkeen.
    
    Valitse **ProductCategory [ProductCategory]** ja kirjoita oikea sulkumerkki.
    
    > [!TIP]
    > Syntaksivirheiden syynä on useimmiten puuttuvat tai väärin sijoitetut loppusulkeet. Power BI Desktop lisää sen kuitenkin usein, jos itse unohdat.
    > 
    > 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_3.png)
    
4. Haluamme lisätä yhdysviivan erottaaksemme jokaisen arvon, joten kirjoita ensimmäisen lausekkeen loppusulkeen jälkeen välilyönti, et-merkki (&), lainausmerkki, välilyönti, yhdysviiva (-), toinen välilyönti, sulkeva lainausmerkki ja lopuksi toinen et-merkki. Kaavan pitäisi nyt näyttää tältä:
    
    **ProductFullCategory = RELATED(ProductCategory[ProductCategory]) & ”-” &**
    
    > [!TIP]
    > Laajenna kaavaeditoria napsauttamalla kaavarivin oikealla puolella olevaa alaspäin osoittavaa nuolta. Siirry seuraavalle riville napsauttamalla Alt- ja Enter-näppäimiä ja siirry kohteesta toiseen käyttämällä Tab-näppäintä.
    > 
    > 
    
5.  Tee kaava valmiiksi kirjoittamalla lopuksi toinen loppuhakasulje ja valitsemalla **[ProductSubcategory]**-sarake. Kaavan pitäisi näyttää tältä:
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_5.png)
    
    Huomaat, että emme käyttäneet toista RELATED (SUHDE) -funktiota toisessa lausekkeessa ProductSubcategory-saraketta kutsuttaessa. Tämä johtuu siitä, että tämä sarake on jo samassa taulukossa, johon olemme luomassa uutta saraketta. Voimme syöttää [ProductCategory]-sarakkeeseen taulukon nimen (täydellinen) tai jättää sen ilman (ei täydellinen).
    
6.  Tee kaava valmiiksi painamalla Enter-näppäintä tai napsauttamalla kaavarivin valintamerkkiä. Kaava on nyt vahvistettu ja lisätty **ProductSubcategory**-taulukon kenttäluetteloon.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_6.png)
    
    Huomaat, että kenttäluettelossa laskettujen sarakkeiden yhteydessä näkyy erityiskuvake. Se kertoo, että ne sisältävät kaavan. Ne näkyvät näin vain Power BI Desktopissa. Power BI-palvelussa (Power BI -sivusto) kaavaa ei voi muuttaa, joten lasketun sarakkeen kentässä ei ole kuvaketta.
    
## <a name="lets-add-our-new-column-to-a-report"></a>Uuden sarakkeen lisääminen raporttiin
Nyt voimme lisätä uuden ProductFullCategory-sarakkeen raporttipohjaan. Tarkastellaan seuraavaksi SalesAmount-arvoa ProductFullCategory-luokan mukaan.

Vedä **ProductFullCategory**-sarake **ProductSubcategory**-taulukosta raporttipohjaan ja sen jälkeen **SalesAmount**-kenttä **Sales**-taulukosta kaavioon.

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_report_1.png)

## <a name="lets-create-another"></a>Toisen sarakkeen luominen
Nyt kun tiedät, miten laskettu sarake luodaan, voimme luoda toisen.

Contoso Sales Sample for Power BI Desktop -malli sisältää sekä aktiivisten että passiivisten myymälöiden myyntitietoja. Haluamme, että passiivisten myymälöiden yhteydessä näkyvät tiedot ovat selkeästi tunnistettavissa. Itse asiassa haluamme Active StoreName -nimisen kentän. Tätä varten luomme toisen sarakkeen. Tässä tapauksessa, kun myymälä on passiivinen, haluamme uuden Active StoreName -sarakkeen (kenttänä) näyttävän myymälän nimellä ”Inactive” (Passiivinen). Kun taas myymälä on aktiivinen, haluamme, että sarakkeessa näkyy sen todellinen nimi.

Myymälät-taulukossa on onneksi sarake nimeltä Tila, jossa aktiivisten myymälöiden arvona on Käytössä ja passiivisten myymälöiden arvona Ei käytössä. Voimme testata Tila-sarakkeessa olevien rivien arvot ja luoda uusia arvoja luomaamme uuteen sarakkeeseen.

### <a name="to-create-an-active-storename-column"></a>Active StoreName -sarakkeen luominen
1.  Luo **Myymälät**-taulukkoon uusi laskettu sarake nimellä **Active StoreName**.
    
    Tässä sarakkeessa jokaisen myymälän tila tullaan tarkistamaan DAX-kaavalla. Jos myymälän tila on On (Käytössä), kaava palauttaa myymälän nimen. Jos tila on Off (Ei käytössä), sen nimi on ”Inactive” (Passiivinen). Jotta voimme tehdä tämän, käytämme loogista [IF](https://msdn.microsoft.com/library/ee634824.aspx) (JOS) -funktiota testataksemme myymälän tilan ja palauttaaksemme tietyn arvon, jos tulos on tosi tai epätosi.
    
2.  Aloita kirjoittamaan **IF**-sanaa. Ehdotusluettelo näyttää, mitä voimme lisätä. Valitse **IF**.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_1.png)
    
    IF-funktion ensimmäinen argumentti on looginen testi. Haluamme testata, onko myymälän tila On (Käytössä) vai ei.
    
3.  Kirjoita avaava hakasulje **[**, jolloin voimme valita sarakkeita Myymälät-taulukosta. Valitse **[Status]** (Tila).
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_2.png)
    
4.  Kirjoita heti **[Status]**-kohdan perään **="On"**,  ja lisää sen jälkeen pilkku (**,**), jotta voit syöttää toisen argumentin. Työkaluvihje ehdottaa, että meidän on lisättävä arvo, kun tulos on tosi.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_3.png)
    
5.  Jos myymälän tila on On (Käytössä), haluamme näkyviin myymälän nimen. Kirjoita avaava hakasulje **[** ja valitse **[StoreName]**-sarake. Lisää sen jälkeen toinen pilkku, jotta voimme lisätä kolmannen argumentin.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step5.png)
    
6.  Meidän on lisättävä arvo, kun tulos on epätosi, tässä tapauksessa haluamme arvon olevan **”Inactive”** (Passiivinen).
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step6.png)
    
7.  Tee kaava valmiiksi painamalla Enter-näppäintä tai napsauttamalla kaavarivin valintamerkkiä. Kaava on nyt vahvistettu ja lisätty Myymälät-taulukon kenttäluetteloon.
    
    Kuten muitakin kenttiä, voimme visualisoinneissa käyttää myös uutta Active StoreName -saraketta. Tässä kaaviossa On (Käytössä) -tilassa olevat myymälät näkyvät eritellysti omalla nimellään, mutta Off (Ei käytössä) -tilassa olevat myymälät näkyvät ryhmiteltyinä yhteen nimellä Inactive (Passiivinen). 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_viz.png)
    
## <a name="what-weve-learned"></a>Mitä olemme oppineet
Laskettujen sarakkeiden avulla voimme rikastaa tietojamme ja saada helpommin merkityksellisiä tietoja. Olemme oppineet, kuinka laskettuja sarakkeita luodaan käyttämällä kaavariviä, kuinka ehdotusluetteloa käytetään ja kuinka uudet sarakkeet kannattaa nimetä.

## <a name="next-steps"></a>Seuraavat vaiheet
Jos haluat tutustua tarkemmin DAX-kaavoihin ja siihen, miten laskettuja sarakkeita voi luoda edistyneemmillä DAX-kaavoilla, lue [DAX-perusteet Power BI Desktopissa](desktop-quickstart-learn-dax-basics.md). Tässä artikkelissa keskitytään DAX-peruskäsitteisiin, kuten syntaksiin ja funktioihin, ja annetaan tarkempaa tietoa kontekstista.

Muista lisätä [Data Analysis Expressions (DAX) -viite](https://msdn.microsoft.com/library/gg413422.aspx) suosikkeihin. Sieltä saat tarkempia tietoja DAX-syntaksista ja -operaattoreista sekä yli 200 DAX-funktiosta.

