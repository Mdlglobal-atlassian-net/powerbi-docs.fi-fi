---
title: 'Opetusohjelma: Power BI -palvelun koontinäyttöjen tietoilmoitusten määrittäminen'
description: Tässä opetusohjelmassa opit asettamaan hälytyksiä ilmoittamaan sinulle, kun koontinäyttösi tiedot muuttuvat Microsoft Power BI -palvelussa asettamiesi rajojen ulkopuolelle.
author: mihart
ms.reviewer: ''
featuredvideoid: removed
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: tutorial
ms.date: 04/18/2020
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 4cad37b9d4a7bf9e74a29312786a02b26fce5463
ms.sourcegitcommit: faa8cfb66e79ea16ba46605f752cc9ca57924d0e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83382757"
---
# <a name="tutorial-set-alerts-on-power-bi-dashboards"></a>Opetusohjelma: Ilmoitusten määrittäminen Power BI -raporttinäkymissä

[!INCLUDE[consumer-appliesto-ynnn](../includes/consumer-appliesto-ynnn.md)]

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Aseta hälytyksiä ilmoittamaan sinulle, kun koontinäyttösi tiedot muuttuvat asettamiesi rajojen ylä- tai alapuolelle. Ilmoitukset voidaan määrittää vain ruuduille, jotka on kiinnitetty raportin visualisoinneista, ja vain mittareissa, suorituskykyilmaisimissa ja korteissa. 

*Kuluttajat* voivat lisätä ilmoituksia ruutuihin, jotka he ovat luoneet **omassa työtilassa**. *Kuluttajat* voi myös lisätä ilmoituksia ruutuihin koontinäytöissä, jotka on jaettu heidän kanssaan [Premium-kapasiteetissa](end-user-license.md). Jos sinulla on Power BI:n Pro-käyttöoikeus, voit määrittää ilmoituksia ruuduille myös missä tahansa muussa työtilassa.
Tämä ominaisuus on vielä kehitteillä, joten katso lisätietoja [alla olevasta Vihjeet ja vianmääritys -kohdasta](#tips-and-troubleshooting).

![ruutu, kortti, suorituskykyilmaisin](media/end-user-alerts/card-gauge-kpi.png)

Vain sinä näet asettamasi hälytykset, vaikka jakaisit koontinäyttösi. Tietoilmoitukset synkronoidaan täysin kaikissa ympäristöissä. Määritä ja tarkastele tietoilmoituksia [Power BI -mobiilisovelluksissa](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) ja Power BI -palvelussa. 

> [!WARNING]
> Näistä ilmoituksista saat tietoja tiedoistasi. Jos tarkastelet Power BI -tietojasi mobiililaitteella ja laite varastetaan, suosittelemme kaikkien hälytysten poistamista käytöstä Power BI -palvelulla.
> 

Tässä artikkelissa käsitellään seuraavat asiat.
> [!div class="checklist"]
> * Kuka voi asettaa hälytyksiä
> * Mitkä visualisoinnit tukevat hälytyksiä
> * Kuka voi nähdä hälytyksiä
> * Toimivatko hälytykset Power BI Desktopissa ja -mobiilisovelluksessa
> * Miten hälytys luodaan
> * Minne vastaanotan hälytykset

Jos et ole rekisteröitynyt Power BI:hin, [rekisteröidy ilmaiseen kokeiluversioon](https://app.powerbi.com/signupredirect?pbi_source=web) ennen aloittamista.

Tässä esimerkissä käytetään Myynti- ja markkinointi -mallisovelluksen koontinäytön korttiruutua. Tämä sovellus on käytettävissä [Microsoft AppSourcessa](https://appsource.microsoft.com). Katso lisätietoja sovelluksen käyttämisestä kohdasta [Myynti- ja markkinointisovelluksen asentaminen ja käyttäminen](end-user-app-marketing.md).

1. Valitse koontinäytön mittarista, suorituskykyilmaisimesta tai korttiruudusta kolme pistettä.
   
   ![korttiruutu](media/end-user-alerts/power-bi-cards.png)
2. Lisää yksi tai useampia hälytyksiä **Yksiköiden markkinaosuus-%** -ruudulle valitsemalla kellokuvake ![Hälytys-kuvake](media/end-user-alerts/power-bi-bell-icon.png) tai **Hälytysten hallinta**.

   ![korttiruutu, jossa kolme pistettä on valittuna](media/end-user-alerts/power-bi-ellipses.png)

   
1. Valitse **Hälytysten hallinta** -ruudussa **+ Lisää hälytyssääntö**.  Varmista, että liukusäädin on asennossa **Käytössä**, ja anna hälytykselle nimi. Nimet helpottavat ilmoitusten tunnistamista.
   
   ![Hälytysten hallinta -ikkuna](media/end-user-alerts/power-bi-manage-alert.png)
4. Vieritä alas ja anna hälytyksen tiedot.  Luomme tässä esimerkissä hälytyksen, joka ilmoittaa meille kerran päivässä, jos markkinaosuutemme nousee yli 35. Ilmoitukset näkyvät ilmoituskeskuksessa. Myös Power BI lähettää meille sähköpostia.
   
   ![Hälytysten hallinta -ikkuna, määritä Raja-arvo](media/end-user-alerts/power-bi-manage-alert-details.png)
5. Valitse **Tallenna ja sulje**.
 
   > [!NOTE]
   > Ilmoitukset toimivat vain tiedoissa, joita päivitetään. Kun tiedot päivitetään, Power BI tarkistaa, onko tiedoille määritetty ilmoitus. Jos tiedot saavuttavat ilmoituksen raja-arvon, aktivoidaan ilmoitus. 
   > 

## <a name="receiving-alerts"></a>Ilmoitusten vastaanottaminen
Kun seuratut tiedot saavuttavat jonkin määrittämistäsi raja-arvoista, tapahtuu useita asioita. Power BI tarkistaa ensin, onko edellisen ilmoituksen lähettämisestä yli tunti tai yli 24 tuntia (valitsemasi vaihtoehdon mukaan). Kunhan tiedot ylittävät raja-arvon, saat ilmoituksen.

Power BI lähettää seuraavaksi ilmoituksen ilmoituskeskukseen ja valinnaisesti myös sähköpostiin. Kussakin ilmoituksessa on suora linkki tietoihin. Valitse linkki nähdäksesi asianmukaisen ruudun.  

1. Jos olet määrittänyt ilmoitukset lähettämään sinulle sähköpostia, Saapuneet-kansiossasi näkyy jotain seuraavanlaista. Tämä on ilmoitus, jonka asetimme eri koontinäytössä. Tämä koontinäyttö seuraa Käytettävyystiimin suorittamia tehtäviä.
   
   ![Ilmoituksen sähköpostiviesti](media/end-user-alerts/power-bi-alert-email.png)
2. Power BI lisää viestin **ilmoituskeskukseesi** ja lisää uuden ilmoituksen kuvakkeen kyseiseen ruutuun.
   
   ![Ilmoituksen kuvake Power BI -palvelussa](media/end-user-alerts/power-bi-task-alert.png)
3. Näytä ilmoituksen tiedot avaamalla ilmoituskeskus.
   
    ![lue ilmoitus](media/end-user-alerts/power-bi-notification.png)
   
  

## <a name="managing-alerts"></a>Ilmoitusten hallinta

Voit hallita ilmoituksia usealla tavalla: suoraan raporttinäkymän ruudusta, Power BI -asetukset -valikosta, ruudusta [iPhonen Power BI -mobiilisovelluksessa](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) tai [Windows 10:n Power BI -mobiilisovelluksessa](mobile/mobile-set-data-alerts-in-the-mobile-apps.md).

### <a name="from-the-tile-itself"></a>Suoraan ruudusta

1. Jos haluat muuttaa tai poistaa ruudun ilmoituksen, avaa **Hallitse ilmoituksia** -ikkuna uudelleen valitsemalla kellokuvakkeen ![Ilmoituskuvake](media/end-user-alerts/power-bi-bell-icon.png). Kaikki kyseiselle ruudulle määrittämäsi ilmoitukset tulevat näyttöön.
   
    ![Hälytysten hallinta -ikkuna](media/end-user-alerts/power-bi-manage-alerts.png).
2. Jos haluat muuttaa ilmoitusta, valitse haluamasi ilmoituksen nimen vasemmalla puolella oleva nuoli.
   
    ![ilmoituksen nimen viereinen nuoli](media/end-user-alerts/power-bi-modify-alert.png).
3. Poista ilmoitus valitsemalla ilmoituksen nimen oikealla puolella oleva roskakori.
   
      ![roskakorikuvake valittu](media/end-user-alerts/power-bi-alert-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Power BI:n Asetukset-valikosta

1. Valitse Power BI -valikkopalkin rataskuvake.
   
    ![rataskuvake](media/end-user-alerts/powerbi-gear-icon.png).
2. Valitse kohdasta **Asetukset** komento **Ilmoitukset**.
   
    ![Asetukset-ikkunan Ilmoitukset-välilehti](media/end-user-alerts/power-bi-alert-settings.png)
3. Täällä voit ottaa hälytyksiä käyttöön ja poistaa niitä käytöstä, avata **Ilmoitusten hallinta** -ikkunan, jos haluat muuttaa tai poistaa hälytyksen.

## <a name="tips-and-troubleshooting"></a>Vihjeet ja vianmääritys 

* Jos et pysty asettamaan hälytystä mittarille, suorituskykyilmaisimelle tai kortille, pyydä apua vuokraajan järjestelmänvalvojalta. Joskus hälytykset on poistettu käytöstä tai ne eivät ole käytettävissä koontinäytössäsi tai tietyntyyppisissä koontinäytön ruuduissa.
* Ilmoitukset toimivat vain tiedoissa, joita päivitetään. Ne eivät toimi staattisissa tiedoissa. Useimmat Microsoftin toimittamista malleista ovat staattisia. 
* Sisällön vastaanottaminen ja jaetun sisällön katsominen edellyttää Power BI Pro- tai Premium-käyttöoikeutta. Saat lisätietoja kohdasta [Mikä käyttöoikeus minulla on?](end-user-license.md)
* Ilmoituksia voidaan määrittää visualisoinneille, jotka on tehty virtautettavista tietojoukoista, jotka kiinnitetään raportista koontinäyttöön. Ilmoituksia ei voi määrittää virtautettaville ruuduille, jotka on tehty suoraan koontinäytössä valitsemalla **Lisää-ruutu** > **Mukautetut virtautettavat tiedot**.


## <a name="clean-up-resources"></a>Puhdista resurssit
Ohjeet hälytysten poistamiseen on annettu edellä. Lyhyesti sanottuna valitse Power BI -valikkopalkin rataskuvake. Valitse **Asetukset**-kohdassa **Hälytykset** ja poista hälytys.

> [!div class="nextstepaction"]
> [Määritä tietoilmoitukset mobiililaitteellasi](mobile/mobile-set-data-alerts-in-the-mobile-apps.md)


