---
title: Parannettujen tietojoukon metatietojen käyttäminen Power BI Desktopissa (esiversio)
description: Tämä artikkeli käsittelee parannettujen tietojoukon metatietojen käyttämistä Power BI:ssä.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 03/31/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 87b4be55b1b811f63dbb7fe271bc3c3fa4af2755
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83347420"
---
# <a name="using-enhanced-dataset-metadata-preview"></a>Parannettujen tietojoukon metatietojen käyttäminen (esiversio)

Kun Power BI Desktop luo raportteja, se luo myös tietojoukon metatietoja vastaaviin PBIX- ja PBIT-tiedostoihin. Aiemmin metatiedot tallennettiin Power BI Desktopille erityisesti määritettyyn muotoon. Se käytti Base 64 -koodattuja M-lausekkeita ja tietolähteitä ja teki oletuksia siitä, miten metatiedot oli tallennettu.

Monet näistä rajoituksista poistuvat **parannettujen tietojoukon metatietojen** ominaisuuden tultua käyttöön. Kun **parannetut tietojoukon metatiedot** -on otettu käyttöön, Power BI Desktopin luomat metatiedot käyttävät samaa muotoa kuin Analysis Services -taulukkomallit, joka perustuu [taulukkomuotoiseen objektimalliin](https://docs.microsoft.com/bi-reference/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo).


**Parannettujen tietojoukon metatietojen** ominaisuus on strateginen ja perusluonteinen, koska tulevat Power BI -ominaisuudet kehitetään sen metatietoja käyttäen. Eräitä lisäominaisuuksia, jotka hyötyvät parannetuista tietojoukon metatiedoista, ovat [XMLA-luku/kirjoitus](https://docs.microsoft.com/power-platform-release-plan/2019wave2/business-intelligence/xmla-readwrite) Power BI -tietojoukkojen hallintaan, sekä Analysis Services -kuormitusten siirtäminen Power BI:hin, joka hyötyy seuraavan sukupolven ominaisuuksista.



## <a name="enable-enhanced-dataset-metadata"></a>Parannettujen tietojoukon metatietojen käyttöönotto

**Parannetut tietojoukon metatiedot** -ominaisuus on tällä hetkellä esikatselussa. Kun haluat ottaa käyttöön parannetut tietojoukon metatiedot, valitse Power BI Desktopissa **Tiedosto > Asetukset ja vaihtoehdot > Asetukset > Esikatseluominaisuudet** ja valitse sitten valintaruutu **Tallenna tietojoukot parannettujen metatietojen muotoa käyttäen**, kuten seuraavassa kuvassa näkyy. 

![Ota käyttöön esikatselutoiminto](media/desktop-enhanced-dataset-metadata/enhanced-dataset-metadata-01.png)

Sinua pyydetään käynnistämään Power BI Desktop uudelleen.

![Uudelleenkäynnistyspyyntö](media/desktop-enhanced-dataset-metadata/enhanced-dataset-metadata-02.png)

Kun esikatselutoiminto on käytössä, Power BI Desktop yrittää päivittää PBIX- ja PBIT-tiedostot, joissa käytetään aikaisempaa metatietomuotoa. 

> [!IMPORTANT]
> **Parannettujen tietojoukon metatietojen** käyttöönotto aiheuttaa peruuttamattoman päivityksen raportteihin. Power BI raportit, jotka on ladattu tai Power BI Desktopilla **parannettujen tietojoukon metatietojen** käyttöönoton jälkeen, muunnetaan peruuttamattomasti tietojoukkojen parannettujen metatietojen muotoon.

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

Esikatseluversiossa ovat voimassa seuraavat rajoitukset, kun esikatselutoiminto on otettu käyttöön.

### <a name="unsupported-features-and-connectors"></a>Ominaisuudet ja liittimet, joita ei tueta
Kun avaat aiemman, päivittämättömän PBIX- tai PBIT-tiedoston, päivitys epäonnistuu, jos tietojoukko sisältää jonkin seuraavista ominaisuuksista tai liittimistä. Jos sellainen epäonnistuminen tapahtuu, sillä ei pitäisi olla välitöntä vaikutusta käyttökokemukseen, ja Power BI Desktop jatkaa aikaisemman metatietomuodon käyttöä.

* Python-komentosarjat
* Mukautetut liittimet
* Azure DevOps Server
* BI-liitin
* Denodo
* Dremio
* Exasol
* Indexima
* IRIS
* Jethro ODBC
* Kyligence Enterprise
* Mark Logic ODBC
* Qubole Presto
* Team Desk
* M-lausekkeet, joihin sisältyy tiettyjä merkkiyhdistelmiä, kuten “\\n” sarakkeiden nimissä
* Kun käytät tietojoukkoja niin, että **parannetut tietojoukon metatiedoten** -ominaisuus on käytössä, kertakirjautumistietolähteitä (SSO-tietolähteitä) ei voi määrittää Power BI -palvelussa

Lisäksi PBIX- ja PBIT-tiedostot, jotka on jo onnistuneesti päivitetty käyttämään **parannettuja tietojoukon metatietoja**, *eivät* voi käyttää yllä olevia ominaisuuksia tai liittimiä nykyisessä versiossa.

### <a name="lineage-view"></a>Historiatietonäkymä
Uutta metatietomuotoa käyttävät tietojoukot eivät tällä hetkellä näytä linkkejä tietovuokohteisiin, jotka ovat Power BI -palvelun historianäkymässä.

## <a name="next-steps"></a>Seuraavat vaiheet

Power BI Desktopilla voit tehdä kaikenlaista. Saat lisätietoja sen toiminnoista seuraavista resursseista:

* [Mikä on Power BI Desktop?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktopin uudet ominaisuudet ja toiminnot](../fundamentals/desktop-latest-update.md)
* [Power BI Desktopin kyselyjen yleiskatsaus](../transform-model/desktop-query-overview.md)
* [Tietotyypit Power BI Desktopissa](desktop-data-types.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](../transform-model/desktop-common-query-tasks.md)
