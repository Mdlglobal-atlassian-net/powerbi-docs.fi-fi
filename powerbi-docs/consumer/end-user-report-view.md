---
title: Raporttisivun näyttökoon ja kuvasuhteen muuttaminen
description: Power BI -raportin sivun näyttöasetusten muuttaminen
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 075751a95512a7d06e22eb104aacf056978a93ea
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54275774"
---
# <a name="change-the-size-of-a-report-page"></a>Raportin sivun koon muuttaminen
Opit [edellisessä artikkelissa ja videossa](../power-bi-report-display-settings.md) kaksi tapaa hallita Power BI -raporttien sivun näyttöä: **Näkymä** ja **Sivun koko**. Sivun Näkymä ja Sivun koko ovat käytettävissä sekä Power BI -palvelussa että Power BI Desktopissa. Niiden ulkonäkö ja toiminnot ovat lähes samat, mutta tässä opetusohjelmassa käytämme Power BI -palvelua.

### <a name="prerequisites"></a>Edellytykset
- Power BI -palvelu   
- [Jälleenmyyntianalyysimallin raportti](../sample-retail-analysis.md)

## <a name="first-lets-change-the-page-view-setting"></a>Muutetaanpa ensiksi sivun Näkymä-asetusta.

1. Avaa raportti lukunäkymässä tai muokkausnäkymässä, ja valitse Raportti-välilehdessä **Uudet myymälät**. Tämä raportin sivu näytetään oletusarvoisesti käyttämällä **Sovita sivulle** -asetusta.  Tässä tapauksessa Sovita sivulle -asetus näyttää raportin sivun ilman vierityspalkkeja, mutta jotkin tiedot ja otsikot ovat liian pieniä luettaviksi.

   ![raportti näkyvissä pohjassa](media/end-user-report-view/pbi_fit_to_page.png)
2. Varmista, että piirtoalustalla ei ole valittu mitään visualisointia. Valitse **Näkymä** ja tarkista näyttöasetukset.

   * Näet lukunäkymässä seuraavan.

     ![Avattava Näytä-valikko, jossa on valittuna Sovita sivulle](media/end-user-report-view/power-bi-page-view-menu-new.png)
   * Näet muokkausnäkymässä seuraavan.

     ![Avattava Näytä-valikko, jossa on valittuna Sovita sivulle](media/end-user-report-view/power-bi-view-editing-view.png)

3. Katsotaanpa, miltä sivu näyttää käyttämällä **Todellinen koko** -asetusta.

   ![raportti näkyvissä pohjassa, kaksi vierityspalkkia](media/end-user-report-view/power-bi-actal-size2.png)

   Ei kovin hyvältä, ja koontinäytössä on nyt kaksinkertaiset vierityspalkit.
4. Vaihda asetukseksi **Sovita leveyteen**.

   ![raportti näkyvissä ilman vierityspalkkia, vain yksi vierityspalkki](media/end-user-report-view/pbi_fit_to_width.png)

   Se näyttää paremmalta. Vierityspalkkeja on yhä yksi, mutta sitä on helpompi lukea tarkemmin.

## <a name="change-the-default-view-for-a-report-page"></a>Raportin sivun oletusnäkymän muuttaminen
Jos olet raportin *laatija*, voit muuttaa raportin sivujen oletusnäkymää. Kun jaat raportin muiden kanssa, raportin sivut avataan käyttämällä määrittämääsi näkymää. Raportin *lukijat* voivat vaihtaa tätä näkymää, mutta he eivät voi tallentaa muutoksiaan, kun he poistuvat raportista.

1. Vaihda raportin **Uudet myymälät**-sivulla takaisin **Todellinen koko** -näkymään.

   ![Avattava Näytä-valikko, jossa on valittuna Todellinen koko](media/end-user-report-view/power-bi-actual-size.png)

2. Määritä **Alueen kuukausimyynti** -sivulla asetukseksi **Sovita leveyteen**.

3. Säilytä **Yleiskatsaus**-raporttisivulla oletusarvoinen Näkymä-asetus.

4. Tallenna raportti nyt valitsemalla **Tiedosto > Tallenna**. Seuraavan kerran avaat tämän raportin, sivut näytetään käyttämällä uutta Näkymä-asetusta. Katsotaanpa, miten tämä tehdään.

   ![Tiedosto-valikko, jossa on valittuna Tallenna](media/end-user-report-view/power-bi-save.png)
3. Valitse nykyisen työtilan nimi yläreunan siirtymispalkista, jotta voit palata tähän työtilaan.  

   ![Yläreunan valikkorivi, jossa näkyy navigointipolku](media/end-user-report-view/power-bi-my-workspace.png)
4. Valitse **Raportit**-välilehti ja valitse sama raportti (jälleenmyyjäanalyysimalli).

    ![Sisältönäkymä, jossa on valittuna Raportit-välilehti](media/end-user-report-view/power-bi-new-report2.png)
5. Avaa raportin jokainen sivu, jotta näet uudet asetukset.

   ![video, jossa näkyy, miten näyttöasetuksia muutetaan](media/end-user-report-view/power-bi-page-view.gif)

## <a name="now-lets-explore-the-page-size-setting"></a>Tutustutaanpa nyt *Sivun koko* -asetukseen.
Sivun koon asetukset ovat käytettävissä vain [muokkausnäkymässä](../service-interact-with-a-report-in-editing-view.md), joten sinulla on oltava muokkausoikeudet (*laatija*) raporttiin sivun koon asetusten muuttamiseksi. Jos olet yhdistänyt johonkin Microsoftin [malliin](../sample-datasets.md), sinulla on *laatijan* käyttöoikeudet näihin raportteihin.

1. Avaa [jälleenmyyjäanalyysimallin](../sample-retail-analysis.md) ”Alueen kuukausimyynti” -sivu muokkausnäkymässä.
2. Varmista, että piirtoalustalla ei ole valittu mitään visualisointia.  Valitse **Visualisoinnit**-ruudussa maalirullakuvake![](media/end-user-report-view/power-bi-paintroller.png).
3. Valitse **Sivun koko** &gt; **Tyyppi**, jos haluat näyttää sivun koon asetukset.

   ![Sivun koon kortti laajennettuna ja 16:9 valittuna](media/end-user-report-view/power-bi-page-size-menu-new.png)
4. Valitse **Letter**.  Piirtoalustalla vain sisältö, joka mahtuu 816 x 1 056 kuvapisteeseen (Letter-koko), näkyy piirtoalustan valkoisella osalla.

   ![Raportin pohja, jossa Sivun koko -kortti on laajennettuna ja Tyyppi > Letter on valittuna](media/end-user-report-view/power-bi-letter-new.png)
5. Valitse **Sivun koko** **16:9**-suhde.

   ![Sivun koko -kortti laajennettuna ja Tyyppi > 16:9 valittuna](media/end-user-report-view/power-bi-16-to-9-new.png)

   Raportin sivulla käytetään kuvasuhdetta, jonka leveys on 16 ja korkeus 9. Voit nähdä käytetyn todelliset kuvapistekoon katsomalla harmaana näkyviä leveys- ja korkeuskenttiä (1 280 x 720). Raportin piirtoalustan ympärillä on paljon tyhjää tilaa, koska määritimme aiemmin **Näkymä**-asetukseksi ”Sovita leveyteen”.
7. Jatka tutustumalla **Sivun koko** -asetuksiin.

## <a name="use-page-view-and-page-size-together"></a>Sivun Näkymä- ja Sivun koko -asetusten käyttö yhdessä
Käyttämällä sivun Näkymä- ja Sivun koko -asetuksia yhdessä voit luoda upean raportin, jonka voit jakaa ystävien kanssa tai upottaa toiseen sovellukseen.

Tässä harjoituksessa luot raportin sivun. Se näytetään sovelluksessa, jonka tilan leveys on 500 kuvapistettä ja korkeus 750 kuvapistettä.

Edellisessä vaiheessa näimme, että raportin sivun leveys on tällä hetkellä 1 280 kuvapistettä ja korkeus 720 kuvapistettä. Tiedämme siis, että meidän on muokattava kokoa reippaasti, jotta kaikki visualisoinnit mahtuvat mukaan.

1. Muuta visualisointien kokoa ja siirrä niitä siten, että ne mahtuvat alle puoleen tilaan nykyisestä piirtoalueesta.

    ![video, jossa näytetään visualisointien koon muuttaminen ja siirtäminen pohjassa](media/end-user-report-view/power-bi-custom-view.gif)
2. Valitse **Sivun koko** &gt; **Mukauta**.
3. Määritä leveydeksi 500 ja korkeudeksi 750.

    ![Muotoilu-ruutu, jossa Sivun koko -kortti on laajennettuna](media/end-user-report-view/power-bi-custom-new.png)
4. Parantele raportin sivua siten, että se näyttää mahdollisimman hyvältä. Tee mukautukset vaihtamalla asetusten **Näkymä > Todellinen koko** ja **Näkymä > Sovita sivulle** välillä.

    ![raportin pohja, jossa Muotoilu-ruutu on laajennettuna](media/end-user-report-view/power-bi-final-new.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Raporttien luominen Cortanaa varten](../service-cortana-answer-cards.md)

Palaa artikkeliin [Power BI- raportin sivun näyttöasetukset](../power-bi-report-display-settings.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
