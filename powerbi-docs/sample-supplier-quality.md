---
title: 'Toimittajan laatuanalyysimalli Power BI:lle: aloita esittely'
description: 'Toimittajan laatuanalyysimalli Power BI:lle: aloita esittely'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/19/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 76e053d34dcd7f1f199f4cbf9f02196e8efc6232
ms.sourcegitcommit: ba95d4979f1869f49a7d266c591f95e2810fdb29
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/19/2019
ms.locfileid: "69621324"
---
# <a name="supplier-quality-analysis-sample-for-power-bi-take-a-tour"></a>Toimittajan laatuanalyysimalli Power BI:lle: aloita esittely

Tämä alan mallikoontinäyttö ja raportti keskittyvät yhteen tyypilliseen toimitusketjun ongelmaan eli toimittajalaatuanalyysiin. Tässä analyysissa on kaksi tärkeää arvoa: vikojen kokonaismäärä ja niiden aiheuttamisen käyttökatkojen kokonaisaika. 

Tällä esimerkillä on kaksi päätavoitetta:

* laadultaan parhaiden ja huonoimpien toimittajien selvittäminen
* vikoja parhaiten löytävien ja hylkäävien toimipisteiden selvittäminen käyttökatkoajan pienentämiseksi.

![Koontinäyttö toimittajan laatuanalyysimallille](media/sample-supplier-quality/supplier1.png)

Tämä malli kuuluu sarjaan, jossa esitellään, miten Power BI:tä voidaan käyttää liiketoimintaan suuntautuneiden tietojen, raporttien ja koontinäyttöjen kanssa. [ObviEnce](http://www.obvience.com/) on luonut sen käyttämällä oikeita tietoja, jotka on muunnettu nimettömään muotoon. Tiedot ovat käytettävissä useissa muodoissa: sisältöpaketti, Power BI Desktopin .pbix-tiedosto tai Excel-työkirja. Tutustu [Power BI:n malleihin](sample-datasets.md). 

Tässä opetusohjelmassa tutustutaan Power BI -palvelun toimittajan laatuanalyysimallin sisältöpakettiin. Koska raportin käyttökokemus on hyvin samankaltainen Power BI Desktopissa ja palvelussa, voit seurata ohjelmaa myös käyttämällä Power BI Desktopin mallin .pbix-tiedostoa. 

Et tarvitse Power BI -käyttöoikeutta Power BI Desktopin malleihin tutustumiseen. Jos sinulla ei ole Power BI Pro -käyttöoikeutta, voit tallentaa mallin omaan työtilaasi Power BI -palvelussa. 

## <a name="get-the-sample"></a>Hanki malli

Ennen kuin voit käyttää mallia, se on ensin ladattava [sisältöpakettina](#get-the-content-pack-for-this-sample), [.pbix-tiedostona](#get-the-pbix-file-for-this-sample) tai [Excel-työkirjana](#get-the-excel-workbook-for-this-sample).

### <a name="get-the-content-pack-for-this-sample"></a>Mallin sisältöpaketin noutaminen

1. Avaa Power BI -palvelu (app.powerbi.com), kirjaudu sisään ja avaa työtila, johon haluat tallentaa mallin.

   Jos sinulla ei ole Power BI Pro -käyttöoikeutta, voit tallentaa mallin omaan työtilaasi.

2. Valitse vasemmasta alakulmasta **Nouda tiedot**.
   
   ![Valitse Nouda tiedot](media/sample-datasets/power-bi-get-data.png)
3. Valitse avautuvalta **Nouda tiedot** -sivulta **Mallit**.
   
4. Valitse **Toimittajan laatuanalyysimalli** ja valitse sitten **Yhdistä**.  
   
   ![Yhdistä malliin](media/sample-supplier-quality/supplier16.png)

5. Power BI tuo sisältöpaketin ja lisää sitten uuden koontinäytön, raportin ja tietojoukon senhetkiseen työtilaasi.
   
   ![Toimittajan laatuanalyysimallin syöte](media/sample-supplier-quality/supplier17.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Hae tämän mallin .pbix-tiedosto

Vaihtoehtoisesti voit ladata toimittajan laatuanalyysimallin [.pbix-tiedostona](http://download.microsoft.com/download/8/C/6/8C661638-C102-4C04-992E-9EA56A5D319B/Supplier-Quality-Analysis-Sample-PBIX.pbix), joka on suunniteltu käytettäväksi Power BI Desktopilla.

### <a name="get-the-excel-workbook-for-this-sample"></a>Hae tämän näytteen Excel-työkirja

Jos haluat perehtyä tämän mallin tietolähteeseen, se on saatavana myös [Excel-työkirjana](http://go.microsoft.com/fwlink/?LinkId=529779). Työkirja sisältää Power View -taulukoita, joita voit tarkastella ja muokata. Saat raakatiedot näkyviin ottamalla käyttöön Tietojen analysointi -apuohjelmat ja valitsemalla sitten **Power Pivot > Hallinta**. Voit ottaa Power View- ja Power Pivot -apuohjelmat käyttöön [tutustumalla Excelin sisältämien Excel-mallien](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself) lisätietoihin.

## <a name="downtime-caused-by-defective-materials"></a>Viallisten materiaalien aiheuttamat käyttökatkot
Analysoidaan viallisten materiaalien aiheuttamia käyttökatkoja ja katsotaan, mitkä toimittajat ovat vastuussa niistä.  

1. Valitse koontinäytössä **Vikojen kokonaismäärä**- tai **Käyttämättömyyden kokonaisaika minuuteissa** -ruutu.

   ![Avaa raportti valitsemalla ruutu](media/sample-supplier-quality/supplier2.png)  

   Toimittajan laatuanalyysimalli -raportti avautuu **Käyttökatkoaika-analyysi**-sivulle.

   Huomaa, että meillä on 33 miljoonaa viallista osaa, mikä aiheuttaa yhteensä 77 000 minuutin käyttökatkon. Vaikka joillakin materiaaleilla on vähemmän viallisia osia, ne voivat aiheuttaa viivästyksiä, mikä aiheuttaa enemmän käyttökatkoksia. Tutustutaan niihin tarkemmin raporttisivulla.  
2. Jos tarkastelemme **Käyttämättömyyden kokonaisaika minuuteissa** -riviä **Viat ja käyttämättömyys (minuutteina) materiaalityypin mukaan** yhdistelmäkaaviota voimme nähdä, että poimutetut materiaalit aiheuttavat eniten käyttökatkoja.  
3. Valitse **Poimutettu**-sarake, jotta näet, mihin toimipisteisiin tämä vika vaikuttaa eniten ja mikä toimittaja on vastuussa.  

   ![Valitse Poimutettu-sarake](media/sample-supplier-quality/supplier3.png)  
4. Valitse **Käyttökatkoaika minuutteina toimipisteen mukaan** -kartalta yksittäisiä toimipisteitä, jotta näet, mikä toimittaja tai materiaali on syynä käyttökatkoihin kyseisessä toimipisteessä.

### <a name="which-are-the-worst-suppliers"></a>Mitkä ovat huonoimmat toimittajat?
 Haluamme löytää kahdeksan huonointa toimittajaa ja määrittää, mikä prosenttiosuus käyttökatkoista johtuu kyseisistä toimittajista. Se onnistuu muuttamalla **Käyttökatkoaika minuutteina toimittajan mukaan** -aluekaavio puukartaksi.  

1. Valitse raportin **Käyttökatkoaika-analyysi**-sivulla **Muokkaa raporttia** vasemmassa yläkulmassa.  
2. Valitse **Käyttökatkoaika minuutteina toimittajan mukaan** -aluekaavio ja valitse **Visualisoinnit**-ruudusta **Puukartta**-kuvake.  

   ![Valitse puukartan kuvake](media/sample-supplier-quality/supplier4.png)  

    Puukartta määrittää automaattisesti **Toimittaja**-kentän **ryhmäksi**.  

    ![Käyttökatkoaika minuutteina toimittajan mukaan -puukartta](media/sample-supplier-quality/supplier5.png)  

   Näemme tässä puukartassa, että kahdeksan parasta toimittajaa ovat kahdeksan lohkoa puukartan vasemmassa reunassa. Näemme myös, että ne aiheuttavat noin 50 % kaikesta käyttökatkoajasta.  
3. Valitse **Toimittajan laatuanalyysimalli** yläreunan siirtymispalkista ja palaa koontinäyttöön.

### <a name="comparing-plants"></a>Toimipisteiden vertaileminen
Seuraavaksi tutustumme siihen, mitkä toimipisteet hallitsevat paremmin viallista materiaalia, jolloin tuloksena on vähemmän käyttökatkoja.  

1. Valitse koontinäytössä **Vikojen kokonaisraportit toimipisteen ja vikatyypin perusteella** -karttaruutu.      

   ![Vikojen kokonaisraportit toimipisteen ja vikatyypin perusteella -ruutu](media/sample-supplier-quality/supplier6.png)  

   Raportti avautuu **Toimittajan laatuanalyysi** -sivulle.  

2. Valitse **Vikojen kokonaisraportit toimipisteen ja vikatyypin perusteella** -ruudun selitteestä **Vaikutus**-ympyrä.  

    ![Valitse Vaikutus](media/sample-supplier-quality/supplier7.png)  

    Huomaa, että kuplakaaviossa **Logistiikka** on hankalin luokka. Se on suurin vikojen kokonaismäärän, vikaraporttien ja käyttökatkominuuttien suhteen. Perehdytään tähän luokkaan tarkemmin.  
3. Valitse kuplakaaviosta **Logistiikka**-kupla ja tutustu toimipisteisiin Illinoisin Springfieldissä ja Napervillessä. Naperville näyttää hallitsevan viallisia toimituksia paljon paremmin, koska siellä hylkäysten määrä on suurempi ja vaikutukset vähäisempiä verrattuna Springfieldin paljon suurempaan vaikutuslukuun.  

   ![Valitse Logistiikka](media/sample-supplier-quality/supplier8.png)  
4. Valitse **Toimittajan laatuanalyysimalli** yläreunan siirtymispalkista ja palaa koontinäyttöön.

## <a name="which-material-type-is-best-managed"></a>Mitä materiaalityyppiä hallitaan parhaiten?
Parhaiten hallittu materiaali on materiaali, jossa on vähäisin käyttökatkoaika tai ei vaikutusta vikamäärästä riippumatta.

1. Katso koontinäytössä **Vikojen kokonaismäärä materiaalityypin ja vikatyypin mukaan** -ruutua.

   ![Vikojen kokonaismäärä materiaalityypin ja vikatyypin mukaan -ruutu](media/sample-supplier-quality/supplier9.png)

   Huomaa, että vaikka **Raaka-aineet**-materiaalityypissä on paljon vikoja kokonaismäärällä mitattuna, valtaosa vioista joko hylätään tai niillä ei ole vaikutusta.

   Vahvistetaan siis, että tämä materiaalityyppi ei aiheuta paljon käyttökatkoja suuresta vikamäärästä huolimatta.

2. Katso koontinäytössä **Vikojen kokonaism., Käyttämättömyyden kokonaisaika minuuteissa materiaalityypin mukaan** -ruutua.

   ![Vikojen kokonaism., Käyttämättömyyden kokonaisaika minuuteissa materiaalityypin mukaan -ruutu](media/sample-supplier-quality/supplier10.png)

   Raaka-aineita hallitaan nähtävästi hyvin: vaikka niissä on enemmän vikoja, niiden käyttämättömyyden kokonaisaika minuuteissa on pienempi.

### <a name="compare-defects-to-downtime-by-year"></a>Vikojen vertaaminen käyttökatkoihin vuoden mukaan
1. Valitse **Vikojen kokonaismäärä tehtaan ja vikatyypin mukaan** -karttaruutu, jotta raportti avautuu **Toimittajan laatuanalyysi** -sivulle.
2. Huomaa, että **Vikojen kokonaismäärä kuukauden ja vuoden mukaan** -kaavion vikojen määrä on suurempi vuonna 2014 kuin 2013.  

    ![Vikojen kokonaismäärä kuukauden ja vuoden mukaan -kaavio](media/sample-supplier-quality/supplier11.png)  
3. Aiheuttaako suurempi vikamäärä enemmän käyttökatkoja? Esitä kysymyksiä Q&A-ruudussa asian selvittämiseksi.  
4. Valitse **Toimittajan laatuanalyysimalli** yläreunan siirtymispalkista ja palaa koontinäyttöön.  
5. Koska tiedämme, että raaka-aineissa on eniten vikoja, kirjoita kysymysruutuun *näytä materiaalityypit, vuosi ja vikojen kokonaismäärä*.  

    Raaka-ainevikoja ilmeni paljon enemmän vuonna 2014 kuin vuonna 2013.  

    ![Q&A-kysymys: Näytä materiaalityypit, vuosi ja vikojen kokonaismäärä](media/sample-supplier-quality/supplier12.png)  
6. Vaihda sitten kysymykseksi _näytä materiaalityypit, vuosi ja **käyttökatkojen kokonaisaika minuutteina**_ .  

   ![Kysymysosion kysymys: Näytä materiaalityypit, vuosi ja käyttökatkojen kokonaisaika minuutteina](media/sample-supplier-quality/supplier13.png)

   Huomaa, että raaka-aineiden käyttökatkoja oli suurin piirtein saman verran vuosina 2013 ja 2014, vaikka raaka-vikoja oli paljon enemmän vuonna 2014. Vaikuttaa siltä, että raaka-aineiden lisäviat vuonna 2014 eivät paljoakaan lisänneet raaka-aineiden käyttökatkoja vuonna 2014.

### <a name="compare-defects-to-downtime-month-to-month"></a>Vikojen vertaaminen käyttökatkoihin kuukausittain
Katsotaan toista koontinäytön ruutua, joka liittyy vikojen kokonaismäärään.  

1. Palaa koontinäyttöön valitsemalla vasemmasta yläkulmasta **Poistu Q&A:sta**.  

    Katso tarkemmin **Vikojen kokonaismäärää kuukauden ja vuoden mukaan** -ruutua. Se näyttää, että vuoden 2014 alkupuolella vikojen määrä vastasi vuotta 2013, mutta vuoden 2014 toisella puoliskolla vikojen kokonaismäärä lisääntyi merkittävästi.  

    ![Vikojen kokonaismäärä kuukauden ja vuoden mukaan -ruutu](media/sample-supplier-quality/supplier14.png)  

    Katsotaan, aiheuttiko tämä vikamäärän kasvu vastaavan kasvun käyttökatkoajassa.  
2. Kirjoita kysymysruutuun *käyttökatkoaika minuutteina kuukauden ja vuoden mukaan viivakaaviona*.  

   ![Q&A-kysymys: Käyttökatkoaika minuutteina kuukauden ja vuoden mukaan viivakaaviona](media/sample-supplier-quality/supplier15.png)

   Käyttökatkoajassa oli hyppy kesäkuun ja lokakuun aikana, mutta muilta osin vikojen määrän kasvu ei aiheuttanut merkittävää lisäystä käyttökatkoissa. Tämä tulos osoittaa, että vikoja hallitaan hyvin.  
3. Jos haluat kiinnittää kaavion raporttinäkymään, valitse Kiinnitä-kuvake ![Kiinnitä-kuvake](media/sample-supplier-quality/pin.png) kysymysruudun yläpuolella.  
4. Jos haluat tutkia poikkeavia kuukausia, tarkista käyttökatkoajat minuutteina lokakuussa materiaalityypin, toimipisteen sijainnin, luokan jne. mukaan esittämällä kysymyksiä, kuten *käyttämättömyyden kokonaisaika minuuteissa lokakuussa toimipisteen mukaan*. 
5. Palaa koontinäyttöön valitsemalla vasemmasta yläkulmasta **Poistu Q&A:sta**.

## <a name="next-steps-connect-to-your-data"></a>Seuraavat vaiheet: Yhdistä tietoihisi
Tässä ympäristössä on turvallista tehdä kokeiluja, koska voit jättää tekemäsi muutokset tallentamatta. Jos kuitenkin tallennat ne, voit aina siirtyä **Nouda tiedot** -kohtaan, jolloin saat tästä mallista uuden kopion.

Toivomme, että tämä esittely on osoittanut, miten Power BI -raporttinäkymät, Q&A ja raportit voivat tarjota uusia näkökulmia mallitietoihin. Nyt on sinun vuorosi – muodosta yhteys omiin tietoihisi. Power BI:n avulla voit yhdistää useisiin eri tietolähteisiin. Lisätietoja on artikkelissa [Power BI -palvelun käytön aloittaminen](service-get-started.md).
