---
title: Paikallisten tietoyhdyskäytävien koko
description: Ohjeita paikallisen tietoyhdyskäytävän koon muuttamiseen.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/30/2019
ms.author: v-pemyer
ms.openlocfilehash: de84dd7e9021abf1198f2dc4f910afb8bd078ac6
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279522"
---
# <a name="on-premises-data-gateway-sizing"></a>Paikallisten tietoyhdyskäytävien koko

Tässä artikkelissa on ohjeita Power BI -järjestelmänvalvojille, joiden on asennettava [paikallinen tietoyhdyskäytävä](../connect-data/service-gateway-onprem.md) ja hallittava sitä.

Yhdyskäytävää tarvitaan, kun Power BI:n on käytettävä tietoja, jotka eivät ole saatavilla suoraan Internetin kautta. Se voidaan asentaa paikalliseen palvelimeen tai näennäiskoneen isännöimään infrastruktuuri palveluna (IaaS) -järjestelmään.

## <a name="gateway-workloads"></a>Yhdyskäytävän kuormitukset

Paikallinen tietoyhdyskäytävä tukee kahdenlaisia kuormituksia. Tutustu ensin tarkemmin näihin kuormituksiin, ennen kuin siirrymme yhdyskäytävän koon muuttamiseen ja suosituksiin.

### <a name="cached-data-workload"></a>Välimuistiin tallennettu tietokuormitus

_Välimuistiin tallennettu tietokuormitus_ noutaa ja muuntaa lähdetiedot Power BI -tietojoukkoihin lataamista varten. Siihen sisältyy kolme vaihetta:

1. **Yhteys**: Yhdyskäytävä muodostaa yhteyden lähdetietoihin.
1. **Tietojen noutaminen ja muuntaminen**: Tiedot noudetaan ja tarvittaessa muunnetaan. Aina kun mahdollista, Power Queryn koostemoduuli siirtää muunnosvaiheet tietolähteeseen. Tämä tunnetaan _[kyselyn delegoimisena lähteeseen](power-query-folding.md)_ . Kun se ei ole mahdollista, yhdyskäytävän on tehtävä muunnokset. Tässä tapauksessa yhdyskäytävä kuluttaa enemmän suoritin- ja muistiresursseja.
1. **Siirto**: Tiedot siirretään Power BI -palveluun, joten luotettava ja nopea Internet-yhteys on tärkeä etenkin suurissa tietomäärissä.

![Kaavio näyttää paikallisen tietoyhdyskäytävän, joka muodostaa yhteyden paikallisiin lähteisiin: relaatiotietokanta, Excel-työkirja ja CSV-tiedostot. Yhdyskäytävä noutaa ja muuntaa tietoja.](media/gateway-onprem-sizing/gateway-onprem-workload-cached-data.png)

### <a name="live-connection-and-directquery-workloads"></a>Reaaliaikainen yhteys- ja DirectQuery-kuormitukset

_Reaaliaikainen yhteys- ja DirectQuery-_ kuormitus toimii useimmiten läpivientitilassa. Power BI -palvelu lähettää kyselyitä, joihin yhdyskäytävä reagoi kyselyn tuloksia lähettämällä. Yleensä kyselyn tulokset ovat pienikokoisia.

- Lisätietoja reaaliaikaisesta yhteydestä on [Tietojoukot Power BI -palvelussa (ulkoisesti isännöidyt mallit)](../connect-data/service-datasets-understand.md#external-hosted-models) -artikkelissa.
- Lisätietoja DirectQuerysta on [Tietojoukkojen tilat Power BI -palvelussa (DirectQuery-tila)](../connect-data/service-dataset-modes-understand.md#directquery-mode) -artikkelissa.

Tämä työmäärä edellyttää suoritinresursseja reitityskyselyille ja kyselyjen tuloksille. Yleensä suoritinresursseille on paljon vähemmän kysyntää kuin välimuistiin tallentamisen tapauksessa, etenkin jos tietoja on muunnettava välimuistiin tallentamista varten.

Luotettava, nopea ja vakaa yhteys on tärkeä, jotta raportin käyttäjien käyttökokemus on miellyttävä.

![Kaavio näyttää paikallisen tietoyhdyskäytävän, joka muodostaa yhteyden paikallisiin lähteisiin: Analysis Servicesin taulukkomuotoinen tietokanta ja relaatiotietokanta. Yhdyskäytävä toimii pääasiassa läpivientitilassa.](media/gateway-onprem-sizing/gateway-onprem-workload-liveconnection-directquery.png)

## <a name="sizing-considerations"></a>Huomioitavaa koon muuttamisesta

Yhdyskäytävätietokoneen oikean koon määrittäminen voi riippua seuraavista muuttujista:

- Välimuistiin tallennettavat kuormitukset:
  - Tietojoukkojen samanaikaisten päivitysten määrä
  - Tietolähteiden tyypit (relaatiotietokanta, analytiikkatietokanta, tietosyötteet tai tiedostot)
  - Tietolähteistä noudettavien tietojen määrä
  - Power Queryn koostemoduulin edellyttämät muunnokset
  - Power BI -palveluun siirrettävien tietojen määrä
- Reaaliaikainen yhteys- ja DirectQuery-kuormitukset:
  - Raporttien käyttäjien samanaikainen määrä
  - Raporttisivujen visualisointien määrä (jokainen visualisointi lähettää vähintään yhden kyselyn)
  - Power BI -koontinäytön kyselyvälimuistin päivitystiheys
  - [Automaattinen sivun päivitys](../create-reports/desktop-automatic-page-refresh.md) -toimintoa käyttävien reaaliaikaisten raporttien määrä
  - Tietojoukkojen pakottaminen käyttämään [rivitason suojausta (RLS)](../create-reports/desktop-rls.md)

Yleensä reaaliaikainen yhteys- ja DirectQuery-kuormitukset edellyttävät kohtuullisia suoritinresursseja, kun taas välimuistiin tallennettavien tietojen kuormitukset vaativat enemmän suoritintehoa ja muistia. Molemmat kuormitukset riippuvat hyvästä yhteydestä Power BI -palveluun ja tietolähteisiin.

> [!NOTE]
> Power BI:n kapasiteetti asettaa rajoituksia mallin päivitysten rinnakkaisuudelle sekä reaaliaikaisen yhteyden ja DirectQueryn siirtomäärälle. Yhdyskäytävien resursseja ei kannata mitoittaa ylisuuriksi Power BI -palvelun tehokkuuteen nähden. Rajoitukset vaihtelevat Premium SKU -yksikön (ja vastaavankokoisen A SKU -yksikön) mukaan. Lisätietoja on ohjeartikkelissa [Mikä Power BI Premium on? (Kapasiteetin solmut)](../admin/service-premium-what-is.md#capacity-nodes).

## <a name="recommendations"></a>Suositukset

Yhdyskäytävän kokosuositukset riippuvat useista muuttujista. Tässä osiossa annamme sinulle yleisiä suosituksia huomioitaviksi.

### <a name="initial-sizing"></a>Ensimmäinen mitoitus

Oikean koon arvioiminen voi olla hankalaa. Suosittelemme, että aloitat tietokoneella, jossa on vähintään kahdeksan suoritinydintä, kahdeksan gigatavua RAM-muistia ja useita gigabitin verkkosovittimia. Voit sitten mitata tyypillisen yhdyskäytävän kuormituksen tutkimalla suoritinten ja muistin käyttölokeja. Lisätietoja on artikkelissa [Paikallisen tietoyhdyskäytävän suorituskyvyn valvonta ja optimointi](/data-integration/gateway/service-gateway-performance).

### <a name="connectivity"></a>Yhteydet

Pyri varmistamaan paras mahdollinen yhteys Power BI -palvelun ja yhdyskäytävän välille sekä yhdyskäytävän ja tietolähteiden välille.

- Aseta tavoitteeksi luotettavuus, nopeus sekä alhainen ja vakaa viive.
- Pyri poistamaan ylimääräiset laitteet yhdyskäytävän ja tietolähteiden välillä tai ainakin vähentämään niiden määrää.
- Poista mahdolliset palomuurin välityspalvelinkerroksen asettamat rajoitukset verkkoliikenteelle. Lisätietoja Power BI:n päätepisteistä saat ohjeartikkelista [Power BI:n URL-osoitteet sallittujen luetteloon](../admin/power-bi-whitelist-urls.md).
- Luo yksityiset ja hallitut yhteydet Power BI:hin määrittämällä [Azure ExpressRoute](/azure/expressroute/expressroute-introduction).
- Jos tietolähteitä on Azure-näennäiskoneissa, varmista, että näennäiskoneet sijaitsevat [Power BI -palvelussa](../admin/service-admin-where-is-my-tenant-located.md).
- Jos käytät reaaliaikaisten yhteyksien kuormituksia SQL Server Analysis Servicesiin (SSAS), joissa hyödynnetään dynaamista rivitason suojausta, varmista hyvä yhteys yhdyskäytävätietokoneen ja paikallisen Active Directoryn välillä.

### <a name="clustering"></a>Klusterointi

Suurissa käyttöönotoissa voit luoda yhdyskäytävän klusteroiduista asennuksista. Klusterien avulla vältät yksittäisiä vikaantumispisteitä ja voit tasata liikenteen kuormitusta yhdyskäytävien välillä. Vaihtoehdot ovat:

- Yhden tai useamman yhdyskäytävän asentaminen klusteriin
- Kuormitusten eristäminen erillisiin yhdyskäytäviin tai yhdyskäytäväpalvelinten klustereihin

Lisätietoja on artikkelissa [Paikallisten tietoyhdyskäytävien suuren käytettävyyden klustereiden ja kuormituksen tasauksen hallitseminen](/data-integration/gateway/service-gateway-high-availability-clusters).

### <a name="dataset-design-and-settings"></a>Tietojoukkojen rakenne ja asetukset

Tietojoukkojen rakenne ja asetukset voivat vaikuttaa yhdyskäytävän kuormituksiin. Jos haluat vähentää yhdyskäytävän kuormitusta, voit kokeilla seuraavia toimia.

Tuotavat tietojoukot:

- Määritä tietojen päivittäminen tapahtumaan harvemmin.
- Ota käyttöön [lisäävä päivitys](../admin/service-premium-incremental-refresh.md), jos haluat pienentää siirrettäväksi määritetyn tiedon määrää.
- Varmista, että [kyselyt delegoidaan lähteeseen](power-query-folding.md) aina mahdollisuuksien mukaan.
- Muunna rakenne DirectQuery- tai [yhdistelmämalliksi](../connect-data/service-dataset-modes-understand.md#composite-mode) varsinkin silloin, kun tietomäärät ovat suuria tai haluat saada tuloksia alhaisella viiveellä.

DirectQuery-tietojoukot:

- Optimoi tietolähteiden, mallien ja raporttien rakenne. Lisätietoja on artikkelissa [Power BI Desktopin DirectQuery-mallin ohjeet](directquery-model-guidance.md).
- [Koosteita](../transform-model/desktop-aggregations.md) luomalla voit tallentaa ylemmän tason tuloksia välimuistiin, jolloin pienennät DirectQuery-pyyntöjen määrää.
- Kasvata [sivun automaattista päivitysväliä](../create-reports/desktop-automatic-page-refresh.md) raportin rakenteessa ja kapasiteettiasetuksissa.
- Rajoita koontinäytön välimuistin päivitystaajuutta etenkin dynaamisen rivitason suojauksen tapauksessa.
- Muunna rakenne tuonti- tai [yhdistelmämalliksi](../connect-data/service-dataset-modes-understand.md#composite-mode), jos tietomäärät ovat pieniä tai ei-muuttuvia.

Reaaliaikaisten yhteyksien tietojoukot:

- Rajoita koontinäytön välimuistin päivitystaajuutta etenkin dynaamisen rivitason suojauksen tapauksessa.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Power BI:n tietoyhdyskäytävän käyttöönotto-ohjeet](../connect-data/service-gateway-deployment-guidance.md)
- [Paikallisen tietoyhdyskäytävän välityspalvelinasetusten määrittäminen](/data-integration/gateway/service-gateway-proxy)
- [Paikallisen tietoyhdyskäytävän suorituskyvyn valvonta ja optimointi](/data-integration/gateway/service-gateway-performance)
- [Yhdyskäytävien vianmääritys – Power BI](../connect-data/service-gateway-onprem-tshoot.md)
- [Paikallisen tietoyhdyskäytävän vianmääritys](/data-integration/gateway/service-gateway-tshoot)
- [Kyselyn lähteeseen delegoinnin tärkeys](power-query-folding.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com)
