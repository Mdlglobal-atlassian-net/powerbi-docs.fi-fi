---
title: Matriisivisualisoinnin käyttö Power BI:ssä
description: Lue, miten voit matriisivisualisoinnin avulla ottaa käyttöön porrastettuja asetteluja ja eriytetyn korostuksen Power BI:ssä.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/25/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 150de174b15e684c49c38f67767b13a3a7f9a36a
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/09/2020
ms.locfileid: "75758964"
---
# <a name="create-matrix-visualizations-in-power-bi"></a>Matriisivisualisoinnin luominen Power BI:ssä

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Matriisivisualisointi muistuttaa taulukkoa.  Taulukko tukee kahta dimensiota ja tiedot ovat pelkistettyjä eli näet arvojen kaksoiskappaleet koostettujen arvojen sijasta. Matriisin ansiosta tiedot on helpompi näyttää mielekkäästi eri dimensioissa – se tukee porrastettua asettelua. Matriisi koostaa tiedot automaattisesti ja mahdollistaa porautumisen alaspäin. 

Voit luoda matriisivisualisointeja **Power BI Desktop** -raporteissa sekä korostaa matriisin sisältämiä elementtejä ristiin tämän raporttisivun muiden visualisointien kanssa. Voit esimerkiksi valita rivejä, sarakkeita ja jopa yksittäisiä soluja sekä ristiinkorostuksen. Voit myös kopioida yksittäisiä ja useita soluosioita sekä liittää niitä muihin sovelluksiin. 

![ristiinkorostettu matriisi ja rengaskaavio](media/desktop-matrix-visual/matrix-visual_2a.png)

Matriiseilla on monia ominaisuuksia, jotka käydään läpi tämän artikkelin seuraavissa osioissa.


## <a name="understanding-how-power-bi-calculates-totals"></a>Miten Power BI laskee kokonaissummat

Ennen kuin siirrymme matriisivisualisoinnin käytön ohjeisiin, on tärkeää ymmärtää, miten Power BI laskee kokonais- ja välisumma-arvot taulukoissa ja matriiseissa. Power Bi arvioi kokonais- ja välisummariveille mittaria pohjana olevien tietojen kaikista riveistä. Se ei koostu ainoastaan näkyvien tai näytettyjen rivien arvoista. Kokonaissummarivin arvo saattaa siis poiketa odotuksistasi.

Katso seuraavia matriisivisualisointeja. 

![vertaa taulukkoa ja matriisia](media/desktop-matrix-visual/matrix-visual_3.png)

Tässä esimerkissä oikeanpuoleisimman matriisivisualisoinnin jokainen rivi näyttää kunkin myyjä-/päivämääräyhdistelmän *summan*. Koska myyjä kuitenkin näkyy usean päivän kohdalla, samat numerot saattavat toistua. Tämän vuoksi pohjalla olevista tiedoista muodostettu tarkka kokonaissumma ei vastaa näkyvien tietojen yksinkertaista yhteenlaskua. Tämä on yleistä tapauksissa, joissa arvo lasketaan yhteen useiden muiden arvojen kanssa.

Kun tarkastelet kokonais- ja välisummia, muista, että nämä arvot perustuvat pohjana oleviin tietoihin. Ne eivät perustu pelkästään näkyvissä oleviin arvoihin.

<!-- use Nov blog post video

## Expanding and collapsing row headers
There are two ways you can expand row headers. The first is through the right-click menu. You’ll see options to expand the specific row header you clicked on, the entire level or everything down to the very last level of the hierarchy. You have similar options for collapsing row headers as well.

![](media/desktop-matrix-visual/power-bi-expand1.png)

You can also add +/- buttons to the row headers through the formatting pane under the row headers card. By default, the icons will match the formatting of the row header, but you can customize the icons’ color and size separately if you want. 
Once the icons are turned on, they work similarly to the icons from PivotTables in Excel.

![](media/desktop-matrix-visual/power-bi-expand2.png)

The expansion state of the matrix will save with your report. It can be pinned to dashboards as well, but consumers will need to open up the report to change the state. Conditional formatting will only apply to the inner most visible level of the hierarchy. Note that this expand/collapse experience is not currently supported when connecting to AS servers older than 2016 or MD servers.

![](media/desktop-matrix-visual/power-bi-expand3.png)

Watch the following video to learn more about expand/collapse in the matrix:

-->
## <a name="using-drill-down-with-the-matrix-visual"></a>Alaspäin porautumisen käyttö matriisivisualisoinnin kanssa
Matriisivisualisoinnilla voit tehdä erilaisia alaspäin porautumisen toimintoja, jotka eivät ennen olleet käytettävissä. Voit porata rivejä, sarakkeita ja jopa yksittäisiä osioita ja soluja. Niiden toiminta on kuvattu alla.

### <a name="drill-down-on-row-headers"></a>Rivien otsikoiden poraaminen

Kun lisäät useita kenttiä Visualisoinnit-ruudun **Kentät**-säilössä olevaan **Rivit**-osioon, otat käyttöön matriisivisualisoinnin rivien porauksen alaspäin. Tämä muistuttaa hierarkian luomista, jonka avulla voit porata (ja varmuuskopioida) tiedot kyseisen hierarkian mukaisessa järjestyksessä ja analysoida ne jokaisella tasolla.

Seuraavassa kuvassa **Rivit**-osio sisältää *Myyntivaiheen* ja *Mahdollisuuden koon*, mikä luo ryhmittelyn (tai hierarkian) porattaville riveille, joita voimme porata.

![Suodattimien kortti näyttää valittavat rivit](media/desktop-matrix-visual/power-bi-rows-matrix.png)

Kun visualisointiin luodaan ryhmittely **Rivit**-osioon, itse visualisoinnissa näytetään *porautuminen*- ja *laajenna*-kuvakkeet vasemmassa yläkulmassa.

![matriisi, jossa porautumisen ohjausobjektit on korostettu](media/desktop-matrix-visual/power-bi-matrix-drilldown.png)

Kuten muidenkin visualisointien poraus- ja laajennustoiminnoissa, näiden painikkeiden valitseminen mahdollistaa poraamisen hierarkian mukaisesti ylös- tai alaspäin. Tässä tapauksessa voit porata *Myyntivaiheesta* *Mahdollisuuden kokoon* seuraavan kuvan mukaisesti. Siinä on valittu Poraus alaspäin yksi taso -kuvake (talikko).

![matriisi, jossa on korostettu talikko](media/desktop-matrix-visual/power-bi-matrix-drill3.png)

Näiden kuvakkeiden käyttämisen lisäksi voit valita minkä tahansa näistä rivin otsikoista ja porata alaspäin valitsemalla toiminnon näyttöön tulevasta valikosta.

![valikon vaihtoehdot matriisin riveille](media/desktop-matrix-visual/power-bi-matrix-menu.png)

Huomaa, että valikossa on muutamia vaihtoehtoja, jotka tuottavat erilaisia tuloksia:

Jos valitset **Poraudu alaspäin**, matriisi laajennetaan *kyseisen* rivin tasolla, *lukuun ottamatta* kaikkia muita riviotsikoita paitsi valittua riviotsikkoa. Seuraavassa kuvassa on valittu **Ehdotus** > **Poraudu alaspäin**. Huomaa, että muita ylimmän tason rivejä ei enää näytetä matriisissa. Tämä porautumistapa on hyödyllinen toiminto ja erityisen kätevä, kun käsittelemme ristiinkorostusta.

![matriisi, jossa on porattu alaspäin yksi taso](media/desktop-matrix-visual/power-bi-drill-down-matrix.png)

Voit palata edelliseen ylimmän tason näkymään valitsemalla **Poraudu ylöspäin** -kuvakkeen. Jos valitset sitten **Ehdotus** > **Näytä seuraava taso**, saat laskeutuvan luettelon kaikista seuraavan tason kohteista (tässä tapauksessa *Mahdollisuuden koko* -kentästä) ilman ylemmän tason hierarkian luokittelua.

![matriisi, joka näyttää seuraavan tason](media/desktop-matrix-visual/power-bi-next-level-matrix.png)

Valitse **Poraa ylöspäin** -kuvake vasemmasta yläkulmasta, jotta matriisi näyttää kaikki ylimmän tason luokat. Valitse sitten **Ehdotus** > **Laajenna seuraavalle tasolle**, jotta näet kaikki arvot hierarkian kummallakin tasolla - *Myyntivaihe* ja *Mahdollisuuden koko*.

![matriisi, jossa on käytössä Laajenna seuraava taso](media/desktop-matrix-visual/power-bi-matrix-expand-next.png)

Voit myös käyttää **Laajenna**-valikkokohdetta hallitsemaan näyttöä tarkemmin.  Valitse esimerkiksi **Ehdotus** > **Laajenna** > **Valinta**. Power BI näyttää yhden kokonaissummarivin kullekin *myyntivaiheelle* ja *Mahdollisuuden koko*-asetukset *ehdotukselle*.

![Matriisi, kun Laajenna-komentoa on sovellettu ehdotukseen](media/desktop-matrix-visual/power-bi-matrix-expand.png)

### <a name="drill-down-on-column-headers"></a>Sarakkeiden otsikoiden poraaminen
Voit porata sarakkeita alaspäin samoin kuin rivejä. Seuraavassa kuvassa näet, että **Sarakkeet**-kentän säilössä on kaksi kenttää, jotka luovat hierarkian samalla tavalla kuin rivien kanssa aiemmin tässä artikkelissa. **Sarakkeet**-kentässä on *Alue* ja *Segmentti*. Heti, kun toinen kenttä on lisätty **Sarakkeet**-kenttään, visualisoinnissa näytetään uusi avattava valikko, jossa on nyt **Rivit**.

![Matriisi, kun toisen sarakkeen arvo on lisätty](media/desktop-matrix-visual/power-bi-matrix-row.png)

Jos haluat porautua alaspäin sarakkeisiin, valitse **Sarakkeet** kohta *Poraudu*-valikosta, joka on matriisin vasemmassa yläkulmassa. Valitse *Itä*-alue ja valitse **Poraudu alaspäin**.

![valikkoa porautumiselle alaspäin sarakkeisiin](media/desktop-matrix-visual/power-bi-matrix-column.png)

Kun valitset **Poraudu alaspäin**, näkyviin tulee sarakehierarkian seuraava taso *Alue > Itä* -kohdalle, joka on tässä tapauksessa *Mahdollisuuden lukumäärä*. Toinen alue on piilotettu.

![matriisi, jossa saraketta on porattu alaspäin yksi taso](media/desktop-matrix-visual/power-bi-matrix-column-drill.png)

Valikon muut kohteet toimivat sarakkeilla samoin kuin riveillä (katso edellinen osio, **Riviotsikoiden poraus alaspäin**). Voit **Näyttää seuraavan tason**, **Laajentaa seuraavalle tasolle** sarakkeita samoin kuin rivejä.

> [!NOTE]
> Matriisivisualisoinnin vasemmassa yläkulmassa olevat ylös ja alas poraamisen kuvakkeet koskevat vain rivejä. Sarakkeiden alaspäin poraaminen edellyttää hiiren kakkospainikkeen valikon käyttöä.

## <a name="stepped-layout-with-matrix-visuals"></a>Porrastettu asettelu matriisivisualisoinneissa

Matriisivisualisointi sisentää hierarkian alaluokat automaattisesti kunkin ylätason alle. Tätä kutsutaan porrastetuksi asetteluksi.

Alkuperäisessä matriisivisualisoinnin versiossa aliluokat näytettiin täysin eri sarakkeella, mikä vei visualisoinnista paljon tilaa. Seuraavassa kuvassa taulukko näytetään alkuperäisessä matriisivisualisoinnissa. Huomaa, että aliluokat ovat erillisessä sarakkeessa.

![Näyttökuva vanhasta matriisivisualisoinnista, joka näyttää aliluokat erillisessä sarakkeessa.](media/desktop-matrix-visual/matrix-visual_14.png)

Seuraavassa kuvassa näytetään matriisivisualisointi porrastetulla asettelulla. Huomaa, että *Tietokoneet*-luokan aliluokat (tietokoneiden oheislaitteet, pöytätietokoneet, kannettavat tietokoneet, näytöt ja niin edelleen) on hieman sisennetty, mikä tekee visualisoinnista siistin ja tiiviin.

![nykyinen tapa, jolla matriisi muotoilee tietoja](media/desktop-matrix-visual/matrix-visual_13.png)

Voit helposti säätää porrastetun asettelun asetuksia. Kun matriisivisualisointi on valittu, siirry **Muotoilu**-osioon (telakuvake) **Visualisoinnit**-ruudulla ja laajenna rivien otsikko-osio. Asetuksia on kaksi: porrastetun asettelun kytkin (käytössä / pois käytöstä) ja Porrastetun asettelun sisennys (määrittää sisennyksen kuvapisteinä).

![Riviotsikot-kortti, joka näyttää porrastetun asettelun ohjausobjektin](media/desktop-matrix-visual/power-bi-stepped-matrix.png)

Jos poistat porrastetun asettelun käytöstä, Power BI näyttää aliluokat toisessa sarakkeessa sen sijaan, että ne sisennettäisiin ylätason luokan alle.

## <a name="subtotals-with-matrix-visuals"></a>Välisummat matriisivisualisoinneissa

Voit ottaa sekä rivien että sarakkeiden välisummat käyttöön ja poistaa ne käytöstä matriisivisualisoinneissa. Seuraavassa kuvassa näet, että rivien välisumma-asetus on **käytössä**.

![matriisi, joka näyttää kokonais- ja välisummat](media/desktop-matrix-visual/matrix-visual_20.png)

Siirry Muotoilu-osioon Visualisoinnit-ruudulla, laajenna **Välisummat**-kortti ja aseta Rivien välisummat -liukusäädin **Pois käytöstä** -asentoon. Kun teet näin, välisummat eivät näy.

![matriisi, jossa välisummat on poistettu käytöstä](media/desktop-matrix-visual/matrix-visual_21.png)

Voit tehdä saman sarakkeiden välisummille.

## <a name="cross-highlighting-with-matrix-visuals"></a>Ristiinkorostus matriisivisualisoinneissa

Matriisivisualisoinneissa matriisin elementtejä voidaan valita ristiinkorostuksen perustaksi. Valitse matriisin sarake, ja Power BI korostaa sarakkeen, kuten muutkin raporttisivun visualisoinnit. Tämä ristiinkorostuksen tyyppi on muiden visualisointien ja arvopisteen valinnan yleinen ominaisuus, joka on nyt laajennettu matriisivisualisointeihin.

Myös Ctrl + napsautus -valinta toimii ristiinkorostuksessa. Esimerkiksi seuraavassa kuvassa matriisivisualisoinnista valittiin kokoelma aliluokkia. Huomaa, miten visualisoinnin valitsemattomat nimikkeet näkyvät harmaina ja miten sivun muut visualisoinnit kuvastavat matriisivisualisoinnissa tehtyjä valintoja.

![Näyttökuva matriisivisualisoinnista ja kahdesta muusta visualisoinnista ristiinkorostuksen Ctrl + napsautus -toiminnon esittelemiseksi.](media/desktop-matrix-visual/matrix-visual_16.png)

## <a name="copying-values-from-power-bi-for-use-in-other-applications"></a>Arvojen kopiointi Power BI:stä muissa sovelluksissa käytettäviksi

Matriisissa tai taulukossa saattaa olla sisältöä, jota haluat käyttää muissa sovelluksissa: Dynamics CRM:ssä, Excelissä ja muissa Power BI -raporteissa. Power BI:n avulla voit hiiren kakkospainikkeella kopioida solun tai valikoiman soluja leikepöydälle ja liittää ne sitten toiseen sovellukseen.


* Kopioi yksittäisen solun arvo valitsemalla solu, napsauttamalla hiiren kakkospainiketta ja valitsemalla **Kopioi arvo**. Solun muotoilematon arvo on nyt leikepöydällä, josta voit liittää sen toiseen sovellukseen.

    ![Näyttökuva matriisivisualisoinnista, jossa nuoli osoittaa arvoon ja jossa hiiren kakkospainikkeen valikkoa on laajennettu kattamaan korostetut Kopioi arvo- ja Kopioi valinta -vaihtoehdot.](media/desktop-matrix-visual/power-bi-cell-copy.png)



* Jos haluat kopioida useita soluja, valitse solualue tai useita soluja yhdessä Ctrl-näppäimen kanssa. 

    ![Näyttökuva matriisivisualisoinnista, jossa nuoli osoittaa arvoon ja jossa hiiren kakkospainikkeen valikkoa on laajennettu kattamaan Kopioi-arvo ja korostetut Kopioi valinta -vaihtoehdot.](media/desktop-matrix-visual/power-bi-copy.png)

* Kopio sisältää sarakkeiden ja rivien otsikot.

    ![Näyttökuva Excel-riveistä ja -sarakkeista, joihin on liitetty arvot.](media/desktop-matrix-visual/power-bi-copy-selection.png)

* Jos haluat tehdä kopion itse visualisoinnista ja sisällyttää vain valitsemasi solut, valitse vähintään yksi solu CTRL-näppäimen avulla, napsauta hiiren kakkospainiketta ja valitse **Kopioi visualisointi**

    ![Kuvakaappaus, joka näyttää visualisoinnin kopiointitoiminnon](media/desktop-matrix-visual/power-bi-copy-visual.png)

* Kopio on toinen matriisivisualisointi, mutta se sisältää vain kopioidut tiedot.

    ![Kuvakaappaus, joka näyttää esimerkin visualisoinnin kopioinnista](media/desktop-matrix-visual/power-bi-copy-visual-example.png)

## <a name="shading-and-font-colors-with-matrix-visuals"></a>Sävytys ja fontin väri matriisivisualisoinneissa
Matriisivisualisoinnin avulla voit käyttää ehdollista muotoilua (värit, sävytys ja tietopalkit) matriisin solujen taustavärinä, ja voit käyttää ehdollista muotoilua myös itse tekstiin ja arvoihin.

Voit käyttää ehdollista muotoilua valitsemalla matriisivisualisoinnin ja avaamalla **Muotoile**-ruudun. Voit vaihtoehtoisesti siirtyä **Ehdollinen muotoilu** -korttiin ja määrittää **taustavärin** **fontin värin** tai **tietopalkit** asettamalla liukusäätimen **Käytössä**-asentoon. Ottamalla käyttöön jonkin näistä vaihtoehdoista näet *Lisäasetukset*-linkin, jonka avulla voit mukauttaa värejä ja värin muotoilun arvoja.
  
  ![Muotoilu-ruutu, joka näyttää tietopalkkien hallinnan](media/desktop-matrix-visual/power-bi-matrix-data-bars.png)

Valitsemalla *Lisäasetukset* näet valintaikkunan, jonka avulla voit tehdä mukautuksia. Tässä esimerkissä näytetään valintaikkuna **Tietopalkit**-kohteelle.

![Tietopalkit-ruutu](media/desktop-matrix-visual/power-bi-data-bars.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Piste- ja kuplakaaviot Power BI:ssä](power-bi-visualization-scatter.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)