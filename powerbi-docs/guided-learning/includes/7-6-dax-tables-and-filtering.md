---
ms.openlocfilehash: d7f30dd43fe875380939520f3dc54fcbbe2f4c9c
ms.sourcegitcommit: 883a58f63e4978770db8bb1cc4630e7ff9caea9a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/07/2019
ms.locfileid: "57555964"
---
**DAX**- ja Excel-kaavakielien yksi merkittävimmistä eroista on se, että DAX mahdollistaa *kokonaisten taulukoiden* välittämisen lausekkeiden välillä (eli tätä ei ole rajoitettu yhteen arvoon). Tämän ansiosta DAX-lausekkeet tarjoavat mahdollisuuden suodattaa taulukoita ja käsitellä sitten suodatettuja arvojoukkoja.

![](media/7-6-dax-tables-and-filtering/dax-tables-filtering_1.png)

DAX:n avulla voit luoda täysin uusia laskettuja taulukoita ja käsitellä niitä kuin mitä tahansa muitakin taulukoita, mukaan lukien suhteiden luominen niiden ja tietomallin muiden taulukoiden välillä.

## <a name="dax-table-functions"></a>DAX-taulukkofunktiot
DAX sisältää laajan valikoiman **taulukkofunktioita**. Käytettävissä ovat esimerkiksi seuraavat funktiot:

* FILTER
* ALL
* VALUES
* DISTINCT
* RELATEDTABLE

Nämä funktiot palauttavat yksittäisen arvon asemesta koko taulukon. Yleensä **taulukkofunktion** tuloksia käytetään jatkoanalysoinnissa osana laajempaa lauseketta (sen sijaan, että käyttäisit palautettua taulukkoa lopullisena arvona). On tärkeää muistaa se, että kun käytät taulukkofunktiota, tulokset perivät sarakkeidensa suhteet.

Voit yhdistellä taulukkofunktioita lausekkeissasi, kunhan kukin funktio käyttää taulukkoa ja palauttaa taulukon. Otetaan esimerkiksi seuraava DAX-lauseke:

    FILTER (ALL (Table), Condition)

Tämä lauseke lisää suodattimen koko *taulukkoon* ja ohittaa kaiken nykyisen suodatinsisällön.

DISTINCT-funktio palauttaa sarakkeen erilliset arvot, jotka ovat myös näkyvissä nykyisessä kontekstissa. Yllä olevan esimerkin DAX-lausekkeessa **ALL**-funktio ohittaa suodattimet, mutta jos korvaat **ALL**-funktion **DISTINCT**-funktiolla, suodattimet huomioidaan.

## <a name="counting-values-with-dax"></a>Arvojen laskeminen DAX:n avulla
Power BI -raporttien käyttäjät haluavat usein löytää vastauksen seuraavaan kysymykseen:

* kuinka monta arvoa tässä sarakkeessa on?

Siihen vastaaminen voi olla helppoa, kun taulukko on auki silmiesi edessä, mutta DAX pyrkii vastaamaan siihen eri tavalla – etenkin silloin, kun taulukoiden välillä on suhteita.

Power BI ja DAX sisältävät esimerkiksi arvoja, joita ei ole indeksoitu keskenään kunnolla. Jos saapuva suhde on rikki, DAX lisää liittyvään taulukkoon uuden rivin, jonka jokainen kenttä on tyhjä, ja linkittää tämän uuden rivin indeksoimattomaan riviin. Näin se takaa viitteiden eheyden. Jos funktiossasi on tyhjiä rivejä, kuten **ALL**-funktiota käytettäessä usein on, nämä tyhjät rivit lasketaan mukaan kyseiselle sarakkeelle palautettavien arvojen määrään.

Voit myös luoda kokonaisia laskettuja taulukoita DAX-funktioilla. DAX:llä luodut lasketut taulukot edellyttävät **NAME**- ja **TABLE**-funktioita. Laskettuja taulukoita voi käyttää kuten kaikkia muitakin taulukoita (mukaan lukien suhteiden luominen).

> Videon sisällön on luonut [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax).
> 
> 

