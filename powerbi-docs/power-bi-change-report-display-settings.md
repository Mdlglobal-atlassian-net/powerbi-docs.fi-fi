---
title: Raportin sivun koon muuttaminen
description: Power BI -raportin sivun näyttöasetusten muuttaminen
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/24/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: c2b9a106c4007af868cf69902ce511da8e03e75f
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34244557"
---
# <a name="change-the-size-of-a-report-page"></a>Raportin sivun koon muuttaminen
Opit [edellisessä artikkelissa ja videossa](power-bi-report-display-settings.md) kaksi tapaa hallita Power BI -raporttien sivun näyttöä: **Näkymä** ja **Sivun koko**. Sivun Näkymä ja Sivun koko ovat käytettävissä sekä Power BI -palvelussa että Power BI Desktopissa. Niiden ulkonäkö ja toiminnot ovat lähes samat, mutta tässä opetusohjelmassa käytämme Power BI -palvelua.

### <a name="prerequisites"></a>Edellytykset
- Power BI -palvelu   
- [Jälleenmyyntianalyysimallin raportti](sample-retail-analysis.md)

## <a name="first-lets-change-the-page-view-setting"></a>Muutetaanpa ensiksi sivun Näkymä-asetusta.

1. Avaa raportti lukunäkymässä tai muokkausnäkymässä, ja valitse Raportti-välilehdessä **Uudet myymälät**. Tämä raportin sivu näytetään oletusarvoisesti käyttämällä **Sovita sivulle** -asetusta.  Tässä tapauksessa Sovita sivulle -asetus näyttää raportin sivun ilman vierityspalkkeja, mutta jotkin tiedot ja otsikot ovat liian pieniä luettaviksi.

   ![](media/power-bi-change-report-display-settings/pbi_fit_to_page.png)
2. Varmista, että piirtoalustalla ei ole valittu mitään visualisointia. Valitse **Näkymä** ja tarkista näyttöasetukset.

    * Näet lukunäkymässä seuraavan.

     ![](media/power-bi-change-report-display-settings/power-bi-page-view-menu-new.png)
    * Näet muokkausnäkymässä seuraavan.

    ![](media/power-bi-change-report-display-settings/power-bi-view-editing-view.png)

1. Katsotaanpa, miltä sivu näyttää käyttämällä **Todellinen koko** -asetusta.

   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)

   Ei kovin hyvältä, ja koontinäytössä on nyt kaksinkertaiset vierityspalkit.
2. Vaihda asetukseksi **Sovita leveyteen**.

   ![](media/power-bi-change-report-display-settings/pbi_fit_to_width.png)

   Se näyttää paremmalta. Vierityspalkkeja on nyt kaksi, mutta niitä on helpompi lukea tarkemmin.

## <a name="change-the-default-view-for-a-report-page"></a>Raportin sivun oletusnäkymän muuttaminen
Jos olet raportin *laatija*, voit muuttaa raportin sivujen oletusnäkymää. Kun jaat raportin muiden kanssa, raportin sivut avataan käyttämällä määrittämääsi näkymää. Raportin *lukijat* voivat vaihtaa tätä näkymää, mutta he eivät voi tallentaa muutoksiaan, kun he poistuvat raportista.

1. Vaihda raportin **Uudet myymälät**-sivulla takaisin **Todellinen koko** -näkymään.

   ![](media/power-bi-change-report-display-settings/power-bi-actual-size.png)

2. Määritä **Alueen kuukausimyynti** -sivulla asetukseksi **Sovita leveyteen**.

3. Säilytä **Yleiskatsaus**-raporttisivulla oletusarvoinen Näkymä-asetus.

4. Tallenna raportti nyt valitsemalla **Tiedosto > Tallenna**. Seuraavan kerran avaat tämän raportin, sivut näytetään käyttämällä uutta Näkymä-asetusta. Katsotaanpa, miten tämä tehdään.

   ![](media/power-bi-change-report-display-settings/power-bi-save.png)
3. Valitse nykyisen työtilan nimi yläreunan siirtymispalkista, jotta voit palata tähän työtilaan.  

   ![](media/power-bi-change-report-display-settings/power-bi-my-workspace.png)
4. Valitse **Raportit**-välilehti ja valitse sama raportti (jälleenmyyjäanalyysimalli).

    ![](media/power-bi-change-report-display-settings/power-bi-new-report2.png)
5. Avaa raportin jokainen sivu, jotta näet uudet asetukset.

   ![](media/power-bi-change-report-display-settings/power-bi-page-view.gif)

## <a name="now-lets-explore-the-page-size-setting"></a>Tutustutaanpa nyt *Sivun koko* -asetukseen.
Sivun koon asetukset ovat käytettävissä vain [muokkausnäkymässä](service-interact-with-a-report-in-editing-view.md), joten sinulla on oltava muokkausoikeudet (*laatija*) raporttiin sivun koon asetusten muuttamiseksi. Jos olet yhdistänyt johonkin Microsoftin [malliin](sample-datasets.md), sinulla on *laatijan* käyttöoikeudet näihin raportteihin.

1. Avaa [jälleenmyyjäanalyysimallin](sample-retail-analysis.md) ”Alueen kuukausimyynti” -sivu muokkausnäkymässä.
2. Varmista, että piirtoalustalla ei ole valittu mitään visualisointia.  Valitse **Visualisoinnit**-ruudussa maalirullakuvake![](media/power-bi-change-report-display-settings/power-bi-paintroller.png).
3. Valitse **Sivun koko** &gt; **Tyyppi**, jos haluat näyttää sivun koon asetukset.

   ![](media/power-bi-change-report-display-settings/power-bi-page-size-menu-new.png)
4. Valitse **Letter**.  Piirtoalustalla vain sisältö, joka mahtuu 816 x 1 056 kuvapisteeseen (Letter-koko), näkyy piirtoalustan valkoisella osalla.

   ![](media/power-bi-change-report-display-settings/power-bi-letter-new.png)
5. Valitse **Sivun koko** **16:9**-suhde.

   ![](media/power-bi-change-report-display-settings/power-bi-16-to-9-new.png)

   Raportin sivulla käytetään kuvasuhdetta, jonka leveys on 16 ja korkeus 9. Voit nähdä käytetyn todelliset kuvapistekoon katsomalla harmaana näkyviä leveys- ja korkeuskenttiä (1 280 x 720). Raportin piirtoalustan ympärillä on paljon tyhjää tilaa, koska määritimme aiemmin **Näkymä**-asetukseksi ”Sovita leveyteen”.
7. Jatka tutustumalla **Sivun koko** -asetuksiin.

## <a name="use-page-view-and-page-size-together"></a>Sivun Näkymä- ja Sivun koko -asetusten käyttö yhdessä
Käyttämällä sivun Näkymä- ja Sivun koko -asetuksia yhdessä voit luoda upean raportin, jonka voit jakaa ystävien kanssa tai upottaa toiseen sovellukseen.

Tässä harjoituksessa luot raportin sivun. Se näytetään sovelluksessa, jonka tilan leveys on 500 kuvapistettä ja korkeus 750 kuvapistettä.

Edellisessä vaiheessa näimme, että raportin sivun leveys on tällä hetkellä 1 280 kuvapistettä ja korkeus 720 kuvapistettä. Tiedämme siis, että meidän on muokattava kokoa reippaasti, jotta kaikki visualisoinnit mahtuvat mukaan.

1. Muuta visualisointien kokoa ja siirrä niitä siten, että ne mahtuvat alle puoleen tilaan nykyisestä piirtoalueesta.

    ![](media/power-bi-change-report-display-settings/power-bi-custom-view.gif)
2. Valitse **Sivun koko** &gt; **Mukauta**.
3. Määritä leveydeksi 500 ja korkeudeksi 750.

    ![](media/power-bi-change-report-display-settings/power-bi-custom-new.png)
4. Parantele raportin sivua siten, että se näyttää mahdollisimman hyvältä. Tee mukautukset vaihtamalla asetusten **Näkymä > Todellinen koko** ja **Näkymä > Sovita sivulle** välillä.

    ![](media/power-bi-change-report-display-settings/power-bi-final-new.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Raporttien luominen Cortanaa varten](service-cortana-answer-cards.md)

Palaa artikkeliin [Power BI- raportin sivun näyttöasetukset](power-bi-report-display-settings.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
