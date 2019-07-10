---
title: Azure SQL -tietokanta ja DirectQuery
description: Azure SQL -tietokanta ja DirectQuery
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/13/2019
LocalizationGroup: Data from databases
ms.openlocfilehash: 2363b9da3ac46ce9fd49f19a00950a4a3cf23502
ms.sourcegitcommit: 30ee81f8c54fd7e4d47d7e3ffcf0e6c3bb68f6c2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2019
ms.locfileid: "67468130"
---
# <a name="azure-sql-database-with-directquery"></a>Azure SQL -tietokanta ja DirectQuery

Lue, miten voit muodostaa yhteyden suoraan Azure SQL -tietokantaan ja luoda raportteja, joissa käytetään reaaliaikaisia tietoja. Voit pitää tietosi lähteessä Power BI:n sijaan.

DirectQueryn avulla kyselyt lähetetään takaisin Microsoft Azuren SQL-tietokantaan tarkastellessasi tietoja raporttinäkymässä. Tätä kokemusta ehdotetaan käyttäjille, jotka ovat perehtyneet tietokantoihin ja entiteetteihin, joihin he ovat muodostamassa yhteyttä.

**Huomautukset:**

* Määritä palvelimen täydellinen nimi yhteyttä muodostettaessa (katso lisätietoja alla).
* Varmista, että tietokannan palomuurisäännöt on määritetty [sallimaan Azure-palveluiden käyttö](https://msdn.microsoft.com/library/azure/ee621782.aspx).
* Jokainen toiminto, kuten sarakkeen valitseminen tai suodattimen lisääminen, lähettää kyselyn takaisin tietokantaan.
* Ruudut päivitetään tunnin välein (päivitystä ei tarvitse ajoittaa). Voit muokata päivitysväliä lisäasetuksissa, kun muodostat yhteyden.
* Q&A ei ole käytettävissä DirectQuery-tietojoukoissa.
* Rakenteen muutoksia ei poimita automaattisesti.

Nämä rajoitukset ja muistiinpanot saattavat muuttua jatkaessamme käyttökokemusten kehittämistä. Yhdistämisen vaiheet on kuvattu alla.

> [!Important]
> Olemme parantaneet liitettävyyttämme Azure SQL -tietokantaan.  Pystyt parhaiten muodostamaan yhteyden Azure SQL -tietokannan tietolähteeseen Power BI Desktopin avulla.  Kun olet luonut mallin ja raportin, voit julkaista sen Power BI -palvelussa.  Suora yhdistin Azure SQL -tietokannalle Power BI-palvelussa on nyt vanhentunut.

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop ja DirectQuery

Jos haluat muodostaa yhteyden Azure SQL -tietokantaan DirectQueryllä, sinun täytyy käyttää Power BI Desktopia. Tämä lähestymistapa tarjoaa enemmän joustavuutta ja ominaisuuksia. Power BI Desktopin avulla luodut raportit voidaan sitten julkaista Power BI -palveluun. Saat lisätietoja yhteyden muodostamisesta [Microsoft Azuren SQL-tietokantaan DirectQueryä käyttämällä](desktop-use-directquery.md) Power BI Desktopissa.

## <a name="find-parameter-values"></a>Parametriarvojen etsiminen

Voit etsiä täydellisen palvelimen nimen ja tietokannan nimen Azure-portaalista.

![Uusi Azure-portaalin päivitys](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![Azure-portaalin päivitys](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

[!INCLUDE [direct-query-sso](includes/direct-query-sso.md)]

## <a name="next-steps"></a>Seuraavat vaiheet

* [DirectQueryn käyttö Power BI Desktopissa](desktop-use-directquery.md)  
* [Mikä on Power BI?](power-bi-overview.md)  
* [Tietojen noutaminen Power BI:hin](service-get-data.md)  

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
