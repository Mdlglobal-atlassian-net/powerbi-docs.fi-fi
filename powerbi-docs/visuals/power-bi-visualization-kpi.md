---
title: Suorituskykyilmaisimen (KPI) visualisoinnit
description: Suorituskykyilmaisimen (KPI) visualisoinnit Power BI:ssä
author: mihart
ms.reviewer: ''
featuredvideoid: xmja6EpqaO0
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 42a9f2c641a0cdac9b7a129ffc5ecc6f7fb8cf8d
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73870858"
---
# <a name="key-performance-indicator-kpi-visuals"></a>Suorituskykyilmaisimen (KPI) visualisoinnit

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Suorituskykyilmaisin (KPI) on visuaalinen vihje, joka kertoo edistymisen määrän kohti mitattavissa olevaa tavoitetta. Lisätietoja suorituskykyilmaisimista on artikkelissa [Suorituskykyilmaisimet (KPI) PowerPivotissa](/previous-versions/sql/sql-server-2012/hh272050(v=sql.110)).

Will näyttää sivulle, miten voit luoda yksittäisten arvojen visualisoinnit: mittarit, kortit ja suorituskyvyn mittarit.
   > [!NOTE]
   > Tässä videossa käytetään Power BI Desktopin vanhempaa versiota.
   > 
   > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="when-to-use-a-kpi"></a>Milloin suorituskykyilmaisinta kannattaa käyttää?

Suorituskykyilmaisin on hyvä vaihtoehto, kun halutaan

* Mitata edistymistä. Vastata kysymykseen ”Mitä olen edellä tai jäljessä?”.

* Mitata etäisyyttä tavoitteeseen. Vastata kysymykseen ”Kuinka paljon edellä tai jäljessä olen?”.

## <a name="kpi-requirements"></a>Suorituskykyilmaisimia koskevat vaatimukset

Suunnittelija käyttää KPI-visualisoinnin pohjana tiettyä mittaria. Suorituskykyilmaisimen tarkoituksena on auttaa sinua arvioimaan mittarin nykyistä arvoa ja tilaa verrattuna määritettyyn tavoitteeseen. Siksi suorituskykyilmaisimen visualisointi edellyttää *perustason* mittaria, joka tekee arvioinnin arvoon, *kohde*mittariin tai arvoon ja *raja-arvoon* tai *tavoitteeseen*.

KPI-tietojoukon pitää sisältää suorituskykyilmaisimen tavoitearvoja. Jos tietojoukko ei sisällä tavoitearvoja, voit luoda niitä lisäämällä tietomalliin tai PBIX-tiedostoon Excel-laskentataulukon, jossa on tavoitteita.

## <a name="prerequisites"></a>Edellytykset

Tässä opetusohjelmassa käytetään [Jälleenmyyntianalyysimallin PBIX-tiedostoa](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**

1. **Jälleenmyyntianalyysimallin PBIX-tiedoston löytäminen**

1. Avaa **jälleenmyyntianalyysimallin PBIX-tiedosto** raporttinäkymässä. ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png)

1. Lisää uusi sivu valitsemalla **+** . ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png)

## <a name="how-to-create-a-kpi"></a>Suorituskykyilmaisimen luominen

Tässä esimerkissä luomme suorituskykyilmaisimen, joka mittaa edistymistä kohti myyntitavoitetta.

1. Valitse **Kentät**-ruudussa **Myynti > Yksikköjen kokonaismäärä tänä vuonna**.  Tämä arvo on ilmaisin.

1. Lisää **Aika > FiscalMonth**.  Tämä arvo edustaa trendiä.

1. Valitse visualisoinnin oikeasta yläkulmasta kolme pistettä (...) ja tarkista, että Power BI lajittelee sarakkeet nousevaan järjestykseen **FiscalMonth**-arvon mukaan.

    > [!IMPORTANT]
    > Kun muunnat visualisoinnin suorituskykyilmaisimeksi, lajitteluvaihtoehtoa **ei** ole. Sinun täytyy lajitella se oikein nyt.

    ![Näyttökuva kolmen pisteen (...) laajennetusta valikosta, jossa on valittuna Lajittele nousevaan järjestykseen ja FiscalMonth.](media/power-bi-visualization-kpi/power-bi-ascending-by-fiscal-month.png)

    Kun visualisointi on lajiteltu oikein, se näyttää tältä:

    ![Näyttökuva oikein lajitellusta visualisoinnista.](media/power-bi-visualization-kpi/power-bi-chart.png)

1. Muunna visualisointi suorituskykyilmaisimeksi valitsemalla **suorituskykyilmaisimen** kuvake **Visualisointi**-ruudusta.

    ![Näyttökuva Visualisoinnit-ruudusta, jossa on korostettu suorituskykyilmaisimen kuvake.](media/power-bi-visualization-kpi/power-bi-kpi-template.png)

1. Lisää tavoite vetämällä **Yksikköjen kokonaismäärä viime vuonna** **Kohdetavoitteet**-kenttään.

    ![Näyttökuva valmiista suorituskykyilmaisimen visualisoinnista ja Kentät-ruudusta, jossa on esitetty arvot.](media/power-bi-visualization-kpi/power-bi-kpi-done.png)

1. Vaihtoehtoisesti voit muotoilla suorituskykyilmaisimen avaamalla muotoiluruudun valitsemalla maalitelakuvakkeen.

    * **Ilmaisin** – ohjaa ilmaisimen näyttöyksiköitä ja desimaaleja.

    * **Trendiakseli** – kun arvona on **Käytössä**, visualisointi näyttää trendiakselin suorituskykyilmaisimen visualisoinnin taustalla.  

    * **Tavoitteet** – kun arvona on **Käytössä**, visualisointi näyttää tavoitteen ja etäisyyden tavoitteesta prosenttilukuna.

    * **Värikoodaus > Suunta** – joitakin suorituskykyilmaisimia pidetään parempina *suuremmille* arvoille ja joitakin pidetään parempina *pienemmille* arvoille. Esimerkiksi tulot vs. odotusaika. Yleensä tulojen suurempi arvo on parempi verrattuna odotusajan suurempaan arvoon. Valitse **suuri on parempi**, ja muuta vaihtoehtoisesti väriasetuksia.

Suorituskykyilmaisimet ovat saatavilla Power BI -palvelussa ja mobiililaitteissa. Sen avulla voit olla aina yhteydessä liiketoimintasi sykkeeseen.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

Jos suorituskykyilmaisimesi ei näytä samalta kuin yksi edellisistä, se johtuu ehkä siitä, ettet lajitellut sitä **FiscalMonth**-arvon mukaan. Suorituskykyilmaisimissa ei ole lajitteluvaihtoehtoa. Sinun täytyy aloittaa uudestaan ja lajitella **FiscalMonth**-arvon mukaan *ennen* visualisoinnin muuntamista suorituskykyilmaisimeksi.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Vinkkejä Power BI -karttavisualisoinneille](power-bi-map-tips-and-tricks.md)

* [Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
