---
title: Yhteyden vianmääritysohjeet
description: Ohjeita malliyhteysongelmien vianmääritykseen.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 03/02/2020
ms.author: v-pemyer
ms.openlocfilehash: e2854d82d858bb1963b691d32d561c7b3bbfc11a
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "78263641"
---
# <a name="relationship-troubleshooting-guidance"></a>Yhteyden vianmääritysohjeet

Tämä artikkeli on tarkoitettu tietojen mallintajille, jotka käyttävät Power BI Desktopia. Siinä on ohjeet sellaisten tiettyjen ongelmien vianmääritykseen, joita saatat kohdata malleja ja raportteja kehittäessäsi.

[!INCLUDE [relationships-prerequisite-reading](includes/relationships-prerequisite-reading.md)]

## <a name="troubleshooting-checklist"></a>Vianmäärityksen tarkistusluettelo

Kun raportin visualisointi on määritetty käyttämään kenttiä kahdesta (tai useammasta) taulukosta eikä se esitä oikeaa tulosta (tai mitään tulosta), on mahdollista, että ongelma liittyy malliyhteyksiin.

Tässä on yleinen vianmäärityksen tarkistusluettelo tällaista tilannetta varten. Voit käydä tarkistusluetteloa vaiheittain läpi, kunnes tunnistat ongelman tai ongelmat.

1. Vaihda visualisointi taulukoksi tai matriisiksi tai avaa Näytä tiedot -ruutu – ongelmien vianmääritys on helpompaa, kun näet kyselyn tuloksen
1. Jos kyselyn tulos on tyhjä, vaihda Tietonäkymään – tarkista, että taulukoihin on ladattu tietorivejä
1. Vaihda Mallinäkymään – yhteydet ja niiden ominaisuudet on helppo nähdä
1. Varmista, että taulukoiden välillä on yhteyksiä
1. Varmista, että kardinaliteettiominaisuudet on määritetty oikein – ne saattavat olla väärin, jos ”monta”-puolen sarake sisältää yksilöllisiä arvoja ja on määritetty virheellisesti ”yksi”-puoleksi
1. Varmista, että yhteydet ovat aktiivisia (yhtenäinen viiva)
1. Varmista, että suodatusohjeet tukevat levittämistä (katso nuolenpäät)
1. Varmista, että oikeat sarakkeet liittyvät toisiinsa – valitse yhteys tai osoita sitä hiirellä, jotta näet toisiinsa liittyvät sarakkeet
1. Varmista, että toisiinsa liittyvien sarakkeiden tietotyypit ovat samat tai ainakin yhteensopivat – tekstisarakkeen voi yhdistää kokonaislukusarakkeeseen, mutta suodattimet eivät löydä levitettäviä vastaavuuksia
1. Vaihda Tietonäkymään ja tarkista, että vastaavat arvot löytyvät toisiinsa liittyvistä sarakkeista

## <a name="troubleshooting-guide"></a>Vianmääritysopas

Tässä on luettelo ongelmista ja niiden mahdollisista ratkaisuista.

|Ongelma|Mahdolliset syyt|
|---------|---------|
|Visualisointi ei näytä tulosta|- Malliin ei ole vielä ladattu tietoja<br />- Suodatinkontekstissa ei ole tietoja<br />- Rivitason suojaus on käytössä<br />- Yhteydet eivät levity taulukoiden välillä – _noudata yllä olevaa tarkistusluetteloa_<br />- Rivitason suojaus on käytössä, mutta kaksisuuntaista yhteyttä ei voi levittää – katso [Rivitason suojaus (RLS) Power BI Desktopissa](../desktop-rls.md)|
|Visualisointi näyttää saman arvon jokaiselle ryhmittelylle |- Yhteyksiä ei ole<br />- Yhteydet eivät levity taulukoiden välillä – _noudata yllä olevaa tarkistusluetteloa_|
|Visualisointi näyttää tulokset, mutta ne eivät ole oikein|- Visualisointi on määritetty virheellisesti<br />- Mittarilogiikka on virheellinen<br />- Mallitiedot täytyy päivittää<br />- Lähdetiedot ovat virheelliset<br />- Yhteyssarakkeiden suhteet ovat väärät (esimerkiksi **ProductID**-sarake on yhdistetty **CustomerID**-kohteeseen)<br />- Yhteys on kahden DirectQuery-taulukon välillä, ja yhteyden ”yksi”-puolen sarake sisältää arvojen kaksoiskappaleita|
|TYHJÄ-ryhmittelyjä tai osittaja-/suodatuskohteita näkyy, eivätkä lähdesarakkeet sisällä TYHJÄ-kohtia|- Yhteys on vahva, ja "monta"-puolen sarake sisältää arvoja, joita ei ole tallennettu "yksi"-puolen sarakkeeseen – katso [Mallien suhteet Power BI Desktopissa (Vahvat yhteydet)](../desktop-relationships-understand.md#strong-relationships)<br />- Kyseessä on vahva yksi yhteen -yhteys, ja toisiinsa liittyvät sarakkeet sisältävät TYHJÄ-kohtia – katso [Mallien suhteet Power BI Desktopissa (Vahvat yhteydet)](../desktop-relationships-understand.md#strong-relationships)<br />- Epäaktiivisen yhteyden "monta"-puolen sarakkeeseen on tallennettu TYHJÄ-kohtia, tai siinä on arvoja, joita ei ole tallennettu "yksi"-puolelle|
|Visualisoinnista puuttuu tietoja|- Virheellisiä/odottamattomia suodattimia on käytössä<br />- Rivitason suojaus on käytössä<br />- Yhteys on heikko, ja toisiinsa liittyvissä sarakkeissa on TYHJÄ-kohtia tai tietojen eheysongelmia – katso [Mallien suhteet Power BI Desktopissa (Heikot yhteydet)](../desktop-relationships-understand.md#weak-relationships)<br />- Kyseessä on kahden DirectQuery-taulukon välinen yhteys, joka on määritetty [olettamaan viite-eheys](../desktop-relationships-understand.md#assume-referential-integrity), mutta tiedoissa on eheysongelmia (ristiriitaisia arvoja toisiinsa liittyvissä sarakkeissa)|
|Rivitason suojausta ei ole otettu käyttöön oikein|- Yhteydet eivät levity taulukoiden välillä – _noudata yllä olevaa tarkistusluetteloa_<br />- Rivitason suojaus on käytössä, mutta kaksisuuntaista yhteyttä ei voi levittää – katso [Rivitason suojaus (RLS) Power BI Desktopissa](../desktop-rls.md)|
|||

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Mallien suhteet Power BI Desktopissa](../desktop-relationships-understand.md)
- Onko sinulla kysymyksiä? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
