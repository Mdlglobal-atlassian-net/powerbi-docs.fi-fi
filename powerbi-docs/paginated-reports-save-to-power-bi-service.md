---
title: Sivutetun raportin julkaiseminen Power BI -palveluun
description: Tässä opetusohjelmassa opit julkaisemaan sivutetun raportin Power BI -palveluun lataamalla sen paikallisesta tietokoneesta.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 11/05/2018
ms.openlocfilehash: 1e5f4a4fda8c6d11ead487ce2891e5c085463b75
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/12/2019
ms.locfileid: "66839612"
---
# <a name="publish-a-paginated-report-to-the-power-bi-service"></a>Sivutetun raportin julkaiseminen Power BI -palveluun

Tässä artikkelissa opit julkaisemaan sivutetun raportin Power BI -palveluun lataamalla sen paikallisesta tietokoneesta. Voit ladata sivutetut raportit omaan työtilaasi tai mihin tahansa muuhun työtilaan niin kauan kuin työtila on Premium-kapasiteetissa. Etsi vinoneliökuvaketta ![Power BI Premium -kapasiteetin vinoneliökuvaketta](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) työtilan nimen vieressä. 

Jos raportin tietolähde on paikallinen, sinun on [luotava yhdyskäytävä](#create-a-gateway) raportin lataamisen jälkeen.

## <a name="add-a-workspace-to-a-premium-capacity"></a>Työtilan lisääminen Premium-kapasiteettiin

Jos työtilassa ei ole vinoneliökuvaketta ![Power BI Premium -kapasiteetin vinoneliökuvaketta](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) nimen vieressä, sinun on lisättävä työtila Premium-kapasiteettiin. 

1. Valitse **Työtilat**, valitse työtilan nimen vierestä kolme pistettä ( **...** ) , ja valitse sitten **Muokkaa työtilaa**.

    ![Valitse Muokkaa työtilaa](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace.png)

1. Laajenna **Muokkaa työtilaa** -valintaikkunassa **Lisäasetukset**-kohtaa ja liu’uta sitten **Varattu kapasiteetti** asentoon **Päällä**.

    ![Valitse Erillinen kapasiteetti](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace-dialog.png)

   Et välttämättä voi muuttaa sitä. Jos et pysty muuttamaan sitä, ota yhteyttä Power BI Premium -kapasiteetin järjestelmänvalvojaan, jotta saat määritysoikeudet työtilan lisäämiseksi Premium-kapasiteettiin.


## <a name="upload-a-paginated-report"></a>Sivutetun raportin lataaminen

1. Luo sivutettu raportti raportin muodostimessa ja tallenna se paikalliseen tietokoneeseen.

1. Avaa Power BI -palvelu selaimessa ja selaa Premium-työtilaan, jossa haluat julkaista raportin. Pane merkille vinoneliökuvake ![Power BI Premium -kapasiteetin vinoneliökuvake](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) nimen vieressä. 

1. Valitse **Nouda tiedot**.

    ![Power BI:n Nouda tiedot](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-get-data.png)

1. Valitse **Tiedostot**-ruudusta **Nouda**.

    ![Power BI:n Nouda tiedostot](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-files-get.png)

1. Valitse **Paikallinen tiedosto** > selaa sivutettuun raporttiin > **Avaa**.

    ![Valitse Paikallinen tiedosto](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-local-file.png)

1. Valitse **Jatka** > **Muokkaa tunnistetietoja**.

    ![Valitse Muokkaa tunnistetietoja.](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-edit-credentials.png)

1. Määritä tunnistetiedot > **Kirjaudu sisään**.

    ![Muokkaa tunnistetietoja](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-credentials.png)

   Näet raportin raporttiluettelossa.

    ![Sivutettu raportti Raportit-luettelossa](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

1. Valitse se Power BI -palvelun avaamiseksi. Jos siinä on parametreja, sinun on valittava ne ennen kuin voit tarkastella raporttia.
 
    ![Valitse parametrit](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

## <a name="create-a-gateway"></a>Luo yhdyskäytävä

Kuten mikä tahansa muu Power BI -raportti, jos raportin tietolähde on paikallinen, sinun on luotava yhdyskäytävä tai yhdistettävä siihen tietojen käyttämiseksi.

1. Valitse raportin nimen vieressä **Hallitse**.

   ![Sivutetun raportin hallinta](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-manage.png)

1. Katso lisätietoja ja seuraavat vaiheet Power BI -palvelun artikkelista [Yhdyskäytävän asentaminen](service-gateway-install.md).

### <a name="gateway-limitations"></a>Yhdyskäytävän rajoitukset

Yhdyskäytävät eivät nykyisin tue moniarvoisia parametrejä.


## <a name="next-steps"></a>Seuraavat vaiheet

- [Sivutetun raportin tarkasteleminen Power BI -palvelussa](paginated-reports-view-power-bi-service.md)
- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)

