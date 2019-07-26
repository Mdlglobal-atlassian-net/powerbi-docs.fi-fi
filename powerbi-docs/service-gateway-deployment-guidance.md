---
title: Power BI:n tietoyhdyskäytävän käyttöönotto-ohjeet
description: Opi parhaat käytännöt ja huomioon otettavia seikkoja Power BI:n tietoyhdyskäytävän käyttöönotosta.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 4351804330982b32582c4c782ef7c2fa0e92f197
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271712"
---
# <a name="guidance-for-deploying-a-data-gateway-for-power-bi"></a>Power BI:n tietoyhdyskäytävän käyttöönotto-ohjeet

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Tämä artikkeli sisältää ohjeita ja huomioon otettavia seikkoja, kun Power BI:n tietoyhdyskäytävä otetaan käyttöön verkko-ympäristössä.

Lisätietoja paikallisen tietoyhdyskäytävän lataamisesta, asentamisesta, määrittämisestä ja hallinnasta on artikkelissa [Mikä paikallinen tietoyhdyskäytävä on](/data-integration/gateway/service-gateway-onprem). Saat lisätietoja paikallisesta tietoyhdyskäytävästä ja Power BI:stä käymällä [Microsoft Power -blogissa](https://powerbi.microsoft.com/blog/) ja [Microsoft Power BI -yhteisön](https://community.powerbi.com/) sivustossa.

## <a name="installation-considerations-for-the-on-premises-data-gateway"></a>Paikallisen tietoyhdyskäytävän asennuksessa huomioitavat seikat

Ennen kuin asennat paikallisen tietoyhdyskäytävän Power BI -pilvipalvelullesi, sinun kannattaa pitää mielessä muutamia seikkoja. Nämä seikat kuvataan seuraavissa osissa.

### <a name="number-of-users"></a>Käyttäjien määrä

Yhdyskäytävää käyttävän raportin käyttäjien lukumäärä on tärkeä mittari pohdittaessa yhdyskäytävän asennuspaikkaa. Seuraavassa on muutamia huomioitavia kysymyksiä:

* Käyttävätkö käyttäjät näitä raportteja päivän eri aikoina?
* Mitä yhteystyyppejä he käyttävät (DirectQuery vai tuonti)?
* Käyttävätkö kaikki käyttäjät samaa raporttia?

Jos kaikki käyttäjät käyttävät tiettyä raporttia joka päivä samaan aikaan, kannattaa varmistaa, että asennat yhdyskäytävän tietokoneeseen, joka pystyy käsittelemään kaikki kyseiset käsittelypyynnöt (seuraavissa osioissa kerrotaan resurssilaskureista ja vähimmäisvaatimuksista, jotka auttavat sinua selvittämään tämän).

**Power BI:ssä** on rajoitus, joka sallii vain *yhden* yhdyskäytävän *raporttia* kohti, joten vaikka raportti perustuisi useampiin tietolähteisiin, kaikkien näiden tietolähteiden on käytettävä yhtä samaa yhdyskäytävää. Jos raporttinäkymä perustuu *useisiin* raportteihin, voit kuitenkin käyttää erillistä yhdyskäytävää kullekin raportille ja siten jakaa yhdyskäytävän kuormitusta näiden useiden raporttien kesken, jotka ovat osa tätä yhtä raporttinäkymää.

### <a name="connection-type"></a>Yhteystyyppi

**Power BI** tarjoaa kaksi yhteystyyppiä: **DirectQueryn** ja **tuonnin**. Kaikki tietolähteet eivät tue molempia yhteystyyppejä ja useat syyt voivat vaikuttaa siihen, kumpi valitaan, kuten suojausvaatimukset, suorituskyky, tietorajoitukset ja tietomallikoot. Lisätietoja yhteystyypistä ja tuetuista tietolähteistä on [käytettävissä olevien tietolähdetyyppien luettelossa](service-gateway-data-sources.md#list-of-available-data-source-types).

Käytössä oleva yhteystyypin mukaan yhdyskäytävän käyttö voi olla erilaista. Sinun tulee esimerkiksi yrittää erottaa **DirectQuery**-tietolähteet **ajoitetun päivityksen** tietolähteistä aina kun mahdollista (olettaen, että ne ovat eri raporteissa ja voidaan erottaa). Tämä estää sen, että yhdyskäytävällä olisi tuhansia DirectQuery-pyyntöjä jonossa samaan aikaan aamuksi ajoitetun suurikokoisen tietomallin päivityksen kanssa, jota käytetään yrityksen pääasiallisessa raporttinäkymässä. Seuraavassa on kummankin osalta huomioitavia seikkoja:

* **Ajoitettu päivitys**: Riippuen kyselyn koosta ja päivittäin tehtävien päivitysten määrästä voit valita, pysytkö suositeltujen laitteistovaatimusten välillä vai päivitätkö suuremman suorituskyvyn koneeseen. Jos tiettyä kyselyä ei ole taitettu, yhdyskäytäväkoneessa tapahtuu muunnoksia ja siten yhdyskäytäväkone hyötyy suuremmasta käytettävissä olevasta RAM-muistista.

* **DirectQuery**: Kysely lähetään aina, kun joku käyttäjä avaa raportin tai tarkastelee tietoja. Joten jos arvelet yli 1 000 käyttäjän käyttävän tietoja samanaikaisesti, kannattaa varmistaa, että tietokoneessa on tehokkaat ja suorituskykyiset laitteisto-osat. Suoritinydinten määrän lisääminen parantaa **DirectQuery**-yhteyden siirtomäärää.

Asennuksessa käytettävää tietokonetta koskevat vaatimukset löytyvät paikallisen tietoyhdyskäytävän [asennusvaatimuksista](/data-integration/gateway/service-gateway-install#requirements).

### <a name="location"></a>Sijainti

Yhdyskäytäväasennuksen sijainnilla voi olla merkittävä vaikutus kyselyn suorituskykyyn, joten varmista, että yhdyskäytäväsi, tietolähteiden sijainnit ja Power BI -vuokraaja ovat mahdollisimman lähellä toisiaan verkon viiveen minimoimiseksi. Määritä Power BI -vuokraajan sijaintisi Power BI -palvelussa valitsemalla **?** -kuvake oikeassa yläkulmassa ja valitsemalla sitten **Tietoja Power BI:stä**.

![Power BI -vuokraajasi sijainnin määrittäminen](media/service-gateway-deployment-guidance/powerbi-gateway-deployment-guidance_02.png)

Jos aiot käyttää Power BI -yhdyskäytävää Azure Analysis Servicesin kanssa, varmista myös, että tietoalueet vastaavat toisiaan. Jos haluat lisätietoja tietoalueiden määrittämisestä useille palveluille, katso [tämä video](https://guyinacube.com/2018/01/power-bi-azure-analysis-services-gateway-data-region/).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Välityspalvelinasetusten määrittäminen](/data-integration/gateway/service-gateway-proxy)  
* [Yhdyskäytävien vianmääritys – Power BI](service-gateway-onprem-tshoot.md)  
* [Paikallisten tietoyhdyskäytävien usein kysytyt kysymykset – Power BI](service-gateway-power-bi-faq.md)  

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

