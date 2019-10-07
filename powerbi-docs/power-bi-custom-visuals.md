---
title: Visualisoinnit Power BI:ssä
description: Mukautetut visualisoinnit Power BI:ssä
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: a782726e34bec4d6a5b8557c88178d469f7987b6
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/04/2019
ms.locfileid: "71946189"
---
# <a name="visuals-in-power-bi"></a>Visualisoinnit Power BI:ssä

Kun luot tai muokkaat Power BI -raporttia, käytettävissäsi on monia eri visualisointityyppejä. Näiden visualisointien kuvakkeet näytetään **Visualisoinnit**-ruudussa. Nämä visualisoinnit ovat heti käytettävissäsi, kun lataat [Power BI Desktopin](https://powerbi.microsoft.com/desktop/) tai avaat [Power BI -palvelun](https://app.powerbi.com).

![visualisoinnit](media/power-bi-custom-visuals/power-bi-visualizations.png)

Sinun ei kuitenkaan tarvitse tyytyä pelkästään näihin visualisointeihin. Kun valitset alareunasta kolme pistettä (...), näet toisenkin lähteen raporttivisualisoinneille: *Power BI -visualisoinnit*.

Kehittäjät luovat Power BI -visualisointeja Power BI -visualisointien SDK:n avulla. Näillä visualisoinneilla yrityskäyttäjät voivat tarkastella tietoja tarpeisiinsa sopivilla tavoilla. Raporttien tekijät voivat tuoda mukautettuja visualisointitiedostoja raportteihinsa ja käyttää niitä minkä tahansa muun Power BI -visualisoinnin tapaan. Power BI -visualisoinnit ovat Power BI:n ykkösluokkaa: niitä voi esimerkiksi suodattaa, korostaa, muokata ja jakaa.

Power BI -visualisointeja voi ottaa käyttöön kolmella tavalla:

* Mukautetut visualisointitiedostot
* Organisaation visualisoinnit
* Marketplacen visualisoinnit

## <a name="custom-visual-files"></a>Mukautetut visualisointitiedostot

Power BI -visualisoinnit ovat paketteja, jotka sisältävät koodin niille tarjottujen tietojen näyttämiseksi (hahmontamiseksi). Kuka tahansa voi luoda mukautetun visualisoinnin ja pakata sen yksittäiseksi `.pbiviz`-tiedostoksi, jonka voi sitten tuoda Power BI -raporttiin.

> [!WARNING]
> Mukautettu visualisointi voi sisältää koodia, joka aiheuttaa suojaus- tai tietosuojariskejä. Varmista, että luotat mukautetun visualisoinnin tekijään ja lähteeseen, ennen kuin tuot sen raporttiisi.

## <a name="organizational-visuals"></a>Organisaation visualisoinnit

Power BI -järjestelmänvalvojat hyväksyvät Power BI -visualisointeja ja ottavat niitä käyttöön organisaatiossaan, jotta raporttien tekijät voivat helposti etsiä, päivittää ja käyttää niitä. Järjestelmänvalvojat voivat hallita näitä visualisointeja helposti (esimerkiksi päivittää version, ottaa käyttöön ja poistaa käytöstä).

 [Lue lisätietoja organisaation visualisoinneista](power-bi-custom-visuals-organization.md).

## <a name="marketplace-visuals"></a>Marketplacen visualisoinnit

Yhteisön jäsenet ja Microsoft ovat antaneet Power BI -visualisointinsa yleiseen käyttöön ja julkaisseet ne [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) Marketplacessa. Voit ladata näitä visualisointeja ja lisätä niitä Power BI -raportteihisi. Microsoft on testannut ja hyväksynyt kaikkien näiden Power BI -visualisointien toiminnan ja laadun.

Mikä [AppSource](developer/office-store.md) on? Se on paikka, josta löydät sovelluksia, apuohjelmia ja laajennuksia Microsoft-ohjelmistollesi. AppSource yhdistää miljoonat Office 365:n, Azuren, Dynamics 365:n, Cortanan ja Power BI:n kaltaisten tuotteiden käyttäjät ratkaisuihin, joiden avulla he voivat työskennellä entistä tehokkaammin, älykkäämmin ja tyylikkäämmin.

### <a name="certified-visuals"></a>Sertifioidut visualisoinnit

Power BI -sertifioidut visualisoinnit ovat Marketplacen visualisointeja, jotka ovat läpäisseet ylimääräisen tiukan laatutestauksen ja joita tuetaan erilaisissa käyttötilanteissa, esimerkiksi [sähköpostitilauksissa](service-report-subscribe.md) ja [PowerPointiin viennissä](service-publish-to-powerpoint.md).
Jos haluat tarkastella luetteloa sertifioiduista Power BI -visualisoinneista tai lähettää oman, lue artikkeli [Sertifioidut Power BI -visualisoinnit](power-bi-custom-visuals-certified.md).

Oletko Web-kehittäjä ja kiinnostunut omien visualisointien luomisesta ja niiden lisäämisestä AppSourceen? Katso artikkeli [Power BI:n mukautetun visualisoinnin kehittäminen](developer/custom-visual-develop-tutorial.md) ja lue lisää [Power BI -visualisointien julkaisemisesta AppSourcessa](developer/office-store.md).

### <a name="import-a-custom-visual-from-a-file"></a>Mukautetun visualisoinnin tuominen tiedostosta

1. Valitse kolme pistettä **Visualisoinnit**-ruudun alareunasta.

    ![visualisoinnit2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Valitse avattavasta valikosta **Tuo tiedostosta**.

    ![tuo tiedostosta](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. Valitse **Avaa tiedosto** -valikosta `.pbiviz`-tiedosto, jonka haluat tuoda, ja valitse sitten **Avaa**. Mukautetun visualisoinnin kuvake lisätään **Visualisoinnit**-ruudun alaosaan. Lisäksi visualisointi on nyt valmis käytettäväksi raportissa.

    ![mukautettu visualisointi tuotu](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organizational-visuals"></a>Organisaation visualisointien tuominen

1. Valitse kolme pistettä **Visualisoinnit**-ruudun alareunasta.

    ![visualisointi org 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. Valitse avattavasta valikosta **Tuo Marketplacesta**.

    ![visualisointi org 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Valitse **OMA ORGANISAATIO** yläreunan välilehtivalikosta.

    ![visualisointi org 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. Etsi tuotava visualisointi selaamalla luetteloa.

    ![visualisointi org 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. Tuo mukautettu visualisointi valitsemalla **Lisää**. Mukautetun visualisoinnin kuvake lisätään **Visualisoinnit**-ruudun alaosaan. Lisäksi visualisointi on nyt valmis käytettäväksi raportissa.

    ![visualisointi org 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-power-bi-visuals-from-microsoft-appsource"></a>Power BI -visualisointien lataaminen tai tuominen Microsoft AppSourcesta

Sinulla on kaksi vaihtoehtoa Power BI -visualisointien lataamiseen ja tuomiseen: Power BI ja [AppSource-sivusto](https://appsource.microsoft.com/).

### <a name="import-power-bi-visuals-from-within-power-bi"></a>Power BI -visualisointien hankkiminen Power BI:ssä

1. Valitse kolme pistettä **Visualisoinnit**-ruudun alareunasta.

    ![visualisoinnit 2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Valitse avattavasta valikosta **Tuo Marketplacesta**.

    ![visualisointi org 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Etsi tuotava visualisointi selaamalla luetteloa.

    ![tuo visualisointi](media/power-bi-custom-visuals/power-bi-import-visual.png)

4. Saat lisätietoja visualisoinnista korostamalla ja valitsemalla sen.

    ![Valitse](media/power-bi-custom-visuals/power-bi-select.png)

5. Tietosivulla voit tarkastella näyttökuvia, videoita, yksityiskohtaista kuvausta ja muita tietoja.

    ![Synoptinen](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. Näet arvosteluja siirtymällä alareunaan.

    ![Arvostelut](media/power-bi-custom-visuals/power-bi-reviews.png)

7. Tuo mukautettu visualisointi valitsemalla **Lisää**. Mukautetun visualisoinnin kuvake lisätään **Visualisoinnit**-ruudun alaosaan. Lisäksi visualisointi on nyt valmis käytettäväksi raportissa.

    ![visualisointi tuotu](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-power-bi-visuals-from-microsoft-appsource"></a>Power BI -visualisointien lataaminen ja tuominen Microsoft AppSourcesta

1. Aloita [Microsoft AppSourcesta](https://appsource.microsoft.com) ja valitse **Sovellukset**-välilehti.

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. Siirry [sovellusten tulossivulle](https://appsource.microsoft.com/marketplace/apps), jossa voit tarkastella kunkin luokan suosituimpia sovelluksia, mukaan lukien *Power BI -sovelluksia*. Koska nyt haetaan Power BI -visualisointeja, rajataan tuloksia valitsemalla vasemmasta siirtymisluettelosta **Power BI -visualisoinnit**. Tämä pienentää tulosten määrää.

    ![AppSource-visualisoinnit](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource näyttää kunkin mukautetun visualisoinnin ruudun.  Jokaisessa ruudussa on tilannevedos mukautetusta visualisoinnista, lyhyt kuvaus ja latauslinkki. Saat lisätietoja valitsemalla ruudun.

    ![Mukauta valittu visualisointi](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. Tietosivulla voit tarkastella näyttökuvia, videoita, yksityiskohtaista kuvausta ja muita tietoja. Lataa mukautettu visualisointi valitsemalla **Hanki se nyt** ja hyväksymällä sitten käyttöehdot.

    ![Hae AppSourcesta](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. Lataa mukautettu visualisointi valitsemalla linkki.

    ![Lataa](media/power-bi-custom-visuals/powerbi-custom-download.png)

    Lataussivu sisältää myös ohjeet mukautetun visualisoinnin tuomiseen Power BI Desktopiin ja Power BI -palveluun.

    Voit myös ladata malliraportin, joka sisältää mukautetun visualisoinnin ja esittelee sen ominaisuuksia.

    ![Kokeile mallia](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. Tallenna `.pbiviz`-tiedosto ja avaa sitten Power BI.

7. Tuo `.pbiviz`-tiedosto raporttiin. (Katso ohjeet ylempää osiosta [Mukautetun visualisoinnin tuominen tiedostosta](#import-a-custom-visual-from-a-file).)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

* Mukautettu visualisointi lisätään tiettyyn raporttiin tuotaessa. Jos haluat käyttää visualisointia toisessa raportissa, sinun on tuotava se myös kyseiseen raporttiin. Kun mukautetun visualisoinnin sisältävä raportti tallennetaan käyttämällä **Tallenna nimellä** -vaihtoehtoa, kopio mukautetusta visualisoinnista tallennetaan uuden raportin yhteydessä.

* Jos et näe **Visualisoinnit**-ruutua, sinulla ei ole raportin muokkausoikeuksia.  Voit lisätä Power BI -visualisointeja vain raportteihin, joita voit muokata, et kanssasi jaettuihin raportteihin.

## <a name="troubleshoot"></a>Vianmääritys

Vianmääritysohjeet löytyvät kohdasta [Power BI:n Power BI -visualisointien vianmääritys](power-bi-custom-visuals-troubleshoot.md).

## <a name="faq"></a>Usein kysytyt kysymykset

Saat lisätietoja ja vastauksia kysymyksiisi [Power BI:n Power BI -visualisointien usein kysytyistä kysymyksistä](power-bi-custom-visuals-faq.md#organizational-visuals).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Visualisoinnit Power BI -raporteissa](visuals/power-bi-report-visualizations.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/).
