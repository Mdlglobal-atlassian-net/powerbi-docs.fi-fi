---
title: Power BI:n iOS-sovelluksen määritykset
description: Power BI:n iOS-sovelluksen toiminnan mukauttaminen MDM-työkalun avulla
author: paulinbar
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/07/2019
ms.author: mshenhav
ms.openlocfilehash: bc9c6dd8cd892ab0304cc5a99a3bb780486f32f0
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/16/2019
ms.locfileid: "70160147"
---
# <a name="remotely-configure-power-bi-ios-app-using-mobile-device-management-mdm-tool"></a>Power BI:n iOS-sovelluksen etämääritys mobiililaitteiden hallintatyökalun (MDM) avulla

Power BI:n iOS-mobiilisovellus tukee sovellusasetuksia, joiden avulla Office 365- ja mobiililaitteiden hallintatyökalujen (esim. Intune) järjestelmänvalvojat voivat mukauttaa sovelluksen toimintaa.

Power BI:n iOS-mobiilisovellus tukee määritystä seuraavissa tilanteissa:

- Raporttipalvelimen määrittäminen
- Tietosuoja-asetukset

## <a name="report-server-configuration"></a>Raporttipalvelimen määrittäminen

Power BI:n iOS-sovelluksen avulla järjestelmänvalvojat voivat pakottaa raporttipalvelimen määritykset rekisteröidyille laitteille.

| Avain | Tyyppi | Kuvaus |
|---|---|---|
| com.microsoft.powerbi.mobile.ServerURL | Merkkijono | Raporttipalvelimen URL-osoite.<br><br>Tulee alkaa merkkijonolla http tai https.|
| com.microsoft.powerbi.mobile.ServerUsername | Merkkijono | [valinnainen]<br><br>Käyttäjänimi, jota käytetään muodostettaessa yhteyttä palvelimeen.<br><br>Jos sellaista ei ole, sovellus pyytää käyttäjää antamaan käyttäjänimen yhteyden muodostamista varten.|
| com.microsoft.powerbi.mobile.ServerDisplayName | Merkkijono | [valinnainen]<br><br>Oletusarvo on ”Raporttipalvelin”<br><br>Kutsumanimi, joka edustaa palvelinta sovelluksessa. |
| com.microsoft.powerbi.mobile.OverrideServerDetails | Totuusarvo | [valinnainen]<br><br>Oletusarvo on Tosi (True). Kun arvoksi on määritetty Tosi, se ohittaa mobiililaitteessa jo olevat raporttipalvelimen määritelmät. Tässä yhteydessä poistetaan olemassa olevat palvelimet, jotka on jo määritetty. Ohituksen Tosi-arvo estää käyttäjää poistamista kyseistä määritystä.<br><br>Epätosi-arvo lisää lähetetyt arvot poistamatta olemassa olevia asetuksia. Jos sama palvelimen URL-osoite on jo määritetty mobiilisovelluksessa, sovellus jättää sen määrityksen ennalleen. Sovellus ei pyydä käyttäjää todentamaan uudelleen samalle palvelimelle. |

## <a name="data-protection-setting"></a>Tietosuoja-asetus

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

Intune-portaalin avulla järjestelmänvalvojat voivat helposti ottaa nämä asetukset käyttöön Power BI:n iOS-sovelluksessa määrityskäytäntöjen kautta.
Kaikkia MDM-palveluita kuitenkin tuetaan. Jos käytössäsi ei ole Intunea, katso MDM-työkalujen ohjeista, miten voit ottaa nämä asetukset käyttöön.

## <a name="next-steps"></a>Seuraavat vaiheet

* Lataa [Power BI iPhone -mobiilisovellus](http://go.microsoft.com/fwlink/?LinkId=522062)
* Seuraa [@MSPowerBI Twitterissä](https://twitter.com/MSPowerBI)
* Liity keskusteluun [Power BI -yhteisössä](http://community.powerbi.com/)
