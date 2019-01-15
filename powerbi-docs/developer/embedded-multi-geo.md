---
title: Power BI Embeddedin Multi-Geo-tuki (esikatselu)
description: Lue, miten voit ottaa sisältöä käyttöön tietokeskuksissa muilla alueilla kuin Power BI Embeddedin kotialueella.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 08/31/2018
LocalizationGroup: Embedded
ms.openlocfilehash: ab1b0f7ea7dbee13f39fbf47505a00e2ed6d41ea
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280420"
---
# <a name="multi-geo-support-for-power-bi-embedded-preview"></a>Power BI Embeddedin Multi-Geo-tuki (esikatselu)

**Power BI Embeddedin Multi-Geo-tuki (esikatselu)** tarkoittaa, että ISV:t ja organisaatiot, jotka luovat sovelluksia Power BI Embeddedin avulla analyysin upottamiseksi sovelluksiinsa, voivat nyt käyttää tietojaan eri alueilla ympäri maailmaa.

**Power BI Embeddediä** käyttävät asiakkaat voivat nyt määrittää **kapasiteetin** käyttämällä **Multi-Geo**-asetuksia samojen ominaisuuksien ja rajoitusten perusteella kuin joita [Power BI Premium tukee Multi-Geon avulla](../service-admin-premium-Multi-Geo.md).

## <a name="creating-new-power-bi-embedded-capacity-resource-with-multi-geo"></a>Uuden Power BI Embedded -kapasiteettiresurssin luominen Multi-Geon avulla

Sinun on valittava kapasiteettisi sijainti **Luo resurssi** -näytössä. Tähän asti sijainniksi oli rajoitettu vain Power BI -vuokraajan sijainti, joten käytettävissä oli vain yksi sijainti. Multi-Geon avulla voit valita kapasiteettisi käyttöönoton eri alueilla.

![Power BI Embeddedin Multi-Geo-asennus](media/embedded-multi-geo/pbie-multi-geo-setup.png)

Huomaa, että kun avaat avattavan sijaintivalikon, kotialueen vuokraaja on oletusvalinta.
  
![Power BI Embeddedin Multi-Geo-oletussijainti](media/embedded-multi-geo/pbie-multi-geo-default-location.png)

Kun valitset eri sijainnin, viestissä kehotetaan varmistamaan, että olet tietoinen valinnasta.

![Sijainnin muuttaminen](media/embedded-multi-geo/pbie-multi-geo-location-change.png)

## <a name="view-capacity-location"></a>Kapasiteetin sijainnin tarkasteleminen

Voit nähdä kapasiteettien sijainnin helposti siirtymällä Power BI Embeddedin päähallintasivulle Azure-portaalissa.

![Eri sijainneissa olevat kapasiteetit](media/embedded-multi-geo/pbie-multi-geo-location-different.png)

Sijainti on käytettävissä myös powerbi.comin hallintaportaalissa. Valitse hallintaportaalissa Kapasiteettiasetukset ja siirry Power BI Embedded -välilehdelle.

![Hallintaportaalissa tarkasteleminen](media/embedded-multi-geo/pbie-multi-geo-admin-portal.png)

[Lue lisätietoja kapasiteettien luomisesta Power BI Embeddedissä.](azure-pbie-create-capacity.md)

## <a name="manage-existing-capacities-location"></a>Olemassa olevien kapasiteettien sijainnin hallinta

Et voi muuttaa Power BI Embedded -resurssin sijaintia, kun olet luonut uuden kapasiteetin.

Siirrä Power BI -sisältösi eri alueelle toimimalla seuraavasti:

1. [Luo uusi kapasiteetti](azure-pbie-create-capacity.md) eri alueelle.
2. Määritä kaikki työtilat olemassa olevasta kapasiteetista uuteen kapasiteettiin.
3. Poista tai keskeytä vanha kapasiteetti.

On tärkeää huomata, että jos päätät poistaa kapasiteetin määrittämättä sen sisältöä uudelleen, kaikki kyseisen kapasiteetin sisältö siirtyy jaettuun kapasiteettiin, joka on kotialueellasi.

## <a name="api-support-for-multi-geo"></a>Multi-Geon ohjelmointirajapintatuki

Jotta voidaan tukea kapasiteettien hallintaa Multi-Geossa ohjelmointirajapinnan kautta, olemassa oleviin ohjelmointirajapintoihin on tehty joitakin muutoksia:

1. **[Kapasiteettien hakeminen](https://docs.microsoft.com/rest/api/power-bi/capacities/getcapacities)** – Ohjelmointirajapinta palauttaa kapasiteettiluettelon, jota käyttäjä voi käyttää. Vastaus sisältää nyt alue-nimisen lisäominaisuuden, joka määrittää kapasiteetin sijainnin.
2. **[Kapasiteettiin määrittäminen](https://docs.microsoft.com/rest/api/power-bi/capacities)** – Ohjelmointirajapinnan avulla tietty työtila voidaan määrittää kapasiteettiin. Tämä toiminto ei salli työtilojen määrittämistä kotialueesi ulkopuoliseen kapasiteettiin tai työtilojen siirtämistä eri alueilla sijaitsevien kapasiteettien välillä. Jotta käyttäjä voi tehdä tämän toiminnon, hänellä on edelleen oltava järjestelmänvalvojan oikeudet työtilaan ja kohdekapasiteetin järjestelmänvalvonta- tai määritysoikeudet.
3. **[Azure Resource Manager -ohjelmointirajapinta](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities)** – Kaikki Azure Resource Manager -ohjelmointirajapinnan toiminnot, mukaan lukien *luominen* ja *poistaminen*, tukevat Multi-Geoa.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

* Vahvista, että kaikki aloittamasi alueiden väliset siirtymät noudattavat kaikkia yrityksen ja julkishallinnon edellyttämiä vaatimustenmukaisuusehtoja ennen tiedonsiirron aloittamista.

* Etäalueelle tallennettu välimuistissa oleva kysely pysyy alueellaan levossa. Muut siirrettävät tiedot voivat kuitenkin liikkua edestakaisin eri maantieteellisten alueiden välillä.

* Kun siirrät tietoja alueelta toiselle Multi-Geo-ympäristössä, lähdetiedot saattavat jäädä jopa 30 päivän ajaksi alueelle, jolta ne on siirretty. Tänä aikana käyttäjät eivät pysty käyttämään niitä. Tiedot poistetaan tältä alueelta ja tuhotaan 30 päivän aikana.

* Multi-Geon käyttäminen ei paranna yleistä suorituskykyä. Raporttien ja raporttinäkymien lataamiseen liittyy edelleen metatietopyyntöjä kotialueelle.

## <a name="next-steps"></a>Seuraavat vaiheet

Lue lisätietoja Power BI Embedded -kapasiteeteista ja kaikkien kapasiteettien Multi-Geo-asetuksista alla olevista linkeistä.

* [Mikä Power BI Embedded on?](azure-pbie-what-is-power-bi-embedded.md)

* [Power BI Embedded -kapasiteetin luominen](azure-pbie-create-capacity.md)

* [Multi-Geo Power BI Premium -kapasiteeteissa](../service-admin-premium-multi-geo.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)