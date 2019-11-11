---
title: Power BI Embedded -kapasiteetin keskeyttäminen ja käynnistäminen Azure-portaalissa | Microsoft Docs
description: Tässä artikkelissa esitellään, miten voit keskeyttää ja käynnistää Power BI Embedded -kapasiteetin Microsoft Azuressa.
services: power-bi-embedded
author: rkarlin
ms.author: rkarlin
editor: ''
tags: ''
ms.service: power-bi-embedded
ms.topic: conceptual
ms.date: 09/28/2017
ms.openlocfilehash: c851e76a57618ad1b683e1fa56251423b8d6eeb3
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73865011"
---
# <a name="pause-and-start-your-power-bi-embedded-capacity-in-the-azure-portal"></a>Power BI Embedded -kapasiteetin keskeyttäminen ja käynnistäminen Azure-portaalissa

Tässä artikkelissa esitellään, miten voit keskeyttää ja käynnistää Power BI Embedded -kapasiteetin Microsoft Azuressa. Tässä oletetaan, että olet luonut Power BI Embedded -kapasiteetin. Jos et ole tehnyt niin, katso ohjeet kohdasta [Power BI Embedded -kapasiteetin luominen Azure-portaalissa](azure-pbie-create-capacity.md).

Jos sinulla ei ole Azure-tilausta, luo [ilmainen tili](https://azure.microsoft.com/free/) ennen aloittamista.

## <a name="pause-your-capacity"></a>Kapasiteetin keskeyttäminen

Kapasiteettisi keskeyttäminen estää sen, että sinua ei laskuteta. Kapasiteettisi keskeyttäminen on kätevää, jos sinun ei tarvitse käyttää kapasiteettia hetkeen. Seuraavien vaiheiden avulla voit keskeyttää kapasiteettisi.

> [!NOTE]
> Kapasiteetin keskeyttäminen saattaa estää sisällön käyttämisen Power BI:ssä. Varmista, että poistat työtilat kapasiteetistasi ennen keskeyttämistä häiriöiden välttämiseksi.

1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com/).

2. Voit tarkastella kapasiteetteja valitsemalla **Kaikki palvelut** > **Power BI Embedded**.

    ![Kaikki palvelut Azure-portaalissa](media/azure-pbie-pause-start/azure-portal-more-services.png)

3. Valitse kapasiteetti, jonka haluat keskeyttää.

    ![Power BI Embedded -kapasiteettiluettelo Azure-portaalissa](media/azure-pbie-pause-start/azure-portal-capacity-list.png)

4. Valitse **Keskeytä** kapasiteetin tiedoissa.

    ![Kapasiteetin keskeyttäminen](media/azure-pbie-pause-start/azure-portal-pause-capacity.png)

5. Valitse **Kyllä**, joka vahvistaa, että haluat keskeyttää kapasiteetin.

    ![Keskeyttämisen vahvistaminen](media/azure-pbie-pause-start/azure-portal-confirm-pause.png)

## <a name="start-your-capacity"></a>Kapasiteetin käynnistäminen

Jatka käyttöä käynnistämällä kapasiteetti. Kapasiteettisi käynnistäminen jatkaa myös laskutustasi.

1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com/).

2. Voit tarkastella kapasiteetteja valitsemalla **Kaikki palvelut** > **Power BI Embedded**.

    ![Kaikki palvelut Azure-portaalissa](media/azure-pbie-pause-start/azure-portal-more-services.png)

3. Valitse kapasiteetti, jonka haluat käynnistää.

    ![Power BI Embedded -kapasiteettiluettelo Azure-portaalissa](media/azure-pbie-pause-start/azure-portal-capacity-list.png)

4. Valitse **Käynnistä** kapasiteetin tiedoissa.

    ![Kapasiteetin käynnistäminen](media/azure-pbie-pause-start/azure-portal-start-capacity.png)

5. Valitse **Kyllä**, joka vahvistaa, että haluat käynnistää kapasiteetin.

    ![Käynnistämisen vahvistaminen](media/azure-pbie-pause-start/azure-portal-confirm-start.png)

Jos kapasiteetille on varattu sisältöä, se on käytettävissä käynnistämisen jälkeen.

## <a name="next-steps"></a>Seuraavat vaiheet

Jos haluat skaalata kapasiteettiasi ylös tai alas, katso kohta [Power BI Embedded -kapasiteetin skaalaaminen](azure-pbie-scale-capacity.md).

Jos haluat aloittaa Power BI -sisällön upottamisen sovellukseesi, katso kohta [Power BI -koontinäyttöjen, -raporttien ja -ruutujen upottaminen](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/).

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)