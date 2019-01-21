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
ms.date: 10/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 2c909f1f7d2c1b500d37de0e4617e10c79977c96
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284767"
---
# <a name="tables-in-power-bi-reports-and-dashboards"></a>Taulukot Power BI -raporteissa ja raporttinäkymissä
Taulukko on ruudukko, joka sisältää tietoja järjestettynä loogiseen sarjaan rivejä ja sarakkeita. Se voi sisältää myös otsikkoja ja summarivin. Taulukot toimivat hyvin kvantitatiivisessa vertailussa, jossa tarkastellaan moni arvoja tietystä kategoriasta. Esimerkiksi tässä taulukossa näkyvät **luokan** viisi eri mittayksikköä.

![](media/power-bi-visualization-tables/table.png)

Voit luoda taulukoita raporteissa ja ristiinkorostaa taulukon elementtejä muiden samalla raporttisivulla olevien visualisointien kanssa.  Lisäksi voit valita rivejä, sarakkeita ja jopa yksittäisiä soluja ristiinkorostettavaksi. Yksittäisten ja useiden solujen valintoja voi kopioida ja liittää muihin sovelluksiin.

## <a name="when-to-use-a-table"></a>Milloin taulukkoa kannattaa käyttää?
Taulukko on hyvä vaihtoehto:

* yksityiskohtaisen tiedon ja tarkkojen arvojen selaamiseen ja vertailemiseen (visuaalisten esitysmuotojen sijaan).
* tietojen esittämiseen taulukkomuodossa.
* numeeristen tietojen luokiteltuun esittämiseen.   

> [!NOTE]
> Jos taulukossa on liikaa arvoja, harkitse sen muuntamista matriisiksi ja/tai alirakenteen käyttämistä. Taulukko näyttää enintään 3 500 arvopistettä.

## <a name="prerequisites"></a>Edellytykset
- Power BI -palvelu tai Power BI Desktop
- Jälleenmyyntianalyysimalli

## <a name="create-a-table"></a>Luo taulukko
Luomme yllä esitetyn taulukon, jossa esitetään myyntiarvot nimikeluokan mukaisesti. Kirjaudu Power BI -palveluun (ei Desktopiin), jotta voit seurata ohjeita. Valitse **Nouda tiedot \> Mallit \> Jälleenmyyntianalyysimalli > Yhdistä** ja valitse **Koontinäyttö**. Visualisoinnin luominen edellyttää tietojoukon ja raportin muokkausoikeuksia. Kaikeksi onneksi Power BI -mallit ovat kaikki muokattavissa. Jos raportti on jaettu kanssasi, et pysty luomaan visualisointeja raporteissa.

1. Valitse vasemmasta siirtymisruudusta **Työtilat > Oma työtila**.    
2. Valitse Tietojoukot-välilehti ja vieritä alas juuri lisäämäsi Jälleenmyyntianalyysimallin tietojoukkoon.  Valitse **Raportin luominen** -kuvake.

    ![raporttikuvakkeen osoittaminen](media/power-bi-visualization-tables/power-bi-create-report.png)
2. Valitse raporttieditorissa **Nimike** > **luokka**.  Power BI luo automaattisesti taulukon, jossa luetellaan kaikki luokat.

    ![luokan lisäämisen tulos](media/power-bi-visualization-tables/power-bi-table1.png)
3. Valitse **Myynti > Keskimääräinen nimikehinta** ja **Myynti > Viime vuoden myynti** ja **Myynti > Tämän vuoden myynti** ja valitse kaikki kolme vaihtoehtoa (Arvo, Tavoite ja Tila).   
4. Etsi Visualisoinnit-ruudussa **Arvot** ja vedä ja pudota niitä, kunnes kaavion sarakkeiden järjestys vastaa tämän sivun ensimmäistä kuvaa.  Arvojen tulee näyttää tältä.

    ![Arvot](media/power-bi-visualization-tables/power-bi-table2.png)
5. Kiinnitä taulukko koontinäytölle valitsemalla Kiinnitä-kuvake.  

     ![nasta](media/power-bi-visualization-tables/pbi_pintile.png)

## <a name="format-the-table"></a>Taulukon muotoileminen
Taulukkoa voi muotoilla erittäin monella tapaa, käsittelemme niistä tässä vain muutamia. Voit oppia lisää muista muotoilutavoista avaamalla Muotoilu-ruudun (maalitelakuvake ![maalitela](media/power-bi-visualization-tables/power-bi-format.png)) ja tutkimalla.

* Kokeile taulukkoruudukon muotoilemista. Tässä olemme lisänneet sinisen pystyruudukon, lisänneet riveihin tilaa, paksuntaneet ääriviivaa ja kasvattaneet hieman tekstin kokoa.

    ![Ruudukkokortti](media/power-bi-visualization-tables/power-bi-table-gridnew.png)

    ![tulokset näyttävä taulukko](media/power-bi-visualization-tables/power-bi-table-grid3.png)
* Vaihdoimme sarakeotsikoiden taustaväriä, lisäsimme ääriviivan ja kasvatimme tekstin kokoa. 

    ![Sarakkeiden otsikkokortti](media/power-bi-visualization-tables/power-bi-table-column-headers.png)

    ![otsikoiden muotoilu taulukossa](media/power-bi-visualization-tables/power-bi-table-column2.png)

* Voit myös käyttää muotoilua yksittäisissä sarakkeissa ja sarakeotsikoissa. Aloita laajentamalla **Kentän muotoilu** ja valitsemalla muotoiltava sarake avattavasta luettelosta. Kentän muotoilun avulla voit tehdä esimerkiksi seuraavia määrityksiä sarakearvojen mukaan: näyttöyksiköt, fontin väri, desimaalipaikkojen määrä, tausta, tasaus ja paljon muuta. Kun olet säätänyt asetukset, valitse, otetaanko ne käyttöön myös otsikossa ja summariveissä.

    ![Tämän vuoden myynti -kentän muotoilu](media/power-bi-visualization-tables/power-bi-field-formatting.png)

* Hieman lisämuokkausta ja tässä on lopullinen taulukkomme. Koska muotoiluvaihtoehtoja on niin paljon, paras tapa oppia on aloittaa tavallisesta taulukosta, avata Muotoilu-ruutu ![](media/power-bi-visualization-tables/power-bi-format.png) ja aloittaa tutustuminen. 

    ![taulukko, joka sisältää kaikki tähän asti käytetyt muotoilut](media/power-bi-visualization-tables/power-bi-table-format.png)

### <a name="conditional-formatting"></a>Ehdollinen muotoilu
Yhdestä muotoilutyypistä käytetään nimitystä *ehdollinen muotoilu* ja sitä käytetään **arvojen** kenttiin Power BI -palvelun tai Desktopin **Visualisointi**-ruudussa. 

Taulukoiden ehdollisen muotoilun avulla voit määrittää mukautettuja solujen taustavärejä ja tekstin värejä solujen arvoihin perustuen. Voit käyttää myös liukuvärejä. 

1. Valitse alaspäin osoittava nuori Power BI -palvelun tai Desktopin **Visualisoinnit**-ruudussa sen **Arvon** vierestä, jota haluat muotoilla (tai napsauta kenttää hiiren kakkospainikkeella). Voit hallita kenttien ehdollista muotoilua ainoastaan **Kenttien** **Arvot**-alueella.

    ![polku Taustaväriasteikkoihin](media/power-bi-visualization-tables/power-bi-conditional-formatting-background.png)
2. Valitse **Taustaväriasteikot**. Voit valita avautuvassa valintaikkunassa värin sekä *Vähimmäis-* ja *Enimmäis*-arvot. Jos valitset **Erkautuva**-valinnan, voit määritellä myös valinnaisen *Keski*arvon.

    ![Taustaväriasteikot-ikkuna](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)

    Käytetäänpä räätälöityä muotoilua Keskimääräisen nimikehintamme arvoihin. Valitse **Erkautuva**, lisää vähän väriä ja paina **OK**. 

    ![erkautuvia värejä esittävä taulukko](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
3. Lisää taulukkoon uusi kenttä, jossa on sekä positiivisia että negatiivisia arvoja.  Valitse **Myynti > Myyntivariaatio yhteensä**. 

    ![oikeassa reunassa näkyvä uusi kenttä](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)
4. Valitse tietopalkin ehdollinen muotoilu painamalla **Myyntivariaatio yhteensä** -kohdan vieressä olevaa alaspäin osoittavaa nuolta ja valitsemalla **Ehdollinen muotoilu > Tietopalkit**.

    ![Tietopalkkien valintapolku](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars.png)
5. Määritä avautuvassa valintaikkunassa värit **positiiviselle palkille**, **negatiiviselle palkille**, lisää valinta kohtaan **Näytä vain palkki** ja tehdä muita haluamiasi muutoksia.

    ![Näytä vain palkki -valintamerkki](media/power-bi-visualization-tables/power-bi-data-bars.png)

    Kun valitset **OK**, tietopalkit korvaavat taulukon numeroarvot, mikä tekee siitä helpommin luettavan.

    ![sama taulukko, jossa viimeiseen sarakkeeseen on lisätty palkit](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)
6. Jos haluat poistaa ehdollisen muotoilun visualisoinnista, napsauta vain kenttää uudelleen hiiren kakkospainikkeella ja valitse **Poista ehdollinen muotoilu**.

> [!TIP]
> Ehdollinen muotoilu on käytettävissä myös Muotoilu-ruudusta (maalirullakuvake). Valitse muokattava arvo ja aseta sitten **Väriasteikko**- tai **Tietopalkki**-arvoksi **Käytössä**, jolloin käytetään oletusasetuksia. Jos haluat mukauttaa asetuksia, valitse **Lisäasetukset**.
> 
## <a name="copy-values-from-power-bi-tables-for-use-in-other-applications"></a>Arvojen kopiointi Power BI -taulukoista muissa sovelluksissa käytettäviksi

Matriisissa tai taulukossa voi olla sisältöä, jota haluat käyttää muissa sovelluksissa, kuten Dynamics CRM:ssä, Excelissä tai jopa muissa Power BI -raporteissa. Power BI:ssä voit hiiren kakkospainikkeella kopioida solun tai valikoiman soluja leikepöydälle ja liittää toiseen sovellukseen.


* Kopioi yksittäisen solun arvo valitsemalla solu, napsauttamalla hiiren kakkospainiketta ja valitsemalla **Kopioi arvo**. Solun muotoilematon arvo on nyt leikepöydällä, josta voit liittää sen toiseen sovellukseen.

    ![Kopiointivalinnat](media/power-bi-visualization-tables/power-bi-copy-value.png)

* Jos haluat kopioida useita soluja, valitse solualue tai useita soluja yhdessä Ctrl-näppäimen kanssa. Kopio sisältää sarakkeiden ja rivien otsikot.

    ![Kopiointivalinnat](media/power-bi-visualization-tables/power-bi-copy-selection.png)

    Kopio sisältää sarakkeiden ja rivien otsikot.

    ![Liitä Exceliin](media/power-bi-visualization-tables/power-bi-paste-selection.png)

## <a name="adjust-the-column-width-of-a-table"></a>Taulukon sarakeleveyden muuttaminen
Joskus Power BI katkaisee raportin tai näkymän sarakeotsikon. Nähdäksesi sarakkeen koko nimen, pidä hiirtä otsikon oikealla puolella nähdäksesi kaksoisnuolet, valitse ja vedä.

![videolähennys sarakkeen koon muuttamisesta](media/power-bi-visualization-tables/resizetable.gif)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
* Sovellettaessa sarakemuotoilua voit valita vain yhden tasausvaihtoehdon saraketta kohti: automaattinen, vasen, keskitetty, oikea. Yleensä sarake sisältää vain tekstiä tai numeroita eikä niiden yhdistelmiä. Jos sarake sisältää sekä numeroita että tekstiä, **Automaattinen** tasaa tekstin vasemmalle ja numerot oikealle. Tämä tukee kieliä, joita luetaan vasemmalta oikealle.   

## <a name="next-steps"></a>Seuraavat vaiheet

[Puukartat Power BI:ssä](power-bi-visualization-treemaps.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)