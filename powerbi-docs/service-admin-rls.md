---
title: Rivitason suojaus (RLS) Power BI:ssä
description: Rivitason suojauksen määrittäminen tuoduille tietojoukoille ja DirectQuerylle Power BI -palvelussa
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 01/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: fc832c25a2a4ff736c9c0f5b407c062ce63f22cc
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2018
---
# <a name="row-level-security-rls-with-power-bi"></a>Rivitason suojaus (RLS) Power BI:ssä
<iframe width="560" height="315" src="https://www.youtube.com/embed/67fK0GoVQ80?showinfo=0" frameborder="0" allowfullscreen></iframe>

Power BI:n rivitason suojauksen (RLS) avulla voidaan rajoittaa tietojen käyttöä tietyille käyttäjille. Suodattimet rajoittavat tietoja rivitasolla. Voit määrittää suodattimia roolien sisällä.

Voit määrittää rivitason suojauksen Power BI:hin tuoduille tietomalleille Power BI Desktopin avulla. Voit myös määrittää rivitason suojauksen tietojoukoille, jotka käyttävät DirectQueryä, kuten SQL Serveriä. Aiemmin pystyit ottamaan rivitason suojauksen käyttöön vain paikallisissa Analysis Services -malleissa Power BI:n ulkopuolella. Määrität rivitason suojauksen paikalliselle mallille Analysis Servicesin reaaliaikaisia yhteyksiä varten. Suojausvaihtoehtoa ei näy reaaliaikaisen yhteyden tietojoukoille.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

Oletuksena rivitason suojauksen suodatuksessa käytetään yksisuuntaisia suodattimia riippumatta siitä, onko suhteet määritetty yksi- vai kaksisuuntaisiksi. Voit ottaa kaksisuuntaisen ristisuodatuksen manuaalisesti käyttöön rivitason suojauksen yhteydessä valitsemalla suhteen ja valitsemalla **Ota suojaussuodattimet käyttöön molempiin suuntiin** -valintaruudun. Valitse tämä ruutu, kun otat käyttöön [dynaaminen rivitason suojauksen](https://docs.microsoft.com/en-us/sql/analysis-services/supplemental-lesson-implement-dynamic-security-by-using-row-filters), jossa rivitason suojaus määritetään käyttäjänimen tai kirjautumistunnuksen perusteella. 

Lisätietoja on artikkelissa [Kaksisuuntainen ristiinsuodatus käyttämällä DirectQueryä Power BI Desktopissa](desktop-bidirectional-filtering.md) ja teknisessä artikkelissa [Taulukkomuotoisen liiketoimintatietojen semanttisen mallin suojaaminen](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Securing the Tabular BI Semantic Model.docx).

![Suojaussuodattimen käyttäminen](media/service-admin-rls/rls-apply-security-filter.png)


[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

## <a name="manage-security-on-your-model"></a>Mallin suojauksen hallinta
Jotta voit hallita tietomallisi suojausta, sinun kannattaa toimia seuraavasti.

1. Valitse **ellipsi (...)**  tietojoukon kohdalta.
2. Valitse **Suojaus**.
   
   ![](media/service-admin-rls/rls-security.png)

Tämä siirtää sinut RLS-sivulle, jolla voit lisätä jäseniä Power BI Desktopissa luomaasi rooliin. Suojaus on vain tietojoukon omistajien käytettävissä. Jos tietojoukko on osa ryhmää, vain ryhmän järjestelmänvalvojat näkevät suojausvaihtoehdon. 

Voit vain luoda tai muokata rooleja Power BI Desktopissa.

## <a name="working-with-members"></a>Jäsenien käsitteleminen
### <a name="add-members"></a>Jäsenien lisääminen
Voit lisätä jäsenen rooliin kirjoittamalla lisättävän käyttäjän, suojausryhmän tai jakeluluettelon sähköpostiosoitteen tai nimen. Jäsenen on oltava organisaatiostasi. Et voi lisätä Power BI:ssä luotuja ryhmiä.

![](media/service-admin-rls/rls-add-member.png)

Roolin nimen tai jäsenten vieressä suluissa olevasta luvusta voit myös nähdä, kuinka monta jäsentä rooliin kuuluu.

![](media/service-admin-rls/rls-member-count.png)

### <a name="remove-members"></a>Jäsenien poistaminen
Voit poistaa jäseniä valitsemalla hänen nimensä vieressä olevan X-merkin. 

![](media/service-admin-rls/rls-remove-member.png)

## <a name="validating-the-role-within-the-power-bi-service"></a>Roolin vahvistaminen Power BI -palvelussa
Voit varmistaa, että määrittämäsi rooli toimii oikein, testaamalla roolin. 

1. Valitse roolin vieressä oleva **ellipsi (...)**.
2. Valitse **Testaa tietoja roolina**.

![](media/service-admin-rls/rls-test-role.png)

Näyttöön tulevat raportit, jotka ovat käytettävissä tälle roolille. Koontinäyttöjä ei esitetä tässä näkymässä. Yläosassa olevasta sinisestä palkista näet, mikä on käytössä.

![](media/service-admin-rls/rls-test-role2.png)

Voit testata muita rooleja tai roolien yhdistelmiä valitsemalla **Tarkastellaan nyt seuraavana**.

![](media/service-admin-rls/rls-test-role3.png)

Voit halutessasi tarkastella tietoja tiettynä henkilönä tai valita käytettävissä olevien roolien yhdistelmän ja vahvistaa, että ne toimivat. 

Palaa normaaliin näkymään valitsemalla **Takaisin rivitason suojaukseen**.

[!INCLUDE [include-short-name](./includes/rls-usernames.md)]

## <a name="using-rls-with-app-workspaces-in-power-bi"></a>Rivitason suojauksen käyttäminen sovelluksen työtilojen kanssa Power BI:ssä
Jos julkaiset Power BI Desktop -raportin sovelluksen työtilassa Power BI -palvelussa, roolit otetaan käyttöön vain luku -jäsenille. Sinun on määritettävä, että jäsenet voivat vain tarkastella Power BI -sisältöä sovelluksen työtilan asetuksissa.

> [!WARNING]
> Jos olet määrittänyt sovelluksen työtilan niin, että jäsenillä on muokkausoikeudet, RLS-rooleja ei sovelleta niihin. Käyttäjät voivat nähdä kaikki tiedot.
> 
> 

![](media/service-admin-rls/rls-group-settings.png)

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Seuraavat vaiheet
[Rivitason suojaus (RLS) Power BI Desktopissa](desktop-rls.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
