---
title: Snowflakeen yhdistäminen Power BI Desktopilla
description: Snowflake ja Power BI:n kertakirjautuminen
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/20/2019
ms.author: gepopell
LocalizationGroup: Connect to services
ms.openlocfilehash: 5e5519e30be30d6367791d1b6822196b407a21b1
ms.sourcegitcommit: 4d98274aa0b9aa09db99add2dda91a3ba8fed40b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576862"
---
#  <a name="connecting-to-snowflake-in-power-bi-service"></a>Snowflakeen yhdistäminen Power BI ‑palvelussa

## <a name="introduction"></a>Johdanto

Snowflakeen yhdistäminen Power BI ‑palvelussa muista liittimistä siten, että AAD:lle on tarjolla yksi lisäominaisuus (johon sisältyy valinnainen kertakirjautuminen). Integraation eri osat edellyttävät eri järjestelmänvalvontarooleja Snowflakessa, Power BI:ssä ja Azuressa. Voit halutessasi ottaa AAD-todennuksen käyttöön ilman kertakirjautumisominaisuutta. Perustodennus toimii samalla tavalla kuin muut palvelun liittimet.

Jos haluat määrittää AAD-integroinnin sekä mahdollisesti ottaa kertakirjautumisen käyttöön:
* Jos olet Snowflake-järjestelmänvalvoja, lue Snowflaken käyttöoppaan [Kertakirjautuminen Snowflakeen Power BI:ssä – Aloittaminen](https://docs.snowflake.net/manuals/LIMITEDACCESS/oauth-powerbi.html) ‑artikkeli.
* (Kertakirjautuminen) Jos olet Power BI ‑järjestelmänvalvoja, tutustu “Power BI ‑palvelun määritykset – hallintaportaali” ‑osioon
* (Kertakirjautuminen) Jos olet Power BI ‑tietojoukon luoja, tutustu “Power BI ‑palvelun määritys – Tietojoukon käyttöönotto” ‑osioon

## <a name="power-bi-service-configuration"></a>Power BI ‑palvelun määrittäminen

### <a name="admin-portal"></a>Hallintaportaali

Jos haluat ottaa kertakirjautumisen käyttöön, vuokraajan järjestelmänvalvojan on siirryttävä hallintaportaaliin ja hyväksyttävä Power BI:n AAD-tunnistetietojen lähettäminen Snowflakeen.

![Vuokraajan järjestelmänvalvojan Snowflake-kertakirjautumisasetukset](media/service-connect-snowflake/snowflakessotenant.png)

Siirry Hallintaportaaliin, valitse sivupalkista “Vuokraajan asetukset" ja vieritä alas, niin näet “Snowflake-kertakirjautuminen” ‑vaihtoehdon “Integroinnin asetukset” ‑kohdassa.

Kuten edellä huomautettiin, sinun on annettava manuaalisesti suostumuksesi sille, että AAD-tunnuksesi lähetetään Snowflake-palvelimille. Voit ottaa sen käyttöön napsauttamalla “Pois käytöstä” ‑valintakytkintä, valitsemalla Käytä ja odottamalla, että uudet asetukset astuvat voimaan. Asetus astuu voimaan tunnin kuluessa.

Kun se on valmis, voit käyttää raportteja kertakirjautumisen avulla.

### <a name="configuring-a-dataset-with-aad"></a>Tietojoukon määrittäminen AAD:llä

Kun Snowflake-liittimeen perustuva raportti on julkaistu verkkoon, tietojoukon luojan on siirryttävä Power BI ‑palvelussa asianmukaiseen työtilaan, valittava “Tietojoukot” ja valittava sitten “Asetukset” (kyseisen tietojoukon viereisestä “...”-lisätoimintovalikosta).

Power BI:n toimintaperiaatteiden vuoksi kertakirjautuminen toimii ainoastaan silloin, kun tietolähteiden tietoja ei siirretä paikallisen tietoyhdyskäytävän kautta.

* Jos käytät tietomallissa ainoastaan Snowflake-lähdettä, voit käyttää kertakirjautumista, jos et halua käyttää paikallista tietoyhdyskäytävää
* Jos käytät Snowflake-lähdettä ja jotain muuta lähdettä, voit käyttää kertakirjautumista, jos mikään lähteistä ei käytä paikallista tietoyhdyskäytävää
* Jos käytät Snowflake-lähdettä paikallisen tietoyhdyskäytävän kautta, AAD-tunnistetiedot eivät ole tällä hetkellä tuettuja. Tällä voi olla merkitystä sellaisissa tapauksissa, että yrität päästä VNetiin yksittäisestä IP-osoitteesta, johon on asennettu yhdyskäytävä, sen sijaan että se olisi asennettu Power BI:n koko IP-osoitealueelle.
* Jos käytät Snowflake-lähdettä ja jotain muuta lähdettä, joka edellyttää yhdyskäytävää, sinun on käytettävä myös Snowflakea paikallisen tietoyhdyskäytävän kautta. Kertakirjautuminen ei tällöin onnistu.

Katso lisätiedot paikallisten tietoyhdyskäytävien käytöstä artikkelista [Mikä paikallinen tietoyhdyskäytävä on?](https://docs.microsoft.com/power-bi/service-gateway-onprem)

Jos et käytä yhdyskäytävää, kaikki on valmista. Jos Snowflake-tunnistetiedot on määritetty paikalliselle tietoyhdyskäytävälle, mutta käytät mallissasi ainoastaan kyseistä tietolähdettä, voit poistaa yhdyskäytävän käytöstä kyseisestä tietomallista napsauttamalla valintakytkintä Tietolähteen asetukset ‑sivulla.

![Tietojoukon asetus, jolla yhdyskäytävä poistetaan käytöstä](media/service-connect-snowflake/snowflake_gateway_toggle_off.png)

Tietojoukon luojan on valittava tietolähteen tunnistetiedot ja kirjauduttava sisään. Tietojoukko voidaan kirjata sisään Snowflakeen perus- tai OAuth2 (AAD) ‑tunnistetiedoilla. Jos päätät käyttää AAD:tä, kertakirjautuminen voidaan ottaa käyttöön tietojoukossa. Kun tämä ensimmäinen käyttäjä kirjautuu Snowflakeen käyttääkseen tietojoukkoa, hänen on valittava asetus, jonka avulla muut käyttäjät voivat noutaa tiedot Oauth2-tunnistetietonsa avulla. Tämä ottaa AAD-kertakirjautumisen käyttöön. AAD-tunnistetiedot lähetetään kertakirjautumisen yhteydessä riippumatta siitä, onko ensimmäinen käyttäjä kirjautunut sisään perustodennuksen vai OAuth2:n (AAD) avulla. 

![Snowflake-kertakirjautumisen tietojoukkoasetukset](media/service-connect-snowflake/snowflakessocredui.png)

Kun tämä on tehty, kaikkien muiden pitäisi käyttää automaattisesti AAD-todentamista yhdistäessään kyseisen Snowflake-tietojoukon tietoihin.

Jos et ota kertakirjautumista käyttöön, raportin päivittävät käyttäjät käyttävät kirjautuneen käyttäjän tunnistetietoja kuten useimmissa muissa Power BI ‑raporteissa.

### <a name="troubleshooting"></a>Vianmääritys

Jos integroinnin käyttämisessä ilmenee ongelmia, tutustu Snowflaken [vianmääritysoppaaseen](https://docs.snowflake.net/manuals/LIMITEDACCESS/oauth-powerbi.html#troubleshooting).

