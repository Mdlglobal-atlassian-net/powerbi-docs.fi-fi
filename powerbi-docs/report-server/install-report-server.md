---
title: Power BI -raporttipalvelimen asentaminen
description: Opi asentamaan Power BI -raporttipalvelin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 03/19/2018
ms.author: maggies
ms.openlocfilehash: 3efd7da5ef320e08ab620da3c63a6d3ff327396a
ms.sourcegitcommit: 49570ab8f5b5cd5bab4cd388f4281b1372bcb80b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/09/2018
ms.locfileid: "35250380"
---
# <a name="install-power-bi-report-server"></a>Power BI -raporttipalvelimen asentaminen

Opi asentamaan Power BI -raporttipalvelin.

 **Lataa** ![lataa](media/install-report-server/download.png "lataa")

Lataa Power BI -raporttipalvelin tutustumalla ohjeaiheeseen [Paikallinen raportointi Power BI -raporttipalvelimella](https://powerbi.microsoft.com/report-server/). Valitse sitten **Lataa ilmainen kokeiluversio**. 

## <a name="before-you-begin"></a>Alkutoimet
Microsoft suosittelee ennen Power BI -raporttipalvelimen asentamista tutustumaan [Power BI -raporttipalvelimen asentamisen laitteisto- ja ohjelmistovaatimuksiin](system-requirements.md).

### <a name="power-bi-report-server-product-key"></a>Power BI -raporttipalvelimen tuoteavain

#### <a name="power-bi-premium"></a>Power BI Premium
Jos olet ostanut Power BI Premiumin, löydät Power BI -raporttipalvelimen tuoteavaimen Power BI -hallintaportaalin **Premium-asetukset**-välilehdeltä. Tämä on käytettävissä vain Yleisille järjestelmänvalvojille ja käyttäjille, joille on määritetty Power BI -palvelun järjestelmänvalvojan rooli.

![](../media/service-admin-premium-manage/pbirs-product-key.png "Power BI -raporttipalvelimen avain Premium-asetuksissa")

Voit avata tuoteavaimen sisältävän valintaikkunan valitsemalla **Power BI -raporttipalvelimen avain** -kohdan. Voit kopioida avaimen ja käyttää sitä asennuksessa.

![](../media/service-admin-premium-manage/pbirs-product-key-dialog.png "Power BI -raporttipalvelimen tuoteavain")

#### <a name="sql-server-enterprise-software-assurance-sa"></a>SQL Server Enterprise Software Assurance (SA)
Jos sinulla on SQL Server Enterprise SA -sopimus, saat tuoteavaimen [volyymikäyttöoikeuskeskuksesta](https://www.microsoft.com/Licensing/servicecenter/).

## <a name="install-your-report-server"></a>Raporttipalvelimen asentaminen
Power BI -raporttipalvelimen asentaminen on helppoa. Tiedostojen asentaminen onnistuu vain parissa vaiheessa.

SQL Server -tietokantamoduulin palvelimen ei tarvitse olla käytettävissä asennuksen aikana. Palvelin tarvitaan raporttipalvelujen määrittämiseksi asennuksen jälkeen.

1. Paikanna PowerBIReportServer.exe-tiedosto ja käynnistä asennusohjelma.
2. Valitse **Asenna Power BI -raporttipalvelin**.
   
    ![Asenna Power BI -raporttipalvelin](media/install-report-server/pbireportserver-install.png)
3. Valitse asennettava versio ja valitse sitten **Seuraava**.
   
    ![Valitse versio](media/install-report-server/pbireportserver-choose-edition.png)
   
    Voit valita avattavasta luettelosta joko Evaluation- tai Developer-version.
   
    ![](media/install-report-server/pbireportserver-choose-edition2.png)
   
    Muussa tapauksessa voit antaa palvelimen tuoteavaimen, jonka olet saanut joko Power BI -palvelusta tai volyymikäyttöoikeuskeskuksesta. Lisätietoja tuoteavaimen hankkimisesta on [Alkutoimet](#before-you-begin)-osassa.
4. Lue ja hyväksy käyttöoikeussopimuksen ehdot ja valitse sitten **Seuraava**.
   
    ![Käyttöoikeusehdot](media/install-report-server/pbireportserver-eula.png)
5. Tietokantamoduulin on oltava käytettävissä raporttipalvelimen tietokannan tallennusta varten. Valitse **Seuraava** asentaaksesi vain raporttipalvelimen.
   
    ![Asenna vain tiedostot](media/install-report-server/pbireportserver-install-files-only.png)
6. Määritä raporttipalvelimen asennuspaikka. Jatka valitsemalla **Asenna**.
   
    ![Määritä asennuspolku](media/install-report-server/pbireportserver-install-file-path.png)
   
    Oletuspolku on C:\Program Files\Microsoft Power BI Report Server.

1. Onnistuneen määrityksen jälkeen käynnistä Reporting Services Configuration Manager valitsemalla **Määritä raporttipalvelin**.
   
    ![Määritä raporttipalvelin](media/install-report-server/pbireportserver-configure.png)

## <a name="configuring-your-report-server"></a>Raporttipalvelimen määrittäminen

Kun valitset asetuksissa **Määritä raporttipalvelin**, näyttöön tulee Reporting Services Configuration Manager. Lisätietoja on artikkelissa [Reporting Services Configuration Manager](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode).

Sinun on [luotava raporttipalvelintietokanta](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-report-server-create-a-report-server-database) raporttipalvelujen alkumäärityksen viimeistelemiseksi. SQL Server -tietokantapalvelin vaaditaan tämän vaiheen suorittamiseksi.

### <a name="creating-a-database-on-a-different-server"></a>Tietokannan luominen eri palvelimessa
Jos olet luomassa raporttipalvelintietokantaa tietokantapalvelimeen, joka sijaitsee eri tietokoneessa, sinun on muutettava raporttipalvelimen palvelutili tunnistetiedoiksi, jotka tunnistetaan tietokantapalvelimessa. 

Oletusarvon mukaan raporttipalvelin käyttää virtuaalista palvelutiliä. Jos yrität luoda tietokannan eri palvelimessa, näyttöön saattaa tulla seuraava virhe Otetaan yhteysoikeuksia käyttöön -vaiheessa.

`System.Data.SqlClient.SqlException (0x80131904): Windows NT user or group '(null)' not found. Check the name again.`

Voit kiertää virheen muuttamalla palvelutilin joko verkkopalveluksi tai toimialuetiliksi. Palvelutilin muuttaminen verkkopalveluksi ottaa käyttöön raporttipalvelimen tietokonetilin oikeudet.

![Raporttipalvelimen palvelutilin määrittäminen](media/install-report-server/pbireportserver-configure-account.png)

Katso lisätietoja kohdasta [Raporttipalvelimen palvelutilin määrittäminen](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager).

## <a name="windows-service"></a>Windows-palvelu
Windows-palvelu luodaan asennuksen osana. Se näkyy muodossa **Power BI -raporttipalvelin**. Palvelunimi on **PowerBIReportServer**.

![Raporttipalvelimen Windows-palvelu](media/install-report-server/pbireportserver-windows-service.png)

![Raporttipalvelimen Windows-palvelun ominaisuudet](media/install-report-server/pbireportserver-windows-service2.png)

## <a name="default-url-reservations"></a>Oletus-URL-varaukset
URL-varaukset koostuvat etuliitteestä, isäntänimestä, portista ja näennäishakemistosta:

| Osa | Kuvaus |
| --- | --- |
| Etuliite |Oletusarvoinen etuliite on HTTP. Jos olet aiemmin asentanut Secure Sockets Layer (SSL) -varmenteen, asennusohjelma yrittää luoda URL-varaukset, jotka käyttävät HTTPS-etuliitettä. |
| Isäntänimi |Oletusarvoinen isäntänimi on vahva yleismerkki (+). Se määrittää, että raporttipalvelin hyväksyy minkä tahansa HTTP-pyynnön määritetyssä portissa mille tahansa isäntänimelle, joka viittaa tietokoneeseen, mukaan lukien `http://<computername>/reportserver`, `http://localhost/reportserver` tai `http://<IPAddress>/reportserver.` |
| Portti |Oletusportti on 80. Jos käytät mitä tahansa muuta porttia kuin 80, sinun on lisättävä se URL-osoitteeseen eksplisiittisesti, kun avaat verkkoportaalin selainikkunassa. |
| Näennäishakemisto |Oletusarvon mukaan näennäishakemistot luodaan ReportServer-muodossa raporttipalvelimen verkkopalvelua ja verkkoportaalin raportteja varten. Raporttipalvelimen verkkopalvelun oletusarvoinen näennäishakemisto on **reportserver**. Verkkoportaalin oletusarvoinen näennäishakemisto on **reports**. |

Täydellinen URL-merkkijono voi olla esimerkiksi seuraavanlainen:

* `http://+:80/reportserver`, tarjoaa pääsyn raporttipalvelimeen.
* `http://+:80/reports`, tarjoaa pääsyn verkkoportaaliin.

## <a name="firewall"></a>Palomuuri
Jos käytät raporttipalvelinta etäkoneesta, sinun tulee varmistaa, että olet määrittänyt palomuurisäännöt, jos palomuuri on käytössä.

Sinun on avattava TCP-portti, jonka olet määrittänyt verkkopalvelun URL-osoitetta ja verkkoportaalin URL-osoitetta varten. Oletusarvon mukaan näille on määritetty TCP-portti 80.

## <a name="additional-configuration"></a>Lisämääritykset
* Jos haluat lisätietoja Power BI -palvelun integroinnin määrittämisestä, jotta voit kiinnittää raporttikohteita Power BI -raporttinäkymään, katso [Integrointi Power BI -palvelun kanssa](https://docs.microsoft.com/sql/reporting-services/install-windows/power-bi-report-server-integration-configuration-manager).
* Lisätietoja sähköpostin määrittämisestä tilausten käsittelyä varten on kohdissa [Sähköpostiasetukset](https://docs.microsoft.com/sql/reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager) ja [Sähköpostin toimitus raporttipalvelimessa](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services).
* Jos haluat määrittää verkkoportaalin niin, että voit käyttää sitä raporttitietokoneessa raporttien tarkastelua ja hallintaa varten, katso [Palomuurin määrittäminen raporttipalvelimen käyttöä varten](https://docs.microsoft.com/sql/reporting-services/report-server/configure-a-firewall-for-report-server-access) ja [Raporttipalvelimen määrittäminen etähallintaa varten](https://docs.microsoft.com/sql/reporting-services/report-server/configure-a-report-server-for-remote-administration).

## <a name="next-steps"></a>Seuraavat vaiheet
[Järjestelmänvalvojan yleiskatsaus](admin-handbook-overview.md)  
[Raporttipalvelimen tuoteavaimen löytäminen](find-product-key.md)  
[Asenna Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)](install-powerbi-desktop.md)  
[Raporttipalvelujen asennuksen tarkistaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/verify-a-reporting-services-installation)  
[Raporttipalvelimen palvelutilin määrittäminen](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager)  
[Raporttipalvelimen URL-osoitteiden määrittäminen](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager)  
[Raporttipalvelimen tietokantayhteyden määrittäminen](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager)  
[Raporttipalvelimen alustaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-encryption-keys-initialize-a-report-server)  
[Raporttipalvelimen SSL-yhteyksien määrittäminen](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server)  
[Windowsin palvelutilien ja käyttöoikeuksien määrittäminen](https://docs.microsoft.com/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions)  
[Power BI -raporttipalvelimen selaintuki](browser-support.md)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

