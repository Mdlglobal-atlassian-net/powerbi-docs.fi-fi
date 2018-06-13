---
title: Paikallinen tietoyhdyskäytävä
description: Tämä on yleiskatsaus paikallisesta tietoyhdyskäytävästä Power BI:lle. Voit käyttää tätä yhdyskäytävää DirectQueryn tietolähteiden kanssa. Voit käyttää myös tätä yhdyskäytävää päivittämään pilvipalvelun tietojoukkoja paikallisten tietojen kanssa.
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 03/26/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: c6c924095e3aaf4839f1c9422e027ba5373b9ad4
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/08/2018
ms.locfileid: "30977052"
---
# <a name="on-premises-data-gateway"></a>Paikallinen tietoyhdyskäytävä
Paikallinen tietoyhdyskäytävä toimii siltana tarjoten nopean ja turvallisen tiedonsiirron paikallisten tietojen (eli tietojen, jotka eivät sijaitse pilvipalvelussa) ja Power BI-, Microsoft Flow-, Logic Apps- ja PowerApps-palveluiden välillä.

Voit käyttää yhtä yhdyskäytävää eri palveluiden kanssa samaan aikaan. Jos käytössäsi on Power BI sekä PowerApps, yhtä yhdyskäytävää voi käyttää molempiin. Se on riippuvainen tilistä, jolle olet kirjautunut sisään.

> [!NOTE]
> Paikallinen tietoyhdyskäytävä toteuttaa tietojen pakkaamisen ja siirron aikaisen salauksen kaikissa tiloissa.
> 
> 

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-requirements-include.md)]

### <a name="limitations-of-analysis-services-live-connections"></a>Reaaliaikaisten Analysis Services -yhteyksien rajoitukset
Voit käyttää reaaliaikaista yhteyttä taulukkomuotoisiin tai moniulotteisiin esiintymiin.

| **Palvelinversio** | **Pakollinen SKU** |
| --- | --- |
| 2012 SP1 CU4 tai uudempi versio |Business Intelligence- ja Enterprise SKU |
| 2014 |Business Intelligence- ja Enterprise SKU |
| 2016 |Standard SKU tai uudempi versio |

* Solutason muotoilu- ja käännösominaisuuksia ei tueta.
* Toiminnot ja Nimetyt joukot eivät näy Power BI:ssä, mutta voit silti muodostaa yhteyden monidimensiollisiin kuutioihin, jotka sisältävät myös toimintoja ja nimettyjä joukkoja ja luoda visualisointeja ja raportteja.

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="download-and-install-the-on-premises-data-gateway"></a>Paikallisen tietoyhdyskäytävänlataaminen ja asentaminen
Jos haluat ladata yhdyskäytävän, valitse **Tietoyhdyskäytävä**-vaihtoehdon Lataukset-valikossa. Lataa [paikallinen tietoyhdyskäytävä](http://go.microsoft.com/fwlink/?LinkID=820925).

![](media/service-gateway-onprem/powerbi-download-data-gateway.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-install-include](./includes/gateway-onprem-install-include.md)]

## <a name="install-the-gateway-in-personal-mode"></a>Asenna yhdyskäytävä henkilökohtaisessa tilassa
> [!NOTE]
> Henkilökohtainen toimii vain Power BI:n kanssa.
> 
> 

Kun henkilökohtainen yhdyskäytävä on asennettu, sinun on käynnistettävä **Power BI:n henkilökohtaisen yhdyskäytävän ohjattu määritys**.

![](media/service-gateway-onprem/personal-gateway-launch-configuration.png)

Sitten on kirjauduttava Power BI:hin rekisteröimään yhdyskäytävä pilvipalvelussa.

![](media/service-gateway-onprem/personal-gateway-signin.png)

Tarvitset myös Windows-käyttäjänimen ja salasanan, joilla Windows-palvelu suoritetaan. Voit määrittää myös oman Windows-tilin. Yhdyskäytäväpalvelu suoritetaan käyttäen tätä tiliä.

![](media/service-gateway-onprem/personal-gateway-windows-service.png)

Kun asennus on valmis, siirry Power BI:n sisällä oleviin tietojoukkoihin ja varmista, että tunnistetiedot syötetään paikalliselle tietolähteelle.

<a name="credentials"></a>

## <a name="storing-encrypted-credentials-in-the-cloud"></a>Salattu tunnistetietojen tallentaminen pilvipalveluun
Kun lisäät tietolähteen yhdyskäytävään, sinun on annettava tunnistetiedot kyseiselle tietolähteelle. Kaikki tietolähteeseen kohdennetut kyselyt suoritetaan näitä tunnistetietoja käyttämällä. Tunnistetiedot salataan turvallisesti käyttäen epäsymmetristä salausta niin, että niitä ei voi salata pilvipalvelussa, ennen kuin ne on tallennettu pilvipalveluun. Tunnistetiedot lähetetään tietokoneelle, jossa yhdyskäytävä on käynnissä paikallisesti, jossa tietojen salaus puretaan käytettäessä tietolähteitä.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

<!-- How the gateway works -->
[!INCLUDE [gateway-onprem-how-it-works-include](./includes/gateway-onprem-how-it-works-include.md)]

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat seikat
* [Azure Information Protection](https://docs.microsoft.com/en-us/microsoft-365/enterprise/protect-files-with-aip
) -toimintoa ei tueta tällä hetkellä
* [Access Online](https://products.office.com/en-us/access) ei tueta tällä hetkellä

## <a name="troubleshooting"></a>Vianmääritys
Jos sinulla on ongelmia, kun asennat tai määrität yhdyskäytävää, varmista, että luet kohdan [Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md). Jos epäilet, että sinulla on ongelma palomuurin kanssa, katso [palomuuria tai välityspalvelinta](service-gateway-onprem-tshoot.md#firewall-or-proxy) koskeva osa vianmääritysartikkelista.

Jos sinulla on välityspalvelimeen liittyviä ongelmia yhdyskäytävän kanssa, katso [Power BI-yhdyskäytävien välityspalvelinasetusten määrittäminen](service-gateway-proxy.md).

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Tietolähteen hallinta – SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Tietolähteen hallinta – SQL Server](service-gateway-enterprise-manage-sql.md)  
[Tietolähteen hallinta – Oracle](service-gateway-onprem-manage-oracle.md)  
[Tietolähteen hallinta – tuonti ja ajoitettu päivitys](service-gateway-enterprise-manage-scheduled-refresh.md)  
[Paikallinen tietoyhdyskäytävä tarkemmin](service-gateway-onprem-indepth.md)  
[Paikallinen tietoyhdyskäytävä (henkilökohtainen tila) – henkilökohtaisen yhdyskäytävän uusi versio](service-gateway-personal-mode.md)
[Välityspalvelinasetusten määrittäminen paikallisten tietojen yhdyskäytäville](service-gateway-proxy.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
