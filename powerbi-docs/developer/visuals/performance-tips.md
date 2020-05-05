---
title: Suorituskykyvihjeitä
description: Hyvin suorituskykyisen Power BI -visualisoinnin luominen
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 04/20/2020
ms.openlocfilehash: 7ebc02b2c459517957425e78438e12e89dc2e1bb
ms.sourcegitcommit: 1059c6222458f189fb5301dcb689dad2b2c00bc1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/28/2020
ms.locfileid: "82196556"
---
# <a name="how-to-build-a-high-performance-power-bi-visual"></a>Hyvin suorituskykyisen Power BI -visualisoinnin luominen
Tässä artikkelissa käsitellään tekniikoita, joiden avulla kehittäjä voi saavuttaa hyvän suorituskyvyn visualisointien hahmontamisessa. 

Visualisoinnin hahmontamiseen kuluvan ajan on syytä olla mahdollisimman lyhyt, joten koodin on toimittava mahdollisimman tehokkaasti hahmontamisen aikana. 

> [!NOTE]
> Kun ympäristöä parannetaan ja tehostetaan, ohjelmointirajapinnasta julkaistaan jatkuvasti uusia versioita. Jotta voit hyödyntää Power BI -visualisointiympäristöä ja -ominaisuusjoukkoa mahdollisimman hyvin, kannattaa aina käyttää uusinta versiota.
>
> Uusimman **version 2.1** jälkeen Power BI -visualisointien latausnopeus on suurentunut keskimäärin 20 prosentilla.

## <a name="power-bi-visual-performance-tips"></a>Power BI -visualisointien suorituskykyvihjeitä
Seuraavassa on joitakin suosituksia optimaalisen visuaalisen suorituskyvyn saavuttamiseen. 

### <a name="use-user-timing-api"></a>User Timing -ohjelmointirajapinnan käyttäminen
Sovelluksesi JavaScript-suorituskyvyn mittaaminen **User Timing -ohjelmointirajapinnan** voi auttaa sinua päättämään, mitkä komentosarjan osat tarvitsevat optimointia.

Lisätietoja on artikkelissa [User Timing -ohjelmointirajapinta](https://msdn.microsoft.com/library/hh772738(v=vs.85).aspx).

### <a name="review-animation-loops"></a>Animaatiosilmukoiden tarkistaminen
Piirtääkö animaatiosilmukka muuttumattomat elementit uudelleen? 

 - Ongelma: Aikaa tuhlataan sellaisten elementtien piirtämiseen, joissa ei ole muutoksia ruutujen välillä.

 - Ratkaisu: Päivitä ruudut valikoidusti. 
 
Kun staattisia visualisointeja animoidaan, on houkuttelevaa niputtaa piirtokoodi yhdeksi päivitystoiminnoksi ja kutsua sitä toistuvasti uusilla tiedoilla animaatiosilmukan jokaista iteraatiota varten.

Harkitse sen sijaan seuraavaa päivityskaavaa ja piirrä kaikki visuaalisen konstruktorimenetelmän avulla, niin päivitystoiminnon tarvitsee piirtää vain muuttuvat visualisoinnin osat. 

   > [!TIP]
   > Tehottomia animaatiosilmukoita on yleensä akseleissa ja selitteissä.

### <a name="cache-dom-nodes"></a>Välimuistin DOM-solmut 
Kun solmu tai solmuluettelo noudetaan DOMista, sinun on ajateltava, voitko käyttää niitä uudelleen myöhemmissä laskentatoiminnoissa (joskus jopa silmukan seuraavan iteraation). Jos sinun ei tarvitse lisätä tai poistaa muita solmuja kyseisessä alueessa, niiden tallentaminen välimuistiin voi parantaa sovelluksesi yleistä tehokkuutta.

Jos haluat varmistaa, että koodisi on nopeaa ja että se ei hidasta selainta, pidä DOM-käyttö mahdollisimman vähäisenä. 

- Ennen: 

   ```javascript
   public update(options: VisualUpdateOptions) { 
       let axis = $(".axis"); 
   }
   ```

- Jälkeen: 

   ```javascript
   public constructor(options: VisualConstructorOptions) { 
       this.$root = $(options.element); 
       this.xAxis = this.$root.find(".xAxis"); 
   } 
 
   public update(options: VisualUpdateOptions) { 
       let axis = this.axis; 
   }
   ```

### <a name="avoid-dom-manipulation"></a>Vältä DOM-käsittelyä 
Rajoita DOM-käsittelyä mahdollisimman paljon.  Lisäysoperaatiot, kuten `prepend()`, `append()` ja `after()` kuluttavat aikaa, ja niitä tulisi käyttää vain tarvittaessa.

Esimerkiksi:

  ```javascript
  for (let i=0; i<1000; i++) { 
      $('#list').append('<li>'+i+'</li>');
  }
  ```

Edellä olevaa esimerkkiä voi nopeuttaa `html()`-määrityksellä ja luomalla luettelon etukäteen: 

  ```javascript
  let list = ''; 
  for (let i=0; i<1000; i++) { 
      list += '<li>'+i+'</li>'; 
  } 

  $('#list').html(list); 
  ```

### <a name="reconsider-jquery"></a>Harkitse uudelleen JQueryn käyttöä

JS-kehysten rajoittaminen ja alkuperäisten JS-tietojen käyttäminen aina mahdollisuuksien mukaan voi lisätä käytettävissä olevaa kaistanleveyttä ja pienentää käsittelyn aiheuttamaa kuormitusta. Tämä voi myös rajoittaa yhteensopivuusongelmia vanhempien selainten kanssa. 

Lisätietoja on osoitteessa [youmightnotneedjquery.com](http://youmightnotneedjquery.com/), jossa on vaihtoehtoisia esimerkkejä funktioista, kuten JQueryn funktioista `show`, `hide`ja `addClass`.  

### <a name="use-canvas-or-webgl"></a>Canvasin tai WebGL:n käyttäminen 
Animaatioiden toistuvassa käytössä kannattaa käyttää **Canvasia** tai **WebGL:ää** SVG:n sijaan. SVG:stä poiketen näiden vaihtoehtojen suorituskyky määräytyy koon mukaan, ei sisällön. 

Lisätietoja eroista on artikkelissa [SVG vs Canvas: How to Choose](https://msdn.microsoft.com/library/gg193983(v=vs.85).aspx). 

### <a name="use-requestanimationframe-instead-of-settimeout"></a>RequestAnimationFrame-toiminnon käyttäminen setTimeout-toiminnon sijaan 
Jos päivität näyttöanimaatiosi [requestAnimationFrame](https://www.w3.org/TR/animation-timing/)-toiminnolla, animaatiofunktioitasi kutsutaan, **ennen kuin** selain kutsuu uutta päivitystä.

Jos haluat lisätietoja, lue tämä [malli](https://testdrive-archive.azurewebsites.net/Graphics/RequestAnimationFrame/Default.html) sujuvista animaatioista `requestAnimationFrame`-toiminnon avulla.

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja optimointitekniikoista on [Power BI:n optimointi oppaassa](/power-bi/guidance/power-bi-optimization).
