---
title: Power BI -yhdyskäytävien käytön aloittaminen
description: Opi Power BI -tietoyhdyskäytävien perusteet.
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 173122c863d9472b53051febbec543e140a4a6db
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/08/2018
---
# <a name="getting-started-with-power-bi-gateways"></a>Power BI -yhdyskäytävien käytön aloittaminen
Tervetuloa **Power BI -yhdyskäytävien käytön aloittaminen** -oppaaseen. Tutustut tässä lyhyessä oppaassa yhdyskäytävän toimintoihin, käyttötapaan ja siihen, miten voit asentaa, määrittää ja suorittaa oman yhdyskäytäväsi.  

![](media/service-gateway-getting-started/gw_gettingstarted_0a.png)

Yhdyskäytävien käyttöön voi liittyä teknisiä ongelmia, ja koska jokainen verkko ja yritys on erilainen, yhdyskäytävät voivat olla hyvinkin monimutkaisia. Jotta ne eivät tuntuisi liian vaikeilta, tutustutaanpa ensin perusteisiin.

## <a name="how-power-bi-gateways-work"></a>Power BI -yhdyskäytävien käyttötapa
**Yhdyskäytävä** on ohjelmisto, joka helpottaa pääsyä yksityisessä paikallisessa verkossa oleviin tietoihin, jotta niitä voidaan käyttää myöhemmin Power BI:n kaltaisessa pilvipalvelussa. Se muistuttaa portinvartijaa, joka kuuntelee yhteyspyyntöjä ja myöntää ne vain, kun käyttäjien pyynnöt täyttävät tietyt ehdot (kuten sen, onko käyttäjillä oikeus käyttää yhdyskäytävää). Sen ansiosta organisaatiot voivat jättää tietokannat ja varastot paikallisiin verkkoihinsa samalla kuitenkin käyttäen turvallisesti näiden tietojen alijoukkoja kiinnostavien raporttien ja koontinäyttöjen luomiseksi Power BI:ssä.

Yhdyskäytävä suojaa myös käyttöä ja tietoja salaamalla ja pakkaamalla kaikki sen läpi kulkevat tiedot ja mahdolliset salasanat, joita käytetään yhteyden muodostamiseen tietolähteisiin. Kaikki tämä kuulostaa ehkä varsin yksinkertaiselta, mutta sinun on otettava huomioon useita näkökohtia.

Haluat ehkä toisinaan saada oman henkilökohtaisen yhdyskäytäväsi, jos sinulla on suuri Excel-työkirja ja kolme SQL-tietokantaa, jotka sisältävät myynti- ja markkinointitietoja monen vuoden ajalta. Haluat ehkä myös luoda Power BI -koontinäytön, joka näyttää nämä myynnit kaikista näkökulmista. Olet ainoa raportteja luova henkilö, kyse on omasta Excel-työkirjastasi ja käytät näitä tietokantoja vain Power BI -raporttien luomiseen. Tarvitset yhdyskäytävän vain omaan käyttöösi, etkä jaa näitä tietolähteitä kenenkään muun kanssa.

Joskus organisaatiossasi saattaa olla monenlaisia tietokantoja eri toimittajilta, mukaan lukien Analysis Services, SAP, Oracle, IBM ja monet muut tietolähteet. Useiden henkilöiden on päästävä näihin tietokantoihin erilaisten raporttien luomiseksi. Tarvitset tässä tapauksessa yhdyskäytävän, jonka avulla voit määrittää oikeudet näihin kaikkiin tietolähteisiin ja joka jaetaan organisaatiosi monen henkilön kanssa. Kyse on tällöin täysin erilaisesta yhdyskäytävästä.

Onneksi Power BI tarjoaa kaksi yhdyskäytävää, jotka sopivat myös näihin tilanteisiin. Nämä Power BI:n tarjoamat kaksi yhdyskäytävää ovat seuraavat:

* **Paikallinen tietoyhdyskäytävä (henkilökohtainen tila)** – yksi käyttäjä voi muodostaa yhteyden tietolähteisiin, eikä tietoyhdyskäytävää voi jakaa muiden kanssa. Voidaan käyttää vain Power BI:n kanssa.
* **Paikallinen tietoyhdyskäytävä** – useat käyttäjät voivat muodostaa yhteyden useisiin paikallisiin tietolähteisiin, joita Power BI, PowerApps, Flow ja Azure Logic -sovellukset voivat käyttää yhden yhdyskäytäväasennuksen kanssa.

Kummatkin yhdyskäytävät suorittavat samantapaisen toiminnon – ne helpottavat yksityisessä paikallisessa verkossa olevien tietojen käyttöä siten, että niitä voidaan käyttää pilvipohjaisissa palveluissa, kuten Power BI:ssä. Henkilökohtaista yhdyskäytävää voi käyttää yksi henkilö ja vain Power BI **, paikallista tietoyhdyskäytävää** voivat käyttää useat käyttäjät ja palvelut.

Yhdyskäytävän valmistelu on kolmiosainen:

* Asenna yhdyskäytävä.
* Lisää käyttäjiä yhdyskäytävään (myönnä heille yhdyskäytävän käyttöoikeus).
* Muodosta yhteys tietolähteisiin.

Lisäksi voit yhdyskäytävän avulla tehdä toisenkin tärkeän jutun eli

* päivittää paikallisia tietoja, jotta Power BI -raportteihin voidaan päivittää tuoreet tiedot.

Tietojen päivittäminen tarkoittaa sitä, että Power BI -koontinäytöt ja -raportit näyttävät tuoreilta ja sisältävät uusimmat tiedot. Kun joku henkilö tarkastelee paikallisten tietojen avulla luomaasi raporttia, se sisältää uusimmat tiedot, vaikka olisit luonut raportin jo aikoja sitten.

Ensimmäinen osa eli yhdyskäytävän asentaminen on helppoa. Voit myös helposti sallia käyttäjien pääsyn yhdyskäytävään lisäämällä heidät vain Power BI -valintaikkunassa, ja homma on valmis. Yhteyden muodostaminen tietolähteisiin voi olla monimutkaista, koska tietolähteitä on paljon, ja niillä on kullakin omat yhteysvaatimuksensa ja -erityispiirteensä. Käsittelemme päivittämistä toisessa oppaassa, joten keskitymme tässä artikkelissa yhdyskäytävään.

Tarkastellaanpa ensin helppoja asioita ja käydään läpi yhdyskäytävän asentamista.

## <a name="install-the-gateway"></a>Yhdyskäytävän asentaminen
Asenna yhdyskäytävä avaamalla Power BI -palvelu (tämän linkin avulla voit käynnistää Power BI -palvelun selaimessasi ja rekisteröityä) ja kirjaudu sisään Power BI -tililläsi. Valitse Power BI -palvelun **latauskuvake** oikeassa yläkulmassa seuraavan kuvan mukaisesti, ja valitse **Tietoyhdyskäytävä**.

![](media/service-gateway-getting-started/gw_gettingstarted_01.png)

Pääset näin lataussivulle, jossa voit käynnistää latauksen napsauttamalla **Lataa yhdyskäytävä**.

![](media/service-gateway-getting-started/gw_gettingstarted_02.png)

Tämä näyttö sisältää tiiviin selvityksen yhdyskäytävän toiminnoista. Se sisältää myös pari tärkeää **varoitusta** – kun asennat yhdyskäytävän, se itse asiassa suoritetaan tietokoneessa, johon sen asensit. Jos tämä tietokone sammutetaan, yhdyskäytävä lakkaa myös toimimasta (eli se ei toimi, jos tietokone ei ole käynnissä). Lisäksi paras vaihtoehto ei ole asentaa sitä tietokoneelle, joka käyttää langatonta verkkoa, joten sinun pitäisi käyttää langalliseen verkkoon yhdistettyä tietokonetta.

Kun olet valmis, voit jatkaa asennusta valitsemalla **Seuraava**.

![](media/service-gateway-getting-started/gw_gettingstarted_03.png)

Päätät tässä vaiheessa, minkä yhdyskäytävän asennat – paikallisen yhdyskäytävän vai henkilökohtaisen yhdyskäytävän. Tässä oppaassa asennamme **paikallisen tietoyhdyskäytävän**.

Tässä päätösvaiheessa on otettava huomioon joitakin asioita:

* Molemmat yhdyskäytävät vaativat 64-bittisen Windows-käyttöjärjestelmän.
* Yhdyskäytäviä ei voi asentaa toimialueen ohjaimeen.
* Voit asentaa enintään kaksi paikallista tietoyhdyskäytävää samaan tietokoneeseen, ja suorittaa yhden tietoyhdyskäytävän kussakin tilassa (henkilökohtainen ja vakio). 
* Samassa tietokoneessa ei voida suorittaa samassa tilassa useampaa kuin yhtä yhdyskäytävää.
* Voit asentaa useita paikallisia tietoyhdyskäytäviä eri tietokoneisiin ja hallita niitä kaikkia samasta Power BI -yhdyskäytävän hallintaliittymästä (paitsi henkilökohtaista tietoyhdyskäytävää, katso seuraavaa luettelokohtaa).
* Kullekin Power BI -käyttäjälle voidaan suorittaa vain yhtä henkilökohtaisen tilan yhdyskäytävää. Jos asennat toisen henkilökohtaisen tilan yhdyskäytävän samalle käyttäjälle, jopa toiseen tietokoneeseen, uusin asennus korvaa aiemmin luodun edellisen asennuksen.

Yhdyskäytävän asennus alkaa, kun valitsemme **Seuraava**. Sinun on määritettävä, mihin yhdyskäytävä asennetaan, ja oletussijainti on yleensä paras.

![](media/service-gateway-getting-started/gw_gettingstarted_06.png)

Asennusprosessi etenee nopeasti, ja näet tilarivin.

![](media/service-gateway-getting-started/gw_gettingstarted_06a.png)

Kun olet melkein valmis, sinun on määritettävä yhdyskäytävän kanssa käytettävä tili. Sen pitäisi olla tili (käyttäjätunnus ja salasana), jota käytät rekisteröitymisessä Power BI -palveluun; yhdyskäytävä liitetään Power BI -tiliisi ja määrität yhdyskäytävät Power BI -palvelusta.

![](media/service-gateway-getting-started/gw_gettingstarted_07.png)

Sisäänkirjautuminen suoritetaan seuraavan kuvan mukaisesti.

![](media/service-gateway-getting-started/gw_gettingstarted_08.png)

Kun olet kirjautunut sisään, sinun on luotava **palautusavain**. Käsittelemme tätä tarkemmin toisessa artikkelissa. Tällä hetkellä sinun on vain tiedettävä, että tarvitset palautusavainta yhdyskäytävän palauttamiseen tai siirtämiseen.

![](media/service-gateway-getting-started/gw_gettingstarted_09.png)

Kun kaikki sujuu hyvin, näkyviin tulee ilmoitusikkuna, jonka mukaan yhdyskäytäväsi on valmis.

![](media/service-gateway-getting-started/gw_gettingstarted_10.png)

Paikallinen yhdyskäytävä on nyt asennettu. Kuten lupasimme, tämä prosessi sujui varsin helposti. Seuraava vaiheessa joko **lisäät käyttäjiä** tai **tietolähteitä**. Voit tehdä kumman tahansa ensin ja lisätä kumman tahansa alkuperäisen määrityksen jälkeen.

Seuraavassa osiossa kuvataan käyttäjien lisäämistä yhdyskäytävään, jonka jälkeen tarkastellaan tietolähteiden lisäämistä yhdyskäytävään.

## <a name="add-users-to-a-gateway"></a>Käyttäjien lisääminen yhdyskäytävään
Nyt kun yhdyskäytävä on asennettu, sitä hallitaan **Power BI -palvelusta**. Saat yhdyskäytävien hallintanäytön Power BI -palvelussa valitsemalla hammaspyöräkuvakkeen oikeassa yläkulmassa ja valitsemalla sitten **Hallitse yhdyskäytäviä**.

![](media/service-gateway-getting-started/gw_gettingstarted_15.png)

Power BI -palvelun piirtoalustassa on sivu, jossa voit hallita yhdyskäytäviä. **Yhdyskäytävän asetukset** -sivu näyttää seuraavanlaiselta.

![](media/service-gateway-getting-started/gw_gettingstarted_12.png)

Jos napautat tai napsautat **Järjestelmänvalvojat**, näet seuraavan järjestelmänvalvojien hallintasivun. Huomaa, että tämä koskee vain sitä, mitkä käyttäjät voivat *hallita* yhdyskäytävää, ja yhdyskäytävän käyttäjät lisätään (tai poistetaan) kustakin yksittäisestä tietolähteestä eri sivun avulla. Tarkastelemme tätä seuraavissa parissa kappaleessa.

![](media/service-gateway-getting-started/gw_gettingstarted_13.png)

Kun olet asentanut ja vahvistanut (yhteyden muodostaminen onnistui) tietolähteen, se näkyy siihen liittyvän yhdyskäytävän alapuolella **Hallitse yhdyskäytäviä** -näytön vasemmalla puolella seuraavan kuvan mukaisesti. Huomaa, että oikeanpuoleisessa ruudussa on kaksi osaa, joiden välillä voit siirtyä: **Tietolähdeasetukset** ja **Käyttäjät**. Seuraava näyttö on **Tietolähdeasetukset**-osio.

![](media/service-gateway-getting-started/gw_gettingstarted_16.png)

Kun valitset **Käyttäjät**, näkyviin tulee tekstiruutu, johon voit kirjoittaa ne organisaatiosi käyttäjät, joille haluat myöntää oikeuden valittuun tietolähteeseen. Seuraavassa kuvassa näet, että olen lisännyt Maggien ja Adamin.

Kun kirjoitat sähköpostiosoitetta tekstiruutuun, Power BI näyttää luettelon käyttäjistä, joiden sähköpostiosoite vastaa kirjoittamaasi. Voit sitten napsauttaa nimeä ja lisätä sen luetteloon.

Voit nyt myös lisätä sähköpostiryhmiä (aliaksia) käyttöoikeuden sallimiseksi henkilöryhmille ja yksittäisille henkilöille.

![](media/service-gateway-getting-started/gw_gettingstarted_17.png)

Kun olet valinnut **Lisää**, lisätyt jäsenet näkyvät ruudussa, ja voit halutessasi lisätä muita jäseniä. Käyttäjien poistaminen on yhtä helppoa. Valitse vain käyttäjien nimen viereinen valintaruutu ja sitten ruudun alta **Poista**-painike.

![](media/service-gateway-getting-started/gw_gettingstarted_18.png)

Siinä kaikki. Muista, että sinun on lisättävä käyttäjiä jokaiseen tietolähteeseen, johon haluat myöntää käyttöoikeuden. Jokaisessa tietolähteessä on erillinen luettelo käyttäjistä, ja sinun on lisättävä käyttäjiä kuhunkin tietolähteeseen erikseen.

## <a name="adding-data-sources"></a>Tietolähteiden lisääminen
Jotta yhdyskäytävästäsi olisi hyötyä, siihen on tietenkin lisättävä tietolähteitä. Tässä vaiheessa Power BI -yhdyskäytävä hieman monimutkaistuu – saatavilla on monia erilaisia tietolähteitä, joilla kullakin on omat vaatimuksensa (ja usein oma vaadittu ohjaimensa).

Ennen toiseen artikkeliin siirtymistä kerromme seuraavassa, miten voit lisätä tietolähteen. Valitse **Power BI -palvelun** **Hallitse yhdyskäytäviä** -sivulla yhdyskäytävä, johon haluat lisätä tietolähteen. Valitse sitten **Lisää tietolähde** sivun vasemmasta yläkulmasta yhdyskäytävien luettelon yläpuolelta.

**Tietolähdeasetukset**-ruutu ilmestyy tällöin oikeanpuoleiseen ruutuun seuraavan kuvan mukaisesti. Voit täällä nimetä tietolähteesi (joka on kirjoitettu **Tietolähteen nimi** -tekstiruutuun) ja valita sen tyypin **avattavasta Tietolähteen tyyppi** -luettelosta.

![](media/service-gateway-getting-started/gw_gettingstarted_14.png)

No niin, yhdyskäytäväsi on nyt asennettu, ja olet valmis lisäämään tietolähteitä. Hienoa! Seuraava tieto-osio sisältää tietolähteiden resurssit, lisätietoja yhdyskäytävien käytöstä ja muita hyödyllisiä tietoja.

## <a name="next-steps"></a>Seuraavat vaiheet
[Paikallisen tietoyhdyskäytävän käyttö](service-gateway-onprem.md)  
[Paikallinen tietoyhdyskäytävä tarkemmin](service-gateway-onprem-indepth.md)  
[Paikallinen tietoyhdyskäytävä (henkilökohtainen tila)](service-gateway-personal-mode.md)
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

