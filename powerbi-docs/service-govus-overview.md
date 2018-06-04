---
title: Power BI Yhdysvaltain valtionhallinnon asiakkaille - Yleiskuvaus
description: Lisätietoja Yhdysvaltain valtionhallinnon asiakkaille Power BI US Government-palvelun ominaisuuksista ja rajoituksista
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Get started
ms.openlocfilehash: b3682deb1897647a7de6f32dc87a4d7ed8bc2c9f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "29706910"
---
# <a name="power-bi-for-us-government-customers"></a>Power BI Yhdysvaltain valtionhallinnon asiakkaille
**Power BI-palvelulla** on versio, joka on saatavilla Yhdysvaltain valtionhallinnon asiakkaille osana **Office 365 US Government Community** -tilauksia. Tässä artikkelissa kuvattu **Power BI -palvelun** versio on suunniteltu erityisesti Yhdysvaltain valtionhallinnon asiakkaille ja on erillinen ja erilainen kuin **Power BI -palvelun** kaupallinen versio.

![](media/service-govus-overview/service_usgov_overview-1.png)

Seuraavissa osissa kuvataan *ominaisuuksia*, jotka ovat käytettävissä **Power BI -palvelun** Yhdysvaltain valtionhallinnon versiossa, selkeytetään joitakin *rajoituksia*, luetellaan **usein kysyttyjä kysymyksiä** ja vastauksia (mukaan lukien miten rekisteröidytään) ja annetaan linkkejä lisätietoihin.

## <a name="features-of-power-bi-us-government"></a>Power BI US Governmentin ominaisuudet
On tärkeää huomata, että **Power BI US Government** on saatavilla vain **Pro-käyttöoikeutena** eikä se ole saatavilla maksuttomana käyttöoikeutena. Tietyt Power BI -palvelun ominaisuudet ovat saatavilla palvelun **Power BI US Government** -versiossa.

Seuraavat ominaisuudet ovat saatavilla **Power BI US Government** -asiakkaille, koska ne koskevat **Pro**-käyttöoikeuden toimintoja:

* Koontinäyttöjen ja raporttien luominen ja tarkasteleminen
* [Tietokapasiteetin rajoitukset](service-admin-manage-your-data-storage-in-power-bi.md)
* [Ajoitettu tietojen päivittäminen](refresh-data.md)
* Päivitettävät työryhmän koontinäytöt
* Active Directory -ryhmät jakamista ja käytön hallintaa varten
* [Tuo tietoja](service-get-data.md) ja raportteja Excel-, CSV- ja Power BI Desktop -tiedostoista
* Tiedonhallinnan yhdyskäytävä
* Kaikki tiedot salataan sekä Azure SQL:ssä että Power BI:n Blob-säilössä
* Muodosta yhteys palveluihin [sisältöpaketeilla](service-connect-to-services.md)

## <a name="connectivity-between-government-and-public-azure-cloud-services"></a>Valtionhallinnon ja julkisten Azure Cloud -palveluiden välinen yhteys 

Azure jaetaan useiden pilvien kesken. Vuokraajat voivat oletusarvoisesti avata palomuurisääntöjä pilvikohtaiseen esiintymään, mutta verkkopilvipalvelujen välinen verkko on erilainen ja edellyttää tiettyjen palomuurisääntöjen avaamista palveluiden väliselle viestinnälle. Jos olet Power BI -asiakas ja sinulla on julkisessa pilvessä aiemmin luotuja SQL-esiintymiä, joita sinun tarvitse käyttää, sinun on avattava SQL:ssä tietyt palomuurisäännöt Azure Government Cloud IP -tilaa varten seuraavissa tietokeskuksissa:

* USGov Iowa
* USGov Virginia
* USGov Texas
* USGov Arizona

Julkisessa pilvessä IP-tilat ovat saatavilla, mutta valtionhallinnon pilven osalta sinun on avattava Azure-tukipyyntö, jos haluat pyytää yllä lueteltujen tietokeskusten IP-osoitealueet. 


## <a name="limitations-of-power-bi-us-government"></a>Power BI US Governmentin rajoitukset
Jotkin ominaisuudet, jotka ovat saatavilla **Power BI -palvelun** kaupallisessa versiossa, *eivät* ole saatavilla **Power BI -palvelussa** Yhdysvaltain valtionhallinnon asiakkaille. Power BI -tiimi pyrkii aktiivisesti saamaan nämä ominaisuudet Yhdysvaltain valtionhallinnon asiakkaille ja päivittää tämän artikkelin tiedot, kun nämä ominaisuudet tulevat saataville.

* **Power BI US Government** on saatavilla vain **Pro**-käyttöoikeutena. Hallintaportaalin viittaukset Power BI (maksuton) -käyttöoikeuksiin (tai käyttäjinä) suoritetaan kaupallisessa Power BI -palvelun pilvessä.
* **Valvonta** – valvontaa ei ole saatavilla Office 365:n tietoturva ja yhteensopivuus -portaalin kautta.
* **Power BI -sisältö Cortanassa** – Power BI:n tulokset eivät näy Cortanan hakutuloksissa. Tämä sisältää Power BI -sisällön (koontinäytöt, raportit, sovellukset) tulokset sekä tulokset, jotka näyttävät Cortanalle optimoidut raporttisivujen avainsanat.
* **Ulkoisen käyttäjän jakaminen** – jakaminen on sallittua vain Power BI -vuokralaisessa. Et voi jakaa käyttäjien kanssa Power BI -vuokraajan ulkopuolella.

Jos sinulla on maksuttomia **Power BI** -käyttöoikeuksia määritettynä tilillesi, kyseiset tilit toimivat kaupallisessa**Power BI** -palvelun versiossa, joten ne ovat eivät ole osa **Power BI US Government** -tarjontaa. Voit kohdata seuraavia ongelmia maksuttomissa tileissä:

* Yhdyskäytävä, mobiili ja työpöytä eivät voi todentaa.
* Et voi käyttää Azuren kaupallisia tietolähteitä.
* PBIX-tiedostot on ladattava manuaalisesti kaupallisesta versiosta.
* Power BI -mobiilisovellukset eivät ole käytettävissä.

Ratkaise ongelmia ottamalla yhteyttä tilisi edustajaan.

## <a name="frequently-asked-questions-faq-for-the-us-government-version-of-the-power-bi-service"></a>Power BI-palvelun Yhdysvaltain valtionhallinnon version usein kysytyt kysymykset
Seuraavat kysymykset (ja vastaukset) on toimitettu auttamaan sinua saamaan tarvitsemasi tiedot palvelusta nopeasti.

**Kysymys:** Miten siirrän kaupallisen **Power BI:n** tiedot Yhdysvaltain valtionhallinnon **Power BI -palveluun**?

**Vastaus:** Järjestelmänvalvojan on luotava uusi **Power BI** -esiintymä erillisessä Yhdysvaltain valtionhallinnon tilauksessa. Voit sitten kopioida kaupalliset tiedot Yhdysvaltain valtionhallinnon **Power BI -palvelussa**, poistaa kaupallisen käyttöoikeutesi ja liittää olemassa olevan toimialueen Yhdysvaltain valtionhallinnon palveluun.

**Kysymys:** Miksi en voi yhdistää tiettyyn sisältöpakettiin?

**Vastaus:** Sinun on varmistettava, että tilauksesi on otettu käyttöön, ennen kuin muodostat yhteyden kyseiseen sisältöpakettiin.

**Kysymys:** Olen kiinnostunut hankkimaan **Power BI:n** Yhdysvaltain valtionhallinnon organisaatiolle. Miten voin aloittaa?

**Vastaus:** Rekisteröityminen (eli *perehdytys*) saattaa vaihdella nykyisen käyttöoikeuden ja tilauksen mukaan. Lisätietoja on artikkelissa [Rekisteröidy Yhdysvaltain valtionhallinnon Power BI:hin](service-govus-signup.md).

**Kysymys:** Eroaako **Power BI:n** Yhdysvaltain valtionhallinnolle URL-yhdistämisosoite kaupallisesta **Power BI** -URL-osoitteesta?

**Vastaus:** Kyllä, URL-osoitteet ovat erilaiset. Seuraavassa taulukossa on kukin URL-osoite:

| Kaupallisen version URL-osoite | Yhdysvaltain valtionhallinnon version URL-osoite |
| --- | --- |
| https://app.powerbi.com/ |[https://app.powerbigov.us](https://app.powerbigov.us) |

## <a name="next-steps"></a>Seuraavat vaiheet
Voit tehdä kaikenlaista Power BI:llä. Saat lisätietoja ja kursseja, mukaan lukien artikkelin, jossa näytetään, miten voit rekisteröidy palveluun, tutustumalla seuraaviin resursseihin:

* [Rekisteröidy Yhdysvaltain valtionhallinnon Power BI:hin](service-govus-signup.md)
* <a href="https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government">Yhdysvaltain valtionhallinnon Power BI:n esittelyohjelma</a>
* [Power BI:n ohjattu oppiminen](guided-learning/gettingstarted.yml#step-1)
* [Power BI -palvelun käytön aloittaminen](service-get-started.md)
* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)
