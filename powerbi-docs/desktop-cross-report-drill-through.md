---
title: Raporttien välillä porautumisen käyttäminen Power BI Desktopissa
description: Katso, miten voit porautua raportista toiseen Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/18/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 7189ef77446446b56b1dcb55b43b022d0fc5c057
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2019
ms.locfileid: "73868770"
---
# <a name="use-cross-report-drillthrough-in-power-bi-desktop"></a>Raporttien välillä porautumisen käyttäminen Power BI Desktopissa

Power BI Desktopin raporttien välisen porautumisominaisuuden avulla voit siirtyä kontekstuaalisesti raportista toiseen. Tämä edellyttää, että raportit ovat samassa työtilassa tai sovelluksessa Power BI ‑palvelussa. Raporttien välillä porautumisen avulla voit yhdistää kaksi tai useita raportteja, joissa on toisiinsa liittyvää sisältöä, ja välittää suodatettua kontekstia raporttien välisen yhteyden ohella. Tässä artikkelissa kerrotaan, miten voit määrittää Power BI ‑raporttien välillä porautumisen sekä se, millainen käyttökokemus on, kun käyttäjät hyödyntävät raporttien välillä porautumista itse.

![Näyttökuva Power BI Desktopin porautumisvaihtoehdosta](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Seuraavat määritelmät on tärkeä tietää, ennen kuin alat määrittää ja käyttää raporttien välillä porautumista:

* **Lähdevisualisointi:** Visualisointi, joka käynnistää porautumistoiminnon visuaalisen pikavalikon avulla.
* **Lähderaportti:** Raportti, joka sisältää lähdevisualisoinnin raporttien välillä porautumiseen.
* **Kohdesivu:** Sivu, jolle käyttäjä päätyy porautumistoiminnon aloittamisen jälkeen.
* **Kohderaportti:** Raportti, joka sisältää kohdesivun raporttien välillä porautumiseen.


> [!NOTE]
> Power BI Desktopin raporttien välisen porautumisominaisuuden avulla voit siirtyä kontekstuaalisesti raportista toiseen. Tämä edellyttää, että raportit ovat samassa työtilassa tai sovelluksessa Power BI ‑palvelussa. Tämä ei ole käytettävissä, kun käytät yksittäisiä jaettuja raportteja *omassa työtilassa* ([Jaettu kanssani -raportit](service-share-dashboards.md#share-a-dashboard-or-report)). Sen sijaan sinun on käytettävä raporttia työtilassa, josta se on alun perin jaettu.


## <a name="enable-cross-report-drillthrough"></a>Raporttien välillä porautumisen käyttöönotto

Jos haluat tehdä raportista raporttien välillä porautumisen kohteen, sinun on otettava kyseinen raportin ominaisuus käyttöön **Asetukset**-ikkunassa. Siirry kohtaan **Tiedosto** > **Asetukset** > **Asetukset** ja sitten sivun vasemmassa alareunassa olevaan kohtaan **Raportin asetukset**.

Valitse **Salli visualisoinnit tässä raportissa, jos haluat käyttää porautumisen kohteita muista raporteista** -valintaruutu seuraavassa kuvassa esitetyllä tavalla.

![Näyttökuva asetusikkunasta, jossa Raporttiasetukset on korostettu](media/desktop-cross-report-drill-through/cross-report-drill-through-02.png)

Raporttien välillä porautuminen on nyt käytössä.

## <a name="set-up-cross-report-drillthrough"></a>Raporttien välillä porautumisen määrittäminen

Raporttien välillä poraaminen määritetään kuin raportin sisäinen porautuminen. Porautuminen on otettu käyttöön kohdesivulla, minkä ansiosta muut visualisoinnit voivat porautua käyttöön otettuun sivuun. Katso artikkelista [Porauksen käyttäminen Power BI Desktopissa](desktop-drillthrough.md) vaiheet, joilla voit luoda porautumisen yhdestä raportista.

Jotta voit aloittaa asennuksen, sinun on suoritettava muutama ennakkovaihe:

* Määritä porautumisen kohdesivu, jota voidaan sen jälkeen käyttää muista työtilan tai sovelluksen raporteista.
* Salli raportin tarkastella porautumissivuja oman raporttinsa ulkopuolelta.

Etsi porautumisasetukset **Visualisoinnit**-ruudun **Kentät**-osiosta seuraavassa kuvassa esitetyllä tavalla.

![Näyttökuva Visualisoinnit-ruudusta, jossa porautumisasetukset on korostettu](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Sivulla porautumisen käyttöönotto edellyttää, että vahvistat ensin lähde- ja kohderaporttien tietomallit. Varmista, että: 

* kentät, jotka haluat välittää, sisältyvät molempiin tietomalleihin.
* kenttien nimet ja niiden taulukoiden nimet, joihin ne kuuluvat, ovat identtiset (merkkijonojen on myös vastattava toisiaan ja kirjainkoko on merkitsevä).

Jos haluat esimerkiksi välittää kenttää *Maa* koskevan suodattimen taulukosta *Maantiede*, molemmissa malleissa on oltava *Maantiede*-taulukko ja kyseisessä taulukossa *Maa*-kenttä. Jos näin ei ole, sinun on päivitettävä pohjana olevassa mallissa olevan kentän tai taulukon nimi. Ainoastaan kenttien näyttönimien päivittäminen ei toimi oikein raporttien välillä porautumisessa. (Huomaa, että raporttien kaikkien rakenteiden ei tarvitse olla täsmälleen samat.)

Jotta voit aloittaa asennuksen, sinun on valmisteltava kohdesivu. Siirry Power BI Desktopissa samalle sivulle ja varmista, että **Raporttien välinen** porautuminen -asetus on **Käytössä**. 

![Näyttökuva, jossa Raporttien välillä porautuminen -asetus on käytössä](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Vedä pohjaan seuraavaksi kentät, joita haluat käyttää porautumisen kohteena. Valitse, haluatko kenttää käytettävän luokkana tai yhteen vedettynä kuin mittayksikön tavoin. Tässä vaiheessa voit valita, haluatko poistaa käytöstä visualisoinnin **Säilytä kaikki suodattimet** -vaihtoehdon. Jos et halua välittää muita käytössä olevia suodattimia lähdevisualisoinnista porautumisen kohdevisualisointiin, valitse **Ei käytössä**.

> [!NOTE]
> Jos käytät sivua vain raporttien välillä porautumiseen, poista **Takaisin**-painike, joka lisätään automaattisesti. **Takaisin**-painike tukee vain yhden raportin sisällä siirtymistä. 

Kun olet määrittänyt visualisoinnin, tallenna raportti, jos käytät Power BI -palvelua, tai tallenna ja julkaise raportti, jos käytät Power BI Desktopia.

Edellisessä osiossa kuvattiin, miten raporttien välillä porautuminen otetaan käyttöön Power BI Desktopissa (**Asetukset**-ikkunassa). Jos käytät Power BI -palvelua raporttien välillä porautumisen kohteen luomiseen, raporttien välillä porautumisen käyttöönottaminen edellyttää seuraavaa: 

1. Valitse työtila, jossa lähde- ja kohderaportti sijaitsevat.
2. Valitse **Raportit**.
3. Valitse lähderaportin **Asetukset**-kuvake.
4. Varmista, että raporttien välillä porautumisen asetus on **Käytössä.**
5. Tallenna raporttisi.

Siinä kaikki! Raporttisi on valmis raportin raporttien välillä porautumiseen. 

Seuraavassa osiossa tutustumme käyttökokemukseen käyttäjän näkökulmasta.

## <a name="cross-report-drillthrough-experience"></a>Raporttien välillä porautumisen käyttökokemus

Kun määrität raporttien välillä porautumisen käyttökokemuksen, voit alkaa hyödyntää ominaisuutta.

Valitse lähderaportti Power BI -palvelussa ja valitse sitten visualisointi, joka käyttää kenttää tai kenttiä tavalla, jonka määritit kohdesivun määrittämisen yhteydessä. Avaa sitten visualisointien pikavalikko napsauttamalla arvopistettä hiiren kakkospainikkeella ja valitse **Porautuminen**.

![Kuvakaappaus lähderaportista Power BI -palvelussa Porautuminen korostettuna](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Näet tulokset raporttien välillä porautumisen kohderaportin sivulla, juuri niin kuin määritit ne kohdetta luodessasi. Tulokset suodatetaan porautumisasetusten mukaan.

> [!IMPORTANT]
> Power BI tallentaa raportti välillä porautumisen kohteet välimuistiin. Jos teet muutoksia, päivitä selaimesi, jos et näe porautumisen kohteita odotetulla tavalla. 

Raporttien välillä porautumisen kohteiden muoto on seuraava: 

`Target Page Name [Target Report Name]`

Kun olet valinnut porautumisen kohdesivun, Power BI siirtyy kyseiselle sivulle. Se välittää suodatuksen kontekstin kohdesivun asetusten perusteella. 

Lähdevisualisoinnin suodatuksen konteksti voi sisältää seuraavat: 

* Lähdevisualisointiin vaikuttavat raportti-, sivu- ja visualisointitason suodattimet. 
* Lähdevisualisointiin vaikuttava ristiinsuodatus ja ristiinkorostus. 
* Sivulla ja synkronoinnin osittajilla olevat osittajat.
* URL-parametrit.

Kun siirryt porautumisen kohderaporttiin, Power BI käyttää suodattimia vain sellaisille kentille, joiden nimelle ja taulukon nimelle se löytää tarkan merkkijonovastaavuuden. Power BI ei käytä kohderaportin kiinteitä suodattimia. Se kuitenkin soveltaa henkilökohtaista oletuskirjanmerkkiäsi, jos sellainen on olemassa. Jos esimerkiksi henkilökohtaisessa oletuskirjanmerkissäsi on raportti tason suodatin *Maa = USA*, Power BI soveltaa kyseistä suodatinta ennen kuin lähdevisualisoinnin suodatuksen kontekstia sovelletaan. 

Raporttien välillä porautumisessa Power BI välittää suodatuksen kontekstin kaikille kohderaportin vakiosivuille. Power BI ei välitä työkaluvihjesivujen suodatuksen kontekstia, koska työkaluvihjesivut suodatetaan työkaluvihjeen käynnistävän lähdevisualisoinnin perusteella.

Jos haluat palata lähderaporttiin, kun raporttien välillä porautuminen on suoritettu, käytä selaimen **Edellinen**-painiketta. 

## <a name="next-steps"></a>Seuraavat vaiheet

Voit olla kiinnostunut myös seuraavista artikkeleista:

* [Osittajien käyttäminen Power BI Desktopissa](visuals/power-bi-visualization-slicers.md)
* [Porautumisen käyttäminen Power BI Desktopissa](desktop-drillthrough.md)

