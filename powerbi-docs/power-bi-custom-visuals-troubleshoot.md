---
title: Power BI:n Power BI -visualisointien kehittämisen vianmääritys
description: Tässä artikkelissa käsitellään joitain yleisiä ongelmia, joita saattaa ilmetä mukautetun Power BI -visualisoinnin kehittämisen tai luomisen aikana.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: troubleshooting
ms.date: 11/06/2018
ms.openlocfilehash: 6fce02a4707d12859286f85073222b498a1a59f4
ms.sourcegitcommit: e5cf19e16112c7dad1591c3b38d232267ffb3ae1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/17/2019
ms.locfileid: "72543879"
---
# <a name="troubleshoot-power-bi-power-bi-visuals"></a>Power BI:n Power BI -visualisointien vianmääritys

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

Power -visualisointien tukitiimille voit lähettää kysymyksiä ja kommentteja:  *pbicvsupport@microsoft.com*  .

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja on kohdassa [Usein kysyttyjä kysymyksiä – Power BI:n Power BI -visualisoinnit](power-bi-custom-visuals-faq.md#organizational-visuals).