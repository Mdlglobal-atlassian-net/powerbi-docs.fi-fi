---
title: Yhteyden muodostaminen Trouxiin Power BI:llä
description: Troux Power BI:lle
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 701b35d317076827148ec523d38f0c23362aed47
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815824"
---
# <a name="connect-to-troux-for-power-bi"></a>Yhteyden muodostaminen Trouxiin Power BI:lle
Troux-sisältöpaketin avulla voit visualisoida yritysarkkitehtuurisäilösi kokonaan uusilla tavoilla suoraan Power BI:ssä. Sisältöpaketti tarjoaa joukon merkityksellisiä tietoja liiketoimintasi ominaisuuksista, kyseiset ominaisuudet mahdollistavista sovelluksista sekä näitä sovelluksia tukevista tekniikoista, jotka ovat Power BI:n avulla täysin mukautettavissa.

Muodosta yhteys [Troux-sisältöpakettiin](https://app.powerbi.com/getdata/services/troux) Power BI:lle.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-troux/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-troux/services.png)
3. Valitse **Troux** \> **Nouda**.
   
   ![](media/service-connect-to-troux/troux.png)
4. Määritä Troux-OData-URL-osoite. Lisätietoja [näiden parametrien löytämisestä](#FindingParams) on alla.
   
   ![](media/service-connect-to-troux/params.png)
5. Valitse kohtaan **Todennusmenetelmä** **Perus** ja anna käyttäjänimesi ja salasanasi (kirjainkoolla on merkitystä), valitse sitten **Kirjaudu sisään**.
   
    ![](media/service-connect-to-troux/creds.png)
6. Hyväksymisen jälkeen tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi koontinäyttö, raportti ja malli tulevat näkyviin siirtymisruutuun. Voit tarkastella tuotuja tietoja valitsemalla koontinäytön.
   
     ![](media/service-connect-to-troux/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä Q&A-ruudussa](power-bi-q-and-a.md) koontinäytön yläreunassa
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä haluamanasi ajankohtana toiminnolla **Päivitä nyt**

## <a name="system-requirements"></a>Järjestelmävaatimukset
Seuraavien käyttöoikeus vaaditaan: Troux-OData-syöte ja Troux 9.5.1 tai uudempi.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Asiakastuki voi antaa sinulle yksilöllisen Troux-OData-syötteen URL-osoitteen

## <a name="troubleshooting"></a>Vianmääritys
Jos tunnistetietojen antamisen jälkeen ilmenee aikakatkaisuvirhe, yritä muodostaa yhteys uudelleen.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

