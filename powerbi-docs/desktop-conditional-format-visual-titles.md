---
title: Lausekepohjaiset otsikot Power BI Desktopissa
description: Luo Power BI Desktopissa dynaamisia otsikoita, jotka muuttuvat ohjelmallisten lausekkeiden perusteella ehdollisen ohjelmallisen muotoilun avulla
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: reference
ms.date: 04/10/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f3c1f047e3be7520005458294381877d1198ee21
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73878620"
---
# <a name="expression-based-titles-in-power-bi-desktop"></a>Lausekepohjaiset otsikot Power BI Desktopissa

Voit luoda dynaamisia, mukautettuja otsikoita Power BI:n visualisoinneille. Luomalla Data Analysis Expressions (DAX) -lausekkeita kenttien, muuttujien tai muiden ohjelmallisten elementtien perusteella visualisointien otsikkoja voidaan säätää automaattisesti tarvittaessa. Nämä muutokset perustuvat suodattimiin, valintoihin tai muihin käyttäjän toimiin ja määrityksiin.

![Näyttökuva Power BI Desktopin ehdollisen muotoilun asetuksesta](media/desktop-conditional-formatting-visual-titles/expression-based-title-01.png)

Dynaamisten otsikkojen, joita kutsutaan joskus *lausekepohjaisiksi otsikoiksi*, luominen on helppoa. 

## <a name="create-a-field-for-your-title"></a>Luo kenttä otsikkoasi varten

Lausekepohjaisen otsikon luomisen ensimmäinen vaihe on luoda malliin kenttä otsikkoa varten. 

On olemassa kaikenlaisia luovia tapoja, joiden avulla saat visualisoinnin otsikon kuvaamaan sitä, mitä haluat sen sanovan tai mitä haluat ilmaista. Tarkastellaan muutamaa esimerkkiä.

Voit luoda lausekkeen, joka muuttuu sen suodatuskontekstin mukaan, jonka visualisointi saa tuotteen tuotemerkin nimestä. Seuraavassa kuvassa näytetään tällaisen kentän DAX-kaava.

![Näyttökuva DAX-kaavasta](media/desktop-conditional-formatting-visual-titles/expression-based-title-02.png)

Toinen esimerkki on käyttää dynaamista otsikkoa, joka muuttuu käyttäjän kielen tai maa-asetuksen perusteella. Voit luoda kielikohtaisia otsikoita DAX-mittayksikössä käyttämällä `USERCULTURE()`-funktiota. Tämä funktio palauttaa käyttäjän maa-asetuksen käyttöjärjestelmän tai selainasetusten perusteella. Voit käyttää seuraavaa DAX-switch-lauseketta oikean käännetyn arvon valitsemiseen. 

```
SWITCH (
  USERCULTURE(),
  "de-DE", “Umsatz nach Produkt”,
  "fr-FR", “Ventes par produit”,
  “Sales by product”
)
```

Voit myös hakea merkkijonon hakutaulukosta, joka sisältää kaikki käännökset. Sijoita kyseinen taulukko malliin. 

Nämä ovat vain muutamia esimerkkejä, joiden avulla voit luoda dynaamisia, lausekepohjaisia otsikoita Power BI Desktopin visualisoinneille. Otsikoiden käyttötapojen rajana ovat vain mielikuvituksesi ja mallisi.


## <a name="select-your-field-for-your-title"></a>Valitse kenttä otsikkoasi varten

Kun olet luonut DAX-lausekkeen malliisi luomassasi kentässä, sinun on otettava se käyttöön visualisoinnin otsikossa.

Jos haluat valita kentän ja ottaa sen käyttöön, siirry **Visualisoinnit**-ruutuun. Näytä visualisoinnin otsikon asetukset valitsemalla **Muoto**-alueella **Otsikko**. 

Kun napsautat hiiren kakkospainikkeella **Otsikkoteksti**, esiin tulee pikavalikko, jossa voit valita **<em>fx</em>Ehdollinen muotoilu**. Kun valitset kyseisen valikkovaihtoehdon, näkyviin tulee **Otsikkoteksti**-valintaikkuna. 

![Näyttökuva Otsikkoteksti-valintaikkunasta](media/desktop-conditional-formatting-visual-titles/expression-based-title-02b.png)

Tästä ikkunasta voit valita kentän, jonka loit otsikkosi käyttöä varten.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Visualisointien lausekepohjaisten otsikoiden nykyiseen toteutukseen liittyy joitakin rajoituksia:

* Lausekepohjaista muotoilua ei tällä hetkellä tueta Python-visualisoinneissa, R-visualisoinneissa tai Tärkeiden vaikuttajien visualisoinneissa.
* Otsikolle luomasi kentän on oltava merkkijonotietotyyppiä. Mittayksiköitä, jotka palauttavat lukuja tai päivämääriä/aikaa (tai mitä tahansa muuta tietotyyppiä), ei tueta tällä hetkellä.
* Lausekepohjaisia otsikoita ei siirretä, kun kiinnität visualisoinnin koontinäyttöön.

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä artikkelissa kuvataan, miten voit luoda DAX-lausekkeita, jotka muuntavat visualisointien otsikot dynaamisiksi kentiksi, jotka voivat muuttua käyttäjien käyttäessä raportteja. Myös seuraavista artikkeleista voi olla sinulle hyötyä.

* [Ehdollinen muotoilu taulukoissa](desktop-conditional-table-formatting.md)
* [Raporttien välillä porautumisen käyttäminen Power BI Desktopissa](desktop-cross-report-drill-through.md)
* [Porautumisen käyttäminen Power BI Desktopissa](desktop-drillthrough.md)
