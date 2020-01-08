---
title: Automaattisen päivämäärän/ajan ohjeet Power BI Desktopissa
description: Automaattisen päivämäärän ja ajan toimintoja koskevat ohjeet Power BI Desktopissa.
author: peter-myers
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/23/2019
ms.author: v-pemyer
ms.openlocfilehash: 30bfacc1024035f0849440eec8b1c7051ff4d82a
ms.sourcegitcommit: 5bb62c630e592af561173e449fc113efd7f84808
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/11/2019
ms.locfileid: "75002439"
---
# <a name="auto-datetime-guidance-in-power-bi-desktop"></a>Automaattisen päivämäärän/ajan ohjeet Power BI Desktopissa

Tämä artikkeli on suunnattu tietomallintajille, jotka kehittävät tuonti- tai yhdistelmämalleja Power BI Desktopissa. Tässä kerrotaan ohjeita, suosituksia ja huomioitavia seikkoja, kun Power BI Desktopin _Automaattinen päivämäärä/aika_ -asetusta käytetään tietyissä tilanteissa. Jos haluat lukea _Automaattinen päivämäärä/aika_ -asetuksen yleiskatsauksen ja esittelyn, katso [Automaattinen päivämäärä/aika Power BI Desktopissa](../desktop-auto-date-time.md).

_Automaattinen päivämäärä/aika_ -asetus tarjoaa aikatiedot kätevästi, nopeasti ja helppokäyttöisesti. Raporttien tekijät voivat käsitellä aikatietoja suodattaessaan ja ryhmitellessään kalenterin aikajaksoja ja porautuessaan niihin.

## <a name="considerations"></a>Huomioitavaa

Seuraavassa luettelossa on huomioitavia seikkoja – ja mahdollisia rajoituksia – jotka liittyvät _Automaattinen päivämäärä/aika_ -asetukseen.

- **Koskee kaikkia tai ei mitään:** Kun _Automaattinen päivämäärä/aika_ -asetus on käytössä, se koskee tuontitaulukoiden kaikkia päivämääräsarakkeita, jotka eivät ole suhteen &quot;monta&quot;-puolia. Sitä ei voi ottaa käyttöön tai poistaa käytöstä valikoivasti sarakekohtaisesti.
- **Vain kalenterijaksot:** Vuosi- ja vuosineljännes-sarakkeet liittyvät kalenterijaksoihin. Tämä tarkoittaa sitä, että vuosi alkaa 1. tammikuuta ja päättyy 31. joulukuuta. Vuoden alkamispäivää (tai päättymispäivää) ei voi mukauttaa.
- **Mukauttaminen:** Aikajaksojen kuvaamiseen käytettyjä arvoja ei voi mukauttaa. Ei ole myöskään mahdollista lisätä lisäsarakkeita kuvaamaan muita aikajaksoja, kuten esimerkiksi viikkoja.
- **Vuosisuodatus:** **Vuosineljännes**-, **Kuukausi**- ja **Päivä**-sarakkeen arvot eivät sisällä vuosiarvoa. Esimerkiksi **Kuukausi**-sarake sisältää vain kuukausien nimet (eli tammikuu, helmikuu jne.). Arvot eivät ole täysin itsestäänselvästi kuvaavia ja eivät joissakin raporttimalleissa välttämättä välitä vuoden suodatinkontekstia.

    Sen vuoksi on tärkeää, että suodatus tai ryhmittely tehdään **Vuosi**-sarakkeessa. Kun poraudutaan hierarkiassa, vuosi suodatetaan, ellei **Vuosi**-tasoa ole tarkoituksella poistettu. Jos suodatusta tai ryhmittelyä ei voi tehdä vuoden mukaan, ryhmittely esimerkiksi kuukauden mukaan kokoaisi yhteen kaikkien vuosien kyseisen kuukauden arvot.
- **Suodatus yksittäisen taulukon päivämäärän mukaan:** Jokainen päivämääräsarake tuottaa oman (piilotetun) Automaattinen päivämäärä/aika -taulukon, joten ei ole mahdollista käyttää aikasuodatinta yhteen taulukkoon ja levittää sitä sitten useisiin mallitaulukoihin. Tällainen suodattaminen on yleinen mallinnusvaatimus, kun raportoidaan useista kohteista (faktatyyppiset taulukot), kuten myynti ja myyntibudjetti. Kun käytetään Automaattinen päivämäärä/aika -asetusta, raportin tekijän on käytettävä suodattimia kaikkiin eri päivämääräsarakkeisiin.
- **Mallin koko:** Jokainen päivämääräsarake, joka luo piilotetun Automaattinen päivämäärä/aika -taulukon, johtaa mallin koon kasvamiseen ja myös tietojen päivitysajan pidentymiseen.

## <a name="recommendations"></a>Suositukset

Suosittelemme, että otat _Automaattinen päivämäärä/aika_ -asetuksen käyttöön vain silloin, kun käytät kalenterin aikajaksoja ja kun mallivaatimukset ovat yksinkertaiset suhteessa aikaan. Tämä asetus voi olla kätevä myös silloin, kun luodaan ad hoc -malleja tai tarkastellaan tietoja tai tehdään profilointia.

Kun tietolähteesi määrittää jo päivämäärän dimensiotaulukkoa, tätä taulukkoa on käytettävä ajan johdonmukaiseen määrittämiseen organisaatiossasi. Tilanne on varmasti tällainen, jos tietolähteesi on tietovarasto. Muussa tapauksessa voit muodostaa päivämäärätaulukoita mallissasi käyttämällä DAX [CALENDAR](/dax/calendar-function-dax)- tai [CALENDARAUTO](/dax/calendarauto-function-dax)-funktioita. Sen jälkeen voit lisätä laskettuja sarakkeita tukemaan tunnettuja aikasuodatus- ja ryhmittelyvaatimuksia. Tämän rakennemenetelmän avulla voit luoda yksittäisen päivämäärätaulukon, joka leviää kaikkiin faktatyyppisiin taulukoihin ja antaa mahdollisesti tulokseksi yksittäisen taulukon, johon voi käyttää aikasuodattimia. Lisätietoja päivämäärätaulukoiden luomisesta saat lukemalla [Päivämäärätaulukkojen määrittäminen ja käyttäminen Power BI Desktopissa](../desktop-date-tables.md) -artikkelin.

Jos _Automaattinen päivämäärä/aika_ -asetus ei ole olennainen projektiesi kannalta, suosittelemme poistamaan yleisen _Automaattinen päivämäärä/aika_ -asetuksen käytöstä. Näin varmistat, että _Automaattinen päivämäärä/aika_ -asetusta ei oteta käyttöön kaikissa uusissa Power BI Desktop -tiedostoissa, jotka luot.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Automaattinen päivämäärä/aika Power BI Desktopissa](../desktop-auto-date-time.md)
- [Päivämäärätaulukkojen määrittäminen ja käyttäminen Power BI Desktopissa](../desktop-date-tables.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)