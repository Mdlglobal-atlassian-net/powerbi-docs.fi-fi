---
title: Power BI -sovelluksen määritykset
description: Power BI -sovelluksen toiminnan mukauttaminen MDM-työkalun avulla
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/05/2020
ms.author: painbar
ms.openlocfilehash: ce147be4c23b738e1a09296a5d798fb0f94efe13
ms.sourcegitcommit: 9b806dfe62c2dee82d971bb4f89d983b97931b43
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/07/2020
ms.locfileid: "80802022"
---
# <a name="remotely-configure-power-bi-app-using-mobile-device-management-mdm-tool"></a>Power BI -sovelluksen etämääritys mobiililaitteiden hallintatyökalun (MDM) avulla

Power BI:n iOS- ja Android-mobiilisovellukset tukevat sovellusasetuksia, joiden avulla mobiililaitteiden hallintatyökalupalveluiden (esim. Intune) järjestelmänvalvojat voivat mukauttaa sovelluksen toimintaa.

Power BI -mobiilisovellus tukee määritystä seuraavissa tilanteissa:

* Raporttipalvelimen määrittäminen (iOS ja Android)
* Tietosuoja-asetukset (iOS ja Android)
* Vuorovaikutusasetukset (iOS ja Android)

## <a name="report-server-configuration-ios-and-android"></a>Raporttipalvelimen määrittäminen (iOS ja Android)

Power BI:n iOS- ja Android-sovelluksen avulla järjestelmänvalvojat voivat pakottaa raporttipalvelimen määritykset rekisteröidyille laitteille.

| Avain | Tyyppi | Kuvaus |
|---|---|---|
| com.microsoft.powerbi.mobile.ServerURL | Merkkijono | Raporttipalvelimen URL-osoite.<br><br>Tulee alkaa merkkijonolla http tai https.|
| com.microsoft.powerbi.mobile.ServerUsername | Merkkijono | [valinnainen]<br><br>Käyttäjänimi, jota käytetään muodostettaessa yhteyttä palvelimeen.<br><br>Jos sellaista ei ole, sovellus pyytää käyttäjää antamaan käyttäjänimen yhteyden muodostamista varten.|
| com.microsoft.powerbi.mobile.ServerDisplayName | Merkkijono | [valinnainen]<br><br>Oletusarvo on ”Raporttipalvelin”<br><br>Kutsumanimi, joka edustaa palvelinta sovelluksessa. |
| com.microsoft.powerbi.mobile.OverrideServerDetails | Totuusarvo | [valinnainen]<br><br>Oletusarvo on Tosi (True). Kun arvoksi on määritetty Tosi, se ohittaa mobiililaitteessa jo olevat raporttipalvelimen määritelmät. Tässä yhteydessä poistetaan olemassa olevat palvelimet, jotka on jo määritetty. Ohituksen Tosi-arvo estää käyttäjää poistamista kyseistä määritystä.<br><br>Epätosi-arvo lisää lähetetyt arvot poistamatta olemassa olevia asetuksia. Jos sama palvelimen URL-osoite on jo määritetty mobiilisovelluksessa, sovellus jättää sen määrityksen ennalleen. Sovellus ei pyydä käyttäjää todentamaan uudelleen samalle palvelimelle. |

## <a name="data-protection-settings-ios-and-android"></a>Tietosuoja-asetukset (iOS ja Android)

Power BI:n iOS- ja Android-mobiilisovellus tarjoaa järjestelmänvalvojille mahdollisuuden mukauttaa suojaus- ja tietosuoja-asetusten oletusmäärityksiä. iOS:ssä voit vaatia käyttäjiltä kasvojentunnistusta, kosketustunnistusta tai tunnuskoodia Power BI -mobiilisovelluksen käyttämistä varten. Androidissa voit pakottaa käyttäjät käyttämään biometristä todentamista (sormenjälkitunnusta).

| Avain | Tyyppi | Kuvaus |
|---|---|---|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Totuusarvo | Oletusarvo on False. <br><br>Voit edellyttää käyttäjiltä biometristä tunnistusta, kuten Touch ID tai Face ID (iOS) tai sormenjälkitunnus (Android), jotta he voivat käyttää sovellusta laitteellaan. Biometrista tunnistusta käytetään tarvittaessa todennuksen lisäksi.<br><br>Jos käytössä on sovelluksen suojauskäytäntöjä, Microsoft suosittelee asetuksen poistamista käytöstä kahden kirjautumiskehotteen välttämiseksi. |

>[!NOTE]
>Tietosuoja-asetukset otetaan käyttöön vain niissä Android-laitteissa, jotka tukevat biometristä todentamista.

## <a name="interaction-settings-ios-and-android"></a>Vuorovaikutusasetukset (iOS ja Android)

Power BI:n iOS- ja Android-sovelluksen avulla järjestelmänvalvojat voivat määrittää vuorovaikutusasetukset, jos päätetään, että oletusvuorovaikutusasetuksia pitää muuttaa kaikissa organisaation käyttäjäryhmissä.

>[!NOTE]
>Kaikkia vuorovaikutuksia ei tueta tällä hetkellä kaikissa laitteissa. Katso [Määritä raportin vuorovaikutusasetukset](mobile-app-interaction-settings.md) kaaviolle, joka näyttää käytettävyyden eri laitteilla.

| Avain | Tyyppi | Arvot | Kuvaus |
|---|---|---|---|
| com.microsoft.powerbi.mobile.ReportTapInteraction | Merkkijono |  <nobr>single-tap</nobr><br><nobr>double-tap</nobr> | Määritä, tehdäänkö visualisoinnin napautuksella myös arvopisteen valinta. |
| com.microsoft.powerbi.mobile.EnableMultiSelect | Totuusarvo |  <nobr>Tosi</nobr><br><nobr>Epätosi</nobr> | Määritä, korvataanko nykyinen valinta arvopisteen napautuksella vai lisätäänkö se nykyiseen valintaan. |
| com.microsoft.powerbi.mobile.RefreshAction | Merkkijono |  <nobr>pull-to-refresh</nobr><br>painike | Määritä, onko käyttäjällä painike raportin päivittämiseen, vai tuleeko hänen päivittää vetämällä. |
| com.microsoft.powerbi.mobile.FooterAppearance | Merkkijono |  docked<br>dynamic | Määritä, kiinnitetäänkö raportin alatunniste raportin alareunaan vai piilotetaanko se automaattisesti. |

## <a name="deploying-app-configuration-settings"></a>Sovelluksen määritysten käyttöönotto

Voit luoda sovelluksen määrityskäytännön seuraavien vaiheiden mukaisesti. Kun määrityskäytäntö on luotu, voit määrittää sen asetukset käyttäjäryhmille.

1. Yhdistä ydintietojen hallintatyökalu.
2. Luo ja nimeä uusi sovelluksen määrityskäytäntö.
3. Valitse käyttäjät, joille haluat jakaa tämän sovelluksen määrityskäytännön.
4. Luo tälle asetukselle avain-arvopareja, jotka haluat ottaa käyttäjien käyttöön.

Intune-portaalin avulla järjestelmänvalvojat voivat helposti ottaa nämä asetukset käyttöön Power BI -sovelluksessa määrityskäytäntöjen kautta. Kaikkia MDM-palveluita kuitenkin tuetaan. Jos käytössäsi ei ole Intunea, katso MDM-työkalujen ohjeista, miten voit ottaa nämä asetukset käyttöön.

## <a name="next-steps"></a>Seuraavat vaiheet

* Hanki Power BI -mobiilisovellus [App Storesta](https://apps.apple.com/app/microsoft-power-bi/id929738808) ja [Google Playstä](https://play.google.com/store/apps/details?id=com.microsoft.powerbim&amp;amp;clcid=0x409)
* Seuraa [@MSPowerBI Twitterissä](https://twitter.com/MSPowerBI)
* Liity keskusteluun [Power BI -yhteisössä](https://community.powerbi.com/)
