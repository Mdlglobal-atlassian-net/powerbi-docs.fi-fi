---
title: Mitä ovat sivutetut raportit Power BI Premiumissa? (esikatselu)
description: Sivutetut raportit ovat raportteja, joita voidaan tulostaa tai jakaa. Voit hallita raportin asettelua tarkasti. Ne näyttävät kaikki tiedot taulukossa, esimerkiksi vaikka taulukko käsittää useita sivuja.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: report-builder
ms.topic: overview
ms.date: 11/08/2018
ms.author: maggies
ms.openlocfilehash: 15ec21a0b86977173c16071980d7527f27db74ef
ms.sourcegitcommit: 5eb0f37f59b5fec15c0caecbbd1f8d688c7f0013
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2018
ms.locfileid: "51297040"
---
# <a name="what-are-paginated-reports-in-power-bi-premium-preview"></a>Mitä ovat sivutetut raportit Power BI Premiumissa? (esikatselu)
Sivutetut raportit, SQL Server Reporting Servicesin vakioraporttimuoto, ovat nyt käytettävissä Power BI -palvelussa. Sivutetut raportit ovat raportteja, jotka on suunniteltu tulostettaviksi tai jaettaviksi. Niitä kutsutaan sivutetuiksi, koska ne sopivat muodoltaan hyvin sivulle ja näyttävät kaikki tiedot taulukossa, esimerkiksi vaikka taulukko käsittää useita sivuja. Niitä kutsutaan joskus pikselintarkasti täydellisiksi, koska voit hallita tarkasti niiden asettelua raportin sivulla. Sivutetut raportit perustuvat SQL Server Reporting Servicesin RDL-raporttitekniikkaan. Raportin muodostin on erillinen työkalu sivutettujen raporttien luomiseen. 

Sivutetuissa raporteissa voi olla useita sivuja. Seuraavassa esimerkissä raportissa on 563 sivua, joista jokainen on aseteltu tarkasti yksi sivu laskua kohti ja ylä- ja alatunnisteet toistuvat kaikissa.

![Sivutettu raportti Power BI -palvelussa](media/paginated-reports-report-builder-power-bi/power-bi-paginated-wwi-report-page.png)

Voit esikatsella raporttisi raportin muodostimessa ja julkaista sen Power BI -palvelussa, http://app.powerbi.com. Tarvitset Power BI Pro -käyttöoikeuden raportin julkaisemiseksi palveluun. Voit julkaista ja jakaa sivutettuja raportteja omassa työtilassasi tai sovelluksen työtiloissa niin kauan kuin työtila on Power BI Premium -kapasiteetissa. Lisäksi Power BI -järjestelmänvalvojan on otettava sivutetut raportit käyttöön Power BI -hallintaportaalissa. Lue lisää [kuormituksien määrittämisestä](service-admin-premium-manage.md#configure-workloads). 

## <a name="create-reports-in-report-builder"></a>Raporttien luominen raportin muodostimessa

Sivutetuilla raporteilla on oma suunnittelutyökalu, raportin muodostin. Jos olet luonut sivutettuja raportteja Power BI -raporttipalvelimeen tai SQL Server Reporting Servicesiin (SSRS), voit käyttää samaa työkalua ja samaa versiota. SSRS 2016:lle ja 2017:lle tai Power BI -raporttipalvelimelle paikallisesti luomasi sivutetut raportit ovat itse asiassa yhteensopivia Power BI -palvelun kanssa. Power BI -palvelu ylläpitää yhteensopivuutta aikaisempien versioiden kanssa, joten voit siirtää raportteja uudempiin versioihin ja päivittää aiemman version sivutetut raportit. Kaikki raporttiominaisuudet eivät ole saatavana julkaistaessa. Lisätietoja on tämän artikkelin kohdassa [Rajoitukset ja huomioitavat asiat](#limitations-and-considerations).
     
## <a name="report-from-a-variety-of-data-sources"></a>Raportti useista eri tietolähteistä

Yksittäisellä sivutetulla raportilla voi olla useita eri tietolähteitä. Sen pohjana ei ole tietomallia, toisin kuin Power BI -raporteissa. Power BI -palvelun sivutettujen raporttien ensimmäisen julkaisun yhteydessä luot upotettuja tietolähteitä ja tietojoukkoja itse raporttiin jaettujen tietolähteiden tai tietojoukkojen palvelimeen yhdistämisen sijaan. Voit luoda raportteja raportin muodostimessa paikallisella tietokoneellasi. Jos raportti on yhdistetty paikallisiin tietoihin, sinun on luotava yhdyskäytävä ja ohjattava tietoyhteys uudelleen sen jälkeen, kun olet ladannut raportin Power BI -palveluun. Voit muodostaa yhteyden seuraaviin tietolähteisiin ensimmäisen julkaisun yhteydessä:

- Azuren SQL-tietokanta ja tietovarasto
- SQL Server yhdyskäytävän kautta
- SQL Server Analysis Services yhdyskäytävän kautta
 
Lisää tietolähteitä on tulossa esikatselun aikana.

## <a name="design-your-report"></a>Raportin suunnitteleminen  

### <a name="create-paginated-reports-with-matrix-chart-and-free-form-layouts"></a>Sivutettujen raporttien luominen matriisin, kaavion ja vapaamuotoisten asettelujen avulla

Luo taulukkoraportteja sarakepohjaisille tiedoille, matriisiraportteja (kuten välilehtien välisiä raportteja tai pivot-taulukkoraportteja) yhteenvedetyille tiedoille, kaavioraportteja graafisille tiedoille ja vapaamuotoisia *luetteloraportteja* kaikille muille, kuten laskuille. 
  
Voit aloittaa jollakin raportin muodostimen ohjatuista toiminnoista. Ohjatut taulukko-, matriisi- ja kaaviotoiminnot käyvät läpi upotetun tietolähteen yhteyden ja upotetun tietojoukon luomisen. Sitten voit luoda tietojoukkokyselyn vetämällä ja pudottamalla kenttiä, valita asettelun ja tyylin ja mukauttaa raporttiasi.  
  
Ohjatun karttatoiminnon avulla voit luoda raportteja, jotka näyttävät koostetietoja maantieteellisellä tai geometrisellä taustalla. Karttatiedot voivat olla paikkatietoja Transact-SQL-kyselystä tai Environmental Systems Research Institute, Inc:n (ESRI) muototiedostosta. Voit myös lisätä Microsoft Bing -karttaruututaustan.  

### <a name="add-more-to-your-report"></a>Raportin täydentäminen

Muokkaa tietoja suodattamalla, ryhmittelemällä ja lajittelemalla tai lisäämällä kaavoja tai lausekkeita. Lisää kaavioita, mittareita, sparkline-kaavioita ja ilmaisimia tietojen yhteenvedon esittämiseksi visuaalisessa muodossa.  Suodata mukautettujen näkymien tietoja parametrien ja suodattimien avulla. Upota kuvia ja muita resursseja, myös ulkoista sisältöä, tai viittaa niihin.  

Koko sivutetun raportin sisällöllä itse raportista jokaiseen tekstiruutuun, kuvaan, taulukkoon ja kaavioon on monia ominaisuuksia, jotka voit määrittää, jotta raportti näyttää täsmälleen sellaiselta kuin haluat.

## <a name="creating-a-report-definition"></a>Raportin määrityksen luominen

Kun suunnittelet sivutetun raportin, luot tosiasiassa *raportin määrityksen*. Se ei sisällä tietoja. Se määrittää, mistä tiedot haetaan, mitkä tiedot haetaan ja miten tiedot näytetään. Kun raportti suoritetaan, raportin käsittely käyttää määrittämääsi raportin määritystä, noutaa tiedot ja yhdistää ne raportin asetteluun raportin luomiseksi. Lataat raportin määrityksen Power BI -palveluun, http://app.powerbi.com, omaan työtilaasi tai työtovereiden kanssa jakamaasi työtilaan. Jos raportin tietolähde on paikallinen, raportin lataamisen jälkeen ohjaat tietolähdeyhteyden uudelleen yhdyskäytävän kautta. 

## <a name="view-your-paginated-report"></a>Sivutetun raportin tarkasteleminen
Voit tarkastella sivutettua raporttia Power BI -palvelussa selaimella ja myös Power BI -mobiilisovelluksissa. Power BI -palvelussa voit viedä raportin useisiin verkko- ja sivupohjaisiin ja työpöytäsovellusmuotoihin, kuten HTML, MHTML, PDF, XML, CSV, TIFF, Word ja Excel. Voit myös jakaa sen muiden kanssa.  
  
## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Tässä on joitakin muita ominaisuuksia, joita ei tueta ensimmäisessä julkaisussa:

- raporttisivujen tai visualisointien kiinnittäminen Power BI -raporttinäkymiin
- vuorovaikutteiset ominaisuudet, kuten asiakirjan rakenneruudut ja painikkeiden näyttäminen/piilottaminen
- aliraportit ja porautumisraportit
- tilaukset
- jaetut tietolähteet ja jaetut tietojoukot
- Power BI -tietojoukot
- visualisoinnit Power BI -raporteista
- sivutetut raportit sovelluksissa. Voit jakaa sivutetun raportin sovellustyötilasta, mutta se ei voi sisältää sitä, kun julkaiset sovelluksen työtilasta.
 
## <a name="next-steps"></a>Seuraavat vaiheet

- [Raportin muodostimen asentaminen Microsoft Download Centeristä](http://go.microsoft.com/fwlink/?LinkID=734968)

- [Opetusohjelma: Sivutetun raportin luominen](paginated-reports-quickstart-aw.md)
  

