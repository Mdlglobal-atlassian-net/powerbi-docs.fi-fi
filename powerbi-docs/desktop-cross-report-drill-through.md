---
title: Raporttien välillä porautumisen käyttäminen Power BI Desktopissa
description: Katso, miten voit porautua raportista toiseen Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/16/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: e500cb29bcc4472c59e7e8215fc0a7e7e728ea0d
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/23/2020
ms.locfileid: "76538824"
---
# <a name="use-cross-report-drillthrough-in-power-bi"></a>Raporttien välillä porautuminen Power BI:ssä

Power BI:n *raporttien välillä porautumisen* avulla voit kontekstuaalisesti siirtyä raportista toiseen saman Power BI -palvelutyötilan tai sovelluksen sisällä. Raportista toiseen porautumalla voit yhdistää kaksi tai useita raportteja, joissa on toisiinsa liittyvää sisältöä, ja välittää suodatettua kontekstia raporttien välisen yhteyden ohella. 

Raporttien välisen porautumisen aloitat valitsemalla arvopisteen *lähdevisualisoinnista*, joka kuuluu *lähderaporttiin*, minkä jälkeen valitset raporttien välisen **Porautuminen**-kohteen pikavalikosta. 

![Power BI:n raporttien välillä porautumisen asetus](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Porautumistoiminto avaa *kohdesivun* *kohderaportissa*. 

![Power BI Desktopin raporttien välillä porautumisen kohde](media/desktop-cross-report-drill-through/cross-report-drill-through-01a.png)

Tämä artikkeli näyttää, miten voit määrittää raporttien välisen porautumistoiminnon ja käyttää sitä Power BI -raporteissa.

> [!NOTE]
> Et voi käyttää raporttien välillä porautumista yksilöllisesti jaetuissa [Jaettu kanssani -raporteissa](service-share-dashboards.md#share-a-dashboard-or-report) **Oman työtilan** sisällä. Jotta voit käyttää raporttien välillä porautumista, sinun on käytettävä raportteja siitä työtilasta, jossa ne on jaettu.

## <a name="enable-cross-report-drillthrough"></a>Raporttien välillä porautumisen käyttöönotto

Ensimmäinen askel raporttien välisen porautumisen käyttöönotossa on lähde- ja kohderaporttien tietomallien vahvistaminen. Vaikka eri raporttien rakenteen ei tarvitse olla sama, niiden kenttien, joiden kautta haluat porautua, on oltava olemassa molemmissa tietomalleissa. Kenttien nimien sekä niiden taulukoiden nimien, joihin ne kuuluvat, on oltava identtiset. Merkkijonojen on vastattava toisiaan myös kirjainkoon osalta.

Esimerkiksi jos haluat sijoittaa suodattimen kenttään **Osavaltio** taulukossa **Yhdysvaltain osavaltiot**, molemmissa malleissa on oltava taulukko **Yhdysvaltain osavaltiot** ja taulukossa on oltava kenttä **Osavaltio**. Jos näin ei ole, sinun on päivitettävä pohjana olevassa mallissa olevan kentän tai taulukon nimi. Ainoastaan kenttien näyttönimien päivittäminen ei toimi oikein raporttien välillä porautumisessa.

Kun olet vahvistanut mallit, ota raporttien välinen porautuminen käyttöön lähderaportissa. 

1. Siirry Power BI Desktopissa kohtaan **Tiedosto** > **Asetukset ja vaihtoehdot** > **Asetukset**. 
1. Valitse siirtymispalkin vasemman puolen **Asetuksissa**, osan **Nykyinen tiedosto** alaosassa, **Raportin asetukset**. 
1. Valitse oikealla alhaalla, kohdassa **Raporttien välillä porautuminen**, **Salli visualisoinnit tässä raportissa, jos haluat käyttää porautumisen kohteita muista raporteista**. 
1. Valitse **OK**. 
   
   ![Raporttien välillä porautumisen käyttöönotto Power BI Desktopissa](media/desktop-cross-report-drill-through/cross-report-drill-through-02.png)

Voit myös ottaa käyttöön raporttien välillä porautumisen Power BI -palvelussa.
1. Valitse Power BI -palvelussa se työtila, joka sisältää kohde- ja lähderaporttisi.
1. Valitse työtilaluettelosta lähderaportin nimen vierestä **Lisäasetukset**-symboli ja valitse sitten **Asetukset**. 
1. Valitse läheltä **Asetukset**-ruudun alareunaa, kohdasta **Raporttien välillä porautuminen** **Salli visualisoinnit tässä raportissa, jos haluat käyttää porautumisen kohteita muista raporteista** ja valitse sitten **Tallenna**.
   
   ![Raporttien välillä porautumisen käyttöönotto Power BI -palvelussa](media/desktop-cross-report-drill-through/cross-report-drill-through-02a.png)

## <a name="set-up-a-cross-report-drillthrough-target"></a>Raporttien välisen porautumiskohteen määrittäminen

Kohdesivun määrittäminen raporttien väliselle porautumiselle on samanlaista kuin porautumisen määrittäminen raportin sisällä. Porautumisen käyttöönotto kohdesivulla sallii muiden visualisointien porautua sivuun. Porautumisen luomisesta yksittäisessä raportissa voit lukea kohteesta [Porautumisen käyttäminen Power BI Desktopissa](desktop-drillthrough.md).

Voit määrittää kohteen raporttien väliselle porautumiselle Power BI Desktopissa tai Power BI -palvelussa. 
1. Muokkaa kohdetiedostoa ja valitse kohderaportin kohdesivulla **Kentät**-osa **Visualisoinnit**-ruudusta. 
1. Määritä **Porautuminen**-kohdassa **Raporttien välillä** -valitsin asentoon **Käytössä**. 
1. Vedä kentät, joita aiot käyttää porautumiskohteina, **Lisää porautumiskentät tähän** -alueelle. Valitse jokaiselle kentälle, haluatko sallia porautumisen, kun kenttää käytetään luokkana, vai kun se summataan mittayksikkönä. 
1. Valitse, haluatko **säilyttää kaikki suodattimet** visualisoinnillesi. Jos et halua välittää lähdevisualisoinnissa käytössä olevia visualisointeja kohdevisualisoinnillesi, valitse **Ei käytössä**.
   
   ![Visualisoinnit-ruutu, jossa porautumisasetukset on korostettu](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)
   
1. Jos käytät sivua vain raporttien välillä porautumiseen, poista **Takaisin**-painike, joka lisätään automaattisesti pohjaan. **Takaisin**-painike toimii vain raportinsisäisessä siirtymisessä. 
1. Kun olet määrittänyt kohdesivun, tallenna raportti, jos käytät Power BI -palvelua, tai tallenna ja julkaise raportti, jos käytät Power BI Desktopia.

Siinä kaikki! Raporttisi ovat valmiita raporttien välillä porautumiseen. 

## <a name="use-cross-report-drillthrough"></a>Raporttien välillä porautumisen käyttö

Raporttien välillä porautumisen käyttämiseksi valitse lähderaportti Power BI -palvelusta ja valitse sitten visualisointi, joka käyttää porautumiskenttää kuten olet määrittänyt kohdesivua määrittäessäsi. Napsauta arvopistettä hiiren kakkospainikkeella visualisointien pikavalikon avaamiseksi, valitse **Porautuminen** ja valitse sitten porautumiskohde. Raporttien välisen porautumisen kohteet esitetään muodossa **Sivun nimi [Raportin nimi]**.

![Power BI:n raporttien välillä porautumisen asetus](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Näet tulokset raporttien välillä porautumisen kohderaportin sivulla, kuten määritit ne kohdetta luodessasi. Tulokset suodatetaan porautumisasetusten mukaan.

![Power BI Desktopin raporttien välillä porautumisen kohde](media/desktop-cross-report-drill-through/cross-report-drill-through-01a.png)

> [!IMPORTANT]
> Power BI tallentaa raportti välillä porautumisen kohteet välimuistiin. Jos teet muutoksia, muista päivittää selaimesi, jos et näe porautumiskohteita odotetulla tavalla. 

Jos määrität **Säilytä kaikki suodattimet** asentoon **Käytössä** määrittäessäsi kohdesivua, lähdevisualisoinnin suodatuskontekstiin voi sisältyä: 

- Raportti-, sivu- ja visualisointitason suodattimia, jotka vaikuttavat lähdevisualisointiin 
- Ristiinsuodatusta ja ristiinkorostusta, jotka vaikuttavat lähdevisualisointiin 
- Sivulla olevia osittajia ja synkronoinnin osittajia
- URL-parametrejä

Kun siirryt porauksen kohderaporttiin, Power BI käyttää suodattimia vain sellaisiin kenttiin, joilla on tarkat merkkijonovastaavuudet kenttänimen ja taulukkonimen osalta. 

Power BI ei käytä tahmeita suodattimia kohderaportista käsin, mutta se käyttää henkilökohtaista oletuskirjanmerkkiäsi, jos sinulla on sellainen. Jos esimerkiksi henkilökohtaisessa oletuskirjanmerkissäsi on raportti tason suodatin *Maa = USA*, Power BI soveltaa kyseistä suodatinta ennen lähdevisualisoinnin suodatuksen kontekstin soveltamista. 

Raporttien välillä porautumisessa Power BI välittää suodatuksen kontekstin kohderaportin vakiosivuille. Power BI ei välitä työkaluvihjesivujen suodatuksen kontekstia, koska työkaluvihjesivut suodatetaan työkaluvihjeen käynnistävän lähdevisualisoinnin perusteella.

Jos haluat palata lähderaporttiin, kun raporttien välillä porautuminen on suoritettu, käytä selaimen **Edellinen**-painiketta. 

## <a name="next-steps"></a>Seuraavat vaiheet

Voit olla kiinnostunut myös seuraavista artikkeleista:

- [Osittajat Power BI:ssä](visuals/power-bi-visualization-slicers.md)
- [Porautumisen käyttäminen Power BI Desktopissa](desktop-drillthrough.md)

