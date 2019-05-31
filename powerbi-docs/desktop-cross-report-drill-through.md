---
title: Rajat raportin porautumisen käyttäminen Power BI Desktop
description: Lue, miten voit porautua yksi raportti toiseen Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 45a7cdd3c7b5324f3d618eaba4bdb3968a9549a5
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375209"
---
# <a name="use-cross-report-drillthrough-in-power-bi-desktop"></a>Rajat raportin porautumisen käyttäminen Power BI Desktop

Power BI Desktop rajat raportin drillthrough-toiminnon voit contextually siirtyä yhden raportin toisesta raportista. Tämä pitää paikkansa, kunhan raportit ovat samassa työtilassa tai sovellus Microsoft Power BI-palvelussa. Rajat-raportin porautumisen käyttö, yhteyden vähintään kaksi raportteja, jotka on Aiheeseen liittyvä sisältö ja välittää rajat raportin yhteys ja suodatinkonteksti. Tässä artikkelissa opit rajat raportin siirtymisessä Power BI-raporttien määrittämisestä ja mitä käyttäjät kohdata, kun ne käyttävät rajat raportin porautumisen itse.

![Power BI Desktop näyttökuva porautumisen vaihtoehto](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Seuraavia määritelmiä on tärkeää ymmärtää, ennen kuin voimme määrittämisessä ja käyttämisessä rajat-raportin porautumisen:

* **Lähdevisualisoinnissa:** Visualisointi, joka käynnistää visual pikavalikko käyttämällä drillthrough-toiminto.
* **Tietolähteen raportti:** Raportin, joka sisältää usean raportin porautumisen lähde-visualisoinnin.
* **Kohdesivu:** Sivu, joka käyttäjän viedään maihin jälkeen aloitetaan drillthrough-toiminto.
* **Kohderaportti:** Raportti, joka sisältää usean raportin porautumisen kohdesivun.

## <a name="enable-cross-report-drillthrough"></a>Ota käyttöön usean raportin siirtyminen

Jotta raportti on usean raportin porautumisen kohde, sinun on otettava raportin ominaisuuden käyttöön **asetukset** ikkunassa. Siirry **tiedoston** > **asetukset ja vaihtoehdot** > **asetukset**, ja sitten **raportin asetukset** lähellä vasemmalla sivun alareunaan.

Valitse **sallia visualisointien Tässä raportissa käyttää drillthrough-kohteet muista raporteista** valintaruutu, seuraavassa kuvassa esitetyllä tavalla.

![Näyttökuva asetukset-ikkunan, kun korostettuna raporttiasetukset](media/desktop-cross-report-drill-through/cross-report-drill-through-02.png)

Rajat raportin porautuminen on nyt käytössä.

## <a name="set-up-cross-report-drillthrough"></a>Rajat raportin porautumisen määrittäminen

Rajat raportin porautumisen määrittäminen on samankaltainen kuin raportin sisältämien porautumisen määrittäminen. Porautuminen on käytössä kohdesivu, sallii kohteeksi porautumisen käytössä sivun muut visualisoinnit. Voit luoda yksittäisen raportin sisältämien porautumisen, aiheessa [porautumisen käyttäminen Power BI Desktop](desktop-drillthrough.md).

Aloita asennus edellyttää muutaman ensimmäisen vaiheet:

* Määritä porautumisen kohdesivua, jota voidaan käyttää sitten muut raportit työtila tai sovelluksen.
* Salli raportin näkevän porautumisen sivuja oman raportin ulkopuolella.

Etsi porautumisen asetukset **kentät** osion **visualisoinnit** seuraavassa kuvassa esitetyllä.

![Näyttökuva-visualisoinnit-ruudussa porautumisen asetuksilla korostettuna](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Porautumisen sivun käyttöönottoon ensimmäinen vaihe on vahvistaminen lähde- ja -raporttien tietomalleja. Varmista, että: 

* Kentät haluat välittää ole sekä tietomalleja.
* Kenttien nimet ja, johon ne kuuluvat taulukoiden nimet ovat samat (merkkijonot vastattava myös ja kirjainkoko on merkitsevä).

Esimerkiksi, jos haluat välittää suodattimen kenttään *maan* taulukon sisällä *Geography*, molempien on oltava *Geography* taulukon ja *maan* kenttää kyseisen taulukon sisällä. Jos ei, sinun on päivitettävä kenttänimi tai pohjana olevassa mallissa taulukkonimi. Päivitetään vain kentät näyttönimi ei toimi oikein rajat raportin porautumisen. (Huomaa, että raporttien rakenteet ei tarvitse olla tarkalleen samat.)

Jos haluat aloittaa asennuksen, sinun on Valmistaudu kohdesivu. Siirry sivulle ja varmista, että Power BI Desktop **rajat raportin** porautumisen Vaihda asetetaan **-** . 

![Rajat raportin vaihtopainike näyttökuva](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Vedä kentät, jotka haluat käyttää porautumiskohde pohjaan. Valitse, kenttää voi käyttää luokan tai yhteenvedetyt kuten mittayksikkö. Tässä vaiheessa voit valita, haluatko poistaa käytöstä **Säilytä kaikki suodattimet** Näytä tai piilota visualisoinnin. Jos et halua siirtää muita käytetyt suodattimet lähteestä visual target-porautumisen visualisoinnin, valitse **käytöstä**.

> [!NOTE]
> Jos käytät sivun vain usean raportin porautumisen, poista **takaisin** painike, joka lisätään automaattisesti. **Takaisin** painike toimii vain yksittäisen raportin sisältämien nagivation. 

Kun olet määrittänyt visualisoinnin, varmista, että Tallenna raportti, jos olet Power BI-palvelussa tai Tallenna ja Julkaise raportti, jos käytät Power BI Desktop.

Edellisessä osassa kuvailtiin ottamisesta käyttöön usean raportin siirtyminen Power BI Desktop-(- **asetukset** ikkuna). Jos käytät Power BI-palvelun luomiseen usean raportin porautumiskohde, ota käyttöön usean raportin porautuminen edellyttää seuraavia toimia: 

1. Valitse työtila, jossa Kohderaportti ja lähderaportin asuvat.
2. Valitse **raporttien**.
3. Valitse **asetukset** lähde-raportin kuvake.
4. Varmista, että rajat raportin porautumisen käytössä on **-** .
5. Tallenna raportti.

Siinä kaikki! Raportti on valmis rajat raportin drillthrough-käyttökokemus. 

Seuraavassa osiossa olemme Tutustu käyttökokemus käyttäjän näkökulmasta.

## <a name="cross-report-drillthrough-experience"></a>Rajat raportin porautumisen käyttökokemus

Kun määrität raportin rajat raportin drillthrough-käyttökokemus, voit sijoittaa ominaisuus käyttää.

Valitse lähderaportti Power BI-palvelussa ja valitse visualisointi, joka käyttää tavalla, kun määrität kohdesivu määritetty kentät. Seuraavaksi hiiren kakkospainikkeella arvopistettä visual pikavalikko, ja valitse **porautumisen**.

![Näyttökuva tietolähteen Power BI-palvelun raportissa porautumisen korostettuna](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Näet tulokset kohde rajat raportin porautuminen-sivulla samalla tavalla kuin niiden määrittämisestä kun kohde luodaan. Tulokset suodatetaan drillthrough-asetustesi mukaan.

> [!IMPORTANT]
> Power BI Lisää rajat raportin porautumisen kohteet. Jos teet muutoksia, muista voit päivittää selaimesi, jos et näe porautumisen kohteet odotetulla tavalla. 

Rajat raportin kohteet on muotoiltu seuraavat tavalla: 

`Target Page Name [Target Report Name]`

Kun olet valinnut kohdesivu, johon haluat porautua, Power BI tuo kyseisen sivun. Se välittävän suodatinkonteksti kohdesivu asetusten perusteella. 

Suodatinkonteksti visual lähteestä voi sisältää seuraavat: 

* Raportin sivun ja visuaalisen tason suodattimet, jotka vaikuttavat lähde-visualisoinnin. 
* Ristiinsuodatuksen ja ristiinkorostuksen, jotka vaikuttavat lähde-visualisoinnin. 
* Osittajat sivulla ja synkronoi osittajat.
* URL-parametreja.

Kun porautuminen kohderaportin päädyt Power BI koskee vain suodattimet kentille, jotka se etsii tarkka merkkijono vastaa kenttänimi ja taulukkonimi. Power BI ei käytä kiinteitä suodattimia target-raportista. Se, koskevat kuitenkin oletusarvon henkilökohtainen kirjanmerkki, jos sellainen on olemassa. Esimerkiksi, jos oletusarvon henkilökohtainen kirjanmerkki sisältää raporttitason suodatin- *maa = USA*, Power BI ottaa suodatin ensin ennen käyttöön suodatinkonteksti lähdevisualisoinnissa. 

Power BI välittämistä suodatinkonteksti rajat raportin porautumisen kohderaportin standard sivuihin. Power BI ei välittää työkaluvihjesivujen, suodatinkonteksti, koska työkaluvihjesivujen lähdevisualisoinnissa, joka kutsuu työkaluvihje on suodatettu perusteella.

Jos haluat palata lähderaportin jälkeen rajat raportin drillthrough-toiminto, käytä selaimen **takaisin** painike. 

## <a name="next-steps"></a>Seuraavat vaiheet

Voit olla kiinnostunut myös seuraavista artikkeleista:

* [Osittajien käyttäminen Power BI Desktopissa](visuals/power-bi-visualization-slicers.md)
* [Porautumisen käyttäminen Power BI Desktopissa](desktop-drillthrough.md)

