---
title: Päivitystilanteiden vianmääritys
description: Päivitystilanteiden vianmääritys
author: maggiesMSFT
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 09/13/2019
ms.author: maggies
LocalizationGroup: Data refresh
ms.openlocfilehash: 583d33a1d28fa926bdea41988d651f12de5a8e92
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83309126"
---
# <a name="troubleshooting-refresh-scenarios"></a>Päivitystilanteiden vianmääritys

Täältä löydät eri skenaarioita koskevia tietoja, joita saatat kohdata Power BI -palvelun tietojen päivittämisen yhteydessä.

> [!NOTE]
> Jos kohtaat skenaarion, joka aiheuttaa ongelmia, etkä löydä sitä luettelossa, voit pyytää apua [yhteisösivustolla](https://community.powerbi.com/) tai luoda [tukipalvelupyynnön](https://powerbi.microsoft.com/support/).
>
>

## <a name="email-notifications"></a>Sähköposti-ilmoitukset

Jos olet siirtynyt tähän artikkeliin sähköposti-ilmoituksesta etkä halua enää vastaanottaa päivitysongelmia koskevia sähköpostiviestejä, ota yhteyttä Power BI -järjestelmänvalvojaan. Pyydä häntä poistamaan sähköpostiosoitteesi tai tilaamasi postituslista asianmukaisista Power BI:n tietojoukoista. Järjestelmänvalvoja voi tehdä tämän seuraavan Power BI -hallintaportaalin alueen kautta.

![Sähköposti päivitysilmoituksista](media/refresh-troubleshooting-refresh-scenarios/refresh-email.png)

## <a name="refresh-using-web-connector-doesnt-work-properly"></a>Päivittäminen käyttämällä verkkoyhdistintä ei toimi oikein

Jos sinulla on verkkoyhdistimen komentosarja, joka käyttää [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx) -toimintoa ja olet päivittänyt tietojoukkosi tai raportin 18.11.2016 jälkeen, sinun on käytettävä yhdyskäytävää, jotta päivitys toimii oikein.

## <a name="unsupported-data-source-for-refresh"></a>Tukemattoman tietolähteen päivitys

Tietojoukkoa määritettäessä saatat saada virheilmoituksen, joka ilmaisee, että tietojoukko käyttää ei-tuettua tietolähdettä päivitystä varten. Lisätietoja on kohdassa [Tukemattoman tietolähteen vianmääritys päivitystä varten](service-admin-troubleshoot-unsupported-data-source-for-refresh.md).

## <a name="dashboard-doesnt-reflect-changes-after-refresh"></a>Koontinäyttö ei näytä muutokssia päivittämisen jälkeen

Odota 10–15 minuuttia, jotta päivitys näkyy raporttinäkymän ruudulla. Jos se ei edelleenkään näy, kiinnitä visualisointi koontinäyttöön uudelleen.

## <a name="gatewaynotreachable-when-setting-credentials"></a>GatewayNotReachable tunnistetietoja määritettäessä

Voit saada `GatewayNotReachable`-virheilmoituksen, kun yrität määrittää tietolähteen tunnistetietoja. Tämä saattaa johtua vanhentuneesta yhdyskäytävästä. Asenna uusin yhdyskäytävä ja yritä uudelleen.

## <a name="processing-error-the-following-system-error-occurred-type-mismatch"></a>Käsittelyvirhe: Ilmeni seuraava järjestelmävirhe: Tyyppiristiriita

Tämä voi johtua ongelmasta Power BI Desktop -tiedoston tai Excel-työkirjan M-komentosarjassa. Se voi myös johtua vanhentuneesta Power BI Desktop -versiosta.

## <a name="tile-refresh-errors"></a>Ruudun päivitysvirheet

Katso virheluettelo koontinäytön ruuduilta ja niiden selitykset kohdasta [Ruutuvirheiden vianmääritys](refresh-troubleshooting-tile-errors.md).

## <a name="refresh-fails-when-updating-data-from-sources-that-use-aad-oauth"></a>Päivittäminen ei onnistu, kun päivität tietoja lähteistä, jotka käyttävät AAD OAuth:ia

Azure Active Directorin (**AAD**) OAuth-tunnus, jota monet eri tietolähteet käyttävät, vanhentuu noin tunnin kuluessa. Voit joutua tilanteisiin, joissa tietojen lataaminen kestää kauemmin kuin tunnus on voimassa (enemmän kuin yksi tunti), koska Power BI -palvelu odottaa enintään kaksi tuntia tietojen lataamista. Tällaisessa tilanteessa tietojen lataamisprosessi saattaa epäonnistua ja tunnistetiedoissa on virhe.

Tietolähteet, jotka käyttävät AAD OAuthia, sisältävät **Microsoft Dynamics CRM Onlinen**, **SharePoint Onlinen** (SPO) ja muita. Jos olet muodostamassa yhteyttä tällaisiin tietolähteisiin ja saa tunnistetietojen virheilmoituksen, kun tietojen lataaminen kestää yli tunnin, tämä voi olla syynä.

Microsoft tutkii ratkaisua, joka sallii tietojen lataamisprosessin päivittää tunnuksen ja jatkaa. Jos Dynamics CRM Online- tai SharePoint Online-esiintymän (tai muuhun AAD OAuth-tietolähteeseen) on niin suuri, että se saattaa aiheuttaa kahden tunnin tietojen lataamisen raja-arvon ylityksen, eteen saattaa tulla tietojen lataamisen aikakatkaisu Power BI-palvelusta.

Huomaa myös, että jotta päivitys toimii oikein, kun yhteyttä muodostetaan **SharePoint Online** -tietolähteeseen AAD OAuth avulla, sinun on käytettävä samaa tiliä, jota käytät kirjautuessasi **Power BI -palveluun**.

## <a name="uncompressed-data-limits-for-refresh"></a>Pakkaamattomien tietojen päivitystä koskevat rajoitukset

Tuodun tietojoukon enimmäiskoko **Power BI-palveluun** on 1 Gt. Nämä tietojoukot on vahvasti pakattu suuren suorituskyvyn varmistamiseksi. Lisäksi jaetun kapasiteetin kohdalla palvelu asettaa rajoituksen päivityksen aikana käsiteltävien pakkaamattomien tietojen määrälle, joka on 10 Gt. Tämän raja koskee pakkaamista ja on siksi paljon suurempi kuin 1 Gt. Rajoitukset eivät koske Power BI Premium -tietojoukkoja. Jos Power BI -palvelussa päivitys epäonnistuu tästä syystä, vähennä tuotavien tietojen määrää ja yritä uudelleen.

## <a name="scheduled-refresh-timeout"></a>Ajoitetun päivityksen aikakatkaisu

Tuotujen tietojoukkojen ajoitettu päivitys aikakatkaistaan kahden tunnin kuluttua. Aikakatkaisu on kasvanut viiteen tuntiin **Premium** -työtilojen tietojoukoissa. Jos tämä raja tulee vastaan, harkitse tietojoukon koon tai monimutkaisuuden pienentämistä tai tietojoukon jakamista pienempiin osiin.

## <a name="scheduled-refresh-failures"></a>Ajoitetun päivityksen epäonnistuminen

Jos ajoitettu päivitys epäonnistuu neljä kertaa peräkkäin, Power BI poistaa päivityksen käytöstä. Korjaa ongelman juurisyy ja ota ajoitettu päivitys uudelleen käyttöön.

## <a name="access-to-the-resource-is-forbidden"></a>Resurssin käyttö on kielletty  

Tämä virhe voi johtua välimuistissa olevista vanhentuneista tunnistetiedoista. Tyhjennä internet-selaimen välimuisti kirjautumalla Power BI:hin ja siirtymällä kohtaan `https://app.powerbi.com?alwaysPromptForContentProviderCreds=true`. Tämä pakottaa tunnistetietojen päivityksen.

## <a name="data-refresh-failure-because-of-password-change-or-expired-credentials"></a>Tietojen päivittämisen epäonnistuminen salasanan vaihtamisen tai vanhentuneiden tunnistetietojen vuoksi

Tietojen päivittäminen voi epäonnistua myös vanhentuneiden välimuistissa olevien tunnistetietojen vuoksi. Tyhjennä internet-selaimen välimuisti kirjautumalla Power BI:hin ja siirtymällä kohtaan `https://app.powerbi.com?alwaysPromptForContentProviderCreds=true`. Tämä pakottaa tunnistetietojen päivityksen.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Tietojen päivittäminen Power BI:ssä](refresh-data.md)  
- [Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
- [Power BI -yhdyskäytävän vianmääritys – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Onko sinulla kysyttävää? [Kysy Microsoftin Power BI -yhteisöltä](https://community.powerbi.com/)
