---
title: Multi-Geo-tuki Power BI Premiumissa (esikatselu)
description: Ota selvää, miten voit ottaa sisällön tietokeskuksia käyttöön muilla alueilla kuin Power BI -vuokraajan kotialueella.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 07/18/2018
ms.author: maggies
LocalizationGroup: Premium
ms.openlocfilehash: b7e1222e5babf1226722c5bd1f5efe3dff4dc8c1
ms.sourcegitcommit: 6faeb642721ee5abb41c04a8b729880c01c4d40e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2018
ms.locfileid: "39210902"
---
# <a name="multi-geo-support-in-power-bi-premium-preview"></a>Multi-Geo-tuki Power BI Premiumissa (esikatselu)
Multi-Geo on Power BI Premiumin ominaisuus, joka auttaa monikansallisia asiakkaita huomioimaan organisaation aluekohtaiset, alakohtaiset ja tietojen säilytykseen liittyvät vaatimukset. Ota selvää, miten voit Power BI Premium -asiakkaana ottaa sisällön tietokeskuksia käyttöön muilla alueilla kuin Power BI -vuokraajan kotialueella. Voit halutessasi ottaa sisältöä käyttöön millä tahansa seuraavista alueista:

- Yhdysvallat 
- Kanada 
- Yhdistynyt kuningaskunta 
- Brasilia 
- Eurooppa 
- Japani 
- Intia 
- Tyynenmeren Aasia 
- Australia 

Maantieteellinen alue voi sisältää useamman kuin yhden alueen. Esimerkiksi Yhdysvallat on maantieteellinen alue, ja esimerkiksi Yhdysvaltojen läntinen keskiosa sekä Yhdysvaltojen eteläinen keskiosa ovat Yhdysvaltain alueita. 

Multi-Geo ei ole käytettävissä Saksan Power BI:ssä, 21Vianetin ylläpitämässä Kiinan Power BI:ssä tai Yhdysvaltain valtionhallinnon Power BI:ssä.

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

Vahvista, että kaikki aloittamasi alueiden väliset siirtymät noudattavat kaikkia yrityksen ja julkishallinnon edellyttämiä vaatimustenmukaisuusehtoja ennen tiedonsiirron aloittamista.

Etäalueelle tallennettu välimuistissa oleva kysely pysyy alueellaan levossa. Muut siirrettävät tiedot voivat kuitenkin liikkua edestakaisin useiden maantieteellisten alueiden välillä. 

Kun siirrät tietoja alueelta toiselle Multi-Geo-ympäristössä, lähdetiedot saattavat jäädä jopa 30 päivän ajaksi alueelle, jolta ne on siirretty. Tänä aikana loppukäyttäjät eivät pysty käyttämään niitä. Tiedot poistetaan tältä alueelta ja tuhotaan 30 päivän aikana.

Multi-Geon käyttäminen ei paranna yleistä suorituskykyä. Raporttien ja raporttinäkymien lataamiseen liittyy edelleen metatietopyyntöjä kotialueelle.

## <a name="next-steps"></a>Seuraavat vaiheet

[Mikä on Power BI Premium?](service-premium.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
