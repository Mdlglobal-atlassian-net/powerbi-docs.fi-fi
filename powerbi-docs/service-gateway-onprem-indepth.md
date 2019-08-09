---
title: Paikallinen tietoyhdyskäytävä tarkemmin
description: Tässä artikkelissa tarkastellaan paikallista yhdyskäytävää tarkemmin. Artikkelissa kerrotaan, miten palvelu toimii Azure Active Directoryn ja paikallisen Active Directoryn kanssa Analysis Servicesiä käytettäessä.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 7d6948f7b5be25b7027a4aa2adaf244a2cde836a
ms.sourcegitcommit: 73228d0a9038b8369369c059ad06168d2c5ff062
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/02/2019
ms.locfileid: "68729957"
---
# <a name="on-premises-data-gateway-in-depth"></a>Paikallinen tietoyhdyskäytävä tarkemmin

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Tiedot on siirretty tästä artikkelista useisiin Power BI:tä käsitteleviin artikkeleihin ja yleisiin asiakirjoihin. Löydät aiheeseen liittyvän sisällön seuraamalla kunkin otsikon alla olevia linkkejä.

## <a name="how-the-gateway-works"></a>Yhdyskäytävän toiminta

Katso [Paikallisen tietoyhdyskäytävän arkkitehtuuri](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="list-of-available-data-source-types"></a>Luettelo käytettävissä olevista tietolähdetyypeistä

Katso [Tietolähteiden hallinta](service-gateway-data-sources.md).

## <a name="authentication-to-on-premises-data-sources"></a>Todentaminen – paikalliset tietolähteet

Katso [Todentaminen – paikalliset tietolähteet](/data-integration/gateway/service-gateway-onprem-indepth#authentication-to-on-premises-data-sources).

## <a name="authentication-to-a-live-analysis-services-data-source"></a>Todentaminen – reaaliaikainen Analysis Services -tietolähde

Katso [Todentaminen – reaaliaikainen Analysis Services -tietolähde](service-gateway-enterprise-manage-ssas.md#authentication-to-a-live-analysis-services-data-source).

## <a name="role-based-security"></a>Roolipohjainen suojaus

Katso [Roolipohjainen suojaus](service-gateway-enterprise-manage-ssas.md#role-based-security).

## <a name="row-level-security"></a>Rivitason suojaus

Katso [Rivitason suojaus](service-gateway-enterprise-manage-ssas.md#row-level-security).

## <a name="what-about-azure-active-directory"></a>Entä Azure Active Directory?

Katso [Azure Active Directory](/data-integration/gateway/service-gateway-onprem-indepth#azure-active-directory).

## <a name="how-do-i-tell-what-my-upn-is"></a>Mistä tiedän, mikä täydellinen käyttäjätunnukseni on?

Katso [Mistä tiedän, mikä täydellinen käyttäjätunnukseni on?](/data-integration/gateway/service-gateway-onprem-indepth#how-do-i-tell-what-my-upn-is).

## <a name="map-user-names-for-analysis-services-data-sources"></a>Käyttäjänimien yhdistäminen Analysis Services -tietolähteitä varten

Katso ohjeaihe [Käyttäjänimien yhdistäminen Analysis Services -tietolähteitä varten](service-gateway-enterprise-manage-ssas.md#map-user-names-for-analysis-services-data-sources).

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Paikallisen Active Directoryn synkronoiminen Azure Active Directoryn kanssa

Katso [Paikallisen Active Directoryn synkronoiminen Azure Active Directoryn kanssa](/data-integration/gateway/service-gateway-onprem-indepth#synchronize-an-on-premises-active-directory-with-azure-active-directory).

## <a name="what-to-do-next"></a>Mitä seuraavaksi?

Lue tietolähteitä käsittelevät artikkelit:

[Tietolähteiden hallinta](service-gateway-data-sources.md)
[Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Tietolähteen hallinta – SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Tietolähteen hallinta – SQL Server](service-gateway-enterprise-manage-sql.md)  
[Tietolähteen hallinta – Oracle](service-gateway-onprem-manage-oracle.md)  
[Tietolähteen hallinta – tuonti ja ajoitettu päivitys](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>Mahdolliset ongelmakohdat

Katso [Paikallisen tietoyhdyskäytävän vianmääritys](/data-integration/gateway/service-gateway-tshoot) ja [Yhdyskäytävien vianmääritys – Power BI](service-gateway-onprem-tshoot.md).

## <a name="sign-in-account"></a>Kirjautumistili

Katso [Kirjautumistili](/data-integration/gateway/service-gateway-onprem-indepth#sign-in-account).

## <a name="windows-service-account"></a>Windows-palvelutili

Katso [Paikallisen tietoyhdyskäytävän palvelutilin muuttaminen](/data-integration/gateway/service-gateway-service-account).

## <a name="ports"></a>Portit

Katso [Portit](/data-integration/gateway/service-gateway-communication#ports).

## <a name="forcing-https-communication-with-azure-service-bus"></a>HTTPS-tiedonsiirron pakottaminen Azuren palveluväylän kanssa

Katso [HTTPS-tiedonsiirron pakottaminen Azuren palveluväylän kanssa](/data-integration/gateway/service-gateway-communication#force-https-communication-with-azure-service-bus).

## <a name="support-for-tls-12"></a>TLS 1.2:n tuki

Katso [TLS 1.2 yhdyskäytäväliikennettä varten](/data-integration/gateway/service-gateway-communication#tls-12-for-gateway-traffic).

## <a name="how-to-restart-the-gateway"></a>Yhdyskäytävän uudelleenkäynnistys

Katso [Yhdyskäytävän käynnistäminen uudelleen](/data-integration/gateway/service-gateway-restart).

## <a name="next-steps"></a>Seuraavat vaiheet

[Mikä on paikallinen tietoyhdyskäytävä?](service-gateway-onprem.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)