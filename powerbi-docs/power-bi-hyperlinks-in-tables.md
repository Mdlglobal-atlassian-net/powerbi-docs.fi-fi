---
title: Hyperlinkin lisääminen taulukkoon
description: Taulukoiden hyperlinkit
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 01/22/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: d696a7492f1295f2e2c9b39088b0eacdb66b15ca
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34310172"
---
# <a name="hyperlinks-in-tables"></a>Taulukoiden hyperlinkit
Tässä aiheessa kurssilla opit käyttämään Power BI Desktopia hyperlinkkien luomiseen. Kun olet luonut hyperlinkit, voit lisätä ne raportin taulukoihin ja matriiseihin Power BI Desktopissa tai -palvelussa. 

![](media/power-bi-hyperlinks-in-tables/hyperlinkedtable.png)

> **Huom.** Hyperlinkit voidaan luoda lennosta [koontinäyttöjen ruutuihin](service-dashboard-edit-tile.md) ja [niiden tekstikenttiin](service-dashboard-add-widget.md) Power BI -palvelussa. [Raporttien tekstiruutuihin](service-add-hyperlink-to-text-box.md) voi luoda hyperlinkkejä lennosta Power BI -palvelussa ja Power BI Desktopissa.
> 
> 

## <a name="to-create-a-hyperlink-in-a-table-or-matrix-using-power-bi-desktop"></a>Hyperlinkin luominen taulukkoon tai matriisiin Power BI Desktopilla
Taulukoihin ja matriiseihin voi luoda hyperlinkkejä Power BI Desktopilla, mutta ei Power BI -palvelusta. Hyperlinkkejä myös voi luoda Excel Power Pivotilla ennen työkirjan tuomista Power BI:hin. Menetelmät on kuvailtu alla.

## <a name="create-a-table-or-matrix-hyperlink-in-power-bi-desktop"></a>Hyperlinkin luominen taulukkoon tai matriisiin Power BI Desktopilla
Hyperlinkin lisäämisen menettely riippuu siitä, oletko tuonut tiedot vai yhdistänyt niihin DirectQueryllä. Molemmat keinot on kuvattu alla.

### <a name="for-data-imported-into-power-bi"></a>Power BI:hin tuodut tiedot
1. Jos hyperlinkkiä ei vielä ole tietojoukon kenttänä, lisää se [mukautettuna sarakkeena](desktop-common-query-tasks.md) Desktopissa.
2. Valitse sarake Tiedot-näkymässä ja sitten **Mallinnus**-välilehdeltä avattava **Tietoluokka**-valikko.
   
    ![](media/power-bi-hyperlinks-in-tables/pbi_data_category.png)
3. Valitse **URL-verkko-osoite**.
4. Siirry Raporttinäkymään ja luo taulukko tai matriisi URL-verkko-osoitteeksi luokiteltuun kenttään. Hyperlinkit näkyvät sinisinä ja alleviivattuina.
   
    ![](media/power-bi-hyperlinks-in-tables/power-bi-table-with-hyperlinks2.png)
5. Jos et halua taulukossa näkyvän pitkiä URL-osoitteita, voit näyttää niiden sijaan hyperlinkkikuvakkeen ![](media/power-bi-hyperlinks-in-tables/power-bi-hyperlink-icon.png). Huomaa, matriiseissa ei voi näyttää kuvakkeita.
   
   * Valitse kaavio, jotta se on aktiivinen.
   * Avaa Muotoilu-välilehti valitsemalla maalitelakuvake ![](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png).
   * Laajenna **Arvot**, etsi **URL-osoitekuvake** ja ota se **käyttöön.**
6. (Valinnainen) [Julkaise raportti Desktopista Power BI -palveluun](guided-learning/publishingandsharing.yml?tutorial-step=2) ja avaa raportti Power BI -palvelussa. Hyperlinkit toimivat myös siellä.

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
   
   ![](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot2.png)
3. Kun PowerPivot avautuu, valitse **Lisäasetukset**-välilehti.
   
   ![](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot3.png)
4. Aseta kohdistin sarakkeeseen, joka sisältää ne URL-osoitteet, jonka haluaisit muuttaa hyperlinkeiksi Power BI -taulukoissa.
   
   > **Huom.** URL-osoitteiden on alussa on oltava **http://-, https://-** tai **www**-etuliite.
   > 
   > 
5. Valitse **Raportointiominaisuudet**-ryhmästä avattava **Tietoluokka**-valikko ja valitse **URL-verkko-osoite**. 
   
   ![](media/power-bi-hyperlinks-in-tables/createhyperlinksnew.png)
6. Muodosta yhteys tähän työkirjaan tai tuo se Power BI -palvelussa tai Power BI Desktopissa.
7. Luo taulukon visualisointi, joka sisältää URL-kentän.
   
   ![](media/power-bi-hyperlinks-in-tables/hyperlinksintables.gif)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
K: Voinko käyttää mukautettua URL-osoitetta taulukon tai matriisin hyperlinkkinä?    
V: Et. Voit käyttää linkkikuvaketta. Jos haluat käyttää mukautettua tekstiä hyperlinkkinä ja URL-osoitteiden luettelo on lyhyt, kokeile käyttää tekstiruutua.


## <a name="next-steps"></a>Seuraavat vaiheet
[Visualisoinnit Power BI -raporteissa](power-bi-report-visualizations.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
