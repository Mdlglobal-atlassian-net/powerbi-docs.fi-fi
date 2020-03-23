---
title: Sivutetut raportit Power BI -palvelussa
description: Asiakirjat, jotka kuvaavat sivutettuja raportteja ja miten niitä voi tarkastella Power BI-palvelussa
author: mihart
ms.reviewer: chris finlan
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: c4c21dc0f02e547cd7319d789a3eb66cce1f4b88
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/14/2020
ms.locfileid: "79377347"
---
# <a name="paginated-reports-in-the-power-bi-service"></a>Sivutetut raportit Power BI -palvelussa

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

Olet opiskellut [Power BI -raportteja](end-user-reports.md), ja ne ovat raporttityyppejä, joita todennäköisimmin kohtaat. On kuitenkin olemassa toinen raporttityyppi, jota kutsutaan *sivutetuksi raportiksi*. Raportin *suunnittelijat* voivat jakaa sivutettuja raportteja kanssasi Premium-kapasiteetissa tai sovelluksessa kyseisestä työtilasta. 

## <a name="what-is-a-paginated-report"></a>Mikä on sivutettu raportti?

Raporttia kutsutaan *sivutetuksi*, koska se on muotoiltu sopimaan hyvin tulostetulle sivulle. Eräs eduista on, että sivutetussa raportissa kaikki taulukoiden tiedot näytetään, vaikka taulukko olisi useita sivuja pitkä. Sivutettuja raportteja kutsutaan joskus pikselintarkasti täydellisiksi, koska *suunnittelija* voi hallita raportin sivuasettelua tarkasti.

Kun *suunnittelet* sivutetun raportin, luot tosiasiassa *raportin määrityksen*. Se ei sisällä tietoja. Se määrittää, mistä tiedot haetaan, mitkä tiedot haetaan ja miten tiedot näytetään. Kun raportti suoritetaan, raportin käsittelytoiminto luo raportin yhdistämällä raportin määrityksen noudettuihin tietoihin. Joskus raportti näyttää oletustiedot. Muussa tapauksessa sinun on syötettävä parametreja, ennen kuin raportti voi näyttää tietoja. 

   ![Raportin parametrit](./media/end-user-paginated-report/power-bi-report-parameters.png)

Tavallisesti parametrien vuorovaikutuksen laajuus jää parametrien asettamiseen. Jos olet laskutusanalyytikko, voit käyttää sivutettuja raportteja laskujen luontiin tai tulostamiseen. Jos olet myyntipäällikkö, voit käyttää sivutettuja raportteja, kun haluat tarkastella tilauksia myymälän tai myyntihenkilön mukaan. 

Tämä yksinkertainen sivutettu raportti antaa tulot vuosittain, kun olet valinnut **vuosi**-parametrin. 

![Yksinkertainen yhden parametrin raportti](./media/end-user-paginated-report/power-bi-report-simple.png)

Power BI -raportit ovat paljon vuorovaikutteisempia verrattuna sivutettuihin raportteihin. Power BI -raportit mahdollistavat ad-hoc-raportoinnin ja tukevat monia muita visualisointityyppejä, mukaan lukien Power BI -visualisoinnit.

## <a name="identify-a-paginated-report"></a>Tunnista sivutettu raportti

Sisältöluetteloissa ja aloitussivulla sivutetut raportit voi tunnistaa ![sivutetun raportin kuvakkeesta](media/end-user-paginated-report/power-bi-report-icon.png).  Sivutettu raportti voidaan jakaa suoraan tai osana [Power BI -sovellusta](end-user-apps.md). Jos raportin *suunnittelija* on antanut sinulle käyttöoikeudet, voit jakaa sivutetun raportin uudelleen ja tilata sen itsellesi ja muille.

![eri kuvakkeita näyttävä raporttiluettelo](./media/end-user-paginated-report/power-bi-report-list.png)

## <a name="interact-with-a-paginated-report"></a>Sivutetun raportin kanssa toimiminen

Sivutetun raportin käsitteleminen eroaa muista raporteista. Voit tehdä eri asioita, kuten tulostaa, lisätä kirjanmerkkejä, viedä raportin ja kommentoida sitä, mutta vuorovaikutteisuutta on vähemmän. Sivutetut raportit edellyttävät usein syötettä raportin pohjalle.  Joskus raportti voi näyttää oletustiedot, ja voit syöttää parametreja nähdäksesi eri tietoja.

### <a name="print-a-paginated-report"></a>Sivutetun raportin tulostaminen

*Sivutetut* raportit muotoillaan sopimaan hyvin tulostetulle sivulle. Näet selaimessa suoraan tulostustuloksen. Lisäksi jos raportissa on pitkä taulukko, koko taulukko tulostuu, vaikka se olisi usealla sivulla. 

Sivutetuissa raporteissa voi olla useita sivuja. Esimerkiksi tässä raportissa on 563 sivua. Jokainen sivu on aseteltu tarkasti yksi sivu laskua kohti -muotoon, ja ylä- ja alatunnisteet toistuvat kaikissa. Kun tulostat tämän raportin, laskujen välille tulee sivunvaihdot.

   ![Sivu yksi sivutetusta raportista, Tailspin Toys](./media/end-user-paginated-report/power-bi-paginated-500.png)


### <a name="navigate-the-paginated-report"></a>Sivutetussa raportissa liikkuminen

Tässä myyntitilausraportissa on kolme parametria: Yritystyyppi, jälleenmyyjä ja tilausnumero. 

![raportti, jossa on kolme parametria](./media/end-user-paginated-report/power-bi-parameter.png)

Jos haluat muuttaa näytettäviä tietoja, anna uudet arvot kolmelle parametrille ja valitse **Näytä raportti**. Tässä olemme valinneet **Specialty Bike Shopin**, **Alpine Ski Housen**ja tilausnumeron **SO46085**. Kun valitset **Näytä raportti**, raporttipohjaan päivitetään tämä uusi myyntitilaus.

![parametrien muuttaminen](./media/end-user-paginated-report/power-bi-order.png)

Uusi myyntitilaus näytetään käyttäen valittuja parametreja. 

![uusi myyntitilaus](./media/end-user-paginated-report/power-bi-new-order.png)

Joissain sivutetuissa raporteissa voi olla useita sivuja.  Sivun ohjausobjektien avulla voit siirtyä raportissa. 

![sivun ohjausobjektit](./media/end-user-paginated-report/power-bi-page.png)

### <a name="export-the-paginated-report"></a>Sivutetun raportin vienti
Sinulla on useita vaihtoehtoja sivutettujen raporttien vientiin, mukaan lukien PDF, Word, XML, PowerPoint, Excel ja monia muita. Viennissä säilytetään mahdollisimman paljon muotoilua. Esimerkiksi Excel-, Word-, PowerPoint-, MHTML- ja PDF-muotoon viedyt sivutetut raportit säilyttävät ”pikselintarkasti täydellisen” muotoilun. 

![uusi myyntitilaus](./media/end-user-paginated-report/power-bi-exporting.png)

![neljä eri vientityyppiä](./media/end-user-paginated-report/power-bi-four.png)

### <a name="subscribe-to-the-paginated-report"></a>Sivutetun raportin tilaus
Kun tilaat sivutetun raportin, Power BI lähettää sinulle sähköpostiviestin, joka sisältää raportin liitteenä. Kun määrität tilauksia, valitset kuinka usein haluat saada sähköpostiviestejä: päivittäin, viikoittain, tunneittain tai kuukausittain. Tilaus sisältää raportin täydelliset tulokset PDF-liitteenä 25 Mt:n kokoon asti. Vie koko raportti tai valitse parametrit etuajassa. Valitse useista eri liitetyypeistä, kuten Excel, PDF, PowerPoint ja monia muita.  

![Tilausmuodot](./media/end-user-paginated-report/power-bi-export-list.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

- Sivutettu raportti voi olla tyhjä, kunnes valitset parametrit ja valitset **Näytä raportti**.

- Jos sinulla ei ole sivutettuja raportteja, se voi johtua siitä, että kukaan ei ole jakanut tämäntyyppistä raporttia kanssasi. Se voi tarkoittaa myös sitä, että järjestelmänvalvojasi ei ole ottanut sivutettuja raportteja käyttöön puolestasi. 

 

## <a name="next-steps"></a>Seuraavat vaiheet
- [Power BI -raportit](end-user-reports.md)
- Onko sinulla kysyttävää? Kokeile [Power BI -yhteisöä](https://community.powerbi.com/).

