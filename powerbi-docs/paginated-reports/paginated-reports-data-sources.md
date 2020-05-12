---
title: Power BI:n sivutetuissa raporteissa tuetut tietolähteet
description: Tässä artikkelissa kerrotaan Power BI -palvelun sivutetuissa raporteissa tuetuista tietolähteistä ja siitä, miten yhteys muodostaa yhteyden Microsoft Azuren SQL-tietokannan tietolähteisiin.
author: onegoodsausage
ms.author: andremi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 04/28/2020
ms.openlocfilehash: ad75cf6b85a896fbdc275748dc31c620206e08a2
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82692879"
---
# <a name="supported-data-sources-for-power-bi-paginated-reports"></a>Power BI:n sivutetuissa raporteissa tuetut tietolähteet

Artikkelissa kuvataan tarkasti Power BI -palvelun sivutetuissa raporteissa tuetut tietolähteet ja se, miten yhteys muodostaa yhteyden Microsoft Azuren SQL-tietokannan tietolähteisiin. Joitakin tietolähteitä tuetaan suoraan. Voit muodostaa yhteyden muihin tietoyhdyskäytävien kautta.

## <a name="natively-supported-data-sources"></a>Suoraan tuetut tietolähteet

Sivutetut raportit tukevat suoraan seuraavia tietolähteitä:

| Tietolähde | Todentaminen | Huomautukset |
| --- | --- | --- |
| Azuren SQL-tietokanta <br>Azure SQL Data Warehouse | Perus, kertakirjautuminen (SSO), OAuth2 | Voit käyttää Enterprise-yhdyskäytävää Azure SQL-tietokannan kanssa. Et kuitenkaan saa käyttää SSO- tai oAuth2-todennusta näissä tilanteissa.   |
| Azure SQL:n hallittu esiintymä | Perustodennus | Julkisen tai yksityisen päätepisteen kautta (yksityinen päätepiste on reititettävä yritysyhdyskäytävän kautta)  |
| Azure Analysis Services | SSO, OAuth2 | AAS-palomuuri täytyy poistaa käytöstä tai määrittää sallimaan kaikki IP-alueet.|
| Power BI -tietojoukko | SSO | Power BI:n Premium- ja muut kuin Premium-tietojoukot. Edellyttää lukuoikeutta |
| Power BI:n Premium-tietojoukko (XMLA) | SSO |   |
| Anna tiedot | – | Tiedot on upotettu raporttiin. |

Microsoft Azuren SQL-tietokantaa lukuun ottamatta kaikki tietolähteet ovat valmiita käytettäviksi sen jälkeen, kun olet ladannut raportin Power BI -palveluun. Tietolähteet siirtyvät oletusarvoisesti käyttämään kertakirjautumista (SSO), jos se on käytettävissä. Azure Analysis Servicesia varten voit vaihtaa todennustyypiksi OAuth2. Kun tietyn tietolähteen todennustyypiksi vaihdetaan OAuth2, sitä ei voi enää palauttaa kertakirjautumiseen.  Tämä muutos koskee myös kaikkia tätä tietolähdettä kaikissa tietyn vuokraajan työtiloissa käyttäviä raportteja.  Sivutettujen raporttien rivitason suojaus ei toimi, elleivät käyttäjät valitse todennustyypiksi kertakirjautumista.

Microsoft Azuren SQL-tietokannoissa on annettava lisätietoja kohdassa [Microsoft Azuren SQL-tietokannan todentaminen](#azure-sql-database-authentication) kuvatulla tavalla.

## <a name="other-data-sources"></a>Muut tietolähteet

Edellä mainittujen suoraan tuettujen tietolähteiden lisäksi seuraavia tietolähteitä voi käyttää [Power BI -tietoyhdyskäytävän](../service-gateway-onprem.md) kautta:

- SQL Server
- SQL Server Analysis Services
- Oracle
- Teradata

Sivutetuissa raporteissa Microsoft Azuren SQL-tietokantaa ja Azure Analysis Servicesia ei tällä hetkellä voi käyttää Power BI -tietoyhdyskäytävän kautta.

## <a name="azure-sql-database-authentication"></a>Microsoft Azuren SQL-tietokannan todentaminen

Microsoft Azuren SQL-tietokantoja varten todennustyyppi on määritettävä enne raportin suorittamista. Tämä pätee vain silloin, kun käytät tietolähdettä ensimmäistä kertaa työtilassa. Näet ensimmäisellä kerralla seuraavan sanoman:

![Julkaistaan Power BI:hin](media/paginated-reports-data-sources/power-bi-paginated-publishing.png)

Jos et anna tunnistetietoja, raportin suorittamisessa tapahtuu virhe. Valitse **Jatka**, jos haluat siirtyä **Tietolähteen tunnistetiedot** -sivulle juuri lataamassasi raportissa:

![Microsoft Azuren SQL-tietokannan asetukset](media/paginated-reports-data-sources/power-bi-paginated-settings-azure-sql.png)

Valitse minkä tahansa haluamasi tietolähteen **Muokkaa tunnistetietoja** -linkki, jotta saat näkyviin **Määritä**-valintaikkunan:

![Määritä Microsoft Azuren SQL-tietokanta](media/paginated-reports-data-sources/power-bi-paginated-configure-azure-sql.png)

Microsoft Azuren SQL-tietokannan tietolähteissä tuetaan seuraavia todennustyyppejä:

- Perus (käyttäjänimi ja salasana)
- SSO (kertakirjautuminen)
- OAuth2 (tallennettu AAD-tunnus)

Jotta SSO ja OAuth2 toimivat oikein, [AAD-todennuksen tuen on oltava käytössä](https://docs.microsoft.com/azure/sql-database/sql-database-aad-authentication-configure) Microsoft Azuren SQL-tietokantapalvelimessa, johon tietolähde muodostaa yhteyden. OAuth2-todennusmenetelmässä AAD luo tunnuksen ja tallentaa sen tulevaa tietolähteen käyttöä varten. Jos haluat käyttää [SSO-todennustapaa](https://docs.microsoft.com/power-bi/service-azure-sql-database-with-direct-connect#single-sign-on) sen sijaan, valitse sen alapuolella oleva SSO-vaihtoehto, **Käyttäjät käyttävät omia OAuth2-tunnistetietojaan käyttäessään tätä tietolähdettä DirectQueryn kautta**.
  
## <a name="next-steps"></a>Seuraavat vaiheet

[Sivutetun raportin tarkasteleminen Power BI -palvelussa](../consumer/paginated-reports-view-power-bi-service.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
