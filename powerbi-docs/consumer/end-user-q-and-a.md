---
title: Power BI -palvelun Q&A-toiminnon yleiskatsaus
description: Yleiskatsaus aiheeseen Power BI:n Q&A-kyselyt luonnollisella kielellä.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 3548041be39705c3013d09740040afc3e7f1c9e7
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/12/2018
ms.locfileid: "53279574"
---
# <a name="qa-for-power-bi-consumers"></a>Q&A Power BI -**kuluttajille**
## <a name="what-is-qa"></a>Mikä on Q&A?
Joskus nopein tapa saada vastauksia tiedoista on kysyä kysymyksiä luonnollisella kielellä. Esimerkiksi ”mikä oli viime vuoden kokonaismyynti”.  
Q&A-toiminnolla voit tutkia tietojasi intuitiivisesti luonnollisella kielellä sekä saada vastauksia eri kaavioiden muodossa. Q&A eroaa hakukoneesta – Q&A antaa vain tuloksia Power BI:n tiedoista.

**Power BI:n Q&A** tukee vastaamista vain englanniksi kysyttyihin, luonnollisella kielellä esitettyihin kyselyihin. Espanjan kielelle löytyy esikatseluversio, jonka Power BI -järjestelmänvalvojasi voi ottaa käyttöön.

**Power BI:n Q&A** on saatavilla Pro- ja Premium-käyttöoikeuksille. 
>

![q&a:n luoma puukartta](media/end-user-q-and-a/power-bi-qna.png)

Kysymyksen esittäminen on vasta alkua.  Toivottavasti tämä artikkeli auttaa sinua tietojen tutkimisessa ja kysymysten keksimisessä. Kysymyksillä voit löytää uusia tietoja, keskittyä yksityiskohtiin ja tarkastella kokonaisuutta laajemmasta näkökulmasta. Tulet yllättymään iloisesti löytämistäsi merkityksellisistä tiedoista ja muusta.

Kokemus on todella interaktiivinen … ja nopea! Muistissa oleva tallennustila tarjoaa vastauksen lähes välittömästi.

## <a name="where-can-i-use-qa"></a>Missä voin käyttää Q&A:ta?
Q&A löytyy Power BI -palvelun koontinäytöistä, Power BI -mobiilisovelluksen koontinäytön alareunasta ja Power BI Embeddedin visualisointien yläpuolelta. Jos suunnittelija ei ole antanut sinulle muokkausoikeuksia, pystyt ainoastaan tutkimaan tietoja Q&A-toiminnon avulla, mutta et voi tallentaa sen avulla luotuja visualisointeja.

![kysymysruutu](media/end-user-q-and-a/powerbi-qna.png)

## <a name="how-does-qa-know-how-to-answer-questions"></a>Miten Q&A tietää vastaukset kysymyksiin?
Q&A etsii vastauksia kaikista koontinäyttöön liittyvistä tietojoukoista. Jos tietojoukolla on ruutu koontinäytössä, Q&A käyttää kyseistä tietojoukkoa vastauksien etsimiseen. 

## <a name="how-do-i-start"></a>Miten pääsen alkuun?
Tutustu ensin sisältöön. Tutustu koontinäytön ja raportin visualisointeihin. Selvitä, mitkä tietotyypit ja -alueet ovat käytettävissäsi. Suuntaa sitten takaisin koontinäyttöön ja aseta kohdistin kysymysruutuun. Q&A-näyttö avautuu.

![Q&A-näyttö](media/end-user-q-and-a/power-bi-qna-screen.png) 

* Jos visualisointien akselien otsikot ja arvot ovat ”myynti”, ”tili”, ”kuukausi” ja ”mahdollisuudet”, voit esittää esimerkiksi seuraavanlaisia kysymyksiä: ”Millä *tilillä* on suurin *mahdollisuus* tai näytä *myynti* kuukauden mukaan palkkikaaviona”.

* Jos sinulla on sivuston suorituskykytietoja Google Analyticsissä, voit kysyä Q&A:lta verkkosivulla käytetystä ajasta, yksilöllisten vierailujen määrästä ja käyttäjien sitoutumisesta. Jos haluat demografisia tietoja, voit esittää kysymyksiä esimerkiksi iästä ja kotitalouden tuloista sijainnin mukaan.

Näytön alareunasta löytyy muita hyödyllisiä kohteita. Q&A näyttää jokaisen tietojoukon kohdalla avainsanoja ja joskus myös mallikysymyksiä tai kysymysehdotuksia. Kun valitset jonkin näistä, se lisätään kysymysruutuun. 

Q&A käyttää myös kehotteita, automaattista täydennystä ja visuaalisia vihjeitä, kun tarvitset apua kysymysten muodostamisessa. 

![video](media/end-user-q-and-a/qa.gif) 


### <a name="which-visualization-does-qa-use"></a>Mitä visualisointia Q&A käyttää?
Q&A valitsee parhaan visualisoinnin näytettyjen tietojen perusteella. Joskus pohjana oleva tietojoukko on määritelty tiettynä tyyppinä tai luokkana, jolloin Q&A tietää missä muodossa tiedot kannattaa näyttää. Esimerkiksi jos tiedot on määritetty päivämäärä-tyypiksi, ne näytetään todennäköisesti viivakaaviona. Kaupungiksi luokitellut tiedot näytetään todennäköisesti karttana.

Voit myös kertoa Q&A:lle mistä visualisoinnista haluat hakea lisäämällä sen kysymykseen. Muista kuitenkin, että Q&A ei ehkä voi näyttää tietoja pyytämästäsi visualisointityypistä. Q&A näyttää sinulle luettelon sopivista visualisointityypeistä.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
**Kysymys**: En näe Q&A:ta tässä raporttinäkymässä.    
**Vastaus 1**: Jos kysymysruutua ei näy, tarkista ensin asetuksesi. Valitse hammasrataskuvake Power BI -työkalurivin oikeasta yläkulmasta.   
![hammasrataskuvake](media/end-user-q-and-a/power-bi-settings.png)

Valitse sitten **Asetukset** > **Koontinäytöt**. Varmista, että **Näytä Q&A-hakuruutu tässä koontinäytössä** -vaihtoehdon vieressä on valintamerkki.
![Q&A:n koontinäyttöasetukset](media/end-user-q-and-a/power-bi-turn-on.png)  


**Vastaus 2**: Raporttinäkymän *suunnittelija* tai järjestelmänvalvoja on saattanut poistaa Q&A:n käytöstä. Kysy, voitko ottaa sen takaisin käyttöön.   

**Kysymys**: En saa haluttuja tuloksia, kun kirjoitan kysymyksen.    
**Vastaus**: Ota yhteys raporttinäkymän *suunnittelijaan*. Suunnittelija voi auttaa parantamaan Q&A:n tuloksia monin eri tavoin. Suunnittelija voi esimerkiksi muuttaa tietojoukon sarakkeessa käytettäviä termejä helpommin ymmärrettäviksi (`CustFN` --> `CustomerFirstName`). Koska suunnittelija tuntee tietojoukon todella hyvin, hän voi myös keksiä sopivia kysymyksiä ja lisätä ne Q&A-pohjaan.

![suositeltu kysymys korostettuna](media/end-user-q-and-a/power-bi-featured-q.png)

## <a name="next-steps"></a>Seuraavat vaiheet

