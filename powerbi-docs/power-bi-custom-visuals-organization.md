---
title: Organisaation mukautettujen visualisointien käyttäminen Power BI:ssä
description: Käytä, hallinnoi ja luo organisaation mukautettuja visualisointeja Power BI:ssä
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
ms.date: 02/06/2018
ms.author: maghan
LocalizationGroup: Visualizations
ms.openlocfilehash: 1f3a3586b3aecb10b07bd171ab7349c4e1089cec
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/04/2018
---
# <a name="using-organization-custom-visuals-in-power-bi"></a>Organisaation mukautettujen visualisointien käyttäminen Power BI:ssä

Power BI:n mukautettujen visualisointien avulla voit luoda yksilöllisen visualisointityypin, joka on räätälöity sinulle tai merkityksellisille tiedoille, joita yrität välittää. Usein näitä mukautettuja visualisointeja luovat kehittäjät, ja niitä luodaan, kun Power BI:hin sisältyvä laaja visualisointivalikoima ei täysin vastaa heidän tarpeitaan. 

Joissakin organisaatioissa mukautetut visualisoinnit ovat vielä tärkeämpiä – niitä saatetaan tarvita organisaation tiettyjen tietojen tai merkityksellisten tietojen välittämiseen, niillä voi olla erityisiä tietovaatimuksia tai ne saattavat korostaa yksityisiä liiketoimintamalleja. Tällaisten organisaatioiden on kehitettävä mukautettuja visualisointeja, jaettava niitä koko organisaatioon ja varmistettava, että niitä ylläpidetään oikein. Power BI:n mukautettujen visualisointien avulla se onnistuu helposti.

Seuraavassa kuvassa näkyy prosessi, jonka mukaan organisaation mukautetut visualisoinnit siirtyvät Power BI:ssä järjestelmänvalvojalta kehityksen ja ylläpidon kautta tietoanalyytikolle.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

Power BI -järjestelmänvalvoja ottaa organisaation visualisoinnit käyttöön ja hallinnoi niitä hallintaportaalissa. Kun ne on otettu käyttöön organisaation säilössä, organisaation käyttäjät voivat helposti löytää ne ja tuoda ne raportteihinsa suoraan Power BI Desktopista.

## <a name="using-organizational-custom-visuals"></a>Organisaation mukautettujen visualisointien käyttäminen

Lisätietoja siitä, miten voit käyttää organisaation mukautettuja visualisointeja luomissasi raporteissa, on seuraavassa artikkelissa: [Lisätietoja organisaation visualisointien tuomisesta raportteihin](power-bi-custom-visuals.md).
 
## <a name="administering-organizational-custom-visuals"></a>Organisaation mukautettujen visualisointien hallinta

Lisätietoja organisaation mukautettujen visualisointien käyttöönotosta ja hallinnasta organisaatiossasi on seuraavassa artikkelissa: [Lisätietoja organisaation mukautettujen visualisointien käyttöönotosta ja hallinnasta](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> Mukautettu visualisointi voi sisältää koodia, joka aiheuttaa suojaus- tai tietosuojariskejä. Varmista, että luotat mukautetun visualisoinnin tekijään ja lähteeseen, ennen kuin se otetaan käyttöön organisaation säilössä. 
> 

## <a name="considerations-and-limitations"></a>Huomioon otettavat seikat ja rajoitukset
 
Sinun on otettava huomioon useita seikkoja ja rajoituksia.
 
Järjestelmänvalvoja:

* Vanhoja mukautettuja visualisointeja (esimerkiksi mukautettuja visualisointeja, joita ei ole luotu uusilla ohjelmointirajapintojen versioilla) ei tueta.

* Jos mukautettu visualisointi poistetaan säilöstä, poistettua visualisointia käyttäviä aiemmin luotuja raportteja ei enää hahmonneta. Säilöstä poistamista ei voi peruuttaa. Voit poistaa mukautetun visualisoinnin tilapäisesti käytöstä Poista käytöstä -ominaisuuden avulla.
 
Käyttäjä:

* Power BI:n työtilakokoelmaa ei tueta organisaation visualisoinneissa.

* AppSource Marketplacen Visio-visualisointia, PowerApps-visualisointia ja GlobeMap-visualisointia ei hahmonneta, jos ne on otettu käyttöön organisaation säilön kautta.
