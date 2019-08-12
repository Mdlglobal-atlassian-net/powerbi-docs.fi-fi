---
title: Taulukkovisualisoinnit Power BI -raporteissa ja raporttinäkymissä
description: Opetusohjelma siitä, miten Power BI -raporttien ja raporttinäkymien taulukkovisualisointien kanssa työskennellään ja miten sarakkeiden leveyksiä muutetaan.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 857db3240385e9bf1b4e0416cc1200d1a029d73e
ms.sourcegitcommit: cc4b18d55b2dca8fdb1bef00f53a0a808c41432a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/09/2019
ms.locfileid: "68867203"
---
# <a name="tables-in-power-bi-reports-and-dashboards"></a>Taulukot Power BI -raporteissa ja raporttinäkymissä

Taulukko on ruudukko, joka sisältää tietoja järjestettynä loogiseen sarjaan rivejä ja sarakkeita. Se voi sisältää myös otsikkoja ja summarivin. Taulukot toimivat hyvin kvantitatiivisessa vertailussa, jossa tarkastellaan yhden luokan monia arvoja. Esimerkiksi tässä taulukossa näytetään **luokan** viisi eri mittaria.

![Näyttökuva taulukosta, jossa näytetään luokan viisi eri mittaria.](media/power-bi-visualization-tables/table.png)

Voit luoda taulukoita raporteissa ja ristiinkorostaa taulukon elementtejä muiden samalla raporttisivulla olevien visualisointien kanssa. Voit valita rivejä, sarakkeita ja jopa yksittäisiä soluja ristiinkorostettavaksi. Voit myös kopioida ja liittää yksittäisten ja useiden solujen valintoja muihin sovelluksiin.

## <a name="when-to-use-a-table"></a>Milloin taulukkoa kannattaa käyttää?

Taulukko on hyvä vaihtoehto:

* yksityiskohtaisen tiedon ja tarkkojen arvojen selaamiseen ja vertailemiseen (visuaalisten esitysten sijaan).

* tietojen esittämiseen taulukkomuodossa.

* numeeristen tietojen luokiteltuun esittämiseen.

## <a name="prerequisites"></a>Edellytykset

* Power BI -palvelu tai Power BI Desktop

* Jälleenmyyntianalyysimallin raportti

## <a name="get-the-retail-analysis-sample-report"></a>Jälleenmyyntianalyysimallin raportin hankkiminen

Näissä ohjeissa käytetään jälleenmyyntianalyysimallia. Visualisoinnin luominen edellyttää tietojoukon ja raportin muokkausoikeuksia. Kaikeksi onneksi Power BI -mallit ovat kaikki muokattavissa. Jos joku jakaa raportin kanssasi, et voi luoda visualisointeja raporteissa. Voit seurata mukana hankkimalla [jälleenmyyntianalyysimallin raportin](../sample-datasets.md).

Kun olet hankkinut **jälleenmyyntianalyysimallin** tietojoukon, voit aloittaa.

## <a name="create-a-table"></a>Luo taulukko

Luot artikkelin alussa kuvatun taulukon, jossa esitetään myyntiarvot nimikeluokan mukaisesti.

1. Valitse **Oma työtila** -kohdasta **Tietojoukot** > **Luo raportti**.

    ![Näyttökuva tietojoukoista > Luo raportti.](media/power-bi-visualization-tables/power-bi-create-a-report.png)

1. Valitse **Kentät**-ruudusta **Nimike** > **luokka**.

    Power BI luo automaattisesti taulukon, jossa luetellaan kaikki luokat.

    ![luokan lisäämisen tulos](media/power-bi-visualization-tables/power-bi-table1.png)

1. Valitse **Myynti > Keskimääräinen yksikköhinta** ja **Myynti > Viime vuoden myynti**

1. Valitse sitten **Myynti > Tämän vuoden myynti** ja valitse kaikki kolme vaihtoehtoa: **Arvo**, **Tavoite** ja **Tila**.

1. Etsi **Visualisoinnit**-ruudusta **Arvot**, ja vedä ja pudota niitä, kunnes kaavion sarakkeiden järjestys vastaa tämän sivun ensimmäistä kuvaa. **Arvot**-säilö näyttää tältä.

    ![Arvot](media/power-bi-visualization-tables/power-bi-table2.png)

1. Kiinnitä taulukko koontinäytölle valitsemalla Kiinnitä-kuvake. ![nasta](media/power-bi-visualization-tables/pbi_pintile.png) visualisoinnin oikeassa yläkulmassa.

## <a name="format-the-table"></a>Taulukon muotoileminen

Taulukkoa voi muotoilla monella eri tavalla. Käsittelemme tässä artikkelissa niistä vain muutamia. Hyvä tapa oppia lisää muista muotoiluvaihtoehdoista on avata **Muotoilu**-ruutu (maalirullakuvake ![maalirulla](media/power-bi-visualization-tables/power-bi-format.png)) ja tutustua niihin.

* Kokeile taulukkoruudukon muotoilemista. Olet tässä lisännyt sinisen pystyruudukon, lisännyt riveihin tilaa, paksuntanut ääriviivaa ja kasvattanut tekstin kokoa.

    ![Ruudukkokortti](media/power-bi-visualization-tables/power-bi-table-gridnew.png)

    ![tulokset näyttävä taulukko](media/power-bi-visualization-tables/power-bi-table-grid3.png)

* Vaihda sarakeotsikoiden taustaväriä, lisää ääriviiva ja kasvata tekstin kokoa.

    ![Sarakkeiden otsikkokortti](media/power-bi-visualization-tables/power-bi-table-column-headers.png)

    ![otsikoiden muotoilu taulukossa](media/power-bi-visualization-tables/power-bi-table-column2.png)

* Voit myös käyttää muotoilua yksittäisissä sarakkeissa ja sarakeotsikoissa. Aloita laajentamalla **Kentän muotoilu** ja valitsemalla muotoiltava sarake avattavasta luettelosta. **Kentän muotoilun** avulla voit tehdä esimerkiksi seuraavia määrityksiä sarakearvojen mukaan: näyttöyksiköt, fontin väri, desimaalipaikkojen määrä, tausta, tasaus ja paljon muuta. Kun olet säätänyt asetukset, valitse, otetaanko ne käyttöön myös otsikossa ja summariveissä.

    ![Tämän vuoden myynti -kentän muotoilu](media/power-bi-visualization-tables/power-bi-field-formatting.png)

    ![Tämän vuoden myynti -kentän muotoilu taulukossa](media/power-bi-visualization-tables/power-bi-field-formatting-1.png)

* Hieman lisämuokkausta ja tässä on lopullinen taulukkomme.

    ![taulukko, joka sisältää kaikki tähän asti käytetyt muotoilut](media/power-bi-visualization-tables/power-bi-table-format.png)

### <a name="conditional-formatting"></a>Ehdollinen muotoilu

*Ehdollinen muotoilu* on yksi muotoilutyyppi. Power BI soveltaa kenttien ehdollista muotoilua **Visualisoinnit**-ruudun **Arvot**-säilöön.

Taulukoiden ehdollisen muotoilun avulla voit määrittää mukautettuja solujen taustavärejä ja tekstin värejä solujen arvoihin perustuen. Voit käyttää myös liukuvärejä.

1. Valitse **Visualisoinnit**-ruudussa **Kentät**-kuvake![kentät-kuvake](media/power-bi-visualization-tables/power-bi-fields-icon.png).

1. Valitse alaspäin osoittava nuoli sen **Arvot**-säilön vierestä, jota haluat muotoilla (tai napsauta kenttää hiiren kakkospainikkeella).

    > [!NOTE]
    > Voit hallita kenttien ehdollista muotoilua ainoastaan **Kenttien** **Arvot**-alueella.

    ![polku Taustaväriasteikkoihin](media/power-bi-visualization-tables/power-bi-conditional-formatting-background.png)

1. Valitse **Taustaväri**.

1. Voit määrittää avautuvassa valintaikkunassa värin sekä **vähimmäisarvon** ja **enimmäisarvon**. Jos valitset **Erkautuva**-vaihtoehdon, voit määrittää myös valinnaisen **keskiarvon**.

    ![Taustaväriasteikot-ikkuna](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)

    Käytetäänpä räätälöityä muotoilua Keskimääräisen nimikehintamme arvoihin. Valitse **Erkautuva**, lisää vähän väriä ja valitse **OK**.

    ![erkautuvia värejä esittävä taulukko](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
1. Lisää taulukkoon uusi kenttä, jossa on sekä positiivisia että negatiivisia arvoja. Valitse **Myynti > Myyntivariaatio yhteensä**.

    ![oikeassa reunassa näkyvä uusi kenttä](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)

1. Valitse tietopalkin ehdollinen muotoilu painamalla **Myyntivariaatio yhteensä** -kohdan vieressä olevaa alaspäin osoittavaa nuolta ja valitsemalla **Ehdollinen muotoilu > Tietopalkit**.

    ![Tietopalkkien valintapolku](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars.png)

1. Määritä avautuvassa valintaikkunassa värit **positiiviselle palkille** ja **negatiiviselle palkille**, valitse **Näytä vain palkki** -vaihtoehto ja tee kaikki muut haluamasi muutokset.

    ![Näytä vain palkki -valintamerkki](media/power-bi-visualization-tables/power-bi-data-bars.png)

1. Valitse **OK**.

    Tietopalkit korvaavat taulukon numeroarvot, mikä tekee siitä helpommin luettavan.

    ![sama taulukko, jossa viimeiseen sarakkeeseen on lisätty palkit](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)

Jos haluat poistaa ehdollisen muotoilun visualisoinnista, napsauta kenttää uudelleen hiiren kakkospainikkeella ja valitse **Poista ehdollinen muotoilu**.

> [!TIP]
> Ehdollinen muotoilu on käytettävissä myös **Muotoilu**-ruudusta. Valitse muokattava arvo ja aseta sitten **Väriasteikko**- tai **Tietopalkki**-arvoksi **Käytössä**, jolloin käytetään oletusasetuksia. Jos haluat mukauttaa asetuksia, valitse **Lisäasetukset**.

## <a name="copy-values-from-power-bi-tables-for-use-in-other-applications"></a>Arvojen kopiointi Power BI -taulukoista muissa sovelluksissa käytettäviksi

Matriisissa tai taulukossa voi olla sisältöä, jota haluat käyttää muissa sovelluksissa, kuten Dynamics CRM:ssä, Excelissä tai jopa muissa Power BI -raporteissa. Power BI:ssä voit hiiren kakkospainikkeella kopioida tiedot yhteen soluun tai valikoiman soluja leikepöydälle ja liittää ne toisiin sovelluksiin.

Kopioi yhden solun arvo seuraavasti:

1. Valitse kopioitava solu.

1. Napsauta solua hiiren kakkospainikkeella.

1. Valitse **Kopioi** > **Kopioi arvo**.

    ![Kopiointivalinnat](media/power-bi-visualization-tables/power-bi-copy-value.png)

    Solun muotoilematon arvo on leikepöydällä, josta voit liittää sen toiseen sovellukseen.

Kopioi useampi kuin yksi solu seuraavasti:

1. Valitse solualue tai valitse **Ctrl**-näppäimellä yksi tai useampi solu.

1. Napsauta hiiren kakkospainikkeella yhden valitsemasi solun sisällä.

1. Valitse **Kopioi** > **Kopioi valinta**.

    ![Kopiointivalinnat](media/power-bi-visualization-tables/power-bi-copy-selection.png)

    Kopio sisältää sarakkeiden ja rivien otsikot.

    ![Liitä Exceliin](media/power-bi-visualization-tables/power-bi-paste-selection.png)

## <a name="adjust-the-column-width-of-a-table"></a>Taulukon sarakeleveyden muuttaminen

Joskus Power BI katkaisee raportin tai näkymän sarakeotsikon. Voit näyttää sarakkeen koko nimen liikuttamalla hiiren osoitinta otsikon oikealla puolella nähdäksesi kaksoisnuolet, ja valitsemalla ja vetämällä.

![videolähennys sarakkeen koon muuttamisesta](media/power-bi-visualization-tables/resizetable.gif)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

Sovellettaessa sarakemuotoilua voit valita vain yhden tasausvaihtoehdon saraketta kohti: **Automaattinen**, **vasen**, **keskitetty**, **oikea**. Yleensä sarake sisältää vain tekstiä tai numeroita eikä niiden yhdistelmiä. Jos sarake sisältää sekä numeroita että tekstiä, **Automaattinen** tasaa tekstin vasemmalle ja numerot oikealle. Tämä käyttäytyminen tukee kieliä, jotka luetaan vasemmalta oikealle.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Puukartat Power BI:ssä](power-bi-visualization-treemaps.md)

* [Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
