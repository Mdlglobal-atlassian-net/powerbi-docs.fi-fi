---
title: Osittajat Power BI:ssä (opetusohjelma)
description: 'Opetusohjelma: Osittajat Power BI:ssä'
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/05/2018
ms.author: v-thepet
LocalizationGroup: Visualizations
ms.openlocfilehash: cfa4c0f17c67a036b7d01744da1b5247345c493a
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/12/2018
ms.locfileid: "30975157"
---
# <a name="slicers-in-power-bi-tutorial"></a>Osittajat Power BI:ssä (opetusohjelma)
Myynnin varatoimitusjohtaja haluaa tarkastella useita tietoja koko yksiköstä ja kustakin yksittäisestä aluejohtajasta. Hän voi luoda erillisen raportin kustakin aluejohtajasta tai käyttää osittajaa. Osittajan avulla voit tarkentaa raportin muissa visualisoinneissa näkyvän tietojoukon osaa. Osittajat ovat vaihtoehtoinen suodatustapa.

Tässä opetusohjelmassa käytetään maksutonta [jälleenmyyntianalyysimallia](sample-retail-analysis.md) ja opit luomaan ja muotoilemaan osittajan sekä käyttämään sitä raportin suodattamiseen. Pidä hauskaa opetellessasi uusia tapoja muotoilla ja käyttää osittajia. 

![osittaja](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Osittajan käyttäminen
Osittajia kannattaa käyttää seuraavissa tilanteissa:

* Haluat helpottaa käyttöä näyttämällä usein käytettyjä tai tärkeitä suodattimia raportin piirtoalustassa.
* Haluat helpottaa nykyisen suodatetun tilan tarkastelua avaamatta avattavaa luetteloa. 
* Haluat käyttää suodatuksessa sarakkeita, jotka ovat tarpeettomia ja piilotettuina tietotaulukoissa.
* Haluat luoda tarkempia raportteja sijoittamalla osittajia tärkeiden visualisointien viereen.

Power BI -osittajia koskevat seuraavat rajoitukset:

- Osittajat eivät tue syöttökenttiä.
- Osittajia ei voi kiinnittää koontinäyttöön.
- Osittajat eivät tue porautumista.
- Osittajat eivät tue visuaalisen tason suodattimia.

## <a name="create-a-slicer"></a>Osittajan luominen

Tässä opetusohjelmassa käytetään luettelon osittajaa. Numeerisella tietotyypillä ja päivämäärä/aika-tietotyypillä voi olla alueen osittajia. Jos haluat lisätietoja alueen osittajien luomisesta ja käyttämisestä, lue artikkeli [Numeerisen alueen osittajan käyttö Power BI Desktopissa](desktop-slicer-numeric-range.md) tai katso seuraava video.
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>

1. Avaa [jälleenmyyntianalyysimalli](sample-retail-analysis.md) Power BI Desktopin tai Power BI -palvelun [muokkausnäkymässä](service-interact-with-a-report-in-editing-view.md) ja [lisää uusi raporttisivu](power-bi-report-add-page.md).
2. Luo uusi visualisointi valitsemalla Kentät-ruudun Alue-kohdasta **Aluejohtaja**.
    
    ![uusi kaavio](media/power-bi-visualization-slicers/1-new-vis.png)
    
3. Muuta uusi visualisointi osittajaksi valitsemalla Visualisoinnit-ruudusta **Osittaja**-kuvake ![osittajakuvake](media/power-bi-visualization-slicers/slicer-icon.png). 
    
    ![muuta osittajaksi](media/power-bi-visualization-slicers/2-slicer.png)

Voit myös luoda uuden osittajan valitsemalla Osittaja-kuvakkeen. Täytä sitten osittajan tiedot valitsemalla tietokenttä tai vetämällä tietokenttä Kenttä-ruutuun.

>[!TIP]
>Voit lajitella osittajan kohteita tietoarvojen mukaan. Jos haluat lajitella osittajan kohteita käänteisessä aakkosjärjestyksessä, valitse osittajan oikeasta yläkulmasta kolmen pisteen symboli (...) ja valitse **lajitteluperusteeksi aluejohtaja**. Tämä asetus on oletusarvon mukaan nousevassa aakkosjärjestyksessä, mutta järjestystä voi vaihtaa nousevan ja laskevan välillä. 

## <a name="format-the-slicer"></a>Osittajan muotoileminen
Käytä visuaalista muotoilua Aluejohtaja-osittajaan.
1. Kun olet valinnut osittajan, tuo muotoiluasetukset näkyviin valitsemalla Visualisoinnit-ruudusta Muotoile-kuvake ![](media/power-bi-visualization-slicers/power-bi-paintroller.png). 
    
    ![muotoilu](media/power-bi-visualization-slicers/3-format.png)
    
2. Voit katsella ja muokata asetuksia napsauttamalla kunkin luokan vieressä olevaa avattavan valikon nuolta. 

### <a name="general-options"></a>Yleiset asetukset
1. Valitse **Ääriviivan väri** -kohdasta punainen ja muuta **Ääriviivan paksuus** -arvoksi 2. Tämä määrittää otsikon ja kohteen ääriviivojen ja alleviivausten värin ja paksuuden, jos käytössä. 
2. Suunta-kohdassa oletusarvona on Pystysuora. Tämä luo pystysuuntaisen luettelon osittajan, jossa on kohteiden edessä valintaruutuja. Valitse **Vaakasuora**, jos haluat luoda osittajan, jossa on vaakasuoraan aseteltuja kohteita. Vaakasuunnan avulla voit luoda erilaisia tekstin, painikkeiden tai ruutujen asetteluja osittajan koon ja muodon sekä kohteen muotoilun mukaan. 
    
    ![vaakasuora](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. Ota käyttöön **reagoiva** asettelu, joka muuttaa vaakasuuntaisten osittajan kohteiden kokoa ja asettelua niin, että ne vastaavat osittajan kokoa ja muotoa. Kun osittaja on erittäin pieni, se muuttuu suodatinkuvakkeeksi. 
    
    ![reagoiva](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >Reagoivan asettelun muutokset saattavat ohittaa määrittämäsi tietyn otsikon ja kohteen muotoilun. 
    
4. Määritä osittajan sijainti ja koko numerotarkkuudella **X-sijainti**-, **Y-sijainti**-, **Leveys**- ja **Korkeus**-kohdissa tai siirrä osittaja suoraan piirtoalustalle ja muuta sen kokoa sekä luo erikokoisia kohteita ja asetteluita, kuten vaakasuuntainen painikerivi. 

    ![vaakasuuntaiset painikkeet](media/power-bi-visualization-slicers/6-buttons.png)

Artikkelissa [Kooltaan muokattavan reagoivan osittajan luominen Power BI:ssä](power-bi-slicer-filter-responsive.md) on lisätietoja vaaka-asettelusta ja reagoivasta muotoilusta.

### <a name="selection-controls-options"></a>Valinnan hallinta -asetukset
1. Näytä Valitse kaikki -asetus on oletusarvon mukaan poistettu käytöstä. Ota asetus käyttöön siirtämällä sen valintakytkin **Käytössä**-asentoon, jos haluat lisätä osittajaan Valitse kaikki -kohteen, jonka avulla voit valita kaikki kohteet tai poistaa niiden valinnan. Kun kaikki kohteet ovat valittuina, yhden kohteen napsauttaminen poistaa sen valinnan, mikä sallii ei-ole-tyypin suodattimen. 
    
    ![valitse kaikki](media/power-bi-visualization-slicers/7-select-all.png)
    
2. Yksittäinen valinta on oletusarvon mukaan käytössä. Voit valita yhden kohteen napsauttamalla kyseistä kohdetta ja useita kohteita painamalla CTRL-painiketta samalla kun napsautat valittavia kohteita. Kun siirrät Yksittäinen valinta -asetuksen valintakytkimen **Ei käytössä** -asentoon, voit valita useita kohteita painamatta Ctrl-painiketta pitkään. Voit poistaa kohteen valinnan napsauttamalla sitä uudelleen. 

### <a name="header-options"></a>Otsikko-asetukset
Otsikko on oletusarvon mukaan käytössä. Otsikko sisältää tietokentän nimen ja näkyy osittajan yläreunassa. 
1. Muotoile otsikon tekstiä valitsemalla **fontin väriksi** punainen, **tekstin kooksi** 14 pt ja **fonttiperheeksi** Arial Black. 
2. Valitse Alleviivattu-kohdasta **Vain alhaalla**, jos haluat lisätä alleviivauksen yleisissä asetuksissa määrittämälläsi koolla ja värillä. 

### <a name="item-options"></a>Kohteet-asetukset
1. Muotoile kohteen tekstiä ja taustaa valitsemalla **fontin väriksi** musta, **taustaksi** vaaleanpunainen, **tekstin kooksi** 10 pt ja **fonttiperheeksi** Arial. 
2. Valitse Alleviivattu-kohdasta **Kehys**, jos haluat piirtää kunkin kohteen ympärille reunuksen yleisissä asetuksissa määrittämälläsi koolla ja värillä. 
    
    ![muotoiltu](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- Kun valittuna on vaakasuunta, valitsemattomissa kohteissa käytetään valittua tekstiä ja taustavärejä ja valituissa kohteissa käytetään järjestelmäoletusta, jolloin tausta on yleensä musta ja teksti valkoinen. 
    >- Kun valittuna on pystysuunta, kohteissa käytetään aina määritettyjä värejä ja valittuna olevat valintaruudut ovat aina mustia. 

### <a name="other-formatting-options"></a>Muut muotoiluasetukset
Muut muotoiluasetukset eivät ole oletusarvon mukaan käytössä. Kun **Käytössä**: 
- **Nimi:** Lisää ja muotoilee osittajan yläreunassa olevan nimen (otsikon lisäksi ja siitä riippumatta). 
- **Tausta:** Lisää taustavärin yleiseen osittajaan ja määrittää sen läpinäkyvyyden.
- **Lukitse kuvasuhde:** Säilyttää osittajan muodon, jos sen kokoa muutetaan.
- **Reunus:** Lisää yhden pikselin reunuksen osittajan ympärille ja määrittää sen värin. (Tämä osittajan reunus on eri kuin yleisissä ääriviiva-asetuksissa määritetty reunus, ja yleisissä ääriviiva-asetuksissa määritetty reunus ei vaikuta tähän reunukseen.) 

## <a name="sync-and-use-the-slicer-on-other-pages"></a>Osittajan synkronoiminen ja käyttäminen muilla sivuilla
Vuoden 2018 helmikuun Power BI -päivityksestä alkaen voit synkronoida osittajan ja käyttää sitä millä tahansa tai kaikilla raportin sivuilla. 
1. Kun valittuna on Aluejohtaja-osittaja, valitse Power BI Desktopin Näytä-valikosta **Synkronoi osittajat** ja ota käyttöön **Synkronoi osittajaruutu** Power BI -palvelussa. Synkronoi osittajat -ruutu avautuu. 
    
    ![synkronoi osittajat](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
2. Valitse ensimmäisestä sarakkeesta **Yleiskatsaus** ja kaikki muut sivut, joilla haluat synkronoida osittajan, tai napsauta **Lisää kaikkiin**, jos haluat synkronoida osittajan kaikilla raportin sivuilla.  
3. Valitse seuraavasta sarakkeesta **Yleiskatsaus** ja kaikki muut sivut, joilla haluat osittajan näkyvän. 
4. Siirry **Yleiskatsaus**-sivulle ja kiinnitä huomiota osittajaan ja sen vaikutuksiin muissa sivun visualisoinneissa. 
    - Valitse eri kohteita ja poista eri kohteiden valintoja ja kiinnitä huomiota siihen, miten muut sivulla olevat visualisoinnit muuttuvat näiden valintojen mukaan. Kohteen valitseminen millä tahansa sivulla näkyy kaikilla synkronoiduilla sivuilla.
    - Muuta osittajan kokoa, muotoa, sijaintia tai muotoilua Yleiskatsaus-sivulla. Osittajan muotoilu ei muutu muilla synkronoiduilla sivuilla. 

### <a name="control-which-page-visuals-are-affected-by-the-slicer"></a>Niiden sivujen määrittäminen, joilla osittajaan tehdyt muutokset näkyvät
Oletusarvon mukaan raporttisivulla olevan osittajan muutokset näkyvät kyseisen sivun kaikissa visualisoinneissa. Estä osittajaan tehtyjen muutosten näkyminen joissakin sivun visualisoinneissa käyttämällä **Visuaaliset vuorovaikutukset** -asetusta.

1. Tee seuraavat toimet **Yleiskatsaus**-sivulla, jolla osittaja on valittuna:
    - Napsauta Power BI Desktopissa Visualisointityökalut-kohdan Muotoile-valikosta **Muokkaa vuorovaikutuksia**.
    - Avaa Power BI -palvelun valikkoriviltä **Visuaaliset vuorovaikutukset** ja ota käyttöön **Muokkaa vuorovaikutuksia**. 
    
    Suodatinasetukset näkyvät kaikkien muiden sivulla olevien visualisointien yläpuolella. ![suodatinasetukset](media/power-bi-visualization-slicers/filter-controls.png)
    
2. Valitse visualisoinnin yläpuolelta **Ei mitään** -kuvake, jos haluat, että osittaja lopettaa visualisoinnin suodattamisen. Valitse **Suodata**-kuvake, jos haluat, että osittaja aloittaa visualisoinnin suodattamisen uudelleen. 

Lisätietoja vuorovaikutusten muokkaamisesta on artikkelissa [Visuaaliset vuorovaikutukset Power BI -raportissa](service-reports-visual-interactions.md).

## <a name="next-steps"></a>Seuraavat vaiheet
[Kokeile sitä – se on maksuton!](https://powerbi.com/)

Onko sinulla ideoita Power BI:n parantamiseksi? [Lähetä idea](https://ideas.powerbi.com/forums/265200-power-bi-ideas).

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

[Visualisoinnin lisääminen raporttiin](power-bi-report-add-visualizations-i.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

