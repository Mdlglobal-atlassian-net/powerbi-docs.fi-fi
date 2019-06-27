---
title: Power BI -tietojen suojaaminen laitteen sisäänrakennetun tunnistuksen avulla
description: Lue, miten voit määrittää iOS-sovelluksen edellyttämään lisätunnistusta ennen Power BI -tietojen käyttöä
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/07/2019
ms.author: mshenhav
ms.openlocfilehash: b7418c9579a439a18a30a967947c15d58693fd44
ms.sourcegitcommit: 206806d8ddb6bdfc322c1a46fb34a1b0678acba2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816819"
---
# <a name="protect-power-bi-app-with-face-id-touch-id-or-passcode"></a>Power BI -sovelluksen suojaaminen Face ID:n, Touch ID:n tai tunnuskoodin avulla 

Monissa tapauksissa Power BI:ssä hallitut tiedot ovat luottamuksellisia. Ne on suojattava ja niiden käyttö sallittava vain valtuutetuille käyttäjille. 

Power BI:n iOS-sovelluksen avulla voit suojata tiedot määrittämällä lisätunnistautumisen. Sinun on suoritettava Face ID-, Touch ID- tai pääsykooditunnistus aina käynnistäessäsi sovelluksen tai tuodessasi sovelluksen taustalta etualalle.

| ![iPhone](./media/tutorial-mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](./media/tutorial-mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhonet |iPadit |

## <a name="turn-on-face-id-touch-id-or-passcode-in-app-setting"></a>Face ID:n, Touch ID:n tai tunnuskoodin käyttöönotto sovelluksen asetuksista

Jotta voit käyttää lisätunnistautumista Power BI:ssä, siirry sovelluksen asetusten kohtaan **Yksityisyys ja tietosuoja**. Sen kautta voit ottaa käyttöön Face ID:n, Touch ID:n tai pääsykoodin laitteen ominaisuuksien mukaan.

![Power BI:n iOS-sovelluksen asetussivu](./media/mobile-ios-native-secure-access/mobile-ios-native-secured-setting.png)

Kun tämä asetus on käytössä, Power BI pyytää sinua tunnistautumaan kun käynnistät sovelluksen tai tuot sen taustalta etualalle. Tunnistautumista pyydetään aina ennen kuin voit käyttää sovellusta. 

iOS määrittää laitteen ominaisuuksien mukaan, pyydetäänkö Face ID:tä, Touch ID:tä tai tunnuskoodia. Jos laite tukee Face ID:tä, sinun on käytettävä sitä. Jos laite tukee Touch ID:tä, sinun on käytettävä sitä. Jos kumpaakaan ei tueta, sinun on annettava tunnuskoodi.

![Power BI:n iOS Face ID](./media/mobile-ios-native-secure-access/mobile-ios-native-secured-faceid.png)

## <a name="use-mdm-to-enforce-face-id-touch-id-or-passcode"></a>MDM:n käyttö Face ID:n, Touch ID:n tai tunnuskoodin käytön pakottamiseksi

Joissain organisaatioissa käytetään suojauskäytäntöjä ja -vaatimuksia, jotka edellyttävät lisätunnistautumista, ennen kuin voit käyttää luottamuksellisia tietoja. 

Power BI:n iOS-mobiilisovellus sallii järjestelmänvalvojien hallita tätä asetusta lähettämällä sovelluksen määritykset Microsoft Intunen ja muiden mobiililaitteiden hallintaratkaisujen (MDM) kautta. Järjestelmänvalvojat voivat käyttää sovelluksen suojauskäytäntöä ottaakseen asetuksen käyttöön kaikille tai joillekin käyttäjille.

|Avain  |Tyyppi  |Kuvaus  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Totuusarvo | Oletusarvo on False. <br>Kun asetus on True, sovellus edellyttää käyttäjiltä tunnistautumista Face ID:n, Touch ID:n tai tunnuskoodin avulla, ennen kuin he voivat tarkastella Power BI -tietoja sovelluksessa. Käyttäjän, jonka laitteelle ei ole määritetty Face ID:tä, Touch ID:tä tai tunnuskoodia, on määritettävä jokin näitä ennen kuin hän voi käyttää Power BI:tä.  |

## <a name="next-steps"></a>Seuraavat vaiheet

[MDM:n käyttö Power BI:n iOS-sovelluksen etämäärittämiseen](mobile-app-configuration.md)
