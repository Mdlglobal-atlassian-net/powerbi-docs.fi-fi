---
title: Power BI Desktop lausekepohjaisia otsikoita
description: Luo Power BI Desktop, joka muuttaa ohjelmallisen lausekkeisiin perustuvien käyttämällä ohjelmallisen ehdollisen dynaaminen otsikot
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: reference
ms.date: 04/10/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b90ef66d2c118a70f1b18ed4fe302ce1db23e45c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "64769751"
---
# <a name="expression-based-titles-in-power-bi-desktop"></a>Power BI Desktop lausekepohjaisia otsikoita

Voit luoda dynaamisia, mukauttaa Power BI-visualisointien otsikot. Luot Data Analysis Expressions (DAX) perusteella kenttiä, muuttujien tai muita ohjelmallisen elementtejä, että visualisoinnit otsikot voit automaattisesti säätöjä tarpeen. Nämä muutokset perustuvat suodattimia, valinnat, tai muiden käyttäjien vuorovaikutuksen ja määritykset.

![Power BI Desktop näyttökuva ehdollisen muotoilun vaihtoehto](media/desktop-conditional-formatting-visual-titles/expression-based-title-01.png)

Luot dynaaminen otsikoita, jota kutsutaan myös *lausekepohjaisia otsikot*, on helppoa. 

## <a name="create-a-field-for-your-title"></a>Luo otsikko kenttä

Ensimmäisessä vaiheessa luodaan lausekepohjaisia otsikko on luoda kentän otsikolle käyttää mallissa. 

On monia erilaisia tapoja on visuaalinen otsikko vastaa mitä haluat sen oletetaan, että tai haluat express. Katsotaanpa pari esimerkkiä.

Voit luoda lausekkeen, joka muutokset suodatinkontekstin, joka visualisoinnin vastaanottaa tuotteen tuotemerkin nimen perusteella. Seuraavassa kuvassa näkyy sellaisen kentän DAX-kaava.

![Näyttökuva DAX-kaava](media/desktop-conditional-formatting-visual-titles/expression-based-title-02.png)

Toinen esimerkki käyttää dynaamisia otsikko, joka muuttuu mukaan käyttäjän kielen tai maa-asetuksen. Voit luoda kielen mukainen otsikot käyttämällä DAX-mittayksikköä `USERCULTURE()` funktio. Tämä funktio palauttaa maa-asetuksen käyttäjälle, käyttöjärjestelmä tai selaimen asetusten perusteella. Voit valita oikean käännetty arvon DAX switch-lauseke. 

```
SWITCH (
  USERCULTURE(),
  "de-DE", “Umsatz nach Produkt”,
  "fr-FR", “Ventes par produit”,
  “Sales by product”
)
```

Tai voit noutaa merkkijono, joka sisältää käännösten hakutaulukko. Taulukko sijoitetaan mallin. 

Nämä ovat vain muutama erityyppinen avulla voit luoda dynaamisia, lausekepohjaisia otsikot visualisoinnit Power BI Desktop esimerkkejä. Mitä voit tehdä-otsikot ovat rajoittaa vain mielikuvitustasi ja mallin.


## <a name="select-your-field-for-your-title"></a>Valitse kenttä-otsikko

Kun olet luonut luot mallisi kentän DAX-lauseke, sinun on käytettävä visualisoinnin otsikon.

Valitse kenttä ja käyttää sitä, siirry **visualisoinnit** ruudussa. \- **Muodossa** alueella **otsikko** näyttämään visualisoinnin otsikon asetukset. 

Kun napsautat hiiren kakkospainikkeella **otsikkoteksti**, näytölle tulee kontekstivalikko, jonka avulla voit valita ***fx* ehdollisen muotoilun**. Kun valitset valikosta, **otsikkoteksti** valintaikkuna tulee näkyviin. 

![Näyttökuva-otsikon teksti-valintaikkuna](media/desktop-conditional-formatting-visual-titles/expression-based-title-02b.png)

Valitse tämä ikkuna kenttä, jonka loit käytettävä otsikko.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Visualisointien lausekepohjaisia otsikot nykyisen toteuttamiseen joitakin rajoituksia:

* Lausekepohjaisia muotoilu ei tueta tällä hetkellä Python-visualisoinnit, R-visualisointeja tai avain Influencers visualisoinnin.
* Voit luoda otsikon kentän on oltava merkkijono tietotyyppi. Mittayksiköitä, jotka palauttavat lukuja tai päivämäärä/kellonaika (tai minkä tahansa muun tietotyypin) ei tueta tällä hetkellä.

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä artikkelissa kuvataan miten voit luoda DAX-lausekkeita, jotka Ota visualisoinnit otsikot dynaaminen kenttiin, voit muuttaa, kun käyttäjät käyttävät raportteja. Sinulla voi olla hyötyä seuraavissa artikkeleissa myös.

* [Rajat raportin porautumisen käyttäminen Power BI Desktop](desktop-cross-report-drill-through.md)
* [Porautumisen käyttäminen Power BI Desktopissa](desktop-drillthrough.md)