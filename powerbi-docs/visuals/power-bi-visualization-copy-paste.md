---
title: Visualisoinnin kopioiminen ja liittäminen Power BI:ssä
description: Visualisoinnin kopioiminen ja liittäminen Power BI:ssä
author: mihart
ms.reviewer: maggie tsang
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/13/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 03ce7f2a8ccd2c453521d28d172ffb25c1bb28bf
ms.sourcegitcommit: b2cb0b02bdc451bf11a92a68f2c4d560a811f563
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/16/2020
ms.locfileid: "81440134"
---
# <a name="copy-and-paste-a-report-visualization"></a>Raporttivisualisoinnin kopioiminen ja liittäminen

[!INCLUDE[consumer-appliesto-yyyn](../includes/consumer-appliesto-yyyn.md)]

Tässä artikkelissa käsitellään kahta eri tapaa kopioida ja liittää visualisointi. 
* Visualisointi voidaan kopioida raporttiin ja liittää toiselle raporttisivulle (edellyttää raportin muokkausoikeuksia).

* Visualisoinnin kuva voidaan liittää Power BI:stä leikepöydälle ja liittää muihin sovelluksiin.

## <a name="copy-and-paste-within-the-same-report"></a>Kopioiminen ja liittäminen samassa raportissa
Power BI -raporttien visualisoinnit voidaan kopioida raportin yhdeltä sivulta samalle sivulle tai saman raportin eri sivulle. 

Visualisoinnin kopioiminen ja liittäminen edellyttävät raportin muokkausoikeuksia. Power BI -palvelussa tämä tarkoittaa raportin avaamista [muokkausnäkymässä](../consumer/end-user-reading-view.md). 

*Koontinäyttöjen* visualisointeja ei voi kopioida ja liittää Power BI -raportteihin tai muihin koontinäyttöihin.

1. Avaa raportti, jossa on vähintään yksi visualisointi.  

2. Valitse visualisointi ja kopioi se valitsemalla **Ctrl+C** tai liitä se valitsemalla **Ctrl+V**.      

   ![lyhyt video, jossa näytetään, miten voit kopioida ja liittää](media/power-bi-visualization-copy-paste/copypasteviznew.gif)


## <a name="copy-a-visual-as-an-image-to-your-clipboard"></a>Visualisoinnin kopioiminen leikepöydälle kuvana

Oletko koskaan halunnut jakaa kuvaa Power BI -raportista tai koontinäytöstä? Voit nyt kopioida visualisoinnin ja liittää sen mihin tahansa muuhun sovellukseen, joka tukee liittämistä. 

Kun kopioit visualisoinnin staattisen kuvan, saat visualisoinnin kopion yhdessä metatietojen kanssa. Näihin sisältyvät:
* linkki takaisin Power BI -raporttiin tai koontinäyttöön
* raportin tai koontinäytön otsikko
* ilmoitus siitä, sisältääkö kuva luottamuksellisia tietoja
* viimeisimmän päivityksen aikaleima
* visualisoinnissa käytetyt suodattimet.

### <a name="copy-from-a-dashboard-tile"></a>Kopioiminen koontinäytön yksittäisestä ruudusta

1. Siirry koontinäyttöön, josta haluat kopioida.

2. Valitse visualisoinnin oikeasta yläkulmasta **Lisää asetuksia (...)** ja valitse **Kopioi visualisointi kuvana**. 

    ![Kopioi visualisointi kuvana -kuvake näkyvissä](media/power-bi-visualization-copy-paste/power-bi-copy-dashboard.png)

3. Kun **Visualisointisi on valmiina kopioitavaksi** -valintaikkuna avautuu, valitse **Kopioi leikepöydälle**.

    ![valintaikkuna, jossa on kopioi leikepöydälle -asetus](media/power-bi-visualization-copy-paste/power-bi-copied.png)

4. Kun visualisointisi on valmis, liitä se toiseen sovellukseen **Ctrl+V**-näppäinyhdistelmällä tai napsauttamalla hiiren kakkospainiketta ja valitsemalla Liitä. Alla olevassa näyttökuvassa visualisointi on liitetty Microsoft Wordiin. 

    ![Outlookiin liitetty visualisointi](media/power-bi-visualization-copy-paste/power-bi-paste-word.png)

### <a name="copy-from-a-report-visual"></a>Kopioiminen raportin yksittäisestä visualisoinnista 

1. Siirry raporttiin, josta haluat kopioida.

2. Valitse visualisoinnin oikeasta yläkulmasta **Kopioi visualisointi kuvana**. 

    ![Kopioi visualisointi kuvana -kuvake näkyvissä](media/power-bi-visualization-copy-paste/power-bi-copy-icon.png)

3. Kun **Visualisointisi on valmiina kopioitavaksi** -valintaikkuna avautuu, valitse **Kopioi leikepöydälle**.

    ![valintaikkuna, jossa on kopioi leikepöydälle -asetus](media/power-bi-visualization-copy-paste/power-bi-copied.png)


4. Kun visualisointisi on valmis, liitä se toiseen sovellukseen **Ctrl+V**-näppäinyhdistelmällä tai napsauttamalla hiiren kakkospainiketta ja valitsemalla Liitä. Alla olevassa näyttökuvassa visualisointi on liitetty sähköpostiviestiin.

    ![Outlookiin liitetty visualisointi](media/power-bi-visualization-copy-paste/power-bi-copy-email.png)

5. Jos raportissa on käytössä tietojen luottamuksellisuustunniste, näyttöön tulee varoitus, kun valitset kopiointikuvakkeen.  

    ![luottamuksellisten tietojen varoitus](media/power-bi-visualization-copy-paste/power-bi-sensitive.png)

    Lisäksi luottamuksellisuustunniste lisätään metatietoihin liitetyn visualisoinnin alapuolelle. 

    ![visualisointi, jossa on luottamuksellisten tietojen tunniste](media/power-bi-visualization-copy-paste/power-bi-confidential.png)

### <a name="manage-use-of-copying-a-visual-as-an-image"></a>Kopioi visualisointi kuvana -toiminnon hallinta
Jos omistat sisällön tai olet vuokraajan järjestelmänvalvoja, voit määrittää, voidaanko visualisointi kopioida kuvana raportista tai koontinäytöstä.

#### <a name="disable-copy-as-an-image-for-a-specific-visual"></a>Kopioi visualisointi kuvana -toiminnon poistaminen tietyn visualisoinnin kohdalla
Jos et halua, että käyttäjät pystyvät kopioimaan tietyn visualisoinnin, voit poistaa kopiointikuvakkeen kyseisestä visualisoinnista.
1. Avaa Muotoilu-ruutu valitsemalla maalitelakuvake. 

1. Avaa **visualisoinnin muotoilun** kortti.
1. Vieritä alaspäin kohtaan **Visualisoinnin otsikko**, laajenna kortti ja poista **kopiointikuvake** käytöstä.

    ![maalirulla valittuna ja kopiointikuvake valittuna](media/power-bi-visualization-copy-paste/power-bi-visual-header.png)

1. Jos et löydä **Visualisoinnin otsikko** -asetusta, ota käyttöön modernin visualisoinnin otsikko **Raporttiasetukset** -kohdassa. 

    ![ota käyttöön moderni visualisoinnin otsikko valittuna](media/power-bi-visualization-copy-paste/power-bi-use-modern.png)

1. Tallenna muutokset. Jaa ja julkaise uudelleen tarpeen mukaan.

#### <a name="disable-copy-as-an-image-for-a-group-of-users"></a>Kopioi visualisointi kuvana -toiminnon poistaminen käyttäjäryhmän kohdalla

Jos omistat sisällön tai olet vuokraajan järjestelmänvalvoja, voit määrittää, ketkä voivat kopioida visualisointeja. Tämä asetus poistaa käytöstä *visualisoinnin kopioinnin kuvana* kaikesta sisällöstä, jota käyttäjä käyttää Power BI -vuokraajassa.
  
1. Siirry hallintaportaaliin.

1. Valitse **Vuokraaja-asetukset**-kohdassa **Vienti-ja jakamisasetukset**. 

    ![ota käyttöön Visualisointien kopioiminen ja liittäminen](media/power-bi-visualization-copy-paste/power-bi-enable.png)

1. Poista **Visualisointien kopioiminen ja liittäminen** käytöstä valituilta käyttäjäryhmiltä. 

1. Tallenna muutokset, jolloin määritetyt ryhmät eivät voi käyttää **Kopioi visualisointi kuvana** -toimintoa Power BI:ssä. 
  

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

   ![kopiointi ei ole käytettävissä](media/power-bi-visualization-copy-paste/power-bi-copy-grey.png)


Kysymys: Miksi kopiointikuvake on poistettu käytöstä visualisoinnissa?    
Vastaus: Tuemme tällä hetkellä alkuperäisiä Power BI -visualisointeja ja sertifioituja visualisointeja. Tietyille visualisoinneille on rajallinen tuki, mukaan lukien: 
- ESRI ja muut karttavisualisoinnit 
- Python-visualisoinnit 
- R-visualisoinnit 
- PowerApps 
- Ei-sertifioituja mukautettuja visualisoinnit mukautetulle visualisoinnillesi tuetaan, lue lisätietoja siitä, [miten voit sertifioida mukautetun visualisoinnin](../developer/visuals/power-bi-custom-visuals-certified.md). 


Kysymys: Miksi visualisointia ei liitetä oikein?    
Vastaus: Kopioi visualisointi kuvana -toiminnossa on esimerkiksi seuraavia rajoituksia: 
- Mukautetut visualisoinnit 
    - visualisoinnit, joissa on käytetty teemoja ja värejä 
    - ruutujen skaalaus liitettäessä 
    - mukautetut visualisoinnit animaatioilla 
- Kopiointirajoitteet 
    - Juuri kiinnitetyn koontinäytön ruudun kopiointi ei onnistu. 
    - Käyttäjien ohjaaminen sisältöön, joka sisältää OData-suodattimia ja kiinteitä tiloja, kuten henkilökohtaisia kirjanmerkkejä, ei onnistu. 
- Sovellukset, joilla on rajoitettu tuki HTML-muotoisen sisällön liittämiseen leikepöydältä, eivät ehkä hahmonna kaikkea visualisoinnista kopioitua sisältöä. 



## <a name="next-steps"></a>Seuraavat vaiheet
Lisätietoja [Power BI -raporttien visualisoinneista](power-bi-report-visualizations.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

