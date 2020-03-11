---
title: Power BI -tietomallin versiointi
description: OData-palvelun käyttöön antama tietomalli
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 76947b1e311bbd1a21e09ce39461a70bed61d926
ms.sourcegitcommit: 87b7cb4a2e626711b98387edaa5ff72dc26262bb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/10/2020
ms.locfileid: "79079596"
---
# <a name="data-model-versioning"></a>Tietomallin versiointi

OData-palvelun käyttöön antama tietomalli, kuten Power BI -tietomalli, määrittää OData-palvelun ja sen asiakkaiden välisen sopimuksen. Palvelut saavat laajentaa malliaan vain siinä määrin, kun se ei riko olemassa olevia asiakkaita. Rikkovat muutokset, kuten ominaisuuksien poistaminen tai olemassa olevien ominaisuuksien tyypin muuttaminen, edellyttävät, että uudelle mallille annetaan uusi palveluversio eri URL-pääosoitteella.  
  
Seuraavat tietomallin lisäykset katsotaan turvallisiksi, joten palvelujen ei tarvitse versioida aloituskohtaansa.  
  
* Tyhjäarvon sallivan tai oletusarvon omaavan ominaisuuden lisääminen; jos sillä on sama nimi kuin olemassa olevalla dynaamisella ominaisuudella, sillä on oltava sama tyyppi (tai perustyyppi) kuin olemassa olevalla dynaamisella ominaisuudella  
* Tyhjäarvon sallivan tai yhteysarvoisen siirtymisominaisuuden lisääminen; jos sillä on sama nimi kuin olemassa olevalla dynaamisella siirtymisominaisuudella, sillä on oltava sama tyyppi (tai perustyyppi) kuin olemassa olevalla dynaamisella siirtymisominaisuudella  
* Uuden entiteettityypin lisääminen malliin  
* Uuden monitasoisen tyypin lisääminen malliin  
* Uuden entiteettijoukon lisääminen  
* Uuden yksittäistietokannan lisääminen  
* Toiminnon, funktion, toiminnon tuonnin tai funktion tuonnin lisääminen
* Tyhjäarvon sallivan toimintoparametrin lisääminen  
* Tyypin määritelmän tai luetteloinnin lisääminen  
* Sellaisen huomautuksen lisääminen mallielementtiin, jota asiakkaan ei tarvitse ymmärtää, jotta se voi olla oikeanlaisessa vuorovaikutuksessa palvelun kanssa  
  
Asiakkaiden ***ON OLTAVA*** valmiita siihen, että palvelut tekevät lisääviä muutoksia malliin. Asiakkaiden on erityisesti valmistauduttava vastaanottamaan sellaisia ominaisuuksia ja johdettuja tyyppejä, joita palvelu ei ole aiemmin määrittänyt.  
  
Palvelut ***EIVÄT SAA*** muuttaa tietomalliaan todennetun käyttäjän mukaan. Jos tietomalli riippuu käyttäjästä tai käyttäjäryhmästä, kaikkien muutosten ON OLTAVA turvallisia muutoksia tämän osion määritelmien mukaisesti, kun täyttä mallia verrataan käyttäjille näkyvään malliin rajoitetuilla valtuutuksilla.  
  
Jos haluat lisätietoja OData-tietomallien standardeista, katso [OData-versio 4.0 osa 1: Protocol Plus Errata 02](https://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html).  
  
## <a name="see-also"></a>Muuta aiheeseen liittyvää
[Power BI REST -ohjelmointirajapinnan yleiskatsaus](https://docs.microsoft.com/rest/api/power-bi/)