---
title: 'Opetusohjelma: Luo Automaattianalyysipalvelujen malli Power BI (esikatselu)'
description: Tässä opetusohjelmassa luot Power BI-Koneoppimisen malli.
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
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61406748"
---
# <a name="tutorial-build-a-machine-learning-model-in-power-bi-preview"></a>Opetusohjelma: Luo Automaattianalyysipalvelujen malli Power BI (esikatselu)

Käytä tämän opetusohjelman artikkelin **automatisoituja Automaattianalyysipalvelujen** luoda ja ottaa käyttöön Power BI binary ennusteen malli. Opetusohjelman sisältää ohjeita luomiseen Power BI-tietovirrassa ja käyttämällä entiteetit määritetty kouluttamaan ja koneoppimisen malli suoraan Power BI tarkistaa tietovirrassa. Sitten Käytämme mallin pisteiden predictions luomiseen.

Ensin sinun täytyy luoda Binary ennusteen koneoppimisen mallin optimoimiseen Osta tarkoitus online shoppers niiden online-istunnon määritteitä joukon perusteella. Tässä harjoituksessa käytetään benchmark tietokoneen oppimisen tietojoukon. Kun malli on harjoitettu, Power BI luo automaattisesti vahvistus-raportin, joka selittää mallin tulokset. Voit tarkistaa vahvistusraportti ja malli käyttöön tietojen pisteiden.

Tässä opetusohjelmassa sisältää seuraavat vaiheet:

> [!div class="checklist"]
> * Luo tietovirrassa syötteen tiedoilla
> * Luo ja kouluttamaan tietokoneen learning-malli
> * Tarkista mallin vahvistus-raportti
> * Käytä mallia tietovirrassa entiteettiin
> * Pisteytetyt tulos mallin käyttäminen Power BI-raporttiin

## <a name="create-a-dataflow-with-the-input-data"></a>Luo tietovirrassa syötteen tiedoilla

Tässä opetusohjelmassa ensimmäinen osa on luoda tietovirrassa syötteen tiedoilla. Että prosessi kestää muutaman vaiheen mukaisesti seuraavissa osioissa kuvataan, alkaen tietojen hankkiminen.

### <a name="get-data"></a>Nouda tiedot

Ensimmäinen vaihe tietovirrassa luominen on on valmis tietolähteisiin. Tässä tapauksessa Käytämme automaattianalyysipalvelujen tietojoukon online istuntoja, joista osa culminated oston joukosta. Tietojoukko sisältää joukon tietoja istuntoja, jota Käytämme-koulutus malliin määritteet.

Voit ladata tietojoukon Yksilöllisyyden Irvine-sivustossa.  Tarjoamme myös tämä saatavilla siihen opetusohjelmassa seuraavasta linkistä: [online_shoppers_intention.csv](https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv).

### <a name="create-the-entities"></a>Luo entiteetit

Jotta voit luoda entiteetit tietovirrassa, kirjaudu sisään Power BI -palveluun ja siirry varatun kapasiteettisi työtilaan, jossa AI-esikatselu on käytössä.

Jos sinulla ei vielä ole työtilan, voit luoda sellaisen valitsemalla **työtilat** Power BI-palveluun ja valitse vasemman siirtymisruudun-valikossa **Luo sovelluksen työtila** paneelin alareunasta, tulee näkyviin. Anna työtilan tiedot oikealla paneeli avautuu. Anna työtilan nimi ja valitse **lisäasetukset**. Vahvista, joilla työtilan varattua kapasiteettia käyttämällä valintanappi ja joka on määritetty varattua kapasiteettia esiintymään, joka on otettu käyttöön AI esikatselu. Valitse **Tallenna**.

![Luo työtila](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-01.png)

Kun työtila on luotu, voit valita **Ohita** alaosassa oikeassa aloitusnäytössä seuraavassa kuvassa esitetyllä tavalla.

![Ohita, jos sinulla on työtila](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-02.png)

Valitse **Dataflows (esikatselu)** välilehti. Valitse **Luo** yläreunassa oikealla työtilan ja valitse sitten **tietovirrassa**.

![Luo tietovirrassa](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-03.png)

Valitse **Lisää uudet entiteetit**. Tämä käynnistää **Power Query** editorin selaimessa.

![Lisää uudet entiteetit](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-04.png)

Valitse **teksti/CSV-tiedoston** tietolähteenä, näkyvät seuraavassa kuvassa.

![Valittu teksti/CSF-tiedosto](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-05.png)

- **Yhdistäminen tietolähteen** , joka tulee näkyviin seuraava, Liitä seuraavaa linkkiä *online_shoppers_intention.csv* into **tiedostopolku tai URL-osoite** ruutua ja valitse sitten  **Seuraava**.

`https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv`

![Tiedostopolku](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-06.png)

Power Query-editorin näyttää esikatselun tiedot CSV-tiedostosta. Valitse **muuntaa taulukon** komento valintanauhasta ja valitse sitten **Käytä ensimmäistä riviä otsikkoina** avautuvasta valikosta. Tämä lisää _korottaa otsikot_ kyselyn vaihetta **käytössä olevat vaiheet** osan näytön oikeassa reunassa. Voit nimetä uudelleen kyselyn mukavampi nimen arvo muuttamalla **nimi** box löytyvät oikeanpuoleisessa ruudussa. Voit esimerkiksi muuttaa kyselyn nimi _Online käyttäjä_.

![Muuta kutsumanimi](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-07.png)

Jotkin tämän tietojoukon määrite tietotyypit ovat _numeerinen_ tai _totuusarvo_, vaikka nämä merkkijonot, voidaan tulkita **Power Query**. Valitse yläreunan kutakin sarakeotsikkoa, voit muuttaa seuraaviin sarakkeet määrite tyyppi-kuvake:

* **Desimaaliluku:** Administrative_Duration; Informational_Duration; ProductRelated_Duration; BounceRates; ExitRates; PageValues; SpecialDay
* **Tosi/epätosi:** Viikonlopun; Tuotto

![Vaihda tietotyyppiä](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-08.png)

**Binary ennusteen** meidän kouluttamaan vaatii Boolean-kenttä selitteenä tunnistetaan viimeisten havainnot-tulokset. Tämän tietojoukon _tuotto_ määrite ilmaisee, osto, ja tämä määrite on jo käytettävissä totuusarvoksi. Siis meidän ei tarvitse lisätä lasketun sarakkeen nimen. Muihin tietojoukkoihin saatat joutua aiemmin otsikon määritteet Muunna Boolean-sarakkeeseen.

Valitse **valmis** Sulje Power Query-editori-painiketta. Tämä näyttää entiteettien luettelo, jossa _Online käyttäjät_ Olemme lisänneet tiedot. Valitse **Tallenna** oikeasta yläkulmasta Anna tietovirrassa nimi ja valitse sitten **Tallenna** valintaikkunan seuraavassa kuvassa esitetyllä tavalla.

![Tallenna tietovirrassa](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-09.png)

### <a name="refresh-the-dataflow"></a>Tietovuon päivittäminen

Tallentamista tietovirrassa tulokset näytetään ilmoituksen, jossa ilmoitetaan, että-tietovirrassa on tallennettu. Valitse **Päivitä nyt** -käyttöä tietolähteen tietoja tietovirrassa.

![Päivitä nyt](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-10.png)

Valitse oikeasta yläkulmasta **Sulje** ja odota, kunnes tietovuon päivitys on valmis.

Voit päivittää sovelluksesi tietovirrassa käyttämällä **toiminnot** komentoja. Tietovirrassa on aikaleima, kun päivitys on suoritettu.

![Päivitä aikaleima](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-11.png)

## <a name="create-and-train-a-machine-learning-model"></a>Luo ja kouluttamaan tietokoneen learning-malli

Kun päivitys on valmis, valitse tietovirrassa. Lisää tietokoneen oppimisen malli, valitse **koskevat ML mallin** painiketta **toiminnot** luettelo perusentiteetin, joka sisältää koulutus tiedot ja selitteen tiedot ja valitse sitten **Lisää tietokoneen oppimisen mallin**.

![Lisää koneoppimismalli](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-12.png)

Ensimmäinen vaihe luomiseen varatun oppimisen malliin on tunnistaa historialliset tiedot, mukaan lukien, jonka haluat ennusteen nimikenttä. Mallin luonut oppimisen näistä tiedoista.

Tietojoukko, jota Käytämme, tämä on **tuotto** kenttä. Valitse **tuotto** 'aiempien tulos kentän' arvo ja valitse sitten **seuraava**.

![Valitse historialliset tiedot](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-13.png)

Seuraava meidän täytyy valita koneoppimisen ja voit myös luoda tyyppiä. Power BI analysoi, jotka on määrittänyt liiketoimintatarpeen aiempien tulos kentän arvot ja ehdottaa tietokoneen oppimisen malleilla, jotka voidaan luoda optimoimiseen kentän tyypit.

Tässä tapauksessa, koska olemme olet korrelaatio binary tulos, onko käyttäjä tekee oston, tai ei, valitse **Binary ennusteen** mallityyppi ja valitse sitten Seuraava.

![Binary ennusteen valittuna](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-14.png)

Seuraavaksi Power BI ei alustava tarkistuksen tietojen ja ehdottaa, malli käyttää syötteitä. Voit halutessasi voit mukauttaa mallia käytetään syöttökenttiä. Valitse entiteetin nimen viereinen valintaruutu valitun tietojoukon, voit valita kaikki kentät. Valitse **seuraava** hyväksymään syötteitä.

![Seuraava valintaruutu](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-15.png)

Lopuksi voimme on annettava malliin nimi sekä tulokset, jota käytetään automaattisesti luotu raportissa, joka tekee yhteenvedon mallin tarkistuksen tulokset kutsumanimi otsikot. Seuraava Meillä on mallin nimi _Osta tarkoitus ennusteen_, ja kuin true ja false-otsikot _Osta_ ja _ei osta_. Valitse **Tallenna**.

![Tallenna malli](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-16.png)

Tietokoneen oppimisen malliin on nyt valmis koulutusta. Valitse **Päivitä nyt** Aloita koulutus mallia.

![Päivitä nyt](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-17.png)

Koulutusprosessi alkaa näytteenotto ja normalisoidaan historialliset tiedot ja jakaa tietojoukkosi kaksi uusia entiteettejä *tarkoitus ennusteen koulutus ostotietoja* ja *Osta tarkoitus ennusteen testaaminen Tietojen*.

Tietojoukon koosta riippuen koulutusprosessi voi kestää muutaman minuutin kuluttua kaksi tuntia. Tässä vaiheessa voit nähdä mallia **ihmis oppiminen mallien** välilehdessä tietovirrassa. _Valmis_ tila ilmaisee, että malli on asetettu jonoon koulutusta tai koulutus on.

![Valmis-koulutus](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-18.png)

Kun malli on koulutusta, et pysty voit tarkastella tai muokata tietovirrassa. Voit vahvistaa, että malli on harjoitettu ja vahvistaa tietovirrassa tilan kautta. Tämä näkyy tietojen päivitys on meneillään **Dataflows** työtilan välilehteen.

![Prosessin](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-19.png)

Kun mallin Harjoitus on valmis, tietovirrassa näyttää päivitetyn päivitysajankohta. Voit vahvistaa, että mallin harjoitettu, siirtymällä **ihmis oppiminen mallien** välilehden tietovirrassa. Mallin, jonka loit pitäisi näkyä tilan **Trained** ja **viimeisen koulutettua** aika nyt voi päivittää.

![Edellinen harjoittaminen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-20.png)

## <a name="review-the-model-validation-report"></a>Tarkista mallin vahvistus-raportti

Tarkastella mallia vahvistus-raportin **tietokoneen oppimisen malleja, s** käyttäjähakemistoon **suorituskyvyn raportin tarkasteleminen ja ota käyttöön mallin** painiketta **toiminnot** sarakkeen mallin . Tämän raportin kuvataan, miten tietokoneen oppimisen mallin todennäköisesti suorittamiseen.

- **Mallin suorituskyvyn** raportin, valitse sivun **avain Influencers** tarkastella yläreunan predictors mallin. Voit valita jonkin nähdäksesi, miten tulos jakauman liittyvät kyseisen predictor predictors.

![Mallin suorituskyky](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-21.png)

Voit määrittää **todennäköisyys raja-arvon** osittajan mallin suorituskyvyn sivulla tutkia sen vaikutus tarkkuus- ja peruuttaminen mallille.

![Todennäköisyyden raja-arvo](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-22.png)

Raportin muilla sivuilla kuvataan tilastoanalyysit suoritusmittaukset mallille.

Raportti sisältää myös koulutus tietosivu, joka kuvaa eri iterointia, joka on suoritettu, miten ominaisuudet olivat poiminut syötteitä ja käyttää lopullisen mallin hyperparameters.

## <a name="apply-the-model-to-a-dataflow-entity"></a>Käytä mallia tietovirrassa entiteettiin

Valitse **Käytä mallin** käynnistämiseen tätä mallia, kun tietovirrassa päivitetään raportin yläreunassa. - **Käytä** valintaikkunan, voit määrittää kohde-entiteetti, jonka lähdetietoja, joihin mallia käytetään.

![Käytä mallia](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-23.png)

Pyydettäessä on **Päivitä** esikatselu mallin tulokset tietovirrassa.

Malli on otettu käyttöön luodaan uusi entiteetti jälkiliite **rikastettua < mallin_nimi >** entiteetin, joihin sovelletaan mallin liitetään. Tässä tapauksessa on otettu käyttöön mallin **OnlineShoppers** entiteettiin Luo **OnlineShoppers rikastettua Osta tarkoitus ennusteen**, joka sisältää ennustettu tulos mallista.

Binary ennusteen malli on otettu käyttöön lisää kolme saraketta, joiden ennustettu tulos ja yläreunan tietueen tiettyjen influencers, ennusteen todennäköisyys pistemäärä, jokainen etuliitteeksi määritetyn sarakkeen nimen.

![Kolmen sarakkeen tuloksesta](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-24.png)

Tunnemme ongelman vuoksi pisteytetyt tulostesarakkeet rikastetun entiteetissä ovat vain Power BI Desktop voi käyttää. Voit esikatsella nämä palvelussa, sinun on käytettävä erityinen esikatselu-entiteetti.

Kun tietovirrassa päivitys on valmis, voit valita **OnlineShoppers rikastettua Osta tarkoitus ennusteen esikatselu** entiteetin tulokset.

![Näytä tulokset](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-25.png)

## <a name="using-the-scored-output-from-the-model-in-a-power-bi-report"></a>Pisteytetyt tulos mallin käyttäminen Power BI-raporttiin

Pisteytetyt tulos-koneoppimisen mallin käyttöön voit muodostaa yhteyttä tietovirrassa Power BI Desktopista, Dataflows-yhdistimen käyttäminen. **OnlineShoppers rikastettua Osta tarkoitus ennusteen** entiteetin nyt voidaan sisällyttää predictions mallin Power BI-raporteissa.

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä opetusohjelmassa luodaan ja otetaan binary ennusteen malli Power BI-seuraavasti:

* Luo tietovirrassa syötteen tiedoilla
* Luo ja kouluttamaan tietokoneen learning-malli
* Tarkista mallin vahvistus-raportti
* Käytä mallia tietovirrassa entiteettiin
* Pisteytetyt tulos mallin käyttäminen Power BI-raporttiin

Katso lisätietoja Power BI-Koneoppimisen automation [Automaattianalyysipalvelujen automatisoituja Power BI (esikatselu)](service-machine-learning-automated.md).
