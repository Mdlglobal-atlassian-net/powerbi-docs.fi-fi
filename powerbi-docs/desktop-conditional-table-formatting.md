---
title: Ehdollinen taulukkomuotoilu Power BI Desktopissa
description: Mukautetun muotoilun käyttö taulukoissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/26/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: c79a8ddd68fa64b0a16663500a3f02e9a991835b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "75730322"
---
# <a name="use-conditional-formatting-in-tables"></a>Ehdollisen muotoilun käyttäminen taulukoissa 

Power BI Desktopin taulukoiden ehdollisen muotoilun avulla voit määrittää mukautettuja solujen värejä kenttien arvoihin perustuen. Voit käyttää myös liukuvärejä. Voit myös kuvata solujen arvoja tietopalkkien tai suorituskykyilmaisinkuvakkeiden avulla tai aktiivisina verkkolinkkeinä. Voit käyttää ehdollista muotoilua mihin tahansa teksti- tai tietokenttään, kunhan perustat muotoilun kenttään, jolla on numero-, väri- tai heksadesimaalikoodi tai URL-osoitearvot. 

Jos haluat käyttää ehdollista muotoilua, valitse Power BI Desktopissa **Taulukko**- tai **Matriisi**-visualisointi. Napsauta **Visualisoinnit**-ruudun **Kentät**-osassa hiiren kakkospainikkeella tai valitse muotoiltavan **Arvot**-lähteen kentän vieressä oleva alanuoli. Valitse **Ehdollinen muotoilu** ja valitse sitten käytettävä muotoilutyyppi.

![Ehdollinen muotoilu -valikko](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

> [!NOTE]
> Ehdollinen muotoilu ohittaa mukautetun taustan tai fontin värin, jota käytät ehdollisesti muotoilluissa soluissa.

Jos haluat poistaa ehdollisen muotoilun visualisoinnista, valitse **Poista ehdollinen muotoilu** kentän avattavasta valikosta ja valitse sitten poistettavan muotoilun tyyppi.

![Poista ehdollinen muotoilu -valikko](media/desktop-conditional-table-formatting/table-formatting-1-remove.png)

Seuraavissa osioissa kuvataan kutakin ehdollisen muotoilun vaihtoehtoa. Voit yhdistää useamman kuin yhden vaihtoehdon yksittäiseen taulukon sarakkeeseen.

## <a name="format-background-or-font-color"></a>Muotoile tausta tai fontin väri

Jos haluat muotoilla solun taustan tai fontin värin, valitse kentälle **ehdollinen muotoilu** ja valitse sitten avattavasta valikosta joko **Taustaväri** tai **Fontin väri**. 

![Taustavärin tai fontin värin valitseminen](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-dialog.png)

**Taustaväri**- tai **Fontin väri** -valintaikkuna avautuu, ja sen otsikossa on muotoilemasi kentän nimi. Kun olet valinnut ehdollisen muotoilun asetukset, valitse **OK**. 

![Taustaväri- ja Fontin väri -valintaikkunat](media/desktop-conditional-table-formatting/table-formatting-2-diverging.png)

**Taustaväri**- ja **Fontin väri** -asetukset ovat samat, mutta ne vaikuttavat solun taustaväriin ja fontin väriin. Voit käyttää samaa tai eri ehdollista muotoilua kentän fontin värissä ja taustavärissä. Jos teet kentän fontista ja taustasta samanväriset, fontti sulautuu taustaan, jolloin taulukon sarakkeessa näkyvät vain värit.

## <a name="color-by-color-scale"></a>Väri väriasteikon mukaan

Jos haluat muotoilla solun taustan tai fontin värin väriasteikon mukaan, valitse **Muotoiluperuste**-kentän **Taustaväri**- tai **Fontin väri** -valinta ikkunassa **Väriasteikko**. Valitse **Perustuu kenttään** -kohdassa kenttä, jolle haluat muotoilun perustuvan. Voit perustaa muotoilun nykyiseen kenttään tai mallin mihin tahansa kenttään, jolla on numeeriset tiedot tai väritiedot. 

Määritä **Yhteenveto**-kohdassa koostamistyyppi, jota haluat käyttää valitussa kentässä. Valitse **Oletusmuotoilu**-kohdassa muotoilu, jota käytetään tyhjille arvoille. 

Valitse **Pienin arvo**- ja **Suurin arvo** -kohdissa, käytetäänkö värimallia pienimmän ja suurimman kenttäarvon perusteella vai antamissasi mukautetuissa arvoissa. Valitse avattavasta valikosta väriruudut, joita haluat käyttää vähimmäis- ja enimmäisarvoissa. Valitse **Erkautuva**-valintaruutu, jos haluat määrittää myös **Keskipiste**-arvon ja -värin. 

![Solun taustan asettaminen väriasteikon avulla](media/desktop-conditional-table-formatting/table-formatting-1-diverging-table.png)

Esimerkkitaulukko, jossa tausta on muotoilu väriasteikon avulla **Affordability**-sarakkeessa, näyttää tältä:

![Esimerkkitaulukko, jossa on erkautuva taustaväriasteikko](media/desktop-conditional-table-formatting/table-formatting-1-apply-color-to.png)

Esimerkkitaulukko, jossa fontti on muotoilu väriasteikon avulla **Affordability**-sarakkeessa, näyttää tältä:

![Esimerkkitaulukko, jossa on erkautuva fonttiväriasteikko](media/desktop-conditional-table-formatting/table-formatting-2-table.png)

## <a name="color-by-rules"></a>Väri sääntöjen mukaan

Jos haluat muotoilla solun taustan tai fontin värin sääntöjen mukaan, valitse **Muotoiluperuste**-kentän **Taustaväri**- tai **Fontin väri** -valinta ikkunassa **Säännöt**. **Perustuu kenttään** näyttää jälleen kentän, johon muotoilu perustuu, ja **Yhteenveto** näyttää kentän koostamistyypin. 

Kirjoita **Säännöt**-kohtaan vähintään yksi tai useampi arvoalue ja määritä kullekin väri. Kukin arvo alkaa *Jos-arvo*-ehdolla, *ja*-arvoehdolla ja värillä. Kunkin arvoalueen solujen taustat tai fontit väritetään annetulla värillä. Seuraavassa esimerkissä on kolme sääntöä:

![Väri sääntöjen mukaan](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-if-value.png)

Esimerkkitaulukko, jossa tausta on muotoilu sääntöjen avulla **Affordability**-sarakkeessa, näyttää tältä:

![Esimerkkitaulukko, joka sisältää värin sääntöjen mukaan](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-table.png)

## <a name="color-by-color-values"></a>Väri väriarvojen mukaan

Jos sinulla on kenttä tai mittari, jossa on värin nimi- tai heksadesimaaliarvotietoja, voit käyttää ehdollista muotoilua, jotta nämä värit otetaan automaattisesti käyttöön sarakkeen taustassa tai fontin värissä. Voit myös käyttää mukautettua logiikkaa käyttääksesi värejä fontissa tai taustassa.

Kenttä voi käyttää mitä tahansa CSS-värimäärityksen väriarvoja, jotka on lueteltu sivulla [https://www.w3.org/TR/css-color-3/](https://www.w3.org/TR/css-color-3/). Näihin väriarvoihin kuuluvat seuraavat:
- 3-, 6- tai 8-numeroinen heksadesimaalikoodit, esimerkiksi #3E4AFF. Muista kirjoittaa #-symboli koodin alkuun. 
- RGB- tai RGBA-arvot, kuten RGBA (234, 234, 234, 0.5).
- HSL- tai HSLA-arvot, kuten HSLA (123, 75%, 75%, 0.5).
- Värien nimet, kuten vihreä, taivaansininen tai persikka. 

Seuraavassa taulukossa on kuhunkin osavaltioon liittyvä värin nimi: 

![Osavaltiotaulukko, jossa on värien nimet](media/desktop-conditional-table-formatting/conditional-table-formatting_01.png)

Jos haluat muotoilla **Väri**-saraketta kentän arvojen perusteella, valitse **Väri**-kentälle **Ehdollinen muotoilu** ja valitse sitten **Taustaväri** tai **Fontin väri**. 

Valitse **Taustaväri**- tai **Fontin väri** -valintaikkunassa **Kentän arvo** avattavasta **Muotoiluperuste**-kentästä.

![Muotoiluperuste-kentän arvo](media/desktop-conditional-table-formatting/conditional-table-formatting_02.png)

Esimerkkitaulukko, jossa **taustaväri** on muotoilu värikentän arvon avulla **Väri**-sarakkeessa, näyttää tältä:

![Esimerkkitaulukko, jossa tausta on muotoilu kentän arvon mukaan](media/desktop-conditional-table-formatting/conditional-table-formatting_03.png)

Jos käytät myös **kentän arvoa** sarakkeen **fontin värin** muotoilemiseen, tuloksena on tasainen väri **Väri**-sarakkeessa:

![Taustan ja fontin muotoilu kentän arvon mukaan](media/desktop-conditional-table-formatting/conditional-table-formatting_04.png)

## <a name="color-based-on-a-calculation"></a>Väri laskennan perusteella

Voit luoda DAX-laskutoimituksen, joka tulostaa eri arvot valitsemiesi liiketoimintalogiikkaehtojen perusteella. DAX-kaavan luominen on yleensä nopeampaa kuin useiden sääntöjen luominen ehdollisen muotoilun valintaikkunassa. 

Esimerkiksi seuraava DAX-kaava käyttää heksadesimaaliväriarvoja uuteen **Affordability rank** -sarakkeeseen olemassa olevien **Affordability**-sarakearvojen perusteella:

![DAX-laskenta](media/desktop-conditional-table-formatting/conditional-table-formatting_05.png)

Jos haluat ottaa värit käyttöön, valitse **Taustaväri**- tai **Fontin väri**- ehdollinen muotoilu **Affordability**-sarakkeelle ja perusta muotoilu **Affordability rank** -sarakkeen **Kentän arvolle**. 

![Taustavärin perustaminen lasketulle sarakkeelle](media/desktop-conditional-table-formatting/conditional-table-formatting_06.png)

Esimerkkitaulukko, jossa **Affordability**-sarakkeen taustaväri perustuu laskettuun **Affordability rank** -sarakkeeseen, näyttää tältä:

![Esimerkkitaulukko, jossa on laskettuihin arvoihin perustuva väri](media/desktop-conditional-table-formatting/conditional-table-formatting_07.png)

Voit luoda monia muita variaatioita käyttämällä mielikuvitustasi ja joitakin DAX-laskutoimituksia.

## <a name="add-data-bars"></a>Tietopalkkien lisääminen

Jos haluat näyttää tietopalkit solujen arvojen perusteella, valitse **Affordability**-kentälle **Ehdollinen muotoilu** ja valitse sitten avattavasta valikosta **Tietopalkit**. 

**Näytä vain palkki** -asetusta ei ole oletuksena valittu **Tietopalkit**-valintaikkunassa, jolloin taulukkosolut näyttävät sekä palkit että todelliset arvot. Jos haluat näyttää vain tietopalkit, valitse **Näytä vain palkki** -valintaruutu.

Voit määrittää **pienimmän** ja **suurimman** arvon, tietopalkin värit ja suunnan sekä akselin värin. 

![Tietopalkit-valintaikkuna](media/desktop-conditional-table-formatting/table-formatting-3-default.png)

Kun tietopalkit ovat käytössä **Affordability**-sarakkeessa, esimerkkitaulukko näyttää tältä:

![Esimerkkitaulukko, jossa on tietopalkkeja](media/desktop-conditional-table-formatting/table-formatting-3-default-table-bars.png)

## <a name="add-icons"></a>Kuvakkeiden lisääminen

Jos haluat näyttää kuvakkeet solujen arvojen perusteella, valitse kentälle **Ehdollinen muotoilu** ja valitse sitten avattavasta valikosta **Kuvakkeet**. 

Valitse **Kuvakkeet**-valintaikkunan **Muotoiluperuste**-kohdassa joko **Säännöt** tai **Kentän arvo**. 

Jos haluat muotoilla sääntöjä, valitse **Perustuu kenttään**, **Yhteenveto**-menetelmä, **kuvakeasettelu**, **kuvakkeen tasaus**, kuvakkeen **tyyli** ja vähintään yksi **sääntö**. Kirjoita **Säännöt**-kohtaan vähintään yksi sääntö, jolla on *Jos-arvo*-ehto sekä *ja*-arvo-ehto, ja valitse kussakin säännössä käytettävä kuvake. 

Jos haluat muotoilla kentän arvojen mukaan, valitse **Perustuu kenttään**, **Yhteenveto**-menetelmä, **Kuvake asettelu** ja **Kuvakkeen tasaus**.

Seuraavassa esimerkissä kuvakkeita lisätään kolmen säännön perusteella:

![Kuvakkeet-valintaikkuna](media/desktop-conditional-table-formatting/table-formatting-1-default-table.png)

Valitse **OK**. Kun kuvakkeet ovat käytössä **Affordability**-sarakkeessa, esimerkkitaulukko näyttää tältä:

![Esimerkkitaulukko, jossa on kuvakkeita](media/desktop-conditional-table-formatting/table-formatting-1-default-dialog.png)

## <a name="format-as-web-urls"></a>Muotoileminen verkko-URL-osoitteina

Jos sinulla on sarake tai mittari, joka sisältää WWW-URL-osoitteita, voit käyttää ehdollista muotoilua käyttääksesi kyseisiä URL-osoitteita kentissä aktiivisina linkkeinä. Seuraavassa taulukossa on esimerkiksi **Verkkosivusto**-sarake, jossa on verkkosivuston URL-osoite kullekin osavaltiolle:

![Taulukko, jossa on WWW-URL-osoite-sarake](media/desktop-conditional-table-formatting/table-formatting-1-diverging.png)

Jos haluat näyttää kunkin osavaltion nimen linkkinä sen verkkosivustolle, valitse **State**-kentälle **Ehdollinen muotoilu** ja valitse sitten **URL-verkko-osoite**. Valitse **URL-verkko-osoite**-valintaikkunan kohdassa **Perustuu kenttään** **Verkkosivusto** ja valitse sitten **OK**. 

Kun **URL-verkko-osoite**-muotoilu on käytössä **State**-kentässä, kunkin osavaltion nimi on toimiva linkki osavaltion verkkosivustoon. Seuraavassa esimerkkitaulukossa **URL-verkko-osoite**-muotoilu on käytössä **State**-sarakkeessa ja ehdolliset **Tietopalkit** ja **Taustan muotoilu** ovat käytössä **Affordability**-sarakkeessa. 

![Taulukko, jossa on URL-verkko-osoite, tietopalkit ja taustaväri](media/desktop-conditional-table-formatting/table-formatting-3-default-table.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset
Sinun on huomioitava muutamia seikkoja, kun käsittelet ehdollista taulukkomuotoilua:

- Ehdollista muotoilua käytetään vain Taulukko- tai Matriisi-visualisointien arvoissa, eikä se koske välisummia, kokonaissummia tai **Summa**-riviä. 
- Mikä tahansa taulukko, jossa ei ole ryhmittelyä, näytetään yhtenä rivinä, joka ei tue ehdollista muotoilua.
- Et voi käyttää liukuvärimuotoa ja automaattisia enimmäis- ja vähimmäisarvoja tai sääntöpohjaista muotoilua prosenttisäännöillä, jos tiedot sisältävät *NaN*-arvoja. NaN on akronyymi sanoista ”Not a Number” eli suomeksi ”ei numero”. Niitä aiheuttavat yleensä nollalla jakamisen virheet. Voit välttää nämä virheet funktiolla [DIVIDE() DAX](https://docs.microsoft.com/dax/divide-function-dax).
- Ehdollisella muotoilulla on oltava kooste tai mittari, jotta sitä voidaan soveltaa arvoon. Tästä syystä **Väri arvon mukaan** -esimerkissä on "Ensimmäinen" tai "Viimeinen". Jos olet luomassa raporttiasi Analysis Servicen moniulotteisen kuution avulla, et voi käyttää määritettä ehdollista muotoilua varten, ellei kuution omistaja ole luonut mittaria, joka antaa arvon.

## <a name="next-steps"></a>Seuraavat vaiheet

Katso lisätietoja värien muotoilusta artikkelista [Vinkkejä värimuotoiluun Power BI:ssä](visuals/service-tips-and-tricks-for-color-formatting.md)  

