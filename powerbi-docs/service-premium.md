---
title: Mikä on Microsoft Power BI Premium?
description: Power BI Premium tarjoaa organisaatiollesi tai tiimillesi varatun kapasiteetin, luotettavamman suorituskyvyn ja suuremmat tietomäärät ilman käyttäjäkohtaisten käyttöoikeuksien hankkimista.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 03/12/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: f327cb95c10756f079778d20e62cba4871b95c02
ms.sourcegitcommit: ac63b08a4085de35e1968fa90f2f49ea001b50c5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/18/2019
ms.locfileid: "57964935"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Mikä on Microsoft Power BI Premium?

> [!NOTE]
> Tätä artikkelia päivitetään parhaillaan. Tulossa on uusien ominaisuuksien kuvauksia, tietojen tarkennuksia ja luettavuutta parantavia muutoksia. Katso uusimmat tiedot kohdasta [Power BI Premium -kapasiteettien käyttöönotto ja hallinta](whitepaper-powerbi-premium-deployment.md).

Power BI Premium tarjoaa organisaatiollesi resurssit Power BI -palvelun käyttämiseen. Se mahdollistaa entistä luotettavamman suorituskyvyn ja suuremmat tietomäärät. Premiumin avulla voit jakaa sisältöä laajasti ilman kuluttajakohtaisten Pro-käyttöoikeuksien hankkimista.  

## <a name="premium-capacity-and-shared-capacity"></a>Premium-kapasiteetti ja jaettu kapasiteetti

Voit hyödyntää Power BI Premiumia määrittämällä työtiloja *Premium-kapasiteettiin*. Premium-kapasiteetti on organisaatiollesi varattu resurssi. Työtiloilla, joille ei ole määritetty Premium-kapasiteettia, on *jaettu kapasiteetti*. Kun käytössä on jaettu kapasiteetti, työnkulut suoritetaan muiden asiakkaiden kanssa jaetuissa laskennallisissa resursseissa.

Seuraavassa kuvassa on esitetty Premium-kapasiteetin ja jaetun kapasiteetin välinen suhde Contoso-organisaation avulla.

![Power BI Premiumin kuva](media/service-premium/premium-chart.png)

| Alue | Kuvaus |
| --- | --- |
| **(1)** Premium-kapasiteetin sisältämät kohteet | <ul><li>Sovellustyötilojen käyttäminen (jäsenenä tai järjestelmänvalvojana) edellyttää Power BI Pro -käyttöoikeutta.<li>Sovelluksen jakaminen edellyttää Pro-käyttöoikeutta, mutta sitä ei edellytetä sovellukseen käyttämiseen.<li>Kaikki koontinäytön vastaanottajat voivat määrittää tietoilmoituksia heille myönnetystä käyttöoikeudesta riippumatta.<li>Upottamiseen tarkoitetut REST-ohjelmointirajapinnat käyttävät käyttäjätilin sijasta palvelutiliä, jolla on Pro-käyttöoikeus.</ul> |
| **(2)** Oma työtila jaetussa kapasiteetissa | <ul><li>Sovelluksen jakaminen ja käyttäminen edellyttävät kumpikin Pro-käyttöoikeutta.</ul> |
| **(3)** Sovellustyötilat jaetussa kapasiteetissa | <ul><li>Minkä tahansa sovelluksen käyttäminen edellyttää Pro-käyttöoikeutta.</ul>|
| | |

Jaetussa kapasiteetissa Power BI määrittää yksittäisille käyttäjille enemmän rajoituksia laadukkaan käyttökokemuksen takaamiseksi kaikille käyttäjille. Työtilasi on oletusarvoisesti jaetussa kapasiteetissa, mukaan lukien *oma työtila* ja sovelluksen työtilat.

Alla olevassa taulukossa on yhteenveto jaetun kapasiteetin ja Premium-kapasiteetin välisistä eroista:

|  | Jaettu kapasiteetti | Power BI Premium -kapasiteetti |
| --- | --- | --- |
| **Päivitystaajuus** |8/päivä |48/päivä |
| Eristys erillisellä laitteistolla |![Ei käytettävissä](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| Yritysjakelu *kaikille käyttäjille* | | |
| Sovellukset ja jakaminen |![Ei käytettävissä](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| Upotettu ohjelmointirajapinta ja ohjausobjektit |![Ei käytettävissä](media/service-premium/not-available.png) |![](media/service-premium/available.png)<sup>[1](#fnt1)</sup> |
| Power BI -raporttien paikallinen julkaisu |![Ei käytettävissä](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| | | |

<a name="fnt1">1</a> Parannuksia tulossa Power BI Premiumiin.



### <a name="premium-capacity-nodes"></a>Premium-kapasiteetin solmut

Power BI Premium on saatavilla solmumäärityksinä eri näennäisydinkapasiteeteilla. Jos haluat lisätietoja tietyistä varastointiyksikkövaihtoehdoista ja niiden hinnoista, katso [Power BI:n hinnoittelu](https://powerbi.microsoft.com/pricing/). [Kustannuslaskin](https://powerbi.microsoft.com/calculator/) on myös käytettävissä. Jos haluat lisätietoja upotetun analytiikan kapasiteetin suunnittelusta, katso [Power BI:n yrityskäyttöönoton suunnittelemisen tekninen raportti](https://aka.ms/pbienterprisedeploy). Yhteenveto:

* P-solmuja voi käyttää upotetuissa tai palvelun käyttöönotoissa.

* EM-solmuja voi käyttää vain upotetuissa käyttöönotoissa. EM-solmut eivät tue Premium-ominaisuuksia, kuten sovellusten jakamista käyttäjille, joilla ei ole Power BI Pro -käyttöoikeutta.

| Kapasiteetin solmu | V-ytimiä yhteensä<br/>*(Tausta+edusta)*  | Taustan näennäisytimet <sup>[1](#fn1)</sup> | Edustan näennäisytimet <sup>[2](#fn2)</sup> | DirectQueryn/live-yhteyden rajoitukset | Samanaikaisten päivitysten enimmäismäärä |
| --- | --- | --- | --- | --- | --- |
| EM1 (kuukausittain) |1 näennäisydin |0,5 näennäisydintä, 2,5 Gt RAM |0,5 näennäisydintä |3,75 sekunnissa |  1 |
| EM2 (kuukausittain) |2 näennäisydintä |1 näennäisydin, 5 Gt RAM |1 näennäisydin |7,5 sekunnissa |  2 |
| EM3 (kuukausittain) |4 näennäisydintä |2 näennäisydintä, 10 Gt RAM |2 näennäisydintä | 15 | 3 |
| P1 |8 näennäisydintä |4 näennäisydintä, 25 Gt RAM |4 näennäisydintä |30 sekunnissa | 6 |
| P2 |16 näennäisydintä |8 näennäisydintä, 50 Gt RAM |8 näennäisydintä |60 sekunnissa | 12 |
| P3 |32 näennäisydintä |16 näennäisydintä, 100 Gt RAM |16 näennäisydintä |120 sekunnissa | 24 |
| | | | | | |

<a name="fn1">1</a>: Edustan näennäisytimet vastaavat verkkopalvelusta. Tähän sisältyvät esimerkiksi raporttinäkymän ja raportin tiedostohallinta, käyttöoikeuksien hallinta, ajoitus, ohjelmointirajapinnat, lataukset ja yleisesti ottaen kaikki, mikä liittyy käyttökokemukseen. 

<a name="fn2">2</a>: Taustan näennäisytimet vastaavat raskaasta työstä eli kyselyiden käsittelystä, välimuistin hallinnasta, R-palvelinten suorittamisesta, tietojen päivittämisestä, luonnollisen kielen käsittelystä, reaaliaikaisista syötteistä sekä raporttien ja kuvien palvelinpuolen hahmontamisesta. Taustan v-ytimille varataan myös tietty määrä muistia. Riittävä muisti on erityisen tärkeä, kun käsitellään suuria tietomalleja tai useita aktiivisia tietojoukkoja.

## <a name="workloads-in-premium-capacity"></a>Kuormitukset Premium-kapasiteetissa

Oletusarvoisesti Power BI Premiumin ja Power BI Embeddedin kapasiteetit tukevat vain kuormitusta, joka liittyy Power BI -kyselyjen suorittamiseen pilvipalvelussa. Premium tukee myös muita kuormituksia **AI**:n, **tietovoiden** ja **sivutettujen raporttien** käsittelyyn. Ennen kuin nämä työnkulut voivat käyttää kapasiteettisi resursseja, ne on otettava käyttöön Power BI -hallintaportaalissa tai Power BI REST -ohjelmointirajapinnan kautta. Kullakin kuormituksella on oletusasetukset sen suhteen, paljonko muistia kukin kuormitus voi enintään kuluttaa. Voit kuitenkin määrittää erilaisia muistin kulutusasetuksia ja määrittää niiden avulla, miten kuormitukset vaikuttavat toisiinsa ja kuluttavat kapasiteetin resursseja. Lisätietoja on artikkelissa [Kuormitusten määrittäminen](service-admin-premium-workloads.md).

## <a name="power-bi-report-server"></a>Power BI -raporttipalvelin

Power BI Premium sisältää myös mahdollisuuden suorittaa Power BI -raporttipalvelin paikallisesti organisaatiossasi. Lisätietoja on artikkelissa [Power BI -raporttipalvelimen käytön aloittaminen](report-server/get-started.md).

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI Premium -kapasiteettien käyttöönotto ja hallinta](whitepaper-powerbi-premium-deployment.md)   
[Ohjeet Power BI Premiumin ostamiseen](service-admin-premium-purchase.md)   
[Power BI Premiumin usein kysytyt kysymykset](service-premium-faq.md)   



Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
