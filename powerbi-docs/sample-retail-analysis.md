---
title: 'Jälleenmyyntianalyysimalli Power BI:lle: aloita esittely'
description: 'Jälleenmyyntianalyysimalli Power BI:lle: aloita esittely'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/02/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 310afbf845550eaca666543397dd78eb0a0d15dc
ms.sourcegitcommit: 1789815c87e306b1427a5838655d30d3b9ba1d29
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/11/2019
ms.locfileid: "67791984"
---
# <a name="retail-analysis-sample-for-power-bi-take-a-tour"></a>Jälleenmyyntianalyysimalli Power BI:lle: aloita esittely

Jälleenmyyntianalyysimallin sisältöpaketti sisältää koontinäytön, raportin ja tietojoukon, joka analysoi useissa myymälöissä ja useilla alueilla myytyjen tuotteiden jälleenmyyntitietoja. Arvoilla vertaillaan tämän ja viime vuoden myyntiä, tuotemääriä, myyntikatetta ja varianssi sekä analysoidaan uusia myymälöitä. 

![Jälleenmyyntianalyysimallin koontinäkymä](media/sample-retail-analysis/retail1.png)

Tämä malli kuuluu sarjaan, jossa esitellään, miten Power BI:tä voidaan käyttää liiketoimintaan suuntautuneiden tietojen, raporttien ja koontinäyttöjen kanssa. Sen luomiseen on käytetty [obviEnceltä](http://www.obvience.com/) saatuja oikeita tietoja, jotka on muunnettu nimettömään muotoon. Tiedot ovat käytettävissä useissa muodoissa: sisältöpaketti, Power BI Desktopin .pbix-tiedosto tai Excel-työkirja. Tutustu [Power BI:n malleihin](sample-datasets.md). 

Tässä opetusohjelmassa tutustutaan Power BI -palvelun jälleenmyyntianalyysimallin sisältöpakettiin. Koska raportin käyttökokemus on hyvin samankaltainen Power BI Desktopissa ja palvelussa, voit seurata ohjelmaa myös käyttämällä Power BI Desktopin mallin .pbix-tiedostoa. 

Et tarvitse Power BI -käyttöoikeutta Power BI Desktopin malleihin tutustumiseen. Jos sinulla ei ole Power BI Pro -käyttöoikeutta, voit tallentaa mallin omaan työtilaasi Power BI -palvelussa. 

## <a name="get-the-sample"></a>Hanki malli

 Ennen kuin voit käyttää mallia, se on ensin ladattava [sisältöpakettina](#get-the-content-pack-for-this-sample), [.pbix-tiedostona](#get-the-pbix-file-for-this-sample) tai [Excel-työkirjana](#get-the-excel-workbook-for-this-sample).

### <a name="get-the-content-pack-for-this-sample"></a>Mallin sisältöpaketin noutaminen

1. Avaa Power BI -palvelu (app.powerbi.com), kirjaudu sisään ja avaa työtila, johon haluat tallentaa mallin. 

    Jos sinulla ei ole Power BI Pro -käyttöoikeutta, voit tallentaa mallin omaan työtilaasi.

2. Valitse vasemmasta alakulmasta **Nouda tiedot**.

    ![Valitse Nouda tiedot](media/sample-datasets/power-bi-get-data.png)
3. Valitse avautuvalta **Nouda tiedot** -sivulta **Mallit**.
   
4. Valitse **Jälleenmyyntianalyysimalli** ja **Yhdistä**.  
  
   ![Yhdistä malliin](media/sample-retail-analysis/retail16.png)
   
5. Power BI tuo sisältöpaketin ja lisää sitten uuden koontinäytön, raportin ja tietojoukon senhetkiseen työtilaasi.
   
   ![Jälleenmyyntianalyysimallin syöte](media/sample-retail-analysis/retail-entry.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Hae tämän mallin .pbix-tiedosto

Vaihtoehtoisesti voit ladata jälleenmyyntianalyysimallin [.pbix-tiedostona](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix), joka on suunniteltu käytettäväksi Power BI Desktopilla. 

### <a name="get-the-excel-workbook-for-this-sample"></a>Hae tämän näytteen Excel-työkirja

Jos haluat perehtyä tämän mallin tietolähteeseen, se on saatavana myös [Excel-työkirjana](http://go.microsoft.com/fwlink/?LinkId=529778). Työkirja sisältää Power View -taulukoita, joita voit tarkastella ja muokata. Saat raakatiedot näkyviin ottamalla käyttöön Tietojen analysointi -apuohjelmat ja valitsemalla sitten **Power Pivot > Hallinta**. Voit ottaa Power View- ja Power Pivot -apuohjelmat käyttöön [tutustumalla Excelin sisältämien Excel-mallien](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself) lisätietoihin.

## <a name="start-on-the-dashboard-and-open-the-report"></a>Käynnistä raporttinäkymässä ja avaa raportti

1. Avaa **Koontinäytöt**-välilehti työtilassa, johon tallensit mallin, ja etsi sitten **Jälleenmyyntianalyysimalli**-koontinäyttö ja valitse se. 
2. Valitse koontinäytössä **Myymälöitä yhteensä, uudet ja olemassa olevat myymälät** -ruutu, joka avautuu Jälleenmyyntianalyysimalli-raportin **Myymälöiden myynnin yleiskatsaus** -sivulle. 

   ![Myymälöitä yhteensä -ruutu](media/sample-retail-analysis/retail-analysis-7.png)  

   Tällä raportin sivulla näet, että meillä on yhteensä 104 myymälää, joista 10 on uusia. Meillä on kaksi ketjua: Fashions Direct ja Lindseys. Fashions Direct -myymälät ovat keskimäärin suurempia.
3. Valitse **Tämän vuoden myynti ketjun mukaan** -ympyräkaaviosta **Fashions Direct**.

   ![Tämän vuoden myynti ketjun mukaan -kaavio](media/sample-retail-analysis/retail3.png)  

   Huomaa tulos **Myyntivariaatioprosentti yhteensä** -kuplakaaviossa:

   ![Myyntivariaatioprosentti yhteensä -kaavio](media/sample-retail-analysis/pbi_sample_retanlbubbles.png)  

   **FD-01**-alueella on suurin keskimääräinen **myynti neliöjalkaa kohden**, FD-02-alueella on pienin **kokonaismyynnin variaatioprosentti** viime vuoteen verrattuna. FD-03- ja FD-04-alueiden suorituskyky on yleisesti heikoin.
4. Valitse yksittäiset kuplat tai muut kaaviot nähdäksesi ristiinkorostuksen, joka osoittaa valintojesi vaikutuksen.
5. Valitse **Jälleenmyyntianalyysimalli** yläreunan siirtymispalkista koontinäyttöön palaamiseksi.

   ![Siirtymispalkki](media/sample-retail-analysis/power-bi-breadcrumbs.png)
6. Valitse raporttinäkymässä **Tämän vuoden myynti, uudet ja olemassa olevat myymälät** -ruutu, joka vastaa kysymyksen *Tämän vuoden myynti* kirjoittamista Q&A-kysymysruutuun.

   ![Tämän vuoden myynti -ruutu](media/sample-retail-analysis/pbi_sample_retanlthisyrsales.png)

   Näkyviin tulevat Q&A-tulokset:

   ![Tämän vuoden myynti Q&A:ssa](media/sample-retail-analysis/retail7.png)

## <a name="review-a-tile-created-with-power-bi-qa"></a>Tarkista Power BI:n Q&A-toiminnolla luotu ruutu
Perehdytään asiaan tarkemmin.

1. Muuta kysymys muotoon *tämän vuoden myynti **alueen mukaan*. Huomaa tulos: Q&A sijoittaa vastauksen automaattisesti palkkikaavioon ja ehdottaa muita lauseita:

   ![Tämän vuoden myynti alueen mukaan Q&A:ssa](media/sample-retail-analysis/retail8.png)
2. Muuta nyt kysymyksesi muotoon *tämän vuoden myynti **postinumeron ja ketjun mukaan***.

   Huomaa, miten Power BI vastaa kysymykseen kirjoittaessasi ja näyttää asianmukaiset kaaviot.
3. Kokeile esittää lisää kysymyksiä ja katso, millaisia tuloksia saat.
4. Kun olet valmis, palaa raporttinäkymään.

## <a name="dive-deeper-into-the-data"></a>Tutki tietoja tarkemmin
Seuraavaksi tutkimme tietoja tarkemmin ja perehdymme alueiden suorituskykyyn.

1. Valitse raporttinäkymässä **Tämän vuoden myynti, edellisen vuoden myynti** -ruutu, joka avaa raportin **Alueen kuukausimyynti** -sivun.

   ![Tämän vuoden myynti, edellisen vuoden myynti -ruutu](media/sample-retail-analysis/pbi_sample_retanlareacht.png)

   Huomaa **Kokonaismyynnin variaatioprosentti tilikauden kuukauden mukaan** -kaavion varianssiprosentin suuri vaihtelu edelliseen vuoteen verrattuna. Tammikuu, huhtikuu ja heinäkuu ovat erityisen heikkoja kuukausia.

   ![Kokonaismyynnin variaatioprosentti tilikauden kuukauden mukaan -kaavio](media/sample-retail-analysis/pbi_sample_retanlsalesvarcol.png)

   Katsotaan, pystymmekö rajaamaan tuloksia ongelman löytämiseksi.
2. Valitse kuplakaaviosta **020-Miehet**-kupla.

   ![Valitse 020-Miehet](media/sample-retail-analysis/retail11.png)  

   Huomaa, että vaikka huhtikuun tulos ei vaikuttanut miesten luokkaan yhtä vakavasti kuin yrityksen kokonaistulokseen, tammikuu ja heinäkuu olivat silti ongelmallisia.
1. Valitse nyt **010-Naiset**-kupla.

   ![Valitse 010-Naiset](media/sample-retail-analysis/retail12.png)

   Huomaa, naisten luokan suorituskyky on paljon heikompi kuin yrityksen kokonaistulos kaikkina kuukausina sekä viime vuotta heikompi lähes kaikkina kuukausina.
1. Valitse kupla uudelleen poistaaksesi suodattimen.

## <a name="try-out-the-slicer"></a>Kokeile osittajaa
Katsotaan, miten tietyt alueet suoriutuvat.

1. Valitse **Alpo Kuusinen** vasemmassa yläkulmassa olevassa **Aluejohtaja**-osittajassa.

   ![Valitse Alpo Kuusinen](media/sample-retail-analysis/retail13.png)

   Huomaa, että Alpon alue suoriutui maaliskuussa ja kesäkuussa paremmin kuin edellisen vuonna.
2. Pidä **Alpo Kuusinen** edelleen valittuna ja valitse **Naisten-10**-kupla kuplakaaviossa.

   ![Alpo Kuusinen ja Naisten-10 valittuna](media/sample-retail-analysis/power-bi-allan.png)

   Huomaa, Naisten-10-luokassa Alpon alue ei yltänyt viime vuoden määrään.
3. Tutki alueen muita johtajia ja luokkia – mitä muita tietoja huomaat?
4. Kun olet valmis, palaa raporttinäkymään.

## <a name="what-the-data-says-about-sales-growth-this-year"></a>Mitä tiedot kertovat tämän vuoden myynnin kasvusta
Lopuksi haluamme tutkia vielä kasvua tarkastelemalla tänä vuonna avattuja uusia myymälöitä.

1. Valitse **Tänä vuonna avatut myymälät avoimen kuukauden ja ketjun mukaan** -ruutu, joka avaa raportin **Uusien myymälöiden analyysi** -sivun.

   ![Uusien myymälöiden analyysi -sivu](media/sample-retail-analysis/retail15.png)

   Kuten ruudusta käy ilmi, tänä vuonna avattiin enemmän Fashions Direct -myymälöitä kuin Lindseys-myymälöitä.
2. Huomaa **Myynti per neliöjalka nimen mukaan** -kaavio:

   ![Myynti per neliöjalka nimen mukaan -kaavio](media/sample-retail-analysis/retail14.png)

    Huomaa ero keskimääräisessä myynnissä/neliöjalka uusien myymälöiden välillä.
3. Valitse **Fashions Direct**-selite **Avoimien myymälöiden määrä kuukauden ja ketjun mukaan** -kaaviosta yläoikealta. Huomaa, että jopa saman ketjun sisällä paras myymälä (Winchester Fashions Direct) suoriutui huomattavasti paremmin kuin huonoin myymälä (Cincinnati 2 Fashions Direct), niiden arvojen ollessa 21,22 ja 12,86 dollaria.

   ![Fashions Direct valittuna](media/sample-retail-analysis/power-bi-lindseys.png)
4. Valitse **Winchester Fashions Direct** **Nimi**-osittajassa ja huomaa viivakaavio. Ensimmäiset myyntiluvut raportoitiin helmikuussa.
5. Valitse osittajassa **Cincinnati 2 Fashions Direct** ja huomaa viivakaavio, joka osoittaa, että myymälä avattiin kesäkuussa ja se vaikuttaa olevan huonoiten suoriutuva myymälä.
6. Selaa valitsemalla muita palkkeja, viivoja ja kuplia koko kaaviossa ja katso, mitä tietoja voit löytää.

## <a name="next-steps-connect-to-your-data"></a>Seuraavat vaiheet: Yhdistä tietoihisi
Tässä ympäristössä on turvallista tehdä kokeiluja, koska voit jättää tekemäsi muutokset tallentamatta. Jos kuitenkin tallennat ne, voit aina siirtyä **Nouda tiedot** -kohtaan, jolloin saat tästä mallista uuden kopion.

Toivomme, että tämä esittely on osoittanut, miten Power BI -raporttinäkymät, Q&A ja raportit voivat tarjota uusia näkökulmia mallitietoihin. Nyt on sinun vuorosi – muodosta yhteys omiin tietoihisi. Power BI:n avulla voit yhdistää useisiin eri tietolähteisiin. Lisätietoja on artikkelissa [Power BI -palvelun käytön aloittaminen](service-get-started.md).
