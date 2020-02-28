---
title: Raporttitiedot Power BI:n raportin muodostimessa
description: Kun koostat raporttia Power BI:n raportin muodostimessa, ensimmäisessä vaiheessa luot pohjana olevia raporttitietoja vastaavat tietolähteet ja tietojoukot.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.custom: seodec18
ms.date: 06/06/2019
ms.openlocfilehash: f8f7d3b43cfc2d5a51b686598c1657ec21b44130
ms.sourcegitcommit: b22a9a43f61ed7fc0ced1924eec71b2534ac63f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/21/2020
ms.locfileid: "77527265"
---
# <a name="report-data-in-power-bi-report-builder"></a>Raporttitiedot Power BI:n raportin muodostimessa

Raporttitiedot voivat olla peräisin useista organisaatiosi lähteistä. Kun koostat raporttia Power BI:n raportin muodostimessa, ensimmäisessä vaiheessa luot pohjana olevia raporttitietoja vastaavat tietolähteet ja tietojoukot. Jokainen tietolähde sisältää tietoyhteyden tiedot. Jokainen tietojoukko sisältää kyselykomennon, joka määrittää, mitä tietolähteen kenttiä käytetään tietoina. Voit visualisoida kunkin tietojoukon tiedot lisäämällä tietoalueen, kuten taulukon, matriisin, kaavion tai kartan. Kun raportti on käsitelty, tietolähteelle suoritetaan kyselyt ja tietoalueet laajenevat tarvittaessa niin, että niissä näkyy kyselyn tulokset.  

Katso, miten voit [luoda sivutettuun raporttiin upotettavan tietolähteen Power BI:n raportin muodostimessa](paginated-reports-embedded-data-source.md).


##  <a name="BkMk_ReportDataTerms"></a> Ehdot  
  
- **Tietoyhteys.** Tunnetaan myös *tietolähteenä*. Tietoyhteys sisältää yhteystyypistä riippuvaisen nimen ja yhteyden ominaisuudet. Tietoyhteys on suunniteltu niin, että se ei voi sisältää tunnistetietoja. Tietoyhteys ei määritä, mitä tietoja ulkoisesta tietolähteestä noudetaan. Voit tehdä tämän määrittämällä kyselyn tietojoukkoa luodessasi.  
  
- **Yhteysmerkkijono.** Yhteysmerkkijono on yhteysasetusten merkkijonoversio, jota tarvitaan muodostettaessa yhteyttä tietolähteeseen. Yhteyden ominaisuudet vaihtelevat tietoyhteyden tyypin mukaan.  
  
- **Upotettu tietolähde.** Kutsutaan myös *raporttikohtaiseksi tietolähteeksi*. Tietolähde, joka on määritetty raportissa ja jota vain kyseinen raportti käyttää.  
  
- **Tunnistetiedot.** Tunnistetiedot ovat todennustietoja, jotka sinun on annettava, jotta voit käyttää ulkoisia tietoja.  
  
##  <a name="BkMk_ReportDataTips"></a> Vihjeitä raporttitietojen määrittämiseen

 Käytä seuraavia tietoja suunnitellessasi lähestymistapaasi raporttitietoihin.  
  
- **Tietojen suodattaminen** Raporttitiedot voidaan suodattaa kyselyssä tai raportissa. Voit käyttää tietojoukkoja ja kyselymuuttujia luodaksesi johdannaisparametreja ja salliaksesi käyttäjän rajata tuhansien vaihtoehtojen joukosta helpommin hallittavan määrän. Voit suodattaa tiedot taulukossa tai kaaviossa itse tai jonkun muun määrittämien parametriarvojen perusteella.  
  
- **Parametrit** Kyselymuuttujia sisältävät tietojoukon kyselykomennot luovat automaattisesti vastaavat raporttiparametrit. Voit luoda parametreja myös manuaalisesti. Kun tarkastelet raporttia, parametrit näkyvät raporttityökalurivillä. Käyttäjät voivat valita raporttitietojen tai raportin ulkoasun hallinta-arvot. Voit mukauttaa raporttitiedot tietylle käyttäjäryhmälle luomalla raporttiparametrien ryhmän, jonka eri oletusarvot on linkitetty samaan raporttimääritykseen, tai käyttämällä sisäistä **Käyttäjätunnus**-kenttää. 
  
- **Ryhmitellyt ja koostetiedot** Raporttitiedot voidaan ryhmitellä ja koostaa kyselyssä tai raportissa. Jos koostat arvot kyselyssä, voit yhdistää raportin arvoja merkityksellisyyden rajoissa.  
  
- **Tietojen lajittelu** Raporttitiedot voidaan lajitella kyselyssä tai raportissa. Taulukoissa voit myös lisätä vuorovaikutteisen lajittelupainikkeen, jonka avulla käyttäjä voi hallita lajittelujärjestystä.  
  
- **Lausekkeisiin perustuvat tiedot** Koska useimmat raportin ominaisuudet voivat olla lausekepohjaisia ja koska lausekkeet voivat sisältää viittauksia tietojoukkokenttiin ja raporttiparametreihin, voit kirjoittaa tehokkaita lausekkeita, joiden avulla voit hallita raportin tietoja ja ulkoasua. Voit antaa käyttäjän hallita näkemiään tietoja määrittämällä parametreja.  
  
- **Tietojoukon tietojen näyttäminen** Tietojoukon tiedot näytetään yleensä yhdessä tai useammassa tietoalueessa, esim. taulukossa ja kaaviossa.  
  
- **Usean tietojoukon tietojen näyttäminen** Voit kirjoittaa tietoalueelle lausekkeita, jotka perustuvat yhteen tietojoukkoon, joka hakee tai koostaa tietoja muista tietojoukoista. Voit sisällyttää taulukkoon tietojoukkoon perustuvia aliraportteja, jotka näyttävät tietoja toisesta tietolähteestä.  
  
 Seuraavan luettelon avulla voit määrittää raportin tietolähteet.  
  
- Tutustu organisaatiosi ohjelmistojen tietokerrosarkkitehtuuriin ja tietotyypeistä mahdolliset johtuviin ongelmiin. Ymmärrä, miten tietolaajennukset ja tietojen käsittelylaajennukset voivat vaikuttaa kyselytuloksiin. Tietotyypit vaihtelevat lähteen tietojen, tietopalvelujen ja raporttimääritystiedostoon (.rdl) tallennettujen tietotyyppien mukaan.  
  
- Tietolähteet ja tietojoukot tehdään raportissa ja julkaistaan Power BI -palveluun. Kun ne on julkaistu, voit määrittää tunnistetiedot suoraan Power BI -palvelussa tai yrityksen yhdyskäytävässä. 

## <a name="next-steps"></a>Seuraavat vaiheet

- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)  
- [Sivutettujen raporttien tietojen nouto-ohjeet](guidance/report-paginated-data-retrieval.md)
