---
title: Suorituskykyilmaisimien visualisoinnit
description: Suorituskykyilmaisimen luominen Power BI -palvelussa ja Power BI Desktopissa
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: xmja6EpqaO0
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 2fc84d82e67b1c1e4a4b37655a13bd5415abf816
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34292589"
---
# <a name="kpi-visuals"></a>Suorituskykyilmaisimien visualisoinnit
Suorituskykyilmaisin (KPI) on visuaalinen vihje, joka kertoo edistymisen määrän kohti mitattavissa olevaa tavoitetta. Katso lisätietoja suorituskykyilmaisimista [Microsoft Developer Networkista](https://msdn.microsoft.com/library/hh272050).

## <a name="when-to-use-a-kpi"></a>Milloin suorituskykyilmaisinta kannattaa käyttää?
Suorituskykyilmaisin on hyvä vaihtoehto, kun halutaan

* mitata edistymistä (minkä edellä vai jäljessä olen?)
* mitata etäisyyttä tavoitteeseen (kuinka paljon edellä tai jäljessä olen?)   

## <a name="kpi-visual-requirements"></a>Suorituskykyilmaisimen visuaaliset vaatimukset
Suorituskykyilmaisin perustuu tiettyyn mittayksikköön, ja se on suunniteltu mittayksikön nykyisen arvon ja tilan arviointiin määritettyyn kohteeseen verrattuna. Siksi suorituskykyilmaisimen visualisointi edellyttää *perustason* mittayksikköä, joka tekee arvioinnin arvoon ja *kohde*mittayksikköön tai arvoon ja raja-arvoon tai tavoitteeseen.

> [!NOTE]
> Tällä hetkellä suorituskykyilmaisimen tietojoukon pitää sisältää suorituskykyilmaisimen tavoitearvoja. Jos tietojoukko ei sisällä niitä, voit luoda tavoitteita lisäämällä tietomalliin tai PBIX-tiedostoon Excel-taulukon, jossa on tavoitteita.
> 
> 

## <a name="how-to-create-a-kpi"></a>Suorituskykyilmaisimen luominen
Seurataksesi kirjaudu Power BI -palveluun ja valitse **Nouda tiedot > Mallit > Jälleenmyyntianalyysimalli**. Luomme suorituskykyilmaisimen, joka mittaa edistymisen kohti myynnin tavoitetta.

Tai kello näyttää, miten voit luoda yksittäisten arvojen visualisoinnit: mittarit, kortit ja suorituskyvyn mittarit.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Avaa raportti [muokkausnäkymässä](service-reading-view-and-editing-view.md) ja [lisää uusi sivu](power-bi-report-add-page.md).    
2. Valitse **Myynti > Yksikköjen kokonaismäärä tänä vuonna**.  Tämä on ilmaisin.
3. Lisää **Kellonaika > Kuukausi**.  Tämä edustaa trendiä.
4. TÄRKEÄÄ: Lajittele kaavio **kuukauden** mukaan. Kun muunnat visualisoinnin suorituskykyilmaisimeksi, lajitteluvaihtoehtoa ei ole.

    ![](media/power-bi-visualization-kpi/power-bi-sort-by-month.png)
5. Muunna visualisointi suorituskykyilmaisimeksi valitsemalla suorituskykyilmaisimen kuvake Visualisointi-ruudusta.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi-icon.png)
6. Lisää tavoite. Lisää edellisen vuoden myynti tavoitteeksi. Vedä **Yksikköjen kokonaismäärä viime vuonna** **Kohdetavoitteet**-kenttään.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi.png)
7. Vaihtoehtoisesti voit muotoilla suorituskykyilmaisimen avaamalla muotoiluruudun valitsemalla maalitelakuvakkeen.
   
   * **Ilmaisin** – ohjaa ilmaisimen näyttöyksiköitä ja desimaaleja.
   * **Trendiakseli** – kun arvona on **Käytössä**, trendiakseli näkyy suorituskykyilmaisimen visualisoinnin taustalla.  
   * **Tavoitteet** – kun arvona on **Käytössä**, visualisointi näyttää tavoitteen ja etäisyyden tavoitteesta prosenttilukuna.
   * **Värikoodaus > Suunta** – joitakin suorituskykyilmaisimia pidetään *parempina* suuremmille arvoille ja joitakin pidetään *parempina* pienemmille arvoille. Esimerkiksi tulot vs. odotusaika. Yleensä tulojen suurempi arvo on parempi verrattuna odotusajan suurempaan arvoon. Valitse **suuri on parempi**, ja voit myös muuttaa väriasetuksia.

1. Kun suorituskykyilmaisimessa on haluamasi asetukset, [kiinnitä se koontinäyttöön](service-dashboard-pin-tile-from-report.md).

Suorituskykyilmaisimet ovat myös käytettävissä mobiililaitteissa – voit siis aina olla yhteydessä liiketoimintasi sykkeeseen.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
* Jos suorituskykyilmaisimesi ei näytä samalta kuin edellä, sinun täytyy ehkä lajitella kuukauden mukaan. Koska suorituskykyilmaisimissa ei ole lajitteluasetusta, sinun täytyy lajitella kuukauden mukaan *ennen* visualisoinnin muuntamista suorituskykyilmaisimeksi.

## <a name="next-steps"></a>Seuraavat vaiheet

[Visualisoinnit Power BI -raporteissa](power-bi-report-visualizations.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

