---
title: Lausekkeet Power BI:n raportin muodostimessa
description: Lausekkeita käytetään yleisesti Power BI:n sivutettujen raporttien muodostimessa tietojen noutamiseen, laskemiseen, näyttämiseen, ryhmittelyyn, lajitteluun, suodattamiseen, parametrisointiin ja muotoiluun.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 76d3ac86-650c-46fe-8086-8b3edcea3882
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: d3a72fd967eeb24cfa1093d16c4434447d5fc89d
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840621"
---
# <a name="expressions-in-power-bi-report-builder"></a>Lausekkeet Power BI:n raportin muodostimessa
  Lausekkeita käytetään yleisesti Power BI:n sivutettujen raporttien muodostimessa tietojen noutamiseen, laskemiseen, näyttämiseen, ryhmittelyyn, lajitteluun, suodattamiseen, parametrisointiin ja muotoiluun. 
  
  Monet raporttikohteiden ominaisuudet voidaan määrittää lausekkeiksi. Lausekkeiden avulla voit hallita raportin sisältöä, rakennetta ja vuorovaikutteisuutta. Lausekkeet on kirjoitettu Microsoft Visual Basicilla ja tallennettu raporttimääritykseen. Raportinkäsittely arvioi ne, kun raportti suoritetaan.  
  
 Toisin kuin Microsoft Office Excel ja muut sovellukset, joissa tietoja käsitellään suoraan laskentataulukossa, raportissa voit käsitellä lausekkeita, jotka toimivat tietojen paikkamerkkeinä. Sinun on esikatseltava raportti, jotta voit nähdä arvioitujen lausekkeiden todelliset tiedot. Kun raportti suoritetaan, raportinkäsittely arvioi jokaisen lausekkeen yhdistäessään raporttitietoja ja raportin asettelun elementtejä, kuten taulukoita ja kaavioita.  
  
 Kun suunnittelet raporttia, monet raporttikohteita koskevat lausekkeet asetetaan puolestasi. Kun esimerkiksi vedät kentän tietoruudusta raportin suunnittelualueelle taulukkosoluun, tekstiruudun arvoksi asetetaan kentän yksinkertainen lauseke. Seuraavassa kuvassa raportin tietoruudussa näkyvät tietojoukon kenttien tunnukset, nimet, myyntialue, koodi ja myynti. Taulukkoon on lisätty kolme kenttää: [Name], [Code] ja [Sales]. Suunnittelualueella olevan [Name]-kentän merkintä tarkoittaa pohjana oleva lauseketta `=Fields!Name.Value`.  
  
![Raportin muodostimen suunnittelunäkymä](media/report-builder-expressions/report-builder-data-design-preview.png)
  
 Kun esikatselet raporttia, raportinkäsittely yhdistää taulukon tietoalueen tietoyhteyden todellisiin tietoihin ja näyttää taulukossa yhden rivin kutakin tulosjoukon riviä kohti.  
  
 Voit lisätä lausekkeita manuaalisesti valitsemalla suunnittelualueella olevan kohteen määrittämällä kohteen ominaisuudet pikavalikot ja valintaikkunoiden avulla. Kun näet avattavassa luettelossa ***(fx)***-painikkeen tai arvon `<Expression>`, tiedät, että voit määrittää ominaisuuden lausekkeen. 
  
##  <a name="Types"></a> Yksinkertaisten ja monimutkaisten lausekkeiden ymmärtäminen  
 Lausekkeet alkavat yhtäläisyysmerkillä (=) ja ne kirjoitetaan Microsoft Visual Basicilla. Lausekkeet voivat sisältää yhdistelmän vakioita, operaattoreita ja viittauksia sisäisiin arvoihin (kentät, kokoelmat ja funktiot) sekä ulkoista tai mukautettua koodia.  
  
 Lausekkeiden avulla voit määrittää useiden raporttikohteiden ominaisuudet. Yleisimmät ominaisuudet ovat tekstiruutujen ja paikkamerkkitekstien arvot. Jos tekstiruutu sisältää vain yhden lausekkeen, lauseke on yleensä tekstiruutuominaisuuden arvo. Jos tekstiruutu sisältää useita lausekkeita, kukin lauseke on tekstiruudun arvon paikkamerkki.  
  
 Lausekkeet näkyvät oletusarvoisesti raportin suunnittelualueella *yksinkertaisina* tai *monimutkaisina lausekkeina*.  
  
-   **Yksinkertainen** Yksinkertainen lauseke sisältää viittauksen sisäisen kokoelman yksittäiseen kohteeseen, esimerkiksi tietojoukon kenttään, parametriin tai sisäiseen kenttään. Suunnittelualueella yksinkertainen lauseke näkyy hakasulkeissa. Esimerkiksi `[FieldName]` vastaa pohjana olevaa lauseketta `=Fields!FieldName.Value`. Yksinkertaiset lausekkeet luodaan puolestasi automaattisesti, kun luot raportin asettelun ja vedät kohteita raportin tietoruudusta suunnittelualueelle. Lisätietoja eri sisäisiä kokoelmia edustavista symboleista on kohdassa [Yksinkertaisten etuliitesymbolien ymmärtäminen](#DisplayText).  
  
-   **Monimutkainen** Monimutkainen lauseke sisältää viittauksia useisiin sisäisiin viittauksiin, operaattoreihin ja funktiokutsuihin. Monimutkainen lauseke näkyy muodossa <\<Lauseke>>, kun lausekkeen arvo sisältää yksinkertaista mutkikkaamman viitteen. Voit tarkastella lauseketta viemällä osoittimen sen päälle ja käyttämällä työkaluvihjettä. Voit muokata lauseketta avaamalla sen **Lauseke**-valintaikkunassa.  
  
 Seuraavassa kuvassa näytetään tyypillinen yksinkertainen ja monimutkainen lauseke sekä tekstiruudulle että paikkamerkkitekstille.  
  
![Lausekkeen oletusmuotoilu raportin muodostimessa](media/report-builder-expressions/report-builder-expression-default-format.png) 
  
 Voit näyttää lausekkeiden tekstin sijaan malliarvot käyttämällä muotoilua tekstiruudun tai paikkamerkin tekstiin. Seuraavassa kuvassa esitetään raportin suunnittelualue, jonka on valittu näyttävän malliarvot:  
  
![Lausekkeen mallimuotoilu raportin muodostimessa](media/report-builder-expressions/report-builder-expression-sample-values-format.png)  


## <a name="DisplayText"></a> Yksinkertaisten lausekkeiden etuliitesymbolien ymmärtäminen  

Yksinkertaisissa lausekkeissa käytetään symboleja ilmaisemaan, onko viittaus kenttä, parametri, sisäinen kokoelma tai raporttikohteet-kokoelma. Seuraavassa taulukossa on esimerkkejä näytön ja lausekkeen tekstistä:  
  
|Kohde|Näytä tekstimalli|Lausekkeen tekstimalli|  
|----------|--------------------------|-----------------------------|  
|Tietojoukkokentät|`[Sales]`<br /><br /> `[SUM(Sales)]`<br /><br /> `[FIRST(Store)]`|`=Fields!Sales.Value`<br /><br /> `=Sum(Fields!Sales.Value)`<br /><br /> `=First(Fields!Store.Value)`|  
|Raportin parametrit|`[@Param]`<br /><br /> `[@Param.Label]`|`=Parameters!Param.Value`<br /><br /> `=Parameters!Param.Label`|  
|Sisäiset kentät|`[&ReportName]`|`=Globals!ReportName.Value`|  
|Tekstiruuduissa käytetyt literaalimerkit|`\[Sales\]`|`[Sales]`|  
  
##  <a name="References"></a> Monimutkaisten lausekkeiden kirjoittaminen  
 Lausekkeet voivat sisältää viittauksia funktioihin, operaattoreihin, vakioihin, kenttiin, parametreihin, sisäisten kokoelmien kohteisiin ja upotettuun mukautettuun koodiin tai mukautettuihin kokoonpanoihin.  
  
 Seuraavassa taulukossa luetellaan viittaustyypit, jotka voit sisällyttää lausekkeisiin:  
  
|Viittaukset|Kuvaus|Esimerkki|  
|----------------|-----------------|-------------|  
|Vakiot|Tässä artikkelissa kuvataan vakiot, joita voit käyttää vuorovaikutteisesti ominaisuuksiin, jotka edellyttävät fontin väriä tai muita vakioarvoja.|`="Blue"`|  
|Operaattorit|Kuvailee operaattorit, joita voit käyttää yhdistääksesi viitteet lausekkeisiin. Esimerkiksi operaattorilla **&** merkkijonoja voidaan liittää yhteen.|`="The report ran at: " & Globals!ExecutionTime & "."`|  
|Sisäiset kokoelmat|Kuvailee sisäiset kokoelmat, jotka voit sisällyttää lausekkeeseen, kuten `Fields`, `Parameters` ja `Variables`.|`=Fields!Sales.Value`<br /><br /> `=Parameters!Store.Value`<br /><br /> `=Variables!MyCalculation.Value`|  
|Sisäiset raportit ja koostefunktiot|Kuvailee sisäiset funktiot, kuten `Sum` tai `Previous`, joita voi käyttää lausekkeissa.|`=Previous(Sum(Fields!Sales.Value))`|  
|Mukautetut koodi- ja kokoonpanoviittaukset raportin muodostimen lausekkeissa |Tässä artikkelissa kuvataan, miten voit käyttää sisäisiä CLR-luokkiin `xref:System.Math` ja `xref:System.Convert`, muita CLR-luokkia, Visual Basic -suorituskirjastoja tai ulkoisten kokoonpanojen menetelmiä.<br /><br /> Tässä artikkelissa kuvataan, miten voit käyttää raporttiin upotettua mukautettua koodia tai koodia, jonka koostat ja asennat mukautettuna kokoonpanona sekä raportin asiakkaalle että raporttipalvelimelle.|`=Sum(Fields!Sales.Value)`<br /><br /> `=CDate(Fields!SalesDate.Value)`<br /><br /> `=DateAdd("d",3,Fields!BirthDate.Value)`<br /><br /> `=Code.ToUSD(Fields!StandardCost.Value)`|  
   
##  <a name="Valid"></a> Lausekkeiden vahvistaminen  
 Kun luot lausekkeen tietylle raporttikohteen ominaisuudelle lausekkeen, voit sisällyttää lausekkeeseen joitain viitteitä. Tuetut viitteet riippuvat siitä, mitä arvoja raporttikohteen ominaisuudet hyväksyvät sekä arvioitavasta laajuudesta. Esimerkki:  
  
-   Oletuksena lauseke [Sum] laskee lausekkeen arviointihetkellä laajuuteen sisältyvien tietojen summan. Taulukkosolujen tapauksessa laajuus määräytyy rivi- ja sarakeryhmien jäsenyyden mukaan. 
  
-   Fontti-ominaisuuden arvon arvo täytyy antaa tulokseksi fontin nimi.  
  
-   Lausekkeen syntaksi vahvistetaan suunnittelun aikana. Lausekkeen laajuus vahvistetaan, kun julkaiset raportin. Todellisista tiedoista riippuvaisten vahvistusten virheet voidaan havaita vain suorituksen aikana. Jotkin lausekkeet tuottavat #Error-virheilmoituksen hahmonnetussa raportissa. 

## <a name="next-steps"></a>Seuraavat vaiheet

- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
