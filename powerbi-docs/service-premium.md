---
title: Power BI Premium – mikä se on?
description: Power BI Premium tarjoaa organisaatiollesi tai tiimillesi varatun kapasiteetin, luotettavamman suorituskyvyn ja suuremmat tietomäärät ilman käyttäjäkohtaisten käyttöoikeuksien hankkimista.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2018
ms.author: mblythe
LocalizationGroup: Premium
ms.openlocfilehash: 81a03c7728d92bcc78dba9a02cbe4c45f582fd3d
ms.sourcegitcommit: 8b2ae15eb0e39cce29f3bf466ab7768f3f7c7815
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2018
ms.locfileid: "40257343"
---
# <a name="power-bi-premium---what-is-it"></a>Power BI Premium – mikä se on?
Power BI Premium tarjoaa organisaatiollesi tai tiimillesi resurssit Power BI -palvelun käyttämiseen. Se mahdollistaa entistä luotettavamman suorituskyvyn ja suuremmat tietomäärät. Premiumin avulla voit jakaa sisältöä laajasti ilman käyttäjäkohtaisten käyttöoikeuksien hankkimista.

Voit hyödyntää Power BI Premiumia määrittämällä työtiloja Premium-kapasiteettiin. *Premium-kapasiteetti* on organisaatiollesi varattu resurssi. Jos työtiloille ei ole määritetty Premium-kapasiteettia, niillä on jaettu kapasiteetti.

Kun käytössä on *jaettu kapasiteetti*, työnkulut suoritetaan muiden asiakkaiden kanssa jaetuissa laskennallisissa resursseissa. Jaetussa kapasiteetissa yksittäisille käyttäjille määritetään enemmän rajoituksia laadukkaan käyttökokemuksen takaamiseksi kaikille käyttäjille.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>Kapasiteettitasot
Power BI:ssä on kahdentyyppistä kapasiteettia: jaettu kapasiteetti ja Power BI Premium -kapasiteetti. Katso tästä kapasiteettien väliset erot.

|  | Jaettu kapasiteetti | Power BI Premium -kapasiteetti |
| --- | --- | --- |
| **Päivitystaajuus** |8/päivä |48/päivä |
| **Eristys erillisellä laitteistolla** |![](media/service-premium/not-available.png "Ei käytettävissä") |![](media/service-premium/available.png "Käytettävissä") |
| **Yritysjakelu** ***kaikille käyttäjille*** | | |
| Sovellukset ja jakaminen |![](media/service-premium/not-available.png "Ei käytettävissä") |![](media/service-premium/available.png "Käytettävissä")<sup>1</sup> |
| Upotettu ohjelmointirajapinta ja ohjausobjektit |![](media/service-premium/not-available.png "Ei käytettävissä") |![](media/service-premium/available.png "Käytettävissä")<sup>2</sup> |
| **Power BI -raporttien paikallinen julkaisu** |![](media/service-premium/not-available.png "Ei käytettävissä") |![](media/service-premium/available.png "Käytettävissä") |

*<sup>1</sup> Lisätietoja on artikkelissa [Käyttäjän valmiudet Power BI Pro- ja Power BI Premium](service-free-vs-pro.md) -toiminnon kanssa.*  
*<sup>2</sup> Parannuksia tulossa Power BI Premiumin yleisesti saatavilla olevaan versioon.*

### <a name="premium-capacity"></a>Premium-kapasiteetti
Aloita Power BI Premium -kapasiteetin käyttö määrittämällä työtila kapasiteettiin. Katso lisätietoja siitä, miten työtila määritetään Premium-kapasiteettiin, artikkelista [Power BI Premiumin hallinta](service-admin-premium-manage.md).

Kun työtilaa tukee Premium-kapasiteetti, voit nauttia Power BI Premiumin eduista.

* **Ajoitetut päivitykset**: Kun käytössä on jaettu kapasiteetti, tuotujen mallien ajoitetut päivitykset on rajoitettu 8 kertaan päivässä. Premium-työtilojen tietojoukkojen päivitysten määrää on lisätty 48 kertaan päivässä. Tämä ei koske DirectQueryn Ajoitettu välimuistin päivitys -asetuksia. Ne pysyvät samoina Premium- ja jaetussa kapasiteetissa.
* **Eristys erillisellä laitteistolla**: Jaetussa kapasiteetissa raporttien ja koontinäyttöjen suorituskykyyn voivat vaikuttaa kapasiteetin muiden kuormitusten resurssivaatimukset, vaikka olemmekin varautuneet siihen. Sitä vastoin Premium tarjoaa yhtenäisemmän ja luotettavamman suorituskyvyn kuormituksillesi eristämällä ne liittymättömistä kuormituksista.

Jos sovellusta tukee Premium-kapasiteetti (eli jos se julkaistiin sovellustyötilasta, joka on tällä hetkellä määritetty Premiumiin), julkaistua sovellusta voi käyttää kuka tahansa organisaation käyttäjä hänelle määritetystä käyttöoikeudesta riippumatta.

### <a name="shared-capacity"></a>Jaettu kapasiteetti
Työtilasi on oletusarvoisesti jaetussa kapasiteetissa. Tähän kuuluu *Oma työtila* sekä sovellustyötilat. Jaettu kapasiteetti on se, johon olet tottunut Power BI:ssä ja jossa työnkulut suoritetaan muiden asiakkaiden kanssa jaetuissa laskennallisissa resursseissa.

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Premium-kapasiteetin solmut
Power BI Premium on saatavilla solmumäärityksinä eri näennäisydinkapasiteeteilla. Jos haluat lisätietoja tietyistä varastointiyksikkövaihtoehdoista ja niiden hinnoista, katso [Power BI:n hinnoittelu](https://powerbi.microsoft.com/pricing/). [Kustannuslaskin](https://powerbi.microsoft.com/calculator/) on myös käytettävissä. Jos haluat lisätietoja upotetun analytiikan kapasiteetin suunnittelusta, katso [Power BI:n yrityskäyttöönoton suunnittelemisen tekninen raportti](https://aka.ms/pbienterprisedeploy).

* P-solmuja voi käyttää upotetuissa tai palvelun käyttöönotoissa.
* EM-solmuja voi käyttää vain upotetuissa käyttöönotoissa. EM-solmut eivät tue Premium-ominaisuuksia, kuten sovellusten jakamista käyttäjille, joilla ei ole Power BI Pro -käyttöoikeutta.

>[!NOTE]
>Tämän taulukon linkit toimivat oikein vain käyttäjillä, jotka ovat Office 365:n yleisiä järjestelmänvalvojia. Muut saavat virheilmoituksen 404. 

| Kapasiteetin solmu | V-ytimiä yhteensä<br/>*(Tausta ja edusta)* | Taustan näennäisytimet | Edustan V-ytimet | DirectQueryn/live-yhteyden rajoitukset | Sivun hahmonnuksia enintään huipputuntina | Käytettävyys |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (kuukausittain)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 näennäisydin |0,5 näennäisydintä, 2,5 Gt RAM |0,5 näennäisydintä |3,75 sekunnissa |150–300 |Käytettävissä |
| [EM2 (kuukausittain)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 näennäisydintä |1 näennäisydin, 5 Gt RAM |1 näennäisydin |7,5 sekunnissa |301–600 |Käytettävissä |
| [EM3 (kuukausittain)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 näennäisydintä |2 näennäisydintä, 10 Gt RAM |2 näennäisydintä | |601–1 200 |Käytettävissä |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 näennäisydintä |4 näennäisydintä, 25 Gt RAM |4 näennäisydintä |30 sekunnissa |1 201–2 400 |Käytettävissä ([kuukausittain](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1) on myös käytettävissä) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 näennäisydintä |8 näennäisydintä, 50 Gt RAM |8 näennäisydintä |60 sekunnissa |2 401–4 800 |Käytettävissä |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 näennäisydintä |16 näennäisydintä, 100 Gt RAM |16 näennäisydintä |120 sekunnissa |4 801–9 600 |Käytettävissä |

* Edustan v-ytimet vastaavat verkkopalvelusta, koontinäytön ja raportin tiedostohallinnasta, käyttöoikeuksien hallinnasta, ajoituksista, ohjelmointirajapinnoista, latauksista ja yleisesti ottaen kaikesta, mikä liittyy käyttökokemukseen.
* Taustan v-ytimet vastaavat raskaasta työstä eli kyselyiden käsittelystä, välimuistin hallinnasta, R-palvelinten suorittamisesta, tietojen päivittämisestä, luonnollisen kielen käsittelystä, reaaliaikaisista syötteistä sekä raporttien ja kuvien palvelinpuolen hahmontamisesta. Taustan v-ytimille varataan myös tietty määrä muistia. Riittävä muisti on erityisen tärkeä, kun käsitellään suuria tietomalleja tai useita aktiivisia tietojoukkoja.

## <a name="power-bi-report-server"></a>Power BI -raporttipalvelin
Power BI Premium sisältää paikallisen Power BI -raporttipalvelimen suorittamisoikeuden. Lisätietoja on artikkelissa [Power BI -raporttipalvelimen käytön aloittaminen](report-server/get-started.md).

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI Premiumin usein kysytyt kysymykset](service-premium-faq.md)  
[Power BI Premiumin julkaisutiedot](service-premium-release-notes.md)  
[Ohjeet Power BI Premiumin ostamiseen](service-admin-premium-purchase.md)  
[Power BI Premiumin hallinta](service-admin-premium-manage.md)  
[Microsoft Power BI Premiumin tekninen raportti](https://aka.ms/pbipremiumwhitepaper)  
[Power BI:n yrityskäyttöönoton suunnittelemisen tekninen raportti](https://aka.ms/pbienterprisedeploy)  
[Power BI:n hallinta organisaatiossa](service-admin-administering-power-bi-in-your-organization.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

