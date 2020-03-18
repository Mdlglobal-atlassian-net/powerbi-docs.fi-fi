---
title: Power BI Embedded -kapasiteetin skaalaaminen | Microsoft Docs
description: Tässä artikkelissa esitellään, miten voit skaalata Power BI Embedded -kapasiteetin Microsoft Azuressa.
services: power-bi-embedded
author: KesemSharabi
ms.author: kesharab
editor: ''
tags: ''
ms.service: power-bi-embedded
ms.topic: how-to
ms.date: 01/31/2019
ms.openlocfilehash: 18ce2f9b89e78fee3856bf1ceb93805ebc4d27b9
ms.sourcegitcommit: a175faed9378a7d040a08ced3e46e54503334c07
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/18/2020
ms.locfileid: "79495615"
---
# <a name="scale-your-power-bi-embedded-capacity-in-the-azure-portal"></a>Power BI Embedded -kapasiteetin skaalaaminen Azure-portaalissa

Tässä artikkelissa esitellään, miten voit skaalata Power BI Embedded -kapasiteetin Microsoft Azuressa. Skaalauksen avulla voit suurentaa tai pienentää kapasiteettisi.

Tässä oletetaan, että olet luonut Power BI Embedded -kapasiteetin. Jos et ole tehnyt niin, katso ohjeet kohdasta [Power BI Embedded -kapasiteetin luominen Azure-portaalissa](azure-pbie-create-capacity.md).

> [!NOTE]
> Skaalaustoiminto voi kestää noin minuutin. Tänä aikana kapasiteetti ei ole käytettävissä. Upotettua sisältöä ei ehkä voi ladata.

## <a name="scale-a-capacity"></a>Kapasiteetin skaalaaminen

1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com/).

2. Voit tarkastella kapasiteetteja valitsemalla **Kaikki palvelut** > **Power BI Embedded**.

    ![Kaikki palvelut Azure-portaalissa](media/azure-pbie-scale-capacity/azure-portal-more-services.png)

3. Valitse kapasiteetti, jonka haluat skaalata.

    ![Power BI Embedded -kapasiteettiluettelo Azure-portaalissa](media/azure-pbie-scale-capacity/azure-portal-capacity-list.png)

4. Valitse **Hinnoittelutaso** kohdassa **Skaalaus** kapasiteettisi sisällä.

    ![Hinnoittelutaso-vaihtoehto Skaalaus-kohdassa](media/azure-pbie-scale-capacity/azure-portal-scale-pricing-tier.png)

    Nykyinen hinnoittelutasosi näkyy sinisenä.

    ![Nykyinen hinnoittelutaso näkyy sinisenä](media/azure-pbie-scale-capacity/azure-portal-current-tier.png)

5. Voit skaalata ylös tai alas valitsemalla uuden tason, johon haluat siirtyä. Uuden tason valitseminen sijoittaa sinisen katkoviivan valinnan ympärille. Valitse **Valitse** skaalataksesi uuteen tasoon.

    ![Uuden tason valitseminen](media/azure-pbie-scale-capacity/azure-portal-select-new-tier.png)

    Kapasiteettisi skaalaus saattaa kestää muutaman minuutin.

6. Vahvista taso Yleiskatsaus-välilehdessä. Nykyinen hinnoittelutaso on luettelossa.

    ![Nykyisen tason vahvistaminen](media/azure-pbie-scale-capacity/azure-portal-confirm-tier.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Katso lisätietoja kapasiteettisi keskeyttämisestä tai käynnistämisestä kohdasta [Power BI Embedded -kapasiteetin keskeyttäminen ja käynnistäminen Azure-portaalissa](azure-pbie-pause-start.md).

Jos haluat aloittaa Power BI -sisällön upottamisen sovellukseesi, katso kohta [Power BI -koontinäyttöjen, -raporttien ja -ruutujen upottaminen](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/).

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
