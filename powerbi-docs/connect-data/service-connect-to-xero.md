---
title: Yhteyden muodostaminen Xeroon Power BI:n avulla
description: Xero for Power BI
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 03/06/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: adb2f66b043b09ecb584870cf96f4c491960d59b
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348432"
---
# <a name="connect-to-xero-with-power-bi"></a>Yhteyden muodostaminen Xeroon Power BI:n avulla
Xero on helppokäyttöinen verkkokirjanpito-ohjelmisto, joka on suunniteltu erityisesti pienyrityksille. Tämän Power BI -mallisovelluksen avulla voit luoda vaikuttavia visualisointeja Xeron taloustietojen pohjalta. Oletuskoontinäyttö sisältää useita pienyritysten mittareita, kuten käteistilanteen, tuoton vrt. kulut, voiton ja tappion trendin, velallisen maksupäivät ja sijoitetun pääoman tuoton.

Muodosta yhteys Power BI:n [Xero-mallisovellukseen](https://app.powerbi.com/getdata/services/xero) tai lue lisää [Xeron ja Power BI:n](https://help.xero.com/Power-BI) integroinnista.

## <a name="how-to-connect"></a>Yhteyden muodostaminen

[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]

3. Valitse **Xero** \> **Hanki se nyt**.
4. Valitse **Asennetaanko tämä Power BI -sovellus?** -kohdasta **Asenna**.

    ![Asenna Xero](media/service-connect-to-xero/power-bi-install-xero.png)

4. Valitse **Sovellukset**-ruudussa **Xero**-ruutu.

   ![Valitse Xero-ruutu](media/service-connect-to-xero/power-bi-start-xero.png)

6. Valitse **Aloita uuden sovelluksesi käyttö** -kohdassa **Yhdistä tiedot**.

    ![Aloita uuden sovelluksesi käyttö](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

4. Kirjoita lempinimi Xero-tiliisi liittyvälle organisaatiolle. Mikä tahansa nimi kelpaa. Sen pääasiallinen tarkoitus on auttaa useiden Xero-organisaatioiden parissa toimivia käyttäjiä pitämään eri tilit järjestyksessä. Lisätietoja [parametrien löytämisestä](#FindingParams) on jäljempänä tässä artikkelissa.

    ![Organisaation lempinimi](media/service-connect-to-xero/params.png)

5. Valitse **todennusmenetelmäksi** **OAuth**. Kirjaudu kehotuksen mukaisesti Xero-tilillesi ja valitse organisaatio, johon haluat muodostaa yhteyden. Kun olet kirjautunut, käynnistä lataus valitsemalla **Kirjaudu sisään**.
   
    ![Todennusmenetelmä](media/service-connect-to-xero/creds.png)
   
    ![Tervetuloa Xeroon](media/service-connect-to-xero/creds2.png)
6. Hyväksymisen jälkeen tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi koontinäyttö, raportti sekä malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
     ![Xero-koontinäyttö](media/service-connect-to-xero/power-bi-xero-dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](../consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](../create-reports/service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](../consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Mallisovelluksen koontinäyttö sisältää ruutuja ja mittareita eri alueilta sekä vastaavat, lisätietoja sisältävät raportit:  

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
* Ilmoitukset  
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
Tarvitset seuraavia rooleja Xero-mallisovelluksen käyttämiseen: ”Standard + Reports” tai ”Advisor”.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Anna organisaatiollesi nimi, jolla sitä voi seurata Power BI:ssä. Yksilöidyn nimen avulla voit muodostaa yhteyden useaan eri organisaatioon. Et voi muodostaa yhteyttä samaan organisaatioon useita kertoja, sillä se vaikuttaa ajoitettuun päivitykseen.   

## <a name="troubleshooting"></a>Vianmääritys
* Xero-käyttäjillä on oltava seuraavat roolit, jotta he voivat käyttää Power BI:n Xero-mallisovellusta: ”Standard + Reports” tai ”Advisor”. Mallisovellus tarvitsee käyttäjäpohjaisia käyttöoikeuksia voidakseen käyttää raportointitietoja Power BI:n kautta.
* Latauksen aikana koontinäytön ruudut ovat yleisessä lataustilassa. Ne pysyvät siinä, kunnes koko lataus on valmis. Jos saat ilmoituksen, että lataus on suoritettu, mutta ruudut latautuvat yhä, yritä päivittää koontinäytön ruudut käyttämällä koontinäytön oikeassa yläkulmassa olevaa ...-painiketta.
* Jos mallisovelluksen päivitys epäonnistuu, tarkista, oletko muodostanut yhteyden samaan organisaatioon Power BI:ssä useammin kuin kerran. Xero sallii vain yhden aktiivisen yhteyden organisaatioon, ja näyttöön voi tulla virhesanoma, jonka mukaan tunnistetiedot ovat virheelliset, jos muodostat yhteyden samaan kohteeseen useammin kuin kerran.  
* Jos yhteyden muodostamisessa Power BI:n Xero-mallisovellukseen ilmenee ongelmia, kuten virhesanomia tai pitkiä latausaikoja, tyhjennä ensin välimuisti, poista evästeet ja käynnistä selain uudelleen ja muodosta sitten yhteys Power BI:hin uudelleen.  

Muissa ongelmatilanteissa tee palvelupyyntö osoitteessa https://support.powerbi.com, jos ongelma jatkuu.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](../fundamentals/service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)
