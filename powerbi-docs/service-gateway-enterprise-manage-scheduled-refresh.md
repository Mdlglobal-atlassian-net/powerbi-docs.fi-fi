---
title: Tietolähteen hallinta – tuonti ja ajoitettu päivitys
description: Paikallisen yhdyskäytävän ja kyseiseen yhdyskäytävään kuuluvien tietolähteiden hallinta. Tämä artikkeli käsittelee erityisesti tietolähteitä, joita voidaan käyttää tuonnissa ja ajoitetussa päivityksessä.
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: arthii
LocalizationGroup: Gateways
ms.openlocfilehash: 13d8cd9838cdcb035e7dd30a1180ac77957441ea
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79207409"
---
# <a name="manage-your-data-source---importscheduled-refresh"></a>Tietolähteen hallinta – tuonti ja ajoitettu päivitys

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Kun [paikallinen tietoyhdyskäytävä on asennettu](/data-integration/gateway/service-gateway-install), sinun on [lisättävä tietolähteitä](service-gateway-data-sources.md#add-a-data-source), joita voidaan käyttää kyseisen yhdyskäytävän kanssa. Tämä artikkeli kuvailee, miten ajoitetussa päivityksessä käytettäviä yhdyskäytäviä ja tietolähteitä käytetään DirectQueryn tai reaaliaikaisen yhteyden sijasta.

## <a name="add-a-data-source"></a>Tietolähteen lisääminen

Lisätietoja tietolähteen lisäämisestä on artikkelissa [Tietolähteen lisääminen](service-gateway-data-sources.md#add-a-data-source). Valitse tietolähdetyyppi.

Kaikkia listattuja tietolähdetyyppejä voi käyttää paikallisen tietoyhdyskäytävän ajoitetussa päivityksessä. Analysis Servicesia, SQL Serveria ja SAP HANA:a voidaan käyttää ajoitetussa päivityksessä tai DirectQueryn/reaaliaikaisen yhteyden kanssa.

![Tietolähteen valitseminen](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings2.png)

Täytä sitten tietolähteen tiedot, mukaan lukien lähteen tiedot sekä tunnistetiedot, joita käytetään kun tietolähteeseen otetaan yhteys.

> [!NOTE]
> Kaikki tietolähteeseen kohdennetut kyselyt suoritetaan näitä tunnistetietoja käyttämällä. Lisätietoja tunnistetietojen tallentamisesta on artikkelissa [Salattu tunnistetietojen tallentaminen pilvipalveluun](service-gateway-data-sources.md#store-encrypted-credentials-in-the-cloud).

![Tietolähdeasetusten täyttäminen](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings3-oracle.png)

Luettelo tietolähdetyypeistä, joita voidaan käyttää ajoitetussa päivityksessä, on kohdassa [Luettelo käytettävissä olevista tietolähdetyypeistä](service-gateway-data-sources.md#list-of-available-data-source-types).

Kun kaikki kohdat on täytetty, valitse **Lisää.** Voit nyt käyttää tietolähdettä paikallisten tietojen ajoitetussa päivityksessä. *Yhteyden muodostaminen onnistui* -teksti tulee näkyviin, jos yhteys muodostettiin onnistuneesti.

![Yhteyden tilan näyttäminen](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings4.png)

### <a name="advanced-settings"></a>Lisäasetukset

Vaihtoehtoisesti voit määrittää tietolähteellesi yksityisyystason. Tällä asetuksella hallinnoidaan sitä, miten tietoja voidaan yhdistää. Sitä käytetään vain ajoitetussa päivityksessä. Lisätietoja tietolähteen yksityisyystasoista on artikkelissa [Yksityisyystasot (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Yksityisyystason määrittäminen](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings9.png)

## <a name="use-the-data-source-for-scheduled-refresh"></a>Tietolähteen käyttö ajoitetussa päivityksessä

Kun tietolähde on luotu, se on käyttäjien saatavilla joko DirectQuery-yhteyksien tai ajoitetun päivityksen välityksellä.

> [!NOTE]
> Palvelimen ja tietokannan nimien pitää täsmätä paikallisen tietoyhdyskäytävän Power BI Desktopin ja tietolähteen kanssa.

Yhdyskäytävän tietojoukon ja tietolähteen välinen linkki perustuu palvelimen ja tietokannan nimiin. Näiden nimien on vastattava toisiaan. Jos esimerkiksi Power BI Desktopissa palvelimen nimelle annetaan IP-osoite, samaa IP-osoitetta tulee käyttää myös yhdyskäytävän kokoonpanon tietolähteessä. Jos käytät Power BI Desktopissa nimeä *PALVELIN\ESIINTYMÄ*, sitä on käytettävä myös yhdyskäytävälle määritetyn tietolähteen sisällä.

Jos sinut on lisätty yhdyskäytävän sisällä määritellyn tietolähteen **Käyttäjät**-välilehdelle ja jos palvelimen ja tietokannan nimet täsmäävät, näet yhdyskäytävän yhtenä, ajoitetun päivityksen kanssa käytettävänä vaihtoehtona.

![Käyttäjien näyttäminen](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-gateway-enterprise-schedule-refresh.png)

> [!WARNING]
> Jos tietojoukkosi sisältää useita tietolähteitä, jokaisen tietolähteen on oltava lisättynä yhdyskäytävään. Jos yksi tai useampi tietolähde ei ole lisättynä yhdyskäytävään, yhdyskäytävää ei näytetä ajoitetun päivityksen yhteydessä.

## <a name="limitations"></a>Rajoitukset

OAuth-todentamista ei tueta paikallisen tietoyhdyskäytävän kanssa käytettäväksi. OAuth-todentamista vaativia tietolähteitä ei ole mahdollista lisätä. Jos tietojoukon tietolähde edellyttää OAuth-todentamista, yhdyskäytävää ei voi käyttää ajoitetussa päivityksessä.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Paikallisen tietoyhdyskäytävän vianmääritys](/data-integration/gateway/service-gateway-tshoot)
* [Yhdyskäytävien vianmääritys – Power BI](service-gateway-onprem-tshoot.md)

Onko sinulla kysyttävää? Kokeile [Power BI -yhteisöä](https://community.powerbi.com/).
