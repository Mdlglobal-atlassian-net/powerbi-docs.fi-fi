---
title: Azure SQL -tietokanta ja DirectQuery
description: Azure SQL -tietokanta ja DirectQuery
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/18/2017
ms.author: maghan
LocalizationGroup: Data from databases
ms.openlocfilehash: 27b2eb90a07d3112b771fd3ee23cc86353a46991
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34242245"
---
# <a name="azure-sql-database-with-directquery"></a>Azure SQL -tietokanta ja DirectQuery
Lue, miten voit muodostaa yhteyden suoraan Azure SQL -tietokantaan ja luoda raportteja, joissa käytetään reaaliaikaisia tietoja. Voit pitää tietosi lähteessä Power BI:n sijaan.

DirectQueryn avulla kyselyt lähetetään takaisin Microsoft Azuren SQL-tietokantaan tarkastellessasi tietoja raporttinäkymässä. Tätä kokemusta ehdotetaan käyttäjille, jotka ovat perehtyneet tietokantoihin ja entiteetteihin, joihin he ovat muodostamassa yhteyttä.

**Huomautukset:**

* Määritä palvelimen täydellinen nimi yhteyttä muodostettaessa (katso lisätietoja alla)
* Varmista, että tietokannan palomuurisääntöjen määrityksenä on ”[Salli Azure-palvelujen käyttö](https://msdn.microsoft.com/library/azure/ee621782.aspx)”
* Jokainen toiminto, kuten sarakkeen valitseminen tai suodattimen lisääminen, lähettää kyselyn takaisin tietokantaan
* Ruudut päivitetään tunnin välein (päivitystä ei tarvitse ajoittaa). Tätä voidaan muokata Lisäasetukset-kohdassa, kun muodostat yhteyden.
* Q&A ei ole käytettävissä DirectQuery-tietojoukoissa
* Rakenteen muutoksia ei poimita automaattisesti

Nämä rajoitukset ja muistiinpanot saattavat muuttua jatkaessamme käyttökokemusten kehittämistä. Yhdistämisen vaiheet on kuvattu alla. 

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop ja DirectQuery
Jotta voit muodostaa yhteyden Microsoft Azuren SQL-tietokantaan DirectQueryä käyttämällä, sinun on käytettävä Power BI Desktopia. Tämä lähestymistapa tarjoaa enemmän joustavuutta ja ominaisuuksia. Power BI Desktopin avulla luodut raportit voidaan sitten julkaista Power BI -palveluun. Saat lisätietoja yhteyden muodostamisesta [Microsoft Azuren SQL-tietokantaan DirectQueryä käyttämällä](desktop-use-directquery.md) Power BI Desktopissa. 

## <a name="single-sign-on"></a>Kertakirjautuminen

Kun julkaiset Azure SQL DirectQuery -tietojoukon palveluun, voit ottaa kertakirjautumisen (SSO) käyttöön Azure Active Directory (Azure AD) OAuth2:n käyttäjillesi. 

Voit ottaa kertakirjautumisen käyttöön siirtymällä tietojoukon asetuksiin, avaamalla **Tietolähteet**-välilehden ja valitsemalla Kertakirjautuminen-valintaruudun.

![Määritä Azure SQL DQ -valintaikkuna](media/service-azure-sql-database-with-direct-connect/sso-dialog.png)

Kun SSO-asetus on käytössä ja käyttäjät käyttävät raportteja, jotka on luotu tietolähteeseen, Power BI lähettää todennetut Azure AD -tunnistetiedot kyselyissä Azure SQL -tietokantaan. Näin Power BI voi noudattaa tietoturva-asetuksia, jotka on määritetty tietolähteen tasolla.

Kertakirjautumisen asetus tulee voimaan kaikissa tietojoukoissa, jotka käyttävät tätä tietolähdettä. Se ei vaikuta tuontitilanteissa käytettyihin todentamismenetelmiin.

## <a name="finding-parameter-values"></a>Parametriarvojen etsiminen
Täydellinen palvelimen nimi ja tietokannan nimi löytyvät Azure-portaalista.

![](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[DirectQueryn käyttö Power BI Desktopissa](desktop-use-directquery.md)  
[Power BI:n käytön aloittaminen](service-get-started.md)  
[Tietojen noutaminen Power BI:hin](service-get-data.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
