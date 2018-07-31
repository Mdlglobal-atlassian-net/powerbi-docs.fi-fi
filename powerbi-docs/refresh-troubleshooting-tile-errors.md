---
title: Ruutuvirheiden vianmääritys
description: Yleisiä virheitä voi ilmetä, kun ruutu yrittää päivittyä
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: b5329614ff988fd9863a51cba314671756b70477
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2018
ms.locfileid: "39329565"
---
# <a name="troubleshooting-tile-errors"></a>Ruutuvirheiden vianmääritys
Seuraavassa on yleisiä virheitä, joita voit kohdata ruutujen kohdalla sekä niiden selitykset.

> [!NOTE]
> Jos kohtaat virheen, joka aiheuttaa ongelmia, etkä löydä sitä luettelossa, voit pyytää apua [yhteisösivustolla](http://community.powerbi.com/) tai luoda [tukipalvelupyynnön](https://powerbi.microsoft.com/support/).
> 
> 

## <a name="errors"></a>Virheitä
**Power BI havaitsi odottamattoman virheen mallin lataamisen aikana. Yritä myöhemmin uudelleen.**
tai **Tietomallia ei voitu noutaa. Ota yhteyttä koontinäytön omistajaan ja varmista, että tietolähteet sekä malli ovat olemassa ja että niitä voi käyttää.**

Ei voineet käyttää tietoja, koska tietolähde ei ollut käytettävissä. Näin voi käydä, jos tietolähde on poistettu, nimetty uudelleen, siirretty, offline-tilassa tai oikeudet ovat muuttuneet. Tarkista, että lähde on edelleen osoittamassamme sijainnissa ja sinulla on edelleen oikeudet käyttää sitä. Jos tämä ei ole ongelman ratkaisu, lähde voi olla hidas. Yritä myöhemmin uudelleen aikana, jolloin lähteen kuormitus on pienempi. Jos kyseessä on paikallinen lähde, tietolähteen omistaja voi ehkä antaa enemmän tietoja.

**Sinulla ei ole oikeuksia tarkastella tätä tiedostoa tai avata työkirjaa.**

Ota yhteyttä koontinäytön omistajaan ja varmista, että tietolähteet sekä malli ovat olemassa ja että niitä voi käyttää tililläsi.

**Tietomuotojen on sisällettävä vähintään yksi ryhmä tai laskutoimitus, joka tulostaa tietoja. Ota yhteyttä koontinäytön omistajaan.**

Meillä ei ole mitään näytettäviä tietoja, koska kysely on tyhjä. Yritä lisätä joitakin kenttiä kenttäluettelosta visualisointiin ja kiinnittää se uudelleen.

**Tietoja ei voi näyttää, koska Power BI ei pysty selvittämään suhdetta kahden tai useamman kentän välillä.**

Yrität käyttää kahta tai useampaa kenttää taulukoista, jotka eivät ole yhteydessä toisiinsa. Sinun pitää poistaa asiaan kuulumattomat kentät visualisoinnista ja tämän jälkeen luoda yhteys taulukoiden välille. Kun olet tehnyt tämän, voit lisätä kentät takaisin visualisointiin. Tämä onnistuu Power BI Desktopissa tai Power Pivot for Excelissä. [Lue lisää](desktop-create-and-manage-relationships.md)

**Ensisijaisen akselin ja toissijaisen akselin ryhmien päällekkäisyys. Ensisijaisen akselin ryhmillä ei voi olla samoja avaimia kuin ryhmillä toissijaisella akselilla.**

Tämä on tavallisesti tilapäinen ongelma. Tämä tapahtuu yleensä, kun siirrät ryhmiä riveiltä sarakkeisiin. Tässä tapauksessa virheen pitäisi kadota näkyvistä, kun olet siirtänyt kaikki ryhmät. Jos näet viestin, kokeile vaihtaa kentät rivien ja sarakkeiden välillä tai akselin selitettä  tai kenttien poistamista visualisoinnista.  

**Visualisointi on ylittänyt käytettävissä olevat resurssit. Kokeile suodatusta näytettävän tietomäärän pienentämiseksi.**

Visualisoinnin on yrittänyt kysellä liikaa tietoja meille tulosta varten käyttämällä käytettävissä olevia resursseja. Kokeile visualisoinnin suodatusta tuloksen tietomäärän vähentämiseksi.

**Emme pysty tunnistamaan seuraavia kenttiä: {0}. Päivitä visualisointi kentillä, jotka ovat olemassa tietojoukossa.**

Kenttä on todennäköisesti poistettu tai nimetty uudelleen. Voit poistaa viallisten kentän visualisoinnista, lisätä eri kentän ja kiinnittää sen uudelleen.

**Tietoja ei voitu hakea tälle visualisoinnille. Yritä myöhemmin uudelleen.**

Tämä on tavallisesti tilapäinen ongelma. Jos yritä myöhemmin uudelleen ja näet tämän viestin edelleen, ota yhteyttä tukeen.

## <a name="contact-support"></a>Ota yhteyttä tukeen
Jos sinulla on edelleen ongelma, [Ota yhteyttä tukeen](https://support.powerbi.com) asian tutkimiseksi tarkemmin.

## <a name="next-steps"></a>Seuraavat vaiheet
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
[Vianmääritys, Power BI Personal Gateway](service-admin-troubleshooting-power-bi-personal-gateway.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

