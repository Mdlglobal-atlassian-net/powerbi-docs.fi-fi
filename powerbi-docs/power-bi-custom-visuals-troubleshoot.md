---
title: Power BI:n mukautettujen visualisointien kehittämisen vianmääritys
description: Tässä artikkelissa käsitellään joitain yleisiä ongelmia, joita saattaa ilmetä mukautetun Power BI -visualisoinnin kehittämisen tai luomisen aikana.
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 11/06/2018
ms.openlocfilehash: cbda8cca80c32056f06788e53540d7f2d6ed972d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61421772"
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

Mukautettujen visualisointien tukitiimille voit lähettää kysymyksiä ja kommentteja:  *pbicvsupport@microsoft.com*  .

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja on kohdassa [Usein kysyttyjä kysymyksiä – Power BI:n mukautetut visualisoinnit](power-bi-custom-visuals-faq.md#organizational-custom-visuals).
