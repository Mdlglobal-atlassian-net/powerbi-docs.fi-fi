---
title: Always Encrypted -toiminto Power BI -raporttipalvelimessa
description: Tässä artikkelissa käsitellään Always Encrypted -toiminnon tukea Power BI -raporttipalvelimessa käytettäessä Microsoft SQL Server- ja Microsoft Azure SQL Database -tietolähdetyyppejä.
author: maggiesMSFT
ms.reviewer: cfinlan
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/22/2020
ms.author: maggies
ms.openlocfilehash: f8d711bba8dc7570f2d470554fd1d971639bbb7b
ms.sourcegitcommit: a1409030a1616027b138128695b80f6843258168
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/24/2020
ms.locfileid: "76710202"
---
# <a name="always-encrypted-in-power-bi-report-server"></a>Always Encrypted -toiminto Power BI -raporttipalvelimessa

Tässä artikkelissa käsitellään Always Encrypted -toiminnon tukea Power BI -raporttipalvelimessa käytettäessä Microsoft SQL Server- ja Microsoft Azure SQL Database -tietolähdetyyppejä. Lisätietoja SQL Serverin Always Encrypted -toiminnosta on artikkelissa [Always Encrypted -toiminto](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine).

## <a name="always-encrypted-user-isolation"></a>Always Encrypted -toiminnon käyttäjän eristys

Tällä hetkellä Power BI -raporttipalvelin ei rajoita raporttien Always Encrypted -sarakkeiden käyttöä, jos käyttäjällä on raportin käyttöoikeus.  Sen vuoksi jos palvelimelle on myönnetty käyttöoikeus sarakkeen salausavaimiin sarakkeen pääavaimella, käyttäjät voivat käyttää sellaisten raporttien kaikkia sarakkeita, joihin heillä on käyttöoikeus.

## <a name="always-encrypted-column-usage"></a>Always Encrypted -sarakkeen käyttö

### <a name="key-storage-strategies"></a>Tärkeimmät tallennusstrategiat

|Tallennus  |Tuetaan  |
|---------|---------|
|Windows-varmennesäilö | Kyllä |
|Azure Key Vault | Ei |
| Cryptography Next Generation (CNG) | Ei |

### <a name="certificate-storage-and-access"></a>Varmenteen tallennus ja käyttö

Tili, joka vaatii varmenteen käyttöoikeutta, on palvelutili. Varmenne on tallennettava paikallisen tietokoneen varmennesäilöön. Lisätietoja:

- [Configure the Report Server Service Account](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager) (Configuration Manager)
- [Making certificates available to applications and users](https://docs.microsoft.com/sql/relational-databases/security/encryption/create-and-store-column-master-keys-always-encrypted#making-certificates-available-to-applications-and-users) -osio SQL Serverin artikkelissa ”Create and store column master keys for Always Encrypted”.

### <a name="column-encryption-strategy"></a>Sarakkeen salausstrategia

Power BI -raporttipalvelimen sarakkeen salausstrategia voi olla *deterministinen* tai *satunnainen*. Seuraavassa taulukossa näytetään erot sen mukaan, mitä strategiaa se käyttää.

|Käytä  |Deterministinen  |Satunnainen  |
|---------|---------|---------|
|Voidaan lukea sellaisenaan kyselyn tuloksissa, esimerkiksi SELECT-lausekkeet. | Kyllä  | Kyllä  |
|Voidaan käyttää Ryhmittelyperuste-entiteettinä kyselyssä. | Kyllä | Ei |
|Voidaan käyttää koostekenttänä, lukuun ottamatta COUNT- ja DISTINCT-lausekkeille. | Ei, lukuun ottamatta COUNT- ja DISTINCT-lausekkeita | Ei |
|Voidaan käyttää raporttiparametrina | Kyllä | Ei |

Lue lisää [deterministisestä salauksesta verrattuna satunnaiseen salaukseen](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine#selecting--deterministic-or-randomized-encryption).

### <a name="parameter-usage"></a>Parametrin käyttö

Parametrin käyttö koskee vain determinististä salausta.

**Yksiarvoinen parametri**.  Voit käyttää yksiarvoista parametria Always Encrypted -sarakkeelle.

**Moniarvoinen parametri**. Et voi käyttää moniarvoista parametria, jossa on useampi kuin yksi arvo, Always Encrypted -sarakkeelle.

**Johdannaisparametrit**. Voit käyttää johdannaisparametreja Always Encrypted -sarakkeen kanssa, jos *kaikki* seuraavat kohdat pitävät paikkansa:

- Kaikkien Always Encrypted -sarakkeiden on oltava Always Encrypted -tilassa deterministisen strategian mukaan.
- Always Encrypted -sarakkeille käytetyt kaikki parametrit ovat yksiarvoisia parametreja.
- Kaikki SQL-vertailut käyttävät Equals (=) -operaattoria.

## <a name="datatype-support"></a>Tietotyypin tuki

| SQL-tietotyyppi | Tukee lukukenttää | Tukee käyttöä Ryhmittelyperuste-elementtinä | Tuetut koosteet (COUNT, DISTINCT, MAX, MIN, SUM jne.) | Tukee suodatusta yhtäläisyyden kautta parametrien avulla | Huomautukset |
| --- | --- | --- | --- | --- | --- |
| int | Kyllä | Kyllä | COUNT, DISTINCT | Kyllä, kokonaislukuna |   |
| liukuluku | Kyllä | Kyllä | COUNT, DISTINCT | Kyllä, liukulukuna |   |
| nvarchar | Kyllä | Kyllä | COUNT, DISTINCT | Kyllä, tekstinä | Deterministisen salauksen on käytettävä sarakelajittelua binary2-lajittelujärjestyksellä merkkisarakkeille. Katso lisätietoja SQL Serverin artikkelista [Always Encrypted -toiminto](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine#selecting--deterministic-or-randomized-encryption).  |
| varchar | Kyllä | Kyllä | COUNT, DISTINCT | Ei |   |
| desimaali | Kyllä | Kyllä | COUNT, DISTINCT | Ei |   |
| numeerinen | Kyllä | Kyllä | COUNT, DISTINCT | Ei |   |
| datetime | Kyllä | Kyllä | COUNT, DISTINCT | Ei |   |
| datetime2 | Kyllä | Kyllä | COUNT, DISTINCT | Kyllä, päivämääränä ja aikana | Tuettu, jos sarakkeella ei ole millisekunnin tarkkuutta (toisin sanoen ei datetime2 (0)) |

## <a name="aggregation-alternatives"></a>Koostevaihtoehdot

Tällä hetkellä ainoat tuetut koosteet deterministisissä Always Encrypted -sarakkeissa ovat koosteita, jotka käyttävät suoraan Equals (=) -operaattoria. Tämä SQL Server -rajoitus johtuu Always Encrypted -sarakkeiden luonteesta. Käyttäjien on koostettava raportissa tietokannassa koostamisen sijaan.

## <a name="always-encrypted-in-connection-strings"></a>Always Encrypted -toiminto yhteysmerkkijonoissa

Always Encrypted -toiminto on otettava käyttöön SQL Server -tietolähteen yhteysmerkkijonossa. Lue lisää [Always Encrypted -toiminnon tuen käyttöönotosta sovelluskyselyissä](https://docs.microsoft.com/sql/relational-databases/security/encryption/develop-using-always-encrypted-with-net-framework-data-provider#enabling-always-encrypted-for-application-queries).

## <a name="next-steps"></a>Seuraavat vaiheet

[Always Encrypted -toiminto](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) SQL Serverissä ja Azure SQL Databasessa

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

