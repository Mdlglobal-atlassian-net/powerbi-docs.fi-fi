---
title: Luo mukautettuja Power BI -vastaussivuja Cortanaa varten
description: Luo mukautettuja vastaussivuja Cortanaa varten Power BI:ssä
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 06f155676dffa7b5f87ce61a8b342708793ef2c6
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73853737"
---
# <a name="use-power-bi-service-or-power-bi-desktop-to-create-a-custom-answer-page-for-cortana"></a>Käytä Power BI -palvelua tai Power BI Desktopia luodaksesi mukautettuja vastaussivuja Cortanaa varten
Hyödynnä Power BI:n kaikkia ominaisuuksia ja luo erityisiä raporttisivuja, joita kutsutaan *Cortana-vastaussivuiksi* (sekä joskus nimellä *Cortana-vastauskortit*), ja jotka on suunniteltu vastaamaan erityisesti Cortana-kysymyksiin.

> [!IMPORTANT]
> Cortanan integrointi on vanhentumassa Power BI:ssä. 11. kesäkuuta alkaen Cortana ei enää toimi koontinäyttöjen ja raporttien kanssa.

![](media/service-cortana-answer-cards/power-bi-cortana.png)

## <a name="before-you-begin"></a>Alkutoimet
Neljä asiakirjaa opastavat Cortanan määrittämisessä ja käyttämisessä Power BI:ssä. Aloita lukemalla artikkeli 1, jos et ole vielä tehnyt niin. Artikkeli 2 on erityisen tärkeä, koska siinä käsitellään joitakin vaiheita, jotka on suoritettava, ennen kuin voit käyttää Cortana-vastaussivuja.

**Artikkeli 1**: [Opi kuinka Cortana ja Power BI toimivat yhdessä](service-cortana-intro.md)

**Artikkeli 2**: [Power BI -raporttien hakeminen: Cortanan käyttöönotto ja integrointi Power BI:hin Windowsissa](service-cortana-enable.md)

**Artikkeli 3**: Tämä artikkeli

**Artikkeli 4**: [Ongelmien vianmääritys](service-cortana-troubleshoot.md)

## <a name="create-a-cortana-answer-page-designed-specifically-for-cortana"></a>Cortanalle erityisesti suunnitellun Cortana-vastaussivun luominen
Raportissa esiintyvän *Cortana-vastaussivun* koko on suunniteltu niin, että Cortana voi näyttää sen näytöllä vastauksena kysymykseen. Cortana-vastaussivun luominen:

1. Suosittelemme aloittamaan tyhjällä raporttisivulla.
2. Valitse **Visualisoinnit**-ruudussa maalirullakuvake ja valitse**Sivun koko** > **Tyyppi** > **Cortana**.
   
    ![](media/service-cortana-answer-cards/pbi-cortana-page-size-new.png)
3. Luo visualisointi tai joukko visualisointeja, joiden haluavat näkyvän Cortanassa, vastauksena tiettyyn kysymykseen (tai joukkoon kysymyksiä).

> [!NOTE]
> Tällä hetkellä Cortana-vastaussivut eivät tue kuvia, joissa näytetään staattisia kuvia. Voit sisällyttää kuvia taulukon tai matriisin visualisointeihin, jotka kootaan dynaamisesti tietojen URL-osoitteen perusteella. 
> 
> 

4. Varmista, että visualisoinnit on sovitettu sivun reunuksiin. Voit halutessasi muokata näytön asetuksia, arvopisteiden nimiä, värejä ja taustoja.  
   
    ![](media/service-cortana-answer-cards/pbi_cortana_modify-new.png)
5. Nimeä sivu ja lisää vaihtoehtoisia nimiä. Cortana käyttää näitä nimiä etsiessään tuloksia. Valitse **Visualisointi**-ruudussa sivellinkuvake ja sitten **Sivun tiedot**. Ota visualisoinnille Q&A käyttöön siirtämällä liukusäädin **Päällä**-asentoon.
   
    ![](media/service-cortana-answer-cards/pbi_cortana_names-newer.png)
   
   > [!TIP]
   > Saat parempia hakutuloksia välttämällä sarakkeiden nimien käyttöä.
   > 
   > 
6. Vaihtoehtoisesti jos raportissasi on sivutason suodattimet, voit halutessasi ottaa **Edellytä yksittäistä valintaa** -asetuksen käyttöön. Cortana näyttää kyseisen raportin vastaukseksi jos yksi, ja vain yksi, suodatinkohteista on määritelty kysymyksessä. **Edellytä yksittäistä valintaa** -asetus löytyy **Suodattimet**-ruudun alareunasta.
   
   > [!NOTE]
   > **Edellytä yksittäistä valintaa** -asetusta ei tarvitse välttämättä ottaa käyttöön, pyytääksesi Cortanaa näyttämään raportin, jossa on sivutason suodattimet. Esimerkiksi ”näytä Charlotte Lindseyn myynnit” -haku näyttää vastaussivun, edellytä yksittäistä valintaa -asetuksesta riippumatta.
   > 
   > 
   
     ![](media/service-cortana-answer-cards/pbi-cortana-single-selection-new.png)
   
      Jos esimerkiksi pyydät Cortanaa:
   
   * "näytä myynnit myymälän nimen mukaan", kyseistä vastaussivua ei näytetä, koska hakuun ei sisällytetty mitään vaaditun sivutason suodattimen kohteita.
   * "näytä Cary Lindseyn ja Charlotte Lindseyn myynnit", kyseistä vastaussivua ei näytetä, koska hakuun määritettiin useampi kuin yksi kohde vaaditulta sivutason suodattimelta.
   * "näytä Charlotte Lindseyn myynnit" puolestaan näyttää kyseisen vastaussivun.
     
     = "näytä myynnit”, kyseistä vastaussivua ei näytetä, koska hakuun ei sisällytetty mitään vaaditun sivutason suodattimien kohteita.

> [!IMPORTANT]
> Cortana ei voi käyttää Cortana-vastaussivua ennen kuin [Ota tietojoukko käyttöön Cortanalle](service-cortana-enable.md) -asetus on päällä.
> 
> 

## <a name="how-does-cortana-order-the-results"></a>Miten Cortana järjestää tulokset?
Tulokset, joiden vastauksilla on suuri pistemäärä (kuten täydellinen vastaavuus määritetyn sivun nimen kanssa) näkyvät ensimmäisinä Cortanassa*parhaina vastineina*. Useita parhaita vastineita voi esiintyä, jos Power BI:ssä on useita Cortana-vastaussivuja. Keskimääräisen tai sitä matalammat pistemäärän saaneita vastauksia, kuten sellaisia, jotka eivät perustu vastaussivun nimeen, tai jos kysymyksessä on käytetty sanoja, joita Power BI ei ymmärrä, listataan linkkeinä parhaiden vastineiden alapuolella.

> [!NOTE]
> Kun uusi tietojoukko tai mukautettu Cortana-vastaussivu lisätään Power BI:hin ja otetaan käyttöön Cortanassa, voi kestää jopa 30 minuuttia, että tulokset alkavat näkyä Cortanassa. Sisään- ja uloskirjautuminen Windows 10:en tai Cortanan uudelleenkäynnistäminen Windows 10:ssä tuo uuden sisällön heti näkyviin.
> 
> 

## <a name="next-steps"></a>Seuraavat vaiheet
[Cortanan käyttö Power BI:ssä](service-cortana-intro.md)

Mitä jos Cortana ei vieläkään toimi Power BI:ssä?  Kokeile [Cortanan vianmääritystä](service-cortana-troubleshoot.md).

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

