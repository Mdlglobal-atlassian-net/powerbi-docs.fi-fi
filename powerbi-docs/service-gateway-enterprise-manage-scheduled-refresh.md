---
title: Tietolähteen hallinta – tuonti ja ajoitettu päivitys
description: Paikallisen yhdyskäytävän ja kyseiseen yhdyskäytävään kuuluvien tietolähteiden hallinta. Tämä artikkeli käsittelee erityisesti tietolähteitä, joita voidaan käyttää tuonnissa ja ajoitetussa päivityksessä.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 8f45fbed0b2c4e5de62f8ef18ee9a552bf05486b
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54293766"
---
# <a name="manage-your-data-source---importscheduled-refresh"></a>Tietolähteen hallinta – tuonti ja ajoitettu päivitys
Kun paikallinen tietoyhdyskäytävä on asennettu, sinun on lisättävä tietolähteitä, joita voidaan käyttää kyseisen yhdyskäytävän kanssa. Tämä artikkeli kuvailee, miten ajoitetussa päivityksessä käytettäviä yhdyskäytäviä ja tietolähteitä käytetään DirectQueryn tai reaaliaikaisen yhteyden sijasta.

## <a name="download-and-install-the-gateway"></a>Lataa ja asenna yhdyskäytävä
Voit ladata yhdyskäytävän Power BI -palvelusta. Valitse **Lataukset** > **Tietoyhdyskäytävä** tai siirry [yhdyskäytävän lataussivulle](https://go.microsoft.com/fwlink/?LinkId=698861).

![](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-download-data-gateway.png)

## <a name="add-a-gateway"></a>Lisää yhdyskäytävä
Lisää yhdyskäytävä valitsemalla [Lataa](https://go.microsoft.com/fwlink/?LinkId=698863) ja asenna yritysyhdyskäytävä ympäristössäsi sijaitsevalle palvelimelle. Kun yhdyskäytävä on asennettu, se näkyy yhdyskäytävälistassa **Hallinnoi yhdyskäytäviä** -kohdassa.

> [!NOTE]
> **Hallinnoi yhdyskäytäviä** -valikkoa ei näytetä, jos et ole yhdenkään yhdyskäytävän järjestelmävalvoja. Pääset järjestelmävalvojaksi jos sinut lisätään sellaiseksi tai jos itse asennat ja määrittelet yhdyskäytävän.
> 
> 

## <a name="remove-a-gateway"></a>Yhdyskäytävän poistaminen
Yhdyskäytävän poistaminen poistaa myös kaikki kyseisen yhdyskäytävän alaiset tietolähteet.  Tämä rikkoo myös kaikki koontinäytöt ja raportit, jotka ovat riippuvaisia kyseisistä tietolähteistä.

1. Valitse hammaspyöräkuvake ![](media/service-gateway-enterprise-manage-scheduled-refresh/pbi_gearicon.png) oikeasta yläkulmasta > **Yhdyskäytävien hallinta**.
2. Yhdyskäytävä > **Poista**
   
   ![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Tietolähteen lisääminen
Voit lisätä tietolähteen joko valitsemalla yhdyskäytävän ja napauttamalla **Lisää tietolähde** -kohtaa tai yhdyskäytävä > **Lisää tietolähde** -valinnasta.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings1.png)

Voit seuraavaksi valita **Tietolähdetyypin** listasta. Kaikkia listattuja tietolähteitä voi käyttää yritysyhdyskäytävän ajoitetussa päivityksessä. Analysis Servicesia, SQL Serveria ja SAP HANA:a voidaan käyttää ajoitetussa päivityksessä tai DirectQueryn/reaaliaikaisen yhteyden kanssa.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings2.png)

Täytä sitten tietolähteen tiedot, mukaan lukien lähteen tiedot sekä tunnistetiedot, joita käytetään kun tietolähteeseen otetaan yhteys.

> [!NOTE]
> Kaikki tietolähteeseen kohdennetut kyselyt suoritetaan näitä tunnistetietoja käyttämällä. Saadaksesi lisätietoja siitä, miten [tunnisteita](service-gateway-onprem.md#credentials) tallennetaan, lue paikallisen yhdyskäytävän pääartikkeli.
> 
> 

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings3-oracle.png)

Napauta **Lisää**-painiketta, kun kaikki kohdat on täytetty.  Voit nyt käyttää tietolähdettä paikallisten tietojen ajoitetussa päivityksessä. *Yhteyden muodostaminen onnistui* -teksti tulee näkyviin, jos yhteys muodostettiin onnistuneesti.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings4.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

### <a name="advanced-settings"></a>Lisäasetukset
Voit määrittää tietolähteellesi tietosuojatason. Tällä hallinnoidaan sitä, miten tietoja voidaan yhdistää. Tätä käytetään vain ajoitetussa päivityksessä. [Lue lisää](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings9.png)

## <a name="remove-a-data-source"></a>Tietolähteen poistaminen
Tietolähteen poistaminen rikkoo kyseisestä tietolähteestä riippuvaiset koontinäytöt tai raportit.  

Poistaaksesi tietolähteen valitse Tietolähde > **Poista**.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings6.png)

## <a name="manage-administrators"></a>Järjestelmävalvojien hallinta
Yhdyskäytävän järjestelmänvalvojat -välilehdellä voit lisätä ja poistaa käyttäjiä, jotka voivat hallinnoida yhdyskäytävää. Tällä hetkellä käyttäjiä voi pelkästään lisätä. Suojausryhmiä ei ole mahdollista lisätä.

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings8.png)

## <a name="manage-users"></a>Käyttäjien hallinta
Tietolähteen käyttäjät -välilehdellä voit lisätä ja poistaa käyttäjiä tai käyttöoikeusryhmiä, jotka voivat käyttää kyseistä tietolähdettä.

> [!NOTE]
> Käyttäjälista hallinnoi pelkästään sitä, kuka pystyy julkaisemaan raportteja. Raportin omistajat voivat luoda koontinäyttöjä tai sisältöpaketteja ja jakaa näitä muille käyttäjille.
> 
> 

![](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings5.png)

## <a name="using-the-data-source-for-scheduled-refresh"></a>Tietolähteen käyttö ajoitetussa päivityksessä
Kun tietolähde on luotu, se on käyttäjien saatavilla joko DirectQuery -yhteyksien tai ajoitetun päivityksen välityksellä.

> [!NOTE]
> Palvelimen ja tietokannan nimien pitää täsmätä paikallisen tietoyhdyskäytävän Power BI Desktopin ja tietolähteen kanssa.
> 
> 

Yhdyskäytävän tietojoukon ja tietolähteen välinen linkki perustuu palvelimen ja tietokannan nimiin. Näiden on täsmättävä. Jos esimerkiksi Power BI Desktopissa palvelimen nimelle annetaan IP-osoite, samaa IP-osoitetta tulee käyttää myös yhdyskäytävän kokoonpanon tietolähteessä. Jos käytät Power BI Desktopissa *PALVELINTA\ ESIINTYMÄÄ* on yhdyskäytävälle määritetyn tietolähteen sisällä käytettävä sitä samaa.

Jos olet listattuna yhdyskäytävässä määritetyn tietolähteen **Käyttäjät** -välilehdellä ja palvelimen sekä tietokannan nimet täsmäävät, yhdyskäytävä näkyy ajoitetussa päivityksessä käytettävissä olevana vaihtoehtona.

![](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-gateway-enterprise-schedule-refresh.png)

> [!WARNING]
> Jos tietojoukkosi sisältää useita tietolähteitä, jokaisen tietolähteen on oltava lisättynä yhdyskäytävään. Jos yksi tai useampi tietolähde ei ole lisättynä yhdyskäytävään, ei yhdyskäytävää näytetä ajoitetun päivityksen yhteydessä.
> 
> 

## <a name="limitations"></a>Rajoitukset
* OAuth-todentamista ei tueta paikallisen tietoyhdyskäytävän kanssa käytettäväksi. OAuth-todentamista vaativia tietolähteitä ei ole mahdollista lisätä. Jos tietojoukon tietolähde vaatii OAuth-todentamisen, ei yhdyskäytävää ole mahdollista käyttää ajoitetussa päivityksessä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)  
[Paikallinen tietoyhdyskäytävä – tarkat tiedot](service-gateway-onprem-indepth.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

