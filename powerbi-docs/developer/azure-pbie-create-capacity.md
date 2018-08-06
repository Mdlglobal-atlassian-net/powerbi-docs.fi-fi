---
title: Power BI Embedded -kapasiteetin luominen Azure-portaalissa | Microsoft Docs
description: Tässä artikkelissa esitellään, miten voit luoda Power BI Embedded -kapasiteetin Microsoft Azuressa.
author: markingmyname
manager: kfile
ms.author: maghan
ms.service: power-bi-embedded
ms.component: ''
ms.devlang: csharp, javascript
ms.topic: conceptual
ms.reviewer: ''
ms.date: 07/31/2018
ms.openlocfilehash: 222a6368bc717880fee4f6ce6958455959b491bd
ms.sourcegitcommit: fecea174721d0eb4e1927c1116d2604a822e4090
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/31/2018
ms.locfileid: "39360295"
---
# <a name="create-power-bi-embedded-capacity-in-the-azure-portal"></a>Power BI Embedded -kapasiteetin luominen Azure-portaalissa

Tässä artikkelissa esitellään, miten voit luoda Power BI Embedded -kapasiteetin Microsoft Azuressa. Power BI Embedded yksinkertaistaa Power BI -ominaisuuksia auttamalla sinua lisäämään upeita visualisointeja, raportteja ja koontinäyttöjä sovelluksiisi nopeasti.

Jos sinulla ei ole Azure-tilausta, luo [ilmainen tili](https://azure.microsoft.com/free/) ennen aloittamista.

> [!VIDEO https://www.youtube.com/embed/aXrvFfg_iSk]

## <a name="before-you-begin"></a>Alkutoimet

Tarvitset tämän pikaoppaan suorittamiseen seuraavat asiat:

* **Azure-tilaus:** Kohdassa [Azuren ilmainen kokeiluversio](https://azure.microsoft.com/free/) voit luoda tilin.
* **Azure Active Directory:** Tilaukseesi on liityttävä Azure Active Directory (AAD) -vuokraaja. Lisäksi ***sinun on kirjauduttava sisään Azureen tilillä kyseisessä vuokraajassa***. Microsoft-tilejä ei tueta. Lisätietoja on kohdassa [Todentaminen ja käyttäjien käyttöoikeudet](https://docs.microsoft.com/azure/analysis-services/analysis-services-manage-users).
* **Power BI -vuokraaja:** Vähintään yhden tilin AAD-vuokraajassa on oltava rekisteröinyt Power BI:hin.
* **Resurssiryhmä:** Käytä olemassa olevaa resurssiryhmää tai [luo uusi](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).

## <a name="create-a-capacity"></a>Kapasiteetin luominen

1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com/).

2. Valitse **Luo resurssi** > **Tiedot ja analytiikka**.

3. Kirjoita hakuruutuun *Power BI Embedded*.

4. Valitse Power BI Embeddedissä **Luo**.

5. Täytä tarvittavat tiedot ja valitse sitten **Luo**.

    ![Täytettävät kentät uuden kapasiteetin luomista varten](media/azure-pbie-create-capacity/azure-portal-create-power-bi-embedded.png)

    |Asetus |Kuvaus |
    |---------|---------|
    |**Resurssin nimi**|Kapasiteetin yksilöivä nimi. Resurssin nimi näkyy Power BI -hallintaportaalissa Azure-portaalin lisäksi.|
    |**Tilaus**|Tilaus, jota vastaan haluat luoda kapasiteetin.|
    |**Resurssiryhmä**|Resurssiryhmä, joka sisältää tämän uuden kapasiteetin. Valitse olemassa olevasta resurssiryhmästä tai luo toinen ryhmä. Saat lisätietoja tutustumalla [Azure Resource Managerin yleiskatsaukseen](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).|
    |**Power BI -kapasiteetin järjestelmänvalvoja**|Power BI -kapasiteetin järjestelmänvalvojat voivat tarkastella kapasiteettia Power BI -hallintaportaalissa ja antaa määrityskäyttöoikeuksia muille käyttäjille. Oletusarvoisesti kapasiteetin järjestelmänvalvoja on tilisi. Kapasiteetin järjestelmänvalvojan on oltava Power BI -vuokraajassa.|
    |**Sijainti**|Sijainti, jossa Power BI sijaitsee vuokraajaasi varten. Tämä asetus on ratkaistu automaattisesti eikä eri sijaintia voi valita.|
    |**Hinnoittelutaso**|Valitse SKU (näennäisytimien määrä ja muistin koko), joka vastaa tarpeitasi.  Lisätietoja on kohdassa [Power BI Embedded -hinnoittelu](https://azure.microsoft.com/pricing/details/power-bi-embedded/)|

6. Valitse **Luo**.

Luonti kestää yleensä alle minuutin, usein vain muutamia sekunteja. Jos valitset **Kiinnitä koontinäyttöön**, voit siirtyä koontinäyttöön ja tarkastella uutta kapasiteettiasi. Vaihtoehtoisesti voit siirtyä kohtaan **Kaikki palvelut** > **Power BI Embedded** ja katsoa, onko kapasiteettisi valmis.

![Azure-portaalin koontinäyttö ja Power BI Embedded -kapasiteetti](media/azure-pbie-create-capacity/azure-portal-dashboard.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Voit käyttää uutta Power BI Embedded -kapasiteettia siirtymällä Power BI -hallintaportaaliin, jossa voit määrittää työtiloja. Lisätietoja on kohdassa [Kapasiteettien hallinta Power BI Premiumissa ja Power BI Embeddedissä](https://powerbi.microsoft.com/documentation/powerbi-admin-premium-manage/).

Jos sinun ei tarvitse käyttää tätä kapasiteettia, voit keskeyttää sen lopettaaksesi laskutuksen. Katso lisätietoja kohdasta [Power BI Embedded -kapasiteetin keskeyttäminen ja käynnistäminen Azure-portaalissa](azure-pbie-pause-start.md).

Jos haluat aloittaa Power BI -sisällön upottamisen sovellukseesi, katso kohta [Power BI -koontinäyttöjen, -raporttien ja -ruutujen upottaminen](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/).

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)