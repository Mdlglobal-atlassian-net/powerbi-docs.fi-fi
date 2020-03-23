---
title: Power BI -visualisointien kehittämisen vianmääritys
description: Tässä artikkelissa käsitellään joitain yleisiä ongelmia, joita saattaa ilmetä mukautetun Power BI -visualisoinnin kehittämisen tai luomisen aikana.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: how-to
ms.subservice: powerbi-custom-visuals
ms.date: 11/06/2018
ms.openlocfilehash: ba11dae61b05ef73ae65db80de56a8a891360e88
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/14/2020
ms.locfileid: "79383248"
---
# <a name="troubleshoot-power-bi-visuals"></a>Power BI -visualisointien vianmääritys

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

Voit lähettää Power -visualisointien tukitiimille (pbicvsupport@microsoft.com) kysymyksiä ja kommentteja.

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja on kohdassa [Usein kysyttyjä kysymyksiä – Power BI -visualisoinnit](power-bi-custom-visuals-faq.md#organizational-power-bi-visuals).