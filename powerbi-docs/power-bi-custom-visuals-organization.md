---
title: Organisaation mukautettujen visualisointien käyttäminen Power BI:ssä
description: Käytä, hallinnoi ja luo organisaation mukautettuja visualisointeja Power BI:ssä
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 10/29/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: e34491ebc1cc7554e8c8c000da7528754b5a673b
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223095"
---
# <a name="use-organizational-custom-visuals-in-power-bi"></a>Organisaation mukautettujen visualisointien käyttäminen Power BI:ssä

Power BI:n mukautettujen visualisointien avulla voit luoda yksilöllisen visualisointityypin, joka on räätälöity sinulle tai merkityksellisille tiedoille, joita yrität välittää. Usein näitä mukautettuja visualisointeja luovat kehittäjät, ja niitä luodaan, kun Power BI:hin sisältyvä laaja visualisointivalikoima ei täysin vastaa heidän tarpeitaan. 

Joissakin organisaatioissa mukautetut visualisoinnit ovat vielä tärkeämpiä – niitä saatetaan tarvita organisaation tiettyjen tietojen tai merkityksellisten tietojen välittämiseen, niillä voi olla erityisiä tietovaatimuksia tai ne saattavat korostaa yksityisiä liiketoimintamalleja. Tällaisten organisaatioiden on kehitettävä mukautettuja visualisointeja, jaettava niitä koko organisaatioon ja varmistettava, että niitä ylläpidetään oikein. Power BI:n mukautettujen visualisointien avulla se onnistuu helposti.

Seuraavassa kuvassa näkyy prosessi, jonka mukaan organisaation mukautetut visualisoinnit siirtyvät Power BI:ssä järjestelmänvalvojalta kehityksen ja ylläpidon kautta tietoanalyytikolle.

![Mukautetun visualisoinnin kuva](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

Power BI -järjestelmänvalvoja ottaa organisaation visualisoinnit käyttöön ja hallinnoi niitä hallintaportaalissa. Kun ne on otettu käyttöön organisaation säilössä, organisaation käyttäjät voivat helposti löytää ne ja tuoda ne raportteihinsa suoraan Power BI Desktopista.

Lisätietoja siitä, miten voit käyttää organisaation mukautettuja visualisointeja luomissasi raporteissa, on seuraavassa artikkelissa: [Lisätietoja organisaation visualisointien tuomisesta raportteihin](power-bi-custom-visuals.md).

## <a name="administer-organizational-custom-visuals"></a>Organisaation mukautettujen visualisointien hallinta

Lisätietoja organisaation mukautettujen visualisointien käyttöönotosta ja hallinnasta organisaatiossasi on seuraavassa artikkelissa: [Lisätietoja organisaation mukautettujen visualisointien käyttöönotosta ja hallinnasta](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> Mukautettu visualisointi voi sisältää koodia, joka aiheuttaa suojaus- tai tietosuojariskejä. Varmista, että luotat mukautetun visualisoinnin tekijään ja lähteeseen, ennen kuin se otetaan käyttöön organisaation säilössä.

## <a name="considerations-and-limitations"></a>Huomioon otettavat seikat ja rajoitukset

Sinun on otettava huomioon useita seikkoja ja rajoituksia.

Järjestelmänvalvoja:

* Vanhoja mukautettuja visualisointeja (esimerkiksi mukautettuja visualisointeja, joita ei ole luotu uusilla ohjelmointirajapintojen versioilla) ei tueta.

* Jos mukautettu visualisointi poistetaan säilöstä, poistettua visualisointia käyttäviä aiemmin luotuja raportteja ei enää hahmonneta. Säilöstä poistamista ei voi peruuttaa. Voit poistaa mukautetun visualisoinnin tilapäisesti käytöstä Poista käytöstä -ominaisuuden avulla.

Käyttäjä:

* Organisaation mukautetut visualisoinnit ovat yksityisiä visualisointeja, jotka on tuotu organisaation säilöstä. Yksityisiä visualisointeja ei voi [viedä PowerPointiin](https://docs.microsoft.com/power-bi/consumer/end-user-powerpoint) tai näyttää sähköpostiviesteissä, joita käyttäjä vastaanottaa [tilatessaan raporttisivuja](https://docs.microsoft.com/power-bi/consumer/end-user-subscribe). Vain suoraan Marketplacesta tuodut [sertifioidut mukautetut visualisoinnit](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified) tukevat näitä ominaisuuksia.

* AppSource Marketplacesta tuodut Visio-visualisoinnit, PowerApps-visualisoinnit, Map Box -visualisoinnit tai GlobeMap-visualisoinnit eivät hahmonnu, jos niitä otetaan käyttöön organisaation säilöstä.

## <a name="troubleshoot"></a>Vianmääritys

Lisätietoja vianmäärityksestä on kohdassa [Power BI:n mukautettujen visualisointien vianmääritys](power-bi-custom-visuals-troubleshoot.md).

## <a name="faq"></a>Usein kysytyt kysymykset

Saat lisätietoja ja vastauksia kysymyksiisi [Power BI:n mukautettujen visualisointien usein kysytyistä kysymyksistä](power-bi-custom-visuals-faq.md#organizational-custom-visuals).

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/).
