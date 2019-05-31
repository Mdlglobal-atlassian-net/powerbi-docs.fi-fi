---
title: Mukautetut visualisoinnit Power BI:ssä
description: Mukautetut visualisoinnit Power BI:ssä
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: 3fd2f3e47c9b6dd2144ed5a66d45e65a00c5b92e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051253"
---
# <a name="custom-visuals-in-power-bi"></a>Mukautetut visualisoinnit Power BI:ssä

Kun luot tai muokkaat Power BI-raporttiin, voit käyttää monia eri visualisointityyppejä. Nämä visualisoinnit kuvakkeet näkyvät **visualisoinnit** ruudussa. Nämä visualisoinnit ovat näihin sovelluksiin esimääritetyn, kun lataat [Power BI Desktop](https://powerbi.microsoft.com/desktop/) tai avaa [Power BI-palvelun](https://app.powerbi.com).

![visualisoinnit](media/power-bi-custom-visuals/power-bi-visualizations.png)

Et ole kuitenkin ainoat visualisointien. Jos valitset alareunassa kolme pistettä (...), toinen raportin visualisointien lähde, on käytettävissä -*mukautettujen visualisointien*.

Kehittäjät luoda mukautettuja visualisointeja mukautettujen visualisointien SDK: N käyttäminen. Nämä visualisoinnit yrityskäyttäjät voivat tarkastella tietojaan parhaiten Omat tavalla. Raporttien tekijät voit sitten tuoda mukautetut visualisointitiedostot raportteihinsa ja käyttää niitä Power BI-visualisointien tapaan. Mukautetut visualisoinnit ovat Power BI ensimmäisen luokan kansalainen ja voidaan suodattaa korostetun, muokattu, jaetun ja niin edelleen.

Mukautetut visualisoinnit on otettu käyttöön kolmella tavalla:

* Mukautetut visualisointitiedostot
* Organisaation visualisoinnit
* Marketplacen visualisoinnit

## <a name="custom-visual-files"></a>Mukautetut visualisointitiedostot

Mukautetut visualisoinnit ovat paketteja, jotka sisältävät koodin antaa heille tietojen hahmontamista varten. Kuka tahansa voi luoda mukautetun visualisoinnin ja pakata sen yksittäisen `.pbiviz` -tiedosto, joka voidaan sitten tuoda Power BI-raporttiin.

> [!WARNING]
> Mukautettu visualisointi voi sisältää koodia, suojaus- tai tietosuojariskejä. Varmista, että luotat tekijään ja mukautetun visualisoinnin lähde ennen kuin tuot sen raporttiisi.

## <a name="organizational-visuals"></a>Organisaation visualisoinnit

Power BI-järjestelmänvalvojat Hyväksy ja ottaa käyttöön organisaatiossaan, joka raporttien tekijät voivat helposti löytää, päivittää ja käyttää mukautettuja visualisointeja. Järjestelmänvalvojat voivat hallita helposti (esimerkiksi version päivitys, käytöstäpoisto/käyttöönotto) nämä visualisoinnit.

 [Lue lisätietoja organisaation visualisointien](power-bi-custom-visuals-organization.md).

## <a name="marketplace-visuals"></a>Marketplacen visualisoinnit

Yhteisön jäsenet ja Microsoft ovat antaneet yleiseen käyttöön mukautettuja julkinen etua ja julkaisseet ne [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) Marketplacessa. Voit ladata nämä visualisoinnit ne lisätään Power BI-raportteja. Microsoft on testannut ja hyväksynyt mukautettujen visualisointien toiminnan ja laadun.

Mikä [AppSource](developer/office-store.md) on? Se on paikka, voit etsiä sovelluksia, apuohjelmia ja laajennuksia Microsoft-ohjelmiston. [AppSource](https://appsource.microsoft.com/) yhdistää miljoonat käyttäjät tuotteita, kuten Office 365, Azure, Dynamics 365, Cortanan ja Power BI-ratkaisuihin, joilla voit työskennellä tehokkaammin, insightfully, ja beautifully kuin ennen.

### <a name="certified-visuals"></a>Sertifioidut visualisoinnit

Power BI-sertifioidut visualisoinnit ovat Marketplacen visualisointeja, jotka ovat läpäisseet tiukkojen laadun testaus ja tuetaan lisätilanteissa, kuten [sähköpostitilausten](https://docs.microsoft.com/power-bi/service-report-subscribe), ja [PowerPointiin](https://docs.microsoft.com/power-bi/service-publish-to-powerpoint).
Jos haluat tarkastella luetteloa sertifioiduista mukautetuista visualisoinneista tai lähettää oman, lue artikkeli [Sertifioidut mukautetut visualisoinnit](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified).

Oletko Web-kehittäjä ja kiinnostunut omien visualisointien luomisesta ja niiden lisäämisestä AppSourceen? Katso [kehittäminen Power BI-visualisointisi](developer/custom-visual-develop-tutorial.md) ja oppia miten [mukautettujen visualisointien julkaiseminen Appsourceen](https://docs.microsoft.com/power-bi/developer/office-store).

### <a name="import-a-custom-visual-from-a-file"></a>Mukautetun visualisoinnin tuominen tiedostosta

1. Valitse kolme pistettä alaosasta **visualisoinnit** ruudussa.

    ![visualisoinnit2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Valitse avattavasta valikosta **Tuo tiedostosta**.

    ![tuo tiedostosta](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. Valitse Avaa Tiedosto-valikosta `.pbiviz` tiedosto, jonka haluat tuoda, ja valitse sitten **Avaa**. Mukautetun visualisoinnin kuvake lisätään alareunassa- **visualisoinnit** ruudussa ja on nyt valmis käytettäväksi raportissa.

    ![mukautettu visualisointi tuotu](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organizational-visuals"></a>Organisaation visualisointien tuominen

1. Valitse kolme pistettä alaosasta **visualisoinnit** ruudussa.

    ![visualisointi org 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. Valitse avattavasta valikosta **Tuo Marketplacesta**.

    ![visualisointi org 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Valitse **OMA ORGANISAATIO** yläreunan välilehtivalikosta.

    ![visualisointi org 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. Etsi tuotava visualisointi selaamalla luetteloa.

    ![visualisointi org 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. Valitse **Lisää** mukautetun visualisoinnin tuominen. Sen kuvake lisätään alareunassa- **visualisoinnit** ruudussa ja on nyt valmis käytettäväksi raportissa.

    ![visualisointi org 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Mukautettujen visualisointien lataaminen tai tuominen Microsoft AppSourcesta

Sinulla on kaksi vaihtoehtoa mukautettujen visualisointien lataamiseen ja tuomiseen:-Power BI-ja - [AppSource sivusto](https://appsource.microsoft.com/).

### <a name="import-custom-visuals-from-within-power-bi"></a>Mukautettujen visualisointien tuominen Power BI:stä

1. Valitse kolme pistettä alaosasta **visualisoinnit** ruudussa.

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

7. Valitse **Lisää** mukautetun visualisoinnin tuominen. Sen kuvake lisätään alareunassa- **visualisoinnit** ruudussa ja on nyt valmis käytettäväksi raportissa.

    ![visualisointi tuotu](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Mukautettujen visualisointien lataaminen tai tuominen Microsoft AppSourcesta

1. Aloita [Microsoft AppSourcesta](https://appsource.microsoft.com) ja valitse **Sovellukset**-välilehti.

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. Siirry [sovellusten tulossivulle](https://appsource.microsoft.com/marketplace/apps), jossa voit tarkastella kunkin luokan suosituimpia sovelluksia, mukaan lukien *Power BI -sovelluksia*. Haetaan mukautettuja visualisointeja, joten valitse **Power BI-visualisointien** rajata tulokset vasemmassa siirtymisruudussa luettelosta.

    ![AppSource-visualisoinnit](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource näyttää kunkin mukautetun visualisoinnin ruudun.  Jokaisessa ruudussa on mukautetun visualisoinnin tilannevedos lyhyt kuvaus ja latauslinkki. Saat lisätietoja valitsemalla ruudun.

    ![Mukauta valittu visualisointi](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. Tietosivulla voit tarkastella näyttökuvia, videoita, yksityiskohtaista kuvausta ja muita tietoja. Valitse **hanki se nyt** mukautetun visualisoinnin lataaminen ja sitten hyväksyt käyttöehdot.

    ![Hae AppSourcesta](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. Lataa mukautettu visualisointi valitsemalla linkki.

    ![Lataa](media/power-bi-custom-visuals/powerbi-custom-download.png)

    Lataus-sivulla sisältää myös ohjeet mukautetun visualisoinnin tuominen Power BI Desktop ja Power BI-palvelussa.

    Voit myös ladata malliraportin, joka sisältää mukautetun visualisoinnin ja esittelee sen ominaisuuksia.

    ![Kokeile mallia](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. Tallenna `.pbiviz` tiedosto ja avaa sitten Power BI.

7. Tuonti `.pbiviz` tiedosto raporttiin. (Katso ohjeet ylempää osiosta [Mukautetun visualisoinnin tuominen tiedostosta](#import-a-custom-visual-from-a-file).)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

* Mukautettu visualisointi lisätään tiettyyn raporttiin tuotaessa. Jos haluat käyttää visualisointia toisessa raportissa, sinun on tuotava se myös kyseiseen raporttiin. Kun mukautetun visualisoinnin sisältävä raportti tallennetaan käyttämällä **Tallenna nimellä** -vaihtoehtoa, kopio mukautetusta visualisoinnista tallennetaan uuden raportin yhteydessä.

* Jos et näe **visualisoinnit** ruudun, joka tarkoittaa, että sinulla ei ole raportin muokkausoikeuksia.  Voit lisätä mukautettuja visualisointeja vain raportteihin, joita voit muokata, et kanssasi jaettuihin raportteihin.

## <a name="troubleshoot"></a>Vianmääritys

Vianmääritys, katso [Power BI: n mukautettujen visualisointien vianmääritys](power-bi-custom-visuals-troubleshoot.md).

## <a name="faq"></a>Usein kysytyt kysymykset

Saat lisätietoja ja vastauksia kysymyksiisi [Power BI:n mukautettujen visualisointien usein kysytyistä kysymyksistä](power-bi-custom-visuals-faq.md#organizational-custom-visuals).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Visualisoinnit Power BI-raporteissa](visuals/power-bi-report-visualizations.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/).
