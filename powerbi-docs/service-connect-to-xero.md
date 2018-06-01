---
title: Yhteyden muodostaminen Xeroon Power BI:n avulla
description: Xero for Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: d9f61067f89fb031926428109ef5dac5bcfd6392
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815859"
---
# <a name="connect-to-xero-with-power-bi"></a>Yhteyden muodostaminen Xeroon Power BI:n avulla
Xero on helppokäyttöinen verkkokirjanpito-ohjelmisto, joka on suunniteltu erityisesti pienille yrityksille. Tämän Power BI -sisältöpaketin avulla voit luoda vaikuttavia visualisointeja Xeron taloustietojen pohjalta. Oletuskoontinäyttö sisältää useita pienyritysten mittareita, kuten käteistilanteen, tuoton vs kulut, voiton ja tappion trendin, velallisen maksupäivät ja sijoitetun pääoman tuoton.

Muodosta yhteys Power BI:n [Xero-sisältöpakettiin](https://app.powerbi.com/getdata/services/xero) tai lue lisää [Xeron ja Power BI:n](https://help.xero.com/Power-BI) integroinnista.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-xero/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-xero/services.png)
3. Valitse **Xero** \> **Nouda**.
   
   ![](media/service-connect-to-xero/connect.png)
4. Kirjoita lempinimi Xero-tiliisi liittyvälle organisaatiolle. Mikä tahansa nimi kelpaa. Sen pääasiallinen tarkoitus on auttaa useiden Xero-organisaatioiden parissa toimivia käyttäjiä pitämään eri tilit järjestyksessä. Tarkempia tietoja on [alla](#FindingParams).
   
   ![](media/service-connect-to-xero/params.png)
5. Valitse **todennusmenetelmäksi** **OAuth**, kun sinua kehotetaan kirjautumaan Xero-tilillesi ja valitsemaan organisaatio, johon haluat muodostaa yhteyden. Kun olet kirjautunut, käynnistä lataus valitsemalla **Kirjaudu sisään**.
   
    ![](media/service-connect-to-xero/creds.png)
   
    ![](media/service-connect-to-xero/creds2.png)
6. Tuontiprosessi alkaa automaattisesti hyväksymisen jälkeen. Kun kaikki on valmista, uusi koontinäyttö, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla koontinäytön.
   
     ![](media/service-connect-to-xero/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko ajastetaan päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana.

## <a name="whats-included"></a>Paketin sisältö
Sisältöpaketin koontinäyttö sisältää ruutuja ja mittareita eri alueilta sekä vastaavat, lisätietoja sisältävät raportit:  

| Alue | Koontinäytön ruudut | Raportti |
| --- | --- | --- |
| Kassa |Päivittäinen kassavirta <br>Tulot <br>Menot <br>Loppusaldo tilin mukaan <br>Loppusaldo tänään |Pankkitilit |
| Asiakas |Laskutetut myynnit <br>Laskutetut myynnit asiakkaan mukaan <br>Laskutettujen myyntien kasvutrendi <br>Erääntyvät myyntilaskut <br>Avoimet saatavat <br>Erääntyneet saatavat |Asiakas <br>Varasto |
| Toimittaja |Laskutetut ostot <br>Laskutettu ostot toimittajan mukaan <br>Laskutettujen ostojen kasvutrendi <br> Erääntyvät ostolaskut <br>Avoimet maksettavat <br>Erääntyneet maksettavat |Toimittajat <br>Varasto |
| Varasto |Kuukausittaisen myynnin määrä tuotteen mukaan |Varasto |
| Tulos |Kuukausittainen tulos <br>Kuluvan tilikauden nettovoitto <br>Kuluvan kuukauden nettovoitto <br>Suurimmat kulutilit |Tulos |
| Tase |Vastaavaa yhteensä <br>Vastattavaa yhteensä <br>Oma pääoma |Tase |
| Kunto |Current ratio -tunnusluku <br>Bruttovoitto prosentteina <br> Pääoman tuottoaste <br>Vastattavan ja oman pääoman välinen suhde |Kunto <br>Sanasto ja tekniset huomautukset |

Tietojoukko sisältää myös seuraavat taulukot, joiden avulla raportteja ja koontinäyttöjä voi mukauttaa:  

* Osoitteet  
* Hälytykset  
* Tiliotteen päiväsaldo  
* Tiliotteet  
* Yhteystiedot  
* Kululaskut  
* Laskurivinimikkeet  
* Laskut  
* Kohteet  
* Kuukauden loppu  
* Organisaatio  
* Alustava tase  
* Xero-tilit

## <a name="system-requirements"></a>Järjestelmävaatimukset
Xero-sisältöpaketin käyttämiseen tarvitaan Standard + Reports- tai Advisor-rooli.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien etsiminen
Anna organisaatiollesi nimi, jolla sitä voi seurata Power BI:ssä. Näin voit muodostaa yhteyden useisiin eri organisaatioihin. Huomaa, että et voi muodostaa yhteyttä samaan organisaatioon useita kertoja, sillä se vaikuttaa ajoitettuun päivitykseen.   

## <a name="troubleshooting"></a>Vianmääritys
* Jotta Xero-käyttäjät voivat käyttää Power BI:n Xero-sisältöpakettia, heillä on oltava Standard + Reports- tai Advisor-rooli. Sisältöpaketti tarvitsee käyttäjäpohjaisia käyttöoikeuksia voidakseen käyttää raportointitietoja Power BI:n kautta.  
* Jos lataamisessa ilmenee virhe jonkin ajan kuluttua, tarkista kuinka kauan kesti, ennen kuin virhesanoma tuli näkyviin. Huomaa, että Xeron tarjoama käyttöoikeustietue on voimassa vain 30 minuuttia, joten jos tilillä on enemmän tietoja kuin kyseisenä ajanjaksona voi ladata, toiminto epäonnistuu. Pyrimme aktiivisesti tekemään parannuksia tässä suhteessa.
* Latauksen aikana koontinäytön ruudut ovat yleisessä lataustilassa. Niiden tilan ei pitäisi muuttua, ennen kuin koko lataus on valmis. Jos saat ilmoituksen, että lataus on suoritettu, mutta ruudut latautuvat yhä, yritä päivittää koontinäytön ruudut käyttämällä koontinäytön oikeassa yläkulmassa olevaa ...-painiketta.
* Jos-sisältöpaketin päivitys epäonnistuu, tarkista, oletko muodostanut yhteyden samaan organisaatioon Power BI:ssä useammin kuin kerran. Xero sallii vain yhden aktiivisen yhteyden organisaatioon, ja näyttöön voi tulla virhesanoma, jonka mukaan tunnistetiedot ovat virheelliset, jos muodostat yhteyden samaan kohteeseen useammin kuin kerran.  
* Jos yhteyden muodostamisessa Power BI:n Xero-sisältöpakettiin ilmenee ongelmia, kuten virhesanomia tai hyvin pitkiä latausaikoja, tyhjennä ensin välimuisti, poista evästeet ja käynnistä selain uudelleen ja muodosta sitten yhteys Power BI:hin uudelleen.  

Muissa ongelmatilanteissa tee palvelupyyntö osoitteessa http://support.powerbi.com, jos ongelma jatkuu.

## <a name="next-steps"></a>Seuraavat vaiheet
[Aloita Power BI:n käyttö](service-get-started.md)

[Nouda tietoja Power BI:ssä](service-get-data.md)

