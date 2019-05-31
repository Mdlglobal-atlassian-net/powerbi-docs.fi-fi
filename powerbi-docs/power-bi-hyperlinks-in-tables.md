---
title: Hyperlinkkien lisääminen taulukkoon
description: Power BI Desktopin avulla voit luoda hyperlinkkejä. Käytä sitten hyperlinkkejä voi lisätä ne raportin taulukoihin ja matriiseihin Power BI Desktop- tai Power BI-palvelussa.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/09/2019
ms.author: maggies
LocalizationGroup: Visualizations
ms.openlocfilehash: 9611d8cd45eba89854fd6cbb485c52097f77f4c0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61421575"
---
# <a name="add-hyperlinks-to-a-table"></a>Hyperlinkkien lisääminen taulukkoon
Tässä aiheessa kurssilla opit käyttämään Power BI Desktopia hyperlinkkien luomiseen. Voit sitten lisätä nämä hyperlinkit raportin taulukoihin ja matriiseihin joko Desktopissa tai Power BI -palvelussa. 

![Taulukko, jossa on hyperlinkit](media/power-bi-hyperlinks-in-tables/hyperlinkedtable.png)

> [!NOTE]
> Voit luoda hyperlinkit [koontinäyttöjen ruutuihin](service-dashboard-edit-tile.md) ja [tekstikenttiin](service-dashboard-add-widget.md) -saman Power BI-palveluun. Voit luoda hyperlinkit [raporttien tekstiruutuihin](service-add-hyperlink-to-text-box.md) -saman käyttämällä Power BI-palvelussa ja Power BI Desktop.
> 

## <a name="to-create-a-hyperlink-in-a-table-or-matrix-using-power-bi-desktop"></a>Hyperlinkin luominen taulukkoon tai matriisiin Power BI Desktopilla
Voit luoda hyperlinkit taulukoihin ja matriiseihin Power BI Desktop, mutta ei Power BI-palvelussa. Voit myös luoda hyperlinkkejä Excelin Power Pivot-, ennen kuin tuot työkirjan Power BI. Menetelmät on kuvailtu alla.

## <a name="create-a-table-or-matrix-hyperlink-in-power-bi-desktop"></a>Hyperlinkin luominen taulukkoon tai matriisiin Power BI Desktopilla
Hyperlinkin lisäämisen menettely riippuu siitä, oletko tuonut tiedot vai yhdistänyt niihin DirectQueryllä. Molemmat keinot on kuvattu alla.

### <a name="for-data-imported-into-power-bi"></a>Power BI:hin tuodut tiedot
1. Jos hyperlinkkiä ei vielä ole tietojoukon kenttänä, lisää se [mukautettuna sarakkeena](desktop-common-query-tasks.md) Desktopissa.
2. Valitse sarake Tiedot-näkymässä ja sitten **Mallinnus**-välilehdeltä avattava **Tietoluokka**-valikko.
   
    ![Tietoluokan avattavan valikon luettelo](media/power-bi-hyperlinks-in-tables/pbi_data_category.png)
3. Valitse **URL-verkko-osoite**.
4. Siirry Raporttinäkymään ja luo taulukko tai matriisi URL-verkko-osoitteeksi luokiteltuun kenttään. Hyperlinkit näkyvät sinisinä ja alleviivattuina.

    ![Siniset ja alleviivatut linkit](media/power-bi-hyperlinks-in-tables/power-bi-table-with-hyperlinks2.png)

    > [!NOTE]
    > URL-osoitteiden alussa on oltava **http://, https://** tai **www**.
    >
   
1. Jos et halua taulukossa näkyvän pitkää URL-osoitetta, voit näyttää sen sijaan  ![Hyperlinkkikuvake](media/power-bi-hyperlinks-in-tables/power-bi-hyperlink-icon.png) hyperlinkkikuvakkeen. Huomaa, matriiseissa ei voi näyttää kuvakkeita.
   
    Valitse kaavio, jotta se on aktiivinen.

    Valitse Muotoilu-kuvake ![Maalirullakuvake](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png) Muotoilu-välilehden avaamiseksi.

    Laajenna **Arvot**, etsi **URL-osoitekuvake** ja ota se **käyttöön.**

    ![Ota käyttöön URL-kuvake](media/power-bi-hyperlinks-in-tables/power-bi-url-icon-on.png)

1. (Valinnainen) [Julkaise raportti Desktopista Power BI -palveluun](guided-learning/publishingandsharing.yml?tutorial-step=2) ja avaa raportti Power BI -palvelussa. Hyperlinkit toimivat myös siellä.

### <a name="for-data-connected-with-directquery"></a>DirectQueryyn yhdistetyt tiedot
Et voi luoda uutta saraketta DirectQuery-tilassa.  Jos tiedoissasi kuitenkin on jo URL-osoitteita, voit muuttaa ne hyperlinkeiksi.

1. Luo Raporttinäkymässä taulukko käyttämällä URL-osoitteita sisältävää kenttää.
2. Valitse sarake Tiedot-näkymässä ja sitten **Mallinnus**-välilehdeltä avattava **Tietoluokka**-valikko.
3. Valitse **URL-verkko-osoite**. Hyperlinkit näkyvät sinisinä ja alleviivattuina.
4. (Valinnainen) [Julkaise raportti Desktopista Power BI -palveluun](guided-learning/publishingandsharing.yml?tutorial-step=2) ja avaa raportti Power BI -palvelussa. Hyperlinkit toimivat myös siellä.

## <a name="create-a-table-or-matrix-hyperlink-in-excel-power-pivot"></a>Hyperlinkin luominen taulukkoon tai matriisiin Excel Power Pivotilla
Toinen tapa lisätä hyperlinkkejä Power BI -taulukoihin ja -matriiseihin on luoda hyperlinkit tietojoukkoon ennen kyseisen tietojoukon tuomista Power BI:hin tai siihen liittämistä Power BI:ssä. Tässä esimerkissä käytetään Excel-työkirjaa.

1. Avaa työkirja Excelissä.
2. Valitse **PowerPivot**-välilehti ja valitse sitten **Hallinta**.
   
   ![Avaa PowerPivot Excelissä](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot2.png)
1. Kun PowerPivot avautuu, valitse **Lisäasetukset**-välilehti.
   
   ![PowerPivotin Lisäasetukset-välilehti](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot3.png)
4. Aseta kohdistin sarakkeeseen, joka sisältää ne URL-osoitteet, jonka haluaisit muuttaa hyperlinkeiksi Power BI -taulukoissa.
   
   > [!NOTE]
   > URL-osoitteiden alussa on oltava **http://, https://** tai **www**.
   > 
5. Valitse **Raportointiominaisuudet**-ryhmästä avattava **Tietoluokka**-valikko ja valitse **URL-verkko-osoite**. 
   
   ![Tietoluokan avattava valikko Excelissä](media/power-bi-hyperlinks-in-tables/createhyperlinksnew.png)

6. Muodosta yhteys tähän työkirjaan tai tuo se Power BI -palvelussa tai Power BI Desktopissa.
7. Luo taulukon visualisointi, joka sisältää URL-kentän.
   
   ![Luo taulukko Power BI:ssä URL-kentän kanssa](media/power-bi-hyperlinks-in-tables/hyperlinksintables.gif)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Kysymys: Voinko käyttää mukautettua URL-osoitetta taulukon tai matriisin hyperlinkkinä?    
Vastaus: Ei. Voit käyttää linkkikuvaketta. Jos haluat käyttää mukautettua tekstiä hyperlinkkinä ja URL-osoitteiden luettelo on lyhyt, kokeile käyttää tekstiruutua.


## <a name="next-steps"></a>Seuraavat vaiheet
[Visualisoinnit Power BI -raporteissa](visuals/power-bi-report-visualizations.md)

[Power BI:n peruskäsitteet](consumer/end-user-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

