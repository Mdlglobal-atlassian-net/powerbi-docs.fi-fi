---
title: Tietoilmoitusten määrittäminen Power BI -mobiilisovelluksissa
description: Lue, miten Power BI -mobiilisovellukseen asetetaan tietoilmoituksia, jotka ilmoittavat, kun koontinäytön tiedot muuttuvat asettamiesi rajojen ulkopuolelle.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 12/11/2019
ms.author: painbar
ms.openlocfilehash: 288ac6620af03c49d0a7f96e219e88d855381caf
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279545"
---
# <a name="set-data-alerts-in-the-power-bi-mobile-apps"></a>Tietoilmoitusten määrittäminen Power BI -mobiilisovelluksissa
Koskee seuraavia:

| ![iPhone](./media/mobile-set-data-alerts-in-the-mobile-apps/iphone-logo-50-px.png) | ![iPad](./media/mobile-set-data-alerts-in-the-mobile-apps/ipad-logo-50-px.png) | ![Android-puhelin](./media/mobile-set-data-alerts-in-the-mobile-apps/android-phone-logo-50-px.png) | ![Android-tabletti](./media/mobile-set-data-alerts-in-the-mobile-apps/android-tablet-logo-50-px.png) | ![Android-tabletti](./media/mobile-set-data-alerts-in-the-mobile-apps/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhonet |iPadit |Android-puhelimet |Android-tabletit |Windows 10 -laitteet |

Voit asettaa koontinäyttöilmoituksia Power BI -mobiilisovelluksissa ja Power BI -palvelussa. Ilmoitukset ilmoittavat, kun ruudun tiedot muuttuvat asettamiesi rajojen ulkopuolelle. Ilmoitukset toimivat ruuduilla, joissa on yksittäinen numero, kuten kortti- ja mittariruuduissa, mutta ei virtautettavien tietojen kohdalla. Voit asettaa tietoilmoituksia mobiililaitteessasi ja nähdä ne Power BI -palvelussa tai päinvastoin. Vain sinä näet määrittämäsi tietoilmoitukset, vaikka jakaisitkin koontinäytön tai ruudun tilannevedoksen.

Voit määrittää ilmoituksia ruuduille, jos sinulla on Power BI Pro -käyttöoikeus tai jos jaetulla koontinäytöllä on Premium-kapasiteetti. 

> [!WARNING]
> Aineistoperäiset ilmoitukset antavat tietoja lähdetiedoistasi. Jos laitteesi varastetaan, suosittelemme Power BI -palvelun avaamista ja kaikkien aineistoperäisten ilmoitussääntöjen poistamista käytöstä. 
> 
> Lue lisää [tietoilmoitusten hallinnasta Power BI -palvelussa](../../create-reports/service-set-data-alerts.md).
> 
> 

## <a name="data-alerts-on-an-iphone-or-ipad"></a>Tietoilmoitukset iPhonella tai iPadilla
### <a name="set-an-alert-on-an-iphone-or-ipad"></a>Ilmoituksen asettaminen iPhonella tai iPadilla
1. Napauttamalla numero- tai mittariruutua koontinäytöllä voit avata sen tarkastelutilassa.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-card-visual.png)
2. Napauttamalla kellokuvaketta ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-alert-icon.png) voit lisätä ilmoituksen.  
3. Valitse **Lisää ilmoitussääntö**.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-add-alert-rule.png)
4. Valitse ilmoitusten vastaanotto, kun tietty arvo ylitetään tai alitetaan, ja määritä sen jälkeen arvo.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-set-alert-threshold.png)
5. Päätä, haluatko vastaanottaa tunti- vai päiväilmoituksia sekä haluatko saada myös sähköpostiviestin, kun saat ilmoituksen.
   
   > [!NOTE]
   > Et saa ilmoituksia joka tunti tai joka päivä, mikäli tiedot eivät ole päivittyneet kyseisenä aikana.
   > 
   > 
6. Voit muuttaa myös ilmoituksen otsikkoa.
7. Valitse **Tallenna**.
8. Yhdellä ruudulla voi olla ilmoituksia sekä raja-arvot ylittäville että alittaville arvoille. Kohdassa **Ilmoitusten hallinta** valitse **Lisää ilmoitussääntö**.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-add-another-alert-rule.png)

### <a name="manage-alerts-on-your-iphone-or-ipad"></a>Ilmoitusten hallinta iPhonella tai iPadilla
Voit hallita yksittäisiä ilmoituksia mobiililaitteessasi tai [hallita kaikkia ilmoituksiasi Power BI -palvelussa](../../create-reports/service-set-data-alerts.md).

1. Koontinäytössä napauta numero- tai mittariruutua, jossa on ilmoitus.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-card-visual_has_alert.png)

2. Napauta kellokuvaketta ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-has-alert-icon.png).  
3. Muokkaa ilmoitusta napauttamalla sen nimeä, poista sähköposti-ilmoitukset käytöstä napauttamalla liukusäädintä tai poista ilmoitus napauttamalla roskakoria.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-edit-delete-alert.png)

## <a name="data-alerts-on-an-android-device"></a>Tietoilmoitukset Android-laitteessa
### <a name="set-an-alert-on-an-android-device"></a>Ilmoituksen asettaminen Android-laitteessa
1. Power BI -koontinäytössä avaa numero- tai mittariruutu napauttamalla sitä.  
2. Napauttamalla kellokuvaketta ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-alert-icon.png) voit lisätä ilmoituksen.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-tap-alert.png)
3. Napauta plusmerkkiä (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-plus-alert.png)
4. Valitse ilmoitusten vastaanotto, kun tietty arvo ylitetään tai alitetaan, ja syötä arvo.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-tablet-set-alert-condition.png)
5. Valitse **Valmis**.
6. Päätä, haluatko vastaanottaa tunti- vai päiväilmoituksia sekä haluatko saada myös sähköpostiviestin, kun saat ilmoituksen.
   
   > [!NOTE]
   > Et saa ilmoituksia joka tunti tai joka päivä, mikäli tiedot eivät ole päivittyneet kyseisenä aikana.
   > 
   > 
7. Voit muuttaa myös ilmoituksen otsikkoa.
8. Valitse **Tallenna**.

### <a name="manage-alerts-on-an-android-device"></a>Ilmoitusten hallinta Android-laitteessa
Voit hallita yksittäisiä ilmoituksia Power BI -mobiilisovelluksessa tai [hallita kaikkia ilmoituksiasi Power BI -palvelussa](../../create-reports/service-set-data-alerts.md).

1. Koontinäytössä napauta kortti- tai mittariruutua, jossa on ilmoitus.  
2. Napauta kellokuvaketta ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-filled-alert-bell.png).  
3. Napauta ilmoitusta, jos haluat muuttaa sen arvoa tai poistaa sen käytöstä.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-manage-alerts.png)
4. Jos haluat lisätä toisen ilmoituksen samaan ruutuun, napauta plusmerkkiä (+).
5. Jos haluat poistaa ilmoituksen kokonaan, napauta roskakorikuvaketta ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-delete-alert-icon.png).

## <a name="data-alerts-on-a-windows-device"></a>Tietoilmoitukset Windows-laitteessa

>[!NOTE]
>Power BI -mobiilisovellustuki **Windows 10 Mobilea käyttäville puhelimille** lopetetaan 16. maaliskuuta 2021. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=2121400)

### <a name="set-data-alerts-on-a-windows-device"></a>Tietoilmoitusten asettaminen Windows-laitteessa
1. Napauttamalla numero- tai mittariruutua koontinäytöllä voit avata sen.  
2. Napauttamalla kellokuvaketta ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-alert-bell-off.png) voit lisätä ilmoituksen.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-tap-alert.png)
3. Napauta plusmerkkiä (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-no-alerts-yet.png)
4. Valitse ilmoitusten vastaanotto, kun tietty arvo ylitetään tai alitetaan, ja syötä arvo.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-set-alert.png)
5. Päätä, haluatko vastaanottaa tunti- vai päiväilmoituksia sekä haluatko saada myös sähköpostiviestin, kun saat ilmoituksen.
   
   > [!NOTE]
   > Et saa ilmoituksia joka tunti tai joka päivä, mikäli tiedot eivät ole päivittyneet kyseisenä aikana.
   > 
   > 
6. Voit muuttaa myös ilmoituksen otsikkoa.
7. Napauta valintamerkkiä.
8. Yhdellä ruudulla voi olla ilmoituksia sekä raja-arvot ylittäville että alittaville arvoille. Kohdassa **Ilmoitusten hallinta** napauta plusmerkkiä (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-add-another-alert.png)

### <a name="manage-alerts-on-a-windows-device"></a>Ilmoitusten hallinta Windows-laitteessa
Voit hallita yksittäisiä ilmoituksia Power BI -mobiilisovelluksessa tai [hallita kaikkia ilmoituksiasi Power BI -palvelussa](../../create-reports/service-set-data-alerts.md).

1. Koontinäytössä napauta kortti- tai mittariruutua, jossa on ilmoitus.  
2. Napauta kellokuvaketta ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-alert-bell-on.png).  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-has-alerts.png)
3. Napauta ilmoitusta, jos haluat muuttaa sen arvoa tai poistaa sen käytöstä.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-add-another-alert.png)
4. Jos haluat poistaa ilmoituksen kokonaan, napsauta hiiren kakkospainikkeella tai napauta pitkään > **Poista**.

## <a name="receiving-alerts"></a>Ilmoitusten vastaanottaminen
Ilmoituksen saapuvat mobiililaitteen tai Power BI-palvelun Power BI [-ilmoituskeskukseen](mobile-apps-notification-center.md). Saat myös ilmoituksia uusista koontinäytöistä, jotka joku on jakanut kanssasi.

Tietolähteet määritetään usein päivittymään päivittäin, vaikka jotkin päivittyvätkin useammin. Kun koontinäytön tiedot päivitetään ja jos seuratut tiedot saavuttavat jonkin määrittämistäsi raja-arvoista, tapahtuu useita asioita.

1. Power BI tarkistaa, onko edellisen ilmoituksen lähettämisestä yli tunti tai yli 24 tuntia (valitsemasi vaihtoehdon mukaan).
   
   Kunhan tiedot ylittävät raja-arvon, saat ilmoituksen joka tunti tai joka 24. tunti.
2. Jos olet määrittänyt ilmoitukset lähettämään sinulle sähköpostia, Saapuneet-kansiossasi näkyy jotain seuraavanlaista.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/powerbi-alerts-email.png)
3. Power BI lisää sanoman [ilmoituskeskukseesi](mobile-apps-notification-center.md) ja lisää keltaisen pisteen kellokuvakkeeseen ![kellokuvake](media/mobile-set-data-alerts-in-the-mobile-apps/powerbi-alert-tile-notification-icon.png) otsikkoriville (iOS ja Android) tai yleiseen siirtymispainikkeeseen ![yleinen siirtymispainike](./media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-alert-global-nav-button.png) (Windows 10 -laitteet).


4. Napauttamalla kellokuvaketta ![kellokuvake](media/mobile-set-data-alerts-in-the-mobile-apps/powerbi-alert-tile-notification-icon.png) tai yleistä siirtymispainiketta ![yleinen siirtymispainike](./media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-alert-global-nav-button.png) voit [avata **ilmoituskeskuksesi**](mobile-apps-notification-center.md) ja nähdä ilmoituksen tiedot.
   
     

> [!NOTE]
> Ilmoitukset toimivat vain tiedoissa, joita päivitetään. Kun tiedot päivitetään, Power BI tarkistaa, onko tiedoille määritetty ilmoitus. Jos tiedot saavuttavat ilmoituksen raja-arvon, aktivoidaan ilmoitus.
> 
> 

## <a name="tips-and-troubleshooting"></a>Vihjeet ja vianmääritys
* Ilmoituksia ei tällä hetkellä tueta Bing-ruuduissa tai korttiruuduissa, joissa on päivämäärä/aika-mittareita.
* Ilmoitukset toimivat vain numeerisissa tiedoissa.
* Ilmoitukset toimivat vain tiedoissa, joita päivitetään. Ne eivät toimi staattisissa tiedoissa.
* Ilmoitukset eivät toimi ruuduissa, jotka sisältävät virtautettavia tietoja.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Power BI -palvelun ilmoitusten hallinta](../../create-reports/service-set-data-alerts.md)
* [Power BI -mobiilisovelluksen ilmoituskeskus](mobile-apps-notification-center.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
