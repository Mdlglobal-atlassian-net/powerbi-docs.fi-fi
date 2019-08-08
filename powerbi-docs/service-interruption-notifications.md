---
title: Palvelun keskeytymisilmoitukset
description: Lue tietoja siitä, miten voit vastaanottaa sähköposti-ilmoituksia, kun Power BI -palvelussa häiriöitä tai toiminnan heikkenemistä.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/25/2019
ms.author: mblythe
ms.openlocfilehash: a33ace000917311cbd060c853e0122034a396ae2
ms.sourcegitcommit: 4595a6231615d253aead315cb3f85472e2f189e6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/25/2019
ms.locfileid: "68501745"
---
# <a name="service-interruption-notifications"></a>Palvelun keskeytymisilmoitukset

On tärkeää, että saat merkityksellistä tietoa liiketoiminnalle tärkeiden yrityssovellusten käytettävyydestä. Power BI sisältää tapausilmoituksen, joten voit halutessasi vastaanottaa sähköpostiviestejä, jos palvelussa on häiriöitä tai toiminnan heikkenemistä. Vaikka Power BI:n palvelutasosopimus (99,9 %) tekee näistä tapahtumista harvinaisia, haluamme varmistaa, että pysyt ajan tasalla. Seuraavassa näyttökuvassa näkyy, millaista sähköpostia saat, jos otat ilmoitukset käyttöön:

![Päivitysilmoituksen sähköposti](media/service-interruption-notifications/refresh-notification-email.png)

Tällä hetkellä lähetämme sähköpostiviestejä seuraavissa _luotettavuustilanteissa_:

- Raportin avaamisen luotettavuus
- Mallin päivityksen luotettavuus
- Kyselyn päivityksen luotettavuus

Näitä ilmoituksia lähetetään esimerkiksi silloin, kun käyttäjillä on pitkä viive toiminnoissa, kuten raporttien avaamisessa, tietojoukon päivityksessä tai kyselyjen suorittamisessa. Kun tapaus on ratkaistu, saat seurantasähköpostiviestin.

> [!NOTE]
> Tämä ominaisuus on tällä hetkellä käytettävissä vain Power BI Premiumin varatuissa kapasiteeteissa. Se ei ole käytettävissä jaetussa tai upotetussa kapasiteetissa.

## <a name="enable-notifications"></a>Ota ilmoitukset käyttöön

Power BI -vuokraajan järjestelmänvalvoja ottaa ilmoitukset käyttöön hallintaportaalissa:

1. Yksilöi tai luo sähköpostia käyttävä käyttöoikeusryhmä, jonka tulee saada ilmoituksia.

1. Valitse hallintaportaalissa **Vuokraaja-asetukset**. Valitse **Ohjeen ja tuen asetukset** ja laajenna **Ota vastaan sähköposti-ilmoituksia palvelukatkoista tai -tapauksista**.

1. Ota ilmoitukset käyttöön, anna käyttöoikeusryhmä ja valitse **Käytä**.

    ![Ota käyttöön palveluilmoitukset](media/service-interruption-notifications/enable-notifications.png)

> [!NOTE]
> Power BI lähettää ilmoitukset tilistä no-reply-powerbi@microsoft.com. Varmista, että tämä tili on sallittujen luettelossa, jotta ilmoitukset eivät päädy roskapostikansioon.

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI Pron ja Power BI Premiumin tukivaihtoehdot](service-support-options.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)