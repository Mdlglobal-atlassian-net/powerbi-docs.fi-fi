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
ms.openlocfilehash: 8cee670028da828e052d8fe30c594882555c5d53
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770164"
---
# <a name="upgrade-power-bi-report-server"></a>Power BI -raporttipalvelimen päivittäminen

Opi päivittämään Power BI -raporttipalvelin.

 **Lataa** ![lataa](media/upgrade/download.png "lataa")

Lataa Power BI -raporttipalvelin ja Power BI -raporttipalvelimelle optimoitu Power BI Desktop tutustumalla ohjeaiheeseen [Paikallinen raportointi Power BI -raporttipalvelimella](https://powerbi.microsoft.com/report-server/).

## <a name="before-you-begin"></a>Alkutoimet

Ennen kuin päivität raporttipalvelimen, raporttipalvelin kannattaa varmuuskopioida seuraavien ohjeiden avulla.

### <a name="backing-up-the-encryption-keys"></a>Salausavaimien varmuuskopioiminen

Salausavaimien kannattaa varmuuskopioida, kun määrität raporttipalvelimen asennuksen ensimmäistä kertaa. Voit myös Varmuuskopioi avaimet aina, kun muutat palvelutilien käyttäjätietoja tai nimeät tietokoneen uudelleen. Lisätietoja on ohjeaiheessa [Raporttipalvelimen salausavaimien varmuuskopiointi ja palauttaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys).

### <a name="backing-up-the-report-server-databases"></a>Raporttipalvelimen tietokantojen varmuuskopioiminen

Koska raporttipalvelin on tilaton palvelin, kaikki sovellustiedot tallennetaan **reportserver**- ja **reportservertempdb**-tietokantoihin, jotka toimivat SQL Server -tietokantamoduulin esiintymässä. Voit varmuuskopioida **reportserver** ja **reportservertempdb** tietokannat käyttämällä jotakin tuetuista tavoista SQL Server-tietokantojen varmuuskopiointiin. Seuraavassa on raporttipalvelintietokannoille tarkoitettuja suosituksia:

* Täysi palautustila avulla voit varmuuskopioida **reportserver** tietokannan.
* Yksinkertaista palautusmallia käyttävissä varmuuskopioi **reportservertempdb** tietokannan.
* Voit käyttää tietokannoille eri varmuuskopiointiaikatauluja. Ainoa syy varmuuskopioida **reportservertempdb** on luoda uudelleen, jos laitteistovirheen ilmetessä. Laitteistovirheen tapauksessa **reportservertempdb**-tietokannan tietoja ei ole välttämätöntä palauttaa, mutta sen taulukkorakenne on tarpeellinen. Jos **reportservertempdb**-tietokanta menetetään, ainoa tapa saada se takaisin on luoda raporttipalvelintietokanta uudelleen. Jos luot **reportservertempdb**-tietokannan uudelleen, sille on annettava sama nimi kuin ensisijaiselle raporttipalvelintietokannalle.

Lisätietoja SQL Server -relaatiotietokantojen varmuuskopioinnista ja palauttamisesta on ohjeaiheessa [SQL Server -tietokantojen varmuuskopiointi ja palauttaminen](https://docs.microsoft.com/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases).

### <a name="backing-up-the-configuration-files"></a>Määritystiedostojen varmuuskopioiminen

Power BI -raporttipalvelin käyttää määritystiedostoja sovellusasetusten tallentamiseen. Varmuuskopioi tiedostot, kun määrität palvelimen ensimmäistä ja sen jälkeen, kun otat käyttöön mukautettuja laajennuksia. Varmuuskopioitavia tiedostoja:

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

    ![Päivitä Power BI-raporttipalvelin](media/upgrade/reportserver-upgrade1.png "Päivitä Power BI-raporttipalvelin")

3. Lue ja hyväksy käyttöoikeussopimuksen ehdot ja valitse sitten **Päivitä**.

    ![Käyttöoikeussopimuksen](media/upgrade/reportserver-upgrade-eula.png "käyttöoikeussopimuksen")

4. Onnistuneen päivityksen jälkeen voit avata raporttipalvelujen kokoonpanon hallinnan valitsemalla **Määritä raporttipalvelin** tai sulkea asennusohjelman valitsemalla **Sulje**.

    ![Päivitä määritys](media/upgrade/reportserver-upgrade-configure.png)

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