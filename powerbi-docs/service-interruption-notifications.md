---
title: Palvelun keskeytymisilmoitukset
description: Lue tietoja siitä, miten voit vastaanottaa sähköposti-ilmoituksia, kun Power BI -palvelussa häiriöitä tai toiminnan heikkenemistä.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/06/2020
ms.author: kfollis
ms.openlocfilehash: 984991d8640df04c19b6461f5f0faaf0a50fe4ed
ms.sourcegitcommit: 2b93c1cc29aaf199ab7441a04c8e5ae49ffca5d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/07/2020
ms.locfileid: "80812962"
---
# <a name="service-interruption-notifications"></a>Palvelun keskeytymisilmoitukset

On tärkeää, että saat merkityksellistä tietoa liiketoiminnalle tärkeiden yrityssovellusten käytettävyydestä. Power BI sisältää tapausilmoituksen, joten voit halutessasi vastaanottaa sähköpostiviestejä, jos palvelussa on häiriöitä tai toiminnan heikkenemistä. Vaikka Power BI:n palvelutasosopimus (99,9 %) tekee näistä tapahtumista harvinaisia, haluamme varmistaa, että pysyt ajan tasalla. Seuraavassa näyttökuvassa näkyy, millaista sähköpostia saat, jos otat ilmoitukset käyttöön:

![Päivitysilmoituksen sähköposti](media/service-interruption-notifications/refresh-notification-email.png)

Tällä hetkellä lähetämme sähköpostiviestejä seuraavissa _luotettavuustilanteissa_:

- Raportin avaamisen luotettavuus
- Mallin päivityksen luotettavuus
- Kyselyn päivityksen luotettavuus

Ilmoituksia lähetetään silloin, kun toiminnoissa, kuten raporttien avaamisessa, tietojoukon päivityksessä tai kyselyjen suorittamisessa, on _pitkä viive_. Kun tapaus on ratkaistu, saat seurantasähköpostiviestin.

> [!NOTE]
> Tämä ominaisuus on tällä hetkellä käytettävissä vain Power BI Premiumin varatuissa kapasiteeteissa. Se ei ole käytettävissä jaetussa tai upotetussa kapasiteetissa.

## <a name="capacity-and-reliability-notifications"></a>Kapasiteetin ja luotettavuuden ilmoitukset

Kun Power BI Premium -kapasiteetilla on pitkiä resurssien runsaan käytön jaksoja, jotka saattavat vaikuttaa luotettavuuteen, lähetetään ilmoitussähköpostiviesti. Tällaisia vaikutuksia ovat esimerkiksi pitkät viiveet toiminnoissa, kuten raportin avaamisessa, tietojoukon päivittämisessä ja kyselyjen suorittamisessa. 

Ilmoitussähköpostiviestissä on tietoja resurssien runsaan käytön syystä, esimerkiksi seuraavat tiedot:

* vastaavan tietojoukon tunnus
* toiminnon tyyppi
* resurssien runsaaseen käyttöön liittyvä suoritinaika.

Power BI lähettää sähköposti-ilmoituksia myös, kun Power BI Premium -kapasiteetissa havaitaan ylikuormitus. Sähköpostiviestissä selitetään ylikuormituksen todennäköinen syy, mitkä toiminnot aiheuttivat kuormituksen edellisen kymmenen minuutin aikana ja miten paljon kuormaa eri toiminnot loivat. 

Jos sinulla on vähintään kaksi Premium-kapasiteettia, sähköpostiviestissä on tietoja kyseisistä kapasiteeteista ylikuormitusjakson aikana, jolloin voit harkita resursseja runsaasti käyttävien työtilojen siirtämistä kapasiteetteihin, joissa on vähiten kuormitusta.

Ylikuormituksesta kertovia sähköposti-ilmoituksia lähetetään vain, kun ylikuormituskynnys ylitetään. Et saa toista sähköpostiviestiä, kun kyseisen Premium-kapasiteetin kuorma palautuu ylikuormittumattomalle tasolle.

Seuraavassa kuvassa on esimerkki ilmoitussähköpostiviestistä:


![ylikuormitettua kapasiteettia koskeva ilmoitussähköpostiviesti](media/service-interruption-notifications/refresh-notification-email-2.png)


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

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
