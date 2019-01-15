---
title: Power BI Premiumin suurten tietojoukkojen tuki
description: Power BI Premium tukee nyt enintään 10 gigatavun tietojoukkoja.
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: 3aa8ef5ea7a51da226d48869bdf255900dee8d6d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284192"
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Power BI Premiumin suurten tietojoukkojen tuki

Power BI Premium tukee kooltaan enintään 10 gigatavun kokoisten Power BI Desktop (.pbix) -tiedostojen lataamista palvelimeen. Kun tiedosto on ladannut, tietojoukko voidaan päivittää enintään 12 gigatavun kokoiseksi. Kun haluat käyttää suurta tietojoukkoa, julkaise se työtilassa, johon on määritetty Premium-kapasiteetti.
 
## <a name="best-practices"></a>Parhaat käytännöt

Tässä osassa esitetään suurten tietojoukkojen käsittelemisen parhaat käytännöt.

**Suuret mallit voivat vaatia erittäin paljon resursseja** kapasiteetiltasi. Suosittelemme vähintään P1 SKU:ta kaikille yli 1 Gt:n malleille. Vaikka suurten mallien julkaiseminen työtiloihin, joita tuetaan A-varastointiyksiköillä A3:een asti, voikin onnistua, niitä ei voida päivittää.

Seuraavassa taulukossa kuvataan suositellut varastointiyksiköt eri .pbix-koille:

   |SKU  |.pbix:n koko   |
   |---------|---------|
   |P1    | < 3 Gt        |
   |P2    | < 6 Gt        |
   |P3, P4, P5    | enintään 10 Gt   |

Power BI Embedded A4 -varastointiyksikkö vastaa P1-varastointiyksikköä, A5 = P2 ja A6 = P3. Huomaa, että suurten mallien julkaiseminen A- ja EM-varastointiyksiköihin voi palauttaa virheitä, jotka eivät liity erityisesti mallin kokorajoituksen virheeseen jaetussa kapasiteetissa. Suurten mallien päivitysvirheet A- ja EM-varastointiyksiköissä osoittavat todennäköisesti aikakatkaisuihin. Pyrimme parantamaan näiden skenaarioiden virheviestejä.

**.pbix-tiedostot kuvaavat tietoja erittäin tehokkaasti pakatussa tilassa**. Tietoja laajennetaan todennäköisesti useita kertoja, kun ne ladataan muistiin, ja uudelleen useita kertoja tietojen päivittämisen aikana.

**Suurten tietojoukkojen ajoitettu päivitys voi kestää kauan** ja vaatia paljon resursseja. Älä siis ajoita useita päivityksiä päällekkäin. Huomaa myös, että ajoitettujen päivitystöiden aikakatkaisu on kaksinkertaistettu neljään tuntiin kaikille tämän kapasiteetin tietojoukoille. Suosittelemme [lisäävää päivitystä](service-premium-incremental-refresh.md), koska se on nopeampi, luotettavampi ja kuluttaa vähemmän resursseja.

**Suurten tietojoukkojen alkuperäisen raportin lataaminen voi kestää kauan**, jos tietojoukon edellisestä käyttökerrasta on kulunut aikaa, koska malli on ladattu Premium-kapasiteetin muistiin. Pitkään latautuvissa raporteissa latauksen edistyminen näkyy latauspalkissa.

**Jos poistat työtilan Premium-kapasiteetista**, mallin ja kaikkien siihen liittyvien raporttien ja raporttinäkymien toiminta loppuu.

**Vaikka kyselykohtaiset muisti- ja aikarajoitukset ovat paljon suuremmat Premium-kapasiteetissa**, on suositeltavaa rajoittaa visualisoinnit näyttämään vain tarpeellinen sisältö käyttämällä suodattimia ja osittajia.

**Seuraavat vaiheet**

[Mikä on Power BI Premium? ](service-premium.md)
[Power BI Premiumin julkaisutiedot](service-premium-release-notes.md)
[Microsoft Power BI Premiumin tekninen raportti](https://aka.ms/pbipremiumwhitepaper)
[Power BI:n yrityskäyttöönoton suunnittelemisen tekninen raportti](https://aka.ms/pbienterprisedeploy)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
