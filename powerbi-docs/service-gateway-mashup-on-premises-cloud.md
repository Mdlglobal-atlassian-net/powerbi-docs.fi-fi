---
title: Paikallisten ja pilvipalvelutietolähteiden yhdistäminen ja liittäminen
description: Käytä paikallista tietoyhdyskäytävää yhdistääksesi tai liittääksesi paikalliset ja pilvipalvelutietolähteet samaan kyselyyn.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 06/06/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 2547be7f7bdadb7f991db54230d4fd791941838d
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/03/2018
ms.locfileid: "37600063"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>Paikallisten ja pilvipalvelutietolähteiden yhdistäminen ja liittäminen

Paikallisen tietoyhdyskäytävän avulla voit yhdistää tai liittää paikallisia ja pilvipalvelutietolähteitä samassa kyselyssä. Tästä on hyötyä, kun haluat koostaa tietoja useista lähteistä käyttämättä erillisiä kyselyjä.

## <a name="prerequisites"></a>Edellytykset

- [Yhdyskäytävä on asennettu](service-gateway-install.md) paikalliseen tietokoneeseen.
- Power BI Desktop-tiedosto, joka sisältää kyselyjä, jotka yhdistävät paikallisia ja pilvipalvelutietolähteitä.

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

     ![Tietojoukon asetukset](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. Kun pilvipalvelun tunnistetiedot on määritetty, voit päivittää tietojoukon käyttämällä **Päivitä nyt** -vaihtoehtoa tai ajoittaa ajoittaisen päivityksen.


## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja yhdyskäytävien tietojen päivittämisestä artikkelista [Tietolähteen käyttäminen ajoitetussa päivityksessä](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh).