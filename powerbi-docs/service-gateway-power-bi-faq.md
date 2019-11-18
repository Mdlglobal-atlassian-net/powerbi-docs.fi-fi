---
title: Paikallisten tietoyhdyskäytävien usein kysytyt kysymykset – Power BI
description: Tämä artikkeli sisältää Power BI:n paikallisten tietoyhdyskäytävien usein kysyttyjä kysymyksiä. Artikkelista löydät Power BI:ssä käytettävien yhdyskäytävien usein kysytyt kysymykset yhdestä paikasta.
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 4aa3d46741044498846865278db51859980a19b9
ms.sourcegitcommit: 0d7ad791a2d2bef45d5d60e38e0af4c9fc22187b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2019
ms.locfileid: "74010830"
---
# <a name="on-premises-data-gateway-faq---power-bi"></a>Paikallisten tietoyhdyskäytävien usein kysytyt kysymykset – Power BI

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

## <a name="power-bi"></a>Power BI

**Kysymys:** Onko paikallinen tietoyhdyskäytävä (henkilökohtainen tila) päivitettävä?

**Vastaus**: Ei, voit jatkaa yhdyskäytävän (henkilökohtainen tila) käyttöä Power BI:ssä.

**Kysymys:** Edellyttääkö yhdyskäytävän asentaminen ja hallitseminen Power BI -palvelussa erityisiä oikeuksia?

**Vastaus**: Erityisiä oikeuksia ei edellytetä.

**Kysymys:** voinko ladata palveluun Excel-työkirjoja, joissa on Power Pivot -tietomalleja, jotka muodostavat yhteyden paikallisiin tietolähteisiin? Tarvitaanko tähän yhdyskäytävä? 

**Vastaus**: Kyllä, voit ladata työkirjan. Tähän ei tarvita yhdyskäytävää. Koska tiedot ovat Excel-tietomallissa, Power BI:n raportit, jotka perustuvat Excel-työkirjaan, eivät ole reaaliaikaisia. Jos haluat päivittää raportit Power BI:ssä, sinun täytyy ladata päivitetty työkirja uudelleen joka kerta. Voit myös käyttää yhdyskäytävää ja ajoitettua päivitystä.

**Kysymys:** jos käyttäjät jakavat koontinäyttöjä, joissa on DirectQuery-yhteys, näkevätkö muut käyttäjät tiedot, vaikka heillä ei ehkä ole samoja käyttöoikeuksia? 

**Vastaus**: Jos kyseessä on Azure Analysis Servicesiin yhteydessä oleva koontinäyttö, käyttäjät näkevät vain tiedot, joihin heillä on oikeudet. Jos käyttäjillä ei ole samoja käyttöoikeuksia, he eivät näe mitään tietoja. Jos kyseessä on muu tietolähde, kaikilla käyttäjillä on samat tunnistetiedot, jotka järjestelmänvalvoja on kyseiselle tietolähteelle määrittänyt.

**Kysymys:** miksi en saa muodostettua yhteyttä Oracle-palvelimeeni? 

**Vastaus**: Sinun täytyy ehkä asentaa Oracle-asiakasohjelma ja määrittää tnsnames.ora-tiedostoon oikeat palvelintiedot, jotta voit muodostaa yhteyden. Tämä on yhdyskäytävästä erillinen asennus. Saat lisätietoja ohjeartikkelista [Oracle-asiakasohjelman asentaminen](service-gateway-onprem-manage-oracle.md#install-the-oracle-client).

**Kysymys:** Käytän R-komentosarjoja. Tuetaanko sitä?

**Vastaus**: R-komentosarjoja tuetaan vain henkilökohtaisessa tilassa.

## <a name="analysis-services-in-power-bi"></a>Analysis Services Power BI:ssä

**Kysymys:** voinko luoda mukautettuja voimassa olevien käyttäjänimien yhdistämismäärityksiä Analysis Servicesille msdmpump.dll-tiedoston avulla? 

**Vastaus**: Ei. Tätä ei tueta tällä hetkellä.

**Kysymys:** voinko yhdistää yhdyskäytävän avulla monidimensioiseen (OLAP) esiintymään? 

**Vastaus**: Kyllä. Paikallinen tietoyhdyskäytävä tukee reaaliaikaisia yhteyksiä Analysis Servicesin monidimensionaalisiin ja taulukkomuotoisiin malleihin.

**Kysymys:** entä jos asennan yhdyskäytävän tietokoneeseen, joka on eri toimialueella kuin Windows-todennusta käyttävä palvelimeni? 

**Vastaus**: Tälle ei ole mitään takeita. Kaikki riippuu kahden toimialueen välisestä luottamussuhteesta. Jos kaksi erillistä toimialuetta ovat luotetun toimialueen mallissa, yhdyskäytävä voi ehkä muodostaa yhteyden Analysis Services -palvelimeen ja voimassa oleva käyttäjänimi voidaan ehkä määrittää. Jos tämä ei onnistu, saattaa ilmetä kirjautumisvirhe.

**Kysymys:** miten voin selvittää, mikä voimassa oleva käyttäjänimi välitetään paikalliseen Analysis Services -palvelimeen? 

**Vastaus**: tähän kysymykseen vastataan [vianmääritysartikkelissa](service-gateway-onprem-tshoot.md).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Paikallisen tietoyhdyskäytävän vianmääritys](/data-integration/gateway/service-gateway-tshoot)

Onko sinulla kysyttävää? Kokeile [Power BI -yhteisöä](https://community.powerbi.com/).

