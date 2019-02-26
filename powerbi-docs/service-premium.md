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
ms.date: 01/15/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: a048f589b19acd1a7c38a5b81cf781d1e76b7b5b
ms.sourcegitcommit: 187d20180d9bae5a2ec53748cede9e7301e0343e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/23/2019
ms.locfileid: "56725336"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Mikä on Microsoft Power BI Premium?

Microsoft Power BI Premium tarjoaa organisaatiollesi resurssit Power BI -palvelun käyttämiseen. Se mahdollistaa entistä luotettavamman suorituskyvyn ja suuremmat tietomäärät. Premiumin avulla voit jakaa sisältöä laajasti ilman kuluttajakohtaisten Pro-käyttöoikeuksien hankkimista.  

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

| Kapasiteetin solmu | V-ytimiä yhteensä<br/>*(Tausta+edusta)*  | Taustan näennäisytimet <sup>[1](#fn1)</sup> | Edustan näennäisytimet <sup>[2](#fn2)</sup> | DirectQueryn/live-yhteyden rajoitukset | Samanaikaisten päivitysten enimmäismäärä |  Käytettävyys
| --- | --- | --- | --- | --- | --- | --- | --- |
| EM1 (kuukausittain) |1 näennäisydin |0,5 näennäisydintä, 2,5 Gt RAM |0,5 näennäisydintä |3,75 sekunnissa |  1 | Käytettävissä |
| EM2 (kuukausittain) |2 näennäisydintä |1 näennäisydin, 5 Gt RAM |1 näennäisydin |7,5 sekunnissa |  2 | Käytettävissä |
| EM3 (kuukausittain) |4 näennäisydintä |2 näennäisydintä, 10 Gt RAM |2 näennäisydintä | | 3 |  Käytettävissä |
| P1 |8 näennäisydintä |4 näennäisydintä, 25 Gt RAM |4 näennäisydintä |30 sekunnissa | 6 | Käytettävissä (kuukausittainen vaihtoehto myös käytettävissä) |
| P2 |16 näennäisydintä |8 näennäisydintä, 50 Gt RAM |8 näennäisydintä |60 sekunnissa | 12 | Käytettävissä |
| P3 |32 näennäisydintä |16 näennäisydintä, 100 Gt RAM |16 näennäisydintä |120 sekunnissa | 24 | Käytettävissä |
| | | | | | | |

<a name="fn1">1</a>: Edustan näennäisytimet vastaavat verkkopalvelusta. Tähän sisältyvät esimerkiksi raporttinäkymän ja raportin tiedostohallinta, käyttöoikeuksien hallinta, ajoitus, ohjelmointirajapinnat, lataukset ja yleisesti ottaen kaikki, mikä liittyy käyttökokemukseen. 

<a name="fn2">2</a>: Taustan näennäisytimet vastaavat raskaasta työstä eli kyselyiden käsittelystä, välimuistin hallinnasta, R-palvelinten suorittamisesta, tietojen päivittämisestä, luonnollisen kielen käsittelystä, reaaliaikaisista syötteistä sekä raporttien ja kuvien palvelinpuolen hahmontamisesta. Taustan v-ytimille varataan myös tietty määrä muistia. Riittävä muisti on erityisen tärkeä, kun käsitellään suuria tietomalleja tai useita aktiivisia tietojoukkoja.

## <a name="workloads-in-premium-capacity"></a>Kuormitukset Premium-kapasiteetissa

Voit ajatella kuormituksia Power BI:ssä palveluina, jotka voit paljastaa käyttäjille. Oletusarvoisesti **Power BI Premiumin** ja **Power BI Embeddedin** kapasiteetit tukevat vain kuormitusta, joka liittyy Power BI -kyselyiden suorittamiseen pilvipalvelussa.

Esikatselun tuki tarjotaan nyt myös kahdelle muulle kuormitukselle: **sivutetut raportit** ja **tietovuot**. Voit ottaa nämä kuormitukset käyttöön Power BI -hallintaportaalin tai Power BI REST -ohjelmointirajapinnan kautta. Voit määrittää enimmäismuistin jokaiselle kuormitukselle. Näin voit hallita sitä, miten eri kuormitukset vaikuttavat toistensa toimintaan. Lisätietoja on kohdassa [Kuormituksien määrittäminen](service-admin-premium-manage.md#configure-workloads).

### <a name="default-memory-settings"></a>Oletusmuistiasetukset

Seuraava taulukko näyttää muistin oletus- ja vähimmäisarvot, jotka perustuvat käytettävissä oleviin erilaisiin [kapasiteettisolmuihin](#premium-capacity-nodes). Muistin kohdistetaan tietovoille dynaamisesti, mutta sivutetuille raporteille staattisesti. Jos haluat lisätietoja, katso seuraavassa osio: [Huomioitavaa sivutetuissa raporteissa](#considerations-for-paginated-reports).

#### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Microsoft Office -varastointiyksiköt Software as a Service (SaaS) -skenaarioille

|                     | EM3                      | P1                       | P2                      | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|
| Sivutetut raportit | – | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % | Oletus 20 %, vähintään 2,5 % |
| Tietovuot | Oletus 20 %, vähintään 8 %  | Oletus 20 %, vähintään 4 %  | Oletus 20 %, vähintään 2 % | Oletus 20 %, vähintään 1 %  |
| | | | | |

#### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Microsoft Azure -varastointiyksiköt Platform as a Service (PaaS) -skenaarioille

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| Sivutetut raportit | –                      | –                      | –                     | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % | Oletus 20 %, vähintään 2,5 % |
| Tietovuot         | Oletus 27 %, vähintään 27 % | Oletus 20 %, vähintään 16 % | Oletus 20 %, vähintään 8 % | Oletus 20 %, vähintään 4 %  | Oletus 20 %, vähintään 2 % | Oletus 20 %, vähintään 1 %   |

### <a name="considerations-for-paginated-reports"></a>Huomioitavaa sivutetuissa raporteissa

Jos käytät sivutettuja raportteja, muista, että niiden avulla voit suorittaa omaa koodia raporttia hahmontaessasi. Näin voit esimerkiksi sallia tekstin värin dynaamisen muuttamisen sisällön perusteella. Power BI Premium -kapasiteetin turvaamiseksi sivutetut raportit suoritetaan kapasiteetin sisäisessä erillisessä tilassa. Tälle tilalle osoitetaan kaikki määrittämäsi muisti riippumatta siitä, onko kuormitus aktiivinen. Jos käytät Power BI -raportteja tai tietovoita samassa kapasiteetissa, varmista, että olet määrittänyt sivutetuille raporteille riittävän vähän muistia, jotta muiden kuormitusten nopeus ei kärsi.

Sivutetut raportit -kuormitus saattaa lakata toimimasta joissain harvinaisissa tapauksissa. Näissä tapauksissa kuormitus näyttää virhetilan hallintaportaalissa ja raportin hahmontaminen aikakatkaistaan käyttäjiltä. Voit ratkaista ongelman poistamalla kuormituksen käytöstä ja ottamalla sen uudelleen käyttöön.

## <a name="power-bi-report-server"></a>Power BI -raporttipalvelin

Power BI Premium sisältää myös mahdollisuuden suorittaa Power BI -raporttipalvelin paikallisesti organisaatiossasi. Lisätietoja on artikkelissa [Power BI -raporttipalvelimen käytön aloittaminen](report-server/get-started.md).

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI Premiumin UKK](service-premium-faq.md)
[Power BI Premiumin ostaminen](service-admin-premium-purchase.md)
[Power BI Premiumin hallinta](service-admin-premium-manage.md)
[Microsoft Power BI Premiumin tekninen raportti](https://aka.ms/pbipremiumwhitepaper)
[Power BI:n yrityskäyttöönoton suunnittelemisen tekninen raportti](https://aka.ms/pbienterprisedeploy)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
