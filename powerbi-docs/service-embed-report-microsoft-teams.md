---
title: Raporttien upottaminen Microsoft Teamsin Power BI ‑välilehdellä
description: Microsoft Teamsin Power BI ‑välilehden avulla voit helposti upottaa vuorovaikutteisia raportteja kanaviin ja keskusteluihin.
author: LukaszPawlowski-MS
ms.author: lukaszp
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 01/31/2020
ms.openlocfilehash: fb4846a777dda4787e1ed0be7de869367a616ea5
ms.sourcegitcommit: b22a9a43f61ed7fc0ced1924eec71b2534ac63f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/21/2020
ms.locfileid: "77530483"
---
# <a name="embed-report-with-the-power-bi-tab-for-microsoft-teams"></a>Raporttien upottaminen Microsoft Teamsin Power BI ‑välilehden avulla

Microsoft Teamsin päivitetyllä Power BI ‑välilehden avulla voit helposti upottaa vuorovaikutteisia raportteja Microsoft Teamsin kanaviin ja keskusteluihin.

Microsoft Teamsin Power BI ‑välilehden avulla työtoverisi voivat löytää tiimisi käyttämät tiedot helposti ja keskustella niistä tiimin kanavilla.

## <a name="requirements"></a>Vaatimukset

**Microsoft Teamsin Power BI ‑välilehden** toiminta edellyttää seuraavaa:

- Power BI Pro ‑käyttöoikeus tai raportin tallentaminen [Power BI Premium ‑kapasiteettiin (EM tai P SKU)](service-premium-what-is.md) Power BI ‑käyttöoikeudella.
- Microsoft Teamsin Power BI ‑välilehti.
- Käyttäjän on kirjauduttava sisään Power BI -palveluun ja aktivoitava Power BI -käyttöoikeutensa, jotta hän voi käyttää raporttia.
- Käyttäjällä on oltava raportin katseluoikeus.

## <a name="embed-your-report"></a>Upota raportti
Jos haluat upottaa raportin Microsoft Teams ‑kanavaan tai ‑keskusteluun, lisää se alla kuvatulla tavalla.

1. Avaa haluamasi kanava tai keskustelu Microsoft Teamsissa ja valitse **+** -kuvake.

    ![Välilehden lisääminen kanavaan tai keskusteluun](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-add.png)

2. Valitse Power BI ‑välilehti.

    ![Microsoft Teamsin välilehtiluettelo, jossa Power BI näkyy](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab.png)

3. Valitse annettujen asetusten avulla raportti työtilasta, kanssasi jaetuista tai Power BI ‑sovelluksesta

    ![Microsoft Teamsin Power BI ‑välilehden asetukset](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab-settings.png)

4. Välilehden nimi päivittyy automaattisesti vastaamaan raportin nimeä, mutta voit halutessasi muuttaa sitä. 

5. Paina **Tallenna**.

## <a name="supported-reports"></a>Tuetut raportit

Välilehti mahdollistaa seuraavien raporttien upottamisen:

- Vuorovaikutteiset ja sivutetut raportit
- Raportit omassa työtilassa, uudenlaisissa työtiloissa ja perinteisissä työtiloissa
- Raportit Power BI -sovelluksissa


## <a name="grant-access-to-reports"></a>Raporttien käyttöoikeuksien myöntäminen

Kun raportti upotetaan Microsoft Teamsiin, käyttäjät eivät saa automaattisesti raportin tarkasteluoikeuksia. Sinun on [annettava käyttäjille raportin katseluoikeudet Power BI:ssä](service-share-dashboards.md). Tämä on helpompaa, jos käytät Office 365 ‑ryhmää. 

> [!IMPORTANT]
> Katso Power BI -palvelussa, kuka saa nähdä raportin, ja myönnä käyttöoikeudet niille, jotka eivät ole luettelossa.

Voit varmistaa, että kaikki ryhmäsi jäsenet voivat käyttää upottamiasi raportteja, esimerkiksi sijoittamalla ne yksittäiseen Power BI:n työtilaan ja antamalla tiimin Office 365 ‑ryhmälle työtilan käyttöoikeudet.

## <a name="known-issues-and-limitations"></a>Tunnetut ongelmat ja rajoitukset

- Power BI ei tue samoja lokalisoituja kieliä kuin Microsoft Teams. Sen vuoksi et välttämättä näe oikeaa lokalisointia upotetussa raportissa.
- Power BI:n raporttinäkymiä ei voi upottaa Microsoft Teamsin Power BI ‑välilehteen.
- Käyttäjä, jolla ei ole Power BI:n tai raportin käyttöoikeutta, saa ”Sisältö ei ole käytettävissä” ‑sanoman.
- Ongelmia saattaa ilmetä, jos käytät Internet Explorer 10:tä. <!--You can look at the [browsers support for Power BI](consumer/end-user-browsers.md) and for [Office 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- [URL-suodattimia](service-url-filters.md) ei tueta Microsoft Teamsin Power BI ‑välilehdellä.
- Power BI:n uusi välilehti ei ole käytettävissä kansallisissa pilvipalveluissa. Käytettävissä saattaa olla vanhempi versio, joka ei tue uudenlaisia työtiloja tai raportteja Power BI ‑sovelluksissa. 
- Kun välilehti on tallennettu, välilehden nimeä ei voi muuttaa välilehden asetuksista. Voit muuttaa välilehden nimen Nimeä uudelleen ‑toiminnolla.

## <a name="next-steps"></a>Seuraavat vaiheet
- [Koontinäytön jakaminen työtovereille ja muille](service-share-dashboards.md)  
- [Sovelluksen luominen ja jakaminen Power BI:ssä](service-create-distribute-apps.md)  
- [Mikä on Power BI Premium?](service-premium-what-is.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
