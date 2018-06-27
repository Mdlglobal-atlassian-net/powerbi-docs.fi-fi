---
title: 'Ulkopuolinen palvelu: Google Analytics -yhdistin Power BI Desktopille'
description: 'Ulkopuolinen palvelu: Google Analytics -yhdistin Power BI Desktopille'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c3f495f64a2edeb85606453c951a7f6eaf2742fe
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34299443"
---
# <a name="google-analytics-connector-for-power-bi-desktop"></a>Google Analytics -yhdistin Power BI Desktopille
> [!NOTE]
> Google Analytics -sisältöpaketti ja -yhdistin Power BI Desktopille ovat riippuvaisia Google Analytics Core Reporting -ohjelmointirajapinnasta. Tämän vuoksi niiden ominaisuudet ja käytettävyys voivat vaihdella ajan mittaan.
> 
> 

Voit muodostaa yhteyden Google Analytics -tietoihin **Google Analytics** -yhdistimen avulla. Voit muodostaa yhteyden seuraavasti:

1. Valitse **Power BI Desktopissa** **Nouda tiedot** valintanauhan **Aloitus**-välilehdeltä.
2. Valitse **Nouda tiedot** -ikkunassa **Online-palvelut** vasemmanpuoleisen ruudun luokista.
3. Valitse **Google Analytics** oikeanpuoleisen ruudun valinnoista.
4. Valitse ikkunan alareunassa **Yhdistä**.  
   ![](media/service-google-analytics-connector/tps_googleanalytics_1.png)

Näkyviin tulee valintaikkuna, jossa kerrotaan, että yhdistin on kolmannen osapuolen palvelu, varoitetaan siitä, että sen ominaisuudet ja käytettävyys saattavat muuttua ajan mittaan, ja annetaan muita selvennyksiä.  
![](media/service-google-analytics-connector/tps_googleanalytics_2.png)

Kun valitset **Jatka**, sinua pyydetään kirjautumaan sisään Google Analyticsiin.  
![](media/service-google-analytics-connector/tps_googleanalytics_3.png)

Kun annat tunnistetietosi, näkyviin tulee valintaikkuna, jossa sinua pyydetään sallimaan Power BI:lle tietojen offline-käyttö. Tällä tavoin voit käyttää Google Analytics -tietojasi **Power BI Desktopissa**.  

Kun sallit tämän, **Power BI Desktop** näyttää, että olet kirjautuneena sisään.  
![](media/service-google-analytics-connector/tps_googleanalytics_5.png)

Valitse **Yhdistä**. Google Analytics-tietosi yhdistetään **Power BI Desktopiin** ja ladataan.  
![](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>Ohjelmointirajapinnan muutokset
Vaikka pyrimmekin julkaisemaan päivityksiä tehtyjen muutosten mukaan, ohjelmointirajapinta saattaa muuttua tavalla, joka vaikuttaa luotujen kyselyjen tuloksiin. Tiettyjä kyselyjä ei ehkä enää tueta joissain tapauksissa. Tämän riippuvuuden vuoksi emme voi taata tekemiesi kyselyjen tuloksia tätä yhdistintä käytettäessä.

Lisätietoja Google Analytics -ohjelmointirajapinnan muutoksista löytyy Google Analyticsin [muutoslokista](https://developers.google.com/analytics/devguides/changelog).

