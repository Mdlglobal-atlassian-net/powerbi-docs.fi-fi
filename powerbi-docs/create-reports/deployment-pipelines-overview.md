---
title: Käyttöönottoputkien yleiskatsaus
description: Tutustu Power BI:n käyttöönottoputkiin
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.date: 05/06/2020
ms.openlocfilehash: be945d1d9612804a90c14c47d2c468f5ed5a843f
ms.sourcegitcommit: 008467dc9d4f88f91728c59caeb68b7db94f267c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/07/2020
ms.locfileid: "82885026"
---
# <a name="introduction-to-deployment-pipelines-preview"></a>Käyttöönottoputkien esittely (esikatselu)

Nykymaailmassa analytiikka on oleellinen osa päätöksentekoa lähes jokaisessa organisaatiossa. Power BI:n lisääntyvä käyttö analytiikkatyökaluna vaatii, että se voi käyttää entistä enemmän tietoja, näyttää houkuttelevalta ja on käyttäjäystävällinen. Ennen kaikkea Power BI:n on kuitenkin oltava aina käytettävissä ja luotettava. Näiden vaatimusten täyttämiseksi BI-sisällöntuottajien on tehtävä yhteistyötä tehokkaasti.

Käyttöönottoputket ovat tehokas ja uudelleenkäytettävä työkalu. Sen avulla yritysten BI-sisällöntuottajat, joilla on käytettävissään Premium-kapasiteetti, voivat hallita organisaation sisällön elinkaarta. Näin voidaan kehittää ja testata Power BI -sisältöä, kuten raportteja, koontinäyttöjä ja tietojoukkoja, ennen kuin käyttäjät kuluttavat niitä.

Työkalu on suunniteltu putkeksi, jossa on kolme vaihetta:

* **<a name="development"></a>Kehitys**
    
    Tämän vaiheen avulla suunnitellaan, luodaan ja ladataan uutta sisältöä muiden sisällöntuottajien kanssa. Tämä on käyttöönottoputkien ensimmäinen vaihe.

* **<a name="test"></a>Testaus**

    Kun sisältö on ladattu palvelimeen ja kaikki muutokset on tehty kehitysvaiheessa, sisältö voidaan siirtää tähän vaiheeseen testausta varten. Seuraavassa on kolme esimerkkiä siitä, mitä testausympäristössä voidaan tehdä:

    * Jaa sisältöä testaajien ja tarkistajien kanssa

    * Lataa ja suorita testejä suurilla tietomäärillä

    * Testaa sovellustasi ja katso, miltä se näyttää loppu käyttäjillesi

* **<a name="production"></a>Tuotanto**

    Kun olet testannut sisällön, voit tuotantovaiheen avulla jakaa sisältösi lopullisen version yrityskäyttäjille koko organisaatiossa.

![käyttöönottoputket](media/deployment-pipelines-overview/deployment-pipelines.png)

## <a name="next-steps"></a>Seuraavat vaiheet

>[!div class="nextstepaction"]
>[Käyttöönottoputkien käytön aloittaminen](deployment-pipelines-get-started.md)

>[!div class="nextstepaction"]
>[Tutustu käyttöönottoputkien prosessiin](deployment-pipelines-process.md)

>[!div class="nextstepaction"]
>[Käyttöönottoputkien vianmääritys](deployment-pipelines-troubleshooting.md)

>[!div class="nextstepaction"]
>[Käyttöönottoputkien parhaat käytännöt](deployment-pipelines-best-practices.md)