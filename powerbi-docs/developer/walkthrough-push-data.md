---
title: Tietojen työntäminen tietojoukkoon
description: Tietojen työntäminen Power BI -tietojoukkoon
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 01/05/2017
ms.author: maghan
ms.openlocfilehash: 76d07c8384123a303c8801a45ecd05b9e6ed0321
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34289460"
---
# <a name="push-data-into-a-power-bi-dataset"></a>Tietojen työntäminen Power BI -tietojoukkoon
Power BI ‑ohjelmointirajapinnan avulla voit työntää tietoja Power BI -tietojoukkoon. Voit esimerkiksi laajentaa aiemmin luotua liiketoiminnan työnkulkua ja työntää avaintietoja tietojoukkoon. Tässä tapauksessa haluat työntää Tuote-taulukon sisältävän Myyntimarkkinointi-tietojoukon tietojoukkoon.

Tarvitset Azure Active Directoryn (Azure AD) ja [Power BI -tilin](create-an-azure-active-directory-tenant.md) ennen kuin voit aloittaa tietojen työntämisen tietojoukkoon.

## <a name="steps-to-push-data-into-a-dataset"></a>Vaiheet tietojen työntämiseksi tietojoukkoon
* Vaihe 1: [Sovelluksen Azure AD -rekisteröinti](walkthrough-push-data-register-app-with-azure-ad.md)
* Vaihe 2: [Todennustunnuksen hankkiminen](walkthrough-push-data-get-token.md)
* Vaihe 3: [Tietojoukon luominen Power BI:ssä](walkthrough-push-data-create-dataset.md)
* Vaihe 4: [Tietojoukon hankkiminen rivien lisäämiseksi Power BI -taulukkoon](walkthrough-push-data-get-datasets.md)
* Vaihe 5: [Rivien lisääminen Power BI -taulukkoon](walkthrough-push-data-add-rows.md)

Seuraava osa sisältää yleistä keskustelua Power BI -ohjelmointirajapinnan toiminnoista, joilla tiedot työnnetään.

## <a name="power-bi-api-operations-to-push-data"></a>Power BI -ohjelmointirajapinnan toiminnot tietojen työntämiseksi
Power BI:n REST‑ohjelmointirajapinnan avulla voit työntää tietolähteitä Power BI:hin. Kun sovellus lisää rivejä tietojoukkoon, koontinäytön ruudut päivittyvät automaattisesti päivitetyillä tiedoilla. Käytät tietojen työntämiseen [Luo tietojoukko](https://msdn.microsoft.com/library/mt203562.aspx) -toimintoa yhdessä [Lisää rivejä](https://msdn.microsoft.com/library/mt203561.aspx) -toiminnon kanssa. Käytät tietojoukon löytämiseen [Hae tietojoukot](https://msdn.microsoft.com/library/mt203567.aspx) -toimintoa. Voit missä tahansa näistä toiminnoista välittää ryhmän tunnuksen ja käsitellä kyseistä ryhmää. Saat luettelon ryhmätunnuksista käyttämällä [Hae ryhmät](https://msdn.microsoft.com/library/mt243842.aspx) -toimintoa.

Seuraavassa luetellaan toiminnot, jotka työntävät tietoja tietojoukkoon:

* [Luo tietojoukko](https://msdn.microsoft.com/library/mt203562.aspx)
* [Hae tietojoukot](https://msdn.microsoft.com/library/mt203567.aspx)
* [Lisää rivejä](https://msdn.microsoft.com/library/mt203561.aspx)
* [Hae ryhmät](https://msdn.microsoft.com/library/mt243842.aspx)

Voit luoda tietojoukon Power BI:ssä välittämällä JavaScript Object Notation (JSON) -merkkijonon Power BI -palveluun. Lisätietoja JSON:stä on artikkelissa [Esittelyssä JSON](http://json.org/).

Tietojoukon JSON-merkkijonossa noudatetaan seuraavaa muotoilua:

**Power BI -tietojoukko JSON-objekti**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

Näin ollen Myyntimarkkinointi-tietojoukon esimerkissä välitetään alla olevaa esimerkkiä vastaava JSON-merkkijono. Tässä esimerkissä **Myyntimarkkinointi** on tietojoukon nimi ja **Tuote** on taulukon nimi. Kun olet määrittänyt taulukon, voit määrittää taulukon rakenteen. **Myyntimarkkinointi**-tietojoukossa taulukon rakenne sisältää seuraavat sarakkeet: ProductID, Valmistaja, Luokka, Segmentti, Tuote ja IsComplete.

**Esimerkkitietojoukon JSON-objekti**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

Power BI:n taulukon rakenteessa voi käyttää seuraavia tietotyyppejä.

## <a name="power-bi-table-data-types"></a>Power BI:n taulukon tietotyypit
| **Tietotyyppi** | **Rajoitukset** |
| --- | --- |
| Int64 |Int64.MaxValue ja Int64.MinValue eivät ole sallittuja. |
| Double |Double.MaxValue- ja Double.MinValue-arvoja ei sallita. NaN:ää ei tueta. Komentoja +Infinity ja -Infinity ei tueta tietyissä funktioissa (esim. Min, Max). |
| Totuusarvo |Ei mitään |
| Päivämäärä ja aika |Tietojen lataamisen aikana arvot muutetaan määrällisiksi 1/300 sekunnin (3,33 ms) kerrannaisten päiväosiin. |
| Merkkijono |Tällä hetkellä sallitaan enintään 128 000 merkkiä. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Lisätietoja tietojen työntämisestä Power BI:hin
Aloita tietojen työntäminen tietojoukkoon katsomalla vasemman reunan siirtymisruudusta kohta [Vaihe 1: Sovelluksen Azure AD -rekisteröinti](walkthrough-push-data-register-app-with-azure-ad.md).

[Seuraava vaihe >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Seuraavat vaiheet
[Rekisteröidy Power BI:hin](create-an-azure-active-directory-tenant.md)  
[Luo tietojoukko](https://msdn.microsoft.com/library/mt203562.aspx)  
[Hae tietojoukot](https://msdn.microsoft.com/library/mt203567.aspx)  
[Lisää rivejä](https://msdn.microsoft.com/library/mt203561.aspx)  
[Hae ryhmät](https://msdn.microsoft.com/library/mt243842.aspx)  
[Esittelyssä JSON](http://json.org/)  
[Power BI REST -ohjelmointirajapinnan yleiskatsaus](overview-of-power-bi-rest-api.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

