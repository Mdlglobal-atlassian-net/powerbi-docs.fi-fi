---
title: 'Opetusohjelma: Koneoppimismallin luominen Power BI:ssä (esikatselu)'
description: Tässä opetusohjelmassa luodaan koneoppimismalli Power BI:ssä.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 03/29/2019
ms.author: davidi
LocalizationGroup: Connect to services
ms.openlocfilehash: 611d6f6c923e6cb68af94840c4266a0b6dee7651
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61406748"
---
# <a name="tutorial-build-a-machine-learning-model-in-power-bi-preview"></a>Opetusohjelma: Koneoppimismallin luominen Power BI:ssä (esikatselu)

Tässä opetusartikkelissa käytetään **automaattianalyysipalveluita** binaariennustemallin luomiseen ja käyttämiseen Power BI:ssä. Opetusohjelma sisältää ohjeita siitä, miten voit luoda Power BI -tietovuon sekä tietovuossa määritettyjä entiteettejä käyttämällä harjoittaa ja vahvistaa koneoppimismallia suoraan Power BI:ssä. Käytämme sitten tätä mallia pisteytystä varten ennusteiden luomiseen.

Ensin luodaan binaarisen ennusteen koneoppimismalli online-ostajien ostoaikeen ennustamiseen heidän online-istunnon määritejoukkonsa perusteella. Tässä harjoituksessa käytetään koneoppimisen tietojoukon vertailuarvoa. Mallin harjoittamisen jälkeen Power BI luo automaattisesti vahvistusraportin, jossa kerrotaan mallin tulokset. Voit sitten tarkistaa vahvistusraportin ja ottaa mallin käyttöön tiedoissasi pisteytystä varten.

Tämä opetusohjelma koostuu seuraavista vaiheista:

> [!div class="checklist"]
> * Tietovuon luominen syötetietojen avulla
> * Koneoppimismallin luominen ja harjoittaminen
> * Mallin vahvistusraportin tarkasteleminen
> * Mallin käyttäminen tietovuoentiteetissä
> * Mallin pisteytetyn tulosteen käyttäminen Power BI -raportissa

## <a name="create-a-dataflow-with-the-input-data"></a>Tietovuon luominen syötetietojen avulla

Tämän opetusohjelman ensimmäinen osa on luoda tietovuo syötetietojen avulla. Prosessissa on muutamia eri vaiheita, kuten seuraavissa osioissa kuvataan, ja ensimmäisenä vaiheena on tietojen hankkiminen.

### <a name="get-data"></a>Nouda tiedot

Tietovuon luomisen ensimmäinen vaihe on tietolähteiden valmistelu. Tässä tapauksessa käytämme koneoppimisen tietojoukkoa online-istuntojen joukosta, joista osa päättyi ostoon. Tietojoukko sisältää joukon määritteitä näistä istunnoista, ja käytämme niitä mallimme harjoittamiseen.

Voit ladata tietojoukon UC Irvine -verkkosivustosta.  Tämä on käytettävissä myös tässä opetusohjelmassa seuraavasta linkistä: [online_shoppers_intention.csv](https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv).

### <a name="create-the-entities"></a>Luo entiteetit

Jotta voit luoda entiteetit tietovirrassa, kirjaudu sisään Power BI -palveluun ja siirry varatun kapasiteettisi työtilaan, jossa AI-esikatselu on käytössä.

Jos sinulla ei vielä ole työtilaa, voit luoda sellaisen valitsemalla Power BI -palvelun vasemmanpuoleisesta siirtymisvalikosta **Työtilat** ja valitsemalla sitten alareunan paneelista **Luo sovelluksen työtila**. Tämä avaa oikeaan reunaan ruudun, jossa voit antaa työtilan tiedot. Kirjoita työtilan nimi ja valitse **Lisäasetukset**. Varmista, että työtila käyttää varattua kapasiteettia valintanapin avulla ja että se on määritetty varattuun kapasiteettiesiintymään, jossa on käytössä tekoälyn esikatselu. Valitse **Tallenna**.

![Luo työtila](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-01.png)

Kun työtila on luotu, voit valita aloitusnäytön oikeassa alanurkassa **Ohita** seuraavan kuvan mukaisesti.

![Ohita, jos sinulla on työtila](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-02.png)

Valitse **Tietovuot (esikatselu)** -välilehti. Valitse työtilan oikeassa ylänurkassa oleva **Luo**-painike ja valitse sitten **Tietovuo**.

![Luo tietovuo](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-03.png)

Valitse **Lisää uudet entiteetit**. Tämä käynnistää **Power Query** -editorin selaimessa.

![Lisää uudet entiteetit](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-04.png)

Valitse tietolähteeksi **teksti- tai CSV-tiedosto** seuraavan kuvan mukaisesti.

![Teksti- tai CSV-tiedosto valittuna](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-05.png)

Liitä seuraavaksi näyttöön tulevassa **Muodosta yhteys tietolähteeseen** -kohdassa seuraava linkki *online_shoppers_intention.csv*-tiedostoon **Tiedostopolku tai URL-osoite** -ruutuun ja valitse sitten **Seuraava**.

`https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv`

![Tiedostopolku](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-06.png)

Power Query -editori näyttää CSV-tiedostossa olevien tietojen esikatselun. Valitse komentopalkista **Muunna taulukko** ja valitse sitten avautuvasta valikosta **Käytä ensimmäistä riviä otsikkoina**. Tämä lisää _Ylennetyt otsikot_ -kyselyvaiheen näytön oikeassa reunassa olevaan **Käytössä olevat vaiheet** -osioon. Voit nimetä kyselyn uudelleen muuttamalla oikealla olevan **Nimi**-ruudun arvoa. Voit esimerkiksi muuttaa kyselyn nimeksi _Online-vierailija_.

![Muuta nimeä](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-07.png)

Jotkin tämän tietojoukon määritetietotyypeistä ovat _lukuja_ tai _totuusarvoja_, mutta **Power Query** voi tulkita ne merkkijonoiksi. Valitse määritetyyppi-kuvake kunkin sarakeotsikon yläosasta, jos haluat muuttaa alla lueteltuja sarakkeita seuraavanlaisiksi:

* **Desimaaliluku:** Administrative_Duration; Informational_Duration; ProductRelated_Duration; BounceRates; ExitRates; PageValues; SpecialDay
* **Tosi/epätosi:** Viikonloppu; Tuotto

![Vaihda tietotyyppiä](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-08.png)

Harjoitettava **binaariennustemalli** edellyttää Totuusarvo-kenttää otsikkona, jossa kerrotaan aiempien havaintojen tulokset. Tässä tietojoukossa _Tuotto_-määrite ilmaisee ostoa, ja tämä määrite on jo saatavana totuusarvona. Otsikolle ei siis tarvitse lisätä laskettua saraketta. Muissa tietojoukoissa on ehkä muunnettava aiemmin luodut otsikkomääritteet Totuusarvo-sarakkeeksi.

Sulje Power Query -editori valitsemalla **Valmis**. Tämä näyttää entiteettiluettelon lisätyillä _Online-vierailijoiden_ tiedoilla. Valitse oikeassa yläkulmassa **Tallenna**, anna tietovuolle nimi ja valitse sitten valintaikkunassa **Tallenna** seuraavan kuvan mukaisesti.

![Tallenna tietovuo](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-09.png)

### <a name="refresh-the-dataflow"></a>Tietovuon päivittäminen

Tietovuon tallentamisen jälkeen näyttöön tulee ilmoitus, jossa kerrotaan, että tietovuo on tallennettu. Valitse **Päivitä nyt**, niin lähteen tietoja käytetään tietovuossa.

![Päivitä nyt](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-10.png)

Valitse oikeasta yläkulmasta **Sulje** ja odota, kunnes tietovuon päivitys on valmis.

Voit päivittää tietovuon myös käyttämällä **Toiminnot**-komentoja. Tietovuossa näkyy aikaleima päivityksen valmistumisesta.

![Päivityksen aikaleima](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-11.png)

## <a name="create-and-train-a-machine-learning-model"></a>Koneoppimismallin luominen ja harjoittaminen

Valitse tietovuo, kun päivitys on valmis. Jos haluat lisätä koneoppimismallin, valitse **Käytä koneoppimismallia** -painike **Toiminnot**-luettelossa sen perusentiteetin kohdalla, joka sisältää harjoitus- ja otsikkotiedot, ja valitse sitten **Lisää koneoppimismalli**.

![Lisää koneoppimismalli](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-12.png)

Ensimmäinen vaihe koneoppimismallin luomisessa on tunnistaa ne historialliset tiedot, mukaan lukien otsikkokenttä, jonka haluat ennustaa. Malli luodaan näistä tiedoista oppimalla.

Käytetyn tietokentän kohdalla kyseessä on **Tuotto**-kenttä. Valitse **Tuotto** Historiallisen tuloksen kenttä -arvoksi ja valitse sitten **Seuraava**.

![Valitse historialliset tiedot](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-13.png)

Seuraavaksi on valittava luotavan koneoppimismallin tyyppi. Power BI analysoi määrittämäsi historiallisen tuloksen kentän arvoja ja ehdottaa tämän kentän ennakoimiseksi luotavien koneoppimismallien tyyppejä.

Tässä tapauksessa, koska ennakoimme binaarista tulosta siitä, tekeekö käyttäjä oston vai ei, valitse mallityypin kohdalla **Binaarinen ennuste** ja valitse sitten Seuraava.

![Binaarinen ennuste valittuna](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-14.png)

Seuraavaksi Power BI tarkistaa tiedot alustavasti ja ehdottaa syötteitä, joita malli voi käyttää. Voit halutessasi mukauttaa mallissa käytettyjä syötekenttiä. Voit valita kootussa tietojoukossa kaikki kentät valitsemalla entiteetin nimen vieressä olevan valintaruudun. Hyväksy syötteet valitsemalla **Seuraava**.

![Valitse Seuraava-valintaruutu](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-15.png)

Viimeisessä vaiheessa mallille on annettava nimi sekä otsikot niille tuloksille, joita käytetään automaattisesti luodussa raportissa, joka tekee yhteenvedon mallin vahvistuksen tuloksista. Seuraavaksi meidän on nimettävä mallin _Ostoaikeen ennuste_ sekä annettava tosi- ja epätosi-otsikoille nimet _Osto_- ja _Ei ostoa_. Valitse **Tallenna**.

![Tallenna malli](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-16.png)

Koneoppimismallimme on nyt valmiina harjoittamiseen. Aloita mallin harjoittaminen valitsemalla **Päivitä nyt**.

![Päivitä nyt](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-17.png)

Harjoitusprosessi aloitetaan ottamalla näytteitä historiallisista tiedoista ja normalisoimalla ne ja sitten jakamalla tietojoukkosi kahdeksi uudeksi entiteeteiksi: *Ostoaikeen ennusteen harjoitustiedot* ja *Ostoaikeen ennusteen testitiedot*.

Tietojoukon koosta riippuen harjoitusprosessi voi kestää muutamasta minuutista muutamaan tuntiin. Tässä vaiheessa näet mallin tietovuon **Koneoppimismallit**-välilehdellä. _Valmis_-tila ilmaisee, että malli on asetettu jonoon harjoittamista varten tai että sitä harjoitetaan parhaillaan.

![Valmiina harjoittamiseen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-18.png)

Kun mallia harjoitetaan, et voi tarkastella tai muokata tietovuota. Voit vahvistaa mallin harjoittamisen ja vahvistamisen tietovuon tilan kautta. Tämä näkyy tietojen päivittämisenä työtilan **Tietovuot**-välilehdessä.

![Käsittelyssä](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-19.png)

Kun mallin harjoittaminen on valmis, tietovuossa näkyy päivitetty päivitysaika. Voit vahvistaa mallin harjoittamisen valmistumisen siirtymällä tietovuon **Koneoppimismallit**-välilehteen. Luomasi mallin tilana pitäisi näkyä **Harjoitettu**, ja **Harjoitettu viimeksi** -ajan pitäisi nyt olla päivitetty.

![Harjoitettu viimeksi](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-20.png)

## <a name="review-the-model-validation-report"></a>Mallin vahvistusraportin tarkasteleminen

Jos haluat tarkastella mallin vahvistusraporttia, valitse **Koneoppimismallit**-kohdassa **Tarkastele suorituskykyraporttia ja käytä mallia** -painike mallin **Toiminnot**-sarakkeessa. Tässä raportissa kuvataan, miten koneoppimismalli todennäköisesti suoriutuu.

Valitse raportin **Mallinsuoritus kyky** -sivulla **Tärkeimmät vaikuttajat**, jotta voit tarkastella mallisi tärkeimpiä ennusteita. Voit valita jonkin ennusteen, jotta näet kyseiseen ennusteeseen liittyvän tulosten jakautumisen.

![Mallin suorituskyky](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-21.png)

Mallin suorituskyky -sivulla olevan **Todennäköisyyden raja-arvo** -osittajan avulla voit tarkastella sen vaikutusta mallin Tarkkuus- ja Saanti-mittareihin.

![Todennäköisyyden raja-arvo](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-22.png)

Raportin muut sivut kuvailevat mallin tilastollisia suorituskykymittareita.

Raportti sisältää myös Harjoitustiedot-sivun, jossa kuvataan erilaisia suoritettuja toistoja, miten ominaisuudet poimittiin syötteistä ja käytetyn lopullisen mallin hyperparametreja.

## <a name="apply-the-model-to-a-dataflow-entity"></a>Mallin käyttäminen tietovuoentiteetissä

Valitse **Käytä mallia** -painike raportin yläosasta, jos haluat käynnistää tämän mallin, kun tietovuo päivitetään. **Käytä**-valintaikkunassa voit määrittää kohde-entiteetin, jonka lähdetietoja malli käyttää.

![Käytä mallia](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-23.png)

**Päivitä** pyydettäessä tietovuo, jotta voit esikatsella mallin tuloksia.

Mallin käyttäminen luo uuden entiteetin, jonka jälkiliite **täydennetty <mallin_nimi>** on liitettynä entiteettiin, jossa malli otettiin käyttöön. Tässä tapauksessa mallin ottaminen käyttöön **OnlineOstajat**-entiteetissä luo kohteen **OnlineOstajat täydennetty Ostoaikeen ennuste**, joka sisältää ennustetun tuloksen mallista.

Binaariennustemallin käyttäminen lisää ennusteeseen kolme saraketta, jotka sisältävät ennustetun tuloksen, todennäköisyyden pistemäärän ja parhaat tietuekohtaiset vaikuttajat ja joista jokaisen etuliitteenä on määritetty sarakkeen nimi.

![Kolme tulossaraketta](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-24.png)

Tunnetun ongelman vuoksi täydennetyn entiteetin pisteytetyt tulostesarakkeet ovat käytettävissä vain Power BI Desktopista. Jos haluat esikatsella näitä palvelussa, sinun on käytettävä erityistä esikatseluentiteettiä.

Kun tietovuon päivitys on valmis, voit tarkastella tuloksia valitsemalla **OnlineOstajat täydennetty Ostoaikeen ennuste – esikatselu** -entiteetin.

![Tarkastele tuloksia](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-25.png)

## <a name="using-the-scored-output-from-the-model-in-a-power-bi-report"></a>Mallin pisteytetyn tulosteen käyttäminen Power BI -raportissa

Jos haluat käyttää koneoppimismallin pisteytettyä tulosta, voit muodostaa yhteyden tietovuohon Power BI Desktopista käyttämällä tietovoiden liitintä. **OnlineOstajat täydennetty Ostoaikeen ennuste** -entiteettiä voidaan nyt käyttää mallin ennustusten sisällyttämiseen Power BI -raportteihin.

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä opetusohjelmassa loit ja käytit binaariennustemallia Power BI:ssä seuraavien vaiheiden avulla:

* Tietovuon luominen syötetietojen avulla
* Koneoppimismallin luominen ja harjoittaminen
* Mallin vahvistusraportin tarkasteleminen
* Mallin käyttäminen tietovuoentiteetissä
* Mallin pisteytetyn tulosteen käyttäminen Power BI -raportissa

Katso lisätietoja automaattianalyysipalveluista Power BI:ssä artikkelista [Automaattianalyysipalvelut Power BI:ssä (esikatselu)](service-machine-learning-automated.md).
