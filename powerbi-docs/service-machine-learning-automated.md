---
title: Automaattianalyysipalvelut Power BI:ssä (esikatselu)
description: Opi käyttämään Power BI automatisoituja Automaattianalyysipalvelujen (AutoML)
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/02/2019
ms.author: davidi
LocalizationGroup: conceptual
ms.openlocfilehash: 894e92687a6283ce71b253bd4dc635aca0c4673f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61236452"
---
# <a name="automated-machine-learning-in-power-bi-preview"></a>Automaattianalyysipalvelut Power BI:ssä (esikatselu)

Automaattinen koneoppimisen (AutoML)-dataflows avulla liiketoiminta-analyytikkojen kouluttamaan, Vahvista ja Koneoppiminen malleja suoraan Power BI-kutsu. Se sisältää yksinkertainen kokemus uusi ML-malli, jossa analyytikot avulla voit määrittää syötteen tiedot harjoitetaan mallin niiden dataflows luomiseen. Palvelun automaattisesti poimii tärkeimpiin ominaisuuksiin, asianmukainen algoritmi valitsee säätää ja vahvistaa ML-malli. Sen jälkeen, kun malli on harjoitettu, Power BI luo automaattisesti raportin, joka sisältää tulokset vahvistuksen, jossa kerrotaan suorituskykyä ja analyytikot tulokset. Mallin voi käynnistää sitten kaikkien uusien tai päivitettyjen tietojen sisällä tietovirrassa.

![Tietokoneen learning-näyttö](media/service-machine-learning-automated/automated-machine-learning-power-bi-01.png)

Automaattinen automaattianalyysipalvelujen on käytettävissä, joita isännöidään vain Power BI Premium ja upotettujen kapasiteettien dataflows. Tämä esikatselu AutoML avulla voit kouluttamaan tietokoneen learning-mallien Binary ennusteen luokitus ja Regression malleille.

## <a name="working-with-automl"></a>AutoML käsitteleminen

[Power BI dataflows](service-dataflows-overview.md) tarjouksen omatoimista tietojen prep suuri tiedoille. AutoML avulla voit hyödyntää tiedot-valmistelutyökalun vaivaa luomiseen tietokoneen oppimisen malleja suoraan Power BI sisällä.

Power BI AutoML avulla tietoanalyytikot dataflows avulla voit rakentaa tietokoneen learning-tietomalleja yksinkertaistettu käytettävyyttä, vain Power BI-osaamistasi. Power BI automaattinen takana ML mallit luomisen datatiede useimmat guardrails Varmista, että tuotti malli on hyvä laadun ja näkyvyyden ja toimittaa koko merkityksellisiä tietoja ML mallin luomiseen käytetyn kanssa.

AutoML tukee luonnin **Binary ennusteen**, **luokitus**, ja **Regression** dataflows malleja. Nämä ovat valvotussa tietokoneen oppimisen malleja, mikä tarkoittaa sitä, että ne Lue viimeisten huomautuksia ennusteen muut havainnot tulokset tunnetut tulokset. Syötteen tietojoukon harjoitetaan AutoML mallia on joukko tietueita, jotka **otsikko** tunnetut tulokset kanssa.

AutoML Power BI integroituu [automatisoituja ML](https://docs.microsoft.com/azure/machine-learning/service/concept-automated-ml) - [Azuren Automaattianalyysipalvelujen service](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml) ML-mallien luomiseen. Et tarvitse kuitenkin AutoML käyttäminen Power BI Azure-tilausta. Koulutus-ja isännöinti ML mallit hallitsee kokonaan Power BI-palvelussa.

ML-malli on harjoitettu, kun AutoML luodaan automaattisesti Power BI-raportin, jossa kerrotaan ML-malliin todennäköisesti suorituskyvyn. AutoML korostaa explainability, korostamalla avaimen influencers antamiesi, jotka vaikuttavat mallin palauttama predictions kesken. Raportti sisältää myös mittareita mallin ML mallin tyypin mukaan.

Luodun raportin muilla sivuilla Näytä yhteenvedossa mallin ja koulutus-tiedot. Tilastoanalyysit yhteenveto on merkitystä käyttäjille, jotka haluaisit nähdä Vakiotiedot tieteelliset mittayksiköt mallin suorituskyvyn. Koulutus-tiedot yhteenvedon, jotka liittyvät mallinnus-parametrien kanssa mallin luomiseen suorittamisessa oli iterointia. Se myös kuvataan miten ML-mallin luomiseen käytetyn Jokainen syöte.

Voit sitten käyttää ML mallin pisteiden tietojen. Kun tietovirrassa päivitetään, Koneoppiminen mallin predictions otetaan automaattisesti käyttöön tietoihisi. Power BI sisältää myös kunkin tietyn ennusteen pistemäärä, joka tuottaa ML-mallin yksilölliset selitys.

## <a name="creating-a-machine-learning-model"></a>Tietokoneen learning-mallin luominen

Tässä osassa kuvataan AutoML-oppimisen mallin luomiseen. 

### <a name="data-prep-for-creating-an-ml-model"></a>Tietojen Valmistaudu ML-mallin luominen

Tietokoneen oppimisen mallin luominen Power BI-, sinun on ensin luotava tietovirrassa tietojen aiempien tulos tiedot, jota käytetään harjoitetaan ML-mallia. Määrittämisestä-tietovirrassa lisätietoja [Omatoiminen tietojen valmistautuminen Power BI](service-dataflows-overview.md).

Nykyinen versio Power BI käyttää vain yksittäisen entiteetin tiedot ML mallia kouluttamaan. Joten jos historialliset tiedot koostuu useita entiteettejä, manuaalisesti Liitä tiedot yhteen tietovirrassa entiteettiin. Tulee myös lisätä minkä tahansa liiketoiminnan mittareita, jotka voi olla tulos ennusteen yrität strong predictors laskettuja sarakkeita.

AutoML on tiettyjä tietoja koskevat harjoitetaan koneoppimisen mallin. Nämä vaatimukset on kuvattu seuraavissa osioissa, asianmukainen malli-tyyppien perusteella.

### <a name="configuring-the-ml-model-inputs"></a>ML mallin syötteitä määrittäminen

Luo AutoML-malli, valitse ML-kuvaketta **toiminnot** sarakkeen tietovirrassa entiteetin historialliset tiedot ja valitse **Lisää tietokoneen learning-malli**.

![Lisää tietokoneen learning-malli](media/service-machine-learning-automated/automated-machine-learning-power-bi-02.png)

Yksinkertaistettu kokemus käynnistetään muodostuu ohjatun toiminnon, joka opastaa ML-mallin luomista. Ohjattu sisältää yksinkertainen seuraavasti.

1. Valitse entiteetti, jolla aiempien tulos tiedot ja haluamasi kenttä, jonka ennusteen
2. Valitse mallityyppi, jotka haluat nähdä ennusteen tyypin perusteella
3. Valitse haluamasi malli käyttää ennakoivan signaalit syötteet
4. Mallin nimi ja Tallenna määrityksesi

Aiempien tulos-kenttä sisältää nimen määritteelle koulutus ML mallin, seuraavassa kuvassa.

![Valitse tiedot aiempien tulos](media/service-machine-learning-automated/automated-machine-learning-power-bi-03.png)

Kun määrität aiempien tulos-kenttä, AutoML analysoi ML malleilla, jotka voivat koulutettava tiedot analysoimalla nimitiedot ja ehdottaa todennäköisesti ML mallityyppi, joka voi harjoitettu. 

> [!NOTE]
> Mallin joitain tietotyyppejä ei välttämättä tueta tietoja, jotka olet valinnut.

AutoML analysoi myös kaikki valitun entiteetin ehdottaa syötteitä, joka voi käyttää harjoitetaan ML-mallin kentät. Tämä prosessi on arvioitu ja perustuu tilastoanalyysi, joten Tarkista käyttää syötteitä. Syötteitä, jotka ovat riippuvaisia aiempien tulos kenttää (tai nimikenttä) ei voi käyttää harjoitetaan ML-mallia, koska ne vaikuta suorituskykyyn.

![Mukauta syötekenttiä](media/service-machine-learning-automated/automated-machine-learning-power-bi-04.png)

Viimeisessä vaiheessa voit nimetä mallin ja tallentaa sen asetuksia.

Sinua kehotetaan Päivitä tietovirrassa, joka alkaa ML mallin koulutusprosessin tässä vaiheessa.

### <a name="ml-model-training"></a>ML mallin Harjoitus

Koulutus AutoML mallien on osa päivityksen tietovirrassa. AutoML valmistelee ensin tiedot-koulutus.

AutoML jakaa historiatietojen annat koulutuksen ja testaus tietojoukkoja. Test-tietojoukko on pidätyksen, jota käytetään mallin suorituskyvyn jälkeen koulutus vahvistetaan. Nämä ovat hyödyntäneet kuin **koulutusta ja testaus** entiteettejä tietovirrassa. AutoML käyttää ristiintarkistuksen mallin vahvistusta varten.

Seuraavaksi syötteen kunkin kentän analysoidaan ja huomioon ottaminen käytetään, joka korvaa korvaava arvot puuttuvat arvot. Muutamalla eri huomioon ottaminen strategioiden käytetään AutoML. Pakollinen näytteenotto ja normalisoiminen käytetään sitten tietojasi.

AutoML koskee useita muunnokset ovat kukin valittu syötteen kenttä tietotyypiksi ja sen tilastoanalyysit ominaisuuksien perusteella. AutoML käyttää näitä muunnoksia käytettäväksi harjoitetaan ML mallin ominaisuuksia.

Koulutusprosessin AutoML malleille koostuu enintään 50 iterointien eri mallinnus algoritmit ja löytää mallin, jonka parhaan suorituskyvyn hyperparameter asetukset. Kaikkien näiden mallien lisäksi arvioidaan vahvistus pidätyksen test tietojoukon kanssa. Koulutus tässä vaiheessa AutoML Luo useita jaksojen koulutus-ja vahvistuksen nämä iterointia. Arvioidaan mallit suorituskykyä voi kestää ajan, missä tahansa kaksi tuntia tietojoukko ja varattua kapasiteettia käytettävissä olevien koosta riippuen useita minuutteja.

Joissakin tapauksissa luodaan lopullisen mallin saa käyttää ensemble oppimiseen, jossa käytetään useiden mallien toimittaa paremmin ennakoivan suorituskyvyn.

### <a name="automl-model-explainability"></a>AutoML mallin explainability

Sen jälkeen, kun malli ole harjoitettu, AutoML analysoi syötteen ominaisuuksia ja mallin tulos välisen suhteen. Sopimuksen merkityksellisiin moninkertaisesti ja mallin tulos pidätyksen test tietojoukon kullekin syötteen ominaisuudelle muutos suuntaa. Tätä kutsutaan *toiminto tärkeä*.

![Ominaisuus tärkeys](media/service-machine-learning-automated/automated-machine-learning-power-bi-05.png)

### <a name="automl-model-report"></a>AutoML raportti

AutoML Luo Power BI-raportin, joka tekee yhteenvedon suorituskyvyn mallin vahvistuksen ja Yleinen ominaisuus tärkeyden aikana. Raportti sisältää yhteenvedon käyttöön ML-mallin pidätyksen testitiedot ja predictions tunnetut tulos arvoilla vertaillaan tuloksista.

Voit tarkastella mallia raportin Ymmärtääksesi sen suorituskyvyn. Voit myös varmistaa, että mallin avaimen influencers Tasaa business-merkityksellisiä tietoja tunnetuista tulokset.

Kaavioiden ja mittayksiköitä käytetään kuvaamaan sitä, mallin suorituskyvyn raportin riippuu mallin. Seuraavissa osissa kuvataan nämä suorituskyvyn kaavioita ja mittayksiköt.

Raportin muita sivuja kuvaus tilastoanalyysit mittayksiköt tietoja mallin tietojenkäsittelytieteen näkökulmasta. Esimerkiksi **Binary ennusteen** raportti sisältää voitto kaavion ja OHJETIEDOSTO käyrän mallille.

Raportit sisältävät myös **koulutus tiedot** sivun, joka sisältää kuvaus ja miten mallin oli harjoitettu kuvaavat mallin suorituskyvyn päälle iterointien on kaavio suoritetaan.

![Harjoitustiedot](media/service-machine-learning-automated/automated-machine-learning-power-bi-06.png)

Tällä sivulla toinen osassa kuvataan, miten huomioon ottaminen menetelmää käyttää täyttämiseen syöttökenttiä, puuttuvat arvot myös ja miten syötteen kunkin kentän muunnettiin poimia mallin käytetyt ominaisuudet. Se sisältää myös lopullisen malli käyttää parametreja.

![Lisätietoja mallin](media/service-machine-learning-automated/automated-machine-learning-power-bi-07.png)

Jos tuotti malli käyttää ensemble kursseja, myös **koulutus tiedot** sivulla on myös osa, joka kuvaa kunkin tuotteen mallissa ensemble sekä sen parametreja leveys.

![Painoarvo ensemble](media/service-machine-learning-automated/automated-machine-learning-power-bi-08.png)

## <a name="applying-the-automl-model"></a>AutoML malli on otettu käyttöön

Jos olet tyytyväinen suorituskyvyn ML-mallin, joka on luotu, voit käyttää sitä uusien tai päivitettyjen tietojen, kun-tietovirrassa päivitetään. Voit tehdä tämän mallin raportista, valitsemalla **Käytä** painiketta oikeassa yläkulmassa.

ML-mallin käyttöön sarakkeita, jotka lisätään tähän entiteettiin mallin output-entiteetti, johon se on otettava käyttöön ja etuliitteen nimi on määritettävä. Sarakkeiden nimien oletusarvoinen etuliite on mallinimi. *Käytä* funktio saa lisäparametrit mallin tyyppiin.

ML-malli on otettu käyttöön Luo uuden entiteetin tietovirrassa jälkiliite **rikastettua < mallin_nimi >** . Esimerkiksi jos käytät _PurchaseIntent_ -malliin _OnlineShoppers_ entiteetin tulos luodaan automaattisesti **OnlineShoppers rikastettua PurchaseIntent**.

Tällä hetkellä output-entiteetti ei voi käyttää esikatselu ML mallin tulokset Power Query-editorissa. Näytettävät sarakkeet näyttävät aina null tuloksena. Voit tarkastella tuloksia sekunnin tuloksena entiteetti, jolla jälkiliite **rikastettua < mallin_nimi > esikatselu** luodaan, kun malli on käytössä.

Sinun on päivitettävä tietovirrassa Esikatsele tuloksia Kyselyeditorissa.

![Kyselyeditori](media/service-machine-learning-automated/automated-machine-learning-power-bi-09.png)

Kun otat käyttöön mallin, AutoML aina pitää yhteyttä predictions ajan tasalla kun tietovirrassa päivitetään.

AutoML sisältää myös yksilölliset selitys kullekin riville, se pisteyttää output-entiteetissä.

Käyttämään merkityksellisiä tietoja ja Koneoppiminen mallista predictions Power BI-raportin, voit muodostaa yhteyden output-entiteettiin käyttämällä Power BI Desktop **dataflows** connector.

## <a name="binary-prediction-models"></a>Binary ennusteen mallit

Binary ennusteen malleja, Lisää virallisesti kutsutaan **binaariluokitus mallien**, käytetään luokitella tietojoukon kahteen ryhmään. Niitä käytetään ennusteen tapahtumia, jotka voivat binary tulos, kuten onko myyntimahdollisuuden muuntaa, onko tili churn, onko laskun kiinnitetään aikaan. onko tapahtuman toimet ja niin edelleen.

Koska tulos on binary, Power BI odottaa oltava totuusarvo, jolla on merkitty tunnettuja tulokset binary ennusteen mallin nimen **true** tai **false**. Esimerkiksi myyntimahdollisuuden muuntaminen mallissa, mahdollisuudet, jotka ovat voittaneet merkitty true, ne, jotka on menetetty merkitty false ja avoimet mahdollisuudet merkitty null.

Binary ennusteen mallin tulos on probability-arvo, joka tunnistaa, että tulos on true selite-arvoa vastaavan saavutetaan todennäköisyyttä.

### <a name="training-a-binary-prediction-model"></a>Harjoitetaan Binary ennusteen mallia

Binary ennusteen mallin luominen koulutus tiedot sisältävä syötteen entiteetin on oltava Boolean-kenttä tunnistamiseen viimeisten tunnetut tulokset aiempien tulos-kentäksi.

Edellytyksiä:

* Boolean-kenttä on käytettävä aiempien tulos-kenttä
* Vähintään 50 riviä historiatietojen vaaditaan jokaisesta tulokset

Yleensä, jos viimeisten tulokset tunnistetaan eri tietotyypiksi kentät, voit lisätä nämä käyttämällä Power Query totuusarvoksi muunnettava lasketun sarakkeen.

Prosessin luonti-Binary ennustemalli noudattaa samaa vaiheet kuin muut AutoML malleja, osassa **määrittäminen ML mallin syötteitä** yläpuolella.

### <a name="binary-prediction-model-report"></a>Binary ennusteen raportti

Binary ennustemalli tuottaa lähtökohdaksi, että tietueen saavuttaa arvoksi True totuusarvo otsikon-arvon määrittämät tulos todennäköisyys. Raportti sisältää todennäköisyys raja-arvo, joka vaikuttaa pisteet ylä- ja todennäköisyys raja-arvon tulkinnassa osittajan.

Raportin kuvaa mallin sekä suorituskykyä *True positiivisten*, *tunnistettujen*, *True negatiiviset* ja *suorittaa*. TRUE positiivisten ja True negatiiviset ovat oikein ennustettu tulokset tulos tietojen kaksi luokkia. Tunnistettujen ovat tulokset, jotka oli todellinen totuusarvo nimen arvon False, mutta on ennustaa tosi. Vastaavasti suorittaa ovat tuloksia missä todellinen totuusarvo otsikon arvo on tosi (TRUE), mutta on ennustaa arvoa EPÄTOSI.

Mittaa, kuten tarkkuus- ja peruuttaminen, kuvaavat todennäköisyys raja-arvon vaikutus-ennustettu tulokset. Voit valita raja-arvo, joka kertyy Tasapainotettu haavoittuvan tarkkuus – peruuttaminen osittajasta todennäköisyys raja-arvo.

![Tarkkuus-esikatselu](media/service-machine-learning-automated/automated-machine-learning-power-bi-10.png)

**Tarkkuutta raportin** mallin raportin sivu sisältää *kertyneet voitot* kaavion ja OHJETIEDOSTO käyrä mallille. Nämä ovat tilastoanalyysit mittayksiköt mallin suorituskyvystä. Raportit sisältävät näytetään kaaviot kuvaukset.

![Raportin näytön tarkkuus](media/service-machine-learning-automated/automated-machine-learning-power-bi-11.png)

### <a name="applying-a-binary-prediction-model"></a>Binary ennusteen malli on otettu käyttöön

Käytä Binary ennustemalli on määritettävä entiteetti, johon haluat käyttää ML mallista predictions tiedoilla. Muut parametrit ovat output-sarakkeen nimen etuliite ja todennäköisyys kynnysarvon luokittelusta ennustettu tulos.

![Ennusteen syötteet](media/service-machine-learning-automated/automated-machine-learning-power-bi-12.png)

Kun käytetään Binary ennusteen-mallin, se Lisää kolme sarakkeiden rikastetun output-entiteettiin. Nämä ovat **PredictionScore**, **PredictionOutcome** ja **PredictionExplanation**. Entiteetin sarakkeiden nimet on määritetty malli on käytetty etuliite.

**PredictionOutcome** sarake sisältää ennustettu tulos nimen. Tietueet, joissa on suurempi kuin raja-arvon kokonaismuutos on ennustaa kuin todennäköistä tulos, ja ne alla ovat kuin todennäköisesti saavuta tulos ennusteen.

**PredictionExplanation** sarake sisältää selitys kanssa, joka oli syötteen ominaisuuksia tietyn vaikutus **PredictionScore**. Tämä on muotoiltu JSON-kokoelma painoarvoja ennusteen syötteen ominaisuuksia.

## <a name="classification-models"></a>Luokitus-mallit

Luokitus-malleja käytetään luokittelemaan tietojoukon useita ryhmiä tai luokkia.  Niitä käytetään ennusteen tapahtumia, jotka voi olla yksi tai useita mahdollista Tulosta, kuten onko asiakas todennäköisesti erittäin suuri, suuri, Normaali tai pieni elinkaaren arvo; onko riski on oletusarvo on suuri, keskitaso, pieni tai erittäin pieni ja niin edelleen.

Luokitus-mallin tulos on probability-arvo, joka tunnistaa, että tietueen saavuttaa tietyn luokan ehdot todennäköisyyttä.

### <a name="training-a-classification-model"></a>Harjoitetaan luokitus-mallia

Koulutus luokitus-mallin tiedot sisältävä syötteen entiteetillä on oltava merkkijono tai numeerisen kentän aiempien tulos-kentäksi, joka tunnistaa viimeisten tunnetut tulokset.

Edellytyksiä:

* Vähintään 50 riviä historiatietojen vaaditaan jokaisesta tulokset

Prosessin luonti-luokitus-mallin noudattaa samaa vaiheet kuin muut AutoML malleja, osassa **määrittäminen ML mallin syötteitä** yläpuolella.

### <a name="classification-model-report"></a>Mallin raportti

Mallin raportin tuotetaan soveltamalla ML-mallin pidätyksen luokitus Testaa tietoja ja vertaamalla ennustettu luokka tietueen todellinen tunnetut luokka.

Mallin raportti sisältää kaavio, joka sisältää oikein ja virheellisesti luokitellun tietueet tunnetut jokaisesta jakautuminen.

![Raportti](media/service-machine-learning-automated/automated-machine-learning-power-bi-13.png)

Luokka-kohtaiset siirtyminen avulla analyysi miten tunnetut luokalle predictions jaetaan. Tämä sisältää luokat, jossa tietueet, joiden havaittu luokan todennäköisesti voi luokitelluista.

![Analyysiraportti](media/service-machine-learning-automated/automated-machine-learning-power-bi-14.png)

Mallin selitys raportin sisältää myös yläreunan predictors kullekin luokalle.

Luokitus mallin raportti sisältää myös muiden sivujen koulutus tiedot sivulle, osiossa kuvatulla **AutoML mallin raportin** tämän artikkelin aiemmassa osassa.

### <a name="applying-a-classification-model"></a>Luokitus-malli on otettu käyttöön

Entiteetti on määritettävä syötetietojen ja output-sarakkeen nimen etuliite, luokitus ML-mallin käyttöön.

Kun käytetään luokitus-mallin, se Lisää kolme Näytä sarakkeet rikastetun output-entiteettiin. Nämä ovat **PredictionScore**, **PredictionClass** ja **PredictionExplanation**. Entiteetin sarakkeiden nimet on määritetty malli on käytetty etuliite.

**PredictionClass** sarake sisältää tietueen todennäköisesti ennustettu luokka. **PredictionScore** sarake sisältää todennäköisyys pisteet mahdollista jokaisesta tietueen luettelo.

**PredictionExplanation** sarake sisältää selitys kanssa, joka oli syötteen ominaisuuksia tietyn vaikutus **PredictionScore**. Tämä on muotoiltu JSON-kokoelma painoarvoja ennusteen syötteen ominaisuuksia.

## <a name="regression-models"></a>Regressio mallit

Regressio mallit ovat käyttää arvon, kuten todennäköisesti toteutunut myynti kaupan, elinkaaren arvo tilin, saatavien laskun, jotka saattavat olla tarkkana, päivämäärä, jolloin laskun saattaa maksaa määrä tuotto , ja niin edelleen.

Regression-mallin tulos on ennustetun arvon.

### <a name="training-a-regression-model"></a>Harjoitetaan regressiomallia

Koulutus tiedot Regression mallin sisältävän syötteen entiteetillä on oltava numeerinen kenttä aiempien tulos-kentäksi, joka tunnistaa tunnetut tulos aiempiin arvoihin.

Edellytyksiä:

* Vähintään 100 riviä historiatietojen vaaditaan Regression mallille

Prosessin luonti-Regression-mallin noudattaa samaa vaiheet kuin muut AutoML malleja, osassa **määrittäminen ML mallin syötteitä** yläpuolella.

### <a name="regression-model-report"></a>Regressio raportti

Muut AutoML mallin raportit, kuten Regression-raportti perustuu mallin kohdistaminen pidätyksen testitiedot tuloksista.

Mallin raportti sisältää kaavio, jossa verrataan ennustettuja arvoja arvolla. Tässä kaaviossa alas etäisyyden ilmaisee ennusteen virhe.

Jättämän virhe kaavio näyttää eri arvot keskimääräinen virhe prosenttiosuus jakautuminen pidätyksen test tietojoukossa. Vaaka-akselin edustaa todellinen arvo ryhmän keskiarvo näytetään taajuus tai arvojen määrän, jotka kuplan koon. Pystyakselin on keskimääräinen jättämän virhe.

![Jättämän virhe kaavio](media/service-machine-learning-automated/automated-machine-learning-power-bi-15.png)

Regressio mallin raportti sisältää myös koulutus tietosivu mallin muuntyyppisten raporttien tapaan, osiossa kuvatulla **AutoML mallin raportin** yläpuolella.

### <a name="applying-a-regression-model"></a>Regressio malli on otettu käyttöön

Entiteetti on määritettävä syötetietojen ja output-sarakkeen nimen etuliite, Regression ML-mallin käyttöön.

![Käytä regression](media/service-machine-learning-automated/automated-machine-learning-power-bi-16.png)

Kun käytetään Regression-mallin, se lisää kaksi sarakkeiden rikastetun output-entiteettiin. Nämä ovat **PredictionValue**, ja **PredictionExplanation**. Entiteetin sarakkeiden nimet on määritetty malli on käytetty etuliite.

**PredictionValue** sarake sisältää tietueen syötteen kenttien mukaan ennustetun arvon. **PredictionExplanation** sarake sisältää selitys kanssa, joka oli syötteen ominaisuuksia tietyn vaikutus **PredictionValue**. Tämä on muotoiltu JSON-kokoelma painoarvoja syötteen ominaisuuksia.

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä artikkelissa antaa yhteenvedon automatisoituja koneoppimisen Dataflows Power BI-palvelussa. Seuraavissa artikkeleissa voi myös olla hyötyä.

* [Opetusohjelma: Luo Automaattianalyysipalvelujen malli Power BI (esikatselu)](service-tutorial-build-machine-learning-model.md)
* [Opetusohjelma: Kognitiivisten palvelujen käyttö Power BI:ssä](service-tutorial-use-cognitive-services.md)
* [Opetusohjelma: Automaattianalyysistudion mallin käynnistys Power BI:ssä (esikatselu)](service-tutorial-invoke-machine-learning-model.md)
* [Kognitiiviset palvelut Power BI:ssä (esikatselu)](service-cognitive-services.md)
* [Azuren automaattianalyysipalveluiden integroiminen Power BI:hin (esikatselu)](service-machine-learning-integration.md)

Lisätietoja tietovoista on seuraavissa artikkeleissa:
* [Tietovoiden luominen ja käyttäminen Power BI:ssä](service-dataflows-create-use.md)
* [Laskettuja entiteettejä käyttämällä Power BI Premium](service-dataflows-computed-entities-premium.md)
* [Dataflows käyttö paikallisiin tietolähteisiin](service-dataflows-on-premises-gateways.md)
* [Power BI dataflows Kehittäjien resurssit](service-dataflows-developer-resources.md)
* [Tietovuot ja Azure Data Lake -integrointi (esikatselu)](service-dataflows-azure-data-lake-integration.md)


