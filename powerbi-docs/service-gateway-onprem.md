---
title: Paikallinen tietoyhdyskäytävä
description: Tämä on yleiskatsaus paikallisesta tietoyhdyskäytävästä Power BI:lle. Voit käyttää tätä yhdyskäytävää DirectQueryn tietolähteiden kanssa. Voit käyttää myös tätä yhdyskäytävää päivittämään pilvipalvelun tietojoukkoja paikallisten tietojen kanssa.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Gateways
ms.date: 07/15/2019
ms.openlocfilehash: 57c4292913a2056ab285716de1e1b83e2313f723
ms.sourcegitcommit: 9d13ef7a257b5006fca5f92acf5b611f5cd143a2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/18/2019
ms.locfileid: "68307091"
---
# <a name="what-is-an-on-premises-data-gateway"></a>Mikä paikallinen tietoyhdyskäytävä on?

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Paikallinen tietoyhdyskäytävä toimii siltana tarjoten nopean ja turvallisen tiedonsiirron paikallisten tietojen (eli tietojen, jotka eivät sijaitse pilvipalvelussa) ja useiden Microsoftin pilvipalveluiden välillä. Pilvipalveluita ovat esimerkiksi Power BI, PowerApps, Microsoft Flow, Azure Analysis Services ja Logic Apps. Yhdyskäytävän avulla organisaatiot voivat säilyttää tietokannat ja muut tietolähteet paikallisissa verkoissa ja käyttää niitä turvallisesti pilvipalveluissa.

## <a name="how-the-gateway-works"></a>Yhdyskäytävän toiminta

![Yhdyskäytävän yleiskatsaus](media/service-gateway-onprem/on-premises-data-gateway.png)

Lisätietoja yhdyskäytävän toiminnasta on artikkelissa [Paikallisen tietoyhdyskäytävän arkkitehtuuri](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Yhdyskäytävien tyypit

Yhdyskäytäviä on kahta tyyppiä, joita kumpaakin käytetään eri skenaarioissa:

* **Paikallinen tietoyhdyskäytävä** – useat käyttäjät voivat muodostaa yhteyden useisiin paikallisiin tietolähteisiin. Voit käyttää paikallista tietoyhdyskäytävää kaikissa tuetuissa palveluissa yhdellä yhdyskäytävän asennuksella. Tämä yhdyskäytävä sopii hyvin monimutkaisiin tilanteisiin, joissa useat käyttäjät käyttävät useita tietolähteitä.

* **Paikallinen tietoyhdyskäytävä (henkilökohtainen tila)** – yksi käyttäjä voi muodostaa yhteyden tietolähteisiin, eikä tietoyhdyskäytävää voi jakaa muiden kanssa. Paikallista tietoyhdyskäytävää (henkilökohtainen tila) voidaan käyttää vain Power BI:n kanssa. Tämä yhdyskäytävä sopii hyvin tilanteisiin, joissa sinä olet ainoa raporttien luoja eikä sinun tarvitse jakaa tietolähteitä muiden kanssa.

## <a name="using-a-gateway"></a>Yhdyskäytävän käyttäminen

Yhdyskäytävän käyttämisessä on neljä päävaihetta:

1. [Lataa ja asenna yhdyskäytävä](/data-integration/gateway/service-gateway-install) paikalliseen tietokoneeseen.
2. [Määritä](/data-integration/gateway/service-gateway-app) yhdyskäytävä palomuurin ja muiden verkkotarpeiden mukaan.
3. [Lisää yhdyskäytävän järjestelmänvalvojat](/data-integration/gateway/service-gateway-manage), jotka voivat myös hallita muita verkkovaatimuksia.
4. [Suorita](service-gateway-onprem-tshoot.md) yhdyskäytävän vianmääritys virheiden varalta.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Paikallisen tietoyhdyskäytävän asentaminen](/data-integration/gateway/service-gateway-install)


Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
