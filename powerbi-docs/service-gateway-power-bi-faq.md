---
title: Paikallisten tietoyhdyskäytävien usein kysytyt kysymykset – Power BI
description: Nämä ovat Power BI:n paikallisten tietoyhdyskäytävien usein kysyttyjä kysymyksiä. Täältä löydät Power BI:ssä käytettävien yhdyskäytävien usein kysytyt kysymykset yhdestä paikasta.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 99a03f88ed5f6585ca8ed6d64f396e70cdd046e5
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/16/2019
ms.locfileid: "68272742"
---
# <a name="on-premises-data-gateway-faq---power-bi"></a>Paikallisten tietoyhdyskäytävien usein kysytyt kysymykset – Power BI

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

## <a name="power-bi"></a>Power BI

**Kysymys:** täytyykö minun päivittää henkilökohtainen yhdyskäytävä?  
**Vastaus**: ei, voit jatkaa henkilökohtaisen yhdyskäytävän käyttöä Power BI:ssä.

**Kysymys:** Edellyttääkö yhdyskäytävän asentaminen ja hallitseminen Power BI -palvelussa erityisiä oikeuksia?
**Vastaus**: Erityisiä oikeuksia ei edellytetä.

**Kysymys:** voinko ladata palveluun Excel-työkirjoja, joissa on Power Pivot -tietomalleja, jotka muodostavat yhteyden paikallisiin tietolähteisiin? Tarvitaanko tähän yhdyskäytävä?  
**Vastaus**: Kyllä, voit ladata työkirjan. Tähän ei tarvita yhdyskäytävää. Koska tiedot ovat Excel-tietomallissa, Power BI:n raportit, jotka perustuvat Excel-työkirjaan, eivät ole reaaliaikaisia. Jos haluat päivittää raportit Power BI:ssä, sinun täytyy ladata päivitetty työkirja uudelleen joka kerta. Voit myös käyttää yhdyskäytävää ja ajoitettua päivitystä.

**Kysymys:** jos käyttäjät jakavat koontinäyttöjä, joissa on DirectQuery-yhteys, näkevätkö muut käyttäjät tiedot, vaikka heillä ei ehkä ole samoja käyttöoikeuksia?  
**Vastaus**: Jos kyseessä on Analysis Servicesiin yhteydessä oleva koontinäyttö, käyttäjät näkevät vain tiedot, joihin heillä on oikeudet. Jos käyttäjillä ei ole samoja käyttöoikeuksia, he eivät näe mitään tietoja. Jos kyseessä on muu tietolähde, kaikilla käyttäjillä on samat tunnistetiedot, jotka järjestelmänvalvoja on kyseiselle tietolähteelle määrittänyt.

**Kysymys:** miksi en saa muodostettua yhteyttä Oracle-palvelimeeni?  
**Vastaus**: Sinun täytyy ehkä asentaa Oracle-asiakasohjelma ja määrittää tnsnames.ora-tiedostoon oikeat palvelintiedot, jotta voit muodostaa yhteyden. Tämä on yhdyskäytävästä erillinen asennus. Saat lisätietoja ohjeartikkelista [Oracle-asiakasohjelman asentaminen](service-gateway-onprem-manage-oracle.md#installing-the-oracle-client).

**Kysymys:** toimiiko yhdyskäytävä ExpressRouten kanssa?  
**Vastaus**: Kyllä. Saat lisätietoja [Power BI ja ExpressRoute](service-admin-power-bi-expressroute.md) -ohjeartikkelista

**Kysymys:** Käytän R-komentosarjoja. Tuetaanko sitä?
**Vastaus**: R-komentosarjoja tuetaan vain henkilökohtaisessa tilassa.

## <a name="analysis-services-in-power-bi"></a>Analysis Services Power BI:ssä

**Kysymys:** voinko luoda mukautettuja voimassa olevien käyttäjänimien yhdistämismäärityksiä Analysis Servicesille msdmpump.dll-tiedoston avulla?  
**Vastaus**: Ei. tätä ei tueta tällä hetkellä.

**Kysymys:** voinko yhdistää yhdyskäytävän avulla monidimensioiseen (OLAP) esiintymään?  
**Vastaus**: Kyllä. Paikallinen tietoyhdyskäytävä tukee reaaliaikaisia yhteyksiä Analysis Servicesin monidimensionaalisiin ja taulukkomuotoisiin malleihin.

**Kysymys:** entä jos asennan yhdyskäytävän tietokoneeseen, joka on eri toimialueella kuin Windows-todennusta käyttävä palvelimeni?  
**Vastaus**: Tälle ei ole mitään takeita. Kaikki riippuu kahden toimialueen välisestä luottamussuhteesta. Jos kaksi erillistä toimialuetta ovat luotetun toimialueen mallissa, yhdyskäytävä voi ehkä muodostaa yhteyden Analysis Services -palvelimeen ja voimassa oleva käyttäjänimi voidaan ehkä määrittää. Jos tämä ei onnistu, saattaa ilmetä kirjautumisvirhe.

**Kysymys:** miten voin selvittää, mikä voimassa oleva käyttäjänimi välitetään paikalliseen Analysis Services -palvelimeen?  
**Vastaus**: tähän vastataan [vianmääritysartikkelissa](service-gateway-onprem-tshoot.md).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Paikallisen tietoyhdyskäytävän vianmääritys](/data-integration/gateway/service-gateway-tshoot)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

