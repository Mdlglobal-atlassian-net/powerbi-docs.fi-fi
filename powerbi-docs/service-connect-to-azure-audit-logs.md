---
title: Muodosta yhteys Azure-valvontalokeihin Power BI:n avulla
description: 'Azure-valvontalokit Power BI:lle '
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/06/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 903f2a345ba4d87cb217ececa459a3cca14d72fa
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2018
ms.locfileid: "37134635"
---
# <a name="connect-to-azure-audit-logs-with-power-bi"></a>Muodosta yhteys Azure-valvontalokeihin Power BI:n avulla
Azure-valvontalokien sisältöpaketissa voit analysoida ja visualisoida valvontalokeihin tallennettuja tietoja. Power BI noutaa tiedot ja laatii sitten valmiin koontinäytön ja siihen liittyvät raportit kyseisten tietojen perusteella.

Muodosta yhteys [Azure-valvontalokien sisältöpakettiin](https://app.powerbi.com/getdata/services/azure-audit-logs) tai lue lisää [Azure-valvontalokien integroinnista](https://powerbi.microsoft.com/integrations/azure-audit-logs) Power BI:hin.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.  
   
    ![](media/service-connect-to-azure-audit-logs/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.  
   
    ![](media/service-connect-to-azure-audit-logs/services.png) 
3. Valitse **Azure-valvontalokit** > **Hae**.  
   
   ![](media/service-connect-to-azure-audit-logs/azureauditlogs.png)
4. Anna pyydettäessä **Azure-tilaustunnus**. Tiedot [tilauksen tunnuksen](#FindingParams) hakemisesta on annettu alla.   
   
    ![](media/service-connect-to-azure-audit-logs/parameters.png)
5. Valitse **todennusmenetelmäksi** **oAuth2** \> **Kirjaudu sisään**.
   
    ![](media/service-connect-to-azure-audit-logs/creds.png)
6. Anna tilin tunnistetiedot kirjautumisprosessin päättämiseksi.
   
    ![](media/service-connect-to-azure-audit-logs/login.png)
7. Power BI noutaa Azure-valvontalokitietosi ja luo käyttövalmiin raporttinäkymän ja raportin. 
   
    ![](media/service-connect-to-azure-audit-logs/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="system-requirements"></a>Järjestelmävaatimukset
Azure-valvontalokien sisältöpaketti edellyttää pääsyä valvontalokeihin Azure-portaalissa. Saat lisätietoja [tästä](https://azure.microsoft.com/documentation/articles/insights-debugging-with-events/).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
On olemassa kaksi helppoa tapaa löytää tilauksen tunnus.

1. Kohdasta https://portal.azure.com -&gt; Selaa -&gt; Tilaukset -&gt; Tilaustunnus
2. Kohdasta https://manage.windowsazure.com -&gt; Asetukset  -&gt; Tilaustunnus

Tilauksen tunnus on pitkä numero- ja merkkisarja, joka on samanlainen kuin esimerkin vaiheessa \#4 yllä. 

## <a name="troubleshooting"></a>Vianmääritys
Jos näet tunnistetietojen virheen tai virheen yritettäessä päivittää virheellisten tunnistetietojen vuoksi, yritä poistaa kaikki esiintymät Azure-valvontalokien sisältöpaketista ja yritä yhteyden muodostamista uudelleen.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)  
[Power BI:n peruskäsitteet](service-basic-concepts.md)  

