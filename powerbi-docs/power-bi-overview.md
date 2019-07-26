---
title: Mikä Power BI on?
description: Yhteenveto Power BI:stä ja siitä, miten sen eri osat – Power BI Desktop, Power BI -palvelu, Power BI -mobiilisovellus, raporttipalvelin ja Power BI Embedded – toimivat yhdessä.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: overview
ms.date: 05/30/2019
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: d6c9eb47d5f88a2d835c1ba6835e871b0c64bf1c
ms.sourcegitcommit: fe8a25a79f7c6fe794d1a30224741e5281e82357
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/18/2019
ms.locfileid: "68324786"
---
# <a name="what-is-power-bi"></a>Mikä Power BI on?
**Power BI** on kokoelma ohjelmistopalveluja, sovelluksia ja yhdistimiä, jotka yhdessä muuntavat toisiinsa liittymättömistä lähteistä peräisin olevan tiedon johdonmukaisiksi, visuaalisesti vaikuttaviksi ja vuorovaikutteisiksi näkemyksiksi. Tiedot voivat olla Excel-laskentataulukossa tai joukossa pilvipohjaisia ja paikallisia hybriditietovarastoja. Power BI:n avulla voit helposti muodostaa yhteyden tietolähteisiin, visualisoida ja löytää tärkeitä asioita sekä jakaa niitä kenen kanssa haluat.

![Power BI:n tietolähteitä kuvastava kaavio](media/power-bi-overview/power-bi-input-new.png)

Power BI:tä voi käyttää yksinkertaisesti ja nopeasti, kun on tarve tuottaa merkityksellisiä tietoja Excel-taulukosta tai paikallisesta tietokannasta käden käänteessä. Power BI on kuitenkin myös järeä ja monipuolinen suuryritystason työkalu, joka sopii laajamittaiseen mallintamiseen, reaaliaikaiseen analytiikkaan ja mukautettavaan kehittämiseen. Se toimii yhtä sujuvasti henkilökohtaisena raportointi- ja visualisointityökaluna kuin analytiikka- ja päätöksentekovälineenä ryhmäprojekteissa, yksiköissä ja kokonaisissa organisaatioissa.

## <a name="the-parts-of-power-bi"></a>Power BI:n osat
Power BI koostuu seuraavista: 
- Windowsin työpöytäsovellus nimeltä **Power BI Desktop**
- Verkossa oleva SaaS (*Software as a Service*) -palvelu nimeltä **Power BI -palvelu** 
- Power BI **-mobiilisovellukset** Windows-, iOS- ja Android-laitteille

![Power BI Desktop, palvelu, mobiilisovellus](media/power-bi-overview/power-bi-blocks.png)

Jokainen osista – &mdash;Power BI Desktop, Power BI -palvelu ja mobiilisovellukset&mdash; – on suunniteltu siten, että merkityksellisten liiketoimintatietojen tuottaminen, jakaminen ja hyödyntäminen on mahdollisimman tehokasta kunkin käyttäjän tai hänen roolinsa kannalta.

Neljännen elementin, **Power BI -raporttipalvelimen**, avulla voit julkaista Power BI -raportteja paikalliseen raporttipalvelimeen, kun olet luonut ne Power BI Desktopissa. Lue lisää [Power BI -raporttipalvelimesta](#on-premises-reporting-with-power-bi-report-server).

## <a name="how-power-bi-matches-your-role"></a>Power BI:n tuki käyttäjärooleille
Power BI:n käyttämisen tapa voi riippua roolistasi projektissa tai tiimissä. Muissa rooleissa toimivat voivat käyttää Power BI:tä toisin.

Saatat itse käyttää ensisijaisesti **Power BI -palvelua**. Runsaasti laskentatehoa vaativia liiketoimintaraportteja tuottava kollegasi saattaa puolestaan luottaa **Power BI Desktopiin** raporttien luomisessa ja julkaista Desktop-raportit sitten Power BI -palveluun tarkasteltaviksesi. Toinen kollega myynnin puolelta voi käyttää pääasiassa **Power BI -puhelinsovellusta** myyntitavoitteidensa seurantaan ja uusien liiditietojen tutkimiseen.

Jos olet sovelluskehittäjä, saatat käyttää Power BI -ohjelmointirajapintoja tietojen viemiseen tietojoukkoihin tai upottaa koontinäyttöjä tai raportteja räätälöityihin sovelluksiisi. Onko sinulla idea uudesta visualisoinnista? Rakenna se itse ja jaa se muiden kanssa.  

Saatat käyttää Power BI:n eri osia aina sen mukaan, mitä on tarkoitus saavuttaa tai mikä roolisi on tietyssä projektissa.

Power BI:n käyttötapasi voi riippua siitä, mikä Power BI:n toiminto tai palvelu on paras työkalu tilanteeseesi. Voit esimerkiksi käyttää Power BI Desktopia raporttien luomiseen tiimillesi asiakkaiden osallistamistilastoista ja tarkastella varastotilannetta tai valmistumisprosessin etenemistä Power BI -palvelun reaaliaikaisessa koontinäytössä. Kukin Power BI:n osa on käytettävissäsi, mikä tekee siitä niin joustavan ja houkuttavan.

Tutustu rooliasi vastaaviin dokumentteihin:
- Power BI [***suunnittelijoille***](desktop-what-is-desktop.md)
- Power BI [***kuluttajille***](consumer/end-user-consumer.md)
- Power BI [***kehittäjille***](developer/what-can-you-do.md)
- Power BI [***järjestelmänvalvojille***](service-admin-administering-power-bi-in-your-organization.md)

## <a name="the-flow-of-work-in-power-bi"></a>Työnkulut Power BI:ssä
Tyypillinen Power BI -työnkulku alkaa yhteyden ottamisesta tietolähteisiin ja raportin luomisesta Power BI Desktopissa. Sen jälkeen julkaiset kyseisen raportin Power BI Desktopista Power BI -palveluun ja jaat sen, jotta Power BI -palvelua ja mobiililaitteita käyttävät loppukäyttäjät voivat tarkastella ja käsitellä raporttia.
Tämä työnkulku on yleinen ja näyttää, miten kolme keskeistä Power BI -osaa täydentävät toisiaan.

Tutustu yksityiskohtaiseen [Power BI Desktopin ja Power BI -palvelun vertailuun](service-service-vs-desktop.md).

Mutta entä jos et ole valmis siirtymään pilvipalveluun, ja haluat säilyttää raporttisi yrityksen palomuurin takana?  Lue lisää.

## <a name="on-premises-reporting-with-power-bi-report-server"></a>Paikallinen raportointi Power BI -raporttipalvelimella
Luo, ota käyttöön ja hallitse Power BI ‑mobiiliraportteja ja sivutettuja raportteja paikallisesti Power BI -raporttipalvelimen tarjoamien erilaisten käyttövalmiiden työkalujen ja palveluiden avulla.

![Paikallisen palvelun kaavio](media/power-bi-overview/power-bi-report-server2.png)

Power BI -raporttipalvelin on ratkaisu, jonka voit ottaa käyttöön oman palomuurisi sisällä ja toimittaa sitten raporttisi halutuille käyttäjille eri tavoilla, halusivat he sitten katsella niitä verkkoselaimella, mobiililaitteella tai sähköpostiviestinä. Ja koska Power BI -raporttipalvelin on yhteensopiva Power BI:n kanssa pilvipalvelussa, voit siirtyä pilvipalveluun, kun olet valmis. 

Lue lisää [Power BI -raporttipalvelimesta](report-server/get-started.md).

## <a name="next-steps"></a>Seuraavat vaiheet
- [Pika-aloitus: Power BI -palvelussa liikkuminen](service-the-new-power-bi-experience.md)   
- [Opetusohjelma: Power BI -palvelun käytön aloittaminen](service-get-started.md)
- [Pika-aloitus: Tietoihin yhdistäminen Power BI Desktopissa](desktop-quickstart-connect-to-data.md)
