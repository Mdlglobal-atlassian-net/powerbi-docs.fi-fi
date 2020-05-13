---
title: Tietovoiden käyttö paikallisiin tietolähteisiin
description: Lue, miten voit käyttää paikallisia tietoja tietovoissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/08/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 1008cf34cd09d8039107794e10dcef845ec35110
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83322420"
---
# <a name="using-dataflows-with-on-premises-data-sources"></a>Tietovoiden käyttö paikallisiin tietolähteisiin

Voit **tietovoiden** avulla luoda tietokokoelmia erilaisista lähteistä, puhdistaa tietoja, muuntaa tietoja ja ladata sitten tiedot Power BI -säilöön. Kun luot tietovuossa, haluat ehkä käyttää paikallisia tietolähteitä. Tässä artikkelissa selvitetään tietovoiden luomiseen liittyvää vaatimusta ja sitä, miten **yritysyhdyskäytävä** on määritettävä näiden yhteyksien käyttöönottamiseksi.

![Tietovuot ja yhdyskäytävät](media/service-dataflows-onpremises-gateways/onpremises-gateways_01.png)

## <a name="configuring-an-enterprise-gateway-for-use-with-dataflows"></a>Yritysyhdyskäytävän määrittäminen tietovuokäyttöä varten

Jos haluat luoda tietovuon yhdyskäytävän avulla, käyttäjän täytyy olla yritysyhdyskäytävän järjestelmänvalvoja – tai järjestelmänvalvojan on täytynyt jakaa tietolähde, jota aiotaan käyttää käyttäjän kanssa. 


> [!NOTE]
> Tietovoita tuetaan vain käyttämällä yritysyhdyskäytäviä.

## <a name="using-an-on-premises-data-source-in-a-dataflow"></a>Paikallisen tietolähteen käyttäminen tietovuossa

Kun luot tietovuota, valitse paikallinen tietolähde tietolähteiden luettelosta seuraavassa kuvassa näytetyn mukaisesti.

![Paikallisen tietolähteen valinta](media/service-dataflows-onpremises-gateways/onpremises-gateways_02a.png)

Kun olet tehnyt valintasi, sinua pyydetään antamaan yhteystiedot yritysyhdyskäytävästä, jota käytetään yhteyden muodostamiseen paikalliseen tietoon. Sinun on itse valittava yhdyskäytävä ja annettava valitun yhdyskäytävän tunnistetiedot.

![Anna yhteyden tiedot](media/service-dataflows-onpremises-gateways/onpremises-gateways_03.png)

## <a name="monitoring-your-gateway"></a>Yhdyskäytävän valvonta

Voit valvoa tietovuon yritysyhdyskäytävää samalla tavoin kuin tietojoukon yhdyskäytäviä.

Power BI:n tietovuon asetusnäytössä voit valvoa tietovuon yhdyskäytävän tilaa ja määrittää yhdyskäytävän tietovuolle seuraavan kuvan mukaisesti.

![Yhdyskäytävän valvominen](media/service-dataflows-onpremises-gateways/onpremises-gateways_01.png)

## <a name="changing-a-gateway"></a>Yhdyskäytävän vaihtaminen

Voit vaihtaa tietylle tietovuolle käytettyä yritysyhdyskäytävää kahdella tavalla:

1. **Luontityökalusta** – voit muuttaa kaikille kyselyillesi määritettyä yhdyskäytävää tietovuon luontityökalun avulla.

    > [!NOTE]
    > Tietovuo yrittää löytää tai luoda vaaditut tietolähteet uuden yhdyskäytävän avulla. Jos se ei voi tehdä tätä, et voi vaihtaa yhdyskäytävää ennen kuin kaikki tarvittavat tietovuot ovat saatavilla valitusta yhdyskäytävästä.

2. **Asetusnäytöstä** – voit vaihtaa määritettyä yhdyskäytävää tietovuon asetusnäytön avulla Power BI -palvelussa.

Lue lisää yritysyhdyskäytävistä artikkelista [Paikallisen tiedon yhdyskäytävä](../connect-data/service-gateway-onprem.md).

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

Yritysyhdyskäytävien ja tietovoiden käyttöön liittyy pari tunnettua rajoitusta:

* Jokainen tietovuo voi käyttää vain yhtä yhdyskäytävää. Näin ollen kaikki kyselyt on määritettävä saman yhdyskäytävän avulla.
* Yhdyskäytävän vaihtaminen vaikuttaa koko tietovuohon.
* Jos tarvitaan useampia yhdyskäytäviä, paras keino on luoda useita tietovoita (yksi kutakin yhdyskäytävää varten) ja yhdistää tiedot laskennan tai entiteetin viitetoimintojen avulla.
* Tietovoita tuetaan vain käyttämällä yritysyhdyskäytäviä. Henkilökohtaisia yhdyskäytäviä ei voi käyttää valintaan avattavissa luetteloissa ja asetusnäytöissä.


## <a name="next-steps"></a>Seuraavat vaiheet

Tässä artikkelissa on lisätietoja paikallisen tietolähteen käyttämisestä tietovoille ja siitä, miten yhdyskäytäviä voidaan käyttää ja määrittää tällaisen tiedon käsittelemiseksi. Myös seuraavista artikkeleista voi olla apua

* [Omatoiminen tietojen valmisteleminen tietovoiden avulla](service-dataflows-overview.md)
* [Tietovoiden luominen ja käyttäminen Power BI:ssä](service-dataflows-create-use.md)
* [Laskettujen entiteettien käyttäminen Power BI Premiumissa](service-dataflows-computed-entities-premium.md)
* [Kehittäjien resurssit Power BI -tietovoille](service-dataflows-developer-resources.md)

Lisätietoja Power Querysta ja ajoitetusta päivityksestä on seuraavissa artikkeleissa:
* [Kyselyn yleiskatsaus Power BI Desktopissa](desktop-query-overview.md)
* [Ajoitetun päivityksen määrittäminen](../connect-data/refresh-scheduled-refresh.md)

Lisätietoja Common Data Modelista on sen yleiskatsauksen sisältävässä artikkelissa:
* [Common Data Model – yleiskatsaus](https://docs.microsoft.com/powerapps/common-data-model/overview)
