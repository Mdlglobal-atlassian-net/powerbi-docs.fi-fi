---
title: 'Raporttieditori: esittely'
description: 'Raporttieditori: esittely'
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/11/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 3c6ae5351908bd71888040c3bc900323837935c2
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/21/2018
ms.locfileid: "46546069"
---
# <a name="the-report-editortake-a-tour"></a>Raporttieditori: esittely
## <a name="editing-reports-in-power-bi-service-and-power-bi-desktop"></a>Raporttien muokkaus Power BI -palvelussa ja Power BI Desktopissa
Power BI -palvelun raporttieditori ja Power BI Desktopin raporttieditori ovat hyvin samankaltaisia. Videossa näytetään Power BI Desktopin raporttieditori ja tässä artikkelissa näytetään Power BI -palvelun raporttieditori. 

## <a name="the-difference-between-report-creators-and-report-consumers"></a>Raportin *laatijoiden* ja raportin *käyttäjien* välinen ero
Vain raportin omistajat (eli raportin *laatijat*) voivat laatia ja muokata raportteja. Jos *käytät* raporttia, joka on jaettu kanssasi, voit yhä avata raportin ja käsitellä sitä Power BI -palvelussa [vain lukunäkymässä](consumer/end-user-reading-view.md). Et voi kuitenkaan hyötyä kaikista niistä tehokkaista ja laajoista ominaisuuksista, jotka ovat saatavilla raportin laatijalle.  

Löydät lisätietoja raportin lukunäkymästä artikkelista [Power BI -palvelun luku- ja muokkausnäkymä](consumer/end-user-reading-view.md). 

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

Power BI-palvelussa *raporttieditori* on saatavilla vain [muokkausnäkymässä](consumer/end-user-reading-view.md). Jotta voit avata raportin muokkausnäkymässä, sinun on oltava raportin omistaja tai laatija.

Power BI -raporttieditorissa on kolme osaa:  

1. **Kentät**-, **Visualisoinnit**- ja **Suodattimet**-ruudut.
2. yläosan siirtymispalkit    
3. raportin piirtoalusta     

![](media/service-the-report-editor-take-a-tour/power-bi-report-canvas.png)

## <a name="1-the-report-editor-panes"></a>1. Raporttieditorin ruudut
![Power BI -raporttieditori](media/service-the-report-editor-take-a-tour/power-bi-report-panes.png)

Kun avaat raportin ensimmäistä kertaa, näet kolme ruutua: Visualisoinnit, Suodattimet ja Kentät. Vasemmanpuoleisten Visualisoinnit- ja Suodattimet-ruutujen avulla hallitaan visualisointien ulkoasua – tyyppiä, värejä, suodatusta ja muotoilua.  Oikeanpuoleisen Kentät-ruudun avulla hallitaan visualisoinneissa käytettäviä pohjatietoja. 

Raporttieditorissa näytetty sisältö vaihtelee raportin piirtoalustassa tehtyjen valintojen mukaan.  Kun esimerkiksi valitset yksittäisen visualisoinnin: 

|  |  |
| --- | --- |
| ![](media/service-the-report-editor-take-a-tour/power-bi-panes.png) |<ul><li>Visualisointi-ruudun yläosassa määritetään käytettävän visualisoinnin tyyppi eli tässä esimerkissä yhdistelmäpylväskaavio.<br><br></li> <li>Visualisointi-ruudun alaosassa (sinun on ehkä vieritettävä alaspäin) näytetään visualisoinnissa käytettävät kentät. Tässä kaaviossa käytetään Verokuukausi-, Aluepäällikkö- ja  Kokonaismyyntivaihtelu-kenttiä. <br><br></li><li>Suodattimet-ruudussa (sinun on ehkä vieritettävä alaspäin) näytetään kaikki sovelletut suodattimet. <br><br></li><li>Kentät-ruudussa luetteloidaan saatavilla olevat taulukot ja, jos laajennat taulukon nimeä, tämän taulukon perustana olevat kentät. Keltainen fontti kertoo, että visualisoinnissa käytetään vähintään yhtä tämän taulukon kenttää.<br><br></li><li>![maalirullakuvake](media/service-the-report-editor-take-a-tour/power-bi-paint-roller-icon.png) Voit näyttää valitun visualisoinnin muotoiluruudun valitsemalla maalirullakuvakkeen.<br><br></li><li>![suurennuslasikuvake](media/service-the-report-editor-take-a-tour/power-bi-magnifying-icon.png) Voit näyttää Analytiikka-ruudun valitsemalla suurennuslasikuvakkeen.</ul> |

## <a name="the-visualizations-pane-from-top-to-bottom"></a>Visualisoinnit-ruutu (ylhäältä alaspäin)
![Visualisointi-ruudun yläosa](media/service-the-report-editor-take-a-tour/selectviz.png)

Voit täällä valita visualisointityypin. Pieniä kuvia kutsutaan *malleiksi*. Yllä olevassa kuvassa on valittu yhdistelmäpalkkikaavio. Jos et valitse ensin visualisointityyppiä vaan alat sen sijaan luoda visualisointia valitsemalla kentät, Power BI poimii visualisointityypin puolestasi. Voit pitää Power BI:n valinnan tai vaihtaa tyyppiä valitsemalla eri mallin. Voit vaihtaa mallia niin monta kertaa kuin tarvitset, jotta löydät tietojasi parhaiten vastaavan visualisointityypin.

### <a name="manage-the-fields-used-in-your-visual"></a>Hallitse visualisoinnissa käytettäviä kenttiä.
![Visualisointi-ruudun keskiosa](media/service-the-report-editor-take-a-tour/power-bi-field-list.png)

Tässä ruudussa näytetyt säilöt (joita kutsutaan joskus *lähteiksi*) vaihtelevat valitsemasi visualisointityypin mukaan.  Jos valitsit esimerkiksi palkkikaavion, näet säilöt Arvot-, Akseli- ja Selite-kentille. Kun valitset kentän tai vedät sen piirtoalustalle, Power BI lisää tämän kentän yhteen säilöistä.  Voit myös vetää kentät Kentät-luettelosta suoraan säilöihin.  Jotkin säilöt on rajoitettu tietyntyyppisiin tietoihin.  Esimerkiksi **Arvot**-kenttään ei hyväksytä ei-numeerisia kenttiä. Jos siis vedät **Työntekijän nimi** -kentän **Arvot**-säilöön, Power BI muuttaa sen **Työntekijän nimen lukumäärä** -kentäksi.

### <a name="remove-a-field"></a>Kentän poistaminen
Voit poistaa kentän visualisoinnista valitsemalla **X** kentän nimen oikealta puolelta.

![Myymälätyypin poistaminen selitteestä](media/service-the-report-editor-take-a-tour/deletefield.png)

Katso lisätietoja artikkelista [Visualisointien lisääminen Power BI -raporttiin](visuals/power-bi-report-add-visualizations-i.md).

### <a name="format-your-visuals"></a>Visualisointien muotoileminen
Voit näyttää Muotoilu-ruudun valitsemalla maalirullakuvakkeen. Saatavilla oleva vaihtoehto riippuu valitun visualisoinnin tyypistä.

![Muotoilu-ruutu](media/service-the-report-editor-take-a-tour/power-bi-formatting.png)

Muotoilumahdollisuudet ovat lähes loputtomat.  Saat lisätietoja tutustumalla aiheeseen omatoimisesti tai lukemalla seuraavat artikkelit:

* [Visualisoinnin otsikon, taustan ja selitteen mukauttaminen](visuals/power-bi-visualization-customize-title-background-and-legend.md)
* [Värin muotoileminen](visuals/service-getting-started-with-color-formatting-and-axis-properties.md)
* [X-akselin ja Y-akselin ominaisuuksien mukauttaminen](visuals/power-bi-visualization-customize-x-axis-and-y-axis.md)

### <a name="add-analytics-to-your-visualizations"></a>Analytiikan lisääminen visualisointeihin
Voit näyttää Analytiikka-ruudun valitsemalla suurennuslasikuvakkeen. Saatavilla oleva vaihtoehto riippuu valitun visualisoinnin tyypistä.

![](media/service-the-report-editor-take-a-tour/power-bi-analytics.png)    
Power BI -palvelun Analytiikka-ruudussa voit lisätä dynaamisia viiteviivoja visualisointeihin ja määrittää kohdistuksen tärkeille trendeille tai merkityksellisille tiedoille. Lisätietoja on artikkelissa [Power BI -palvelun Analytiikka-ruutu](service-analytics-pane.md) tai [Power BI Desktopin Analytiikka-ruutu](desktop-analytics-pane.md).

- - -
## <a name="the-filters-pane"></a>Suodattimet-ruutu
Voit Suodattimet-ruudun avulla tarkastella, määrittää ja muokata raporttien pysyviä suodattimia sivun, raportin, porautumisen ja visualisoinnin tasolla. Kyllä, voit suodattaa myös tilapäisesti raportin sivuja ja visualisointeja valitsemalla visualisoinnin elementit tai käyttämällä osittajien kaltaisia työkaluja. Kun käytät Suodattimet-ruutua, suodattimien tila tallennetaan kuitenkin raportin kanssa. 

Suodattimet-ruudulla on myös toinen tehokas ominaisuus eli voit suodattaa käyttämällä kenttää ***, jota ei jo käytetä raportin yhdessä visualisoinnissa***. Selvitän tätä tarkemmin. Kun luot raportin sivun, Power BI lisää automaattisesti kaikki käyttämäsi kentät visualisointeihin Suodattimet-ruudun Visualisointi-tason suodatinalueella.  Jos haluat määrittää visualisoinnin, sivun, porauksen tai raportin suodattimen käyttämällä kenttää, jota ei tällä hetkellä käytetä visualisoinnissa, vedä se yhteen Suodattimet-säilöistä.   

![Suodattimet-ruutu](media/service-the-report-editor-take-a-tour/power-bi-formatting-pane.png)

Katso lisätietoja artikkelista [Suodattimen lisääminen raporttiin](power-bi-report-add-filter.md).

- - -
## <a name="the-fields-pane"></a>Kentät-ruutu
Kentät-ruudussa näytetään tiedoissasi olevat taulukot ja kentät, joiden avulla voit luoda visualisointeja.

|  |  |
| --- | --- |
| ![Kentät-ruutu](media/service-the-report-editor-take-a-tour/reportfields.png) |<ul><li>Voit aloittaa uuden visualisoinnin vetämällä kentän sivulle.  Voit myös vetää kentän aiemmin luotuun visualisointiin, jos haluat lisätä kentän tähän visualisointiin.<br><br></li> <li>Kun lisäät valintamerkin kentän viereen, Power BI lisää tämän kentän aktiiviseen (tai uuteen) visualisointiin. Se myös päättää, mihin säilöön tämä kenttä sijoitetaan.  Esimerkiksi pitäisikö käyttää Selite-, Akseli- vai Arvo-kenttää? Power BI tekee parhaan arvauksen, ja voit siirtää sen tästä säilöstä toiseen tarvittaessa. <br><br></li><li>Kummassakin tapauksessa kukin valittu kenttä lisätään Visualisoinnit-ruutuun raporttieditorissa.</li></ul> |

**HUOMAUTUS**: Jos käytät Power BI Desktopia, voit myös näyttää/piilottaa kentät, lisätä laskutoimituksia jne.

### <a name="what-do-the-field-icons-mean"></a>Mitä kentän kuvakkeet tarkoittavat?
* **∑ Koosteet** Kooste on numeerinen arvo, joka esimerkiksi ynnätään yhteen tai pyöristetään keskiarvoksi. Koosteita tuodaan yhdessä tietojen kanssa (määritetty tietomallissa, johon raportti perustuu).
  Katso lisätietoja artikkelista [Power BI -raporttien koosteet](service-aggregates.md).
* ![Laskimen kuvake](media/service-the-report-editor-take-a-tour/pbi_calculated_icon.png) **Lasketut mitat (kutsutaan myös lasketuiksi kentiksi)**  
   Jokaisella lasketulla kentällä on oma pysyväiskoodattu kaavansa. Et voi muuttaa laskutoimitusta. Jos se on  esimerkiksi summa, se voi olla vain summa. Saat lisätietoja artikkelista [Mittayksikköjen ymmärtäminen](desktop-measures.md).
* ![Yksilöllisen kentän kuvake](media/service-the-report-editor-take-a-tour/icon.png) **Yksilölliset kentät**  
   Tämän kuvakkeen kentät on tuotu Excelistä ja ne on määritetty näyttämään kaikki arvot, vaikka niillä olisi kaksoiskappaleita. Tiedoissa voi olla esimerkiksi kaksi tietuetta henkilölle nimeltä ”Matti Virtanen”, ja jokaista niistä käsitellään yksilöllisenä, eikä niitä lasketa yhteen.  
* **![Maantiedekuvake](media/service-the-report-editor-take-a-tour/pbi_geo_icon.png) Maantiede-kentät**  
   Voit sijainnin kenttien avulla luoda karttavisualisointeja. 
* **![Hierarkiakuvake](media/service-the-report-editor-take-a-tour/power-bi-hierarchy-icon.png) Hierarkia**  
   Valitse nuoli, jotta näet kentät, jotka muodostavat hierarkian. 

- - -
## <a name="2-the-top-navigation-bar"></a>2. Yläreunan siirtymispalkki
Yläreunan siirtymispalkissa on useita toimintoja, joita lisätään koko ajan. Saat lisätietoja tietystä toiminnosta Power BI -dokumentaation sisällysluettelosta tai hakuruudusta.

## <a name="3-the-report-canvas"></a>3. Raportin piirtoalusta
Työsi tulee näkyviin raportin piirtoalustalle. Kun luot visualisointeja Kentät-, Suodattimet- ja Visualisoinnit-ruutujen avulla, visualisoinnit näytetään raportin piirtoalustalla. Piirtoalustan alareunan jokainen välilehti edustaa raportin sivua. Avaa tämä sivu valitsemalla välilehti. 

## <a name="next-steps"></a>Seuraavat vaiheet:
[Raportin luominen](service-report-create-new.md)

Lue lisää raporteista artikkeleista [Power BI -palvelu](consumer/end-user-reports.md), [Power BI Desktop](desktop-report-view.md) ja [Power BI -mobiilisovellus](consumer/mobile/mobile-apps-view-phone-report.md).

[Power BI:n peruskäsitteet](consumer/end-user-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

