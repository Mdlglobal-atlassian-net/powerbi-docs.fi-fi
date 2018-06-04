---
title: Power BI Desktopin hankkiminen
description: Power BI Desktopin lataaminen ja asentaminen
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: monitoring
qualitydate: 08/15/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Get started
ms.openlocfilehash: a03e859e769f880b0c627080a864b41e96fc138b
ms.sourcegitcommit: 8132f7edc6879eda824c900ba90b29cb6b8e3b21
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/03/2018
---
# <a name="get-power-bi-desktop"></a>Power BI Desktopin hankkiminen
**Power BI Desktopilla** voit luoda tarkempia kyselyjä, malleja ja raportteja, jotka visualisoivat tietoja. **Power BI Desktopilla** voit luoda tietomalleja ja raportteja sekä jakaa töitäsi julkaisemalla niitä Power BI -palvelussa.  **Power BI Desktop** on ladattavissa maksutta.

Voit hankkia **Power BI Desktopin** kahdella tavalla, jotka kuvataan seuraavissa osioissa:

* Voit **ladata** sen suoraan MSI-pakettina, jonka asennat tietokoneeseesi.
* Voit asentaa sen sovelluksena **Microsoft Storesta**.

Molemmilla tavoilla saat uusimman **Power BI Desktop** -version tietokoneeseesi, mutta tavoilla on muutamia eroja, jotka on syytä huomioida ja jotka kuvataan seuraavissa osioissa.

## <a name="download-power-bi-desktop"></a>Power BI Desktopin lataaminen
Jos haluat ladata **Power BI Desktopin** uusimman version, valitse latauskuvake Power BI -palvelun oikeasta yläkulmasta ja valitse sitten **Power BI Desktop**.

![](media/desktop-get-the-desktop/getpbid_downloads.png)

Voit ladata Power BI Desktopin uusimman version myös seuraavalta lataussivulta:

* [**Power BI Desktopin lataus** (sekä 32- että 64-bittiset versiot)](https://powerbi.microsoft.com/desktop).
  
  [![](media/service-admin-power-bi-security/PBI_Security_01.png)](https://powerbi.microsoft.com/desktop)

Riippumatta siitä, kummalla tavalla lataat, sinua kehotetaan suorittamaan asennustiedosto, kun **Power BI Desktop** on ladattu tietokoneeseesi.

![](media/desktop-get-the-desktop/getpbid_3.png)

**Power BI Desktop** asennetaan sovelluksena, jonka voit suorittaa työpöydältäsi.

![](media/desktop-get-the-desktop/designer_gsg_install.png)

> [!NOTE]
> **Power BI Desktopin** ladattavan MSI-version ja **Microsoft Store** -version asentamista samaan tietokoneeseen tueta. (Tätä kutsutaan joskus *rinnakkaisasennukseksi*.)
> 
> 

## <a name="install-as-an-app-from-the-microsoft-store"></a>Sovelluksen asentaminen Microsoft Storesta
Voit hankkia **Power BI Desktopin** myös Microsoft Storesta seuraavan linkin avulla:

* [asenna **Power BI Desktop** **Microsoft Storesta**](http://aka.ms/pbidesktopstore).

![](media/desktop-get-the-desktop/getpbid_04.png)

**Power BI Desktopin** Microsoft Storesta hankkimisella on muutamia etuja:

* **Automaattiset päivitykset**: Windows lataa uusimman version automaattisesti taustalla heti, kun uusi versio on saatavilla, joten sovellus pysyy aina ajan tasalla.
* **Pienemmät lataukset**: **Microsoft Store** varmistaa, että koneeseesi ladataan vain ne komponentit, jotka ovat muuttuneet kussakin päivityksessä. Tämä pienentää kunkin päivityksen latauskokoa.
* **Järjestelmänvalvojaoikeuksia ei tarvita**: MSI-tiedoston lataamiseen ja asentamiseen tarvitaan järjestelmänvalvojaoikeudet, jotta asennus onnistuu. Kun hankit **Power BI Desktopin** Microsoft Storesta, järjestelmänvalvojaoikeuksia *ei* tarvita.
* **Helpompi käyttöönotto**: **Microsoft Store** -version *käyttöönotto* on helpompaa kaikille organisaation käyttäjille. Lisäksi IT-osasto voi tarjota **Power BI Desktopin** **Microsoft Store for Businessissa**.
* **Kielen tunnistaminen**: **Microsoft Store** -versio sisältää kaikki tuetut kielet. Lisäksi se tarkistaa tietokoneessasi käytetyn kielen aina, kun sovellus käynnistetään. Tämä vaikuttaa myös **Power BI Desktopissa** luotuihin lokalisointimalleihin. Esimerkiksi sisäiset päivämäärähierarkiat vastaavat kieltä, jolla **Power BI Desktopia** käytettiin, kun .pbix-tiedosto luotiin.

**Power BI Desktopin** asentamisella Microsoft Storesta on muutamia huomioitavia seikkoja ja rajoituksia. Näitä ovat esimerkiksi seuraavat:

* Jos käytät SAP-yhdistintä, sinun täytyy ehkä siirtää SAP-ohjaintiedostot *Windows\System32*-kansioon.
* Kun asennat **Power BI Desktopin** Microsoft Storesta, käyttäjäasetuksia ei kopioida MSI-versiosta. Sinun täytyy ehkä yhdistää uudelleen viimeisimmät tietolähteet ja antaa tietolähteiden tunnistetiedot uudelleen. 

> [!NOTE]
> **Power BI Desktopin** ladattavan MSI-version ja **Microsoft Store** -version asentamista samaan tietokoneeseen tueta. (Tätä kutsutaan joskus *rinnakkaisasennukseksi*.) Poista **Power BI Desktopin** asennus manuaalisesti, ennen kuin lataat sen **Microsoft Storesta**.
> 
> [!NOTE]
> **Power BI Desktopin** Power BI -raporttipalvelinversio on erillinen. Se on erillinen asennus verrattuna muihin tässä artikkelissa käsiteltyihin versioihin. Jos haluat lisätietoja **Power BI Desktopin** Raporttipalvelin-versiosta, lue ohjeartikkeli [Pikaopas: Power BI -raportin luominen Power BI -raporttipalvelimelle](report-server/quickstart-create-powerbi-report.md).
> 
> 

## <a name="using-power-bi-desktop"></a>Power BI Desktopin käyttäminen
Kun käynnistät **Power BI Desktopin**, näyttöön avautuu *Tervetuloa*-näyttö.

![](media/desktop-get-the-desktop/getpbid_05.png)

Jos käytät **Power BI Desktopia** ensimmäistä kertaa (jos asennus ei siis ole päivitys), sinua pyydetään täyttämään lomake ja vastaamaan muutamaan kysymykseen tai kirjautumaan **Power BI -palveluun**, ennen kuin voit jatkaa.

Tämän jälkeen voit aloittaa tietomallien ja raporttien luomisen sekä niiden jakamisen muiden kanssa Power BI -palvelussa. Tämän artikkelin lopussa olevista **Lisätietoja**-linkeistä löydät oppaita, joista voi olla apua aloittaessasi **Power BI Desktopin** käyttöä.

## <a name="minimum-requirements"></a>Vähimmäisvaatimukset
Alla on lueteltu **Power BI Desktopin** käytön vähimmäisvaatimukset:

* Tarvitset Windows 7:n tai Windows Server 2008 R2:n tai tätä uudemman käyttöjärjestelmän.
* Tarvitset .NET 4.5:n.
* Tarvitset Internet Explorer 9:n tai tätä uudemman selaimen.
* **RAM-muisti:** vapaata muistia täytyy olla vähintään 1 Gt, suositus on kuitenkin 1,5 Gt.
* **Näyttö:** näytön tarkkuuden täytyy olla vähintään 1 440 x 900, suositus on 1 600 x 900 (16:9). Pienempiä näyttötarkkuuksia (esimerkiksi 1 024 x 768 tai 1 280 x 800) ei suositella, koska jotkin ohjausobjektit (esimerkiksi aloitusnäytön sulkemistoiminto) eivät näy kunnolla niillä.
* **Windowsin näyttöasetukset**: Jos näyttöasetuksesi on määritetty siten, että tekstin, sovellusten tai muiden kohteiden koko on yli 100 %, et ehkä näe joitain valintaikkunoita, jotka täytyy sulkea tai joihin sinun täytyy reagoida, jotta voit jatkaa **Power BI Desktopin** käyttöä. Jos törmäät tähän ongelmaan, tarkista Windowsin **näyttöasetukset** valitsemalla **Asetukset > Järjestelmä > Näyttö** ja palauta näyttökoon asetus sataan prosenttiin liukusäätimellä.
* **Suoritin:** suosittelemme vähintään yhden gigahertsin (GHz) x86-suoritinta tai x64-bittistä suoritinta tai tätä nopeampaa suoritinta.

## <a name="next-steps"></a>Seuraavat vaiheet
Kun olet asentanut **Power BI Desktopin**, seuraavan sisällön avulla voit aloittaa sen käytön nopeasti:

* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)
* [Power BI Desktopin kyselyiden yleiskatsaus](desktop-query-overview.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietoihin yhdistäminen Power BI Desktopissa](desktop-connect-to-data.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](desktop-common-query-tasks.md)   
