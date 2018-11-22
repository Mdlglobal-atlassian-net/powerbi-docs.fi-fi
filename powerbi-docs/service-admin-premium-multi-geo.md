---
title: Power BI Premiumin Multi-Geo-tuki (esikatselu)
description: Ota selvää, miten voit ottaa sisällön tietokeskuksia käyttöön muilla alueilla kuin Power BI -vuokraajan kotialueella.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/20/2018
LocalizationGroup: Premium
ms.openlocfilehash: 91e1880e1a879ee98d65d6ad91b26e534e807040
ms.sourcegitcommit: a13abdb5a6c0c6a397b328ec2d68788ce3afa866
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/21/2018
ms.locfileid: "52268293"
---
# <a name="multi-geo-support-for-power-bi-premium-preview"></a>Power BI Premiumin Multi-Geo-tuki (esikatselu)

Multi-Geo on Power BI Premiumin ominaisuus, joka auttaa monikansallisia asiakkaita huomioimaan organisaation aluekohtaiset, alakohtaiset ja tietojen säilytykseen liittyvät vaatimukset. Ota selvää, miten voit Power BI Premium -asiakkaana ottaa sisällön tietokeskuksia käyttöön muilla alueilla kuin Power BI -vuokraajan kotialueella. Maantieteellinen alue voi sisältää useamman kuin yhden alueen. Esimerkiksi Yhdysvallat on maantieteellinen alue, ja esimerkiksi Yhdysvaltojen läntinen keskiosa sekä Yhdysvaltojen eteläinen keskiosa ovat Yhdysvaltain alueita. Voit halutessasi ottaa sisältöä käyttöön millä tahansa seuraavista alueista:

- Yhdysvallat
- Kanada
- Yhdistynyt kuningaskunta
- Brasilia
- Eurooppa
- Japani
- Intia
- Tyynenmeren Aasia
- Australia

Multi-Geo ei ole käytettävissä Saksan Power BI:ssä, 21Vianetin ylläpitämässä Kiinan Power BI:ssä tai Yhdysvaltain valtionhallinnon Power BI:ssä.

Multi-Geo on nyt käytettävissä myös Power BI Embeddedissä. Lisätietoja on artikkelissa [Multi-Geo-tuki Power BI Embeddedissä (esikatselu)](developer/embedded-multi-geo.md).

## <a name="using-multi-geo"></a>Multi-Geon käyttäminen

Voit ottaa Multi-Geon käyttöön uusille kapasiteeteille valitsemalla avattavasta valikosta muun kuin oletusalueen.  Kukin käytettävissä oleva kapasiteetti näyttää alueen, minne se tällä hetkellä sijoittuu, kuten **Yhdysvaltojen läntinen keskiosa**.

![Kapasiteetin koko: valitse alue. Power BI Multi-Geo](media/service-admin-premium-multi-geo/power-bi-multi-geo-capacity-size.png)

Kun olet luonut kapasiteetin, se säilyy kyseisellä alueella. Kaikkien luotavien työtilojen sisältö tallennetaan tälle alueelle. Voit siirtää työtilojen alueelta toiselle kautta työtilan asetusnäytön avattavan luettelon kautta.

![Muokkaa työtilaa: Valitse käytettävissä oleva kapasiteetti. Power BI Multi-Geo](media/service-admin-premium-multi-geo/power-bi-multi-geo-edit-workspace.png)

Näet tämän viestin vahvistukseksi muutoksesta.

![Muuta varattua työtilaa -vahvistus](media/service-admin-premium-multi-geo/power-bi-multi-geo-change-assigned-workspace-capacity.png)

Sinun ei tarvitse vaihtaa yhdyskäytävän tunnistetietoja siirron aikana tällä hetkellä.  Ne on vaihdettava siirron yhteydessä sen jälkeen, kun ne on tallennettu Premium-kapasiteetin alueelle.

Siirron aikana tietyt toiminnot voivat epäonnistua, kuten uusien tietojoukkojen julkaiseminen tai ajoitettu tietojen päivittäminen.  

Seuraavat kohteet tallennetaan Premium-alueelle, kun Multi-Geo on käytössä:

- Mallit (.ABF-tiedostot) tuomista varten ja DirectQuery-tietojoukot
- Kyselyn välimuisti
- R-kuvat.

Nämä kohteet säilyvät vuokraajan kotialueella:

- Push-tietojoukot
- Excel-työkirjat
- Raporttinäkymän/raporttien metatiedot, kuten ruutujen nimet ja ruutujen kyselyt
- Palveluväylät yhdyskäytävän kyselyitä tai ajoitettuja päivitystöitä varten
- Käyttöoikeudet
- Tietojoukon tunnistetiedot

## <a name="view-capacity-regions"></a>Kapasiteettien alueiden tarkasteleminen

Hallintaportaalissa voit tarkastella Power BI -vuokraajan kaikkia kapasiteetteja ja niiden nykyisiä alueita.

![Näytä Premium-kapasiteetit](media/service-admin-premium-multi-geo/power-bi-multi-geo-premium-capacities.png) 

## <a name="change-the-region-for-existing-content"></a>Olemassa olevan sisällön alueen muuttaminen

Jos haluat muuttaa olemassa olevan sisällön aluetta, sinulla on kaksi vaihtoehtoa.

- Luo toinen kapasiteetti ja siirrä työtilat. Maksuttomat käyttäjät eivät joudu kokemaan käyttökatkoja, kunhan vuokraajalla on käyttämättömiä V-ytimiä.
- Jos toisen kapasiteetin luominen ei ole mahdollista, voit siirtää sisällön tilapäisesti takaisin Premiumin jaettuun kapasiteettiin. Et tarvitse ylimääräisiä V-ytimiä, mutta maksuttomat käyttäjät saattavat kokea joitakin käyttökatkoja.

## <a name="move-content-out-of-multi-geo"></a>Sisällön siirtäminen ulos Multi-Geosta  

Voit ottaa työtiloja ulos Multi-Geo-kapasiteetista jommallakummalla seuraavista tavoista:

- Poista nykyinen kapasiteetti, johon työtila sisältyy.  Tämä siirtää työtilan takaisin jaettuun kapasiteettiin kotialueella.
- Siirrä yksittäisiä työtiloja takaisin kotialueen vuokraajan Premium-kapasiteettiin.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

- Vahvista, että kaikki aloittamasi alueiden väliset siirtymät noudattavat kaikkia yrityksen ja julkishallinnon edellyttämiä vaatimustenmukaisuusehtoja ennen tiedonsiirron aloittamista.
- Etäalueelle tallennettu välimuistissa oleva kysely pysyy alueellaan levossa. Muut siirrettävät tiedot voivat kuitenkin liikkua edestakaisin useiden maantieteellisten alueiden välillä.
- Kun siirrät tietoja alueelta toiselle Multi-Geo-ympäristössä, lähdetiedot saattavat jäädä jopa 30 päivän ajaksi alueelle, jolta ne on siirretty. Tänä aikana loppukäyttäjät eivät pysty käyttämään niitä. Tiedot poistetaan tältä alueelta ja tuhotaan 30 päivän aikana.
- Multi-Geon käyttäminen ei paranna yleistä suorituskykyä. Raporttien ja raporttinäkymien lataamiseen liittyy edelleen metatietopyyntöjä kotialueelle.
- [Tietovuot](service-dataflows-overview.md)-ominaisuutta (esikatselu) ei tällä hetkellä tueta Multi-Geon yhteydessä.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Mikä on Power BI Premium?](service-premium.md)
- [Multi-Geo Power BI Embedded -kapasiteeteille](developer/embedded-multi-geo.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
