---
title: 'DAX: Vältä tyhjien arvojen muuntamista arvoiksi'
description: Vältä tyhjien tulosten muuntamista arvoiksi.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/24/2019
ms.author: v-pemyer
ms.openlocfilehash: 2f70b98ed540a2e5b87e5a949e30b0c1c02069d1
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "74700382"
---
# <a name="dax-avoid-converting-blanks-to-values"></a>DAX: Vältä tyhjien arvojen muuntamista arvoiksi

Kun tietomallintajana kirjoitat mittarilausekkeita, saatat törmätä tilanteisiin, joissa merkityksellistä arvoa ei voi palauttaa. Näissä tapauksissa saatat haluta palauttaa arvon, kuten nollan, sen sijaan. Suosittelemme, että selvität tarkkaan, onko tämä malli tehokas ja käytännöllinen.

Harkitse seuraavaa mittarimääritystä, joka nimenomaisesti muuntaa tyhjät tulokset nolliksi.

```dax
Sales (No Blank) =
IF(
    ISBLANK([Sales]),
    0,
    [Sales]
)
```

Harkitse toista mittarimääritystä, joka myös muuntaa tyhjät tulokset nolliksi.

```dax
Profit Margin =
DIVIDE([Profit], [Sales], 0)
```

[DIVIDE](/dax/divide-function-dax)-funktiolla jaetaan **Profit**-mittari **Sales**-mittarin mukaan. Jos tulos on nolla tai tyhjä, funktio palauttaa kolmannen argumentin – vaihtoehtoisen tuloksen (joka on valinnainen). Tässä esimerkissä, koska nolla välitetään vaihtoehtoisena tuloksena, mittari palauttaa aina arvon.

Nämä mittarimallit ovat tehottomia ja johtavat huonoihin raporttimalleihin.

Kun ne lisätään raportin visualisointiin, Power BI yrittää noutaa kaikki suodatinkontekstin ryhmittelyt. Suurten kyselyjen tulosten arviointi ja nouto johtavat usein hitaaseen raportin hahmontamiseen. Kukin esimerkki muuntaa niukan laskennan tiheäksi ja pakottaa käytännössä Power BI:n käyttämään enemmän muistia kuin on tarpeen.

Myös liian monet ryhmittelyt liian usein väsyttävät raporttikäyttäjiäsi.

Katsotaan, mitä tapahtuu, kun **Profit Margin** -mittari lisätään taulukkovisualisointiin ryhmiteltynä asiakkaan mukaan.

![Taulukon visualisoinnissa on kolme saraketta: Asiakas, myynti ja voittomarginaali. Taulukossa näkyy noin 10 riviä tietoja, mutta pystysuuntainen vierityspalkki ilmaisee, että näkyvissä voi olla useita rivejä. Myynti-sarakkeessa ei näytetä arvoja. Voittomarginaali-sarakkeessa näkyy vain nolla.](media/dax-avoid-converting-blank/table-visual-poor.png)

Taulukon visualisointi näyttää valtavan määrän rivejä. (Mallissa on itse asiassa 18 484 asiakasta, joten taulukko yrittää näyttää ne kaikki.) Huomaa, että näkymän asiakkaat eivät ole saavuttaneet myyntiä. Koska **Profit Margin** -mittari kuitenkin palauttaa aina arvon, ne näytetään.

> [!NOTE]
> Kun visualisoinnissa on liian monta arvopistettä, Power BI voi käyttää tietojen vähentämisen strategioita suurten kyselyjen tulosten poistamiseen tai yhteenvetojen tekemiseen. Katso lisätietoja kohdasta [Arvopisterajat ja strategiat visualisointityypin mukaan](../visuals/power-bi-data-points.md).

Katsotaan, mitä tapahtuu, kun **Profit Margin** -mittarinmääritystä parannetaan. Se palauttaa nyt arvon vain, kun **Sales**-mittari ei ole tyhjä (tai nolla).

```dax
Profit Margin =
DIVIDE([Profit], [Sales])
```

Taulukon visualisointi näyttää nyt vain asiakkaat, jotka ovat tehneet myyntiä nykyisessä suodatuskontekstista. Parannettu mittari parantaa raportin käyttäjien käytännön kokemusta.

![Sama taulukkovisualisointi näyttää nyt neljä tietoriviä. Jokainen rivi on asiakkaalle, jolla on myyntiarvo, eikä voittomarginaali ole nolla.](media/dax-avoid-converting-blank/table-visual-good.png)

> [!TIP]
> Voit tarvittaessa määrittää visualisoinnin näyttämään kaikki ryhmät (jotka palauttavat arvoja tai tyhjän) suodatinkontekstissa ottamalla käyttöön asetuksen [Näytä kohteet, joilla ei ole tietoja](../desktop-show-items-no-data.md).

## <a name="recommendation"></a>Suositus

Suosittelemme, että mittarit palauttavat tyhjän, kun mielekästä arvoa ei voi palauttaa.

Tämä suunnittelumenetelmä on tehokas, joten Power BI voi hahmontaa raportteja entistä nopeammin. Tyhjän palauttaminen on parempaa, koska raporttien visualisoinnit oletusarvoisesti poistavat ryhmittelyt, kun yhteenvedot ovat tyhjiä.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Data Analysis Expressions (DAX) -viittaukset](/dax/)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
