---
title: Paikallisten ja pilvipalvelutietolähteiden yhdistäminen ja liittäminen
description: Käytä paikallista tietoyhdyskäytävää yhdistääksesi tai liittääksesi paikalliset ja pilvipalvelutietolähteet samaan kyselyyn.
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 079e3c785277c91bdc09f91c083e80abd6bdd36b
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73881616"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>Paikallisten ja pilvipalvelutietolähteiden yhdistäminen ja liittäminen

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Voit käyttää paikallista tietoyhdyskäytävää yhdistääksesi tai liittääksesi paikalliset ja pilvipalvelutietolähteet samaan kyselyyn. Tästä ratkaisusta on hyötyä, kun haluat yhdistää tietoja useista lähteistä käyttämättä erillisiä kyselyjä.

>[!NOTE]
>Tämä artikkeli koskee vain tietojoukkoja, joihin on yhdistetty sekä pilvitietolähteitä että paikallisia tietolähteitä yksittäiseen kyselyyn. Tietojoukoissa, joissa on erillisiä kyselyitä (toinen muodostaa yhteyden paikalliseen tietolähteeseen ja toinen pilvitietolähteeseen), yhdyskäytävä ei suorita pilvitietolähteen kyselyä.

## <a name="prerequisites"></a>Edellytykset

- [Yhdyskäytävä on asennettu](/data-integration/gateway/service-gateway-install) paikalliseen tietokoneeseen.
- Power BI Desktop-tiedosto, joka sisältää kyselyjä, jotka yhdistävät paikallisia ja pilvipalvelutietolähteitä.

>[!NOTE]
>Minkä tahansa pilvitietolähteen käyttäminen edellyttää sen varmistamista, että yhdyskäytävä voi käyttää kyseisiä tietolähteitä.

1. Valitse ![Asetukset-rataskuvake](media/service-gateway-mashup-on-premises-cloud/icon-gear.png) >  Power BI -palvelun oikeasta yläkulmasta ja valitse sitten **Hallitse yhdyskäytäviä**.

    ![Hallitse yhdyskäytäviä](media/service-gateway-mashup-on-premises-cloud/manage-gateways.png)

2. Valitse yhdyskäytävä, jonka haluat määrittää.

3. Kohdassa **Yhdyskäytäväklusterin asetukset**, valitse **Salli käyttäjän pilvipalvelutietolähteiden päivittäminen tämän yhdyskäytäväklusteri kautta** > **Käytä**.

    ![Päivitä tämän yhdyskäytäväklusteri kautta](media/service-gateway-mashup-on-premises-cloud/refresh-gateway-cluster.png)

4. Tässä yhdyskäytäväklusterissa voit lisätä kyselyissä käytettäviä [paikallisia tietolähteitä](service-gateway-enterprise-manage-scheduled-refresh.md#add-a-data-source). Sinun ei tarvitse lisätä tähän pilvipalvelutietolähteitä.

5. Lataa Power BI -palveluun Power -tiedosto, joka sisältää kyselyt, jotka yhdistävät paikallisia ja pilvipalvelutietolähteitä.

6. Uuden tietojoukon **Tietojoukon asetukset** -sivulla:

   - Valitse kyseiseen tietolähteeseen liittyvän yhdyskäytävän paikallinen lähde.
   - Muokkaa tarvittaessa tietolähteen tunnistetietoja kohdassa **Tietolähteen tunnistetiedot**.

    Varmista yksityisyystasojen asianmukainen määritys sekä pilvitietolähteissä että paikallisissa tietolähteissä, jotta liitoksia käsitellään turvallisesti.

     ![Tietojoukon asetukset](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. Kun pilvipalvelun tunnistetiedot on määritetty, voit päivittää tietojoukon käyttämällä **Päivitä nyt** -vaihtoehtoa. Voit myös ajoittaa sen päivittämään säännöllisin väliajoin.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja yhdyskäytävien tietojen päivittämisestä artikkelista [Tietolähteen käyttäminen ajoitetussa päivityksessä](service-gateway-enterprise-manage-scheduled-refresh.md#use-the-data-source-for-scheduled-refresh).
