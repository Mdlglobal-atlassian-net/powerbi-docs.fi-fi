---
title: Yhteyden muodostaminen Trouxiin Power BI:llä
description: Troux Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: dbf3831264a354ec96a38751dfa7a3719c5c9f2a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34247937"
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
6. Hyväksymisen jälkeen tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
     ![](media/service-connect-to-troux/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

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
