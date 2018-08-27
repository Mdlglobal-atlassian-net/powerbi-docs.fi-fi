---
title: Mukautetut visualisoinnit Power BI:ssä
description: Mukautetut visualisoinnit Power BI:ssä
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 02/06/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: 872f0c556dd995c20d461d9f4969b7fa00f80571
ms.sourcegitcommit: 8990028a348b642ba5c96f001fe3a4280f0166ee
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/14/2018
ms.locfileid: "40256951"
---
# <a name="custom-visuals-in-power-bi"></a>Mukautetut visualisoinnit Power BI:ssä

Kun luot tai muokkaat Power BI -raporttia, käytettävissäsi on monia eri visualisointityyppejä. Nämä visualisoinnit näkyvät **Visualisoinnit**-ruudussa. Kun lataat Power BI Desktopin tai avaa Power BI -palvelun (app.powerbi.com), visualisointijoukko tulee valmiina pakettina.

![](media/power-bi-custom-visuals/power-bi-visualizations.png)

Nämä eivät kuitenkaan ole ainoat käytettävissäsi olevat visualisoinnit: kun valitset kolme pistettä, avautuu toinen raportin visualisointien lähde, *mukautetut visualisoinnit*.

Mukautettuja visualisointeja luovat kehittäjät mukautettujen visualisointien SDK:n avulla, jotta yrityskäyttäjät voivat tarkastella tietojaan yritykselle parhaiten sopivalla tavalla. Raporttien tekijät voivat tuoda mukautettuja visualisointitiedostoja raportteihinsa ja käyttää niitä minkä tahansa muun Power BI -visualisoinnin tapaan. Mukautetut visualisoinnit ovat Power BI:n ykkösluokkaa, ja niitä voidaan suodattaa, korostaa, muokata, jakaa ja niin edelleen.

Mukautetut visualisoinnit voivat olla kolmen käyttöönottokanavan muodossa:
* Mukautetut visualisointitiedostot
* Organisaation visualisoinnit
* Marketplacen visualisoinnit

## <a name="custom-visual-files"></a>Mukautetut visualisointitiedostot

Mukautetut visualisoinnit ovat paketteja, jotka sisältävät koodin niille tarjottujen tietojen hahmontamista varten. Kuka tahansa voi luoda mukautetun visualisoinnin ja pakata sen yksittäiseksi `.pbiviz`-tiedostoksi, joka voidaan tuoda Power BI -raporttiin.

> [!WARNING]
> Mukautettu visualisointi voi sisältää koodia, johon liittyy tietoturva- tai tietosuojariskejä. Varmista, että luotat mukautetun visualisoinnin tekijään ja lähteeseen, ennen kuin tuot sen raporttiisi.

## <a name="organization-visuals"></a>Organisaation visualisoinnit

Power BI -järjestelmänvalvojat voivat ottaa mukautettuja visualisointeja käyttöön organisaatiossaan, jotta raporttien tekijät voivat helposti löytää ja käyttää mukautettuja visualisointeja, jotka järjestelmänvalvoja on hyväksynyt käytettäväksi organisaation sisällä. Näin järjestelmänvalvoja voi valita tietyt mukautetut visualisoinnit, joita organisaatiossa voidaan käyttää. Myös visualisointien hallinta (esimerkiksi version päivitys ja käytöstäpoisto/käyttöönotto) on näin helpompaa. Raportin tekijän on helppo löytää visualisointeja, jotka ovat yksilöllisiä organisaatiolle, ja visualisointien päivittämiseen tarjotaan saumaton tuki.

Jos tarvitset lisätietoja organisaation mukautetuista visualisoinneista, [lue lisää organisaation visualisoinneista](power-bi-custom-visuals-organization.md).

## <a name="marketplace-visuals"></a>Marketplacen visualisoinnit

Yhteisön jäsenet ja Microsoft ovat antaneet mukautetut visualisointinsa yleiseen käyttöön ja julkaisseet ne [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals) Marketplacessa. Näitä visualisointeja voi ladata ja lisätä Power BI -raportteihin. Microsoft on testannut ja hyväksynyt kaikkien mukautettujen visualisointien toiminnan ja laadun.

Mikä AppSource on? Lyhyesti sanottuna se on paikka, josta löydät sovelluksia, apuohjelmia ja laajennuksia Microsoft-ohjelmistollesi. [AppSource](https://appsource.microsoft.com/en-us/) yhdistää miljoonat Office 365:n, Azuren, Dynamics 365:n, Cortanan ja Power BI:n kaltaisten tuotteiden käyttäjät ratkaisuihin, joiden avulla he voivat työskennellä entistä tehokkaammin, älykkäämmin ja tyylikkäämmin.

### <a name="certified-visuals"></a>Sertifioidut visualisoinnit

Power BI -sertifioidut visualisoinnit ovat Marketplacen visualisointeja, jotka ovat läpäisseet ylimääräisen tiukan laatutestauksen ja joita tuetaan lisätilanteissa, kuten [sähköpostitilauksissa](https://docs.microsoft.com/power-bi/service-report-subscribe) ja [PowerPointiin viennissä](https://docs.microsoft.com/power-bi/service-publish-to-powerpoint).
Jos haluat tarkastella luetteloa sertifioiduista mukautetuista visualisoinneista tai lähettää oman, lue artikkeli [Sertifioidut mukautetut visualisoinnit](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified).

Oletko Web-kehittäjä ja kiinnostunut omien visualisointien luomisesta ja niiden lisäämisestä AppSourceen? Katso artikkeli [Kehittäjien työkalujen käytön aloittaminen](https://docs.microsoft.com/power-bi/service-custom-visuals-getting-started-with-developer-tools) ja lue lisää [mukautettujen visualisointien julkaisemisesta AppSourcessa](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals).

### <a name="import-a-custom-visual-from-a-file"></a>Mukautetun visualisoinnin tuominen tiedostosta

1. Valitse kolme pistettä Visualisoinnit-ruudun alareunasta.

    ![](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Valitse avattavasta valikosta **Tuo tiedostosta**.

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. Valitse Avaa tiedosto -valikosta `.pbiviz`-tiedosto, jonka haluat tuoda, ja valitse sitten Avaa. Mukautetun visualisoinnin kuvake lisätään Visualisoinnit-ruudun alaosaan, ja visualisointi on valmis käytettäväksi raportissa.

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organization-visuals"></a>Organisaation visualisointien tuominen

1. Valitse kolme pistettä Visualisoinnit-ruudun alareunasta.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. Valitse avattavasta valikosta Tuo Marketplacesta.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Valitse **OMA ORGANISAATIO** yläreunan välilehtivalikosta.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. Etsi tuotava visualisointi selaamalla luetteloa.
    
    ![](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. Tuo mukautettu visualisointi valitsemalla **Lisää**. Mukautetun visualisoinnin kuvake lisätään Visualisoinnit-ruudun alaosaan, ja visualisointi on valmis käytettäväksi raportissa.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Mukautettujen visualisointien lataaminen tai tuominen Microsoft AppSourcesta

Sinulla on kaksi vaihtoehtoa mukautettujen visualisointien lataamiseen ja tuomiseen: Power BI ja AppSource-sivusto.

### <a name="import-custom-visuals-from-within-power-bi"></a>Mukautettujen visualisointien tuominen Power BI:stä

1. Valitse kolme pistettä Visualisoinnit-ruudun alareunasta.

    ![](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Valitse avattavasta valikosta **Tuo Marketplacesta**.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Etsi tuotava visualisointi selaamalla luetteloa.

    ![](media/power-bi-custom-visuals/power-bi-import-visual.png)

4. Saat lisätietoja visualisoinnista korostamalla ja valitsemalla sen.

    ![](media/power-bi-custom-visuals/power-bi-select.png)

5. Tietosivulla voit tarkastella näyttökuvia, videoita, yksityiskohtaista kuvausta ja muita tietoja.

    ![](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. Näet arvosteluja siirtymällä alareunaan.

    ![](media/power-bi-custom-visuals/power-bi-reviews.png)

7. Tuo mukautettu visualisointi valitsemalla Lisää. Mukautetun visualisoinnin kuvake lisätään Visualisoinnit-ruudun alaosaan, ja visualisointi on valmis käytettäväksi raportissa.

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Mukautettujen visualisointien lataaminen tai tuominen Microsoft AppSourcesta

1. Aloita [Microsoft AppSourcesta](https://appsource.microsoft.com) ja valitse **Sovellukset**-välilehti. 

    ![](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. Näin siirryt [sovellusten tulossivulle](https://appsource.microsoft.com/en-us/marketplace/apps), jossa voit tarkastella kunkin luokan suosituimpia sovelluksia mukaan lukien *Power BI -sovellukset*. Koska nyt haetaan mukautettuja visualisointeja, rajataan tuloksia valitsemalla **Power BI -visualisoinnit** vasemmasta siirtymisluettelosta.

    ![](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource näyttää kunkin mukautetun visualisoinnin ruudun.  Jokaisessa ruudussa on tilannevedos mukautetusta visualisoinnista, lyhyt kuvaus ja latauslinkki. Saat lisätietoja valitsemalla ruudun.

    ![](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. Tietosivulla voit tarkastella näyttökuvia, videoita, yksityiskohtaista kuvausta ja muita tietoja. Lataa mukautettu visualisointi valitsemalla **Hanki se nyt** ja hyväksymällä käyttöehdot.

    ![](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. Lataa mukautettu visualisointi valitsemalla linkki.

    ![](media/power-bi-custom-visuals/powerbi-custom-download.png)

    Lataussivu sisältää myös ohjeet mukautetun visualisoinnin tuomiseen Power BI Desktopiin ja Power BI -palveluun.

    Voit myös ladata malliraportin, joka sisältää mukautetun visualisoinnin ja esittelee sen ominaisuuksia.

    ![](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. Tallenna .pbiviz-tiedosto ja avaa sitten Power BI.

7. Tuo .pbiviz-tiedosto raporttiin (katso osio [Mukautetun visualisoinnin tuominen tiedostosta](#import-a-custom-visuals-from-a-file) edellä)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

- Mukautettu visualisointi lisätään tiettyyn raporttiin tuotaessa. Jos haluat käyttää visualisointia toisessa raportissa, sinun on tuotava se myös kyseiseen raporttiin. Kun mukautetun visualisoinnin sisältävä raportti tallennetaan käyttämällä **Tallenna nimellä** -vaihtoehtoa, kopio mukautetusta visualisoinnista tallennetaan uuden raportin yhteydessä.

- Jos et näe **Visualisoinnit**-ruutua, sinulla ei ole raportin muokkausoikeuksia.  Voit lisätä mukautettuja visualisointeja vain raportteihin, joita voit muokata, et kanssasi jaettuihin raportteihin.

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
