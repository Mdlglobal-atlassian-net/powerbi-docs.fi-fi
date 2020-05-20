---
title: Sivutetun raportin julkaiseminen Power BI -palveluun
description: Tässä opetusohjelmassa opit julkaisemaan sivutetun raportin Power BI -palveluun lataamalla sen paikallisesta tietokoneesta.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/04/2020
ms.openlocfilehash: 39609d0bf3681de2b01f433143556ac102ee0662
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565479"
---
# <a name="publish-a-paginated-report-to-the-power-bi-service"></a>Sivutetun raportin julkaiseminen Power BI -palveluun

Tässä artikkelissa opit julkaisemaan sivutetun raportin Power BI -palveluun lataamalla sen paikallisesta tietokoneesta. Voit ladata sivutetut raportit omaan työtilaasi tai mihin tahansa muuhun työtilaan niin kauan kuin työtila on Premium-kapasiteetissa. Etsi vinoneliökuvaketta ![Power BI Premium -kapasiteetin vinoneliökuvaketta](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) työtilan nimen vieressä. 

Jos raportin tietolähde on paikallinen, sinun on luotava yhdyskäytävä raportin lataamisen jälkeen. Lisätietoja on tämän artikkelin myöhemmässä [Luo yhdyskäytävä](#create-a-gateway) -osassa.

## <a name="add-a-workspace-to-a-premium-capacity"></a>Työtilan lisääminen Premium-kapasiteettiin

Jos työtilassa ei ole vinoneliökuvaketta ![Power BI Premium -kapasiteetin vinoneliökuvaketta](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) nimen vieressä, sinun on lisättävä työtila Premium-kapasiteettiin. 

1. Valitse **Työtilat**, valitse työtilan nimen vierestä kolme pistettä ( **...** ) , ja valitse sitten **Muokkaa työtilaa**.

    ![Valitse Muokkaa työtilaa](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace.png)

1. Laajenna **Muokkaa työtilaa** -valintaikkunassa **Lisäasetukset**-kohtaa ja liu’uta sitten **Varattu kapasiteetti** asentoon **Päällä**.

    ![Valitse Erillinen kapasiteetti](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace-dialog.png)

   Et välttämättä voi muuttaa sitä. Jos et pysty muuttamaan sitä, ota yhteyttä Power BI Premium -kapasiteetin järjestelmänvalvojaan, jotta saat määritysoikeudet työtilan lisäämiseksi Premium-kapasiteettiin.

## <a name="from-report-builder-publish-a-paginated-report"></a>Julkaise sivutettu raportti raportin muodostimen kautta

1. Luo sivutettu raportti raportin muodostimessa ja tallenna se paikalliseen tietokoneeseen.

1. Valitse raportin muodostimen **Tiedosto**-valikosta **Tallenna nimellä**.

    ![Tiedosto-valikko > Tallenna > Tallenna nimellä](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-save-as.png)

    Jos et ole vielä kirjautunut sisään Power BI:hin, sinun on nyt kirjauduttava sisään tai luotava tili. Valitse raportin muodostimen oikeasta yläkulmasta **Kirjaudu sisään** ja suorita vaiheet.

2. Valitse vasemmalla olevasta työtilojen luettelosta työtila, jonka nimen vieressä on vinoneliökuvake ![Power BI Premium kapasiteetin vinoneliö-kuvake](media/paginated-reports-save-to-power-bi-service/premium-diamond.png). Kirjoita ruutuun **tiedoston nimi** > **Tallenna**. 

    ![Premium-työtilan valitseminen](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-workspace.png)

4. Avaa Power BI -palvelu selaimessa ja selaa Premium-työtilaan, jossa julkaisit sivutetun raportin. Näet raportin **Raportit**-välilehdellä.

    ![Sivutettu raportti Raportit-luettelossa](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

5. Valitse sivutettu raportti avataksesi sen Power BI -palvelussa. Jos siinä on parametreja, sinun on valittava ne ennen kuin voit tarkastella raporttia.

    ![Valitse parametrit](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

6. Jos raportin tietolähde on paikallinen, lue tästä artikkelista, miten voit käyttää tietolähdettä [luomalla yhdyskäytävän](#create-a-gateway).

## <a name="from-the-power-bi-service-upload-a-paginated-report"></a>Lataa sivutettu raportti Power BI -palvelun kautta

Voit myös aloittaa Power BI-palvelusta ja ladata sivutetun raportin.

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

   Näet raportin **Raportit**-välilehdellä.

    ![Sivutettu raportti Raportit-luettelossa](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

1. Valitse se Power BI -palvelun avaamiseksi. Jos siinä on parametreja, sinun on valittava ne ennen kuin voit tarkastella raporttia.
 
    ![Valitse parametrit](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

6. Jos raportin tietolähde on paikallinen, lue tästä artikkelista, miten voit käyttää tietolähdettä [luomalla yhdyskäytävän](#create-a-gateway).

## <a name="create-a-gateway"></a>Luo yhdyskäytävä

Kuten mikä tahansa muu Power BI -raportti, jos raportin tietolähde on paikallinen, sinun on luotava yhdyskäytävä tai yhdistettävä siihen tietojen käyttämiseksi.

1. Valitse raportin nimen vieressä **Hallitse**.

   ![Sivutetun raportin hallinta](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-manage.png)

1. Katso lisätietoja ja seuraavat vaiheet Power BI -palvelun artikkelista [Mikä paikallinen tietoyhdyskäytävä on](../connect-data/service-gateway-onprem.md).



## <a name="next-steps"></a>Seuraavat vaiheet

- [Sivutetun raportin tarkasteleminen Power BI -palvelussa](../consumer/paginated-reports-view-power-bi-service.md)
- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
- [Opetusohjelma: Power BI:n sivutetun raportin upottaminen sovellukseen asiakkaitasi varten ](../developer/embedded/embed-paginated-reports-customers.md)
