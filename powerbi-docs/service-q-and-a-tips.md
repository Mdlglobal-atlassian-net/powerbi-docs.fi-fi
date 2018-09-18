---
title: Vinkkejä kysymysten kysymiseen Power BI:n Q&A-toiminnolla
description: Vinkkejä kysymysten kysymiseen Power BI:n Q&A-toiminnolla
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/18/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 189134a82e183819f1d48be0b420c9f92a5e69b3
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/12/2018
ms.locfileid: "44725945"
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>Vihjeitä kysymysten esittämiseen Power BI:n Q&A-toiminnolla
## <a name="words-and-terminology-that-qa-recognizes"></a>Q&A-toiminnon tunnistamia sanoja ja termejä
Avainsanaluettelo ei ole täydellinen.  Paras tapa nähdä, tunnistaako Power BI avainsanan, on kokeilla sen kirjoittamista kysymysruutuun.  Jos sana tai termi näkyy harmaana, Power BI ei tunnista sitä tai ei tunnista sitä nykyisessä kontekstissa.

Alla olevassa luettelossa käytetään preesensiä, mutta useimmissa tapauksissa kaikki aikamuodot tunnistetaan. Esimerkki: ”on” sisältää myös muodot ovat, oli, olivat.  Ja ”lajittele” sisältää muodot lajiteltu ja lajittelu.  Power BI tunnistaa ja ottaa hakuun mukaan sanan yksikön ja monikon. Power BI tunnistaa esimerkiksi sanat ”vuosi” ja ”vuodet”.

> [!NOTE]
> Q&A-toiminto on käytettävissä myös [Microsoft Power BI -sovelluksessa iOS:lle iPad-, iPhone- ja iPod Touch -laitteissa](consumer/mobile/mobile-apps-ios-qna.md).
> 
> 

Jos olet tietojoukon omistaja, lisää sanamuotoja ja synonyymejä asiakkaiden Q&A-tulosten parantamiseksi.

**Summat**: yhteensä, summa, määrä, numero, lukumäärä, loppusumma, keskiarvo, eniten, vähiten, suurin, pienin, korkein, isoin, maksimi, max, enin, vähin, vähäisin, minimi, min

**Artikkelit (mikäli englanninkielinen)**: a, an, the

**Tyhjä ja totuusarvo**: tyhjä, sisällötön, nolla, ”ei”- tai ”muu”-etuliite, tyhjä merkkijono, tyhjä teksti, tosi, true, epätosi, false, t, f

**Vertailut**: vs, versus, verrattuna, verrataan

**Konjunktiot**: ja, tai, kukin, kanssa, verrattuna, mutta, ei kumpikaan, sekä, lisäksi

**Supistumat**: Q&A-toiminto tunnistaa lähes kaikki supistumat, kokeile.  Joitakin esimerkkejä: ettei, muttei, tai esimerkiksi englannin didn’t, haven’t, won’t, wouldn’t.

**Päivämäärät**: Power BI tunnistaa useimmat päivämääräsanat (päivä, viikko, kuukausi, vuosi, vuosineljännes, vuosikymmen jne.) sekä eri muodoissa kirjoitetut päivämäärät (katso alla). Power BI tunnistaa myös seuraavat avainsanat: MonthName, Days 1-31, decade.

Esimerkkejä: tammikuun 3. 1995, 3. tammikuuta 1995, 3.1.1995, 03.01.1995, kolmas tammikuuta, tammikuu 1995, 1995 tammikuu, 1995-01, 01/1995, kuukausien nimet.

**Suhteelliset päivämäärät**: tänään, juuri nyt, tämänhetkinen aika, eilen, huomenna, nykyinen, seuraava, tuleva, viimeinen, edellinen, sitten, ennen kuin nyt, aiemmin kuin, jälkeen, myöhemmin kuin, alkaen, aikana, päivänä, tästä hetkestä lähtien, tämän hetken jälkeen, tulevaisuudessa, menneisyydessä, sisällä, yli, N päivää sitten, N päivän päästä, kerran, kaksi kertaa.

Esimerkki: tilausten määrä viimeisten 6 päivän aikana.

**Yhtäläisyys (alue)**: yhtä suuri kuin, =, on yli, välillä

Esimerkkejä: Tilausvuosi on aiempi kuin 2012? Hinta on välillä 10–20? Onko Jonin ikä suurempi kuin 40? Kokonaismyynti välillä 200–300?

**Yhtäläisyys (arvo)**: on, yhtä suuri, yhtä suuri kuin, sama kuin

Esimerkkejä: Mitkä tuotteet ovat vihreitä? Tilauksen päivämäärä on 2012. Onko Jonin ikä 40? Kokonaismyynti, joka ei ole sama kuin 200? Tilauksen päivämäärä on 1/1/2016. Hinta on 10? Väri on vihreä? Hinta on 10?

**Nimet**: jos tietojoukon sarake sisältää ilmauksen ”name” (esimerkiksi EmployeeName), Q&A-toiminto ymmärtää, että sarakkeen arvot ovat nimiä. Silloin voit esittää esimerkiksi kysymyksen ”minkä työntekijöiden nimi on Robert” kaltaisia kysymyksiä.

**Pronominit**: hän, hänen, se,sen, he heidän, tuo, nuo

**Kyselykomennot**: lajiteltu, lajittele, suunta, ryhmä, ryhmitä, näytä, luetteloi, osoita, anna, nimi, juuri, vain, järjestä, vertaa, vastaan, aakkosjärjestys, nouseva, laskeva, järjestys

**Alue**: suurempi, enemmän, isompi, yli, >, vähemmän, pienempi, harvempi, alle, <, vähintään, ei ole pienempi kuin, > =, enintään, korkeintaan, < =, välillä, alueella, alkaen, päättyen, aikaisempi, myöhäisempi, ennen, jälkeen, lähtien, aikaisemmin, myöhemmin

**Ajat**: klo, kello, am, pm, keskipäivä, keskiyö, tunti, minuutti, sekunti, hh:mm:ss

Esimerkkejä: klo 10, kello 23:35, 10:35:15 pm, keskipäivällä, keskiyöllä, tunti, minuutti sekunti.

**Ylimmät N** (tilaus, luokittelu): ylin, alin, suurin, pienin, ensimmäinen, viimeinen, seuraava, aikaisin, uusin, vanhin, viimeisin

**Visualisointityypit**: kaikki Power BI:n alkuperäiset visualisointityypit.  Jos visualisointiruudussa on jokin vaihtoehto, voit sisällyttää sen kysymykseen.  Poikkeuksena ovat [Mukautetut visualisoinnit](power-bi-custom-visuals.md), jotka olet lisännyt manuaalisesti visualisointiruutuun.

Esimerkki: näytä alueet kuukauden ja kokonaismyynnin mukaan palkkikaaviona

**Wh (suhde, määre)**: milloin, missä, mikä, kuka, kenen, kuinka monta, kuinka paljon, kuinka monta kertaa, kuinka usein, määrä, numero, lukumäärä, miten pitkään, mitä

## <a name="qa-helps-you-phrase-the-question"></a>Q&A-toiminto auttaa kyselyn muotoilemisessa
Q&A-toiminto pyrkii varmistamaan, että vastaus vastaa niin tarkasti kuin mahdollista esitettyä kysymystä. Tähän pyritään usealla eri tavalla. Kaikkien vaihtoehtojen kohdalla voit hyväksyä toiminnon kokonaan, osittain tai ei ollenkaan. Kysymystä kirjoittaessasi Q&A-toiminto:

* täydentää sanoja ja kysymyksiä automaattisesti. Toiminto hyödyntää eri menetelmiä, kuten tunnistettavien sanojen, työkirjoissa usein esitettyjen kysymysten sekä kelvollisen vastauksen palauttaneiden aiemmin esitettyjen kysymysten automaattista täydennystä. Jos tarjolla on useampi kuin yksi automaattisen täydennyksen vaihtoehto, ne esitetään avattavana luettelona.
* korjaa kirjoitusasua.
* tarjoaa esikatselukuvan vastauksesta visualisoinnin muodossa. Visualisointi päivittyy kysymystä kirjoittaessasi ja muokatessasi (se ei odottaa Enterin painamista).
* ehdottaa automaattisesti vaihtoehtoisia termejä pohjalla olevasta tietojoukosta/tietojoukoista, kun siirrät osoittimen takaisin kysymysruutuun.
* oikaisee kysymyksen pohjalla olevien tietojoukkojen tietojen perusteella. Tämän avulla voidaan varmistaa, että Q&A-toiminto ymmärtää kysymyksesi, kun Q&A korvaa käyttämiäsi sanoja pohjalla olevasta tietojoukosta löytyvillä synonyymeillä.
* himmentää sanoja, joita toiminto ei ymmärrä.

## <a name="dont-stop-now"></a>Älä lopeta tähän
Kun Q&A-toiminto näyttää tulokset, jatka keskustelua! Hyödynnä visualisoinnin ja Q&A-toiminnon vuorovaikutteisia toimintoja ja saa vieläkin enemmän tietoja.

## <a name="next-steps"></a>Seuraavat vaiheet
Takaisin artikkeliin [Q&A Power BI:ssä](power-bi-q-and-a.md)  

[Power BI:n peruskäsitteet](service-basic-concepts.md)  

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

