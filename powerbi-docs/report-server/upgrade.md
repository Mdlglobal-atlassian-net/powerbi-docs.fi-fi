---
title: Power BI -raporttipalvelimen päivittäminen
description: Opi päivittämään Power BI -raporttipalvelin.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.custom: ''
ms.date: 09/05/2017
ms.openlocfilehash: 52863ea4bd666547a9c63b3add1d2d9c0626adc7
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/12/2019
ms.locfileid: "66839684"
---
# <a name="upgrade-power-bi-report-server"></a>Power BI -raporttipalvelimen päivittäminen

Opi päivittämään Power BI -raporttipalvelin.

 **Lataa** ![lataa](media/upgrade/download.png "lataa")

Lataa Power BI -raporttipalvelin ja Power BI -raporttipalvelimelle optimoitu Power BI Desktop tutustumalla ohjeaiheeseen [Paikallinen raportointi Power BI -raporttipalvelimella](https://powerbi.microsoft.com/report-server/).

## <a name="before-you-begin"></a>Alkutoimet

Ennen kuin päivität raporttipalvelimen, raporttipalvelin kannattaa varmuuskopioida seuraavien ohjeiden avulla.

### <a name="backing-up-the-encryption-keys"></a>Salausavaimien varmuuskopioiminen

Salausavaimet kannattaa varmuuskopioida, kun määrität raporttipalvelimen asennuksen ensimmäistä kertaa. Avaimet kannattaa varmuuskopioida myös aina silloin, kun muutat palvelutilien käyttäjätietoja tai nimeät tietokoneen uudelleen. Lisätietoja on ohjeaiheessa [Raporttipalvelimen salausavaimien varmuuskopiointi ja palauttaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys).

### <a name="backing-up-the-report-server-databases"></a>Raporttipalvelimen tietokantojen varmuuskopioiminen

Koska raporttipalvelin on tilaton palvelin, kaikki sovellustiedot tallennetaan **reportserver**- ja **reportservertempdb**-tietokantoihin, jotka toimivat SQL Server -tietokantamoduulin esiintymässä. Voit varmuuskopioida **reportserver**- ja **reportservertempdb**-tietokannat käyttämällä jotakin tuetuista tavoista SQL Server -tietokantojen varmuuskopiointiin. Seuraavassa on raporttipalvelintietokannoille tarkoitettuja suosituksia:

* Käytä **reportserver**-tietokannan varmuuskopiointiin täyttä palautusmallia.
* Käytä **reportservertempdb**-tietokannan varmuuskopiointiin yksinkertaista palautusmallia.
* Voit käyttää tietokannoille eri varmuuskopiointiaikatauluja. Ainoa syy **reportservertempdb**-tietokannan varmuuskopiointiin on se, ettei sitä tarvitsisi luoda uudelleen laitteistovirheen ilmetessä. Laitteistovirheen tapauksessa **reportservertempdb**-tietokannan tietoja ei ole välttämätöntä palauttaa, mutta sen taulukkorakenne on tarpeellinen. Jos **reportservertempdb**-tietokanta menetetään, ainoa tapa saada se takaisin on luoda raporttipalvelintietokanta uudelleen. Jos luot **reportservertempdb**-tietokannan uudelleen, sille on annettava sama nimi kuin ensisijaiselle raporttipalvelintietokannalle.

Lisätietoja SQL Server -relaatiotietokantojen varmuuskopioinnista ja palauttamisesta on ohjeaiheessa [SQL Server -tietokantojen varmuuskopiointi ja palauttaminen](https://docs.microsoft.com/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases).

### <a name="backing-up-the-configuration-files"></a>Määritystiedostojen varmuuskopioiminen

Power BI -raporttipalvelin käyttää määritystiedostoja sovellusasetusten tallentamiseen. Varmuuskopioi tiedostot, kun määrität palvelimen ensimmäistä kertaa ja aina silloin, jos otat käyttöön mukautettuja laajennuksia. Varmuuskopioitavia tiedostoja:

* config.json
* RSHostingService.exe.config
* Rsreportserver.config
* Rssvrpolicy.config
* Reportingservicesservice.exe.config
* Web.config raporttipalvelimen ASP.NET-sovelluksille
* ASP.NETin Machine.config

## <a name="upgrade-the-report-server"></a>Raporttipalvelimen päivittäminen

Power BI -raporttipalvelimen päivittäminen on helppoa. Tiedostojen asentaminen onnistuu vain parissa vaiheessa.

1. Paikanna PowerBIReportServer.exe-tiedosto ja käynnistä asennusohjelma.

2. Valitse **Päivitä Power BI -raporttipalvelin**.

    ![Päivitä Power BI -raporttipalvelin](media/upgrade/reportserver-upgrade1.png "Päivitä Power BI -raporttipalvelin")

3. Lue ja hyväksy käyttöoikeussopimuksen ehdot ja valitse sitten **Päivitä**.

    ![Käyttöoikeussopimus](media/upgrade/reportserver-upgrade-eula.png "Käyttöoikeussopimus")

4. Onnistuneen päivityksen jälkeen voit avata raporttipalvelujen kokoonpanon hallinnan valitsemalla **Määritä raporttipalvelin** tai sulkea asennusohjelman valitsemalla **Sulje**.

    ![Määrityksen päivittäminen](media/upgrade/reportserver-upgrade-configure.png)

## <a name="upgrade-power-bi-desktop"></a>Power BI Desktopin päivittäminen

Kun raporttipalvelin on päivitetty, kannattaa varmistaa, että kaikki Power BI -raporttien tekijät päivittävät palvelimen versiota vastaavaan Power BI -raporttipalvelimelle optimoituun Power BI Desktopiin.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Järjestelmänvalvojan yleiskatsaus](admin-handbook-overview.md)  
* [Asenna Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)](install-powerbi-desktop.md)  
* [Raporttipalvelujen asennuksen tarkistaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/verify-a-reporting-services-installation)  
* [Raporttipalvelimen palvelutilin määrittäminen](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager)  
* [Raporttipalvelimen URL-osoitteiden määrittäminen](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager)  
* [Raporttipalvelimen tietokantayhteyden määrittäminen](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager)  
* [Raporttipalvelimen alustaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-encryption-keys-initialize-a-report-server)  
* [Raporttipalvelimen SSL-yhteyksien määrittäminen](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server)  
* [Windowsin palvelutilien ja käyttöoikeuksien määrittäminen](https://docs.microsoft.com/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions)  
* [Power BI -raporttipalvelimen selaintuki](browser-support.md)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)