---
title: Mallisisältöpaketin kokemukset Power BI:ssä
description: Mallisisältöpaketin kokemukset
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/09/2017
ms.author: maghan
ms.openlocfilehash: fb1aaded94ce5411cf26257a1e561125cec9a347
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2018
ms.locfileid: "30973072"
---
# <a name="template-content-pack-experiences-in-power-bi"></a>Mallisisältöpaketin kokemukset Power BI:ssä
Tässä osassa esitellään tyypillinen käyttökokemus, kun käyttäjä muodostaa yhteyden ISV:n [sisältöpakettiin](../service-connect-to-services.md). 

Kokeile yhdistämistä itse muodostamalla yhteys julkaistuun sisältöpakettiin osoitteessa https://app.powerbi.com/getdata/services (käytä esimerkiksi alla esitettyä [GitHub-sisältöpakettia](https://app.powerbi.com/getdata/services/github)).

## <a name="connect"></a>Yhdistä
Aluksi käyttäjä selaa sisältöpakettivalikoimaa ja valitsee sisältöpaketin, johon yhteys muodostetaan. Sisältöpakettimerkintä sisältää nimen, kuvakkeen ja kuvaavan tekstin, joka antaa lisätietoa käyttäjälle.

![yhdistä](media/template-content-pack-experience/github_data.png)

![yhdistä](media/template-content-pack-experience/github_connect.png)

## <a name="parameters"></a>Parametrit
Kun paketti on valittu, käyttäjältä pyydetään parametreja (tarvittaessa). Tekijä antaa parametrien valintaikkunan ilmoituksella sisältöpaketin luonnin aikana.

Tällä hetkellä parametrien käyttöliittymä on erittäin yksinkertainen – avattavia luetteloita ei voi luetella millään tavalla ja tietosyötön oikeellisuustarkistus on rajoitettu säännönmukaiseksi lausekkeeksi.

![parametrit](media/template-content-pack-experience/github_params.png)

## <a name="credentials"></a>Tunnistetiedot
Parametrien jälkeen käyttäjää pyydetään kirjautumaan sisään.  Jos lähde tukee useita todentamistyyppejä, käyttäjä valitsee sopivan vaihtoehdon. Jos lähde edellyttää OAuth-todentamista, palvelun kirjautumiskäyttöliittymä avautuu, kun käyttäjä valitsee Kirjaudu sisään.  Muussa tapauksessa käyttäjä voi antaa tunnistetietonsa valintaikkunassa.

![Tunnistetiedot](media/template-content-pack-experience/github_login.png)

![yhdistä](media/template-content-pack-experience/github_creds2.png)

## <a name="instantiation"></a>Esiintymä
Kun kirjautuminen onnistuu, sisältöpakettiin sisältyvät osat – malli, raportit ja koontinäyttö – näkyvät siirtymispalkissa.  Nämä osat lisätään kunkin käyttäjän tiliin.  Tiedot ladataan asynkronisesti tietojoukon (mallin) täyttämiseksi.  Käyttäjä voi sitten käyttää koontinäyttöä, raportteja ja mallia.

Oletusarvoisesti käyttäjälle on määritetty päivittäinen päiväaikataulu, jossa arvioidaan uudelleen mallin kyselyt.  Käyttäjälle annettujen tunnistetietojen on sallittava tietojen päivittäminen ilman, että tunnistetiedot ovat näkyvissä.

![Esiintymä](media/template-content-pack-experience/github_dashboard.png)

## <a name="exploration-and-monitoring"></a>Tarkasteleminen ja valvonta
Kun sisältöpaketti on lisätty käyttäjän tiliin, hän voi tutkia ja valvoa tietoja ja merkityksellisiä tietoja.

Tämä sisältää yleensä seuraavat:

* koontinäytön tarkasteleminen ja mukauttaminen
* raportin tarkasteleminen ja mukauttaminen
* tietoja koskevien kysymysten esittäminen luonnollisella kielellä
* tietomallin tietojen tutkiminen tarkastelemisen piirtoalustan avulla

Paketin luomisessa kannattaa harkita luonnollisen kielen mallin (synonyymit) ja ymmärrettävän mallirakenteen tarjoamista, jotta tarkastelukokemus olisi parempi.
