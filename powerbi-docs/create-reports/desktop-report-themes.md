---
title: Raporttiteemojen käyttäminen Power BI Desktopissa
description: Lue ohjeet mukautetun värivalikoiman käyttöön ja sen käyttöön kokonaisessa raportissa Power BI Desktopissa.
author: davidiseminger
ms.reviewer: ''
ms.custom: contperfq4
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/16/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1f29d59d3b10f8dc963d8ba1965638bc01bae0c8
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83335691"
---
# <a name="use-report-themes-in-power-bi-desktop"></a>Raporttiteemojen käyttäminen Power BI Desktopissa

Power BI Desktopin *raporttiteemojen* avulla voit soveltaa rakennemuutoksia koko raporttiin, esimerkiksi käyttää yrityksen värejä, muuttaa kuvakejoukkoja tai ottaa käyttöön visualisointien uuden oletusarvoisen muotoilun. Kun otat käyttöön raporttiteeman, kaikissa raporttisi visualisoinneissa käytetään valitun teeman oletusvärejä ja -muotoilua. Muutamia poikkeuksia on, ja ne kuvataan jäljempänä tässä artikkelissa.

![Raporttiteemat](media/desktop-report-themes/report-themes-1a.png)

Raporttiteemoja on kahdenlaisia – valmiita raporttiteemoja ja mukautettuja raporttiteematiedostoja:

- Valmiissa raporttiteemoissa on erilaisia esimääritettyjä värimalleja, jotka asennetaan Power BI Desktopin kanssa. Voit valita valmiita raporttiteemoja suoraan Power BI Desktopin valikosta.

- Mukautetut raporttiteematiedostot ovat raporttiteemoja, jotka luodaan niiden perusrakenteen määrittävissä JSON-tiedostoissa. Voit ottaa mukautetun raporttiteeman käyttöön tuomalla sen JSON-tiedoston Power BI Desktopiin ja ottamalla sen käyttöön raportissasi.

  Voit myös mukauttaa aiemmin luodun raporttiteeman Power BI Desktopin sisältä käsin käyttämällä [**Mukauta teemaa** -valintaikkunaa](#create-and-customize-a-theme-in-power-bi-desktop).

Voit mukauttaa ja yhdenmukaistaa lähes kaikki **Visualisoinnit**-ruudun **Muotoile**-osiossa olevat elementit joko tekemällä mukauttamisen suoraan Power BI Desktopista tai vaihtoehtoisesti raporttiteeman JSON-tiedoston kautta. Tavoitteena on antaa käyttäjille täydet mahdollisuudet hallita omien raporttiensa oletusulkoasua yksityiskohtaisesti.

## <a name="how-report-themes-work"></a>Raporttiteemojen toiminta

Jos haluat käyttää raporttiteemaa Power BI Desktop -raportissa, voit valita jonkin [käytettävissä olevista valmiista raporttiteemoista](#built-in-report-themes), voit [tuoda mukautetun teeman JSON-tiedoston](#import-custom-report-theme-files) tai voit [käyttää **Mukauta teemaa** -valintaikkunaa](#create-and-customize-a-theme-in-power-bi-desktop).

Lisätietoja siitä, mitä oletusarvoja voidaan muokata, saat alempaa kohdasta [raporttiteeman JSON-muoto](#report-theme-json-file-format).

### <a name="built-in-report-themes"></a>Valmiit raporttiteemat

Valitse käytettävissä olevista valmiista raporttiteemoista seuraavasti:

1. Valitse **Vaihda teemaa** **Aloitus**-valintanauhassa.

   ![Valitse raporttiteema](media/desktop-report-themes/report-themes-2a.png)

2. Valitse avattavasta valikosta jokin valittavana olevista teemoista.

   Raporttiteema on nyt käytössä raportissa.

Seuraavassa taulukossa on näkyvissä käytettävissä olevat valmiit raporttiteemat.

| Valmis raporttiteema | Oletusvärien järjestys |
|------ |---------- |
| Oletus | ![Oletus](media/desktop-report-themes/report-themes-color-scheme-default.png)|
| Highrise | ![Highrise](media/desktop-report-themes/report-themes-color-scheme-highrise.png)|
| Johtaja | ![Johtaja](media/desktop-report-themes/report-themes-color-scheme-executive.png)|
| Rajaseutu| ![Rajaseutu](media/desktop-report-themes/report-themes-color-scheme-frontier.png)|
| Innovoi | ![Innovoi](media/desktop-report-themes/report-themes-color-scheme-innovative.png)|
| Kukoistus | ![Kukoistus](media/desktop-report-themes/report-themes-color-scheme-bloom.png)|
| Vuorovesi| ![Vuorovesi](media/desktop-report-themes/report-themes-color-scheme-tidal.png)|
| Lämpötila | ![Lämpötila](media/desktop-report-themes/report-themes-color-scheme-temperature.png)|
| Aurinko| ![Aurinko](media/desktop-report-themes/report-themes-color-scheme-solar.png)|
| Poikkeava | ![Poikkeava](media/desktop-report-themes/report-themes-color-scheme-divergent.png)|
| Myrsky | ![Myrsky](media/desktop-report-themes/report-themes-color-scheme-storm.png)|
| Perinteinen | ![Perinteinen](media/desktop-report-themes/report-themes-color-scheme-classic.png)|
| Kaupungin puisto | ![Kaupungin puisto](media/desktop-report-themes/report-themes-color-scheme-city-park.png)|
| Luokkahuone | ![Luokkahuone](media/desktop-report-themes/report-themes-color-scheme-classroom.png)|
| Turvallinen värisokeille | ![Turvallinen värisokeille](media/desktop-report-themes/report-themes-color-scheme-colorblind-safe.png)|
| Sähköinen | ![Sähköinen](media/desktop-report-themes/report-themes-color-scheme-electric.png)|
| Suuri kontrasti | ![Suuri kontrasti](media/desktop-report-themes/report-themes-color-scheme-high-contrast.png)|
| Auringonlasku | ![Auringonlasku](media/desktop-report-themes/report-themes-color-scheme-sunset.png)|
| Hämy | ![Hämy](media/desktop-report-themes/report-themes-color-scheme-twilight.png)|

## <a name="customize-report-themes"></a>Raporttiteemojen mukauttaminen

Power BI Desktopin joulukuun 2019 julkaisuversiosta lähtien raporttiteemoja voi mukauttaa kahdella eri tavalla:

- [Teeman luominen ja mukauttaminen Power BI Desktopissa](#create-and-customize-a-theme-in-power-bi-desktop)
- [Mukautetun raporttiteeman JSON-tiedoston luominen ja mukauttaminen](#introduction-to-report-theme-json-files)

### <a name="create-and-customize-a-theme-in-power-bi-desktop"></a>Teeman luominen ja mukauttaminen Power BI Desktopissa

Teeman mukauttaminen suoraan Power BI Desktopissa:

1. Valitse **Aloitus**-valintanauhassa **Vaihda teemaa** > **Mukauta nykyistä teemaa**.

   Näyttöön tulee valintaikkuna, jossa näytetään tapoja mukauttaa raportissa parhaillaan käytössä olevaa raporttiteemaa.

   ![Teeman mukauttaminen](media/desktop-report-themes/report-themes_5b.png)

2. Jos pidät aiemmin luodusta teemasta ja haluat tehdä joitakin muutoksia, valitse (tai tuo) teema ja valitse sitten **Mukauta nykyistä teemaa**.

   ![Mukauta nykyistä teemaa](media/desktop-report-themes/report-themes_5c.png)

Mukautettavissa olevat teeman asetukset löytyvät seuraavista luokista, jotka näkyvät **Mukauta teemaa** -ikkunassa:

- **Nimi ja värit**: Teeman nimi ja väriasetukset sisältävät [teeman värit](#how-report-theme-colors-stick-with-your-reports), asennearvojen värit, poikkeavat värit ja [rakennevärit (lisäasetukset)](#setting-structural-colors).
- **Text**: Tekstiasetuksiin sisältyvät fonttiperhe, koko ja väri, jotka määrittävät [pääasiallisen tekstiluokan oletusarvot](#setting-formatted-text-defaults) etiketeille, otsikoille, korteille ja suorituskykyilmaisimille sekä välilehtien otsikoille.
- **Visualisoinnit**: Visualisointiasetukset sisältävät taustan, reunan, ylätunnisteen ja työkaluvihjeet.
- **Sivu**: Sivun elementtien asetukset sisältävät taustakuvan ja taustan.
- **Suodatinruutu**: Suodatinruudun asetukset sisältävät taustan värin, läpinäkyvyyden, fontin ja kuvakkeen värin, koon ja suodatinkortit.

Kun olet tehnyt haluamasi muutokset, Tallenna teema valitsemalla **Käytä ja tallenna**. Teemaa voi nyt käyttää nykyisessä raportissa, ja se voidaan viedä.

Nykyisen teeman mukauttaminen tällä tavalla tekee teemojen mukauttamisesta helppoa ja nopeaa. Voit kuitenkin tehdä teemoihin hienovaraisempia mukautuksia, jotka edellyttävät teeman [JSON-tiedoston](#report-theme-json-file-format) muokkaamista.

> [!TIP]
> Voit mukauttaa tavallisimpia raporttiteemavalintoja käyttämällä valintaikkunan **Mukauta teemaa** ohjausobjekteja. Jos haluat lisää hallintavaltaa, voit halutessasi viedä JSON-tiedoston ja tehdä hienosäädettyjä muutoksia muokkaamalla manuaalisesti tiedoston asetuksia. Voit nimetä uudelleen tämän hienosäädetyn JSON-tiedoston ja tuoda sen myöhemmin.

### <a name="import-custom-report-theme-files"></a>Mukautettujen raporttiteematiedostojen tuominen

Voit tuoda mukautetun raporttiteematiedoston seuraavasti:

1. Valitse **Aloitus**-valintanauhassa **Vaihda teemaa** ja valitse sitten avattavasta valikosta **Tuo teema**.

   ![Tuo teema](media/desktop-report-themes/report-themes-3a.png)

   Näyttöön avautuu ikkuna, jossa voit selata JSON-teematiedoston sijaintiin.

2. Seuraavassa kuvassa saatavilla on muutamia juhlapyhäteematiedostoja. Valitaan juhlapyhäteema maaliskuulle, *St Patricks Day.json*.

   ![Juhlapyhäteema](media/desktop-report-themes/report-themes_4.png)

   Kun teematiedosto on ladattu, Power BI Desktop näyttää onnistumisilmoituksen.

   ![Teeman tuominen onnistui](media/desktop-report-themes/report-themes_5.png)

## <a name="introduction-to-report-theme-json-files"></a>Raporttiteeman JSON-tiedostojen esittely

 Kun avaat edellisessä osiossa mainitun JSON-perustiedoston, (St Patricks Day.json), se näyttää seuraavanlaiselta:

 ```json
    {
        "name": "St Patrick's Day",
        "dataColors": ["#568410", "#3A6108", "#70A322", "#915203", "#D79A12", "#bb7711", "#114400", "#aacc66"],
        "background":"#FFFFFF",
        "foreground": "#3A6108",
        "tableAccent": "#568410"
    }
```

Tässä raporttiteeman JSON-tiedostossa on seuraavat rivit:

- **name**: Raporttiteeman nimi. Tämä kenttä on ainoa pakollinen kenttä.
- **dataColors**: Luettelo Power BI Desktopin visualisointien tietojen heksadesimaalivärikoodeista. Luettelo voi sisältää haluamasi määrän värejä.
- **background**, **firstLevelElements** ja **tableAccent** (jne): Väriluokkia. Väriluokkien avulla voit valita useita rakennevärejä raporttiisi yhdellä kertaa.

Voit käyttää tätä JSON-tiedostoa perustana luodaksesi oman mukautetun raporttiteematiedoston tuontia varten. Jos haluat mukauttaa vain raportin perusvärejä, muuta tiedoston nimeä ja heksadesimaalikoodeja.

Voit määrittää raporttiteeman JSON-tiedostossa vain muotoilun, jota haluat muuttaa. Jos jotakin ei määritetä JSON-tiedostossa, se palautuu Power BI Desktopin oletusasetuksiin.

JSON-tiedoston luomisella on monia etuja Voit esimerkiksi määrittää kaikkien kaavioiden fonttikooksi 12, tietyn fonttiperheen käyttöön tietyissä visualisoinneissa tai poistaa tietoselitteet käytöstä tietyissä kaaviotyypeissä. Kun käytät JSON-tiedostoa, voit luoda raporttiteematiedoston, jolla yhdenmukaistat kaavioita ja raportteja. Näin takaat helposti organisaatiosi raporttien yhdenmukaisuuden.

Lisätietoja JSON-tiedoston muodosta on kohdassa [Raporttiteeman JSON-tiedoston muotoilu](#report-theme-json-file-format).

> [!NOTE]
> Mukautetun JSON-raportin muokkaaminen [**Mukauta teemaa** -valintaruudusta](#create-and-customize-a-theme-in-power-bi-desktop) on turvallista.  Valintaruutu ei muuta sellaisia teema-asetuksia, jotka eivät ole sen hallinnassa, ja se päivittää raporttiteemaan tehdyt muutokset paikalla.

## <a name="how-report-theme-colors-stick-with-your-reports"></a>Miten raporttiteeman värit pysyvät raporteissasi?

Kun julkaiset raportin Power BI -palveluun, raporttiteeman värit pysyvät sen mukana. **Muoto**-paneelin **Tietojen värit** -osion värit ovat raporttiteemasi mukaisia.

Voit tarkastella raporttiteeman käytettävissä olevia värejä seuraavasti:

1. Valitse visualisointi.

2. Valitse **Visualisointi**-ruudun **Muotoile**-osasta **Tietojen värit**.

3. Valitse kohteen avattava luettelo, jos haluat tarkastella raporttiteeman **Teeman värit** -tietoja.

   ![Teeman värit](media/desktop-report-themes/report-themes_8.png)

Esimerkissä sen jälkeen, kun St. Patrick's Day -raporttiteemassa on otettu käyttöön useita vihreitä ja ruskeita värejä, voit tarkastella teeman värejä. Näetkö kaiken tämän vihreän? Tämä johtuu siitä, että nämä värit sisältyvät tuotuun raporttiteemaan, joka otettiin käyttöön.

Värivalikoiman värit ovat suhteessa nykyiseen teemaan. Oletetaan esimerkiksi, että valitset arvopisteen ylimmän rivin kolmannen värin. Jos vaihdat teemaa myöhemmin, kyseisen arvopisteen väri päivittyy automaattisesti uuden teeman ylimmän rivin kolmanteen väriin. Näin tapahtuisi myös, jos vaihtaisit teemaa Microsoft Officessa.

### <a name="situations-when-report-theme-colors-wont-stick-to-your-reports"></a>Tilanteet, joissa raporttiteeman värit eivät pysy raporteissasi

Oletetaan, että otat käyttöön mukautetun värijoukon (tai yksittäisen värin) visualisoinnin tietyssä arvopisteessä värinvalitsimen **Mukautettu väri** -vaihtoehdon avulla. Kun otat raporttiteeman käyttöön, se *ei* ohita tätä mukautettua arvopisteen väriä.

Saatat myös haluta määrittää arvopisteen värin manuaalisesti käyttämällä **Teeman värit** -osiota. Värejä *ei* päivitetä, kun otat käyttöön uuden raporttiteeman. Jos haluat palauttaa oletusvärit (jotta ne päivittyvät, kun otat käyttöön uuden raporttiteeman), valitse värinvalitsimen **Teeman värit** -valikoimasta **Palauta oletusasetukseen** tai valitse väri.

![Palauta oletusasetukset](media/desktop-report-themes/report-themes_9.png)

Monet Power BI -visualisoinnit eivät käytä raporttiteemoja.

## <a name="custom-report-theme-files-you-can-use-right-now"></a>Tällä hetkellä käytettävissä olevat mukautetut raporttiteematiedostot

Haluatko aloittaa raporttiteemojen käytön? Tutustu mukautettuihin raporttiteemoihin [teemavalikoimassa](https://community.powerbi.com/t5/Themes-Gallery/bd-p/ThemesGallery) tai kokeile seuraavia valmiita mukautettuja raporttiteeman JSON-tiedostoja, jotka voit ladata ja tuoda Power BI Desktop -raporttiisi:

- [Aaltomuoto-teema](https://community.powerbi.com/t5/Themes-Gallery/Waveform/m-p/140536). Tämä raporttiteema esiteltiin [blogikirjoituksessa](https://powerbi.microsoft.com/blog/power-bi-desktop-march-feature-summary/), jossa kerrottiin raporttiteemojen ensijulkaisusta. [Lataa Waveform.json](https://go.microsoft.com/fwlink/?linkid=843924).

  ![Waveform.json-teema](media/desktop-report-themes/report-themes_10.png)

- [Värisokeille sopiva teema](https://community.powerbi.com/t5/Themes-Gallery/Color-Blind-Friendly/m-p/140597).
Tämän raporttiteema on näkörajoitteisille helppolukuisempi. [Lataa ColorblindSafe-Longer.json](https://go.microsoft.com/fwlink/?linkid=843923).

  ![ColorblindSafe-Longer.json-teema](media/desktop-report-themes/report-themes_11.png).

- Power View -teemat, kuten Apothecary.json. [Lataa Power View -teemoja zip-tiedostona](https://go.microsoft.com/fwlink/?linkid=843925).

  ![Apothecary.json-teema](media/desktop-report-themes/report-themes_12.png)

- Valentine's Day -teema.

  ![Valentine's Day -teema](media/desktop-report-themes/report-themes_13.png)

  Tässä on Valentine's day -teeman JSON-tiedoston koodi:

   ```json
       {
           "name": "Valentine's Day",
           "dataColors": ["#990011", "#cc1144", "#ee7799", "#eebbcc", "#cc4477", "#cc5555", "#882222", "#A30E33"],
           "background":"#FFFFFF",
           "foreground": "#ee7799",
           "tableAccent": "#990011"
       }
   ```

Alla on muutama muu raporttiteema, joiden avulla pääset alkuun:

- [Sunflower-twilight](https://community.powerbi.com/t5/Themes-Gallery/Sunflower-Twilight/m-p/140749)
- [Plum](https://community.powerbi.com/t5/Themes-Gallery/Plum/m-p/140711)
- [Autumn](https://community.powerbi.com/t5/Themes-Gallery/Autumn/m-p/140746)
- [High contrast.](https://community.powerbi.com/t5/Themes-Gallery/Color-Blind-Friendly/m-p/140597)

Raporttiteemojen avulla voit ilmaista Power BI Desktop -raporteissasi itseäsi, organisaatiotasi, juhlapyhää tai vuodenaikaa värikkäin tavoin.

## <a name="export-report-themes-preview"></a>Raporttiteemojen vieminen (esiversio)

Power BI Desktopin joulukuun 2019 julkaisuversiosta alkaen voit nyt halutessasi viedä käytössä olevan raporttiteeman suoraan Power BI Desktopista JSON-tiedostoon. Kun olet vienyt raporttiteeman, voit käyttää sitä uudelleen muissa raporteissa. Tämän asetuksen avulla voit viedä JSON-tiedoston useimpiin valmiisiin teemoihin. Ainoat poikkeukset ovat perusteemat (klassinen ja oletusteema), joiden pohjalle muut teemat rakentuvat tuonnin yhteydessä.

Käytössä olevan teeman vieminen Power BI Desktopista:

1. Valitse **Tiedosto** > **Asetukset ja vaihtoehdot** > **Asetukset**.

2. Valitse **Esikatselutoiminnot** -osiossa **Mukauta nykyistä teemaa** ja valitse sitten **OK**.

   Saatat saada kehotteen käynnistää Power BI Desktop uudelleen, jotta esiversiotoiminto voidaan ottaa käyttöön. Kun olet käynnistänyt tietokoneen uudelleen, voit aloittaa käytössä olevan teeman viemisen.

3. Valitse **Aloitus**-valintanauhassa **Vaihda teemaa** > **Vie nykyinen teema**.

4. Siirry **Tallenna nimellä** -valintaikkunassa hakemistoon, johon JSON-tiedosto tallennetaan, ja valitse sitten **Tallenna**.

## <a name="report-theme-json-file-format"></a>Raporttiteeman JSON-tiedoston muotoilu

Teeman JSON-tiedostossa on yksinkertaisimmillaan vain yksi pakollinen rivi: **nimi**.

```json
{
    "name": "Custom Theme"
}
```

Muut rivit kuin **nimi** ovat valinnaisia, mikä tarkoittaa sitä, että voit halutessasi lisätä vain sellaisia ominaisuuksia, jotka haluat erityisesti muotoilla teematiedostoon, ja käyttää Power BI:n oletusarvoja muualla.

### <a name="setting-theme-colors"></a>Teemavärien määrittäminen

**Nimi**-kohdassa voit lisätä seuraavia perustietojen väriin liittyviä ominaisuuksia:

- **dataColors**: Luettelo värien heksadesimaalivärikoodeista, joilla väritetään tietoja edustavat muodot Power BI Desktop -visualisoinneissa. Luettelo voi sisältää haluamasi määrän värejä. Kun tämän luettelon kaikkia värejä on käytetty ja visualisointiin tarvitaan vielä lisää värejä, se alkaa käyttää Power BI:n oletusarvoista värivalikoimaa.
- **hyvä**, **neutraali**, **huono**: Nämä ominaisuudet määrittävät vesiputouskaaviossa ja suorituskykyilmaisimen visualisoinnissa käytetyt värit.
- **suurin**, **keski**, **pienin**, **tyhjäarvo**: Nämä värit määrittävät eri liukuvärit ehdollisen muotoilun valintaikkunassa.

Nämä värit määrittävä perusteema voisi näyttää seuraavalta:

```json
{
    "name": "Custom Theme",
    "dataColors": [
        "#118DFF",
        "#12239E",
        "#E66C37",
        "#6B007B",
        "#E044A7",
        "#744EC2",
        "#D9B300",
        "#D64550",
        "#197278",
        "#1AAB40"
    ],
    "good": "#1AAB40",
    "neutral": "#D9B300",
    "bad": "#D64554",
    "maximum": "#118DFF",
    "center": "#D9B300",
    "minimum": "#DEEFFF",
    "null": "#FF7F48"
}
```

### <a name="setting-structural-colors"></a>Rakennevärien määrittäminen

Seuraavaksi voit lisätä erilaisia väriluokkia, kuten **background** ja **firstLevelElements**. Nämä väriluokat määrittävät raportin elementtien rakennevärit, kuten akseliruudukot, korostusvärit ja taustavärit visuaalisille elementeille.

Seuraavassa taulukossa ovat kuusi väriluokkaa, jotka voit muotoilla.  **Väriluokkien** nimet vastaavat nimiä, jotka löytyvät “Lisäasetukset”-aliosasta, “Nimi ja värit” -osasta, [**Mukauta teemaa** -valintaikkunasta](#create-and-customize-a-theme-in-power-bi-desktop).

|Väriluokka  |Mitä väriluokka muotoilee  |
|---------|---------|
| **firstLevelElements** <br> **foreground**    (vanhentunut) | Otsikoiden taustaväri (arvopisteiden ulkopuolella) <br> Trendiviivan väri <br>  Tekstiruudun oletusväri <br> Taulukoiden ja matriisien arvojen sekä summien fonttien värit Tietopalkkien akselien väri <br> Korttien arvopisteiden otsikot <br> Mittarien kuvaselitearvojen väri <br> Suorituskykyilmaisimien tavoitteen väri <br>  Suorituskykyilmaisimien tekstin väri <br> Osittajien kohteen väri (kohdistustilassa)  <br> Osittajien avattavan kohteen fontin väri <br> Osittajien lukusyötteen fontin väri <br> Osittajien ylätunnisteen fontin väri <br> Pistekaavioiden suhdeviivan väri <br> Viivakaavion ennusteviivan väri <br> Kartan johtoviivan väri <br> Suodatinruudun ja kortin tekstien väri|
| **secondLevelElements** <br> **foregroundNeutralSecondary** (vanhentunut) | “vaalea” [toissijaiset tekstiluokat](#setting-formatted-text-defaults) <br> Otsikoiden värit  <br> Selitteiden otsikoiden väri <br> Akselien otsikoiden väri <br> Taulukoiden ja matriisien otsikoiden fontin väri <br> Mittarin kohteen ja kohteiden johtoviivan väri <br>  Suorituskykyilmaisimen trendiakselin väri <br> Osittajien liukusäätimen väri <br> Osittajien kohteiden fontin väri <br> Osittajien ääriviivan väri <br> Viivakaavion väri hiirellä osoitettaessa <br> Monirivisten korttien otsikon väri <br> Valintanauhavetojen väri <br> Muotokarttojen reunan väri <br> Painiketekstien fontin väri <br> Painikekuvakkeiden viivan väri <br> Painikekuvakkeiden ääriviivan väri |
| **thirdLevelElements** <br >**backgroundLight** (vanhentunut) | Akselien ruudukoiden väri <br> Taulukoiden ja matriisien ruudukoiden väri <br> Osittajien otsikoiden taustaväri (kohdistustilassa)  <br> Monirivisten korttien ääriviivan väri  <br> Muotojen täyttöväri <br> Taustavärien kaaren taustaväri <br> Sovelletun suodatinkortin taustaväri <br> Kun tausta = FFFFFF: <br> Käytöstä poistetun painikkeen täytön väri <br> Käytöstä poistetun painikkeen ääriviivan väri <br> |
| **fourthLevelElements** <br> **foregroundNeutralTertiary** (vanhentunut) | selitteen himmennetty väri <br> Korttiluokan otsikon väri <br> Monirivisten korttien luokkien otsikoiden väri <br> Monirivisten korttien palkin väri <br> Vuokaavion konversioasteen vetojen väri <br> Käytöstä poistetun painikkeen fontin väri <br> Käytöstä poistetun viivan väri <br> |
| **background** | Otsikoiden taustaväri (arvopisteiden sisäpuolella) <br> Osittajien avattavien kohteiden taustaväri  <br> Rengaskaavioiden vetojen väri <br> Puukarttojen vetojen väri <br> Yhdistelmäkaavioiden taustaväri <br> Painikkeiden täyttöväri <br> Suodatinruudun ja käytettävissä olevan suodatinkortin taustaväri |
| **secondaryBackground** <br> **backgroundNeutral** (vanhentunut) | Taulukoiden ja matriisien ruudukoiden ääriviivan väri <br> Muotokarttojen oletusväri <br> Nauhakaavion täyttöväri (kun sarjojen vastaavuusvaihtoehto on pois käytöstä) <br> Kun tausta != FFFFFF: <br> Käytöstä poistetun painikkeen täytön väri <br> Käytöstä poistetun painikkeen ääriviivan väri <br> |
| **tableAccent** | Ohittaa taulukoiden ja matriisien ruudukon ääriviivan värin, kun käytössä |

Seuraavassa on esimerkkiteema, joka määrittää väriluokat:

```json
{
    "name": "Custom Theme",
    "firstLevelElements": "#252423",
    "secondLevelElements": "#605E5C",
    "thirdLevelElements": "#F3F2F1",
    "fourthLevelElements": "#B3B0AD",
    "background": "#FFFFFF",
    "secondaryBackground": "#C8C6C4",
    "tableAccent": "#118DFF"
}
```

> [!TIP]
> Jos luot “pimeää teemaa” tai muuta värikästä teemaa, joka eroaa tyypillisestä “mustasta” **firstLevelElements** “valkoisella” **taustalla** -tyylillä, varmista että määrität myös muiden rakennevärien arvot sekä [ensisijaisen tekstiluokan väriarvot](#setting-formatted-text-defaults).  Tämä varmistaa, että (esimerkiksi) kaavioiden otsikkotaustaiset arvopisteen otsikot sopivat yhteen odotetun tyylin kanssa ja ovat luettavissa, samalla kun varmistuu, että akselin ruudukot ovat näkyvissä.

### <a name="setting-formatted-text-defaults"></a>Muotoillun tekstin oletusarvojen määrittäminen

Seuraavaksi voit lisätä JSON-tiedostoon tekstiluokkia. Tekstiluokat muistuttavat väriluokkia, mutta niiden avulla voit päivittää raportin tekstiryhmien fontin koon, värin ja perheen.

Tekstiluokkia on 12, mutta riittää, että määrität vain neljä luokkaa, joita kutsutaan *ensisijaisiksi luokiksi*. Niiden avulla voit muuttaa kaikkia raportin tekstimuotoiluja.  Nämä neljä ensisijaista luokkaa voidaan määrittää [**Mukauta teemaa** -valintaikkunassa](#create-and-customize-a-theme-in-power-bi-desktop) “Teksti”-osiossa: “Yleinen” vastaa **etikettiä**, “Otsikko” **otsikkoa**, “Kortit ja suorituskykyilmaisimet” **kuvatekstiä** ja “Välilehden otsikko” **ylätunnistetta**.

Muut tekstiluokat, joita pidetään *toissijaisina luokkina*, ovat ominaisuuksiltaan niihin liittyvien ensisijaisten luokkien johdannaisia. Usein toissijaiselle luokalle valitaan vaaleampi tekstin värisävy tai prosenttiluvultaan suurempi tai pienempi tekstikoko ensisijaiseen luokkaan verrattuna.

Katso esimerkiksi **otsikkoluokkaa**. **Otsikkoluokan** oletusmuotoilu on Segoe UI, #252423 (a tummanharmaa väri) ja 12 pisteen fonttikoko. Tätä luokkaa käytetään taulukon ja matriisin arvojen muotoiluun. Yleensä taulukon tai matriisin kokonaissummissa on samanlainen muotoilu, mutta ne on tummennettu **lihavoidulla otsikkoluokalla**, jotta ne erottuvat paremmin. Sinun ei kuitenkaan tarvitse määrittää kyseistä luokkaa teeman JSON-muodossa. Power BI tekee sen automaattisesti. Jos myöhemmin päätät, että haluat otsikkojen fonttikoon olevan 14 pistettä ja määrität sen teemassasi, sinun ei tarvitse päivittää **lihavoitua otsikkoluokkaa**, koska se perii kaikki tekstimuotoilut **otsikkoluokasta**.

Seuraavassa taulukossa on esitelty seuraavat tiedot:

- Neljä ensisijaista tekstiluokkaa, mitä ne muotoilevat ja niiden oletusasetukset
- Toissijaiset luokat, mitä ne muotoilevat ja niiden oletusasetuksen, joka on yksilöllinen ensisijaiseen luokkaan nähden

|Ensisijainen luokka  |Toissijaiset luokat  |JSON-luokan nimi  | Oletusasetukset  |Liittyvät visualisointien objektit  |
|---------|---------|---------|---------|---------|
| Kuvateksti | – | kuvateksti | DIN <br> #252423 <br> 45pt |Korttien arvopisteiden otsikot <br> Suorituskykyilmaisin|
|Ylätunniste|–|ylätunniste|Segoe UI Semibold <br> #252423 <br> 12pt |Tärkeimpien vaikuttajien otsikot |
| Otsikko || otsikko |DIN <br> #252423 <br> 12pt |Luokka-akselin otsikko <br> Arvoakselin otsikko <br> Monirivisten korttien otsikko * <br> Osittajan otsikko|
|-| Suuri otsikko | largeTitle |14pt |Visualisointien otsikko |
|Selite ||selite |Segoe UI<br>#252423<br>10pt |Taulukko- ja matriisisarakkeen otsikot <br> Matriisirivin otsikot<br>Taulukon ja matriisin ruudukko<br>Taulukon ja matriisin arvot |
|-|Puolilihavoitu |semiboldLabel| Segoe UI Semibold | Avainvaikuttajien profiiliteksti
|-|Suuri |largeLabel |12pt | Monirivisen kortin arvopisteiden otsikot |
|-|Pieni |smallLabel |9pt |Viiteviivan otsikot * <br>Osittajan päivämääräalueiden otsikot<br> Osittajien lukusyötteen tekstityyli<br>Osittajien hakukenttä<br>Avainvaikuttajien vaikuttajateksti|
|-|Vaalea |lightLabel |#605E5C |Selitteen teksti<br>Painikkeen teksti<br>Luokka-akselin otsikko<br>Vuokaavion arvopisteiden otsikot<br>Vuokaavion konversioasteiden otsikot<br>Mittarin kohde<br>Pistekaavion luokan arvo<br>Osittajan kohteet|
|-|Lihavointi |boldLabel |Segoe UI Bold |Matriisin välisummat<br>Matriisin loppusummat<br>Taulukon summat |
|-|Suuri ja vaalea |largeLightLabel |#605E5C<br>12pt |Korttiluokkien otsikot<br>Mittarien otsikot<br>Monirivisten korttien luokkien otsikot |
|-|Pieni ja vaalea |smallLightLabel |#605E5C<br>9pt |Arvopisteiden otsikot<br>Arvoakselien otsikot|

*\*Myös tähdellä merkityt kohteet väritetään raporttiteeman ensimmäisen tiedon mukaisella värillä.*

> [!TIP]
> Tekstiluokkien *vaaleat* muunnelmat väritetään vaalealla värillä, joka perustuu yllä määriteltyihin [rakenneväreihin](#setting-structural-colors).  Jos olet luomassa “tummaa teemaa”, huolehdi siitä, että määrität myös “firstLevelElements”-värit (jotka vastaavat ensisijaista tekstiväriä), “secondLevelElements”-värit (jotka vastaavat tekstille ennakoitua “vaaleaa” väriä). ja taustavärin (riittävästi kontrastia sekä ensisijaisten että toissijaisten elementtien väreille).

Tässä on esimerkkiteema, joka määrittää vain ensisijaiset tekstiryhmät:

```json
{
    "name": "Custom Theme",
    "textClasses": {
        "callout": {
            "fontSize": 45,
            "fontFace": "DIN",
            "color": "#252423"
        },
        "title": {
            "fontSize": 12,
            "fontFace": "DIN",
            "color": "#252423"
        },
        "header": {
            "fontSize": 12,
            "fontFace": "Segoe UI Semibold",
            "color": "#252423"
        },
        "label": {
            "fontSize": 10,
            "fontFace": "Segoe UI",
            "color": "#252423"
        }
    }
}
```

Sinun ei tarvitse määrittää toissijaisia luokkia teematiedostossa, koska ne perivät ensisijaisesta luokasta. Jos et kuitenkaan pidä periytymissäännöistä (jos esimerkiksi et halua, että kokonaissummat ovat taulukon arvojen lihavoituja versioita), voit muotoilla toissijaisia luokkia suoraan teematiedostossa aivan kuin ensisijaisiakin luokkia.

### <a name="setting-visual-property-defaults-visualstyles"></a>Visuaalisen ominaisuuden oletusarvojen määrittäminen (`visualStyles`)

Lopuksi: jos haluat luoda yksityiskohtaisemman JSON-tiedoston, jolla voit määrittää raportin kaikkien visualisointien muotoilun tarkemmin, voit lisätä JSON-tiedostoon **visualStyles**-osion ja asettaa muotoilun tarkemmat määritelmät tämän osion sisään. Tässä on malliesimerkki **visualStyles**-osiosta:

```json
    "visualStyles": {
        "<visualName>": {
            "<styleName>": {
                "<cardName>": [{
                    "<propertyName>": <propertyValue>
                }]
            }
        }
    }
```

Käytä **visualName**- ja **cardName**-osioissa tiettyä visualisointia ja kortin nimeä. Tällä hetkellä **styleName** on aina tähtimerkki (*), mutta tulevissa julkaisuissa voit luoda visualisoinneille eri tyylejä ja nimetä niitä (kuin taulukkojen ja matriisien tyylejä). **propertyName** on muotoiluasetuksen nimi ja **propertyValue** on kyseisen muotoiluasetuksen arvo.

Käytä **visualName**- ja **cardName**-kohdissa tähteä, jos haluat, että asetus koskee kaikkia visualisointeja tai kortteja, joissa on ominaisuus. Jos käytät tähteä sekä visualisoinnin että kortin nimessä, käytännössä asetusta sovelletaan raportissa yleisesti. Esimerkiksi fonttikoko tai tietty kirjasinperhe valitaan kaikille visualisoinneille.

Tässä on esimerkki, jossa asetetaan joitain ominaisuuksia visualisointien tyylien avulla:

```json
{
   "name":"Custom Theme",
   "visualStyles":{
      "*": {
         "*": {
            "*": [{
                "wordWrap": true
            }],
            "categoryAxis": [{
                "gridlineStyle": "dotted"
            }],
            "filterCard": [
              {
                "$id": "Applied",
                "foregroundColor": {"solid": {"color": "#252423" } }
              },
              {
                "$id":"Available",
                "border": true
              }
            ]
         }
      },
      "scatterChart": {
         "*": {
            "bubbles": [{
                  "bubbleSize": -10
            }]
         }
      }
   }
}
```

Tässä esimerkissä on seuraavat asetukset:

- ottaa automaattisen rivityksen käyttöön kaikkialla
- määrittää ruudukon tyylin pisteviivaksi kaikille luokka-akselin visualisoinneille
- määrittää jotkin muotoilut käytettävissä oleville ja sovelletuille suodatinkorteille (huomaa muotoilu, jossa ”$id”-arvoa käytetään määrittämään suodatinkorttien eri versiot)
- määrittää pistekaavioiden kuplan koon arvoon -10.

> [!NOTE]
> Sinun tarvitsee määrittää vain ne muotoiluasetukset, joita haluat muokata. Kaikki muotoiluelementit, jotka eivät ole mukana JSON-tiedostossa, ovat oletusarvojen ja -asetusten mukaisia.

### <a name="visualstyles-definition-list"></a>`visualStyles`-määritelmien luettelo

Tämän osion taulukoissa määritetään visualisointien nimet (**visualName**), korttien nimet (**cardName**), ominaisuuksien nimet (**propertyName**) ja luetteloinnit, joita tarvitaan JSON-tiedoston luomiseen.

| visualName-arvot |
| --- |
| areaChart |
| barChart |
| basicShape |
| card |
| clusteredBarChart |
| clusteredColumnChart |
| columnChart |
| comboChart |
| donutChart |
| filledMap |
| funnel |
| gauge |
| hundredPercentStackedBarChart |
| hundredPercentStackedColumnChart |
| image |
| kpi |
| lineChart |
| lineClusteredColumnComboChart |
| lineStackedColumnComboChart |
| kartta |
| multiRowCard |
| pieChart |
| pivotTable |
| ribbonChart |
| scatterChart |
| shapeMap |
| slicer |
| stackedAreaChart |
| tableEx |
| puukartta |
| waterfallChart |

Seuraavassa taulukossa määritetään **cardName**-arvot. Jokaisen solun ensimmäinen arvo on JSON-tiedoston termi. Toinen arvo on kortin nimi Power BI Desktop -käyttöliittymässä.

| cardName-arvot |
| --- |
| axis: Mittarin akseli |
| breakdown: Erittely |
| bubbles: Kuplat |
| calloutValue: Kuvaselitearvo |
| card: Kortti |
| cardTitle: Kortin otsikko |
| categoryAxis: X-akseli |
| categoryLabels: Luokkien otsikot |
| columnFormatting: Kentän muotoilu |
| columnHeaders: Sarakeotsikot |
| dataLabels: Arvopisteiden otsikot |
| fill: Täyttö |
| fillPoint: Täyttöpiste |
| forecast: Ennuste |
| general: Yleiset |
| goals: Tavoitteet |
| grid: Ruudukko |
| header: Ylätunniste |
| imageScaling: Skaalaus |
| indicator: Ilmaisin |
| items: Kohteet |
| labels: Arvopisteiden otsikot |
| legend: Selite |
| lineStyles: Muodot |
| mapControls: Kartan ohjausobjektit |
| mapStyles: Karttatyylit |
| numericInputStyle: Numeeriset syötteet |
| percentBarLabel: Muuntonopeuden otsikko |
| plotArea: Tulostusalue |
| plotAreaShading: Symmetriavarjostus |
| ratioLine: Suhdeviiva |
| referenceLine: Yhtenäinen viiva |
| ribbonChart: Valintanauhat |
| rotation: Kierto |
| rowHeaders: Riviotsikot |
| selection: Valinnan hallinta |
| sentimentColors: Asennearvojen värit |
| shape: Muoto |
| slider: Liukusäädin |
| status: Värikoodaus |
| subTotals: Välisummat |
| target: Tavoite |
| total: Kokonaissumma |
| trend: Trendiviiva |
| trendline: Trendiakseli |
| valueAxis: Y-akseli |
| values: Arvot |
| wordWrap: Automaattinen rivitys |
| xAxisReferenceLine: X-akselin yhtenäinen viiva |
| y1AxisReferenceLine: Yhtenäinen viiva |
| zoom: Zoomaa |

### <a name="properties-within-each-card"></a>Kunkin kortin ominaisuudet

Seuraavassa osiossa määritetään kunkin kortin ominaisuudet. Kortin nimen perässä on kunkin ominaisuuden nimi. Näet kunkin ominaisuuden nimen kohdalta, näytetäänkö muotoilu-ruutu, kuvauksen muotoiluasetuksen tarkoituksesta ja muotoiluasetuksen tyypin. Tämän lähestymistavan ansiosta tiedät, millaisia arvoja voit käyttää teematiedostossasi.

Kun käytät **dateTime**-arvoa, päivämäärän täytyy olla ISO-päivämäärä puolilainausmerkeissä siten, että datetime on alussa. Katso seuraavaa esimerkkiä.

  "datetime'2011-10-05T14:48:00.000Z'"

Totuusarvo on joko true tai false (tosi tai epätosi). Merkkijonojen täytyy olla lainausmerkeissä, kuten seuraavassa esimerkissä: "tämä on merkkijono". Luvut ovat vain itse arvoja (eivät lainausmerkeissä).

Värit ovat seuraavassa muodossa, jossa mukautettu heksadesimaalikoodisi korvaa esimerkin ”FFFFFF”-kohdan:

    { "solid": { "color": "#FFFFFF" } }

Luettelointia käytetään yleisimmin avattavien valikoiden muotoiluasetuksissa, ja se tarkoittaa sitä, että se voidaan määrittää mihin tahansa ruudussa näkyvistä vaihtoehdoista. Se voi olla esimerkiksi "RightCenter", jos haluat sen olevan selitteen paikalla, tai "Tietoarvo, prosenttiosuus", jos haluat käyttää sitä piirakkakaavion tietojen otsikkona. Luettelointiasetukset on näytetty alla ominaisuusluettelossa.

```json
{
      "general":{
        "responsive": {
          "type": [
            "bool"
          ],
          "displayName": [
            "(Preview) Responsive"
          ],
          "description": [
            "The visual will adapt to size changes"
          ]
        },
        "legend": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Select the location for the legend"
          ]
        },
        "showTitle": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Title"
          ],
          "description": [
            "Display a title for legend symbols"
          ]
        },
        "labelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        }
      },
      "categoryAxis": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "axisScale": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Scale type"
          ]
        },
        "start": {
          "type": [
            "numeric",
            "dateTime"
          ],
          "displayName": [
            "Start"
          ],
          "description": [
            "Enter a starting value (optional)"
          ]
        },
        "end": {
          "type": [
            "numeric",
            "dateTime"
          ],
          "displayName": [
            "End"
          ],
          "description": [
            "Enter an ending value (optional)"
          ]
        },
        "axisType": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Type"
          ]
        },
        "showAxisTitle": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Title"
          ],
          "description": [
            "Title for the X-axis",
            "Title for the Y-axis"
          ]
        },
        "axisStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Style"
          ]
        },
        "labelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "labelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "labelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "concatenateLabels": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Concatenate labels"
          ],
          "description": [
            "Always concatenate levels of the hierarchy instead of drawing the hierarchy."
          ]
        },
        "preferredCategoryWidth": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Minimum category width"
          ]
        },
        "titleColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Title color"
          ]
        },
        "titleFontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "titleFontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Title text size"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Select left or right"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "duration": {
          "type": [
            "numeric"
          ]
        }
      },
      "valueAxis": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Select left or right"
          ]
        },
        "axisScale": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Scale type"
          ]
        },
        "start": {
          "type": [
            "numeric",
            "dateTime"
          ],
          "displayName": [
            "Start"
          ],
          "description": [
            "Enter a starting value (optional)"
          ]
        },
        "end": {
          "type": [
            "numeric",
            "dateTime"
          ],
          "displayName": [
            "End"
          ],
          "description": [
            "Enter an ending value (optional)"
          ]
        },
        "showAxisTitle": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Title"
          ],
          "description": [
            "Title for the Y-axis",
            "Title for the X-axis"
          ]
        },
        "axisStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Style"
          ]
        },
        "labelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "labelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "labelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "titleColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Title color"
          ]
        },
        "titleFontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "titleFontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Title text size"
          ]
        },
        "axisLabel": {
          "type": [
            "none"
          ],
          "displayName": [
            "Y-Axis (Column)"
          ]
        },
        "secShow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show secondary"
          ]
        },
        "alignZeros": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Align zeros"
          ],
          "description": [
            "Align the zero tick marks for both value axes"
          ]
        },
        "secAxisLabel": {
          "type": [
            "none"
          ],
          "displayName": [
            "Y-Axis (Line)"
          ]
        },
        "secPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Select left or right"
          ]
        },
        "secAxisScale": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Scale type"
          ]
        },
        "secStart": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Start"
          ],
          "description": [
            "Enter a starting value (optional)"
          ]
        },
        "secEnd": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "End"
          ],
          "description": [
            "Enter an ending value (optional)"
          ]
        },
        "secShowAxisTitle": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Title"
          ],
          "description": [
            "Title for the Y-axis"
          ]
        },
        "secAxisStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Style"
          ]
        },
        "secLabelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ]
        },
        "secFontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "secFontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "secLabelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "secLabelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "secTitleColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Title color"
          ]
        },
        "secTitleFontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "secTitleFontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Title text size"
          ]
        }
      },
      "dataPoint": {
        "defaultColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Default color",
            "Default Column Color"
          ]
        },
        "fill": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Fill"
          ]
        },
        "defaultCategoryColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Default color",
            "Default Column Color"
          ]
        },
        "showAllDataPoints": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show all"
          ]
        }
      },
      "labels": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "showSeries": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "labelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "labelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "showAll": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Customize series"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "labelDensity": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Label density"
          ]
        },
        "labelOrientation": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Orientation"
          ]
        },
        "labelPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ]
        },
        "percentageLabelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "% decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the percentages"
          ]
        },
        "labelStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Label style"
          ]
        }
      },
      "lineStyles": {
        "strokeWidth": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Stroke width"
          ]
        },
        "strokeLineJoin": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Join type"
          ]
        },
        "lineStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        },
        "showMarker": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show marker"
          ]
        },
        "markerShape": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Marker shape"
          ]
        },
        "markerSize": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Marker size"
          ]
        },
        "markerColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Marker color"
          ]
        },
        "showSeries": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Customize series",
            "Show"
          ]
        },
        "shadeArea": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Shade area"
          ]
        }
      },
      "plotArea": {
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for background color"
          ]
        }
      },
      "trend": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "displayName": {
          "type": [
            "text"
          ],
          "displayName": [
            "Name"
          ],
          "description": [
            "Set trend line name"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set trend line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for trend line color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Style"
          ],
          "description": [
            "Set trend line style"
          ]
        },
        "combineSeries": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Combine Series"
          ],
          "description": [
            "Show one trend line per series or combine"
          ]
        }
      },
      "y1AxisReferenceLine": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "value": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value"
          ],
          "description": [
            "Set reference line numeric value"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set reference line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for reference line color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Arrange relative to chart data points"
          ]
        },
        "dataLabelShow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Data label"
          ],
          "description": [
            "Display a data label for the reference line"
          ]
        },
        "dataLabelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set the reference line data label color"
          ]
        },
        "dataLabelDecimalPoints": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Decimal Places"
          ]
        },
        "dataLabelHorizontalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Horizontal Position"
          ],
          "description": [
            "Set the horizontal position for the reference line data label"
          ]
        },
        "dataLabelVerticalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Vertical Position"
          ],
          "description": [
            "Set the vertical position for the reference line data label"
          ]
        },
        "dataLabelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        }
      },
      "referenceLine": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "displayName": {
          "type": [
            "text"
          ],
          "displayName": [
            "Name"
          ],
          "description": [
            "Set reference line name"
          ]
        },
        "value": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value"
          ],
          "description": [
            "Set reference line numeric value"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set reference line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for reference line color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Arrange relative to chart data points"
          ]
        },
        "dataLabelShow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Data label"
          ],
          "description": [
            "Display a data label for the reference line"
          ]
        },
        "dataLabelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set the reference line data label color"
          ]
        },
        "dataLabelDecimalPoints": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Decimal Places"
          ]
        },
        "dataLabelHorizontalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Horizontal Position"
          ],
          "description": [
            "Set the horizontal position for the reference line data label"
          ]
        },
        "dataLabelVerticalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Vertical Position"
          ],
          "description": [
            "Set the vertical position for the reference line data label"
          ]
        },
        "dataLabelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        }
      },
      "line": {
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for background color"
          ]
        },
        "weight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Weight"
          ]
        },
        "roundEdge": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Round edges"
          ]
        }
      },
      "fill": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "fillColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Fill color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for background color"
          ]
        }
      },
      "rotation": {
        "angle": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Rotation"
          ]
        }
      },
      "categoryLabels": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "wordWrap": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        }
      },
      "dataLabels": {
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "cardTitle": {
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "card": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "outlineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Outline color"
          ],
          "description": [
            "Color of the outline"
          ]
        },
        "outlineWeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Outline weight"
          ],
          "description": [
            "Thickness of the outline in pixels"
          ]
        },
        "barShow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show bar"
          ],
          "description": [
            "Display a bar to the left side of the card as an accent"
          ]
        },
        "barColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Bar color"
          ]
        },
        "barWeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Bar thickness"
          ],
          "description": [
            "Thickness of the bar in pixels"
          ]
        },
        "cardPadding": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Padding"
          ],
          "description": [
            "Background"
          ]
        },
        "cardBackground": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background"
          ]
        }
      },
      "percentBarLabel": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "axis": {
        "min": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Min"
          ]
        },
        "max": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Max"
          ]
        },
        "target": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Target"
          ]
        }
      },
      "target": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "labelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "labelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "calloutValue": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Select color for data labels"
          ]
        },
        "labelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "labelPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        }
      },
      "forecast": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "displayName": {
          "type": [
            "text"
          ],
          "displayName": [
            "Name"
          ],
          "description": [
            "Set forecast name"
          ]
        },
        "confidenceBandStyle": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Confidence band style"
          ],
          "description": [
            "Set forecast confidence band style"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set forecast line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for background color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        },
        "transform": {
          "type": [
            "queryTransform"
          ]
        }
      },
      "bubbles": {
        "bubbleSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Size"
          ]
        }
      },
      "mapControls": {
        "autoZoom": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Auto zoom"
          ]
        },
        "zoomLevel": {
          "type": [
            "numeric"
          ]
        },
        "centerLatitude": {
          "type": [
            "numeric"
          ]
        },
        "centerLongitude": {
          "type": [
            "numeric"
          ]
        }
      },
      "mapStyles": {
        "mapTheme": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Theme"
          ]
        }
      },
      "shape": {
        "map": {
          "type": [
            "geoJson"
          ]
        },
        "projectionEnum": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Projection"
          ],
          "description": [
            "Projection"
          ]
        }
      },
      "zoom": {
        "autoZoom": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Auto zoom"
          ],
          "description": [
            "Zoom in on shapes with available data"
          ]
        },
        "selectionZoom": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Selection zoom"
          ],
          "description": [
            "Zoom in on selected shapes"
          ]
        },
        "manualZoom": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Manual zoom"
          ],
          "description": [
            "Allow user to zoom and pan"
          ]
        }
      },
      "xAxisReferenceLine": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "value": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value"
          ],
          "description": [
            "Set reference line numeric value"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set reference line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for reference line color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        },
        "position": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Position"
          ],
          "description": [
            "Arrange relative to chart data points"
          ]
        },
        "dataLabelShow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Data label"
          ],
          "description": [
            "Display a data label for the reference line"
          ]
        },
        "dataLabelColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set the reference line data label color"
          ]
        },
        "dataLabelDecimalPoints": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Decimal Places"
          ]
        },
        "dataLabelHorizontalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Horizontal Position"
          ],
          "description": [
            "Set the horizontal position for the reference line data label"
          ]
        },
        "dataLabelVerticalPosition": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Vertical Position"
          ],
          "description": [
            "Set the vertical position for the reference line data label"
          ]
        },
        "dataLabelDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        }
      },
      "fillPoint": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        }
      },
      "colorByCategory": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        }
      },
      "plotAreaShading": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "upperShadingColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Upper shading"
          ],
          "description": [
            "Shading color of the upper region"
          ]
        },
        "lowerShadingColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Lower shading"
          ],
          "description": [
            "Shading color of the lower region"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for background color"
          ]
        }
      },
      "ratioLine": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "lineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ],
          "description": [
            "Set reference line color"
          ]
        },
        "transparency": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Transparency"
          ],
          "description": [
            "Set transparency for line color"
          ]
        },
        "style": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Line style"
          ]
        }
      },
      "grid": {
        "outlineColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Outline color"
          ],
          "description": [
            "Color of the outline"
          ]
        },
        "outlineWeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Outline weight"
          ],
          "description": [
            "Thickness of the outline in pixels"
          ]
        },
        "gridVertical": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Vert grid"
          ],
          "description": [
            "Show/Hide the vertical gridlines"
          ]
        },
        "gridVerticalColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Vert grid color"
          ],
          "description": [
            "Color for the vertical gridlines"
          ]
        },
        "gridVerticalWeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Vert grid thickness"
          ],
          "description": [
            "Thickness of the vertical gridlines in pixels"
          ]
        },
        "gridHorizontal": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Horiz grid"
          ],
          "description": [
            "Show/Hide the horizontal gridlines"
          ]
        },
        "gridHorizontalColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Horiz grid color"
          ],
          "description": [
            "Color for the horizontal gridlines"
          ]
        },
        "gridHorizontalWeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Horiz grid thickness"
          ],
          "description": [
            "Thickness of the horizontal gridlines in pixels"
          ]
        },
        "rowPadding": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Row padding"
          ],
          "description": [
            "Padding in pixels applied to top and bottom of every row"
          ]
        },
        "imageHeight": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Image height"
          ],
          "description": [
            "The height of images in pixels"
          ]
        },
        "textSize": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Text Size"
          ]
        }
      },
      "columnHeaders": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the cells"
          ]
        },
        "wordWrap": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Word wrap"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "autoSizeColumnWidth": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Auto-size column width"
          ]
        },
        "urlIcon": {
          "type": [
            "bool"
          ],
          "displayName": [
            "URL icon"
          ],
          "description": [
            "Show an icon instead of the full URL"
          ]
        }
      },
      "values": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color scales"
          ]
        },
        "fontColorPrimary": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the odd rows"
          ]
        },
        "backColorPrimary": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the odd rows"
          ]
        },
        "fontColorSecondary": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Alternate font color"
          ],
          "description": [
            "Font color of the even rows"
          ]
        },
        "backColorSecondary": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Alternate background color"
          ],
          "description": [
            "Background color of the even rows"
          ]
        },
        "urlIcon": {
          "type": [
            "bool"
          ],
          "displayName": [
            "URL icon"
          ],
          "description": [
            "Show an icon instead of the full URL"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "wordWrap": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Word wrap"
          ]
        },
        "bandedRowHeaders": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Banded row style"
          ],
          "description": [
            "Apply banded row style to the last level of the row group headers, using the colors of the values."
          ]
        },
        "valuesOnRow": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show on rows"
          ],
          "description": [
            "Show values in row groups rather than columns"
          ]
        }
      },
      "total": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the cells"
          ]
        },
        "applyToHeaders": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Apply to labels"
          ]
        },
        "totals": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Totals"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        }
      },
      "columnFormatting": {
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the cells"
          ]
        },
        "styleHeader": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Color header"
          ]
        },
        "styleValues": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Color values"
          ]
        },
        "styleTotal": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Color total"
          ]
        },
        "styleSubtotals": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Color subtotals"
          ]
        }
      },
      "rowHeaders": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the cells"
          ]
        },
        "wordWrap": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Word wrap"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "stepped": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Stepped layout"
          ],
          "description": [
            "Render row headers with stepped layout"
          ]
        },
        "steppedLayoutIndentation": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Stepped layout indentation"
          ],
          "description": [
            "Set the indentation, in pixels, applied to row headers"
          ]
        },
        "urlIcon": {
          "type": [
            "bool"
          ],
          "displayName": [
            "URL icon"
          ],
          "description": [
            "Show an icon instead of the full URL"
          ]
        }
      },
      "subTotals": {
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "backColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background color"
          ],
          "description": [
            "Background color of the cells"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "fontSize": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "rowSubtotals": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Total row"
          ]
        },
        "columnSubtotals": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Total column"
          ]
        },
        "applyToHeaders": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Apply to labels"
          ]
        }
      },
      "selection": {
        "selectAllCheckboxEnabled": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Select All"
          ]
        },
        "singleSelect": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Single Select"
          ]
        }
      },
      "header": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "background": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background"
          ]
        },
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "textSize": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "items": {
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "background": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background"
          ]
        },
        "outline": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Outline"
          ]
        },
        "textSize": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        }
      },
      "numericInputStyle": {
        "fontColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Font color"
          ],
          "description": [
            "Font color of the cells"
          ]
        },
        "textSize": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Text Size"
          ]
        },
        "fontFamily": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Font family"
          ]
        },
        "background": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Background"
          ]
        }
      },
      "slider": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        },
        "color": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Color"
          ]
        }
      },
      "dateRange": {
        "includeToday": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Include today"
          ]
        }
      },
      "sentimentColors": {
        "increaseFill": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Increase"
          ]
        },
        "decreaseFill": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Decrease"
          ]
        },
        "totalFill": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Total"
          ]
        },
        "otherFill": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Other"
          ]
        }
      },
      "breakdown": {
        "maxBreakdowns": {
          "type": [
            "integer"
          ],
          "displayName": [
            "Max breakdowns"
          ],
          "description": [
            "The number of individual breakdowns to show (rest grouped into Other)"
          ]
        }
      },
      "indicator": {
        "indicatorDisplayUnits": {
          "type": [
            "formatting"
          ],
          "displayName": [
            "Display units"
          ],
          "description": [
            "Select the units (millions, billions, etc.)"
          ]
        },
        "indicatorPrecision": {
          "type": [
            "numeric"
          ],
          "displayName": [
            "Value decimal places"
          ],
          "description": [
            "Select the number of decimal places to display for the values"
          ]
        },
        "kpiFormat": {
          "type": [
            "text"
          ],
          "displayName": [
            "Format"
          ]
        }
      },
      "trendline": {
        "show": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Show"
          ]
        }
      },
      "goals": {
        "showGoal": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Goal"
          ]
        },
        "showDistance": {
          "type": [
            "bool"
          ],
          "displayName": [
            "Distance"
          ]
        }
      },
      "status": {
        "direction": {
          "type": [
            "enumeration"
          ],
          "displayName": [
            "Direction"
          ]
        },
        "goodColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Good Color"
          ]
        },
        "neutralColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Neutral Color"
          ]
        },
        "badColor": {
          "type": [
            "fill"
          ],
          "displayName": [
            "Bad Color"
          ]
        }
      }
```



### <a name="enumerations-in-the-json-file"></a>Luetteloinnit JSON-tiedostossa
Seuraavassa osiossa määritetään luetteloinnit, joita voit käyttää JSON-tiedostossa.

```json
    {
        "legend": {
            "position": [
                {
                    "value": "Top",
                    "displayName": "Top"
                },
                {
                    "value": "Bottom",
                    "displayName": "Bottom"
                },
                {
                    "value": "Left",
                    "displayName": "Left"
                },
                {
                    "value": "Right",
                    "displayName": "Right"
                },
                {
                    "value": "TopCenter",
                    "displayName": "Top Center"
                },
                {
                    "value": "BottomCenter",
                    "displayName": "Bottom Center"
                },
                {
                    "value": "LeftCenter",
                    "displayName": "Left Center"
                },
                {
                    "value": "RightCenter",
                    "displayName": "Right center"
                }
            ],
            "legendMarkerRendering": [
                {
                    "value": "markerOnly",
                    "displayName": "Markers only"
                },
                {
                    "value": "lineAndMarker",
                    "displayName": "Line and markers"
                },
                {
                    "value": "lineOnly",
                    "displayName": "Line only"
                }
            ]
        },
        "categoryAxis": {
            "axisScale": [
                {
                    "value": "linear",
                    "displayName": "Linear"
                },
                {
                    "value": "log",
                    "displayName": "Log"
                }
            ],
            "axisType": [
                {
                    "value": "Scalar",
                    "displayName": "Continuous"
                },
                {
                    "value": "Categorical",
                    "displayName": "Categorical"
                }
            ],
            "axisStyle": [
                {
                    "value": "showTitleOnly",
                    "displayName": "Show title only"
                },
                {
                    "value": "showUnitOnly",
                    "displayName": "Show unit only"
                },
                {
                    "value": "showBoth",
                    "displayName": "Show both"
                }
            ],
            "gridlineStyle": [
                {
                    "value": "dashed",
                    "displayName": "Dashed"
                },
                {
                    "value": "solid",
                    "displayName": "Solid"
                },
                {
                    "value": "dotted",
                    "displayName": "Dotted"
                }
            ],
            "position": [
                {
                    "value": "Left",
                    "displayName": "Left"
                },
                {
                    "value": "Right",
                    "displayName": "Right"
                }
            ]
        },
        "valueAxis": {
            "position": [
                {
                    "value": "Left",
                    "displayName": "Left"
                },
                {
                    "value": "Right",
                    "displayName": "Right"
                }
            ],
            "axisScale": [
                {
                    "value": "linear",
                    "displayName": "Linear"
                },
                {
                    "value": "log",
                    "displayName": "Log"
                }
            ],
            "axisStyle": [
                {
                    "value": "showTitleOnly",
                    "displayName": "Show title only"
                },
                {
                    "value": "showUnitOnly",
                    "displayName": "Show unit only"
                },
                {
                    "value": "showBoth",
                    "displayName": "Show both"
                }
            ],
            "gridlineStyle": [
                {
                    "value": "dashed",
                    "displayName": "Dashed"
                },
                {
                    "value": "solid",
                    "displayName": "Solid"
                },
                {
                    "value": "dotted",
                    "displayName": "Dotted"
                }
            ],
            "secPosition": [
                {
                    "value": "Left",
                    "displayName": "Left"
                },
                {
                    "value": "Right",
                    "displayName": "Right"
                }
            ],
            "secAxisScale": [
                {
                    "value": "linear",
                    "displayName": "Linear"
                },
                {
                    "value": "log",
                    "displayName": "Log"
                }
            ],
            "secAxisStyle": [
                {
                    "value": "showTitleOnly",
                    "displayName": "Show title only"
                },
                {
                    "value": "showUnitOnly",
                    "displayName": "Show unit only"
                },
                {
                    "value": "showBoth",
                    "displayName": "Show both"
                }
            ]
        },
        "lineStyles": {
            "strokeLineJoin": [
                {
                    "value": "miter",
                    "displayName": "Miter"
                },
                {
                    "value": "round",
                    "displayName": "Round"
                },
                {
                    "value": "bevel",
                    "displayName": "Bevel"
                }
            ],
            "lineStyle": [
                {
                    "value": "dashed",
                    "displayName": "Dashed"
                },
                {
                    "value": "solid",
                    "displayName": "Solid"
                },
                {
                    "value": "dotted",
                    "displayName": "Dotted"
                }
            ],
            "markerShape": [
                {
                    "value": "circle",
                    "displayName": "●"
                },
                {
                    "value": "square",
                    "displayName": "■"
                },
                {
                    "value": "diamond",
                    "displayName": "◆"
                },
                {
                    "value": "triangle",
                    "displayName": "▲"
                },
                {
                    "value": "x",
                    "displayName": "☓"
                },
                {
                    "value": "shortDash",
                    "displayName": " -"
                },
                {
                    "value": "longDash",
                    "displayName": "—"
                },
                {
                    "value": "plus",
                    "displayName": "+"
                }
            ]
        },
        "trend": {
            "style": [
                {
                    "value": "dashed",
                    "displayName": "Dashed"
                },
                {
                    "value": "solid",
                    "displayName": "Solid"
                },
                {
                    "value": "dotted",
                    "displayName": "Dotted"
            }
        ]
    },
    "y1AxisReferenceLine": {
        "style": [
            {
                "value": "dashed",
                "displayName": "Dashed"
            },
            {
                "value": "solid",
                "displayName": "Solid"
            },
            {
                "value": "dotted",
                "displayName": "Dotted"
            }
        ],
        "position": [
            {
                "value": "back",
                "displayName": "Behind"
            },
            {
                "value": "front",
                "displayName": "In Front"
            }
        ],
        "dataLabelText": [
            {
                "value": "Value",
                "displayName": "Value"
            },
            {
                "value": "Name",
                "displayName": "Name"
            },
            {
                "value": "ValueAndName",
                "displayName": "Name and Value"
            }
        ],
        "dataLabelHorizontalPosition": [
            {
                "value": "left",
                "displayName": "Left"
            },
            {
                "value": "right",
                "displayName": "Right"
            }
        ],
        "dataLabelVerticalPosition": [
            {
                "value": "above",
                "displayName": "Above"
            },
            {
                "value": "under",
                "displayName": "Under"
            }
        ]
    },
    "referenceLine": {
        "style": [
            {
                "value": "dashed",
                "displayName": "Dashed"
            },
            {
                "value": "solid",
                "displayName": "Solid"
            },
            {
                "value": "dotted",
                "displayName": "Dotted"
            }
        ],
        "position": [
            {
                "value": "back",
                "displayName": "Behind"
            },
            {
                "value": "front",
                "displayName": "In Front"
            }
        ],
        "dataLabelText": [
      {
        "value": "Value",
        "displayName": "Value"
      },
      {
        "value": "Name",
        "displayName": "Name"
      },
      {
        "value": "ValueAndName",
        "displayName": "Name and Value"
      }
    ],
    "dataLabelHorizontalPosition": [
      {
        "value": "left",
        "displayName": "Left"
      },
      {
        "value": "right",
        "displayName": "Right"
      }
    ],
    "dataLabelVerticalPosition": [
      {
        "value": "above",
        "displayName": "Above"
      },
      {
        "value": "under",
        "displayName": "Under"
      }
    ]
    },
    "labels": {
    "labelOrientation": [
      {
        "value": "vertical",
        "displayName": "Vertical"
      },
      {
        "value": "horizontal",
        "displayName": "Horizontal"
      }
    ],
    "labelPosition": [
      {
        "value": "Auto",
        "displayName": "Auto"
      },
      {
        "value": "InsideEnd",
        "displayName": "Inside End"
      },
      {
        "value": "OutsideEnd",
        "displayName": "Outside End"
      },
      {
        "value": "InsideCenter",
        "displayName": "Inside Center"
      },
      {
        "value": "InsideBase",
        "displayName": "Inside Base"
      }
    ],
    "labelStyle": [
      {
        "value": "Category",
        "displayName": "Category"
      },
      {
        "value": "Data",
        "displayName": "Data value"
      },
      {
        "value": "Percent of total",
        "displayName": "Percent of total"
      },
      {
        "value": "Both",
        "displayName": "Category, data value"
      },
      {
        "value": "Category, percent of total",
        "displayName": "Category, percent of total"
      },
      {
        "value": "Data value, percent of total",
        "displayName": "Data value, percent of total"
      },
      {
        "value": "Category, data value, percent of total",
        "displayName": "All detail labels"
      }
     ]
    },
    "card": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
         ]
    },
    "imageScaling": {
        "imageScalingType": [
          {
            "value": "Normal",
            "displayName": "Normal"
          },
          {
            "value": "Fit",
            "displayName": "Fit"
          },
          {
            "value": "Fill",
            "displayName": "Fill"
          }
        ]
    },
    "forecast": {
        "confidenceBandStyle": [
          {
            "value": "fill",
            "displayName": "Fill"
          },
          {
            "value": "line",
            "displayName": "Line"
          },
          {
            "value": "none",
            "displayName": "None"
          }
        ],
        "style": [
          {
            "value": "dashed",
            "displayName": "Dashed"
          },
          {
            "value": "solid",
            "displayName": "Solid"
          },
          {
            "value": "dotted",
            "displayName": "Dotted"
          }
        ]
        },
        "mapStyles": {
        "mapTheme": [
          {
            "value": "aerial",
            "displayName": "Aerial"
          },
          {
            "value": "canvasDark",
            "displayName": "Dark"
          },
          {
            "value": "canvasLight",
            "displayName": "Light"
          },
          {
            "value": "grayscale",
            "displayName": "Grayscale"
          },
          {
            "value": "road",
            "displayName": "Road"
          }
        ]
    },
    "shape": {
        "projectionEnum": [
          {
            "value": "albersUsa",
            "displayName": "Albers USA"
          },
          {
            "value": "equirectangular",
            "displayName": "Equirectangular"
          },
          {
            "value": "mercator",
            "displayName": "Mercator"
          },
          {
            "value": "orthographic",
            "displayName": "Orthographic"
          }
        ]
        },
        "xAxisReferenceLine": {
        "style": [
          {
            "value": "dashed",
            "displayName": "Dashed"
          },
          {
            "value": "solid",
            "displayName": "Solid"
          },
          {
            "value": "dotted",
            "displayName": "Dotted"
          }
        ],
        "position": [
          {
            "value": "back",
            "displayName": "Behind"
          },
          {
            "value": "front",
            "displayName": "In Front"
          }
        ],
        "dataLabelText": [
          {
            "value": "Value",
            "displayName": "Value"
          },
          {
            "value": "Name",
            "displayName": "Name"
          },
          {
            "value": "ValueAndName",
            "displayName": "Name and Value"
          }
        ],
        "dataLabelHorizontalPosition": [
          {
            "value": "left",
            "displayName": "Left"
          },
          {
            "value": "right",
            "displayName": "Right"
          }
        ],
        "dataLabelVerticalPosition": [
          {
            "value": "above",
            "displayName": "Above"
          },
          {
            "value": "under",
            "displayName": "Under"
          }
        ]
        },
        "ratioLine": {
        "style": [
          {
            "value": "dashed",
            "displayName": "Dashed"
          },
          {
            "value": "solid",
            "displayName": "Solid"
          },
          {
            "value": "dotted",
            "displayName": "Dotted"
          }
        ]
        },
        "columnHeaders": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "values": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "total": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "rowHeaders": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "subTotals": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ],
        "rowSubtotalsPosition": [
          {
            "value": "Top",
            "displayName": "Top"
          },
          {
            "value": "Bottom",
            "displayName": "Bottom"
          }
        ]
        },
        "general": {
        "orientation": [
          {
            "value": "vertical",
            "displayName": "Vertical"
          },
          {
            "value": "horizontal",
            "displayName": "Horizontal"
          }
        ]
        },
        "data": {
        "relativeRange": [
          {
            "value": "Last",
            "displayName": "Last"
          },
          {
            "value": "Next",
            "displayName": "Next"
          },
          {
            "value": "This",
            "displayName": "This"
          }
        ],
        "relativePeriod": [
          {
            "value": "None",
            "displayName": "Select"
          },
          {
            "value": "Days",
            "displayName": "Days"
          },
          {
            "value": "Weeks",
            "displayName": "Weeks"
          },
          {
            "value": "Calendar Weeks",
            "displayName": "Weeks (Calendar)"
          },
          {
            "value": "Months",
            "displayName": "Months"
          },
          {
            "value": "Calendar Months",
            "displayName": "Months (Calendar)"
          },
          {
            "value": "Years",
            "displayName": "Years"
          },
          {
            "value": "Calendar Years",
            "displayName": "Years (Calendar)"
          }
        ],
        "mode": [
          {
            "value": "Between",
            "displayName": "Between"
          },
          {
            "value": "Before",
            "displayName": "Before"
          },
          {
            "value": "After",
            "displayName": "After"
          },
          {
            "value": "Basic",
            "displayName": "List"
          },
          {
            "value": "Dropdown",
            "displayName": "Dropdown"
          },
          {
            "value": "Relative",
            "displayName": "Relative"
          },
          {
            "value": "Single",
            "displayName": "Single Value"
          }
        ]
        },
        "header": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "items": {
        "outline": [
          {
            "value": "None",
            "displayName": "None"
          },
          {
            "value": "BottomOnly",
            "displayName": "Bottom only"
          },
          {
            "value": "TopOnly",
            "displayName": "Top only"
          },
          {
            "value": "LeftOnly",
            "displayName": "Left only"
          },
          {
            "value": "RightOnly",
            "displayName": "Right only"
          },
          {
            "value": "TopBottom",
            "displayName": "Top + bottom"
          },
          {
            "value": "LeftRight",
            "displayName": "Left + right"
          },
          {
            "value": "Frame",
            "displayName": "Frame"
          }
        ]
        },
        "status": {
        "direction": [
          {
            "value": "Positive",
            "displayName": "High is good"
          },
          {
            "value": "Negative",
            "displayName": "Low is good"
          }
         ]
       }
    }
  }
}
```

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Jos käytät yhtä alkuperäisistä teemoistamme, eli Perinteinen-teemaa, tai mukautettua teemaa, jonka olet tuonut näiden lisäksi, teeman valintaikkunan tekstiosa ei ole saatavilla määritettäväksi.

Sisäisistä teemoista tämä rajoitus vaikuttaa seuraaviin:
* Perinteinen
* Kaupungin puisto
* Luokkahuone
* Turvallinen värisokeille
* Sähköinen
* Suuri kontrasti
* Auringonlasku
* Hämy

Jos käytät yhtä niistä teemoista, joihin tämä vaikuttaa, eikä sinun tarvitse muokata tekstiasetuksia, voit turvallisesti käyttää valintaikkunan muita välilehtiä ilman ongelmia. Mutta jos haluat käyttää tekstiluokkia yhden sellaisen teeman kanssa, johon tämä vaikuttaa, sinulla on pari vaihtoehtoa:

- Nopein ja helpoin tapa mahdollistaa tekstiluokat on valita teeman oletusasetukset.
- Jos haluat säilyttää nykyisen mukautetun teemasi, ota tekstivälilehti käyttöön:
  1. Vie nykyinen teema.
  1. Valitse oletusteema.
  1. Tuo mukautettu teema, jonka veit ensimmäisessä vaiheessa.

Raporttisi teksti näyttää erilaiselta, mutta pääset käyttämään tekstivälilehteä teeman valintaikkunassa.


