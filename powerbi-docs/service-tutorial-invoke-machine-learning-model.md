---
title: 'Opetusohjelma: Automaattianalyysistudion mallin käynnistys Power BI:ssä (esikatselu)'
description: Tässä opetusohjelmassa käynnistetään automaattianalyysistudion malli Power BI:ssä.
author: davidiseminger
manager: kfile
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 03/12/2019
ms.author: davidi
LocalizationGroup: Connect to services
ms.openlocfilehash: 368f860ed064cf3b4ff73496db1fa993fd3b716a
ms.sourcegitcommit: 8cc2b7510aae76c0334df6f495752e143a5851c4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/01/2019
ms.locfileid: "73432217"
---
# <a name="tutorial-invoke-a-machine-learning-studio-model-in-power-bi-preview"></a>Opetusohjelma: Automaattianalyysistudion mallin käynnistys Power BI:ssä (esikatselu)

Tässä opetusohjelmassa käymme läpi merkityksellisten tietojen sisällyttämisen **Azuren automaattianalyysistudio** -mallista Power BI:hin. Opetusohjelma sisältää ohjeita siitä, miten Power BI -käyttäjälle myönnetään käyttöoikeus Azuren automaattianalyysipalveluiden malliin, kuinka tietovirta luodaan ja kuinka Azuren automaattianalyysipalveluiden mallin merkityksellisiä tietoja käytetään omassa tietovuossa. Opetusohjelmassa on myös viite Azuren automaattianalyysipalveluiden mallin luonnin pikaoppaaseen, jos sinulla ei vielä ole mallia.

Opetusohjelmassa on seuraavat vaiheet:

> [!div class="checklist"]
> * Azuren automaattianalyysipalveluiden mallin luominen ja julkaiseminen
> * Mallin käyttöoikeuksien myöntäminen Power BI -käyttäjälle
> * Tietovirran luominen
> * Azuren automaattianalyysipalveluiden mallin merkityksellisten tietojen lisääminen tietovirtaan

## <a name="create-and-publish-an-azure-ml-model"></a>Azuren automaattianalyysipalveluiden mallin luominen ja julkaiseminen

Noudata ohjeita kohdassa [Ohjeiden vaihe 1: Luo automaattianalyysistudion työtila](https://docs.microsoft.com/azure/machine-learning/studio/walkthrough-1-create-ml-workspace) -kohdan ohjeita ja luo **Automaattianalyysipalvelut**-työtila.

Voit käyttää näitä vaiheita minkä tahansa valmiin Azuren automaattianalyysipalveluiden mallin tai tietojoukon kanssa. Jos sinulla ei ole julkaistua mallia, voit luoda mallin hetkessä katsomalla ohjeet [Luo ensimmäinen datatiedekokeilu Azuren automaattianalyysistudiossa](https://docs.microsoft.com/azure/machine-learning/studio/create-experiment) -artikkelista, jossa määritetään Azuren automaattianalyysipalveluiden malli autojen hintaennusteita varten.

Noudata artikkelissa [Azuren Automaattianalyysistudio -verkkopalvelun käyttöönotto](https://docs.microsoft.com/azure/machine-learning/studio/publish-a-machine-learning-web-service) olevia ohjeita ja julkaise Azuren Automaattianalyysistudio -malli verkkopalveluna.

## <a name="grant-a-power-bi-user-access"></a>Käyttöoikeuden myöntäminen Power BI -käyttäjälle

Jotta voisit käsitellä Azuren Automaattianalyysistudio-mallia Power BI:stä käsin, tarvitset **luku**oikeuden Azure-tilaukseen ja -resurssiryhmään sekä **luku**oikeuden Azuren Automaattianalyysistudio -verkkopalveluun Automaattianalyysistudio-malleja varten.  Azuren automaattianalyysipalveluiden mallia varten tarvitset **luku**oikeuden Automaattianalyysipalvelu-työtilaan.

Seuraavissa vaiheissa oletetaan, että olet sen Azure-tilauksen ja -resurssiryhmän rinnakkaisjärjestelmänvalvoja, johon malli on julkaistu.

Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com) ja siirry **Tilaukset**-sivulle, jonka voit etsiä käyttämällä vasemmanpuoleisen valikon **Kaikki palvelut** -luetteloa.

![Azure-portaali](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_01.png)

Valitse Azure-tilaus, jota käytit mallin julkaisemiseen, ja valitse sitten **Käyttöoikeuksien hallinta (IAM)** . Valitse **Lisää roolimääritys**, valitse **Lukija**-rooli ja valitse sitten Power BI -käyttäjä. Kun olet valmis, valitse **Tallenna**. Valinnat näkyvät seuraavassa kuvassa.

![Azure-portaalin Käyttöoikeuksien hallinta](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_02.png)

Toista sitten yllä olevat vaiheet ja myönnä Power BI -käyttäjälle **Osallistuja**-roolin käyttöoikeudet siihen Automaattianalyysipalvelujen verkkopalveluun, jossa Azuren automaattianalyysimalli on otettu käyttöön.

## <a name="create-a-dataflow"></a>Tietovirran luominen

### <a name="get-data-for-creating-the-dataflow"></a>Tietojen noutaminen tietovirran luomista varten

Kirjaudu sisään Power BI -palveluun käyttämällä niitä käyttäjän tunnistetietoja, joille edellisessä vaiheessa myönsit Azuren automaattianalyysipalveluiden mallin käyttöoikeuden.

Tässä vaiheessa oletetaan, että tiedot, joita haluat käyttää Azuren automaattianalyysipalveluiden mallissa, ovat CSV-muodossa.  Jos olet luonut mallin automaattianalyysistudiossa käyttämällä **kokeellista autojen hinnoittelua**, tietojoukko on jaettu seuraavassa linkissä:

* [Azuren automaattianalyysistudion esimerkkimalli](https://github.com/santoshc1/PowerBI-AI-samples/blob/master/Tutorial_MLStudio_model_integration/Automobile%20price%20data%20_Raw_.csv)

### <a name="create-a-dataflow"></a>Tietovirran luominen

Jotta voit luoda entiteetit tietovirrassa, kirjaudu sisään Power BI -palveluun ja siirry varatun kapasiteettisi työtilaan, jossa AI-esikatselu on käytössä.

Jos sinulla ei vielä ole työtilaa, voit luoda sellaisen valitsemalla vasemmanpuoleisesta valikosta **Työtilat** ja valitsemalla sitten alareunan paneelista **Luo työtila**.  Tämä avaa ruudun, jossa voit antaa työtilan tiedot. Kirjoita työtilan nimi ja valitse sitten **Tallenna**.

![Työtilan luominen](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_03.png)

Kun työtila on luotu, voit valita aloitusnäytön oikeassa alanurkassa **Ohita**.

![Ohita](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_04.png)

Valitse **Tietovuot (esikatselu)** -välilehti, valitse työtilan oikeassa ylänurkassa oleva **Luo**-painike ja valitse sitten **Tietovuo**.

![Tietovuot (esikatselu)](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_05.png)

Valitse **Lisää uudet entiteetit**, joka käynnistää selaimessa **Power Query -editorin**.

![Lisää uudet entiteetit](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_06.png)

Valitse tietolähteeksi **teksti- tai CSV-tiedosto**.

![Valitse tietolähde](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_07.png)

Seuraavassa näytössä sinua pyydetään muodostamaan yhteys tietolähteeseen. Liitä linkki tietoihin, joita käytit Azuren automaattianalyysipalveluiden mallin luomiseen. Jos käytit _Automotive Pricing_ -tietoja, voit liittää seuraavan linkin **Tiedostopolku tai URL-osoite** -ruutuun ja valita sitten **Seuraava**.

`https://raw.githubusercontent.com/MicrosoftLearning/Principles-of-Machine-Learning-Python/master/Module7/Automobile%20price%20data%20_Raw_.csv`

![Muodosta yhteys tietolähteeseen](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_08.png)

Power Query -editori näyttää CSV-tiedostossa olevien tietojen esikatselun. Valitse komentopalkista **Muunna taulukko** ja valitse sitten **Käytä ensimmäistä riviä otsikkoina**.  Tämä lisää _Ylennetyt otsikot_ -kyselyvaiheen oikealla puolella olevaan **Käytössä olevat vaiheet** -ruutuun. Voit myös nimetä kyselyn uudelleen ja määrittää sille kätevämmän nimen, kuten _Auton hinnoittelu_, käyttämällä oikealla olevaa ruutua.

![Azure-portaali](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_09.png)

Lähdetietojoukossa tuntemattomien arvojen muodoksi on määritetty ’?’.  Arvon '?' voi korvata arvolla '0', jotta jatkossa vältytään virheiltä.  Voit tehdä tämän valitsemalla sarakkeet *normalisoidut-menetykset (normalized-losses)* , *putki (bore)* , *tahtisuus (stroke)* , *puristussuhde (compression-ratio)* , *hevosvoimat (horsepower)* , *huippukierrokset (peak-rpm)* ja *hinta (price)* napsauttamalla sarakkeiden nimiä sarakeotsikoissa ja valitsemalla ensin Muunna sarakkeet ja sitten Korvaa arvot.  Korvaa ?-merkki 0-merkillä.

![Korvaa arvot](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_10.png)

Kaikkia teksti- tai CSV-lähteestä tulevia taulukon sarakkeita käsitellään tekstisarakkeina.  Seuraavaksi numeeriset sarakkeet on muutettava oikeiden tietotyyppien mukaisiksi.  Voit tehdä tämän Power Queryssä napsauttamalla tietotyyppisymbolia sarakeotsikossa.  Muuta sarakkeet alla oleviksi tietotyypeiksi:

- **Kokonaisluku**: symboling, normalized-losses, curb-weight, engine-size, horsepower, peak-rpm, city-mpg, highway-mpg, price
- **Desimaaliluku**: wheel-base, length, width, height, bore, stroke, compression-ratio

![Muuta sarakkeita](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_11.png)

Sulje Power Query-editori valitsemalla **Valmis**. Tämä toiminto näyttää entiteettien luettelon, joka sisältää lisätyt _Auton hinnoittelu_ -kyselyn tiedot. Valitse oikeassa yläkulmassa **Tallenna**, anna tietovuolle nimi ja valitse sitten **Tallenna**.

![Tallenna tietovuo](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_12.png)

### <a name="refresh-the-dataflow"></a>Tietovuon päivittäminen

Tietovuon tallentaminen tuo näyttöön ilmoituksen siitä, että tietovuo on tallennettu. Valitse **Päivitä nyt**, niin lähteen tietoja käytetään tietovuossa.

![Päivitä tietovuo](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_13.png)

Valitse oikeasta yläkulmasta **Sulje** ja odota, kunnes tietovuon päivitys on valmis.

Voit päivittää tietovuon myös käyttämällä **Toiminnot**-komentoja. Tietovuossa näkyy aikaleima päivityksen valmistumisesta.

![Manuaalinen päivitys](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_14.png)

## <a name="apply-insights-from-your-azure-ml-model"></a>Käytä merkityksellisiä tietoja Azuren automaattianalyysipalveluiden mallista

Jos haluat käyttää Azuren automaattianalyysipalveluiden mallia _autojen hintaennusteiden_ yhteydessä, voit muokata _Auton hinnoittelu_ -entiteettiä, johon haluamme lisätä ennustetun hinnan.

![Muokkaa entiteettiä](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_15.png)

**Muokkaa**-kuvakkeen valitseminen avaa Power Query -editorin tietovuossa oleville entiteeteille.

![Muokkaa](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_16.png)

Valitse valintanauhan **Tekoälyn merkitykselliset tiedot** -painike ja valitse sitten vasemmasta siirtymisvalikosta _Azuren koneoppimismallit_ -kansio.

Ne Azuren automaattianalyysipalveluiden mallit, joihin olet saanut käyttöoikeudet, näkyvät Power Query -funktioina etuliitteellä *AzureML*.  Kun napsautat _AutomobilePricePrediction_-mallia vastaavaa funktiota, mallin verkkopalvelun parametrit merkitään funktioparametreiksi.

Jos haluat käynnistää Azuren automaattianalyysipalveluiden mallin, voit määrittää avattavassa luettelossa minkä tahansa valitun entiteetin sarakkeista syötteeksi. Voit myös määrittää syötteenä käytettävän vakioarvon käyttämällä syötevalintaikkunan vasemmalla puolella olevaa sarakekuvaketta. Kun sarakkeen nimi, joka vastaa funktion jonkin parametrin nimeä, saraketta ehdotetaan automaattisesti syötteeksi.  Jos sarakkeen nimi ei vastaa mitään, voit valita sen avattavasta valikosta.

_Automobile Pricing Prediction_ -mallin osalta syöteparametreja ovat seuraavat:

- malli (make)
- rungon-tyyli (body-style)
- akseliväli (wheel-base)
- moottorin-koko (engine-size)
- hevosvoimat (horsepower)
- huippukierrokset (peak-rpm)
- mailia-gallonaa-kohti-valtatiellä (highway-mpg)

Tässä tapauksessa taulukkomme vastaa alkuperäistä tietojoukkoa, jota käytettiin mallin koulutukseen, joten kaikille parametreille on jo valittu oikeat sarakkeet.

![Harjoita mallia](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_17.png)

Valitse **Käynnistä**, niin voit tarkastella Azuren automaattianalyysipalveluiden mallin tulostetta entiteettitaulukon uutena sarakkeena. Näet myös mallin kutsun kyselyyn käytettynä vaiheena.

Mallin tuloste näkyy tietueena tulostesarakkeessa. Voit laajentaa sarakkeen, niin että saat yksittäiset tulosteparametrit erillisiin sarakkeisiin. Tässä tapauksessa olemme kiinnostuneita vain _Pisteytetyt otsikot (Scored Labels)_ -kohdasta, jossa on auton ennustettu hinta.  Poistetaan siis muiden valinta ja valitaan **OK**.

![Mallituloste](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_18.png)

Tulokseksi saadussa *Pisteytetyt otsikot (Scored Labels)* -sarakkeessa on hinta-ennuste Azuren automaattianalyysipalveluiden mallista.

![Pisteytetyt otsikot](media/service-tutorial-invoke-machine-learning-model/tutorial-invoke-machine-learning-model_19.png)


Kun tallennat tietovuon, Azuren automaattianalyysipalveluiden malli käynnistetään automaattisesti, kun tietovuohon päivitetään entiteettitaulukon uusia tai päivitettyjä rivejä.

## <a name="clean-up-resources"></a>Resurssien tyhjentäminen

Jos et enää tarvitse tässä artikkelissa luotuja Azure-resursseja, poista niitä, jotta ne eivät aiheuta kustannuksia.  Voit poistaa myös luomasi tietovuot, jos et enää tarvitse niitä.

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä opetusohjelmassa olet luonut yksinkertaisen kokeilun käyttämällä Azuren automaattianalyysistudiota käyttämällä yksinkertaista tietojoukkoa ja seuraavia vaiheita:

- Azuren automaattianalyysipalveluiden mallin luominen ja julkaiseminen
- Mallin käyttöoikeuksien myöntäminen Power BI -käyttäjälle
- Tietovirran luominen
- Azuren automaattianalyysipalveluiden mallin merkityksellisten tietojen lisääminen tietovirtaan

Katso lisätietoja Azuren automaattianalyysipalvelujen integroinnista Power BI:ssä artikkelista [Azuren Automaattianalyysipalveluiden Power BI -integrointi (esikatselu)](service-machine-learning-integration.md).
