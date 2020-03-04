---
title: Taulukkovisualisoinnit Power BI -raporteissa ja raporttinäkymissä
description: Opetusohjelma siitä, miten Power BI -raporttien ja raporttinäkymien taulukkovisualisointien kanssa työskennellään ja miten sarakkeiden leveyksiä muutetaan.
author: mihart
ms.reviewer: willt
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/10/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: de0328a35922279082c93a9a2d2a4948f1af7dc5
ms.sourcegitcommit: 4d98274aa0b9aa09db99add2dda91a3ba8fed40b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576826"
---
# <a name="tables-in-power-bi-reports-and-dashboards"></a>Taulukot Power BI -raporteissa ja raporttinäkymissä

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Taulukko on ruudukko, joka sisältää tietoja järjestettynä loogiseen sarjaan rivejä ja sarakkeita. Se voi sisältää myös otsikkoja ja summarivin. Taulukot toimivat hyvin kvantitatiivisessa vertailussa, jossa tarkastellaan yhden luokan monia arvoja. Esimerkiksi tässä taulukossa näytetään **luokan** viisi eri mittaria.

![Näyttökuva taulukosta, jossa näytetään luokan viisi eri mittaria.](media/power-bi-visualization-tables/power-bi-table-grid3.png)

Voit luoda taulukoita raporteissa ja ristiinkorostaa taulukon elementtejä muiden samalla raporttisivulla olevien visualisointien kanssa. Voit valita rivejä, sarakkeita ja jopa yksittäisiä soluja ristiinkorostettavaksi. Voit myös kopioida ja liittää yksittäisten ja useiden solujen valintoja muihin sovelluksiin.

## <a name="when-to-use-a-table"></a>Milloin taulukkoa kannattaa käyttää?

Taulukko on hyvä vaihtoehto:

* yksityiskohtaisen tiedon ja tarkkojen arvojen selaamiseen ja vertailemiseen (visuaalisten esitysten sijaan).

* tietojen esittämiseen taulukkomuodossa.

* numeeristen tietojen luokiteltuun esittämiseen.

## <a name="prerequisite"></a>Edellytys

Tässä opetusohjelmassa käytetään [Jälleenmyyntianalyysimallin PBIX-tiedostoa](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. **Jälleenmyyntianalyysimallin PBIX-tiedoston löytäminen**

1. Avaa **Jälleenmyyntianalyysimallin PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.


## <a name="create-a-table"></a>Luo taulukko

Luot artikkelin alussa kuvatun taulukon, jossa esitetään myyntiarvot nimikeluokan mukaisesti.


1. Valitse **Kentät**-ruudusta **Nimike** > **luokka**.

    Power BI luo automaattisesti taulukon, jossa luetellaan kaikki luokat.

    ![luokan lisäämisen tulos](media/power-bi-visualization-tables/power-bi-table1.png)

1. Valitse **Myynti > Keskimääräinen yksikköhinta** ja **Myynti > Viime vuoden myynti**

1. Valitse sitten **Myynti > Tämän vuoden myynti** ja valitse kaikki kolme vaihtoehtoa: **Arvo**, **Tavoite** ja **Tila**.

1. Etsi **Visualisoinnit**-ruudusta **Arvot** ja valitse arvoja, kunnes kaavion sarakkeiden järjestys vastaa tämän sivun ensimmäistä kuvaa. Vedä arvot säilöön tarvittaessa. **Arvot**-säilö näyttää tältä.

    ![Arvot](media/power-bi-visualization-tables/power-bi-table2.png)


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

*Ehdollinen muotoilu* on yksi muotoilutyyppi. Power BI voi soveltaa ehdollista muotoilua mihin tahansa kenttään, jonka lisäsit **Visualisoinnit**-ruudun **Arvot**-säilöön.

![Visualisointi-ruutu](media/power-bi-visualization-tables/power-bi-table-values.png)

Taulukoiden ehdollisen muotoilun avulla voit määrittää kuvakkeita, URL-osoitteita, solun taustavärejä ja fontin värejä soluarvojen perusteella. Voit käyttää myös liukuvärejä.

1. Avaa **Muotoile**-ruudussa **Ehdollinen muotoilu** -kortti.

    ![Ehdollinen muotoilu -kortti](media/power-bi-visualization-tables/power-bi-conditional.png)

1. Valitse muotoiltava kenttä ja ota **taustavärin** liukusäädin käyttöön. Power BI käyttää liukuväriä sarakkeen arvojen perusteella. Jos haluat muuttaa oletusvärejä, valitse **Lisäohjausobjektit**.

    Jos valitset **Erkautuva**-vaihtoehdon, voit määrittää myös valinnaisen **keskiarvon**.

    ![Taustaväriasteikot-ikkuna](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)

    Käytetäänpä räätälöityä muotoilua Keskimääräisen nimikehintamme arvoihin. Valitse **Erkautuva**, lisää vähän väriä ja valitse **OK**.

    ![erkautuvia värejä esittävä taulukko](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
1. Lisää taulukkoon uusi kenttä, jossa on sekä positiivisia että negatiivisia arvoja. Valitse **Myynti > Myyntivariaatio yhteensä**.

    ![oikeassa reunassa näkyvä uusi kenttä](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)

1. Lisää tietopalkin ehdollinen muotoilu ottamalla **Tietopalkit**-liukusäädin käyttöön.  

    ![Ehdollinen muotoilu -kortti, jossa tietopalkit on otettu käyttöön](media/power-bi-visualization-tables/power-bi-data-bar-matrix.png)

1. Jos haluat mukauttaa tietopalkkeja, valitse **Lisäohjausobjektit**. Määritä avautuvassa valintaikkunassa värit **positiiviselle palkille** ja **negatiiviselle palkille**, valitse **Näytä vain palkki** -vaihtoehto ja tee kaikki muut haluamasi muutokset.

    ![Näytä vain palkki -valintamerkki](media/power-bi-visualization-tables/power-bi-data-bar.png)

1. Valitse **OK**.

    Tietopalkit korvaavat taulukon numeroarvot, mikä tekee siitä helpommin luettavan.

    ![sama taulukko, jossa viimeiseen sarakkeeseen on lisätty palkit](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)

1. Lisää visuaalisia vihjeitä taulukkoosi *ehdollisten kuvakkeiden* avulla.  Valitse **Ehdollinen muotoilu** -kortissa **Tämän vuoden myynti** avattavasta valikosta. Ota **Kuvakkeet**-liukusäädin **käyttöön**.  Jos haluat mukauttaa kuvakkeita, valitse **Lisäohjausobjektit**.

    ![Esimerkkitaulukko, johon on lisätty kuvakkeita](media/power-bi-visualization-tables/power-bi-table-icons.png)


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

## <a name="adjust-the-column-width-of-a-table"></a>Taulukon sarakeleveyden muuttaminen

Joskus Power BI katkaisee raportin tai näkymän sarakeotsikon. Voit näyttää sarakkeen koko nimen liikuttamalla hiiren osoitinta otsikon oikealla puolella nähdäksesi kaksoisnuolet, ja valitsemalla ja vetämällä.

![videolähennys sarakkeen koon muuttamisesta](media/power-bi-visualization-tables/resizetable.gif)


## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

* Sovellettaessa sarakemuotoilua voit valita vain yhden tasausvaihtoehdon saraketta kohti: **Automaattinen**, **vasen**, **keskitetty**, **oikea**. Yleensä sarake sisältää vain tekstiä tai numeroita eikä niiden yhdistelmiä. Jos sarake sisältää sekä numeroita että tekstiä, **Automaattinen** tasaa tekstin vasemmalle ja numerot oikealle. Tämä käyttäytyminen tukee kieliä, jotka luetaan vasemmalta oikealle.

* Jos taulukon solujen tai otsikoiden tekstitiedoissa on uusi rivi -merkkejä, nämä merkit ohitetaan, ellet vaihda tekstin rivitysasetusta elementin liittyvässä muotoiluruudun kortissa. 


## <a name="next-steps"></a>Seuraavat vaiheet

* [Puukartat Power BI:ssä](power-bi-visualization-treemaps.md)

* [Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
