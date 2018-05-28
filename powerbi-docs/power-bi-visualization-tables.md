---
title: Opetusohjelma - Taulukkovisualisoinnit Power BI -raporteissa ja raporttinäkymissä (Opetusohjelma)
description: Opetusohjelma siitä, miten Power BI -raporttien ja raporttinäkymien taulukkovisualisointien kanssa työskennellään ja miten sarakkeiden leveyksiä muutetaan.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: ''
qualityfocus: ''
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/22/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: d41fd5085912ec74312fa4a4b25060cbd4afba94
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
---
# <a name="working-with-tables-in-power-bi-reports-and-dashboards-tutorial"></a>Taulukoiden käyttäminen Power BI -raporteissa ja raporttinäkymissä (Opetusohjelma)
Taulukko on ruudukko, joka sisältää tietoja järjestettynä loogiseen sarjaan rivejä ja sarakkeita. Se voi sisältää myös otsikkoja ja summarivin. Taulukot toimivat hyvin kvantitatiivisessa vertailussa, jossa tarkastellaan moni arvoja tietystä kategoriasta. Esimerkiksi tässä taulukossa näkyvät **luokan** viisi eri mittayksikköä.

![](media/power-bi-visualization-tables/table.png)

## <a name="when-to-use-a-table"></a>Milloin taulukkoa kannattaa käyttää?
Taulukko on hyvä vaihtoehto:

* yksityiskohtaisen tiedon ja tarkkojen arvojen selaamiseen ja vertailemiseen (visuaalisten esitysmuotojen sijaan).
* tietojen esittämiseen taulukkomuodossa.
* numeeristen tietojen luokiteltuun esittämiseen.   

> [!NOTE]
> Jos taulukossa on liikaa arvoja, harkitse sen muuntamista matriisiksi ja/tai alirakenteen käyttämistä.
> 
> 
## <a name="prerequisites"></a>Edellytykset
 - Power BI -palvelu tai Power BI Desktop
 - Jälleenmyyntianalyysimalli


## <a name="create-a-table"></a>Luo taulukko
Luomme yllä esitetyn taulukon, jossa esitetään myyntiarvot nimikeluokan mukaisesti. Seurataksesi kirjaudu Power BI -palveluun, valitse **Nouda tiedot \> Mallit \> Jälleenmyyntianalyysimalli > Yhdistä** ja valitse **Koontinäyttö. Visualisoinnin luominen edellyttää tietojoukon ja raportin muokkausoikeuksia. Kaikeksi onneksi Power BI -mallit ovat kaikki muokattavissa. Jos raportti on jaettu kanssasi, et pysty luomaan visualisointeja raporteissa.

1. Valitse vasemmasta siirtymisruudusta **Työtilat > Oma työtila**.    
2. Valitse Tietojoukot-välilehti ja vieritä alas juuri lisäämäsi Jälleenmyyntianalyysimallin tietojoukkoon.  Valitse **Raportin luominen** -kuvake.
   
    ![](media/power-bi-visualization-tables/power-bi-create-report.png)
2. Valitse raporttieditorissa **Nimike** > **luokka**.  Power BI luo automaattisesti taulukon, jossa luetellaan kaikki luokat.
   
    ![](media/power-bi-visualization-tables/power-bi-table1.png)
3. Valitse **Myynti > Keskimääräinen nimikehinta** ja **Myynti > Viime vuoden myynti** ja **Myynti > Tämän vuoden myynti** ja valitse kaikki kolme vaihtoehtoa (Arvo, Tavoite ja Tila).   
4. Etsi Visualisoinnit-ruudussa **Arvot** ja vedä ja pudota niitä, kunnes kaavion sarakkeiden järjestys vastaa tämän sivun ensimmäistä kuvaa.  Arvojen tulee näyttää tältä.
   
    ![](media/power-bi-visualization-tables/power-bi-table2.png)
5. Kiinnitä taulukko koontinäytölle valitsemalla Kiinnitä-kuvake.  
   
     ![](media/power-bi-visualization-tables/pbi_pintile.png)

## <a name="format-the-table"></a>Taulukon muotoileminen
Taulukkoa voi muotoilla erittäin monella tapaa, ja käsittelemme niistä tässä vain muutamia. Hyvä tapa oppia lisää muista muotoilutavoista on avata Muotoilu-ruutu (maalirullakuvake ![](media/power-bi-visualization-tables/power-bi-format.png)) ja tutkia.

* Kokeile taulukkoruudukon muotoilemista. Tässä olemme lisänneet sinisen pystyruudukon, lisänneet riveihin tilaa, paksuntaneet ääriviivaa ja kasvattaneet hieman tekstin kokoa.
  
    ![](media/power-bi-visualization-tables/power-bi-table-grid2-new.png)
  
    ![](media/power-bi-visualization-tables/power-bi-table-grid3.png)
* Vaihdoimme sarakeotsikoiden taustaväriä, lisäsimme ääriviivan ja kasvatimme tekstin kokoa. 
  
    ![](media/power-bi-visualization-tables/power-bi-table-column.png)
  
    ![](media/power-bi-visualization-tables/power-bi-table-column2.png)
* Hieman lisämuokkausta ja tässä on lopullinen taulukkomme. Koska muotoiluvaihtoehtoja on niin paljon, paras tapa oppia on aloittaa tavallisesta taulukosta, avata Muotoilu-ruutu ![](media/power-bi-visualization-tables/power-bi-format.png)  ja aloittaa tutustuminen. 
  
    ![](media/power-bi-visualization-tables/power-bi-table-format.png)

### <a name="conditional-formatting"></a>Ehdollinen muotoilu
Yhdestä muotoilutyypistä käytetään nimitystä *ehdollinen muotoilu* ja sitä käytetään **arvojen** kenttiin Power BI -palvelun tai Desktopin **Visualisointi**-ruudussa. 

Taulukoiden ehdollisen muotoilun avulla voit määrittää mukautettuja solujen taustavärejä ja tekstin värejä solujen arvoihin perustuen. Voit käyttää myös liukuvärejä. 

1. Valitse alaspäin osoittava nuori Power BI -palvelun tai Desktopin **Visualisoinnit**-ruudussa sen **Arvon** vierestä, jota haluat muotoilla (tai napsauta kenttää hiiren kakkospainikkeella). Voit hallita kenttien ehdollista muotoilua ainoastaan **Kenttien** **Arvot**-alueella.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-background.png)
2. Valitse **Taustaväriasteikot**. Voit valita avautuvassa valintaikkunassa värin sekä *Vähimmäis-* ja *Enimmäis*-arvot. Jos valitset **Erkautuva**-valinnan, voit määritellä myös valinnaisen *Keski*arvon.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)
   
    Käytetäänpä räätälöityä muotoilua Keskimääräisen nimikehintamme arvoihin. Valitse **Erkautuva**, lisää vähän väriä ja paina **OK**. 
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
3. Lisää taulukkoon uusi kenttä, jossa on sekä positiivisia että negatiivisia arvoja.  Valitse **Myynti > Myyntivariaatio yhteensä**. 
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)
4. Valitse tietopalkin ehdollinen muotoilu painamalla **Myyntivariaatio yhteensä** -kohdan vieressä olevaa alaspäin osoittavaa nuolta ja valitsemalla **Ehdollinen muotoilu > Tietopalkit**.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars.png)
5. Määritä avautuvassa valintaikkunassa värit **positiiviselle palkille**, **negatiiviselle palkille**, lisää valinta kohtaan **Näytä vain palkki** ja tehdä muita haluamiasi muutoksia.
   
    ![](media/power-bi-visualization-tables/power-bi-data-bars.png)
   
    Kun valitset **OK**, tietopalkit korvaavat taulukon numeroarvot, mikä tekee siitä helpommin luettavan.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)
6. Jos haluat poistaa ehdollisen muotoilun visualisoinnista, napsauta vain kenttää uudelleen hiiren kakkospainikkeella ja valitse **Poista ehdollinen muotoilu**.

> [!TIP]
> Ehdollinen muotoilu on käytettävissä myös Muotoilu-ruudusta (maalirullakuvake). Valitse muokattava arvo ja määrittele sitten **Väriasteikko** tai **Tietopalkki**, johon oletusasetuksia sovelletaan, tai **Lisäasetukset** räätälöidäksesi asetuksia.
> 
> 

## <a name="adjust-the-column-width-of-a-table"></a>Taulukon sarakeleveyden muuttaminen
Joskus Power BI katkaisee raportin tai näkymän sarakeotsikon. Nähdäksesi sarakkeen koko nimen, pidä hiirtä otsikon oikealla puolella nähdäksesi kaksoisnuolet, valitse ja vedä.

![](media/power-bi-visualization-tables/resizetable.gif)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

