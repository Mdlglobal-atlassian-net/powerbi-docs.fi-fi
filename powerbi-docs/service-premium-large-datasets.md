---
title: Power BI Premiumin suurten tietojoukkojen tuki
description: Power BI Premium tukee nyt enintään 10 gigatavun tietojoukkoja.
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 02/27/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: fa05fd6808ebe78d5d17e2ad3d93fbcf22f7d3c9
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34298592"
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Power BI Premiumin suurten tietojoukkojen tuki

Power BI Premium tukee kooltaan enintään 10 gigatavun kokoisten Power BI Desktop (.pbix) -tiedostojen lataamista palvelimeen. Kun tiedosto on ladannut, tietojoukko voidaan päivittää enintään 12 gigatavun kokoiseksi. Kun haluat käyttää suurta tietojoukkoa, julkaise se työtilassa, johon on määritetty Premium-kapasiteetti.
 
## <a name="best-practices"></a>Parhaat käytännöt

Tässä osassa esitetään suurten tietojoukkojen käsittelemisen parhaat käytännöt.

**Suuret mallit voivat vaatia erittäin paljon resursseja** kapasiteetista. Suosittelemme vähintään P1 SKU:ta yli 1 gigatavun malleille. Seuraavassa taulukossa kuvataan suositellut varastointiyksiköt eri .pbix-koille:


   |Varastointiyksikkö  |.pbix:n koko   |
   |---------|---------|
   |P1    | < 3 Gt        |
   |P2    | < 6 Gt        |
   |P3    | enintään 10 Gt   |



**.pbix-tiedostot kuvaavat tietoja erittäin tehokkaasti pakatussa tilassa**. Tietoja laajennetaan todennäköisesti useita kertoja, kun ne ladataan muistiin, ja uudelleen useita kertoja tietojen päivittämisen aikana.

**Suurten tietojoukkojen ajoitettu päivitys voi kestää kauan** ja vaatia paljon resursseja. Älä siis ajoita useita päivityksiä päällekkäin. Huomaa myös, että ajoitettujen päivitystöiden aikakatkaisu on kaksinkertaistettu neljään tuntiin kaikille tämän kapasiteetin tietojoukoille.

**Suurten tietojoukkojen alkuperäisen raportin lataaminen voi kestää kauan**, jos tietojoukon edellisestä käyttökerrasta on kulunut aikaa, koska malli on ladattu Premium-kapasiteetin muistiin. Pitkään latautuvissa raporteissa latauksen edistyminen näkyy latauspalkissa.

**Jos poistat työtilan Premium-kapasiteetista**, mallin ja kaikkien siihen liittyvien raporttien ja raporttinäkymien toiminta loppuu.

**Vaikka kyselykohtaiset muisti- ja aikarajoitukset ovat paljon suuremmat Premium-kapasiteetissa**, on suositeltavaa rajoittaa visualisoinnit näyttämään vain tarpeellinen sisältö käyttämällä suodattimia ja osittajia.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI Premium?](service-premium.md)  
[Power BI Premiumin julkaisutiedot](service-premium-release-notes.md)  
[Microsoft Power BI Premiumin tekninen raportti](https://aka.ms/pbipremiumwhitepaper)  
[Power BI:n yrityskäyttöönoton suunnittelemisen tekninen raportti](https://aka.ms/pbienterprisedeploy)  
[Laajennetun Pro-kokeiluversion aktivointi](service-extended-pro-trial.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
