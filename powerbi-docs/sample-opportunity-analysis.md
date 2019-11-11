---
title: 'Mahdollisuusanalyysimalli Power BI:lle: aloita esittely'
description: 'Mahdollisuusanalyysimalli Power BI:lle: aloita esittely'
author: maggiesMSFT
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/02/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: d871fa15c999e5b6c83b0334d6c978b2ba3c9870
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73858698"
---
# <a name="opportunity-analysis-sample-for-power-bi-take-a-tour"></a>Mahdollisuusanalyysimalli Power BI:lle: aloita esittely

Mahdollisuusanalyysimallin sisältöpaketti sisältää koontinäytön, raportin ja tietojoukon ohjelmistoyritykselle, jolla on kaksi myyntikanavaa: *suora* ja *kumppani*. Myyntipäällikkö loi tämän koontinäytön seuratakseen mahdollisuuksia ja tuloja alueen, kaupan koon ja kanavan mukaan.

Tämä malli käyttää kahta tuottoa koskevaa mittaria:

* Tuotto: Myyjän arvio siitä, mikä tuotto on.
* Laskutettu tuotto: Lasketaan kaavalla tuotto × todennäköisyysprosentti, ja sen hyväksytään olevan tarkempi ennuste todellisesta myyntituotosta. Todennäköisyyden määrittää kaupan senhetkinen *myynnin vaihe*:
  * Liidi: 10 %  
  * Kvalifioidut: 20 %  
  * Ratkaisu: 40 %  
  * Ehdotus: 60 %  
  * Viimeistely: 80 %

![Mahdollisuusanalyysimallin koontinäyttö](media/sample-opportunity-analysis/opportunity1.png)

Tämä malli kuuluu sarjaan, jossa esitellään, miten Power BI:tä voidaan käyttää liiketoimintaan suuntautuneiden tietojen, raporttien ja koontinäyttöjen kanssa. [ObviEnce](http://www.obvience.com/) on luonut sen käyttämällä oikeita tietoja, jotka on muunnettu nimettömään muotoon. Tiedot ovat käytettävissä useissa muodoissa: sisältöpaketti, Power BI Desktopin .pbix-tiedosto tai Excel-työkirja. Tutustu [Power BI:n malleihin](sample-datasets.md). 

Tässä opetusohjelmassa tutustutaan Power BI -palvelun mahdollisuusanalyysimallin sisältöpakettiin. Koska raportin käyttökokemus on hyvin samankaltainen Power BI Desktopissa ja palvelussa, voit seurata ohjelmaa myös käyttämällä Power BI Desktopin mallin .pbix-tiedostoa. 

Et tarvitse Power BI -käyttöoikeutta Power BI Desktopin malleihin tutustumiseen. Jos sinulla ei ole Power BI Pro -käyttöoikeutta, voit tallentaa mallin omaan työtilaasi Power BI -palvelussa. 

## <a name="get-the-sample"></a>Hanki malli

Ennen kuin voit käyttää mallia, se on ensin ladattava [sisältöpakettina](#get-the-content-pack-for-this-sample), [.pbix-tiedostona](#get-the-pbix-file-for-this-sample) tai [Excel-työkirjana](#get-the-excel-workbook-for-this-sample).

### <a name="get-the-content-pack-for-this-sample"></a>Mallin sisältöpaketin noutaminen

1. Avaa Power BI -palvelu (app.powerbi.com), kirjaudu sisään ja avaa työtila, johon haluat tallentaa mallin. 

    Jos sinulla ei ole Power BI Pro -käyttöoikeutta, voit tallentaa mallin omaan työtilaasi.

2. Valitse vasemmasta alakulmasta **Nouda tiedot**.

    ![Valitse Nouda tiedot](media/sample-datasets/power-bi-get-data.png)
3. Valitse avautuvalta **Nouda tiedot** -sivulta **Mallit**.

4. Valitse **Mahdollisuusanalyysimalli** ja valitse sitten **Yhdistä**.  

   ![Yhdistä malliin](media/sample-opportunity-analysis/opportunity-connect.png)
5. Power BI tuo sisältöpaketin ja lisää sitten uuden koontinäytön, raportin ja tietojoukon senhetkiseen työtilaasi.

   ![Mahdollisuusanalyysimallin syöte](media/sample-opportunity-analysis/opportunity-entry.png)

### <a name="get-the-pbix-file-for-this-sample"></a>Hae tämän mallin .pbix-tiedosto

Vaihtoehtoisesti voit ladata mahdollisuusanalyysimallin [.pbix-tiedostona](https://download.microsoft.com/download/9/1/5/915ABCFA-7125-4D85-A7BD-05645BD95BD8/Opportunity%20Analysis%20Sample%20PBIX.pbix), joka on suunniteltu käytettäväksi Power BI Desktopilla.

### <a name="get-the-excel-workbook-for-this-sample"></a>Hae tämän näytteen Excel-työkirja

Jos haluat perehtyä tämän mallin tietolähteeseen, se on saatavana myös [Excel-työkirjana](https://go.microsoft.com/fwlink/?LinkId=529782). Työkirja sisältää Power View -taulukoita, joita voit tarkastella ja muokata. Saat raakatiedot näkyviin ottamalla käyttöön Tietojen analysointi -apuohjelmat ja valitsemalla sitten **Power Pivot > Hallinta**. Voit ottaa Power View- ja Power Pivot -apuohjelmat käyttöön [tutustumalla Excelin sisältämien Excel-mallien](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself) lisätietoihin.

## <a name="what-is-our-dashboard-telling-us"></a>Mitä koontinäyttö kertoo?
Myyntipäällikkö on luonut koontinäytön itselleen tärkeimpien arvojen seuraamista varten. Kun hän näkee jotakin mielenkiintoista, hän voi valita ruudun ja perehtyä tietoihin tarkemmin:

- Yrityksen tuotto on 2 miljardia dollaria ja laskutettu tuotto on 461 miljoonaa dollaria.
- Mahdollisuuksien lukumäärä ja tuotto seuraavat tunnettua suppilomallia siten, että kokonaismäärät pienenevät kussakin myöhemmässä vaiheessa.
- Useimmat mahdollisuudet ovat itäisellä alueella.
- Suuret mahdollisuudet tuottavat enemmän tuottoa kuin keskikokoiset tai pienet mahdollisuudet.
- Suuret kumppanisopimukset tuottavat enemmän tuottoa: keskimäärin 8 miljoonaa dollaria verrattuna suoran myynnin 6 miljoonaan.

Koska panostus sopimuksen saamiseen on sama riippumatta siitä, onko sopimus luokiteltu suureksi, keskikokoiseksi vai pieneksi, yrityksemme pitää analysoida tiedot, jotta saamme lisätietoa suurista mahdollisuuksista.

1. Avaa **Koontinäytöt**-välilehti työtilassa, johon tallensit mallin, ja etsi sitten **mahdollisuusanalyysimalli**-koontinäyttö ja valitse se.

2. Valitse **Mahdollisuuksien lukumäärä kumppanivedon mukaan, myyntivaihe** -ruutu avataksesi Mahdollisuusanalyysimalli-raportin ensimmäisen sivun. 

    ![Mahdollisuuksien lukumäärä kumppanivedon mukaan, myyntivaihe -ruutu](media/sample-opportunity-analysis/opportunity2.png)

## <a name="explore-the-pages-in-the-report"></a>Raportin sivujen tutkiminen

Tarkastele raportin jokaista sivua valitsemalla sivuvälilehtiä alareunasta.

### <a name="opportunity-count-overview-page"></a>Mahdollisuuksien lukumäärän yleiskatsaus -sivu
![Mahdollisuuksien lukumäärä -sivu](media/sample-opportunity-analysis/opportunity3.png)

Huomioi seuraavat tiedot:
* Itä on suurin alueemme mahdollisuuksien lukumäärällä mitattuna.  
* Valitse **Mahdollisuuksien lukumäärä alueittain** -ympyräkaaviosta yksitellen kukin alue, jos haluat suodattaa sivun alueen mukaan. Huomaa, että kunkin alueen kumppanit tavoittelevat merkittävästi enemmän suuria mahdollisuuksia.   
* **Mahdollisuuksien lukumäärä kumppanivedon ja mahdollisuuden koon mukaan** -pylväskaavio näyttää, että valtaosa suurista mahdollisuuksista on kumppanivetoisia, kun taas suurin osa pienistä ja keskisuurista mahdollisuuksista ei ole.
* Valitse **Mahdollisuuksien lukumäärä myyntivaiheittain** -palkkikaaviosta kukin **Myyntivaihe** yksitellen nähdäksesi aluekohtaisten lukumäärien erot. Huomaa, että vaikka itäalueella on suurin mahdollisuuksien lukumäärä, kaikilla kolmella alueella Ratkaisu-, Ehdotus- ja Viimeistely-myyntivaiheissa on verrattavissa olevat lukumäärät. Tämä tulos tarkoittaa, että sopimusten viimeistelyn prosenttiosuus on suurempi maan keski- ja länsialueilla.

### <a name="revenue-analysis-page"></a>Tuottoanalyysi-sivu
Tällä sivulla tietoja tarkastellaan samankaltaisella tavalla, mutta lukumäärän sijaan perspektiivinä on tuotto.  

![Tuoton yleiskatsaus -sivu](media/sample-opportunity-analysis/opportunity4.png)

Huomioi seuraavat tiedot:
* Itä on suurin alueemme mahdollisuuksien lukumäärän lisäksi myös tuotolla mitattuna.  
* Jos suodatat **Tuotto myyntivaiheen ja kumppanivedon mukaan** -kaavion valitsemalla **Kyllä** kohdassa **Kumppaniveto**, näet, että tuotto on 1,5 miljardia dollaria ja laskutettu tuotto 294 miljoonaa. Vertaa näitä summia muun kuin kumppanivetoisen tuoton 644 miljoonaan dollariin ja 166 miljoonaan dollariin. 
* Suurten tilien keskimääräinen tuotto on suurempi (8 miljoonaa), jos mahdollisuus on kumppanivetoinen, verrattuna muuhun kuin kumppanivetoon, jossa keskimääräinen tuotto on 6 miljoonaa.  
* Kumppanivetoisissa yrityksissä suurten mahdollisuuksien keskimääräinen tuotto on lähes kaksinkertainen keskikokoisiin mahdollisuuksiin verrattuna.  
* Pienten ja keskisuurten liiketoimien keskimääräinen tuotto on vastaava sekä kumppanivetoisessa että muussa kuin kumppanivetoisessa liiketoiminnassa.   

Kumppanit onnistuvat selvästi paremmin asiakkaille myynnissä kuin ei-kumppanit. Sopimusten kanavoiminen entistä enemmän kumppaneiden kautta voisi olla järkevää.

### <a name="opportunity-count-by-region-and-stage"></a>Mahdollisuuksien lukumäärä alueen ja vaiheen mukaan
Tällä raportin sivulla tarkastellaan samankaltaisia tietoja edellisellä sivulla, mutta ne eritellään alueen ja vaiheen mukaan. 

![Aluevaiheen määrät -sivu](media/sample-opportunity-analysis/opportunity5.png)

Huomioi seuraavat tiedot:
* Jos suodatat itäalueen valitsemalla kohdan **Itä** **Mahdollisuuksien lukumäärä alueittain** -ympyräkaaviossa, näet, että tällä alueella mahdollisuudet jakautuvat lähes tasan kumppanivetoisiin ja muihin kuin kumppanivetoisiin.
* Suuri mahdollisuudet ovat yleisimpiä keskialueella, pienet mahdollisuudet ovat yleisimpiä idässä ja keskisuuret mahdollisuudet ovat yleisimpiä lännessä.

### <a name="upcoming-opportunities-by-month-page"></a>Tulevat mahdollisuudet kuukauden mukaan -sivu
Tarkastelemme tällä sivulla samankaltaisia tekijöitä, mutta perspektiivinä on päivämäärä ja aika. 
 
![Tulevat mahdollisuudet -sivu](media/sample-opportunity-analysis/opportunity6.png)

Talousjohtajamme käyttää tätä sivua kuormitusten hallintaan. Perehtymällä tuottomahdollisuuksiin myyntivaiheen ja kuukauden mukaan hän voi suunnitella työt asianmukaisesti.

Huomioi seuraavat tiedot:
* Viimeistely-myyntivaiheessa keskimääräinen tuotto on suurin. Näiden sopimusten saaminen on etusijalla.
* Jos suodatat kuukauden mukaan (valitsemalla **Kuukausi**-osittajassa kuukauden nimen), näet, että tammikuussa suuria sopimuksia on suhteellisesti eniten Viimeistely-myyntivaiheessa ja laskutettu tuotto on 75 miljoonaa dollaria. Helmikuussa sen sijaan keskikokoisia sopimuksia on eniten Ratkaisu- ja Ehdotus-myyntivaiheissa.
* Yleensä laskutetun tuoton luvut vaihtelevat myyntivaiheen, mahdollisuuksien lukumäärän ja sopimuksen koon mukaan. Saat näkyviin lisää merkityksellisiä tietoja lisäämällä näihin tekijöihin suodattimia käyttämällä oikeassa reunassa olevaa **Suodatin**-ruutua.

## <a name="next-steps-connect-to-your-data"></a>Seuraavat vaiheet: Yhdistä tietoihisi
Tässä ympäristössä on turvallista tehdä kokeiluja, koska voit jättää tekemäsi muutokset tallentamatta. Jos kuitenkin tallennat ne, voit aina siirtyä **Nouda tiedot** -kohtaan, jolloin saat tästä mallista uuden kopion.

Toivomme, että tämä esittely on osoittanut, miten Power BI -raporttinäkymät, Q&A ja raportit voivat tarjota uusia näkökulmia mallitietoihin. Nyt on sinun vuorosi – muodosta yhteys omiin tietoihisi. Power BI:n avulla voit yhdistää useisiin eri tietolähteisiin. Lisätietoja on artikkelissa [Power BI -palvelun käytön aloittaminen](service-get-started.md).

