---
title: Poista Power Query -taustalataus käytöstä
description: Ohjeet, milloin Power Query -taustalataus kannattaa poistaa käytöstä.
author: peter-myers
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: v-pemyer
ms.openlocfilehash: 59cb62a9186da03a265fc3a8711d7275c3772af3
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "75623057"
---
# <a name="disable-power-query-background-refresh"></a>Poista Power Query -taustalataus käytöstä

Tämä artikkeli on tarkoitettu tuotujen tietojen mallintajille, jotka käyttävät Power BI Desktopia.

Kun Power Query tuo tietoja, oletusarvon mukaan se myös tallentaa välimuistiin kustakin kyselystä enintään 1 000 riviä esikatselutietoja. Esikatselutietojen avulla lähdetiedot ja kyselyiden jokaisen vaiheen muunnostulokset voi esikatsella nopeasti. Tiedot tallennetaan erikseen levylle. Niitä ei tallenneta Power BI Desktopin tiedostoon.

Kun Power BI Desktopin tiedostosi sisältää useita kyselyitä, esikatselutietojen noutaminen ja tallentaminen voi pidentää aikaa, joka kuluu päivityksen viimeistelyyn.

## <a name="recommendation"></a>Suositus

Päivitys tapahtuu nopeammin, kun asetat Power BI Desktopin tiedoston päivittämään esikatseluvälimuistin _taustalla_. Ota se käyttöön Power BI Desktopissa valitsemalla _Tiedosto > Asetukset ja vaihtoehdot > Asetukset_. Valitse sitten _Tietojen lataaminen_ -sivu. Sen jälkeen voit ottaa käyttöön **Salli tietojen esikatselun latautua taustalla** -vaihtoehdon. Huomaa, että tämä vaihtoehto voidaan valita vain nykyiselle tiedostolle.

![Power BI Desktopin taustatietojen asetukset](media/power-query-background-refresh/power-query-options-background-data.png)

Esikatselutiedot eivät välttämättä ole ajan tasalla, kun taustapäivitys on otettu käyttöön. Jos näin käy, Power Query -editori näyttää seuraavan varoituksen:

![Power Query -editorin varoitus vanhoista esikatselutiedoista](media/power-query-background-refresh/power-query-preview-data-old.png)

Esikatseluvälimuistin voi aina päivittää. Voit päivittää sen yksittäisessä kyselyssä tai kaikissa kyselyissä käyttämällä **Päivitä esikatselu** -komentoa. Löydät sen Power Query -editorin ikkunasta **aloitussivun** valintanauhasta.

![Power Query -editorin komennot esikatselutietojen päivittämistä varten](media/power-query-background-refresh/power-query-refresh-preview-data.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Power Queryn ohjeet](/power-query/)
- Onko sinulla kysymyksiä? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
