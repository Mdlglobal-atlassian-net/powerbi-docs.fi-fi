---
title: Power BI:n mukautettujen visualisointien kehittämisen vianmääritys
description: Tässä artikkelissa käsitellään joitain yleisiä ongelmia, joita saattaa ilmetä mukautetun Power BI -visualisoinnin kehittämisen tai luomisen aikana.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/06/2018
ms.openlocfilehash: 3d9e8e46fdd84edbeb5b4ff5e8f7efe4a4291049
ms.sourcegitcommit: a739a99e1006834a0f56e387c0bd9d945fb8a76b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/15/2018
ms.locfileid: "51679234"
---
# <a name="troubleshoot-power-bi-custom-visuals"></a>Power BI:n mukautettujen visualisointien vianmääritys

## <a name="debug"></a>Virheenkorjaus

**Pbiviz-komentoa ei löydy (tai samankaltaisia virheitä)**

Jos suoritat kohteen `pbiviz` päätteen komentorivillä, näkyviin pitäisi tulla Ohje-näyttö. Jos näin ei ole, sitä ei ole asennettu oikein. Varmista, että olet asentanut vähintään NodeJS 4.0 -version.

**Visualisoinnin virheenkorjausta ei löydy Visualisoinnit-välilehdestä**

Visualisoinnin virheenkorjaus on kehotekuvakkeen kaltainen **Visualisoinnit**-välilehdessä.

![Visualisoinnin valinta](media/power-bi-custom-visuals-troubleshoot/powerbi-developer-visual-selection.png)

Jos et näe sitä, varmista, että olet ottanut sen käyttöön Power BI:n asetuksissa.

> [!NOTE]
> Virheenkorjauksen visualisointi on nykyisin saatavilla vain Power BI Desktopissa tai mobiilisovelluksessa. Pakattu visualisointi toimii edelleen kaikkialla.

**Yhteyden muodostaminen visualisointipalvelimeen ei onnistu**

Suorita visualisointipalvelin käyttämällä `pbiviz start`-komentoa päätteen komentorivillä visualisointiprojektin juurikansiosta. Jos palvelin ei toimi, se johtuu todennäköisesti siitä, että SSL-varmenteita ei ole asennettu oikein.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja ja vastauksia kysymyksiisi [Power BI:n mukautettujen visualisointien usein kysytyistä kysymyksistä](power-bi-custom-visuals-faq.md#organizational-custom-visuals).
