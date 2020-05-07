---
title: Power BI -tietojen suojaaminen laitteen sisäänrakennetun tunnistuksen avulla
description: Lue, miten voit määrittää iOS- ja Android-sovelluksen edellyttämään lisätunnistusta ennen Power BI -tietojen käyttöä
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/07/2020
ms.author: painbar
ms.openlocfilehash: ce7b3c3bc667023ef36650d8c551caaceab04c02
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80802797"
---
# <a name="protect-power-bi-app-with-face-id-touch-id-passcode-or-biometric-data"></a>Power BI -sovelluksen suojaaminen Face ID:n, Touch ID:n, tunnuskoodin tai biometristen tietojen avulla 

Monissa tapauksissa Power BI:ssä hallitut tiedot ovat luottamuksellisia. Ne on suojattava ja niiden käyttö sallittava vain valtuutetuille käyttäjille. 

Power BI:n iOS- ja Android-sovelluksen avulla voit suojata tiedot määrittämällä lisätunnistautumisen. Sen jälkeen aina, kun sovellus käynnistetään tai tuodaan edustalle, tunnistetiedot vaaditaan. iOS:ssä tämä tarkoittaa Face ID:n, Touch ID:n tai tunnuskoodin antamista. Android-laitteissa se tarkoittaa biometristen tietojen (sormenjälkitunnuksen) antamista.

Koskee seuraavia:

| ![iPhone](./media/mobile-native-secure-access/ios-logo-40-px.png) | ![iPadit](./media/mobile-native-secure-access/ios-logo-40-px.png) | ![Android-puhelin](././media/mobile-native-secure-access/android-logo-40-px.png) | ![Android-tabletti](././media/mobile-native-secure-access/android-logo-40-px.png) |
|:--- |:--- |:--- |:--- |
|iPhonet |iPadit |Android-puhelimet |Android-tabletit |

## <a name="turn-on-face-id-touch-id-or-passcode-on-ios"></a>Face ID:n, Touch ID:n tai tunnuskoodin käyttöönotto iOS:ssä

Jotta voit käyttää lisätunnistautumista Power BI:n iOS-mobiilisovelluksessa, siirry sovelluksen asetusten kohtaan **Yksityisyys ja tietosuoja**. Sen kautta voit ottaa käyttöön Face ID:n, Touch ID:n tai tunnuskoodin. Näkyvissä olevat vaihto ehdot määräytyvät laitteesi ominaisuuksien mukaan.

![Power BI:n iOS-sovelluksen asetussivu](./media/mobile-native-secure-access/mobile-ios-native-secured-setting.png)

Kun tämä asetus on käytössä ja käynnistät sovelluksen tai tuot sen taustalta etualalle, sovellus pyytää sinua tunnistautumaan. Tunnistautumista pyydetään aina, ennen kuin voit käyttää sovellusta.

Sen tunnuksen tyyppi, joka sinua pyydetään antamaan, määräytyy laitteesi ominaisuuksien mukaan. Jos laite tukee Face ID:tä, sinun on käytettävä sitä. Jos laite tukee Touch ID:tä, sinun on käytettävä sitä. Jos kumpaakaan ei tueta, sinun on annettava tunnuskoodi. Alla olevassa kuvassa näkyy Face ID -todennusnäyttö.

![Power BI:n iOS Face ID](./media/mobile-native-secure-access/mobile-ios-native-secured-faceid.png)

## <a name="turn-on-biometric-data-fingerprint-id-on-android"></a>Biometristen tietojen (sormenjälkitunnuksen) käyttöönotto Androidissa

Jotta voit käyttää lisätunnistautumista Power BI:n Android-mobiilisovelluksessa, siirry sovelluksen asetusten kohtaan **Yksityisyys ja tietosuoja**. Näkyviin tulee vaihtoehto, jolla otetaan biometriset tiedot käyttöön.

![Power BI:n Android-sovelluksen asetussivu](./media/mobile-native-secure-access/mobile-android-native-secured-setting.png)

Kun tämä asetus on käytössä ja käynnistät sovelluksen tai tuot sen taustalta etualalle, sovellus pyytää sinua tunnistautumaan. Tunnistautumista biometrisillä tiedoilla (sormenjälkitunnuksella) pyydetään aina, ennen kuin voit käyttää sovellusta.

Alla olevassa kuvassa näkyy sormenjälkitunnuksen todennusnäyttö.

![Power BI:n iOS Face ID](./media/mobile-native-secure-access/mobile-android-native-secured-fingerprint-id.png)

>[!NOTE]
>Jotta voit käyttää mobiilisovelluksen Edellytä biometrista todennusta -asetusta, sinun on ensin määritettävä biometriikka Android-laitteessasi. Jos laitteesi ei tue biometriikkaa, et voi suojata Power BI -tietojesi käyttöä tämän mobiilisovelluksen asetuksen avulla.
>
>Jos järjestelmänvalvoja on [etäyhteydellä ottanut suojatun käytön käyttöön](#mdm-enforcement-of-secure-access-to-your-power-bi-mobile-app) mobiilisovellusta varten etkä ole vielä määrittänyt biometriaa laitteessasi, tee se nyt, jotta voit käyttää sovellusta. Jos laitteesi ei tue biometriikkaa, etäasetus ei vaikuta sinuun. Mobiilisovelluksesi käyttö pysyy suojaamattomana.

## <a name="mdm-enforcement-of-secure-access-to-your-power-bi-mobile-app"></a>Power BI -mobiilisovelluksen suojatun käytön valvonta mobiililaitteiden hallinnan avulla.

Joissain organisaatioissa käytetään suojauskäytäntöjä ja -vaatimuksia, jotka edellyttävät lisätunnistautumista, ennen kuin voit käyttää luottamuksellisia tietoja.

Tämän tukemiseksi Power BI:n mobiilisovellus sallii järjestelmänvalvojien hallita mobiilisovelluksen suojatun käytön asetusta lähettämällä sovelluksen määritykset Microsoft Intunen ja muiden mobiililaitteiden hallintaratkaisujen (MDM) kautta. Järjestelmänvalvojat voivat käyttää sovelluksen suojauskäytäntöä ottaakseen asetuksen käyttöön kaikille tai joillekin käyttäjille. Lisätietoja on artikkelissa [MDM:n käyttö Power BI:n mobiilisovelluksen etämäärittämiseen](mobile-app-configuration.md#data-protection-settings-ios-and-android).

## <a name="next-steps"></a>Seuraavat vaiheet
* [MDM:n käyttö Power BI:n mobiilisovelluksen etämäärittämiseen](mobile-app-configuration.md)
