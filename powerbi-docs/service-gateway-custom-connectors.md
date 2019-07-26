---
title: Mukautettujen tietoliittimien käyttäminen paikallisen tietoyhdyskäytävän kanssa
description: Voit käyttää mukautettuja tietoliittimiä paikallisen tietoyhdyskäytävän kanssa.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 074a8dd876e0612f87c220f9fb077b60b2b85c88
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271795"
---
# <a name="use-custom-data-connectors-with-the-on-premises-data-gateway"></a>Mukautettujen tietoliittimien käyttäminen paikallisen tietoyhdyskäytävän kanssa

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Power BI:n tietoliittimien avulla voit muodostaa yhteyden sovelluksen, palvelun tai tietolähteen tietoihin ja käyttää niitä sieltä. Voit kehittää mukautettuja tietoliittimiä ja käyttää niitä Power BI Desktopissa.

Löydät [tietoliittimen SDK GitHub -sivulta](http://aka.ms/dataconnectors) lisätietoja siitä, miten voit kehittää Power BI:n mukautettuja tietoliittimiä. Sivustossa on aloitustiedot ja esimerkkejä Power BI:tä ja Power Querya varten.

Kun olet luonut Power BI Desktopissa mukautettuja tietoliittimiä käyttäviä raportteja, voit paikallisen tietoyhdyskäytävän avulla päivittää nämä raportit Power BI -palvelusta.

## <a name="how-to-enable-and-use-this-capability"></a>Tämän ominaisuuden ottaminen käyttöön ja hyödyntäminen

Kun olet asentanut paikallisen tietoyhdyskäytävän heinäkuun 2018 version tai uudemman version, näet paikallisen tietoyhdyskäytävän sovelluksessa **Liittimet**-välilehden ja vaihtoehdon, jonka kautta voit valita kansion mukautettujen liittimien lataamista varten. Varmista, että valitset kansion, jota voidaan käyttää yhdyskäytäväpalvelun avulla (oletusarvoisesti *NT SERVICE\PBIEgwService*). Yhdyskäytävä lataa tässä kansiossa sijaitsevat mukautetun liittimen tiedostot automaattisesti, ja ne näkyvät tietoliittimien luettelossa.

![Mukautettu liitin 1](media/service-gateway-custom-connectors/gateway-onprem-customconnector1.png)

Jos käytät paikallista tietoyhdyskäytävää (henkilökohtainen tila), voit tässä vaiheessa ladata Power BI -raporttisi Power BI -palveluun ja päivittää sen yhdyskäytävän avulla.

Paikallista yhdyskäytävää varten sinun on yhä luotava tietolähde mukautetulle liittimelle. Power BI -palvelun Yhdyskäytävän asetukset -sivulla pitäisi näkyä uusi vaihtoehto, kun valitset yhdyskäytäväklusterin mukautettujen liittimien käytön sallimiseksi tämän klusterin kanssa. Varmista, että klusterin kaikissa yhdyskäytävissä on vuoden 2018 heinäkuun päivitysversio tai uudempi versio, jotta tämä vaihtoehto on saatavilla. Valitse nyt tämä vaihtoehto mukautettujen liittimien käyttöönottamiseksi tämän klusterin kanssa.

![Mukautettu liitin 2](media/service-gateway-custom-connectors/gateway-onprem-customconnector2.png)

Kun tämä vaihtoehto on käytössä, mukautetut liittimet ovat nyt saatavilla tietolähteinä, joita voit luoda tässä yhdyskäytäväklusterissa. Kun olet luonut tietolähteen uuden mukautetun liittimen avulla, voit nyt päivittää Power BI -raportteja käyttämällä mukautettua liitintä Power BI-palvelussa.

![Mukautettu liitin 3](media/service-gateway-custom-connectors/gateway-onprem-customconnector3.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

* Varmista, että taustalla oleva yhdyskäytäväpalvelu pääsee käyttämään luomaasi kansiota. Yleensä et voi käyttää Windows-kansiossa olevia kansioita tai järjestelmäkansioita. Paikallisen tietoyhdyskäytävän sovellus näyttää viestin, jos kansioon ei pääse (tämä ei koske yhdyskäytävän henkilökohtaista versiota)
* Jotta mukautetut liittimet toimisivat paikallisen tietoyhdyskäytävän kanssa, niiden on sovellettava mukautetun liittimen koodin ”Testiyhteys”-osiota. Tätä ei vaadita, kun käytät mukautettuja liittimiä Power BI Desktopin avulla. Voit käyttää tätä varten Desktopin kanssa toimivaa mukautettua liitintä, mutta et yhdyskäytävää. Katso [näistä ohjeista](https://github.com/Microsoft/DataConnectors/blob/master/docs/m-extensions.md#implementing-testconnection-for-gateway-support), miten voit soveltaa Testiyhteys-osiota.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [Tietolähteen hallinta – SAP HANA](service-gateway-enterprise-manage-sap.md)  
* [Tietolähteen hallinta – SQL Server](service-gateway-enterprise-manage-sql.md)  
* [Tietolähteen hallinta – Oracle](service-gateway-onprem-manage-oracle.md)  
* [Tietolähteen hallinta – tuonti ja ajoitettu päivitys](service-gateway-enterprise-manage-scheduled-refresh.md)  

* [Paikallisen tietoyhdyskäytävän välityspalvelinasetusten määrittäminen](/data-integration/gateway/service-gateway-proxy)  
* [Käytä Kerberosta SSO:ta varten (kertakirjautuminen) Power BI:stä paikallisiin tietolähteisiin](service-gateway-sso-kerberos.md)  

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
