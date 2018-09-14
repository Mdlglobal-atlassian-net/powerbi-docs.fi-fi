---
title: Power BI -palvelun tietoilmoitusten määrittäminen
description: Opi asettamaan ilmoituksia ilmoittamaan sinulle, kun koontinäyttösi tiedot muuttuvat Microsoft Power BI -palvelussa asettamiesi rajojen ulkopuolelle.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: JbL2-HJ8clE
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/28/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 153676c983ef81bcccf1ea6bf0adf95ef29a2765
ms.sourcegitcommit: fe03f2a80f2df82219b8e026085f93a8453201df
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/08/2018
ms.locfileid: "44167924"
---
# <a name="data-alerts-in-power-bi-service"></a>Power BI -palvelun tietoilmoitukset
Aseta ilmoituksia ilmoittamaan sinulle, kun koontinäyttösi tiedot muuttuvat asettamiesi rajojen ulkopuolelle. 

Voit asettaa ruutujen ilmoituksia, jos sinulla on Power BI Pro - käyttöoikeus tai jos koontinäyttö on jaettu kanssasi [Premium-kapasiteetista](service-premium.md). Ilmoitukset voidaan määrittää vain ruuduille, jotka on kiinnitetty raportin visualisoineista, ja vain mittareissa, suorituskykyilmaisimissa ja korteissa. Ilmoitukset voidaan määrittää visualisoinneille, jotka on luotu virtautustietojoukoista, jotka on kiinnitetty koontinäyttöön raportista, mutta niitä ei voi määrittää virtautusruuduille, jotka on luotu suoraan koontinäytöstä valitsemalla **Lisää ruutu**  >  **Mukautetut virtautettavat tiedot** . 

Vain sinä näet asettamasi hälytykset, vaikka jakaisit koontinäyttösi. Tietoilmoitukset synkronoidaan täysin kaikissa ympäristöissä. Määritä ja tarkastele tietoilmoituksia [Power BI -mobiilisovelluksissa](mobile-set-data-alerts-in-the-mobile-apps.md) ja Power BI -palvelussa. Ne eivät ole käytettävissä Power BI Desktopissa. Ilmoitukset voidaan myös [automatisoida ja integroida Microsoft Flowin kanssa](https://flow.microsoft.com) - [kokeile itse](service-flow-integration.md).

![ruudut](media/service-set-data-alerts/powerbi-alert-types-new.png)

> [!WARNING]
> Aineistoperäisen ilmoitukset antavat on tietoja lähdetiedoistasi. Jos tarkastelet Power BI -tietojasi mobiililaitteella ja laite varastetaan, suosittelemme kaikkien tietopohjaisten hälytysten poistamista käytöstä Power BI -palvelulla.
> 
> 

## <a name="set-data-alerts-in-power-bi-service"></a>Power BI -palvelun tietoilmoitusten määrittäminen
Katsele, kuinka Amanda lisää joitakin ilmoituksia hänen koontinäyttönsä ruutuihin. Kokeile sitten itse noudattamalla videon alapuolella olevia vaiheittaisia ohjeita.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JbL2-HJ8clE" frameborder="0" allowfullscreen></iframe>

Tässä esimerkissä käytetään jälleenmyyntianalyysimallin koontinäytön korttiruutua.

1. Aloita koontinäytöstä. Valitse koontinäytön mittarista, suorituskykyilmaisimesta tai korttiruudusta kolme pistettä.
   
   ![Myymälöitä yhteensä -ruutu](media/service-set-data-alerts/powerbi-card.png)
2. Lisää yksi tai useampia hälytyksiä **Myymälöitä yhteensä** -ruudulle valitsemalla kellokuvake ![Hälytys-kuvake](media/service-set-data-alerts/power-bi-bell-icon.png) tai **Hälytysten hallinta**.
   
1. Valitse **Hälytysten hallinta** -ruudussa **+ Lisää hälytyssääntö**.  Varmista, että liukusäädin on asennossa **Käytössä**, ja anna hälytykselle nimi. Nimet helpottavat ilmoitusten tunnistamista.
   
   ![Hälytysten hallinta -ikkuna](media/service-set-data-alerts/powerbi-alert-title.png)
4. Vieritä alas ja anna hälytyksen tiedot.  Luomme tässä esimerkissä ilmoituksen, joka ilmoittaa meille kerran päivässä, jos kauppojen kokonaismäärä ylittää sadan. Ilmoitukset näkyvät ilmoituskeskuksessa. Myös Power BI lähettää meille sähköpostia.
   
   ![Hälytysten hallinta -ikkuna, määritä Raja-arvo](media/service-set-data-alerts/power-bi-set-alert-details.png)
5. Valitse **Tallenna ja sulje**.

## <a name="receiving-alerts"></a>Ilmoitusten vastaanottaminen
Kun seuratut tiedot saavuttavat jonkin määrittämistäsi raja-arvoista, tapahtuu useita asioita. Power BI tarkistaa ensin, onko edellisen ilmoituksen lähettämisestä yli tunti tai yli 24 tuntia (valitsemasi vaihtoehdon mukaan). Kunhan tiedot ylittävät raja-arvon, saat ilmoituksen.

Power BI lähettää seuraavaksi ilmoituksen ilmoituskeskukseen ja valinnaisesti myös sähköpostiin. Kussakin ilmoituksessa on suora linkki tietoihin. Avaa asiaankuuluva ruutu, jossa voit tutkia, jakaa ja hankkia lisätietoja, valitsemalla linkki.  

1. Jos olet määrittänyt ilmoitukset lähettämään sinulle sähköpostia, Saapuneet-kansiossasi näkyy jotain seuraavanlaista.
   
   ![Ilmoituksen sähköpostiviesti](media/service-set-data-alerts/powerbi-alerts-email.png)
2. Power BI lisää viestin **ilmoituskeskukseesi** ja lisää uuden ilmoituksen kuvakkeen kyseiseen ruutuun.
   
   ![Ilmoituksen kuvake Power BI -palvelussa](media/service-set-data-alerts/powerbi-alert-notifications.png)
3. Näytä ilmoituksen tiedot avaamalla ilmoituskeskus.
   
    ![lue ilmoitus](media/service-set-data-alerts/powerbi-alert-notfication.png)
   
   > [!NOTE]
   > Ilmoitukset toimivat vain tiedoissa, joita päivitetään. Kun tiedot päivitetään, Power BI tarkistaa, onko tiedoille määritetty ilmoitus. Jos tiedot saavuttavat ilmoituksen raja-arvon, aktivoidaan ilmoitus.
   > 
   > 

## <a name="managing-alerts"></a>Ilmoitusten hallinta
Voit hallita ilmoituksia usealla tavalla: suoraan koontinäytön ruudusta, Power BI -asetukset -valikosta, ruudusta [iPhonen Power BI -mobiilisovelluksessa](mobile-set-data-alerts-in-the-mobile-apps.md) tai [Windows 10:n Power BI -mobiilisovelluksessa](mobile-set-data-alerts-in-the-mobile-apps.md).

### <a name="from-the-tile-itself"></a>Suoraan ruudusta
1. Jos haluat muuttaa tai poistaa ruudun ilmoituksen, avaa **Hallitse ilmoituksia** -ikkuna uudelleen valitsemalla kellokuvakkeen ![Ilmoituskuvake](media/service-set-data-alerts/power-bi-bell-icon.png). Kaikki kyseiselle ruudulle määrittämäsi ilmoitukset tulevat näyttöön.
   
    ![Hälytysten hallinta -ikkuna](media/service-set-data-alerts/powerbi-see-alerts.png).
2. Jos haluat muuttaa ilmoitusta, valitse haluamasi ilmoituksen nimen vasemmalla puolella oleva nuoli.
   
    ![ilmoituksen nimen viereinen nuoli](media/service-set-data-alerts/powerbi-see-alerts-arrow.png).
3. Poista ilmoitus valitsemalla ilmoituksen nimen oikealla puolella oleva roskakori.
   
      ![roskakorikuvake valittu](media/service-set-data-alerts/powerbi-see-alerts-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Power BI:n Asetukset-valikosta
1. Valitse Power BI -valikkopalkin rataskuvake.
   
    ![rataskuvake](media/service-set-data-alerts/powerbi-gear-icon.png).
2. Valitse kohdasta **Asetukset** komento **Ilmoitukset**.
   
    ![Asetukset-ikkunan Ilmoitukset-välilehti](media/service-set-data-alerts/powerbi-alert-settings.png)
3. Täällä voit ottaa hälytyksiä käyttöön ja poistaa niitä käytöstä, avata **Ilmoitusten hallinta** -ikkunan, jos haluat muuttaa tai poistaa hälytyksen.

## <a name="tips-and-troubleshooting"></a>Vihjeet ja vianmääritys
* Hälytyksiä ei tällä hetkellä tueta Bing-ruuduissa tai korttiruuduissa, joissa on päivämäärä/aika-mittayksiköitä.
* Hälytykset toimivat vain numeerisissa tietotyypeissä.
* Ilmoitukset toimivat vain tiedoissa, joita päivitetään. Ne eivät toimi staattisissa tiedoissa.
* Ilmoitukset toimivat virtautustietojoukoissa vain, jos luot suorituskykyilmaisimen, kortin tai mittarin raportin visualisoinnin ja kiinnität kyseisen visualisoinnin koontinäyttöön.

## <a name="next-steps"></a>Seuraavat vaiheet
[Luo Microsoft Flow, joka sisältää tietoilmoituksen](service-flow-integration.md)    
[Määritä tietoilmoitukset mobiililaitteellasi](mobile-set-data-alerts-in-the-mobile-apps.md)    

