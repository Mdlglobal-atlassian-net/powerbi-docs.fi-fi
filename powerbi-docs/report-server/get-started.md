---
title: Power BI-raporttipalvelimen käytön aloittaminen
description: 'Opi asentamaan Power BI -raporttipalvelin. '
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
ms.date: 3/5/2018
ms.author: maghan
ms.openlocfilehash: 88aa347a5e6feae969cf9b32e0e2177114efc757
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/08/2018
ms.locfileid: "30974887"
---
# <a name="get-started-with-power-bi-report-server"></a>Power BI-raporttipalvelimen käytön aloittaminen
Luo, ota käyttöön ja hallitse Power BI ‑mobiiliraportteja ja sivutettuja raportteja paikallisesti Power BI -raporttipalvelimen tarjoamien erilaisten käyttövalmiiden työkalujen ja palveluiden avulla.

## <a name="create-deploy-and-manage-reports"></a>Raporttien luominen, käyttöönotto ja hallinta
Power BI -raporttipalvelin on ratkaisu, jonka asiakkaasi voivat ottaa käyttöön omissa tiloissaan. Sen avulla voi luoda, julkaista ja hallita raportteja sekä toimittaa ne sitten halutuille käyttäjille eri tavoilla, halusivat he sitten katsella niitä verkkoselaimella, mobiililaitteella tai sähköpostiviestinä.

Power BI -raporttipalvelin tarjoaa kokonaisen tuotepaketin:

* Nykyaikainen verkkoportaali, jota voi käyttää millä tahansa modernilla selaimella. Verkkoportaalissa voi järjestellä ja katsella raportteja ja suorituskykyilmaisimia. Lisäksi portaaliin voi tallentaa Excel-työkirjoja.
* Power BI Desktopissa luodut Power BI ‑raportit, joita voit tarkastella omasta ympäristöstäsi verkkoportaalin kautta.
* Sivutetut raportit, joiden avulla voi tehdä nykyaikaisilta näyttäviä raportteja, sekä niiden luontityökalut.
* Mobiiliraportit, joiden reagoiva asettelu sopeutuu eri laitteille ja näytön suunnan mukaisesti.

Tässä artikkelissa kerrotaan niistä lisää jäljempänä.

### <a name="whats-new-in-power-bi-report-server"></a>Power BI -raporttipalvelinten uudet ominaisuudet
Seuraavien lähteiden avulla pysyt ajan tasalla Power BI -raporttipalvelimen uusista ominaisuuksista.

* [Power BI -raporttipalvelinten uudet ominaisuudet](whats-new.md)
* [Microsoftin Power BI ‑blogi](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services -tiimin blogi](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [Guy in a Cube ‑YouTube-kanava](https://aka.ms/guyinacube)

## <a name="web-portal"></a>Verkkoportaali
![](media/get-started/web-portal.png)

Loppukäyttäjille Power BI -raporttipalvelimen etuovi on nykyaikainen verkkoportaali, jota voit tarkastella missä tahansa nykyaikaisessa selaimessa. Voit käyttää kaikkia raportteja ja suorituskykyilmaisimia uudessa portaalissa.

Voit käyttää verkkoportaalissa omia mukautettuja [brändejäsi](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal). Lisäksi voit luoda suorituskykyilmaisimia suoraan verkkoportaalista. Suorituskykyilmaisimet voivat tuoda esiin tärkeitä liiketoiminnan arvoja yhdellä vilkaisulla selaimessa – ilman raporttien avaamista.

Verkkoportaalin sisältö on järjestetty tyypin mukaan: Power BI ‑raportit, mobiiliraportit, sivutetut raportit ja suorituskykyilmaisimet sekä raporttien rakennusmateriaaleina käytettävät Excel-työkirjat, jaetut tietojoukot ja jaetut tietolähteet. Voit tallentaa ja hallita niitä portaalissa turvallisesti, perinteisen kansiohierarkian mukaan järjestettyinä. Voit merkitä suosikkeja ja hallita sisältöä, jos sinulla on siihen sopiva käyttäjärooli.

Uudessa verkkoportaalissa voit myös ajastaa raporttien käsittelyn, käyttää raportteja pyynnöstä sekä tilata julkaistut raportit itsellesi.

Lisätietoja [verkkoportaalista](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).

## <a name="power-bi-reports"></a>Power BI -raportit
![](media/get-started/powerbi-reports.png)

Power BI -raportti on usean perspektiivin tietojoukkonäkymä, jonka visualisoinnit edustavat eri havaintoja ja merkityksellisiä tietoja tietojoukosta.  Raportilla voi olla yksittäinen visualisointi tai sivuja, jotka ovat täynnä visualisointeja. Työroolistasi riippuen voit olla joku, joka luo raportteja, ja/tai voit olla joku, joka kuluttaa eli käyttää raportteja.

Raportit perustuvat yhteen tietojoukkoon. Jokainen raportin visualisointi edustaa tiedonjyvää. Visualisoinnit eivät ole staattisia. Voit lisätä ja poistaa tietoja, muuttaa visualisointityyppejä ja lisätä suodattimia ja osittajia, kun pureudut tietoihin ja etsit merkityksellisiä tietoja ja haet vastauksia. Kuten koontinäyttö, raportti on vuorovaikutteinen ja mukautettava, ja visualisoinnit päivittyvät sitä mukaa, kun sen pohjana olevat tiedot muuttuvat.

## <a name="paginated-reports"></a>Sivutetut raportit
![](media/get-started/paginated-reports.png)

Sivutetut raportit ovat sivutettuja asiakirjatyylisiä raportteja, joissa on sitä useampia sivuja mitä enemmän tietoja sinulla on ja mitä enemmän taulukoissa on rivejä. Ne sopivat erinomaisesti pikselintarkasti täydellisesti aseteltuihin kiinteisiin raportteihin, jotka on optimoitu tulostettavaksi esimerkiksi PDF- tai Word-tiedostoina.

Voit luoda ulkoasultaan moderneja raportteja käyttämällä [raportin muodostinta](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016) tai Report Designeria [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt) -työkaluista.

## <a name="report-server-programming-features"></a>Raporttipalvelimen ohjelmointiominaisuudet
Hyödynnä Power BI -raporttipalvelimen ohjelmointiominaisuudet, joiden avulla voit laajentaa ja mukauttaa raporttitoiminnallisuuksia. Ohjelmointirajapintojen kautta voit integroida niitä mukautettuihin sovelluksiin sekä laajentaa tietojen ja raporttien käsittelyä sovelluksissa.

Lisää [ohjeita raporttipalvelinkehittäjälle](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation).

## <a name="next-steps"></a>Seuraavat vaiheet
[Käyttöopas](user-handbook-overview.md)  
[Järjestelmänvalvojien opas](admin-handbook-overview.md)  
[Pikaopas: Power BI -raporttipalvelimen asentaminen](quickstart-install-report-server.md)  
[Raportin muodostimen asentaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) -työkalujen lataaminen](http://go.microsoft.com/fwlink/?LinkID=616714)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)


