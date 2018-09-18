---
title: Linkin luominen tiettyyn sijaintiin Power BI ‑mobiilisovelluksissa
description: Opettele luomaan Power BI ‑mobiilisovelluksessa tarkka linkki tiettyyn koontinäkymään, ruutuun tai raporttiin käyttämällä URI-tunnusta.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 06/28/2018
ms.author: maggies
ms.openlocfilehash: 63b9129c56b064f224eef0720e5f585c86d80a93
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/12/2018
ms.locfileid: "44735562"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Linkin luominen tiettyyn sijaintiin Power BI ‑mobiilisovelluksissa
Voit luoda URI-tunnuksen (uniform resource identifier) ja tehdä sen avulla linkin tiettyyn sijaintiin (*tarkka linkki*) Power BI ‑mobiilisovelluksissa kaikissa mobiiliympäristöissä: iOS:ssä, Android-laitteilla ja Windows 10:ssä.

URI-linkit voivat osoittaa suoraan koontinäyttöihin, ruutuihin ja raportteihin.

Tarkan linkin kohde määrittää URI-tunnuksen muodon. Näiden ohjeiden avulla voit luoda tarkkoja linkkejä eri sijainteihin. 

## <a name="open-the-power-bi-mobile-app"></a>Power BI ‑mobiilisovelluksen avaaminen
Käyttämällä tätä URI-tunnusta voit avata Power BI ‑mobiilisovelluksen millä tahansa laitteella:

    mspbi://app/


## <a name="open-to-a-specific-dashboard"></a>Siirtyminen suoraan tiettyyn koontinäyttöön
Tällainen URI-tunnus avaa Power BI ‑mobiilisovelluksen tietyn koontinäytön:

    mspbi://app/OpenDashboard?DashboardObjectId=<36-character-dashboard-id>

Löydät koontinäytön 36-merkkisen objektitunnuksen siirtymällä Power BI -palvelussa (https://powerbi.com) haluamaasi koontinäyttöön. Katso esimerkiksi tämän URL-osoitteen korostettua osaa:

`https://powerbi.com/groups/me/dashboards/**61b7e871-cb98-48ed-bddc-6572c921e270**`

Jos koontinäyttö on osa jotakin muuta ryhmää kuin omaa työtilaa, lisää joko ennen koontinäytön tunnusta tai sen perään `&GroupObjectId=<36-character-group-id>`. Esimerkki: 

mspbi://app/OpenDashboard?DashboardObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60 **&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

Huomaa, että niiden väliin tulee et-merkki (&).

## <a name="open-to-a-specific-tile-in-focus"></a>Tietyn ruudun avaaminen kohdistustilassa
Tällainen URI-tunnus avaa Power BI ‑mobiilisovelluksessa tietyn ruudun:

    mspbi://app/OpenTile?DashboardObjectId=<36-character-dashboard-id>&TileObjectId=<36-character-tile-id>

Löydät koontinäytön ja ruudun 36-merkkiset objektitunnukset siirtymällä Power BI -palvelussa (https://powerbi.com) haluamaasi koontinäyttöön ja avaamalla ruudun kohdistustilassa. Katso esimerkiksi tämän URL-osoitteen korostetut osat:

`https://powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus`

Tämän ruudun URI olisi:

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

Huomaa, että niiden väliin tulee et-merkki (&).

Jos koontinäyttö on osa jotakin muuta ryhmää kuin omaa työtilaa, lisää `&GroupObjectId=<36-character-group-id>`

## <a name="open-to-a-specific-report"></a>Tietyn raportin avaaminen
Tällainen URI-tunnus avaa Power BI ‑mobiilisovelluksessa tietyn raportin:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>

Löydät raportin 36-merkkisen objektitunnuksen siirtymällä Power BI -palvelussa (https://powerbi.com) haluamaasi raporttiin. Katso esimerkiksi tämän URL-osoitteen korostettua osaa:

`https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300`

## <a name="open-to-a-specific-report-page"></a>Tietyn raporttisivun avaaminen
Tällainen URI-tunnus avaa Power BI ‑mobiilisovelluksessa tietyn raporttisivun:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>&reportPage=ReportSection<number>

Raporttisivun nimityksenä on ”ReportSection” ja sitä seuraava numero. Avaa jälleen raportti Power BI -palvelussa (https://powerbi.com) ja siirry haluamallesi raporttisivulle. 

Katso esimerkiksi tämän URL-osoitteen korostettua osaa:

`https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/ReportSection11`

## <a name="open-in-full-screen-mode"></a>Koko näytön tilassa avaaminen
Jos haluat, että jokin raportti avautuu koko näytön tilassa, lisää korostettuna oleva parametri:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>**&openFullScreen=true**

Esimerkki: 

mspbi://app/OpenReport?ReportObjectId=500217de-50f0-4af1-b345-b81027224033&openFullScreen=true

## <a name="add-context-optional"></a>Kontekstin lisääminen (valinnainen)
Voit lisätä merkkijonoon myös kontekstin. Sitten jos sinulle tulee tarvetta ottaa meihin yhteyttä, me voimme suodattaa kontekstin avulla tietojamme sovellukseesi. Lisää linkkiin `&context=<app-name>`

Katso esimerkiksi tämän URL-osoitteen korostettua osaa: 

`https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/&context=SlackDeepLink`

## <a name="next-steps"></a>Seuraavat vaiheet
Palaute auttaa meitä päättämään, mitä toimintoja otamme käyttöön tulevaisuudessa, joten muista äänestää muita ominaisuuksia, jotka haluaisit nähdä Power BI ‑mobiilisovelluksissa. 

* [Power BI -sovellukset mobiililaitteille](mobile-apps-for-mobile-devices.md)
* Seuraa käyttäjää @MSPowerBI Twitterissä
* Liity keskusteluun [Power BI -yhteisössä](http://community.powerbi.com/)
* [Mikä on Power BI?](../../power-bi-overview.md)

