---
title: 'Opetusohjelma: Power BI -palvelun tietoilmoitusten määrittäminen'
description: Tässä opetusohjelmassa opit asettamaan hälytyksiä ilmoittamaan sinulle, kun koontinäyttösi tiedot muuttuvat Microsoft Power BI -palvelussa asettamiesi rajojen ulkopuolelle.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: JbL2-HJ8clE
ms.service: powerbi
ms.component: powerbi-service
ms.topic: tutorial
ms.date: 10/08/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: ba27b42d6449d38fef2659507f035144c67f23fd
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223210"
---
# <a name="tutorial-set-data-alerts-in-power-bi-service"></a>Opetusohjelma: Power BI -palvelun tietoilmoitusten määrittäminen
Aseta ilmoituksia ilmoittamaan sinulle, kun koontinäyttösi tiedot muuttuvat asettamiesi rajojen ulkopuolelle. 

Voit asettaa ruutujen ilmoituksia, jos sinulla on Power BI Pro - käyttöoikeus tai jos koontinäyttö on jaettu kanssasi [Premium-kapasiteetista](../service-premium.md). Ilmoitukset voidaan määrittää vain ruuduille, jotka on kiinnitetty raportin visualisoineista, ja vain mittareissa, suorituskykyilmaisimissa ja korteissa. Ilmoitukset voidaan määrittää visualisoinneille, jotka on luotu virtautustietojoukoista, jotka on kiinnitetty koontinäyttöön raportista, mutta niitä ei voi määrittää virtautusruuduille, jotka on luotu suoraan koontinäytöstä valitsemalla **Lisää ruutu**  >  **Mukautetut virtautettavat tiedot** . 

Vain sinä näet asettamasi hälytykset, vaikka jakaisit koontinäyttösi. Tietoilmoitukset synkronoidaan täysin kaikissa ympäristöissä. Määritä ja tarkastele tietoilmoituksia [Power BI -mobiilisovelluksissa](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) ja Power BI -palvelussa. 

![ruudut](../media/service-set-data-alerts/powerbi-alert-types-new.png)

> [!WARNING]
> Aineistoperäisen ilmoitukset antavat on tietoja lähdetiedoistasi. Jos tarkastelet Power BI -tietojasi mobiililaitteella ja laite varastetaan, suosittelemme kaikkien tietopohjaisten hälytysten poistamista käytöstä Power BI -palvelulla.
> 

Tässä artikkelissa käsitellään seuraavat asiat.
> [!div class="checklist"]
> * Kuka voi asettaa hälytyksiä
> * Mitkä visualisoinnit tukevat hälytyksiä
> * Kuka voi nähdä hälytyksiä
> * Toimivatko hälytykset Power BI Desktopissa ja -mobiilisovelluksessa
> * Hälytyksen luominen
> * Minne vastaanotan hälytykset

Jos et ole rekisteröitynyt Power BI:hin, [rekisteröidy ilmaiseen kokeiluversioon](https://app.powerbi.com/signupredirect?pbi_source=web) ennen aloittamista.

## <a name="set-data-alerts-in-power-bi-service"></a>Power BI -palvelun tietoilmoitusten määrittäminen
Katsele, kuinka Amanda lisää joitakin ilmoituksia hänen koontinäyttönsä ruutuihin. Kokeile sitten itse noudattamalla videon alapuolella olevia vaiheittaisia ohjeita.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JbL2-HJ8clE" frameborder="0" allowfullscreen></iframe>

Tässä esimerkissä käytetään [jälleenmyyntianalyysimallin koontinäytön](http://go.microsoft.com/fwlink/?LinkId=529778) korttiruutua.

1. Valitse koontinäytön mittarista, suorituskykyilmaisimesta tai korttiruudusta kolme pistettä.
   
   ![Myymälöitä yhteensä -ruutu](media/end-user-alerts/powerbi-card.png)
2. Lisää yksi tai useampia hälytyksiä **Myymälöitä yhteensä** -ruudulle valitsemalla kellokuvake ![Hälytys-kuvake](media/end-user-alerts/power-bi-bell-icon.png) tai **Hälytysten hallinta**.
   
1. Valitse **Hälytysten hallinta** -ruudussa **+ Lisää hälytyssääntö**.  Varmista, että liukusäädin on asennossa **Käytössä**, ja anna hälytykselle nimi. Nimet helpottavat ilmoitusten tunnistamista.
   
   ![Hälytysten hallinta -ikkuna](media/end-user-alerts/powerbi-alert-title.png)
4. Vieritä alas ja anna hälytyksen tiedot.  Luomme tässä esimerkissä ilmoituksen, joka ilmoittaa meille kerran päivässä, jos kauppojen kokonaismäärä ylittää sadan. Ilmoitukset näkyvät ilmoituskeskuksessa. Myös Power BI lähettää meille sähköpostia.
   
   ![Hälytysten hallinta -ikkuna, määritä Raja-arvo](media/end-user-alerts/power-bi-set-alert-details.png)
5. Valitse **Tallenna ja sulje**.

## <a name="receiving-alerts"></a>Ilmoitusten vastaanottaminen
Kun seuratut tiedot saavuttavat jonkin määrittämistäsi raja-arvoista, tapahtuu useita asioita. Power BI tarkistaa ensin, onko edellisen ilmoituksen lähettämisestä yli tunti tai yli 24 tuntia (valitsemasi vaihtoehdon mukaan). Kunhan tiedot ylittävät raja-arvon, saat ilmoituksen.

Power BI lähettää seuraavaksi ilmoituksen ilmoituskeskukseen ja valinnaisesti myös sähköpostiin. Kussakin ilmoituksessa on suora linkki tietoihin. Valitse linkki nähdäksesi asianmukaisen ruudun.  

1. Jos olet määrittänyt ilmoitukset lähettämään sinulle sähköpostia, Saapuneet-kansiossasi näkyy jotain seuraavanlaista.
   
   ![Ilmoituksen sähköpostiviesti](media/end-user-alerts/powerbi-alerts-email.png)
2. Power BI lisää viestin **ilmoituskeskukseesi** ja lisää uuden ilmoituksen kuvakkeen kyseiseen ruutuun.
   
   ![Ilmoituksen kuvake Power BI -palvelussa](media/end-user-alerts/powerbi-alert-notifications.png)
3. Näytä ilmoituksen tiedot avaamalla ilmoituskeskus.
   
    ![lue ilmoitus](media/end-user-alerts/powerbi-alert-notfication.png)
   
   > [!NOTE]
   > Ilmoitukset toimivat vain tiedoissa, joita päivitetään. Kun tiedot päivitetään, Power BI tarkistaa, onko tiedoille määritetty ilmoitus. Jos tiedot saavuttavat ilmoituksen raja-arvon, aktivoidaan ilmoitus.
   > 
   > 

## <a name="managing-alerts"></a>Ilmoitusten hallinta
Voit hallita ilmoituksia usealla tavalla: suoraan koontinäytön ruudusta, Power BI -asetukset -valikosta, ruudusta [iPhonen Power BI -mobiilisovelluksessa](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) tai [Windows 10:n Power BI -mobiilisovelluksessa](mobile/mobile-set-data-alerts-in-the-mobile-apps.md).

### <a name="from-the-tile-itself"></a>Suoraan ruudusta
1. Jos haluat muuttaa tai poistaa ruudun ilmoituksen, avaa **Hallitse ilmoituksia** -ikkuna uudelleen valitsemalla kellokuvakkeen ![Ilmoituskuvake](media/end-user-alerts/power-bi-bell-icon.png). Kaikki kyseiselle ruudulle määrittämäsi ilmoitukset tulevat näyttöön.
   
    ![Hälytysten hallinta -ikkuna](media/end-user-alerts/powerbi-see-alerts.png).
2. Jos haluat muuttaa ilmoitusta, valitse haluamasi ilmoituksen nimen vasemmalla puolella oleva nuoli.
   
    ![ilmoituksen nimen viereinen nuoli](media/end-user-alerts/powerbi-see-alerts-arrow.png).
3. Poista ilmoitus valitsemalla ilmoituksen nimen oikealla puolella oleva roskakori.
   
      ![roskakorikuvake valittu](media/end-user-alerts/powerbi-see-alerts-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Power BI:n Asetukset-valikosta
1. Valitse Power BI -valikkopalkin rataskuvake.
   
    ![rataskuvake](media/end-user-alerts/powerbi-gear-icon.png).
2. Valitse kohdasta **Asetukset** komento **Ilmoitukset**.
   
    ![Asetukset-ikkunan Ilmoitukset-välilehti](media/end-user-alerts/powerbi-alert-settings.png)
3. Täällä voit ottaa hälytyksiä käyttöön ja poistaa niitä käytöstä, avata **Ilmoitusten hallinta** -ikkunan, jos haluat muuttaa tai poistaa hälytyksen.

## <a name="tips-and-troubleshooting"></a>Vihjeet ja vianmääritys
* Hälytyksiä ei tällä hetkellä tueta Bing-ruuduissa tai korttiruuduissa, joissa on päivämäärä/aika-mittayksiköitä.
* Hälytykset toimivat vain numeerisissa tietotyypeissä.
* Ilmoitukset toimivat vain tiedoissa, joita päivitetään. Ne eivät toimi staattisissa tiedoissa.
* Ilmoitukset toimivat virtautustietojoukoissa vain, jos luot suorituskykyilmaisimen, kortin tai mittarin raportin visualisoinnin ja kiinnität kyseisen visualisoinnin koontinäyttöön.

## <a name="clean-up-resources"></a>Resurssien tyhjentäminen
Ohjeet hälytysten poistamiseen on annettu edellä. Lyhyesti sanottuna valitse Power BI -valikkopalkin rataskuvake. Valitse **Asetukset**-kohdassa **Hälytykset** ja poista hälytys.

> [!div class="nextstepaction"]
> [Määritä tietoilmoitukset mobiililaitteellasi](mobile/mobile-set-data-alerts-in-the-mobile-apps.md)


