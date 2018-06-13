---
title: Power BI -raporttien nopea etsiminen ja tarkastelu ja raporttinäkymien käyttö Cortanan avulla
description: Käytä Cortanaa Power BI:n kanssa saadaksesi vastauksia tiedoistasi. Tämä toimii tällä hetkellä raporttien ja raporttinäkymien kanssa.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
editor: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/13/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 11bba0ec026650e59b8757b207f5f6d596499f0a
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815424"
---
# <a name="quickly-find-and-view-your-power-bi-data-using-cortana-for-power-bi"></a>Power BI -tietojen nopea etsiminen ja tarkastelu Power BI:n Cortana-ominaisuuden avulla
Saat heti vastauksia liiketoimintaa koskeviin tärkeisiin kysymyksiisi Windows 10 -laitteilla Cortanan avulla. Power BI -integraation avulla Cortana voi noutaa avaintietoja suoraan Power BI -raporttinäkymistä ja -raporteista. Tarvitset vain Windows 10:n marraskuun 2015 version tai sitä uudemman, Cortanan, Power BI:n ja vähintään yhden tietojoukon käyttöoikeudet.

![Cortana-hakukenttä](media/service-cortana-intro/power-bi-cortana-searchbox.png)

## <a name="preview-the-new-cortana-dashboard-search-experience-for-windows-10"></a>Esikatsele uuden Cortana *-raporttinäkymän* hakukokemusta Windows 10:llä
Aiemmin [Cortanan avulla on voinut noutaa tietyntyyppisiä raporttisivuja](service-cortana-answer-cards.md). Nyt olemme lisänneet **uuden käyttökokemuksen**: mahdollisuuden hakea myös raporttinäkymiä. Kokeile sitä ja [lähetä meille palautetta ](mailto:pbicortanasg@microsoft.com). *Uutta käyttökokemusta* laajennetaan niin, että lopulta se sisältää myös raporttien Cortana-haun.  Eräs uuden käyttökokemuksen suurimmista eduista on se, että sen käyttöönottoon ei vaadita mitään erityistä, kuten Cortanan käyttöönottoa tai Windows 10:n määrittämistä. Se vain toimii.

> [!NOTE]
> Jos se ei ”vain toimi”, tutustu [vianmääritysartikkelin](service-cortana-troubleshoot.md) ohjeisiin.
> 
> 

Pohjana oleva tekniikka perustuu [Microsoftin Azure Search -palveluun](). Kyseinen hakupalvelu sisältää lisätoimintoja, kuten älykkään luokittelun, virheenkorjauksen ja automaattisen täydentämisen.

Molemmat Cortana-käyttökokemukset ovat käytettävissä rinnakkain.

## <a name="cortana-for-power-bi-documentation"></a>Power BI:n Cortana-ominaisuuden ohjeet
Seuraavat neljä asiakirjaa opastavat Cortanan määrittämisessä ja käyttämisessä Power BI:ssä. Tämä artikkelisarja käsittelee seuraavat vaiheet:

**Artikkeli 1** (tämä artikkeli): Opit ymmärtämään, miten Cortana ja Power BI toimivat yhdessä

**Artikkeli 2**: [Hakeminen Power BI -raporteista: Cortanan käyttöönotto ja integrointi Power BI:hin Windowsissa](service-cortana-enable.md)

**Artikkeli 3**: [Hakeminen Power BI -raporteista: erityisten *Cortana-vastauskorttien luominen*](service-cortana-answer-cards.md)

**Artikkeli 4**: [Ongelmien vianmääritys](service-cortana-troubleshoot.md)

## <a name="how-do-cortana-and-power-bi-work-together"></a>Miten Cortana ja Power BI toimivat yhdessä?
Cortanan avulla voit esittää kysymyksiä, joihin Cortana voi etsiä vastauksia mm. Power BI:stä. Cortana voi etsiä Power BI -raporteista monipuolisia aineistoperäisiä vastauksia (jotka sisältävät *Cortana-vastauskorteiksi* kutsuttuja erityisiä raporttisivuja) ja Power BI -raporttinäkymiä.

Jos Cortana löytää vastauksen, se näyttää kyseisen raporttinäkymän tai raportin nimen suoraan Cortana-ruudulla. Voit avata raporttinäkymän tai raportin sivun Power BI:ssä. Raportin sivuja voi tarkastella myös suoraan Cortanassa – ne ovat vuorovaikutteisia.

![vuorovaikutteinen raporttisivu Cortanassa](media/service-cortana-intro/power-bi-report-cortana-s.png)

### <a name="cortana-and-dashboards-the-new-experience"></a>Cortana ja raporttinäkymät ( *uusi käyttökokemus*)
Cortana voi etsiä vastauksia omistamistasi raporttinäkymistä ja raporttinäkymistä, jotka on jaettu kanssasi. Kysy Cortanalta kysymyksiä otsikoiden, avainsanojen, omistajien nimen, työtilan nimen, sovellusten nimen tai muun ehdon perusteella.

Kysymyksessä on oltava vähintään kaksi sanaa, jotta Cortana voi etsiä vastausta. Jos etsit raporttinäkymää, jonka nimi on yksi sana (”Markkinointi”) lisää ”näytä” tai ”Power BI” tai ”<owner name>” kysymykseesi, esim. ”Näytä Markkinointi” ja ”michele hart otos”. 

Jos raporttinäkymän otsikossa on enemmän kuin yksi sana, Cortana osaa toimittaa raporttinäkymän, jos hakusi vastaa vähintään kahta otsikon sanoista tai jos raporttinäkymä vastaa yhtä sanoista ja omistajan nimeä. Käytetään esimerkkinä raporttinäkymää, jonka nimi on ”Asiakkaan tuottavuuden malli”: 

* ”näytä asiakkaan” -hakusanat *eivät* palauta Power BI -raporttinäkymätulosta.   
* Sen sijaan ”näytä asiakkaan tuottavuuden”, ”asiakkaan t”, ”asiakkaan m”, ”tuottavuuden otos”, ”michele hart otos”, ”näytä asiakkaan tuottavuuden otos” ja ”näytä asiakkaan t” *palauttavat* Power BI -hakutuloksen.
* ”Powerbi”-sanan lisääminen lasketaan toiseksi kahdesta vaadittavasta sanasta, joten ”powerbi otos” *palauttaa* hakutuloksen Power BI:ssä. 
  
    ![Cortana-haku, jossa on vähintään kaksi sanaa](media/service-cortana-intro/power-bi-cortana-2-words.png)

### <a name="cortana-and-reports"></a>Cortana ja raportit
 Cortana voi etsiä vastauksia raporteista, joissa on [erityisesti Cortanassa näytettäväksi suunniteltuja sivuja](service-cortana-answer-cards.md). Esitä kysymys käyttämällä tällaisten erikoissivujen otsikkoa tai avainsanoja.  

Raporttien tekniikka perustuu [Microsoftin Power BI Q&A](power-bi-q-and-a.md):han.

Kun esität Cortanalle kysymyksen, Power BI antaa vastaukseksi erityisesti Cortanalle suunniteltuja raporttisivuja. Cortana selvittää mahdolliset vastaukset lennosta suoraan Power BI:ssä luoduista Cortanan *vastauskorteista*.  Voit tutustua vastaukseen tarkemmin avaamalla tuloksen Power BI:ssä.

> [!NOTE]
> Ennen kuin Cortana voi hakea vastauksia Power BI -raporteista, sinun on [otettava tämä ominaisuus käyttöön Power BI -palvelussa ja määrittää Windowsin ja Power BI:n välinen tiedonsiirto](service-cortana-enable.md).  
> 
> 

## <a name="using-cortana-to-get-answers-from-power-bi"></a>Vastauksien hakeminen Power BI:stä Cortanan avulla
1. Aloita Cortanasta. Voit *avata* Cortanan eri tavoilla: valitsemalla Cortana-kuvakkeen tehtäväpalkista (kuvassa alla), äänikomennolla tai napauttamalla Windows-mobiililaitteen hakukuvaketta.
   
     ![](media/service-cortana-intro/power-bi-cortana-searchbox.png)
2. Kun Cortana on valmis, kirjoita kysymyksesi Cortanan hakupalkkiin tai sano se ääneen. Cortana näyttää käytettävissä olevat tulokset. Jos Power BI -raporttinäkymä vastaa kysymystä, se näkyy kohdassa **Paras vastaavuus** tai **Power BI**.
   
     ![Cortana-haku löytää Power BI -raporttinäkymän](media/service-cortana-intro/power-bi-cortana-search-hr.png "Cortana löytää Power BI -raporttinäkymän")
   
   > [!NOTE]
   > Tällä hetkellä Cortanaa tuetaan vain englanniksi.
   > 
   > 
3. Valitse raporttinäkymä avataksesi sen Cortanassa.

    ![Valitse Power BI -raporttinäkymä](media/service-cortana-intro/power-bi-cortana-dashboard.png "Valitse Power BI -raporttinäkymä")

    Voit muuttaa asettelua [muokkaamalla koontinäytön *puhelinnäkymää*](service-create-dashboard-mobile-phone-view.md). 

1. Cortanasta voit halutessasi avata raporttinäkymän Power BI -palvelussa tai Power BI -mobiilisovelluksessa. Avaa raporttinäkymä Power BI -palvelussa valitsemalla **Avaa verkossa**. 
   
   ![Avaa raporttinäkymä Cortanasta](media/service-cortana-intro/power-bi-dashboard-opens.png "Avaa raporttinäkymä Cortanasta")   
4. Haetaan nyt raporttia Cortanan avulla. Tarvitsemme [raportin, jossa on Cortana-vastauskortin sisältävä sivu ](service-cortana-answer-cards.md). Tässä esimerkissä raportissa nimeltä ”Cortana-New-Stores” on Cortana-vastauskortti ”cortana stores” -sivulla.  
   
     Kirjoita kysymyksesi Cortanan hakupalkkiin tai sano se ääneen. Cortana näyttää käytettävissä olevat tulokset. Jos Power BI -raporttisivu vastaa kysymystä, se näkyy kohdassa **Paras vastaavuus** tai **Power BI**. Tässä esimerkissä vastauskortin luomiseen käyttämäni .pbix-tiedosto (ja varmuuskopio) näkyy myös -- **Asiakirjat**-kohdassa.
   
     ![Raportin etsiminen](media/service-cortana-intro/power-bi-cortana-search3-m.png "raportin etsiminen") 
5. Valitse **Cortana stores** -raporttisivu näytettäväksi Cortana-ikkunassa.
   
    ![raporttisivu avautuu Cortanassa](media/service-cortana-intro/power-bi-report-cortana-opens.png "raporttisivu avautuu Cortanassa")   
   
    Muista, että *vastauskortti* on erityinen Power BI -raporttisivu, jonka tietoryhmän omistaja on luonut.  Lisätietoja on kohdassa [Cortana-vastauskortin luominen](service-cortana-answer-cards.md).
6. Eikä siinä vielä kaikki. Voit käsitellä vastauskortin visualisointeja samalla tavalla kuin Power BI:ssä.
   
   * Voit valita esimerkiksi yhden ristiinsuodatettavan visualisoinnin ja korostaa vastauskortin muut visualisoinnit.
     
     ![](media/service-cortana-intro/power-bi-cortana-filtered-new.png)
   * Luonnollisen kielen suodattimen avulla voit suodattaa tulokset.  Voit esimerkiksi kysyä ”Cortana stores for Lindseys” ja saada suodattimien ansiosta vain Lindseys-ketjun tiedot kortissa.
     
     ![ristiinsuodatus Cortanassa](media/service-cortana-intro/power-bi-cortana-filtered-2.png "ristiinsuodatus Cortanassa")
7. Jatka tutustumista. Vieritä Cortana-ikkunan alareunaan ja valitse **Avaa Power BI:ssä**.
   
     ![](media/service-cortana-intro/power-bi-cortana-open-new.png)
8. Raporttisivu avautuu Power BI:ssä.    
     ![Avaa raportti Cortanasta](media/service-cortana-intro/power-bi-cortana-open2.png "Cortana-vastauskortti avautuu Cortana-haussa")

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
* Cortanalla ei ole pääsyä Cortana-kortteihin, joita ei ole [otettu käyttöön Power BI:ssä](service-cortana-enable.md).
* Mitä jos Cortana ei vieläkään toimi Power BI:ssä?  Kokeile [Cortanan vianmääritystä](service-cortana-troubleshoot.md).
* Power BI:n Cortana-ominaisuus on tällä hetkellä käytettävissä vain englanniksi.
* Power BI:n Cortana-ominaisuus on käytettävissä vain Windows-mobiililaitteissa.

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

## <a name="next-steps"></a>Seuraavat vaiheet
[Cortanan käyttöönotto ja integrointi Power BI:hin Windowsissa](service-cortana-enable.md)
