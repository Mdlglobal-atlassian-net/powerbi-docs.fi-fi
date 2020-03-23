---
title: 'Opetusohjelma: Tietojen muotoilu ja yhdistäminen Power BI Desktopissa'
description: Tässä opetusohjelmassa opit tietojen muotoilun ja yhdistämisen Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 10/18/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: d6a36f8ef3ef5d668fe8d6021758b651cdbf7fd5
ms.sourcegitcommit: 7e845812874b3347bcf87ca642c66bed298b244a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/13/2020
ms.locfileid: "79206765"
---
# <a name="tutorial-shape-and-combine-data-in-power-bi-desktop"></a>Opetusohjelma: Tietojen muotoilu ja yhdistäminen Power BI Desktopissa

Power BI Desktopilla voit muodostaa yhteyksiä moniin erilaisiin tietolähteisiin ja muotoilla sitten tietoja tarpeidesi mukaisesti. Näin voit luoda visuaalisia raportteja, joita voit jakaa muille. Tietojen *muotoileminen* tarkoittaa tietojen muuntamista: sarakkeiden tai taulukoiden nimeämistä uudelleen, tekstin muuntamista luvuiksi, rivien poistamista, ensimmäisen rivin määrittämistä otsikoiksi ja niin edelleen. Tietojen *yhdistäminen* tarkoittaa kahden tai useamman tietolähteen yhdistämistä, tietojen muotoilua tarvittaessa ja sitten tietojen yhdistämistä hyödylliseksi kyselyksi.

Tässä opetusohjelmassa opit:

* muotoilemaan tietoja käyttämällä kyselyeditoria
* yhdistämään eri tietolähteisiin
* yhdistämään kyseiset tietolähteet ja luomaan tietomallin raportissasi käytettäviksi.

Tässä opetusohjelmassa näytetään, miten voit muotoilla kyselyä Power BI Desktopilla, sekä tuodaan esiin yleisimpiä tehtäviä. Tässä käytetty kysely kuvataan tarkemmin ohjeartikkelissa [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md), josta saat myös ohjeet kyselyn luomiseen kokonaan itse.

Power BI Desktopin kyselyeditorissa käytetään runsaasti hiiren kakkospainikkeella avattavien valikoiden toimintoja sekä **Muunna**-valintanauhan toimintoja. Useimmat toiminnot, jotka ovat valittavissa valintanauhassa, ovat käytettävissä myös napsauttamalla kohdetta, esimerkiksi saraketta, hiiren kakkospainikkeella ja valitsemalla sitten toiminto näyttöön avautuvasta valikosta.

## <a name="shape-data"></a>Tietojen muotoileminen
Kun muotoilet tietoja kyselyeditorissa, annat kyselyeditorille tietojen muokkaamiseksi vaiheittaiset ohjeet, jotka se toteuttaa puolestasi tietojen lataamiseksi ja näyttämiseksi. Tämä ei vaikuta alkuperäiseen tietolähteeseen, sillä vain tätä tietonäkymää muokataan eli *muotoillaan*.

Kyselyeditori kirjaa määrittämäsi vaiheet (esimerkiksi taulukon nimeäminen uudelleen, tietotyypin muuntaminen tai sarakkeen poistaminen). Aina, kun tämä kysely muodostaa yhteyden tietolähteeseen, kyselyeditori suorittaa nämä vaiheet, niin että tiedot muotoillaan aina määrittämälläsi tavalla. Tämä prosessi suoritetaan aina, kun käytät kyselyeditoria ja kun joku käyttää jaettua kyselyäsi esimerkiksi Power BI -palvelussa. Vaiheet kirjataan järjestyksessä **Kyselyasetukset**-ruudun **Käytössä olevat vaiheet** -kohtaan. Käymme läpi jokaisen näistä vaiheista seuraavissa kappaleissa.

![Käytössä olevat vaiheet kyselyasetuksissa](media/desktop-shape-and-combine-data/shapecombine_querysettingsfinished2.png)

Käytämme tässä esimerkissä [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md) -artikkelista tuttuja eläköitymistietoja, jotka löysimme muodostamalla yhteyden verkkotietolähteeseen. Muotoilemme tässä esimerkissä näitä tietoja omiin tarpeisiimme. Lisäämme mukautetun sarakkeen, jolla lasketaan sijoitus sillä perusteella, että kaikki tiedot ovat yhtä tärkeitä, ja verrataan tätä saraketta olemassa olevaan **Rank**-sarakkeeseen.  

1. Valitse **Lisää sarake**-valintanauhasta **Mukautettu sarake**, jonka avulla voit lisätä mukautetun sarakkeen.

    ![Valitse mukautettu sarake](media/desktop-shape-and-combine-data/shapecombine_customcolumn.png)

1. Kirjoita **Mukautettu sarake** -ikkunan **Uuden sarakkeen nimi** -kohtaan _New Rank_. Lisää **Mukautettu sarakekaava** -kohtaan seuraavat tiedot:

    ```
    ([Cost of living] + [Weather] + [Health care quality] + [Crime] + [Tax] + [Culture] + [Senior] + [#"Well-being"]) / 8
    ```
 
1. Varmista, että tilailmoitus on *Syntaksivirheitä ei ole havaittu*, ja valitse **OK**.

    ![Mukautettu sarake -sivu, jossa ei ole syntaksivirheitä](media/desktop-shape-and-combine-data/shapecombine_customcolumndialog.png)

1. Jotta sarakkeiden tiedot pysyvät johdonmukaisena, muunna uudet sarakearvot kokonaisluvuiksi. Voit vaihtaa arvot napsauttamalla sarakeotsikkoa hiiren kakkospainikkeella ja valitsemalla sitten **Muuta tyyppi \> Kokonaisluku**. 

    Jos haluat valita useita sarakkeita, valitse sarake, paina **VAIHTO**-näppäin pohjaan, valitse vierekkäisiä sarakkeita ja napsauta sitten sarakeotsikkoa hiiren kakkospainikkeella. Painamalla **CTRL**-näppäintä valitessasi voit valita kerralla useita sarakkeita, jotka eivät ole vierekkäin.

    ![Valitse Kokonaisluku-sarakkeen tiedot](media/desktop-shape-and-combine-data/shapecombine_changetype2.png)

1. Jos haluat *muuntaa* sarakkeen tietotyyppejä, eli muuntaa nykyisen tietotyypin toiseksi, valitse **Tietotyyppi teksti** **Muunna**-valintanauhasta. 

   ![Valitse Tietotyyppi teksti](media/desktop-shape-and-combine-data/queryoverview_transformribbonarrow.png)

1. Kaikki tietojen muotoiluvaiheet kirjataan **Kyselyasetukset**-ruudun **Käytössä olevat vaiheet** -luetteloon. Jos haluat poistaa vaiheen muotoiluprosessista, valitse haluamasi vaiheen vasemmalta puolelta **X**. 

    Seuraavassa kuvassa **Käytössä olevat vaiheet**-luettelo kuvastaa tähän mennessä lisättyjä vaiheita: 
     - **Lähde**: Yhdistetään verkkosivustoon.
     - **Siirtyminen**: Valitaan taulukkoa. 
     - **Muutettu tyyppi**: Tekstipohjaisten lukusarakkeiden muuttaminen *tekstistä* *kokonaisluvuksi*. 
     - **Lisätty mukautettu**: Mukautetun sarakkeen lisääminen.
     - **Muutettu tyyppi1**: Viimeisin käyttöön otettu vaihe.

       ![Luettelo käytössä olevista vaiheista](media/desktop-shape-and-combine-data/shapecombine_appliedstepsearly2.png)

## <a name="adjust-data"></a>Säädä tietoja

Ennen kuin voimme käyttää tätä kyselyä, meidän täytyy säätää sen tietoja tekemällä muutama muutos:

   - Säädä sijoituksia poistamalla sarake.

       Olemme päättäneet, sarake **Cost of living** ei vaikuta tuloksiimme. Kun tämä sarake on poistettu, tiedot pysyvät muuttumattomina. 

   - Korjaa muutama virhe.

       Koska poistimme sarakkeen, meidän täytyy muokata **New Rank** -sarakkeen laskelmia ja muuttaa kaavaa.

   - Lajittele tiedot.

       Tiedot lajitellaan **New Rank**- ja **Rank**-sarakkeiden perusteella.
 
   - Korvaa tiedot.

       Näytämme, miten voit korvata tietyn arvon ja miksi **käytössä oleva vaihe** täytyy lisätä.

   - Muuta taulukon nimi. 

       Koska **Table 0** ei kuvaa taulukkoa hyödyllisellä tavalla, muutamme sen nimen.

1. Jos haluat poistaa **Cost of living** -sarakkeen, valitse sarake, valitse valintanauhan **Aloitus**-välilehti ja valitse sitten **Poista sarakkeet**.

    ![Valitse Poista sarakkeet](media/desktop-shape-and-combine-data/shapecombine_removecolumnscostofliving.png)

   Huomaat, että **New Rank** -arvot eivät ole muuttuneet. Tämä johtuu vaiheiden järjestyksestä. Koska kyselyeditori kirjaa vaiheet järjestyksessä ja silti toisistaan riippumatta, voit siirtää kutakin **käytössä olevaa vaihetta** järjestyksessä aiemmaksi tai myöhemmäksi. 

1. Napsauta vaihetta hiiren kakkospainikkeella. Kyselyeditori näyttää valikon, jossa voit tehdä seuraavat tehtävät: 
   - **Nimeä uudelleen**; nimeä vaihe uudelleen.
   - **Poista**: Poista vaihe.
   - **Poista** **loppuun saakka**: Poista nykyinen vaihe sekä kaikki seuraavat vaiheet.
   - **Siirrä ylös**: Siirrä vaihetta ylöspäin luettelossa.
   - **Siirrä alas**: Siirrä vaihetta alaspäin luettelossa.

1. Siirrä viimeinen vaihe eli **Removed Columns** **Added Custom** -vaiheen yläpuolelle.

   ![Siirrä vaihetta ylöspäin käytössä olevissa vaiheissa](media/desktop-shape-and-combine-data/shapecombine_movestep.png)

1. Valitse **Added Custom** -vaihe. 

   Huomaat, että tiedoissa näkyy nyt _virhe_, joka meidän täytyy korjata.

   ![Virhetulos saraketiedoissa](media/desktop-shape-and-combine-data/shapecombine_error2.png)

   Voit hankkia lisätietoa eri virheistä muutamin tavoin. Jos valitset solun napsauttamatta *Virhe*-sanaa, kyselyeditori näyttää virhetiedot ikkunan alareunassa.

   ![Virhetiedot kyselyeditorissa](media/desktop-shape-and-combine-data/shapecombine_errorinfo2.png)

   Jos valitset *Virhe*-sanan suoraan, kyselyeditori luo **käytössä olevan vaiheen** **kyselyasetusten** ruutuun ja näyttää tiedot virheestä. 

1. Koska meidän ei tarvitse näyttää tietoja virheistä, valitse **Peruuta**.

1. Jos haluat korjata virheet, valitse **New Rank** -sarake ja näytä sarakkeen tiedot valitsemalla **Kaavarivi**-valintaruutu **Näytä**-valintanauhasta. 

   ![Valitse Kaavarivi](media/desktop-shape-and-combine-data/shapecombine_formulabar.png)

1. Poista _Cost of living_ -parametri ja pienennä jakaja muuttamalla kaava seuraavaan muotoon: 
   ```
    Table.AddColumn(#"Removed Columns", "New Rank", each ([Weather] + [Health care quality] + [Crime] + [Tax] + [Culture] + [Senior] + [#"Well-being"]) / 7)
   ```

1. Valitse kaavaruudun vasemmalla puolella oleva vihreä valintamerkki tai valitse **Enter**.

  Kyselyeditori korvaa tiedot tarkistetuilla arvoilla, ja **Lisätty mukautettu** -vaihe valmistuu ilman virheitä.

   > [!NOTE]
   > Voit myös valita **Poistaa virheet** käyttämällä valintanauhaa tai hiiren kakkospainiketta. Tämä poistaa kaikki rivit, joilla on virheitä. Emme kuitenkaan halunneet tehdä näin tässä opetusohjelmassa, koska halusimme säilyttää taulukon tiedot.

1. Lajittele tiedot **New Rank** -sarakkeen perusteella. Valitse ensin viimeisin käytetty vaihe eli **Changed Type1** näyttääksesi uusimmat tiedot. Valitse sitten avattava valikko **New Rank** -sarakeotsikon vierestä ja valitse **Lajittele nousevaan järjestykseen**.

   ![Lajittele New Rank -sarakkeen tiedot](media/desktop-shape-and-combine-data/shapecombine_sort.png)

   Tiedot lajitellaan nyt **New Rank** -sarakkeen perusteella. Jos taas katsot **Rank**-saraketta, näet, että tietoja ei lajitella oikein kohdissa, joissa **New Rank** -arvo on tasapeli. Korjaamme tämän seuraavassa vaiheessa.

1. Voit korjata tietojen lajitteluongelman valitsemalla **New Rank** -sarakkeen ja vaihtamalla sitten **kaavarivin** kaavan seuraavaan muotoon:

   ```
    = Table.Sort(#"Changed Type1",{{"New Rank", Order.Ascending},{"Rank", Order.Ascending}})
   ```

1. Valitse kaavaruudun vasemmalla puolella oleva vihreä valintamerkki tai valitse **Enter**. 

   Rivit on nyt järjestetty sekä **New Rank**- että **Rank**-sarakkeen mukaisesti. Voit myös valita **käytössä olevan vaiheen** luettelon mistä tahansa kohdasta ja jatkaa tietojen muotoilua järjestyksen tässä kohdassa. Kyselyeditori lisää automaattisti uuden vaiheen tällä hetkellä valitun **käytössä olevan vaiheen** perään. 

1. Valitse **Käytössä oleva vaihe** -kohdassa mukautettua saraketta edeltävä vaihe, eli **Poistetut sarakkeet** vaihe. Korvaamme tässä **Weather**-sijoituksen arvon Arizonassa. Napsauta hiiren kakkospainikkeella solua, joka sisältää Arizonan **Weather**-sijoituksen. Valitse sitten **Korvaa arvot**. Huomioi, mikä **käytössä oleva vaihe** on valittuna.

   ![Valitse sarakkeelle Korvaa arvot](media/desktop-shape-and-combine-data/shapecombine_replacevalues2.png)

1. Valitse **lisää**.

    Koska lisäämme vaiheen, kyselyeditori varoittaa tämän vaaroista: myöhemmät vaiheet voivat tehdä kyselystä rikkinäisen. 

    ![Vahvista Lisää vaihe](media/desktop-shape-and-combine-data/shapecombine_insertstep.png)

1. Muuta tietoarvoksi _51_. 

   Kyselyeditori korvaa Arizonan tiedot. Kun luot uutta **käytössä olevaa vaihetta**, kyselyeditori nimeää sen toiminnon mukaisesti: tässä tapauksessa nimeksi tulee **Replaced Value**. Jos sinulla kyselyssä useita vaiheita, joilla on sama nimi, kyselyeditori lisää jokaiseen myöhempään **käytettyyn vaiheeseen** nimen loppuun järjestysnumeron, jotta erotat vaiheet toisistaan.

1. Valitse viimeinen **käytössä oleva vaihe**, **Lajiteltu rivit**. 

   Huomaa, että tiedot ovat muuttuneet Arizonan uuden sijoituksen suhteen. Muutos johtuu siitä, että lisäsimme **Replaced Value** -vaiheen oikeaan sijaintiin ennen **Added Custom** -vaihetta.

1. Lopuksi haluamme vaihtaa taulukon nimeksi paremmin kuvaavan nimen. Kirjoita **kysely asetukset**-ruudun **ominaisuudet**-kohtaan taulukon uusi nimi ja valitse **Anna**. Anna tälle taulukolle nimeksi *RetirementStats*.

   ![Nimeä taulukko uudelleen kyselyasetuksissa](media/desktop-shape-and-combine-data/shapecombine_renametable2.png)

   Kun ryhdyt luomaan raportteja, taulukoiden nimien kannattaa olla kuvaavia. Tämä pätee etenkin silloin, jos muodostat yhteyden useisiin tietolähteisiin, jotka on lueteltu **raporttinäkymän** **Kentät**-ruudussa.

   Nyt olemme muotoilleet tietojamme tarpeeksi. Seuraavaksi muodostamme yhteyden toiseen tietolähteeseen ja yhdistämme tiedot.

## <a name="combine-data"></a>Tietojen yhdistäminen
Tiedot eri osavaltioista ovat mielenkiintoisia. Niistä on myös hyötyä muidenkin analyysien ja kyselyiden luomisessa. Tässä on kuitenkin yksi ongelma: suurin osa saatavilla olevista tiedoista käyttää kaksikirjaimisia osavaltiolyhenteitä, ei osavaltioiden koko nimiä. Meidän täytyy siis yhdistää osavaltioiden nimet ja niiden lyhenteet.

Meillä on kuitenkin onnea, sillä eräs toinen julkinen tietolähde tekee juuri tämän, mutta sen tiedot vaativat suhteellisen paljon muotoilua, ennen kuin voimme yhdistää ne tähän eläköitymistaulukkoomme. Jos haluat muotoilla tietoja, toimi seuraavasti:

1. Valitse kyselyeditorin **Aloitus**-valintanauhasta **Uusi lähde \> Verkko**. 

2. Anna osavaltioiden lyhenteet sisältävän sivuston osoite, *https://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations* , ja valitse sitten **Yhdistä**.

   Siirtymistoiminto näyttää verkkosivuston sisällön.

    ![Siirtymissivu](media/desktop-shape-and-combine-data/designer_gsg_usstateabbreviationsnavigator2.png)

1. Valitse **Koodit ja lyhenteet**. 

   > [!TIP]
   > Vaatii melko paljon työtä, ennen kuin taulukon tiedot on muotoiltu haluamallamme tavalla. Onko alla lueteltujen vaiheiden suorittamiseen jokin nopeampi tai helpompi tapa? Kyllä, voit luoda kahden taulukon välille *suhteen* ja muotoilla tietoja sitten tämän suhteen perusteella. Seuraavista vaiheista on kuitenkin hyötyä, kun opettelet taulukoiden käyttöä, mutta suhteiden avulla voit käyttää nopeasti tietoja useista taulukoista.
> 
> 

Jos haluat saada tiedot kuntoon, toimi seuraavasti:

1. Poista ylin rivi. Ylin rivi on seurausta tavasta, jolla verkkosivun taulukko on luotu, joten emme tarvitse sitä. Valitse **Aloitus**-valintanauhasta **Vähennä rivejä \> Poista rivit \> Poista ylimmät rivit**.

    ![Valitse Poista ylimmät rivit](media/desktop-shape-and-combine-data/shapecombine_removetoprows.png)

    Näyttöön avautuu **Poista ylimmät rivit** ikkuna, jossa voit määrittää, montako riviä haluat poistaa.

    > [!NOTE]
    > Jos Power BI tuo vahingossa taulukko-otsikot rivinä tietotaulukkoosi, voit korjata taulukkosi valitsemalla valintanauhan **Aloitus**- tai **Muunna**-välilehdestä **Käytä ensimmäistä riviä otsikkoina**.

1. Poista alimmat 26 riviä. Nämä rivit ovat Yhdysvaltain alueita, joita meidän ei tarvitse sisällyttää. Valitse **Aloitus**-valintanauhasta **Vähennä rivejä \> Poista rivit \> Poista alimmat rivit**.

    ![Valitse Poista alimmat rivit](media/desktop-shape-and-combine-data/shapecombine_removebottomrows.png)

1. Koska RetirementStats-taulukko ei sisällä Washington DC:n tietoja, meidän täytyy suodattaa se luettelostamme. Valitse avattava **Region Status** -valikko ja poista sitten valintaruutu **Federal district** -kohdan vierestä.

    ![Tyhjennä Federal District -valintaruutu](media/desktop-shape-and-combine-data/shapecombine_filterdc.png)

1. Poista muutama tarpeeton sarake. Koska meidän täytyy vain yhdistää kukin osavaltio sen viralliseen kaksikirjaimiseen lyhenteeseen, voimme poistaa seuraavat sarakkeet: **Column1**, **Column3**, **Column4** ja **Column6**–**Column11**. Valitse ensin **Column1**, paina **CTRL**-näppäin pohjaan ja valitse sitten muut poistettavat sarakkeet yksitellen. Valitse valintanauhan **Aloitus**-välilehdestä **Poista sarakkeet \> Poista sarakkeet**.

   ![Poista sarake](media/desktop-shape-and-combine-data/shapecombine_removecolumns.png)

   > [!NOTE]
   > Tämä on hyvä hetki huomauttaa, että kyselyeditorissa käytettyjen vaiheiden *järjestys* on tärkeä. Se voi myös vaikuttaa tietojen muotoiluun. On tärkeää huomioida se, miten yksi vaihe voi vaikuttaa toiseen myöhempään vaiheeseen. Jos poistat vaiheen käytetyistä vaiheista, myöhemmät vaiheet eivät ehkä toimi niin kuin alun perin tarkoitit, koska vaiheen poistaminen kyselyn vaihejärjestyksestä vaikuttaa muihin vaiheisiin.

   > [!NOTE]
   > Kun pienennät kyselyeditorin ikkunaa kapeammaksi, jotkin valintanauhan kohteet tiivistetään, jotta näkyvissä oleva tila on käytössä mahdollisimman tehokkaasti. Kun levennät kyselyeditorin ikkunaa, valintanauhan kohteet laajentuvat, jotta valintanauhan suurempi tila saadaan paremmin käyttöön.

1. Nimeä sarakkeet ja taulukko uudelleen. Sarake voidaan nimetä uudelleen muutamia tavoilla: Valitse ensin sarake ja valitse sitten **Nimeä uudelleen** valintanauhan **Muunna**-välilehdestä tai napsauta hiiren kakkospainikkeella ja valitse **Nimeä uudelleen**. Seuraavassa kuvassa on nuolet, jotka osoittavat molempiin toimintoihin, mutta sinun tarvitsee käyttää vain toista.

   ![Nimeä sarake uudelleen kyselyeditorissa](media/desktop-shape-and-combine-data/shapecombine_rename.png)

1. Anna sarakkeiden uusiksi nimiksi *State Name* ja *State Code*. Jos haluat nimetä taulukon uudelleen, anna **nimi** **Kyselyasetukset**-ruudussa. Anna tälle taulukolle nimeksi *StateCodes*.

## <a name="combine-queries"></a>Yhdistä kyselyt

Nyt kun olemme muotoilleet StateCodes-taulukon halutulla tavalla, yhdistetään nämä kaksi taulukkoa tai kyselyä yhdeksi. Koska taulukot, jotka meillä nyt ovat, ovat tulosta tietoihin soveltamistamme kyselyistä, niitä kutsutaan usein *kyselyiksi*.

Kyselyitä voi yhdistää kahdella tavalla: *yhdistämällä* tai *loppuun liittämällä*.

- Jos sinulla on sarake tai sarakkeita, jonka tai jotka haluat lisätä toiseen kyselyyn, *yhdistä* kyselyt. 
- Jos sinulla on lisärivejä tietoja, jotka haluat lisätä olemassa olevaan kyselyyn, *liitä ne kyselyn loppuun*.

Tässä tapauksessa haluamme yhdistää kyselyt. Toimi seuraavasti:
 
1. Valitse kyselyeditorin vasemmasta ruudusta kysely, *johon* haluat toisen kyselyn yhdistyvän. Tässä tapauksessa se on **RetirementStats**. 

1. Valitse valintanauhan **Aloitus\>-välilehdestä** Yhdistä  **Yhdistä kyselyt**.

   ![Valitse Yhdistä kyselyt](media/desktop-shape-and-combine-data/shapecombine_mergequeries.png)

   Sinua saatetaan pyytää määrittämään yksityisyystaso. Näin varmistetaan, että tiedot yhdistetään siten, että sisällytä tai siirrä tietoja, joita et halua.

   Seuraavaksi näyttöön avautuu **Yhdistä**-ikkuna. Siinä kysytään, minkä taulukon haluat yhdistää valittuun taulukkoon ja pyydetään määrittämään yhdistämisen vastaavat sarakkeet. 

1. Valitse RetirementStats-taulukosta **State** ja valitse sitten **StateCodes**-kysely. 

   Kun valitset oikeat vastaavat sarakkeet, **OK**-painike on käytössä.

   ![Yhdistä-ikkuna](media/desktop-shape-and-combine-data/shapecombine_merge2.png)

1. Valitse **OK**.

   Kyselyeditori luo kyselyn loppuun sarakkeen **NewColumn**, joka sisältää sen taulukon (kyselyn) sisällön, joka yhdistettiin olemassa olevaan kyselyyn. Kaikki yhdistetyn kyselyn sarakkeet tiivistetään **NewColumn**-sarakkeeseen, mutta voit **laajentaa** taulukon ja sisällyttää haluamasi sarakkeet.

   ![NewColumn-sarake](media/desktop-shape-and-combine-data/shapecombine_mergenewcolumn.png)

1. Jos haluat laajentaa yhdistetyn taulukon ja valita sisällytettävät sarakkeet, valitse laajennuskuvake (.![Laajenna-kuvake](media/desktop-shape-and-combine-data/icon.png)). 

   Näyttöön avautuu **Laajenna**-ikkuna.

   ![NewColumn kyselyssä](media/desktop-shape-and-combine-data/shapecombine_mergeexpand.png)

1. Tässä tapauksessa haluamme vain **State Code** -sarakkeen. Valitse sarake, poista kohdan **Käytä alkuperäisen sarakkeen nimeä etuliitteenä** valinta ja valitse sitten **OK**.

   Jos olisimme jättäneet kohdan **Käytä alkuperäisen sarakkeen nimeä etuliitteenä** valintaruudun valituksi, yhdistetyn sarakkeen nimeksi olisi tullut **NewColumn.State Code**.

   > [!NOTE]
   > Haluatko kokeilla, miten voit tuoda NewColumn-taulukon? Voit kokeilla eri tapoja. Jos et pidä tuloksista, poista kyseinen vaihe **Kyselyasetukset**-ruudun **käytössä olevien vaiheiden** luettelosta. Tämä palauttaa kyselysi tilaan, jossa se oli ennen tätä **laajennusvaihetta**. Voit tehdä näin niin monta kertaa kuin haluat, kunnes saat laajennusprosessista haluamasi kaltaisen.

   Nyt meillä on yksi kysely (taulukko), joka yhdistää kaksi tietolähdettä, jotka kummatkin on muotoiltu tarpeidemme mukaisesti. Tämän kyselyn pohjalta voit luoda useita muitakin kiinnostavia tietoyhteyksiä, esimerkiksi asumiskuluista, demografisista tiedoista tai työmahdollisuuksista missä tahansa osavaltiossa.

1. Ota muutoksesi käyttöön ja sulje kyselyeditori valitsemalla valintanauhan **Aloitus**-välilehdeltä **Sulje ja ota käyttöön**. 

   Muunnettu tietojoukko näytetään Power BI Desktopissa, jossa voit luoda raportteja sen pohjalta.

   ![Valitse Sulje ja ota käyttöön](media/desktop-shape-and-combine-data/shapecombine_closeandapply.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Lisää tietoja Power BI Desktopista ja sen toiminnoista on seuraavissa resursseissa:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Kyselyn yleiskatsaus Power BI Desktopissa](desktop-query-overview.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietoihin yhdistäminen Power BI Desktopissa](desktop-connect-to-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](desktop-common-query-tasks.md)   

