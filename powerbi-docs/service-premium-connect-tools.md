---
title: Yhteyden muodostaminen Power BI Premium-tietojoukkoja, joilla asiakassovellusten ja työkalut (esikatselu)
description: Kuvataan, miten muodostat yhteyden Power BI Premium-tietojoukkoja asiakassovellusten ja työkalut.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 05/20/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 063f43cb2345ccb3d1fec5c414100beb8ccde451
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65941516"
---
# <a name="connect-to-datasets-with-client-applications-and-tools-preview"></a>Tietojoukkoihin asiakassovellusten ja työkalujen (esikatselu)

Työtilat ja tietojoukkojen tuki Power BI Premium *vain luku-* yhteydet Microsoftin ja kolmansien osapuolten sovelluksissa ja työkalut. 

> [!NOTE]
> Tämä artikkeli on tarkoitettu vain, jos haluat ottaa käyttöön vain luku-yhteys Power BI Premium-työtilojen ja tietojoukkoja. Se *ei ole* tarkoitus on tarkempia tietoja ohjelmoitavuusominaisuuden työkalut ja, arkkitehtuuri ja sovellusten hallinnan työtila ja tietojoukon. Tässä kuvattu rekisteröidyiksi edellyttävät tiedot siitä, että Analysis Services-taulukkomallissa tietokannan arkkitehtuuri ja hallinnan.

## <a name="protocol"></a>Protokolla

Käyttää Power BI Premium [XML for Analysis](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference) asiakassovellusten ja moduuli, joka hallitsee työtilat ja tietojoukkojen välinen tietoliikenne (XMLA)-protokollan. Ilmoitukset on kautta, mitä ovat kutsutaan yleisesti XMLA-päätepisteitä. XMLA on Microsoft Analysis Services-moduulia, joka käyttölupaa, toimii Power BI semanttisen mallinnus, hallinnon, elinkaaren ja tietojen hallinta käyttää samaa tietoliikennettä-protokollaa. 

Useimmissa sovelluksissa ja työkaluja, joilla ei eksplisiittisesti muodostaa moottorin käyttämällä XMLA-päätepisteitä. Käytä sen sijaan ne asiakaskirjastot, kuten MSOLAP, ADOMD-yhteyksien ja AMO asiakassovelluksen ja moduulia, joka viestii yksinomaan käyttämällä XMLA muodostettu.


## <a name="supported-tools"></a>Tuettuja työkaluja

Näiden työkalujen tukevat vain luku-oikeudet Power BI Premium-työtilojen ja tietojoukkojen:

**SQL Server Management Studio (SSMS)** -tukee DAX-, MDX-, XMLA- ja TraceEvent kyselyitä. Edellyttää versiota 18.0. Lataa [tähän](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms). 

**SQL Server Profiler** -mukana SSMS 18.0 (esikatselu), tämä työkalu tarjoaa seuranta ja virheenkorjauksen palvelimen tapahtumiin. Voi siepata ja Tallenna tiedosto tai taulukkoon analysoida myöhemmin tapahtuman tietoja. Kun tuote virallisesti vanhentunut SQL Server, Profiler jatkuu sisällytettävä ssms: ssä ja pysyy tuetut Analysis Services ja Power BI Premium nyt. Lisätietoja on artikkelissa [SQL Server Profiler](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler).

**DAX-Studio** – avoimen lähdekoodin yhteisön työkalu suoritetaan ja analysointi DAX-kyselyt Analysis Services-vastaan. Edellyttää 2.8.2 versio tai uudempi versio. Lisätietoja on artikkelissa [daxstudio.org](https://daxstudio.org/).

**Excelin pivot-taulukot** – pika-versio Office 16.0.11326.10000 tai uudempi on pakollinen.

**Kolmannen osapuolen** – sisältää asiakassovellukset tietojen visualisointi ja työkaluja, joiden avulla voit muodostaa yhteyden, kyselyn ja käyttää Power BI Premium-tietojoukkoja. Useimmat Työkalut edellyttävät MSOLAP-asiakaskirjastot uusimmat versiot, mutta jotkin voi käyttää ADOMD-yhteyksien.

## <a name="client-libraries"></a>Asiakaskirjastot

Asiakaskirjastot tarvitaan yhteyden muodostamiseen Power BI Premium-työtilojen asiakassovellusten ja työkalut. Power BI Premium tukee myös muodostaa yhteyden Analysis Services käyttää samaa asiakaskirjastot. Microsoft-asiakassovellusten, kuten Excel, SQL Server Management Studio (SSMS) ja SQL Server Data Tools (SSDT) asentaa kaikki kolme asiakaskirjastot ja päivitä ne. sekä säännöllisesti sovellusten päivitykset. Erityisesti kolmannen osapuolen sovellukset ja työkaluja, ja joissakin tapauksissa joudut ehkä asentaa asiakaskirjastot uudempia. Asiakaskirjastot päivitetään kuukausittain. Lisätietoja on artikkelissa [muodostettaessa yhteyttä Analysis Services-asiakaskirjastot](https://docs.microsoft.com/azure/analysis-services/analysis-services-data-providers).

## <a name="connecting-to-a-premium-workspace"></a>Yhteyden muodostaminen Premium-työtila

Voit muodostaa yhteyden työtilat määritetty varattu Premium-kapasiteetteja. Määritetty varattua kapasiteettia työtilat ovat yhteysmerkkijono URL-Osoitteen muoto. 

Saada Power BI-työtila-yhteysmerkkijono tässä **työtilan asetukset**edelleen **Premium** -välilehden **työtilan yhteyden**, valitse **kopioi**.

![Työtilan yhteysmerkkijono](media/service-premium-connect-tools/connect-tools-workspace-connection.png)

Työtilan yhteydet käyttämällä URL-muotoa osoite työtilan tavoin Analysis Services-palvelimen nimi:   
`powerbi://api.powerbi.com/v1.0/[tenant name]/[workspace name]` 

Esimerkiksi `powerbi://api.powerbi.com/v1.0/contoso.com/Sales Workspace`
> [!NOTE]
> `[workspace name]` on merkitsevä ja voi olla välilyöntejä. 

### <a name="to-connect-in-ssms"></a>Yhteyden ssms: ssä

- **Muodosta yhteys palvelimeen** > **palvelintyyppi**, valitse **Analysis Services-** . - **Palvelimen nimi**, anna URL-osoite. - **Todentamisen**, valitse **Active Directory - Universal MFA-tuen**, ja valitse sitten **käyttäjänimi**, anna organisaation käyttäjätunnuksesi. 

Kun yhteys on muodostettu, työtilan näytetään Analysis Services-palvelimeen ja työtilan tietojoukot näkyvät tietokantoja.  

![SSMS: SSÄ](media/service-premium-connect-tools/connect-tools-ssms.png)

### <a name="initial-catalog"></a>Alkuperäinen luettelo

Jotkin työkaluja, kuten SQL Server Profiler joudut ehkä määrittämään *alkuperäinen luettelo*. Määritä työtilan tietojoukko (tietokanta). - **Muodosta yhteys palvelimeen**, valitse **asetukset**. - **Muodosta yhteys palvelimeen** valintaikkunassa, **yhteyden ominaisuudet** -välilehden **tietokannan yhdistäminen**, tietojoukon nimi.

### <a name="duplicate-workspace-name"></a>Työtilan nimen kaksoiskappale

Kun muodostat yhteyden käyttäen samaa nimeä kuin työtiloissa työtilan, saatat saada seuraavan virheen: **Ei voi muodostaa yhteyttä powerbi://api.powerbi.com/v1.0/ [vuokraajan nimi] / [työtilan nimi].**

Voit kiertää tämän virheen lisäksi työtilan nimi määrittämällä käyttämiseen, joka voidaan kopioida URL-työtilan objectid-tunnus. Lisää yhteys URL-Osoitteeseen objectid-kohdetta. Esimerkiksi ”powerbi://api.powerbi.com/v1.0/myorg/Contoso myynti - 9d83d204 82a9-4b36-98f2-a40099093830'

### <a name="duplicate-dataset-name"></a>Tietojoukon nimen kaksoiskappale

Kun muodostat yhteyden tietojoukkoon käyttäen samaa nimeä kuin samassa työtilassa tietojoukosta, liitetään tietojoukon nimen tietojoukon GUID-tunnus. Saat tietojoukon sekä nimi *ja* GUID-tunnus, kun yhteys on muodostettu työtilan ssms: ssä. 

### <a name="delay-in-datasets-shown"></a>Tietojoukot näkyvät viive

Muodostettaessa yhteyttä työtilan muutokset uusi poistettu ja nimetty tietojoukoista voi kestää jopa viisi minuuttia näkyvät. 

### <a name="unsupported-datasets"></a>Ei tueta tietojoukkoja

Seuraavissa tietojoukoissa ei voi käyttää käyttämällä XMLA-päätepisteitä. Nämä tietojoukot *ei* näkyy työtilan ssms: ssä tai muissa työkaluissa: 

- Tietojoukkoja, joilla on reaaliaikainen yhteys Analysis Services-malleja. 
- Tietojoukkoja, joissa on tietojen siirtämiseen REST-Ohjelmointirajapinnan avulla.
- Excel-työkirjan tietojoukoista. 

Seuraavissa tietojoukoissa ei tueta Power BI-palvelussa:   

- Tietojoukot käyttäen reaaliaikaista yhteyttä Power BI-tietojoukkoon.

## <a name="audit-logs"></a>Valvontalokit 

Kun asiakassovellusten ja työkaluja, joilla yhteyden työtilaan, access XMLA-päätepisteiden kautta on kirjautunut sisään Power BI-valvontalokit **GetWorkspaces** toiminto. Lisätietoja on artikkelissa [valvonta Power BI-](service-admin-auditing.md).

## <a name="see-also"></a>Katso myös

[Analysis Services References](https://docs.microsoft.com/bi-reference/#pivot=home&panel=home-all)   
[SQL Server Management Studio](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-ssms)   
[SQL Server Analysis Services taulukkomuotoisia protokolla](https://docs.microsoft.com/openspecs/sql_server_protocols/ms-ssas-t/b98ed40e-c27a-4988-ab2d-c9c904fe13cf)   
[Dynaamista näkymät (DMVs)](https://docs.microsoft.com/sql/analysis-services/instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services)   


Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
