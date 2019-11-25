---
title: Power BI -sovelluksen määritykset
description: Power BI -sovelluksen toiminnan mukauttaminen MDM-työkalun avulla
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 11/07/2019
ms.author: painbar
ms.openlocfilehash: a517ee4edce6e18eadcbe2b1b6765684f8121b21
ms.sourcegitcommit: 768e1e4b19fe8c7627010127c2420d63021cb542
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199433"
---
# <a name="remotely-configure-power-bi-app-using-mobile-device-management-mdm-tool"></a>Power BI -sovelluksen etämääritys mobiililaitteiden hallintatyökalun (MDM) avulla

Power BI:n iOS- ja Android-mobiilisovellukset tukevat sovellusasetuksia, joiden avulla Office 365- ja mobiililaitteiden hallintatyökalupalveluiden (esim. Intune) järjestelmänvalvojat voivat mukauttaa sovelluksen toimintaa.

Power BI -mobiilisovellus tukee määritystä seuraavissa tilanteissa:

- Raporttipalvelimen määrittäminen (iOS ja Android)
- Tietosuoja-asetukset (iOS)

## <a name="report-server-configuration-ios-and-android"></a>Raporttipalvelimen määrittäminen (iOS ja Android)

Power BI:n iOS- ja Android-sovelluksen avulla järjestelmänvalvojat voivat pakottaa raporttipalvelimen määritykset rekisteröidyille laitteille.

| Avain | Tyyppi | Kuvaus |
|---|---|---|
| com.microsoft.powerbi.mobile.ServerURL | Merkkijono | Raporttipalvelimen URL-osoite.<br><br>Tulee alkaa merkkijonolla http tai https.|
| com.microsoft.powerbi.mobile.ServerUsername | Merkkijono | [valinnainen]<br><br>Käyttäjänimi, jota käytetään muodostettaessa yhteyttä palvelimeen.<br><br>Jos sellaista ei ole, sovellus pyytää käyttäjää antamaan käyttäjänimen yhteyden muodostamista varten.|
| com.microsoft.powerbi.mobile.ServerDisplayName | Merkkijono | [valinnainen]<br><br>Oletusarvo on ”Raporttipalvelin”<br><br>Kutsumanimi, joka edustaa palvelinta sovelluksessa. |
| com.microsoft.powerbi.mobile.OverrideServerDetails | Totuusarvo | [valinnainen]<br><br>Oletusarvo on Tosi (True). Kun arvoksi on määritetty Tosi, se ohittaa mobiililaitteessa jo olevat raporttipalvelimen määritelmät. Tässä yhteydessä poistetaan olemassa olevat palvelimet, jotka on jo määritetty. Ohituksen Tosi-arvo estää käyttäjää poistamista kyseistä määritystä.<br><br>Epätosi-arvo lisää lähetetyt arvot poistamatta olemassa olevia asetuksia. Jos sama palvelimen URL-osoite on jo määritetty mobiilisovelluksessa, sovellus jättää sen määrityksen ennalleen. Sovellus ei pyydä käyttäjää todentamaan uudelleen samalle palvelimelle. |

## <a name="data-protection-settings-ios"></a>Tietosuoja-asetukset (iOS)

Power BI:n iOS-sovellus tarjoaa järjestelmänvalvojille mahdollisuuden mukauttaa suojaus- ja tietosuoja-asetusten oletusmäärityksiä. Voit vaatia käyttäjiltä kasvojentunnistusta, kosketustunnistusta tai tunnuskoodia Power BI -sovelluksen käyttämiseksi.

| Avain | Tyyppi | Kuvaus |
|---|---|---|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Totuusarvo | Oletusarvo on False. <br><br>Voit edellyttää käyttäjiltä biometristä tunnistusta, kuten kasvojen- tai kosketustunnistusta, jotta he voivat käyttää sovellusta laitteellaan. Biometrista tunnistusta käytetään tarvittaessa todennuksen lisäksi.<br><br>Jos käytössä on sovelluksen suojauskäytäntöjä, Microsoft suosittelee asetuksen poistamista käytöstä kahden kirjautumiskehotteen välttämiseksi. |

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
