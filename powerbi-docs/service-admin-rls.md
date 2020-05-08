---
title: Rivitason suojaus (RLS) Power BI:ssä
description: Rivitason suojauksen määrittäminen tuoduille tietojoukoille ja DirectQuerylle Power BI -palvelussa
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.author: kfollis
ms.date: 12/05/2019
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 70f10620932708dd178b635f966a55f8139cde65
ms.sourcegitcommit: 220910f0b68cb1e265ccd5ac0cee4ee9c6080b26
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82841154"
---
# <a name="row-level-security-rls-with-power-bi"></a>Rivitason suojaus (RLS) Power BI:ssä

Power BI:n rivitason suojauksen (RLS) avulla voidaan rajoittaa tietojen käyttöä tietyille käyttäjille. Suodattimet rajoittavat tietojen käyttöä rivitasolla ja voit määrittää roolien sisäisiä suodattimia. Huomioi, että Power BI -palvelussa työtilan jäsenillä on pääsy työtilan tietojoukkoihin. Rivitason suojaus ei rajoita näiden tietojen käyttöoikeuksia.

Voit määrittää rivitason suojauksen Power BI:hin tuoduille tietomalleille Power BI Desktopin avulla. Voit myös määrittää rivitason suojauksen tietojoukoille, jotka käyttävät DirectQueryä, kuten SQL Serveriä. Aiemmin pystyit ottamaan rivitason suojauksen käyttöön vain paikallisissa Analysis Services -malleissa Power BI:n ulkopuolella. Reaaliaikaisia Analysis Services- tai Azure Analysis Services -yhteyksiä varten rivitason suojaus määritetään mallissa, ei Power BI Desktopissa. Suojausvaihtoehtoa ei näy reaaliaikaisen yhteyden tietojoukoille.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

Oletuksena rivitason suojauksen suodatuksessa käytetään yksisuuntaisia suodattimia riippumatta siitä, onko suhteet määritetty yksi- vai kaksisuuntaisiksi. Voit ottaa kaksisuuntaisen ristisuodatuksen manuaalisesti käyttöön rivitason suojauksen yhteydessä valitsemalla suhteen ja valitsemalla **Ota suojaussuodattimet käyttöön molempiin suuntiin** -valintaruudun. Valitse tämä ruutu, kun olet ottanut käyttöön myös dynaaminen rivitason suojauksen palvelintasolla, jossa rivitason suojaus perustu käyttäjänimeen tai kirjautumistunnukseen.

Lisätietoja on artikkelissa [Kaksisuuntainen ristiinsuodatus käyttämällä DirectQueryä Power BI Desktopissa](desktop-bidirectional-filtering.md) ja teknisessä artikkelissa [Taulukkomuotoisen liiketoimintatietojen semanttisen mallin suojaaminen](https://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Securing%20the%20Tabular%20BI%20Semantic%20Model.docx).

![Suojaussuodattimen käyttäminen](media/service-admin-rls/rls-apply-security-filter.png)


[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

## <a name="manage-security-on-your-model"></a>Mallin suojauksen hallinta

Jotta voit hallita tietomallisi suojausta, sinun kannattaa toimia seuraavasti.

1. Valitse **ellipsi (...)**  tietojoukon kohdalta.
2. Valitse **Suojaus**.
   
   ![Ota suojaussuodattimet käyttöön molempiin suuntiin](media/service-admin-rls/rls-security.png)

Tämä siirtää sinut RLS-sivulle, jolla voit lisätä jäseniä Power BI Desktopissa luomaasi rooliin. Suojaus on vain tietojoukon omistajien käytettävissä. Jos tietojoukko on osa ryhmää, vain ryhmän järjestelmänvalvojat näkevät suojausvaihtoehdon. 

Voit vain luoda tai muokata rooleja Power BI Desktopissa.

## <a name="working-with-members"></a>Jäsenien käsitteleminen

### <a name="add-members"></a>Jäsenien lisääminen

Voit lisätä jäsenen rooliin kirjoittamalla lisättävän käyttäjän, suojausryhmän tai jakeluluettelon sähköpostiosoitteen tai nimen. Et voi lisätä Power BI:ssä luotuja ryhmiä. Voit lisätä jäseniä, jotka ovat [organisaatiosi ulkopuolisia henkilöitä](guidance/whitepaper-azure-b2b-power-bi.md#data-security-for-external-partners).

![Lisää jäsen](media/service-admin-rls/rls-add-member.png)

Roolin nimen tai jäsenten vieressä suluissa olevasta luvusta voit myös nähdä, kuinka monta jäsentä rooliin kuuluu.

![Roolin jäsenet](media/service-admin-rls/rls-member-count.png)

### <a name="remove-members"></a>Jäsenien poistaminen

Voit poistaa jäseniä valitsemalla hänen nimensä vieressä olevan X-merkin. 

![Poista jäsen](media/service-admin-rls/rls-remove-member.png)

## <a name="validating-the-role-within-the-power-bi-service"></a>Roolin vahvistaminen Power BI -palvelussa

Voit varmistaa, että määrittämäsi rooli toimii oikein, testaamalla roolin. 

1. Valitse **Enemmän vaihtoehtoja** (...) roolin vierestä.
2. Valitse **Testaa tietoja roolina**.

![Testaa roolina](media/service-admin-rls/rls-test-role.png)

Näyttöön tulevat raportit, jotka ovat käytettävissä tälle roolille. Koontinäyttöjä ei esitetä tässä näkymässä. Yläosassa olevasta sinisestä palkista näet, mikä on käytössä.

![Tarkastellaan nyt seuraavana: <role>](media/service-admin-rls/rls-test-role2.png)

Voit testata muita rooleja tai roolien yhdistelmiä valitsemalla **Tarkastellaan nyt seuraavana**.

![Testaa muita rooleja](media/service-admin-rls/rls-test-role3.png)

Voit halutessasi tarkastella tietoja tiettynä henkilönä tai valita käytettävissä olevien roolien yhdistelmän ja vahvistaa, että ne toimivat. 

Palaa normaaliin näkymään valitsemalla **Takaisin rivitason suojaukseen**.

[!INCLUDE [include-short-name](./includes/rls-usernames.md)]

## <a name="using-rls-with-workspaces-in-power-bi"></a>Rivitason suojauksen käyttäminen työtilojen kanssa Power BI:ssä

Jos julkaiset Power BI Desktop -raportin työtilassa Power BI -palvelussa, roolit otetaan käyttöön vain luku -jäsenille. Sinun on määritettävä, että jäsenet voivat vain tarkastella Power BI -sisältöä työtilan asetuksissa.

> [!WARNING]
> Jos olet määrittänyt työtilan niin, että jäsenillä on muokkausoikeudet, RLS-rooleja ei sovelleta niihin. Käyttäjät voivat nähdä kaikki tiedot.

![Ryhmän asetukset](media/service-admin-rls/rls-group-settings.png)

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Seuraavat vaiheet
[Rivitason suojaus (RLS) Power BI Desktopissa](desktop-rls.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
