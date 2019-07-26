---
title: Paikallisten ja pilvipalvelutietolähteiden yhdistäminen ja liittäminen
description: Käytä paikallista tietoyhdyskäytävää yhdistääksesi tai liittääksesi paikalliset ja pilvipalvelutietolähteet samaan kyselyyn.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 39f5a01a396e45207777b1a5e58e73808ddf3f88
ms.sourcegitcommit: a58461fe7dfa65c751490b52de5fc73f8e69a17f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/19/2019
ms.locfileid: "68352185"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>Paikallisten ja pilvipalvelutietolähteiden yhdistäminen ja liittäminen

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Paikallisen tietoyhdyskäytävän avulla voit yhdistää tai liittää paikallisia ja pilvipalvelutietolähteitä samassa kyselyssä. Tästä on hyötyä, kun haluat yhdistää tietoja useista lähteistä käyttämättä erillisiä kyselyjä.

>[!NOTE]
>Tämä artikkeli koskee vain tietojoukkoja, joihin on yhdistetty sekä pilvitietolähteitä että paikallisia tietolähteitä yksittäiseen kyselyyn. Tietojoukoissa, joissa on erillisiä kyselyitä (toinen muodostaa yhteyden paikalliseen ja toinen pilvitietolähteeseen), pilvitietolähdettä käyttävää kyselyä ei suoriteta yhdyskäytävän avulla.

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

   - Kohdasta **Tietolähteen tunnistetiedot**, muokkaa tarvittaessa tietolähteen tunnistetietoja.

    Varmista yksityisyystasojen asianmukainen määritys sekä pilvitietolähteissä että paikallisissa tietolähteissä, jotta liitoksia käsitellään turvallisesti.

     ![Tietojoukon asetukset](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. Kun pilvipalvelun tunnistetiedot on määritetty, voit päivittää tietojoukon käyttämällä **Päivitä nyt** -vaihtoehtoa tai ajoittaa ajoittaisen päivityksen.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja yhdyskäytävien tietojen päivittämisestä artikkelista [Tietolähteen käyttäminen ajoitetussa päivityksessä](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh).
