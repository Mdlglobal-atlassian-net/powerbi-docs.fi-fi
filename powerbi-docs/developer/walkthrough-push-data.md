---
title: Tietojen työntäminen tietojoukkoon
description: Tietojen työntäminen Power BI -tietojoukkoon
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 9eb81610044f795b6f9dc5c58aeefad13de06542
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222149"
---
# <a name="push-data-into-a-power-bi-dataset"></a>Tietojen työntäminen Power BI -tietojoukkoon

Power BI API-avulla voit työntää tietoja Power BI-tietojoukkoon. Tässä artikkelissa esittelemme miten voit lähettää Myyntimarkkinointi-tietojoukon, joka sisältää aiemmin luodun tietojoukon tuote-taulukko.

Ennen aloittamista, sinun Azure Active Directory (Azure AD) ja [Power BI-tilin](create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Vaiheet tietojen työntämiseksi tietojoukkoon

* Vaihe 1: [Rekisteröi sovellus Azure AD:n kanssa ](walkthrough-push-data-register-app-with-azure-ad.md)
* Vaihe 2: [Todennustunnuksen hankkiminen](walkthrough-push-data-get-token.md)
* Vaihe 3: [Tietojoukon luominen Power BI:ssä](walkthrough-push-data-create-dataset.md)
* Vaihe 4: [Tietojoukon hankkiminen rivien lisäämiseksi Power BI -taulukkoon](walkthrough-push-data-get-datasets.md)
* Vaihe 5: [Rivien lisääminen Power BI -taulukkoon](walkthrough-push-data-add-rows.md)

Seuraava osa sisältää yleistä keskustelua Power BI -ohjelmointirajapinnan toiminnoista, joilla tiedot työnnetään.

## <a name="power-bi-api-operations-to-push-data"></a>Power BI -ohjelmointirajapinnan toiminnot tietojen työntämiseksi

Power BI:n REST‑ohjelmointirajapinnan avulla voit työntää tietolähteitä Power BI:hin. Kun sovellus lisää rivejä tietojoukkoon, koontinäytön ruutuihin päivityksen automaattisesti uusia tietoja. Tietojen työntämiseen [Julkaise tietojoukko](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset) ja [Julkaise rivejä](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows) toimintoja. Voit etsiä tietojoukon avulla [Hae tietojoukot](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets) toiminto. Voit välittää ryhmän tunnuksen ja käsitellä missä tahansa näistä toiminnoista ryhmälle. Jos haluat ryhmän tunnus luettelon, käytä [Hae ryhmät](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups) toiminto.

Seuraavassa luetellaan toiminnot, jotka työntävät tietoja tietojoukkoon:

* [Julkaise tietojoukko](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)
* [Hae tietojoukot](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)
* [Julkaise rivit](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows)
* [Hae ryhmät](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups)

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

Myyntimarkkinointi tietojoukon esimerkissä välitetään JSON-merkkijonon, kuten alla. Tässä esimerkissä **Myyntimarkkinointi** on tietojoukon nimi, ja **tuotteen** on taulukkonimi. Kun olet määrittänyt taulukon, voit määrittää taulukkorakennetta. **Myyntimarkkinointi**-tietojoukossa taulukon rakenne sisältää seuraavat sarakkeet: ProductID, Valmistaja, Luokka, Segmentti, Tuote ja IsComplete.

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
| Double |Double.MaxValue- ja Double.MinValue-arvoja ei sallita. NaN ei tueta. komentoja + Infinity ja - Infinity ei tueta tietyissä funktioissa (esimerkiksi Min, Max). |
| Totuusarvo |Ei mitään |
| Päivämäärä ja aika |Tietojen lataaminen, aikana määrällisiksi 1/300 sekunnin (3,33 ms) kerrannaisten päiväosiin arvot. |
| Merkkijono |Tällä hetkellä sallitaan enintään 128 K-merkkiä. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Lisätietoja tietojen työntämisestä Power BI:hin

Aloita tietojen työntäminen tietojoukkoon katsomalla vasemman reunan siirtymisruudusta kohta [Vaihe 1: Sovelluksen Azure AD -rekisteröinti](walkthrough-push-data-register-app-with-azure-ad.md).

[Seuraava vaihe >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Seuraavat vaiheet

[Rekisteröidy Power BI -palveluun](create-an-azure-active-directory-tenant.md)  
[Esittelyssä JSON](http://json.org/)  
[Power BI REST -ohjelmointirajapinnan yleiskatsaus](overview-of-power-bi-rest-api.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)