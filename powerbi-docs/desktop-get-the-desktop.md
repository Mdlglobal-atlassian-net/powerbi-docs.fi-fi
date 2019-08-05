---
title: Power BI Desktopin hankkiminen
description: Power BI Desktopin lataaminen ja asentaminen
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/26/2019
ms.author: davidi
LocalizationGroup: Get started
ms.openlocfilehash: 9fa79bc17e87863d094afbc479d664c8bbf9daaf
ms.sourcegitcommit: 0332efe8f83cb55a9b8ea011db7c99e9b4568118
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2019
ms.locfileid: "68590484"
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
* **Järjestelmänvalvojan oikeuksia ei tarvita**: kun lataat  MSI:n suoraan ja asennat sen, sinun on oltava järjestelmänvalvoja, jotta asennus voidaan suorittaa. Kun hankit **Power BI Desktopin** Microsoft Storesta, järjestelmänvalvojan oikeuksia *ei* tarvita.
* **Helpompi käyttöönotto**: **Microsoft Store** -version *käyttöönotto* on helpompaa kaikille organisaation käyttäjille. Lisäksi IT-osasto voi tarjota **Power BI Desktopin** **Microsoft Store for Businessissa**.
* **Kielen tunnistaminen**: **Microsoft Store** -versio sisältää kaikki tuetut kielet. Lisäksi se tarkistaa tietokoneessasi käytetyn kielen aina, kun sovellus käynnistetään. Tämä vaikuttaa myös **Power BI Desktopissa** luotuihin lokalisointimalleihin. Esimerkiksi sisäiset päivämäärähierarkiat vastaavat kieltä, jolla **Power BI Desktopia** käytettiin, kun .pbix-tiedosto luotiin.

**Power BI Desktopin** asentamisella Microsoft Storesta on muutamia huomioitavia seikkoja ja rajoituksia. Näitä ovat esimerkiksi seuraavat:

* Jos käytät SAP-yhdistintä, sinun täytyy ehkä siirtää SAP-ohjaintiedostot *Windows\System32*-kansioon.
* Kun asennat **Power BI Desktopin** Microsoft Storesta, käyttäjäasetuksia ei kopioida MSI-versiosta. Sinun täytyy ehkä yhdistää uudelleen viimeisimmät tietolähteet ja antaa tietolähteiden tunnistetiedot uudelleen. 

> [!NOTE]
> **Power BI Desktopin** ladattavan MSI-version ja **Microsoft Store** -version asentamista samaan tietokoneeseen tueta. (Tätä kutsutaan joskus *rinnakkaisasennukseksi*.) Poista **Power BI Desktopin** asennus manuaalisesti, ennen kuin lataat sen **Microsoft Storesta**.
> 
> [!NOTE]
> **Power BI Desktopin** Power BI -raporttipalvelinversio on erillinen. Se on erillinen asennus verrattuna muihin tässä artikkelissa käsiteltyihin versioihin. Jos haluat lisätietoja **Power BI Desktopin** raporttipalvelimen versiosta, katso artikkeli [Power BI -raportin luominen Power BI -raporttipalvelimelle](report-server/quickstart-create-powerbi-report.md).
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
* Tarvitset Internet Explorer 10:n tai tätä uudemman selaimen.
* **Muisti (RAM):** vapaata muistia täytyy olla vähintään 1 Gt, suositus on kuitenkin vähintään 1,5 Gt.
* **Näyttö:** näytön tarkkuuden täytyy olla vähintään 1 440 x 900, suositus on 1 600 x 900 (16:9). Pienempiä näyttötarkkuuksia (esimerkiksi 1 024 x 768 tai 1 280 x 800) ei suositella, koska jotkin ohjausobjektit (esimerkiksi aloitusnäytön sulkemistoiminto) eivät näy kunnolla niillä.
* **Windowsin näyttöasetukset:** Jos näyttöasetuksesi on määritetty siten, että tekstin, sovellusten tai muiden kohteiden koko on yli 100 %, et ehkä näe joitain valintaikkunoita, jotka täytyy sulkea tai joihin sinun täytyy reagoida, jotta voit jatkaa **Power BI Desktopin** käyttöä. Jos törmäät tähän ongelmaan, tarkista Windowsin **näyttöasetukset** valitsemalla **Asetukset > Järjestelmä > Näyttö** ja palauta näyttökoon asetus sataan prosenttiin liukusäätimellä.
* **Suoritin:** suosittelemme vähintään yhden gigahertsin (GHz) x86- tai x64-bittistä suoritinta tai tätä nopeampaa suoritinta.

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

Tavoitteena on, että Power BI Desktopin käyttökokemuksesi on aina hyvä. Saatat joskus kohdata ongelman Power BI Desktopissa, joten tässä osiossa on ratkaisuja tai ehdotuksia mahdollisten ongelmien selvittämiseksi. 

### <a name="issues-when-using-previous-releases-of-power-bi-desktop"></a>Ongelmia Power BI Desktopin aiempia versioita käytettäessä

Jotkin käyttäjät ovat kohdanneet seuraavanlaisen virheen käyttäessään vanhentunutta versiota **Power BI Desktopista**: 

    "We weren't able to restore the saved database to the model" 

Power BI Desktopin päivitys nykyisen versioon ratkaisee yleensä ongelman.

### <a name="disabling-notifications"></a>Ilmoitusten poistaminen käytöstä
Suosittelemme päivittämään Power BI Desktopin uusimpaan versioon ominaisuuksiin, suorituskykyyn ja vakauteen tehtyjen parannusten ja muiden parannusten hyödyntämiseksi. Jotkin organisaatiot ei ehkä halua käyttäjien päivittävän jokaiseen uuteen versioon. Voit poistaa ilmoitukset käytöstä muokkaamalla rekisteriä seuraavien ohjeiden mukaisesti:

1. Siirry Rekisterieditoria käyttämällä kohtaan *HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft Power BI Desktop*
2. Luo uusi merkintä seuraavilla asetuksilla: *REG_DWORD : DisableUpdateNotification*
3. Määritä uuden merkinnän arvoksi **1**.

Tietokone on käynnistettävä uudelleen, jotta muutos tulee voimaan.

### <a name="power-bi-desktop-loads-with-a-partial-screen"></a>Power BI Desktopista latautuu osittainen näyttö

Joissakin tilanteissa, kuten tiettyjen näytön tarkkuusmääritysten yhteydessä, Power BI Desktop saattaa hahmontaa sisältöä joillekin käyttäjille siten, että siinä näkyy laajoja mustia alueita. Tämä johtuu yleensä viimeaikaisista käyttöjärjestelmän päivityksistä, jotka vaikuttavat kohteiden esitystapaan, sen sijaan, että kyseessä olisi Power BI Desktopin sisällön esitystavan suora tulos. Siitä huolimatta laajat mustat alueet eivät ole yhtä houkuttelevia kuin hyvät visualisoinnit, joten voit ratkaista ongelman seuraavasti:

1. Paina aloitusnäppäintä ja kirjoita sana *sumea* hakupalkkiin, joka tulee näkyviin.
2. Valitse avautuvassa valintaikkunassa seuraava vaihtoehto: *Anna Windowsin korjata sumeat sovellukset.*
3. Käynnistä Power BI Desktop uudelleen.

Tämä ongelma saattaa ratketa seuraavien Windowsin päivitysten julkaisun yhteydessä. 
 

## <a name="next-steps"></a>Seuraavat vaiheet
Kun olet asentanut **Power BI Desktopin**, seuraavan sisällön avulla voit aloittaa sen käytön nopeasti:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin kyselyiden yleiskatsaus](desktop-query-overview.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietoihin yhdistäminen Power BI Desktopissa](desktop-connect-to-data.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](desktop-common-query-tasks.md)   

