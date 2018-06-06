---
title: Päivitystilanteiden vianmääritys
description: Päivitystilanteiden vianmääritys
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: d94e25b78edef2aefaa5e63c788e5f11dc948791
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
ms.locfileid: "30975807"
---
# <a name="troubleshooting-refresh-scenarios"></a>Päivitystilanteiden vianmääritys
Täältä löydät eri skenaarioita koskevia tietoja, joita saatat kohdata Power BI -palvelun tietojen päivittämisen yhteydessä.

> [!NOTE]
> Jos kohtaat skenaarion, joka aiheuttaa ongelmia, etkä löydä sitä luettelossa, voit pyytää apua [yhteisösivustolla](http://community.powerbi.com/) tai luoda [tukipalvelupyynnön](https://powerbi.microsoft.com/support/).
> 
> 

## <a name="refresh-using-web-connector-doesnt-work-properly"></a>Päivittäminen käyttämällä verkkoyhdistintä ei toimi oikein
Jos sinulla on verkkoyhdistimen komentosarja, joka käyttää [ **Web.Page** ](https://msdn.microsoft.com/library/mt260924.aspx) -toimintoa ja olet päivittänyt tietojoukkosi tai raportin 18. marraskuuta 2016 jälkeen, sinun on käytettävä yhdyskäytävää, jotta päivitys toimii oikein .

## <a name="unsupported-data-source-for-refresh"></a>Tukemattoman tietolähteen päivitys
Tietojoukkoa määritettäessä saatat saada virheilmoituksen, joka ilmaisee, että tietojoukko käyttää ei-tuettua tietolähdettä päivitystä varten. Lisätietoja saa kohdasta [Tukemattoman tietolähteen vianmääritys päivitystä varten](service-admin-troubleshoot-unsupported-data-source-for-refresh.md)

## <a name="dashboard-doesnt-reflect-changes-after-refresh"></a>Koontinäyttö ei näytä muutokssia päivittämisen jälkeen
Odota noin 10-15 minuuttia, jotta päivitys näkyy koontinäytön ruudulla.  Jos se ei edelleenkään näy, kiinnitä visualisointi koontinäyttöön uudelleen.

## <a name="gatewaynotreachable-when-setting-credentials"></a>GatewayNotReachable tunnistetietoja määritettäessä
Voit saada virheilmoituksen GatewayNotReachable, kun yrität määrittää tietolähteen tunnistetiedot. Tämä saattaa johtua vanhentuneesta yhdyskäytävästä.  Asenna uusin yhdyskäytävä ja yritä uudelleen.

## <a name="processing-error-the-following-system-error-occurred-type-mismatch"></a>Käsittelyvirhe: Seuraava järjestelmävirhe tapahtui: tyypin ristiriita
Tämä voi johtua ongelmasta Power BI Desktop -tiedoston tai Excel-työkirjan M-komentosarjassa.  Se voi myös johtua vanhentuneesta Power BI Desktop -versiosta.

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
Tuotujen tietojoukkojen ajoitettu päivitys aikakatkaistaan kahden tunnin kuluttua. Aikakatkaisu on kasvanut viiteen tuntiin **Premium** -työtilojen tietojoukoissa. Jos tämä raja tulee vastaan, harkitse tietojoukkosi koon tai monimutkaisuuden pienentämistä tai tietojoukon jakamista pienempiin osiin.

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietojen päivittäminen](refresh-data.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
[Power BI -yhdyskäytävän vianmääritys – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

