---
title: Ruutuvirheiden vianmääritys
description: Yleisiä virheitä voi ilmetä, kun ruutu yrittää päivittyä Power BI:ssä
author: maggiesMSFT
ms.reviewer: kayu
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 12/06/2018
ms.author: maggies
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 04ee1386547ed888531ea139227969d49629863d
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74699540"
---
# <a name="troubleshooting-tile-errors"></a>Ruutuvirheiden vianmääritys
Seuraavassa on yleisiä virheitä, joita voit kohdata ruutujen kohdalla sekä niiden selitykset.

> [!NOTE]
> Jos kohtaat virheen, joka aiheuttaa ongelmia, etkä löydä sitä luettelossa, voit pyytää apua [yhteisösivustolla](https://community.powerbi.com/) tai luoda [tukipalvelupyynnön](https://powerbi.microsoft.com/support/).
> 
> 

## <a name="errors"></a>Virheitä
**Power BI havaitsi odottamattoman virheen mallin lataamisen aikana. Yritä myöhemmin uudelleen.**
tai **Tietomallia ei voitu noutaa. Ota yhteyttä koontinäytön omistajaan ja varmista, että tietolähteet sekä malli ovat olemassa ja että niitä voi käyttää.**

Ei voineet käyttää tietoja, koska tietolähde ei ollut käytettävissä. Tämä ongelma voi ilmetä, jos tietolähde on poistettu, sen nimi on vaihdettu, se on siirretty toiseen paikkaan, se on offline-tilassa tai sen käyttöoikeudet ovat muuttuneet. Tarkista, että lähde on edelleen osoittamassamme sijainnissa ja sinulla on edelleen oikeudet käyttää sitä. Jos tämä ei ole ongelman ratkaisu, lähde voi olla hidas. Yritä myöhemmin uudelleen aikana, jolloin lähteen kuormitus on pienempi. Jos kyseessä on paikallinen lähde, tietolähteen omistaja voi ehkä antaa enemmän tietoja.

**Sinulla ei ole oikeuksia tarkastella tätä tiedostoa tai avata työkirjaa.**

Ota yhteyttä koontinäytön omistajaan ja varmista, että tietolähteet ja malli ovat olemassa ja että niitä voi käyttää tililläsi.

**Järjestelmänvalvojasi on poistanut mukautetut visualisoinnit käytöstä.**

Power BI-järjestelmänvalvojasi on poistanut käytöstä organisaatiosi tai suojausryhmäsi mukautetut visualisoinnit. Et voi käyttää [Microsoft Marketplace](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)n mukautettuja visualisointeja etkä tuoda omia visualisointeja tiedostosta. Voi käyttää vain valmiiksi pakattua joukkoa visualisointeja.


**Tietomuotojen on sisällettävä vähintään yksi ryhmä tai laskutoimitus, joka tulostaa tietoja. Ota yhteyttä koontinäytön omistajaan.**

Meillä ei ole mitään näytettäviä tietoja, koska kysely on tyhjä. Yritä lisätä joitakin kenttiä kenttäluettelosta visualisointiin ja kiinnittää se uudelleen.

**Tietoja ei voi näyttää, koska Power BI ei pysty selvittämään suhdetta kahden tai useamman kentän välillä.**

Yrität käyttää kahta tai useampaa kenttää taulukoista, jotka eivät ole yhteydessä toisiinsa. Sinun pitää poistaa asiaan kuulumattomat kentät visualisoinnista ja tämän jälkeen luoda yhteys taulukoiden välille. Kun olet tehnyt tämän muutoksen, voit lisätä kentät takaisin visualisointiin. Tämä onnistuu Power BI Desktopissa tai Power Pivot for Excelissä. [Lue lisää](desktop-create-and-manage-relationships.md)

**Ensisijaisen akselin ja toissijaisen akselin ryhmien päällekkäisyys. Ensisijaisen akselin ryhmillä ei voi olla samoja avaimia kuin ryhmillä toissijaisella akselilla.**

Se on tavallisesti tilapäinen ongelma. Tämä tapahtuu yleensä, kun siirrät ryhmiä riveiltä sarakkeisiin. Tässä tapauksessa virheen pitäisi kadota näkyvistä, kun olet siirtänyt kaikki ryhmät. Jos näet viestin, kokeile vaihtaa kentät rivien ja sarakkeiden välillä tai akselin selitettä  tai kenttien poistamista visualisoinnista.  

**Visualisointi on ylittänyt käytettävissä olevat resurssit. Kokeile suodatusta näytettävän tietomäärän pienentämiseksi.**

Visualisoinnin on yrittänyt kysellä liikaa tietoja meille tulosta varten käyttämällä käytettävissä olevia resursseja. Kokeile visualisoinnin suodatusta tuloksen tietomäärän vähentämiseksi.

**Emme pysty tunnistamaan seuraavia kenttiä: {0}. Päivitä visualisointi kentillä, jotka ovat olemassa tietojoukossa.**

Kenttä on todennäköisesti poistettu tai nimetty uudelleen. Voit poistaa viallisten kentän visualisoinnista, lisätä eri kentän ja kiinnittää sen uudelleen.

**Tietoja ei voitu hakea tälle visualisoinnille. Yritä myöhemmin uudelleen.**

Tämä on tavallisesti tilapäinen ongelma. Jos yrität myöhemmin uudelleen ja näet tämän viestin edelleen, ota yhteyttä tukeen.

**Ruudut näyttävät edelleen suodattamattomia tietoja, kun kertakirjautuminen on otettu käyttöön.**

Näin voi käydä, jos taustalla oleva tietojoukko on määritetty käyttämään DirectQuery-tilaa tai reaaliaikaista yhteyttä Analysis Servicesiin paikallisen tietoyhdyskäytävän kautta. Tässä tapauksessa ruudut näyttävät edelleen suodattamattomia tietoja, kun kertakirjautuminen on otettu käyttöön. Niitä näytetään siihen saakka, kunnes ruutu päivitetään seuraavan kerran. Tämän jälkeen Power BI käyttää kertakirjautumista määritetyllä tavalla ja ruuduissa näytetään käyttäjätietojen perusteella suodatettuja tietoja. 

Jos haluat nähdä suodatetut tiedot heti, voit pakottaa ruudun päivityksen valitsemalla **Enemmän vaihtoehtoja** (...) raporttinäkymän oikeasta yläkulmasta ja valitsemalla **Päivitä raporttinäkymän ruudut**.

Tietojoukon omistajana voit myös muokata ruudun päivitysväliä. Jos haluat nopeuttaa ruudun päivitystä, määritä päivitysväliksi 15 minuuttia. Valitse rataskuvake Power BI -palvelun oikeassa yläkulmassa ja valitse sitten **Asetukset**. Valitse **Asetukset**-sivulla **Tietojoukot**-välilehti. Laajenna **Ajoitettu välimuistin päivitys** -kohta ja muokkaa **Päivitystaajuus**-kohdan arvoa. Varmista, että muokkaat määrityksiin takaisin alkuperäisen päivitysvälin, kun Power BI suorittaa seuraavan ruutupäivityksen.

> [!NOTE]
> **Ajoitettu välimuistin päivitys** -osio on saatavilla tietojoukoille vain DirectQuery-tilassa tai reaaliaikaisen yhteyden tilassa. Tuontitilan tietojoukot eivät edellytä erillistä ruudun päivitystä, koska ruudut päivitetään automaattisesti seuraavan ajoitetun tietojen päivittämisen yhteydessä.

## <a name="contact-support"></a>Ota yhteyttä tukeen
Jos sinulla on edelleen ongelma, [ota yhteyttä tukeen](https://support.powerbi.com) asian tutkimiseksi tarkemmin.

## <a name="next-steps"></a>Seuraavat vaiheet
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
[Vianmääritys, Power BI Personal Gateway](service-admin-troubleshooting-power-bi-personal-gateway.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

