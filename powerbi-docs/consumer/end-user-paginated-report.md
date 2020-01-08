---
title: Sivutetut raportit Power BI -palvelussa
description: Asiakirjat, jotka kuvaavat sivutettuja raportteja ja miten niitä voi tarkastella Power BI-palvelussa
author: mihart
ms.reviewer: chris finlan
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 12/02/2019
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: a66189707bc6b688be012eeb59881ce4a8517ea1
ms.sourcegitcommit: e492895259aa39960063f9b337a144a60c20125a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/05/2019
ms.locfileid: "74830485"
---
# <a name="paginated-reports-in-the-power-bi-service"></a>Sivutetut raportit Power BI -palvelussa
Olet opiskellut [Power BI -raportteja](end-user-reports.md), ja ne ovat raporttityyppejä, joita todennäköisimmin kohtaat. On kuitenkin olemassa toinen raporttityyppi, jota kutsutaan *sivutetuksi raportiksi*. Raportin *suunnittelijat* voivat jakaa sivutettuja raportteja kanssasi Premium-kapasiteetissa tai sovelluksessa kyseisestä työtilasta. 

## <a name="what-is-a-paginated-report"></a>Mikä on sivutettu raportti?

Raporttia kutsutaan *sivutetuksi*, koska se on muotoiltu sopimaan hyvin sivulle. Eräs eduista on, että niissä kaikki tiedot näytetään taulukossa, vaikka taulukko olisi useita sivuja pitkä. Niitä kutsutaan joskus pikselintarkasti täydellisiksi, koska *suunnittelija* voi hallita tarkasti niiden asettelua raportin sivulla.

Kun *suunnittelet* sivutetun raportin, luot tosiasiassa *raportin määrityksen*. Se ei sisällä tietoja. Se määrittää, mistä tiedot haetaan, mitkä tiedot haetaan ja miten tiedot näytetään. Kun raportti suoritetaan, raportin käsittely käyttää raportin määritystä, noutaa tiedot ja yhdistää ne raportin asetteluun raportin luomiseksi. Joskus raportti näyttää oletustiedot. Muina aikoina sinun on syötettävä parametreja, ennen kuin raportti voi näyttää tietoja. 

   ![Raportin parametrit](./media/end-user-paginated-report/power-bi-report-parameters.png)

Kyseessä on tavallisesti parametrien vuorovaikutuksen laajuus. Jos olet laskutusanalyytikko, voit käyttää sivutettuja raportteja laskujen luontiin tai tulostamiseen. Jos olet myyntipäällikkö, voit käyttää sivutettuja raportteja tilausten katselemiseksi myymälän tai myyntihenkilön perusteella. 

Tämä yksinkertainen sivutettu raportti antaa tulot vuosittain, kun olet valinnut **vuosi**-parametrin. 

![Yksinkertainen yhden parametrin raportti](./media/end-user-paginated-report/power-bi-report-simple.png)

Power BI -raportit ovat paljon vuorovaikutteisempia verrattuna sivutettuihin raportteihin. Power BI -raportit mahdollistavat ad-hoc-raportoinnin ja tukevat monia muita visualisointien tyyppejä, mukaan lukien mukautetut visualisoinnit.

## <a name="identify-a-paginated-report"></a>Tunnista sivutettu raportti

Sisältöluetteloissa ja aloitussivullasi sivutetut raportit voidaan tunnistaa ![sivutetun raportin kuvakkeesta](media/end-user-paginated-report/power-bi-report-icon.png).  Sivutettu raportti voidaan jakaa suoraan tai osana [Power BI -sovellusta](end-user-apps.md). Jos raportin *suunnittelija* on antanut sinulle käyttöoikeudet, voit jakaa sivutetun raportin uudelleen ja tilata sen itsellesi ja muille.

![eri kuvakkeita näyttävä raporttiluettelo](./media/end-user-paginated-report/power-bi-report-list.png)

## <a name="interact-with-a-paginated-report"></a>Sivutetun raportin kanssa toimiminen

Sivutetun raportin käsitteleminen eroaa muista raporteista. Voit tehdä asioita, kuten tulosteen, kirjanmerkin, viedä ja kommentoida, mutta vuorovaikutteisuutta on vähemmän. Sivutetut raportit edellyttävät usein syötettä raportin pohjalle.  Muina aikoina raportti näyttää oletustiedot, ja voit syöttää parametreja, jotta näet eri tiedot.

### <a name="print-a-paginated-report"></a>Sivutetun raportin tulostaminen

*Sivutetut* raportit muotoillaan sopimaan hyvin sivulle, joka voidaan tulostaa tai jakaa. Näet selaimessa, mitä näet tulostaessasi. Lisäksi jos raportissa on pitkä taulukko, koko taulukko tulostuu, vaikka se olisi usealla sivulla. 

Sivutetuissa raporteissa voi olla useita sivuja. Esimerkiksi tässä raportissa on 563 sivua. Jokainen sivu on aseteltu tarkasti yksi sivu laskua kohti -muotoon, ja ylä- ja alatunnisteet toistuvat kaikissa. Kun tulostat tämän raportin, saat sivunvaihdot laskujen välille.

   ![Sivu yksi sivutetusta raportista, Tailspin Toys](./media/end-user-paginated-report/power-bi-paginated-500.png)


### <a name="navigate-the-paginated-report"></a>Sivutetussa raportissa liikkuminen

Tässä myyntitilausraportissa on kolme parametria: Yritystyyppi, jälleenmyyjä ja tilausnumero. 

![raportti, jossa on kolme parametria](./media/end-user-paginated-report/power-bi-parameter.png)

Jos haluat muuttaa näytettäviä tietoja, anna uudet arvot kolmelle parametrille ja valitse **Näytä raportti**. Tässä olemme valinneet **Specialty Bike Shopin**, **Alpine Ski Housen**ja tilauksen numero **SO46085**. Kun valitset **Näytä raportti**, raporttipohjaan päivitetään tämä uusi myyntitilaus.

![rarametrien muuttaminen](./media/end-user-paginated-report/power-bi-order.png)

Uusi myynti tilaus näytetään käyttäen valitsemiasi parametreja. 

![uusi myyntitilaus](./media/end-user-paginated-report/power-bi-new-order.png)

Joissain sivutetuissa raporteissa voi olla useita sivuja.  Sivun ohjausobjektien avulla voit siirtyä raportissa. 

![sivun ohjausobjektit](./media/end-user-paginated-report/power-bi-page.png)

### <a name="export-the-paginated-report"></a>Sivutetun raportin vienti
Sinulla on useita vaihtoehtoja sivutettujen raporttien vientiin, mukaan lukien PDF, Word, XML, PowerPoint, Excel ja paljon muuta. Viennissä säilytetään mahdollisimman paljon muotoilua. Esimerkiksi Excel-, Word-, PowerPoint-, MHTML- ja PDF-muotoon viedyt sivutetut raportit säilyttävät "Pixel Perfect"-muotoilun. 

![uusi myyntitilaus](./media/end-user-paginated-report/power-bi-exporting.png)

![neljä eri vientityyppiä](./media/end-user-paginated-report/power-bi-four.png)

### <a name="subscribe-to-the-paginated-report"></a>Sivutetun raportin tilaus
Kun tilaat sivutetun raportin, Power BI lähettää sinulle sähköpostiviestin, joka sisältää liitteenä olevan raportin. Kun määrität tilauksia, valitset kuinka usein haluat saada sähköpostiviestejä: päivittäin, viikoittain, tunneittain vai kuukausittain. Tilaus sisältää raportin täydelliset tulokset PDF-liitteenä. 25 Mt:n kokoon asti. Vie koko raportti tai valitse parametrit etuajassa. Valitse useista eri liitetyypeistä, kuten Excel, PDF, PowerPoint ja paljon muuta.  

![Tilausmuodot](./media/end-user-paginated-report/power-bi-export-list.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

- Sivutettu raportti voi olla tyhjä, kunnes valitset parametrit ja valitset **Näytä raportti**.

- Jos sinulla ei ole sivutettuja raportteja, se voi johtua siitä, että kukaan ei ole jakanut tämäntyyppistä raporttia kanssasi. Se voi tarkoittaa myös sitä, että järjestelmänvalvojasi ei ole ottanut sivutettuja raportteja käyttöön puolestasi. 

 

## <a name="next-steps"></a>Seuraavat vaiheet
- [Power BI -raportit](end-user-reports.md)
- Onko sinulla kysyttävää? Kokeile [Power BI -yhteisöä](https://community.powerbi.com/).
