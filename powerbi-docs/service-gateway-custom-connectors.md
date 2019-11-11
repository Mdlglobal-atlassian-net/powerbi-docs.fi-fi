---
title: Mukautettujen tietoliittimien käyttäminen paikallisen tietoyhdyskäytävän kanssa
description: Voit käyttää mukautettuja tietoliittimiä paikallisen tietoyhdyskäytävän kanssa.
author: mgblythe
ms.author: mblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: c76c8fdb635db7724ffeb1a5140e9095c9b2eff5
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73881758"
---
# <a name="use-custom-data-connectors-with-the-on-premises-data-gateway"></a>Mukautettujen tietoliittimien käyttäminen paikallisen tietoyhdyskäytävän kanssa

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Power BI:n tietoliittimien avulla voit muodostaa yhteyden sovelluksen, palvelun tai tietolähteen tietoihin ja käyttää niitä sieltä. Voit kehittää mukautettuja tietoliittimiä ja käyttää niitä Power BI Desktopissa.

Löydät [tietoliittimen SDK GitHub -sivulta](https://aka.ms/dataconnectors) lisätietoja siitä, miten voit kehittää Power BI:n mukautettuja tietoliittimiä. Sivustossa on aloitustiedot ja esimerkkejä Power BI:tä ja Power Querya varten.

Kun olet luonut Power BI Desktopissa mukautettuja tietoliittimiä käyttäviä raportteja, voit paikallisen tietoyhdyskäytävän avulla päivittää nämä raportit Power BI -palvelusta.

## <a name="enable-and-use-this-capability"></a>Tämän ominaisuuden ottaminen käyttöön ja hyödyntäminen

Kun olet asentanut paikallisen tietoyhdyskäytävän heinäkuun 2018 version tai uudemman version, näet paikallisen tietoyhdyskäytävän sovelluksessa **Liittimet**-välilehden ja vaihtoehdon. Valitse **Lataa mukautetut tieto liittimet kansiosta kansio** -ruudusta kansio, jota yhdyskäytäväpalvelua käyttävä käyttäjä voi käyttää. Oletuskäyttäjä on *NT SERVICE\PBIEgwService.* Yhdyskäytävä lataa automaattisesti kyseisessä kansiossa sijaitsevat mukautetut kytkentätiedostot. Ne näkyvät tietoliittimien luettelossa.

![Mukautetut tietoliittimet](media/service-gateway-custom-connectors/gateway-onprem-customconnector1.png)

Jos käytät paikallista tietoyhdyskäytävää (henkilökohtainen tila), voit ladata Power BI -raporttisi Power BI -palveluun ja päivittää sen yhdyskäytävän avulla.

Paikallista yhdyskäytävää varten sinun on luotava tietolähde mukautetulle liittimelle. Power BI -palvelun Yhdyskäytävän asetukset -sivulla pitäisi näkyä vaihtoehto, kun valitset yhdyskäytäväklusterin mukautettujen liittimien käytön sallimiseksi tämän klusterin kanssa. Varmista, että klusterin kaikissa yhdyskäytävissä on vuoden 2018 heinäkuun päivitysversio tai uudempi versio, jotta tämä vaihtoehto on saatavilla. Valitse tämä vaihtoehto mukautettujen liittimien käyttöönottamiseksi tämän klusterin kanssa.

![Yhdyskäytäväklusterin asetukset -sivu](media/service-gateway-custom-connectors/gateway-onprem-customconnector2.png)

Kun tämä vaihtoehto on käytössä, mukautetut liittimet ovat saatavilla tietolähteinä, joita voit luoda tässä yhdyskäytäväklusterissa. Kun olet luonut tietolähteen, joka käyttää uutta mukautettua liitintä, voit päivittää Power BI -raportteja käyttämällä mukautettua liitintä Power BI -palvelussa.

![Tietolähdeasetukset-sivu](media/service-gateway-custom-connectors/gateway-onprem-customconnector3.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

* Varmista, että taustalla oleva yhdyskäytäväpalvelu pääsee käyttämään luomaasi kansiota. Yleensä et voi käyttää Windows-kansiossa olevia kansioita tai järjestelmäkansioita. Paikallinen tietoyhdyskäytävä -sovellus tuo näyttöön sanoman, jos kansio ei ole käytettävissä. Tämä ohje ei koske paikallista tietoyhdyskäytävää (henkilökohtainen tila).
* Jotta mukautetut liittimet toimisivat paikallisen tietoyhdyskäytävän kanssa, niiden on sovellettava mukautetun liittimen koodin ”Testiyhteys”-osiota. Tätä osiota ei vaadita, kun käytät mukautettuja liittimiä Power BI Desktopin avulla. Tästä syystä voit käyttää tätä varten Desktopin kanssa toimivaa mukautettua liitintä, mutta et yhdyskäytävää. Katso [näistä ohjeista](https://github.com/Microsoft/DataConnectors/blob/master/docs/m-extensions.md#implementing-testconnection-for-gateway-support), miten voit ottaa käyttöön Testiyhteys-osion.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [Tietolähteen hallinta – SAP HANA](service-gateway-enterprise-manage-sap.md)  
* [Tietolähteen hallinta – SQL Server](service-gateway-enterprise-manage-sql.md)  
* [Tietolähteen hallinta – Oracle](service-gateway-onprem-manage-oracle.md)  
* [Tietolähteen hallinta – tuonti ja ajoitettu päivitys](service-gateway-enterprise-manage-scheduled-refresh.md)
* [Paikallisen tietoyhdyskäytävän välityspalvelinasetusten määrittäminen](/data-integration/gateway/service-gateway-proxy)
* [Kerberoksen käyttäminen kertakirjautumista (SSO) varten Power BI:stä paikallisiin tietolähteisiin](service-gateway-sso-kerberos.md)  

Onko sinulla kysyttävää? Voit esittää kysymyksiä [Power BI -yhteisössä](https://community.powerbi.com/).
