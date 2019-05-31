---
title: Mitä ovat sivutetut raportit Power BI Premiumissa? (esikatselu)
description: Sivutetut raportit, SQL Server Reporting Servicesin vakioraporttimuoto, ovat nyt käytettävissä Power BI -palvelussa. Nämä raportit voidaan tulostaa tai jakaa. Voit hallita raportin asettelua tarkasti. Ne näyttävät kaikki tiedot taulukossa, esimerkiksi vaikka taulukko käsittää useita sivuja.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: overview
ms.date: 05/20/2019
ms.openlocfilehash: 8da24bb8f7d3b8d507dbb6792556004083b673fe
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65991059"
---
# <a name="what-are-paginated-reports-in-power-bi-premium-preview"></a>Mitä ovat sivutetut raportit Power BI Premiumissa? (esikatselu)

Sivutetut raportit, SQL Server Reporting Servicesin vakioraporttimuoto, ovat nyt käytettävissä Power BI -palvelussa. Nämä raportit voidaan tulostaa tai jakaa. Niitä kutsutaan ”sivutetuiksi”, koska ne on muotoiltu sopimaan hyvin sivulle. Niissä kaikki tiedot näytetään taulukossa, vaikka taulukko olisi useita sivuja pitkä. Niitä kutsutaan joskus pikselintarkasti täydellisiksi, koska voit hallita tarkasti niiden asettelua raportin sivulla. Sivutetut raportit perustuvat SQL Server Reporting Servicesin RDL-raporttitekniikkaan. Raportin muodostin on erillinen työkalu sivutettujen raporttien luomiseen. 

Sivutetuissa raporteissa voi olla useita sivuja. Esimerkiksi tässä raportissa on 563 sivua. Jokainen sivu on aseteltu tarkasti yksi sivu laskua kohti -muotoon, ja ylä- ja alatunnisteet toistuvat kaikissa.

![Sivutettu raportti Power BI -palvelussa](media/paginated-reports-report-builder-power-bi/power-bi-paginated-wwi-report-page.png)

Voit esikatsella raporttisi raportin muodostimessa ja julkaista sen Power BI -palvelussa, http://app.powerbi.com. Tarvitset Power BI Pro -käyttöoikeuden raportin julkaisemiseksi palveluun. Voit julkaista ja jakaa sivutettuja raportteja omassa työtilassasi tai sovelluksen työtiloissa niin kauan kuin työtila on Power BI Premium -kapasiteetissa. Lisäksi Power BI -järjestelmänvalvojan on otettava sivutetut raportit käyttöön Power BI -hallintaportaalissa. 

## <a name="create-reports-in-power-bi-report-builder"></a>Luo raportteja Power BI-raportin muodostin

Sivutetut raportit on omat suunnittelutyökalu Power BI-raportin muodostin. Se on uusi työkalu, joka jakaa saman foundation kuin Työkalut, olet aiemmin käyttänyt Sivutettujen raporttien luomiseen Power BI-raporttipalvelimessa tai SQL Server Reporting Services (SSRS). SSRS 2016:lle ja 2017:lle tai Power BI -raporttipalvelimelle paikallisesti luomasi sivutetut raportit ovat itse asiassa yhteensopivia Power BI -palvelun kanssa. Power BI -palvelu ylläpitää yhteensopivuutta aikaisempien versioiden kanssa, joten voit siirtää raportteja uudempiin versioihin ja päivittää aiemman version sivutetut raportit. Kaikki raporttiominaisuudet eivät ole käytettävissä käynnistettäessä. Katso lisätietoja [rajoituksista ja huomioitavista seikoista](#limitations-and-considerations) tästä artikkelista.
     
## <a name="report-from-a-variety-of-data-sources"></a>Raportti useista eri tietolähteistä

Yksittäisellä sivutetulla raportilla voi olla useita eri tietolähteitä. Sen pohjana ei ole tietomallia, toisin kuin Power BI -raporteissa. Power BI -palvelun sivutettujen raporttien ensimmäisen julkaisun yhteydessä luot upotettuja tietolähteitä ja tietojoukkoja itse raporttiin. Tällä hetkellä et voi käyttää jaettuja tietolähteitä tai jaettuja tietojoukkoja. Voit luoda raportteja raportin muodostimessa paikallisella tietokoneellasi. Jos raportti on yhdistetty paikallisiin tietoihin, sinun on luotava yhdyskäytävä ja ohjattava tietoyhteys uudelleen sen jälkeen, kun olet ladannut raportin Power BI -palveluun. Tässä on tällä hetkellä voit muodostaa yhteyden tietolähteisiin:

- Azuren SQL-tietokanta ja tietovarasto
- Azure Analysis Services (kautta SSO)
- SQL Server yhdyskäytävän kautta
- SQL Server Analysis Services yhdyskäytävän kautta
- Power BI Premium-tietojoukot
- Oracle
- Teradata
 
Lisää tietolähteitä on tulossa esikatselun aikana.

## <a name="design-your-report"></a>Raportin suunnitteleminen  

### <a name="create-paginated-reports-with-matrix-chart-and-free-form-layouts"></a>Sivutettujen raporttien luominen matriisin, kaavion ja vapaamuotoisten asettelujen avulla

Taulukon raportit toimivat hyvin sarakepohjaisille tiedoille. Matriisiraportit, kuten rajavälilehti tai pivot-taulukon raportit, sopivat hyvin yhteenvetotiedoille. Kaavion raportit esittävät tiedot graafisessa muodossa ja vapaamuotoiset *luettelon* raportit voivat esittää lähes mitä tahansa muuta, kuten laskuja. 
  
Voit aloittaa jollakin raportin muodostimen ohjatuista toiminnoista. Ohjatut taulukko-, matriisi- ja kaaviotoiminnot käyvät läpi upotetun tietolähteen yhteyden ja upotetun tietojoukon luomisen. Sitten voit luoda tietojoukkokyselyn vetämällä ja pudottamalla kenttiä, valita asettelun ja tyylin ja mukauttaa raporttiasi.  
  
Ohjatun karttatoiminnon avulla voit luoda raportteja, jotka näyttävät koostetietoja maantieteellisellä tai geometrisellä taustalla. Karttatiedot voivat olla paikkatietoja Transact-SQL-kyselystä tai Environmental Systems Research Institute, Inc. (ESRI) -muototiedostosta. Voit myös lisätä Microsoft Bing -karttaruututaustan.  

### <a name="add-more-to-your-report"></a>Raportin täydentäminen

Muokkaa tietoja suodattamalla, ryhmittelemällä ja lajittelemalla tai lisäämällä kaavoja tai lausekkeita. Lisää kaavioita, mittareita, sparkline-kaavioita ja ilmaisimia tietojen yhteenvedon esittämiseksi visuaalisessa muodossa.  Suodata mukautettujen näkymien tietoja parametrien ja suodattimien avulla. Upota kuvia ja muita resursseja, myös ulkoista sisältöä, tai viittaa niihin.  

Koko sivutetun raportin sisällöllä itse raportista jokaiseen tekstiruutuun, kuvaan, taulukkoon ja kaavioon on monia ominaisuuksia, jotka voit määrittää, jotta raportti näyttää täsmälleen sellaiselta kuin haluat.

## <a name="creating-a-report-definition"></a>Raportin määrityksen luominen

Kun suunnittelet sivutetun raportin, luot tosiasiassa *raportin määrityksen*. Se ei sisällä tietoja. Se määrittää, mistä tiedot haetaan, mitkä tiedot haetaan ja miten tiedot näytetään. Kun raportti suoritetaan, raportin käsittely käyttää määrittämääsi raportin määritystä, noutaa tiedot ja yhdistää ne raportin asetteluun raportin luomiseksi. Lataat raportin määrityksen Power BI -palveluun, http://app.powerbi.com, omaan työtilaasi tai työtovereiden kanssa jakamaasi työtilaan. Jos raportin tietolähde on paikallinen, raportin lataamisen jälkeen ohjaat tietolähdeyhteyden uudelleen yhdyskäytävän kautta. 

## <a name="view-your-paginated-report"></a>Sivutetun raportin tarkasteleminen
Voit tarkastella sivutettua raporttia Power BI -palvelussa selaimella ja myös Power BI -mobiilisovelluksissa. Power BI -palvelusta käsin voit viedä raportin eri muodoissa, esimerkiksi HTML:nä, MHTML:nä, PDF:nä, XML:nä, CSV:nä, TIFF:nä, Wordinä ja Excelinä. Voit myös jakaa sen muiden kanssa.  

## <a name="create-a-subscription-to-your-report"></a>Tilauksen raportin luominen

Voit nyt määrittää itsellesi ja muille Sivutettujen raporttien sähköpostitilaukset Power BI-palvelussa. Yleensä prosessi on sama kuin tilaaminen raportteja ja koontinäyttöjä Power BI-palvelussa. Määritetään tilaukset, valitse kuinka usein haluat saada sähköpostiviestit: päivittäin, viikoittain tai tunnittaisten. Tilaus sisältää PDF-liitteen koko raportin tuloksen.

Lisätietoja on artikkelissa [itsellesi ja muille tilata sivutetut raportit Power BI-palvelussa](paginated-reports-subscriptions.md). 

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Tässä on joitakin muita ominaisuuksia, joita ei tueta ensimmäisessä julkaisussa:

- raporttisivujen tai visualisointien kiinnittäminen Power BI -raporttinäkymiin Voit edelleen kiinnittää visualisointeja Power BI -koontinäyttöön paikallisesta sivutetusta raportista Power BI -raporttipalvelimessa tai Reporting Services -raporttipalvelimessa. Katso lisätietoja artikkelista [Reporting Services -kohteiden kiinnittäminen Power BI -koontinäyttöihin](https://docs.microsoft.com/sql/reporting-services/pin-reporting-services-items-to-power-bi-dashboards).
- vuorovaikutteiset ominaisuudet, kuten asiakirjan rakenneruudut ja painikkeiden näyttäminen/piilottaminen
- aliraportit ja porautumisraportit
- jaetut tietolähteet ja jaetut tietojoukot
- visualisoinnit Power BI -raporteista
 
## <a name="next-steps"></a>Seuraavat vaiheet

- [Asenna Power BI-raportin muodostin Microsoft Download Centeristä](https://go.microsoft.com/fwlink/?linkid=2086513)
- [Opetusohjelma: Luo sivutettu raportti](paginated-reports-quickstart-aw.md)
- [Anna tiedot suoraan sivutettuun raporttiin](paginated-reports-enter-data.md)

  

