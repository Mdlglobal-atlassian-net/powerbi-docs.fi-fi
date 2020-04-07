---
title: 'IT-kulutusanalyysimalli Power BI:lle: aloita esittely'
description: 'IT-kulutusanalyysimalli Power BI:lle: aloita esittely'
author: maggiesMSFT
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/05/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 00effa1838327a9463671cf9be2f5764be71deb4
ms.sourcegitcommit: 444f7fe5068841ede2a366d60c79dcc9420772d4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/30/2020
ms.locfileid: "80404695"
---
# <a name="it-spend-analysis-sample-for-power-bi-take-a-tour"></a>IT-kulutusanalyysimalli Power BI:lle: aloita esittely

IT-kulutusanalyysimallin sisältöpaketti sisältää koontinäytön, raportin ja tietojoukon, jotka analysoivat IT-osaston suunniteltuja kuluja verrattuna todellisiin kuluihin. Tämän vertailun avulla voi arvioida sitä, kuinka hyvin yritys suunnitteli vuoden, sekä tutkia osa-alueita, jotka poikkeavat merkittävästi suunnitelmasta. Tämän esimerkin yritys käyttää vuosittaista suunnittelujaksoa ja laatii neljännesvuosittain uusimman arvion, jonka avulla voidaan analysoida IT-osaston kuluissa tilivuoden aikana tapahtuneita muutoksia.

![IT-kulutusanalyysimallin koontinäyttö](media/sample-it-spend/it1.png)

Tämä malli kuuluu sarjaan, jossa esitellään, miten Power BI:tä voidaan käyttää liiketoimintaan suuntautuneiden tietojen, raporttien ja koontinäyttöjen kanssa. [ObviEnce](http://www.obvience.com/) on luonut sen käyttämällä oikeita tietoja, jotka on muunnettu nimettömään muotoon. Tiedot ovat käytettävissä useissa muodoissa: sisältöpaketti, Power BI Desktopin .pbix-tiedosto tai Excel-työkirja. Tutustu [Power BI:n malleihin](sample-datasets.md). 

Tässä opetusohjelmassa tutustutaan Power BI -palvelun IT-kulutusanalyysimallin sisältöpakettiin. Koska raportin käyttökokemus on hyvin samankaltainen Power BI Desktopissa ja palvelussa, voit seurata ohjelmaa myös käyttämällä Power BI Desktopin mallin .pbix-tiedostoa. 

Et tarvitse Power BI -käyttöoikeutta Power BI Desktopin malleihin tutustumiseen. Jos sinulla ei ole Power BI Pro -käyttöoikeutta, voit tallentaa mallin omaan työtilaasi Power BI -palvelussa. 

## <a name="get-the-sample"></a>Hanki malli

 Ennen kuin voit käyttää mallia, se on ensin ladattava [sisältöpakettina](#get-the-content-pack-for-this-sample), [.pbix-tiedostona](#get-the-pbix-file-for-this-sample) tai [Excel-työkirjana](#get-the-excel-workbook-for-this-sample).

### <a name="get-the-content-pack-for-this-sample"></a>Mallin sisältöpaketin noutaminen

1. Avaa Power BI -palvelu (app.powerbi.com), kirjaudu sisään ja avaa työtila, johon haluat tallentaa mallin.

   Jos sinulla ei ole Power BI Pro -käyttöoikeutta, voit tallentaa mallin omaan työtilaasi.

2. Valitse vasemmasta alakulmasta **Nouda tiedot**.
   
   ![Valitse Nouda tiedot](media/sample-datasets/power-bi-get-data.png)
3. Valitse avautuvalta **Nouda tiedot** -sivulta **Mallit**.
   
4. Valitse **IT-kulutusanalyysimalli** ja valitse sitten **Yhdistä**.  
  
   ![Yhdistä malliin](media/sample-it-spend/it-connect.png)
   
5. Power BI tuo sisältöpaketin ja lisää sitten uuden koontinäytön, raportin ja tietojoukon senhetkiseen työtilaasi.
   
   ![IT-kulutusanalyysimallin syöte](media/sample-it-spend/it-spend-analysis-sample-entry.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Hae tämän mallin .pbix-tiedosto

Vaihtoehtoisesti voit ladata IT-kulutusanalyysimallin [.pbix-tiedostona](https://download.microsoft.com/download/E/9/8/E98CEB6D-CEBB-41CF-BA2B-1A1D61B27D87/IT%20Spend%20Analysis%20Sample%20PBIX.pbix), joka on suunniteltu käytettäväksi Power BI Desktopilla.

### <a name="get-the-excel-workbook-for-this-sample"></a>Hae tämän näytteen Excel-työkirja

Jos haluat perehtyä tämän mallin tietolähteeseen, se on saatavana myös [Excel-työkirjana](https://go.microsoft.com/fwlink/?LinkId=529783). Työkirja sisältää Power View -taulukoita, joita voit tarkastella ja muokata. Saat raakatiedot näkyviin ottamalla käyttöön Tietojen analysointi -apuohjelmat ja valitsemalla sitten **Power Pivot > Hallinta**. Voit ottaa Power View- ja Power Pivot -apuohjelmat käyttöön [tutustumalla Excelin sisältämien Excel-mallien](sample-datasets.md#explore-excel-samples-inside-excel) lisätietoihin.

## <a name="it-spend-analysis-sample-dashboard"></a>IT-kulutusanalyysimallin koontinäyttö
Koontinäytön vasemman reunan kaksi numeroruutua, **Varianssisuunnitelma %** ja **Varianssin uusin arvio % 3. vuosineljännes**, antavat yleiskuvan siitä, miten yritys on suoriutunut verrattuna suunnitelmaan ja uusimpaan vuosineljännesarvioon (LE3 = uusin arvio 3. vuosineljännes). Yleisesti ero suunnitelmaan on noin 6 prosenttia. Tutkitaanpa, mistä varianssi johtuu: milloin, missä ja missä luokassa?

## <a name="ytd-it-spend-trend-analysis-page"></a>IT-kulutrendianalyysi vuoden alusta -sivu
**Varianssisuunnitelma % myyntialueittain** -koontinäyttöruudun valitseminen siirtää sinut IT-kulutusanalyysimallin raportin **IT-kulutrendianalyysi vuoden alusta** -sivulle. Näemme yhdellä silmäyksellä, että varianssi on positiivinen Yhdysvalloissa ja Euroopassa sekä negatiivinen Kanadassa, Latinalaisessa Amerikassa ja Australiassa. Yhdysvalloissa on noin 6 % +LE-varianssi ja Australiassa on noin 7 % -LE-varianssi.

![Varianssisuunnitelma (%) myyntialueittain](media/sample-it-spend/it2.png)

Mutta vain tämän kaavion katsominen ja päätelmien tekeminen sen perusteella voi olla harhaanjohtavaa. Meidän on tutustuttava todellisiin rahamääriin, jos haluamme todellisen kuvan asioista.

1. Valitse **Aus ja NZ** **Varianssisuunnitelma % myyntialueittain** -kaaviossa ja katso **Varianssisuunnitelma IT-alueittain** -kaaviota.

   ![IT-kulutrendianalyysi vuoden alusta -sivu](media/sample-it-spend/it3.png)
2. Valitse seuraavaksi **USA**. Huomaa, että Australian ja Uuden-Seelannin osuus on hyvin pieni yleistä kulutuksestamme verrattuna Yhdysvaltoihin.

    Katsotaanpa seuraavaksi, mikä luokka Yhdysvalloissa aiheuttaa varianssin.

## <a name="ask-questions-of-the-data"></a>Kysymysten kysyminen tiedoista
1. Palaa mallikoontinäyttöön valitsemalla **IT-kulutusanalyysimalli** yläreunan siirtymisruudusta.
2. Valitse **Kysymysten kysyminen tiedoista**.
3. Valitse **Kysymyksiä, joiden avulla pääset alkuun** -luettelosta vasemmalla puolella **suunnitelma IT-alueen mukaan**.

   ![Suunnittele IT-alueittain -kaavio](media/sample-it-spend/it-area-chart.png)

4. Poista Q&A-ruudussa aiempi syöte ja syötä *Näytä IT-alueet, varianssisuunnitelma % ja varianssi le3 % -palkkikaavio*.

   ![Varianssisuunnitelma % ja varianssisuunnitelma LE3 % IT-alueittain -kaavio](media/sample-it-spend/it4.png)

   Ensimmäisellä IT-alueella, **Infrastruktuuri**, prosenttiosuus on muuttunut huomattavasti alkuperäisen varianssisuunnitelman ja varianssisuunnitelman uusimman arvion välillä.

## <a name="ytd-spend-by-cost-elements-page"></a>YTD-kulutus kustannustasoittain -sivu

1. Palaa koontinäyttöön ja tarkastele **Varianssisuunnitelma %, varianssin uusin arvio % – 3. vuosineljännes** -koontinäyttöruutua.

   ![Varianssisuunnitelma %, varianssi LE3 -ruutu](media/sample-it-spend/it5.png)

   Huomaa, että Infrastruktuuri-alue erottuu suuren positiivisen varianssinsa ansiosta verrattuna suunnitelmaan.

1. Valitse tämä ruutu raportin avaamiseksi ja **YTD-kulutus kustannustasoittain** -sivun tarkastelemiseksi.
2. Valitse **Infrastruktuuri**-palkki oikeasta alakulmasta **Varianssisuunnitelma % ja varianssi LE3 % IT-alueittain** -kaaviosta ja tarkastele varianssi suunnitelmaan verrattuna -arvoja vasemman alakulman **Varianssisuunnitelma % myyntialueittain** -kaaviossa.

    ![YTD-kulutus kustannustasoittain -sivu](media/sample-it-spend/it6.png)
3. Valitse kukin nimi vuorostaan **Kustannustasoryhmä**-osittajasta löytääksesi kustannustason, jolla on suurin varianssi.
4. Kun **Muu** on valittuna, valitse **Infrastruktuuri** **IT-alue**-osittajassa ja napsauta alialueita **IT-alialue**-osittajassa suurimmalla varianssilla varustetun alialueen löytämiseksi.  

   Huomaa **Verkko**-kohdan suuri varianssi. Ilmeisesti yritys päätti antaa työntekijöilleen puhelinpalveluja etuutena, vaikka tätä toimenpidettä ei suunniteltu.

## <a name="plan-variance-analysis-page"></a>Suunnitelmavarianssianalyysi-sivu

1. Valitse **Suunnitelmavarianssianalyysi**-välilehti sivun alareunasta.

2. Valitse vasemmalta **Varianssisuunnitelma ja Varianssisuunnitelma % liiketoiminta-alueittain** -kaaviosta **Infrastruktuuri**-kaavio infrastruktuurin korostamiseksi liiketoiminta-alueittain sivun muissa osissa.

    ![Suunnitelmavarianssianalyysi-sivu](media/sample-it-spend/it7.png)

   Huomaa **Varianssisuunnitelma % kuukausittain ja liiketoiminta-alueittain** -kaaviossa, että infrastruktuurin liiketoiminta-alueen positiivinen varianssi alkoi helmikuussa. Huomaa myös, miten varianssi verrattuna suunnitelmaan -arvo vaihtelee maan mukaan verrattuna kaikkiin muihin liiketoiminta-alueisiin. 

3. Oikealla olevien **IT-alue**- ja **IT-alialue**-osittajien avulla voit suodattaa sivun muissa osissa olevia arvoja ja tarkastella tietoja. 

## <a name="edit-the-report"></a>Muokkaa raporttia
Valitse vasemmasta yläkulmasta **Muokkaa raporttia** muokkausnäkymän tarkastelemiseksi:

* Katso, miten sivut muodostetaan, kussakin kaaviossa olevat kentät ja sivuilla olevat suodattimet.
* Lisää sivuja ja kaavioita samojen tietojen perusteella.
* Muuta kunkin kaavion visualisointityyppiä.
* Koontinäytössä olevat kiinnostavat PIN-kaaviot.

## <a name="next-steps-connect-to-your-data"></a>Seuraavat vaiheet: Yhdistä tietoihisi
Tässä ympäristössä on turvallista tehdä kokeiluja, koska voit jättää tekemäsi muutokset tallentamatta. Jos kuitenkin tallennat ne, voit aina siirtyä **Nouda tiedot** -kohtaan, jolloin saat tästä mallista uuden kopion.

Toivomme, että tämä esittely on osoittanut, miten Power BI -raporttinäkymät, Q&A ja raportit voivat tarjota uusia näkökulmia mallitietoihin. Nyt on sinun vuorosi – muodosta yhteys omiin tietoihisi. Power BI:n avulla voit yhdistää useisiin eri tietolähteisiin. Lisätietoja on artikkelissa [Power BI -palvelun käytön aloittaminen](service-get-started.md).
