---
title: Dynaaminen rivitason suojaus Analysis Servicen taulukkomallissa
description: Dynaaminen rivitason suojaus Analysis Servicen taulukkomallissa
author: selvarms
ms.reviewer: davidi
editor: davidi
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 05/28/2019
ms.author: selvar
LocalizationGroup: Connect to data
ms.openlocfilehash: 09e4a9cc3e6a5c16f23532f0a4589fdcb1906549
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/09/2020
ms.locfileid: "75759516"
---
# <a name="implement-row-level-security-in-an-analysis-services-tabular-model"></a>Rivitason suojauksen käyttöönotto Analysis Servicen taulukkomallissa

Tässä opetusohjelmassa näytetään esimerkkitietojoukon avulla, miten voit toteuttaa [**rivitason suojauksen**](service-admin-rls.md)**Analysis Services -taulukkomallissa** ja käyttää sitä Power BI -raportissa. 

* Luo uusi suojaustaulukko [**AdventureworksDW2012**-tietokannassa](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)
* Kokoa taulukkomalli tarvittavilla fakta- ja dimensiotaulukoilla
* Määritä käyttäjäroolit ja oikeudet
* Ota käyttöön **Analysis Services -taulukkoesiintymän** malli
* Laadi Power BI Desktopin -raportti, jossa näytetään raporttia käsittelevälle käyttäjälle räätälöidyt tiedot
* Ota raportti käyttöön **Power BI -palvelussa**
* Luo raporttiin perustuva uusi koontinäyttö
* jaa koontinäyttö työtovereille 

Tämä opetusohjelma edellyttää [**AdventureworksDW2012**-tietokantaa](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).

## <a name="task-1-create-the-user-security-table-and-define-data-relationship"></a>Tehtävä 1: Käyttäjän tietoturvataulukon luominen ja tietojen yhteyden määrittäminen

Lukuiset artikkelit opastavat rivitason dynaamisen suojauksen määrittämisessä **taulukkomuotoiseen SQL Server Analysis Services (SSAS)** -malliin. Tässä esimerkissä käytämme [Dynaamisen suojauksen toteuttaminen rivisuodattimien avulla](https://docs.microsoft.com/analysis-services/tutorial-tabular-1200/supplemental-lesson-implement-dynamic-security-by-using-row-filters) -artikkelin ohjeita. 

Nämä ohjeet edellyttävät **AdventureworksDW2012**-relaatiotietokannan käyttöä.

1. Luo **AdventureworksDW2012**-tietokannassa **DimUserSecurity**-taulukko alla kuvatulla tavalla. Tässä esimerkissä taulukon luomiseen käytetään [SQL Server Management Studiota (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms).
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable.png)

2. Kun taulukko on luotu ja tallennettu, sinun on luotava suhde **DimUserSecurity**-taulukon **SalesTerritoryID**-sarakkeen ja **DimSalesTerritory**-taulukon **SalesTerritoryKey**-sarakkeen välille alla kuvatulla tavalla. 

   Napsauta **SSMS**:ssä **DimUserSecurity**-taulukkoa hiiren kakkospainikkeella ja valitse **Rakenne**. Valitse sitten **Taulukon suunnittelu -> Suhteet...** . Kun olet valmis, tallenna taulukko.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_keys.png)

3. Käyttäjien lisääminen taulukkoon: napsauta hiiren kakkospainikkeella **DimUserSecurity**-taulukkoa ja valitse **Muokkaa 200 ylintä riviä**. Kun olet lisännyt käyttäjät, **DimUserSecurity**-taulukon pitäisi vastata seuraavaa (omilla käyttäjilläsi):
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_users.png)
   
   Näet kyseiset käyttäjät myös myöhemmissä tehtävissä.

4. Tee seuraavaksi *sisäliitos***DimSalesTerritory**-taulukon kanssa. Taulukon avulla näet käyttäjän alueeseen liittyvät tiedot. Tämä SQL-koodi tekee *sisäliitoksen*. Kuvasta ilmenee, miltä taulukko tulee näyttämään.
   
       select b.SalesTerritoryCountry, b.SalesTerritoryRegion, a.EmployeeID, a.FirstName, a.LastName, a.UserName from [dbo].[DimUserSecurity] as a join  [dbo].[DimSalesTerritory] as b on a.[SalesTerritoryID] = b.[SalesTerritoryKey]
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_join_users.png)

   **Vaiheessa 2** luodun suhteen ansiosta kuvassa näkyy kunkin myyntialueen vastuuhenkilö. Esimerkiksi **Jon Doe** on vastuussa **Australian** myyntialueesta. 

## <a name="task-2-create-the-tabular-model-with-facts-and-dimension-tables"></a>Tehtävä 2: Kokoa taulukkomalli fakta- ja dimensiotaulukoilla

1. Kun relaatiotietovarasto on paikallaan, sinun on määritettävä taulukkomalli. Voit luoda mallin [**SQL Server Data Tools (SSDT)** ](https://docs.microsoft.com/sql/ssdt/sql-server-data-tools) -työkaluilla. Katso lisätiedot [Uuden taulukkomalliprojektin luominen](https://msdn.microsoft.com/library/hh231689.aspx) -artikkelista.

2. Tuo kaikki tarvittavat taulukot malliin alla kuvatulla tavalla.
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/ssdt_model.png)

3. Kun olet tuonut tarvittavat taulukot, sinun on määritettävä rooli nimeltä **SalesTerritoryUsers**, jolla on **Luku**-käyttöoikeudet. Valitse **Malli**-valikko SQL Server Data Tools -työkaluissa ja valitse sitten **Roolit**. Valitse **Roolinhallinta**-valintaikkunasta **Uusi**.

4. Lisää **Roolinhallinnan** **Jäsenet**-välilehdellä käyttäjät, jotka määritettiin **DimUserSecurity**-taulukkoon **Tehtävän 1 vaiheessa 3**.
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager.png)

5. Lisää seuraavaksi asianmukaiset funktiot sekä **DimSalesTerritory**- että **DimUserSecurity**-taulukoihin alla **Rivisuodattimet**-välilehdellä osoitetulla tavalla.
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager_complete.png)

6. Tässä vaiheessa käytetään **LOOKUPVALUE**-funktiota palauttamaan arvot sarakkeelle, jossa Windows-käyttäjänimi on sama kuin **USERNAME**-funktion palauttama käyttäjänimi. Voit sitten rajoittaa kyselyt alueisiin, joissa **LOOKUPVALUE**-funktion palauttamat arvot vastaavat liittyvän taulukon arvoja. Kirjoita seuraava kaava **DAX-suodattimen** sarakkeeseen:
   
       =DimSalesTerritory[SalesTerritoryKey]=LOOKUPVALUE(DimUserSecurity[SalesTerritoryID], DimUserSecurity[UserName], USERNAME(), DimUserSecurity[SalesTerritoryID], DimSalesTerritory[SalesTerritoryKey])

    Tässä kaavassa **LOOKUPVALUE**-funktio palauttaa kaikki arvot **DimUserSecurity[SalesTerritoryID]** -sarakkeesta, jossa **DimUserSecurity[UserName]** on nykyinen kirjautunut Windows-käyttäjänimi ja **DimUserSecurity[SalesTerritoryID]** on sama kuin **DimSalesTerritory[SalesTerritoryKey]** .
   
    > [!IMPORTANT]
    > DAX-funktiota [USERELATIONSHIP](https://msdn.microsoft.com/query-bi/dax/userelationship-function-dax) ei tueta rivitason suojausta käytettäessä.

   SalesTerritoryKey-arvon **LOOKUPVALUE**-arvonpalauttamia myyntijoukkojen avulla rajoitetaan **DimSalesTerritory**-kentässä näytettäviä rivejä. Vain sellaiset rivit näytetään, joissa rivin **SalesTerritoryKey** sisältyy **LOOKUPVALUE**-funktion palauttamiin tunnuksiin.

7. Kirjoita seuraava kaava **DimUserSecurity**-taulukon **DAX-suodattimen** sarakkeeseen:
   
       =FALSE()

    Tämä kaava määrittää, että kaikkien sarakkeiden ratkaisu on `false`. Se tarkoittaa, että **DimUserSecurity**-taulukon sarakkeista ei voi tehdä hakuja.

8. Seuraavaksi malli käsitellään ja otetaan käyttöön. Katso lisätietoja [Käyttöönotto-artikkelista](https://msdn.microsoft.com/library/hh231693.aspx).

## <a name="task-3-add-data-sources-within-your-on-premises-data-gateway"></a>Tehtävä 3: Tietolähteiden lisääminen paikallisessa tietoyhdyskäytävässä

Kun taulukkomuotoinen malli on otettu käyttöön ja valmis yleiseen käyttöön, sinun on lisättävä tietolähdeyhteys paikalliseen Analysis Services -taulukkopalvelimeen.

1. Jotta voit antaa **Power BI -palvelulle** paikallisen analysointipalvelun käyttöoikeudet, **[paikallisen tietoyhdyskäytävän](service-gateway-onprem.md)** on oltava asennettuna ja määritettynä ympäristöösi.

2. Kun yhdyskäytävä on määritetty oikein, sinun on luotava tietolähdeyhteys **Analysis Services** -palvelun taulukkomuotoisiin esiintymiin. Katso lisätietoja artikkelista [Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md).
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_gateway.png)

  Kun edellinen vaihe on valmis, yhdyskäytävä on määritetty ja valmis käsittelemään **Analysis Services** -tietolähdettä.

## <a name="task-4-create-report-based-on-analysis-services-tabular-model-using-power-bi-desktop"></a>Tehtävä 4: Analyysipalveluiden taulukkomalliin perustuvan raportin luominen Power BI Desktopilla

1. Käynnistä **Power BI Desktop** ja valitse **Nouda tiedot > Tietokanta**.

2. Valitse tietolähteiden luettelosta **SQL Server Analysis Services -tietokanta** ja valitse **Yhdistä**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata.png)

3. Täytä taulukkomuotoisen **Analysis Services-** -esiintymän tiedot ja valitse **Yhdistä reaaliajassa**. Valitse **OK**. Dynaaminen suojaus toimii **Power BI:ssä** vain **reaaliaikaisella yhteydellä**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)

4. Käyttöön otettu malli on nyt **Analysis Services** -esiintymässä. Valitse asianmukainen malli ja sitten **OK**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)

   **Power BI Desktop** näyttää nyt kaikki käytettävissä olevat kentät **Kentät**-ruudun oikeanpuoleisessa pohjassa.

5. Valitse oikealla olevasta **Kentät**-ruudussa olevasta **FactInternetSales**-taulukosta **SalesAmount**-mittari ja **SalesTerritory**-taulukosta **SalesTerritoryRegion**-dimensio.

6. Emme tällä kertaa lisää enempää sarakkeita, jotta raportista ei tule liian monimutkainen. Tiedot esitetään kuvaavammin, kun visualisointi muutetaan **rengaskaavioksi**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart.png)

7. Kun raportti on valmis, voit julkaista sen suoraan Power BI -portaaliin. Valitse **Power BI Desktopin** **Aloitus**-valintanauhasta **Julkaise**.

## <a name="task-5-create-and-share-a-dashboard"></a>Tehtävä 5: Koontinäytön luominen ja jakaminen

1. Olet luonut raportin ja julkaissut sen **Power BI** -palveluun. Nyt voit käyttää edellisissä vaiheissa luotua esimerkkiä mallin suojaustilanteen havainnollistamiseen.
   
   **Myyntipäällikön** roolinsa ansiosta Sumit voit nähdä kaikkien eri myyntialueiden tiedot. Sumit luo tämän raportin (tehtävän edellisissä vaiheissa luotu raportti) ja julkaisee sen Power BI -palveluun.
   
   Kun Sumit julkaisee raportin, seuraavaksi hän luo Power BI -palveluun koontinäytön, jonka nimi on raportin perusteella **TabularDynamicSec**. Huomaa, että seuraavassa kuvassa Sumit voi nähdä kaikkien myyntialueiden tiedot.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart_1.png)

2. Nyt Sumit jakaa koontinäytön työtoverilleen Jon Doelle, joka vastaa Australian alueen myynnistä.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/user_jon_doe.png)
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_dashboard.png)

3. Kun Jon Doe kirjautuu sisään **Power BI** -palveluun ja tarkastelee Sumitin luomaa jaettua koontinäyttöä, **ainoastaan** hänen oman vastuualueensa myynnin pitäisi olla näkyvissä. 
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/dashboard_jon_doe.png)

    Onnittelut! **Power BI-palvelussa** näytetään paikallisessa **Analysis Services** -taulukkomallissa määritetty dynaaminen rivitason suojaus. Power BI käyttää **effectiveusername**-ominaisuutta lähettäessään senhetkisen Power BI -käyttäjän kirjautumistiedot paikalliselle tietolähteelle kyselyiden suorittamiseksi.

## <a name="task-6-understand-what-happens-behind-the-scenes"></a>Tehtävä 6: Taustalla tapahtuvien toimintojen ymmärtäminen

Tässä tehtävässä oletetaan, että [SQL Profiler](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler) on sinulle tuttu, koska sinun on tallennettava SQL Server profiler -jäljitys paikallisesta, taulukkomuotoisesta SSAS -esiintymästä.

1. Istunto käynnistetään heti, kun käyttäjä (Jon Doe) käyttää koontinäyttöä Power BI -palvelussa. Huomaat, että **salesterritoryusers**-rooli astuu heti voimaan. Käytettävä käyttäjänimi on **<EffectiveUserName>jondoe@moonneo.com</EffectiveUserName>**
   
       <PropertyList><Catalog>DefinedSalesTabular</Catalog><Timeout>600</Timeout><Content>SchemaData</Content><Format>Tabular</Format><AxisFormat>TupleFormat</AxisFormat><BeginRange>-1</BeginRange><EndRange>-1</EndRange><ShowHiddenCubes>false</ShowHiddenCubes><VisualMode>0</VisualMode><DbpropMsmdFlattened2>true</DbpropMsmdFlattened2><SspropInitAppName>PowerBI</SspropInitAppName><SecuredCellValue>0</SecuredCellValue><ImpactAnalysis>false</ImpactAnalysis><SQLQueryMode>Calculated</SQLQueryMode><ClientProcessID>6408</ClientProcessID><Cube>Model</Cube><ReturnCellProperties>true</ReturnCellProperties><CommitTimeout>0</CommitTimeout><ForceCommitTimeout>0</ForceCommitTimeout><ExecutionMode>Execute</ExecutionMode><RealTimeOlap>false</RealTimeOlap><MdxMissingMemberMode>Default</MdxMissingMemberMode><DisablePrefetchFacts>false</DisablePrefetchFacts><UpdateIsolationLevel>2</UpdateIsolationLevel><DbpropMsmdOptimizeResponse>0</DbpropMsmdOptimizeResponse><ResponseEncoding>Default</ResponseEncoding><DirectQueryMode>Default</DirectQueryMode><DbpropMsmdActivityID>4ea2a372-dd2f-4edd-a8ca-1b909b4165b5</DbpropMsmdActivityID><DbpropMsmdRequestID>2313cf77-b881-015d-e6da-eda9846d42db</DbpropMsmdRequestID><LocaleIdentifier>1033</LocaleIdentifier><EffectiveUserName>jondoe@moonneo.com</EffectiveUserName></PropertyList>

2. Analysis Services muuntaa pyynnön käytettävän käyttäjänimen pyynnön perusteella moonneo\jondoe-kirjautumistunnuksiksi paikallisen Active Directory -hakemiston kyselyn jälkeen. Kun **Analysis Services** saa tunnistetiedot, **Analysis Services** palauttaa tiedot, joita käyttäjällä on oikeus käyttää.

3. Jos koontinäytössä tapahtuu muuta toimintaa, esimerkiksi jos Jon Doe siirtyy koontinäytöstä sen pohjana olevaan raporttiin, Analysis Services -taulukkomalliin palautettava kysely näkyy SQL Profilerissa DAX-kyselynä.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/profiler1.png)

4. Alla näet myös DAX-kyselyn, joka suoritetaan raportin tietojen täyttämiseksi.
   
   ```
   EVALUATE
     ROW(
       "SumEmployeeKey", CALCULATE(SUM(Employee[EmployeeKey]))
     )
   
   <PropertyList xmlns="urn:schemas-microsoft-com:xml-analysis">``
             <Catalog>DefinedSalesTabular</Catalog>
             <Cube>Model</Cube>
             <SspropInitAppName>PowerBI</SspropInitAppName>
             <EffectiveUserName>jondoe@moonneo.com</EffectiveUserName>
             <LocaleIdentifier>1033</LocaleIdentifier>
             <ClientProcessID>6408</ClientProcessID>
             <Format>Tabular</Format>
             <Content>SchemaData</Content>
             <Timeout>600</Timeout>
             <DbpropMsmdRequestID>8510d758-f07b-a025-8fb3-a0540189ff79</DbpropMsmdRequestID>
             <DbPropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbPropMsmdActivityID>
             <ReturnCellProperties>true</ReturnCellProperties>
             <DbpropMsmdFlattened2>true</DbpropMsmdFlattened2>
             <DbpropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbpropMsmdActivityID>
           </PropertyList>
   ```

## <a name="considerations"></a>Huomioitavaa

* Paikallinen rivitason suojaus toimii Power BI:ssä vain reaaliaikaisella yhteydellä.

* Malliin käsittelyn jälkeen tehdyt muutokset ovat heti käyttäjien (jotka käsittelevät raporttia **reaaliaikaisella yhteydellä**) käytettävissä Power BI -palvelussa.

