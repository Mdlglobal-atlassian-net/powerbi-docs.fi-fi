---
title: Raporttien tutkiminen Power BI -mobiilisovelluksissa
description: Lue lisätietoja raporttien tarkastelemisesta ja käsittelemisestä Power BI -mobiilisovelluksissa puhelimella tai tabletilla. Voit luoda raportteja Power BI -palvelussa tai Power BI Desktopissa ja käsitellä niitä sitten mobiilisovelluksissa.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 08/17/2018
ms.author: maggies
ms.openlocfilehash: 694ae2cd6f77fbcf898a984b135fb65b9163a43b
ms.sourcegitcommit: f25464d5cae46691130eb7b02c33f42404011357
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/10/2018
ms.locfileid: "53180986"
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Raporttien tutkiminen Power BI -mobiilisovelluksissa
Koskee seuraavia:

| ![iPhone](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Android-puhelin](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Android-tabletti](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Windows 10 -laitteet](./media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhonet |iPadit |Android-puhelimet |Android-tabletit |Windows 10 -laitteet |

Power BI -raportti on vuorovaikutteinen näkymä tiedoistasi, joka sisältää eri havaintoja ja merkityksellisiä tietoja esittäviä visualisointeja. Raporttien tarkasteleminen Power BI -mobiilisovelluksissa on kolmivaiheisen prosessin kolmas vaihe.

1. [Luo raportteja Power BI Desktopissa](../../desktop-report-view.md). Voit jopa [optimoida raportin puhelimille](mobile-apps-view-phone-report.md) Power BI Desktopissa. 
2. Julkaise raportit Power BI -palvelussa [(https://powerbi.com)](https://powerbi.com) tai [Power BI -raporttipalvelimessa](../../report-server/get-started.md).  
3. Käsittele niitä sitten Power BI -mobiilisovelluksissa.

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>Power BI -raportin avaaminen mobiilisovelluksessa
Power BI -raportit tallennetaan eri paikkoihin mobiilisovelluksessa sen mukaan, mistä ne ovat peräisin. Sijaintipaikka voi olla Sovellukset, Jaettu kanssani, Työtilat (myös Oma työtila) tai raporttipalvelin. Joskus sinun on käytävä läpi aiheeseen liittyvä raporttinäkymä, jotta saat raportin, ja joskus raportit on luetteloitu.

* Napauta kolmea pistettä (...) raporttinäkymän ruudun oikeassa yläkulmassa > **Avaa raportti**.
  
  ![Raportin avaaminen](./media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  Kaikissa ruuduissa ei ole raportin avaamisvaihtoehtoa. Esimerkiksi Q&A-ruudussa kysymyksiä esittämällä luodut ruudut eivät avaa raportteja, kun niitä napautetaan. 
  
  Puhelimessa raportti avautuu vaakatilassa, ellei sitä ole [optimoitu puhelimella tarkasteltavaksi](mobile-reports-in-the-mobile-apps.md#view-reports-optimized-for-phones).
  
  ![Puhelinraportti vaakatilassa](./media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-landscape.png)

## <a name="view-reports-optimized-for-phones"></a>Puhelimille optimoitujen raporttien tarkasteleminen
Power BI -raportin tekijät voivat luoda erityisesti puhelimille optimoidun raportin asettelun. Puhelimille optimoiduille raporttisivuille on lisätty toimintoja: voit esimerkiksi porautua visualisointeihin ja lajitella niitä, voit käyttää [suodattimia, jotka raportin tekijä on lisännyt raporttisivulle](mobile-apps-view-phone-report.md#filter-the-report-page-on-a-phone). Raportti avautuu puhelimessa suodatettuna verkossa olevassa raportissa suodatettuihin arvoihin ja saat ilmoituksen, että sivulla on aktiivisia suodattimia. Voit muuttaa suodattimia puhelimessasi.

Optimoidulla raportilla on erityinen kuvake raporttiluettelossa ![Puhelinraportin kuvake](./media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png):

![Avaa puhelinraportti](./media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

Kun tarkastelet raporttia puhelimessa, se avautuu pystynäkymässä.

![Raportti pystynäkymässä](./media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

 Raportissa saattaa olla sekä sivuja, jotka on optimoitu puhelimille, että sivuja, joita ei ole optimoitu. Jos näin on, raporttia selatessasi näkymä vaihtuu pystysuuntaisesta vaakasuuntaiseksi kullakin sivulla.

Lue lisätietoja [puhelinnäkymään optimoiduista raporteista](mobile-apps-view-phone-report.md).

## <a name="use-slicers-to-filter-a-report"></a>Raportin suodattaminen osittajien avulla
Kun suunnittelet raporttia Power BI Desktopissa tai Power BI -palvelussa, harkitse [osittajien lisäämistä raporttisivulle](../../visuals/power-bi-visualization-slicers.md). Sinä ja työtoverisi voitte käyttää osittajia sivun suodattamiseen selaimessa ja mobiilisovelluksissa. Kun tarkastelet raporttia puhelimessa, näet osittajat ja voit käyttää niitä vaakatilassa ja puhelimen pystytilaan optimoidulla sivulla. Jos valitset osittajan tai suodattimen arvon selaimessa, arvo valitaan myös, kun tarkastelet sivua mobiilisovelluksessa. Saat ilmoituksen siitä, että sivulla on aktiivisia suodattimia.  

* Kun valitset osittajan arvon raporttisivulla, se suodattaa sivun muut visualisoinnit.
  
  ![Raportin osittaja](./media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  Tässä kuvassa osittaja suodattaa pylväskaavion näyttämään vain heinäkuun arvot.

## <a name="cross-filter-and-highlight-a-report"></a>Raportin ristisuodatus ja korostaminen
Kun valitset arvon visualisoinnissa, se ei suodata muita visualisointeja. Se korostaa liittyvät arvot muissa visualisoinneissa.

* Napauta arvoa visualisoinnissa.
  
  ![Sivun ristisuodatus](./media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  Suuri-sarakkeen napauttaminen visualisoinnissa korostaa liittyvät arvot muissa visualisoinneissa. 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>Visualisoinnin lajitteleminen iPadilla tai tabletilla
* Napauta kaaviota, valitse kolme pistettä (**...**) ja napauta kentän nimeä.
  
   ![Visualisoinnin lajitteleminen](./media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* Voit muuttaa lajittelujärjestyksen käänteiseksi napauttamalla kolmea pistettä (**...**) uudelleen ja valitsemalla saman kentän nimen.

## <a name="drill-down-and-up-in-a-visual"></a>Porautuminen alas- ja ylöspäin visualisoinnissa
Jos raportin tekijä on lisännyt porautumisominaisuuden visualisointiin, voit porautua visualisointiin nähdäksesi arvot, jotka muodostavat osan siitä. Voit [lisätä alaspäin porautumisen visualisointiin](../end-user-drill.md) Power BI Desktopissa tai Power BI -palvelussa. 

* Kosketa haluamaasi visualisoinnin palkkia tai pistettä pitkään nähdäksesi sen työkaluvihjeen. Jos siihen voi porautua, alemmassa työkaluvihjeessä on napautettavissa olevia nuolia. 
  
  ![Porautuminen alaspäin visualisoinnissa](./media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-tooltip.png)

* Porautuaksesi takaisin ylös, napauta ylöspäin osoittavaa nuolta työkaluvihjeessä.
  
  ![Porautuminen ylöspäin](./media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-tooltip.png)

* Voit porautua alaspäin kaikissa visualisoinnin arvopisteissä. Avaa kohdistustila, napauta tutkimiskuvaketta ja valitse sitten näytä kaikki seuraavalla tasolla, tai laajenna nähdäksesi nykyisen ja seuraavan tason.

   ![Power BI poraudu alaspäin kaikissa](./media/mobile-reports-in-the-mobile-apps/power-bi-drill-down-all.png)

## <a name="drill-through-from-one-page-to-another"></a>Poraudu yhden sivun läpi seuraavaan

Kun napautat tiettyä kohtaa visualisoinnissa, voit *porautumalla* siirtyä Power BI:ssä raportin eri sivulle, joka suodatetaan napauttamasi arvon mukaisesti. Raportin tekijä voi määrittää yhden tai useampia porautumisvaihtoehtoja, joista jokainen siirtää sinut eri sivulle. Voit siinä tapauksessa valita mihin sivuun haluat porautua. Seuraavassa esimerkissä, napauttaessasi mittarin arvoa, voit valita poraudutko joko **käyttö liiketoiminta-alueen mukaan**-sivulle vai **suunnittelu liiketoiminta-alueen mukaan**-sivulle.

![Porautuminen raportissa Power BI -mobiilisovelluksessa](./media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-through-it-spent-report.png)

Takaisin-painike vie sinut takaisin raportin edelliselle sivulle.

Lue lisää [porautumisen lisäämisestä Power BI Desktopiin](../../desktop-drillthrough.md).

## <a name="show-data-and-copy-values"></a>Tietojen näyttäminen ja arvojen kopioiminen

Voit tarkastella visualisoinnin taustalla olevia tietoja valitsemalla valikkoasetusten kolme pistettä (**...**) visualisoinnin oikeasta yläkulmasta puhelinraportissa. Valitse sen jälkeen **Näytä tiedot**.

![Power BI -mobiilisovelluksen Näytä tiedot -valikkovaihtoehto](./media/mobile-reports-in-the-mobile-apps/copy-data-visual.png)

Esitetyn taulukon solun pitkä napautus tuo näkyviin alkuperäisen valinta- ja kopiointivalikon, joten voit valita kopioitavat tiedot taulukosta (tai taulukon kokonaan).

![Porautuminen raportissa Power BI -mobiilisovelluksessa](./media/mobile-reports-in-the-mobile-apps/copy-data-table.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Puhelimelle optimoitujen Power BI -raporttien tarkasteleminen ja käyttäminen](mobile-apps-view-phone-report.md)
* [Puhelimille optimoidun raporttiversion luominen](../../desktop-create-phone-report.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

