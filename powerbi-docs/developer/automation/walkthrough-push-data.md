---
title: Tietojen työntäminen tietojoukkoon
description: Tietojen työntäminen Power BI -tietojoukkoon
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: tutorial
ms.date: 05/22/2019
ms.openlocfilehash: 932e458c90b248e01a88d45a849838cff27f6dcb
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79488196"
---
# <a name="push-data-into-a-power-bi-dataset"></a>Tietojen työntäminen Power BI -tietojoukkoon

Power BI -ohjelmointirajapinnan avulla voit työntää tietoja Power BI -tietojoukkoon. Tässä artikkelissa kuvataan, miten voit työntää Tuote-taulukon sisältävän Myyntimarkkinointi-tietojoukon olemassa olevaan tietojoukkoon.

Ennen aloittamista tarvitset Azure Active Directoryn (Azure AD) ja [Power BI -tilin](../embedded/create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Vaiheet tietojen työntämiseksi tietojoukkoon

* Vaihe 1: [Rekisteröi sovellus Azure AD:n kanssa ](../embedded/register-app.md)
* Vaihe 2: [Todennustunnuksen hankkiminen](walkthrough-push-data-get-token.md)
* Vaihe 3: [Tietojoukon luominen Power BI:ssä](walkthrough-push-data-create-dataset.md)
* Vaihe 4: [Tietojoukon hankkiminen rivien lisäämiseksi Power BI -taulukkoon](walkthrough-push-data-get-datasets.md)
* Vaihe 5: [Rivien lisääminen Power BI -taulukkoon](walkthrough-push-data-add-rows.md)

Seuraava osa sisältää yleistä keskustelua Power BI -ohjelmointirajapinnan toiminnoista, joilla tiedot työnnetään.

## <a name="power-bi-api-operations-to-push-data"></a>Power BI -ohjelmointirajapinnan toiminnot tietojen työntämiseksi

Power BI:n REST‑ohjelmointirajapinnan avulla voit työntää tietolähteitä Power BI:hin. Kun sovellus lisää rivejä tietojoukkoon, uudet tiedot päivittyvät automaattisesti koontinäytön ruutuihin. Kun haluat työntää tietoja, käytä [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)- ja [PostRows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows)-toimintoja. Käytä tietojoukon löytämiseen [Hae tietojoukot](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets) -toimintoa. Voit missä tahansa näistä toiminnoista välittää ryhmän tunnuksen ja käsitellä kyseistä ryhmää. Saat luettelon ryhmätunnuksista käyttämällä [Hae ryhmät](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups) -toimintoa.

Seuraavassa luetellaan toiminnot, jotka työntävät tietoja tietojoukkoon:

* [Julkaise tietojoukko](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)
* [Hae tietojoukot](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)
* [Julkaise rivit](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows)
* [Hae ryhmät](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups)

Voit luoda tietojoukon Power BI:ssä välittämällä JavaScript Object Notation (JSON) -merkkijonon Power BI -palveluun. Lisätietoja JSON:stä on artikkelissa [Esittelyssä JSON](https://json.org/).

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

Myyntimarkkinointi-tietojoukon esimerkissä välitetään alla olevaa esimerkkiä vastaava JSON-merkkijono. Tässä esimerkissä **Myyntimarkkinointi** on tietojoukon nimi ja **Tuote** on taulukon nimi. Kun olet määrittänyt taulukon, voit määrittää taulukon rakenteen. **Myyntimarkkinointi**-tietojoukossa taulukon rakenne sisältää seuraavat sarakkeet: ProductID, Valmistaja, Luokka, Segmentti, Tuote ja IsComplete.

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
| Double |Double.MaxValue- ja Double.MinValue-arvoja ei sallita. NaN:ää ei tueta. Komentoja +Infinity ja -Infinity ei tueta tietyissä funktioissa (esimerkiksi Min, Max). |
| Totuusarvo |Ei mitään |
| Päivämäärä ja aika |Tietojen lataamisen aikana arvot muutetaan määrällisiksi 1/300 sekunnin (3,33 ms) kerrannaisten päiväosiin. |
| Merkkijono |Tällä hetkellä sallitaan enintään 128 000 merkkiä. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Lisätietoja tietojen työntämisestä Power BI:hin

Aloita tietojen työntäminen tietojoukkoon katsomalla vasemman reunan siirtymisruudusta kohta [Vaihe 1: Rekisteröi sovelluksen Azure AD:n kanssa](../embedded/register-app.md) siirtymisruudussa.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Rekisteröidy Power BI -palveluun](../embedded/create-an-azure-active-directory-tenant.md)  
* [Esittelyssä JSON](https://json.org/)  
* [Power BI REST -ohjelmointirajapinnan yleiskatsaus](overview-of-power-bi-rest-api.md)  

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)