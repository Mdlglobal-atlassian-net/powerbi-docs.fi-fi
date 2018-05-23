---
title: Paikallisten tietoyhdyskäytävien usein kysytyt kysymykset
description: Nämä ovat paikallisten tietoyhdyskäytävien usein kysyttyjä kysymyksiä. Täältä löydät yhdyskäytävien usein kysytyt kysymykset yhdestä paikasta.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 01/24/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: b4ecec3b2e53c2fea0fcbb7d78d1114da1a105ed
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2018
---
# <a name="on-premises-data-gateway-faq"></a>Paikallisten tietoyhdyskäytävien usein kysytyt kysymykset
<!-- Shared FAQ shared Include -->
[!INCLUDE [gateway-onprem-faq-shared-include](./includes/gateway-onprem-faq-shared-include.md)]

## <a name="analysis-services"></a>Analysis Services
**Kysymys:** voinko luoda mukautettuja voimassa olevien käyttäjänimien yhdistämismäärityksiä Analysis Servicesille msdmpump.dll-tiedoston avulla?  
**Vastaus**: et voi, tätä ei tueta tällä hetkellä.

**Kysymys:** voinko yhdistää yhdyskäytävän avulla monidimensioiseen (OLAP) esiintymään?  
**Vastaus:** Kyllä. Paikallinen tietoyhdyskäytävä tukee reaaliaikaisia yhteyksiä Analysis Servicesin monidimensionaalisiin ja taulukkomuotoisiin malleihin.

**Kysymys:** entä jos asennan yhdyskäytävän tietokoneeseen, joka on eri toimialueella kuin Windows-todennusta käyttävä palvelimeni?  
**Vastaus:** Tälle ei ole mitään takeita. Kaikki riippuu kahden toimialueen välisestä luottamussuhteesta. Jos kaksi erillistä toimialuetta ovat luotetun toimialueen mallissa, yhdyskäytävä voi ehkä muodostaa yhteyden Analysis Services -palvelimeen ja voimassa oleva käyttäjänimi voidaan ehkä määrittää. Jos tämä ei onnistu, saattaa ilmetä kirjautumisvirhe.

**Kysymys:** miten voin selvittää, mikä voimassa oleva käyttäjänimi välitetään paikalliseen Analysis Services -palvelimeen?  
**Vastaus**: tähän vastataan [vianmääritysartikkelissa](service-gateway-onprem-tshoot.md).

**Kysymys:** Minulla on 25 tietokantaa Analysis Servicessä. Onko mitään tapaa saada ne kaikki käyttöön yhdyskäytävässä samanaikaisesti?  
**Vastaus**: Ei. Tämä on suunnitteilla, mutta aikataulu ei ole vielä tiedossa.

## <a name="administration"></a>Hallinta
**Kysymys:** voiko yhdyskäytävällä olla useita järjestelmänvalvojia?  
**Vastaus:** Kyllä. Kun hallitset yhdyskäytävää, voit lisätä lisää järjestelmänvalvojia järjestelmänvalvojien välilehdessä.

**Kysymys:** täytyykö yhdyskäytävän järjestelmänvalvojan olla järjestelmänvalvoja koneessa, johon yhdyskäytävä on asennettu?  
**Vastaus**: Ei. Yhdyskäytävän järjestelmänvalvoja hallitsee yhdyskäytävää palvelussa.

**Kysymys:** voinko estää organisaationi käyttäjiä luomasta yhdyskäytävää?  
**Vastaus**: Et. Tämä on suunnitteilla, mutta aikataulu ei ole vielä tiedossa.

**Kysymys:** onko organisaationi yhdyskäytäville saatavilla käyttö- ja tilastotietoja?  
**Vastaus**: Ei. Tämä on suunnitteilla, mutta aikataulu ei ole vielä tiedossa.

## <a name="power-bi"></a>Power BI
**Kysymys:** täytyykö minun päivittää henkilökohtainen yhdyskäytävä?
**Vastaus**: ei, voit jatkaa henkilökohtaisen yhdyskäytävän käyttöä Power BI:ssä.

**Kysymys:** kuinka usein Power BI:n koontinäytön ruudut päivitetään, kun käytössä on paikallisen tietoyhdyskäytävän yhteys?  
**Vastaus**: Ne päivitetään noin 10 minuutin välein. DirectQuery-yhteydet hoitavat tämän. Tämä ei tarkoita sitä, että ruutu tekee kyselyn paikalliseen palvelimeen ja näyttää uudet tiedot joka kymmenes minuutti.

**Kysymys:** voinko ladata palveluun Excel-työkirjoja, joissa on Power Pivot -tietomalleja, jotka muodostavat yhteyden paikallisiin tietolähteisiin? Tarvitaanko tähän yhdyskäytävä?  
**Vastaus**: Kyllä, voit ladata työkirjan. Tähän ei tarvita yhdyskäytävää. Koska tiedot ovat Excel-tietomallissa, Power BI:n raportit, jotka perustuvat Excel-työkirjaan, eivät ole reaaliaikaisia. Jos haluat päivittää raportit Power BI:ssä, sinun täytyy ladata päivitetty työkirja uudelleen joka kerta. Voit myös käyttää yhdyskäytävää ja ajoitettua päivitystä.

**Kysymys:** jos käyttäjät jakavat koontinäyttöjä, joissa on DirectQuery-yhteys, näkevätkö muut käyttäjät tiedot, vaikka heillä ei ehkä ole samoja käyttöoikeuksia?  
**Vastaus**: Jos kyseessä on Analysis Servicesiin yhteydessä oleva koontinäyttö, käyttäjät näkevät vain tiedot, joihin heillä on oikeudet. Jos käyttäjillä ei ole samoja käyttöoikeuksia, he eivät näe mitään tietoja. Jos kyseessä on muu tietolähde, kaikilla käyttäjillä on samat tunnistetiedot, jotka järjestelmänvalvoja on kyseiselle tietolähteelle määrittänyt.

**Kysymys:** miksi en saa muodostettua yhteyttä Oracle-palvelimeeni?  
**Vastaus:** Sinun täytyy ehkä asentaa Oracle-asiakasohjelma ja määrittää tnsnames.ora-tiedostoon oikeat palvelintiedot, jotta voit muodostaa yhteyden. Tämä on yhdyskäytävästä erillinen asennus. Saat lisätietoja ohjeartikkelista [Oracle-asiakasohjelman asentaminen](service-gateway-onprem-manage-oracle.md#installing-the-oracle-client).

**Kysymys:**: toimiiko yhdyskäytävä ExpressRouten kanssa?  
**Vastaus:** Kyllä. Saat lisätietoja [Power BI ja ExpressRoute](service-admin-power-bi-expressroute.md) -ohjeartikkelista

## <a name="next-steps"></a>Seuraavat vaiheet
[Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)  
[Paikallinen tietoyhdyskäytävä tarkemmin](service-gateway-onprem-indepth.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

