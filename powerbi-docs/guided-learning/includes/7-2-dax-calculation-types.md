---
ms.openlocfilehash: 4ea1b2141cf9a072f11a3a62789c7c0ec5b500a4
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "73799804"
---
Voit luoda DAX:llä kahdenlaisia päälaskelmia:

* **lasketut sarakkeet**
* **lasketut mittarit**.

Ennen kuin perehdymme niihin, on kuitenkin syytä tutustua taulukoiden ja sarakkeiden DAX-syntaksiin, jota käytät luodessasi **laskettuja sarakkeita** ja **laskettuja mittareita**.

## <a name="dax-table-and-column-name-syntax"></a>DAX-taulukoiden ja sarakkeiden nimien syntaksi
Riippumatta siitä, oletko luomassa uutta saraketta vai mittaria, on tärkeää tuntea DAX:n yleinen taulukkonimien muoto:

    'Table Name'[ColumnName]

Jos taulukon nimessä on välilyöntejä (kuten yllä), taulukon nimen ympärillä täytyy käyttää heittomerkkejä. Jos taulukon nimessä ei ole välilyöntejä, heittomerkit eivät ole pakollisia. Tässä tapauksessa syntaksi on seuraava:

    TableName[ColumnName]

Seuraavasta kuvasta näet Power BI:ssä luotavan DAX-kaavan:

![](media/7-2-dax-calculation-types/dax-calc-types_1.png)

Voit myös poistaa taulukon nimen kokonaan ja käyttää vain sarakkeen nimeä, mutta emme suosittele tätä funktioiden selkeyden (ja täten DAX-koodin selkeyden) kannalta. Sarakenimien täytyy aina olla hakasulkeissa.

Suosittelemme, että noudatat *aina* seuraavia parhaita käytäntöjä:

* Älä käytä taulukoiden nimissä välilyöntejä.
* Sisällytä aina taulukon nimi kaavoihin (älä poista sitä, vaikka DAX tämän mahdollistaakin).

## <a name="creating-calculated-columns"></a>Laskettujen sarakkeiden luominen
**Lasketuista sarakkeista** on hyötyä, kun haluat osittaa tai suodattaa arvon tai haluat tehdä laskutoimituksen taulukon jokaiselle riville.

Voit luoda laskettuja sarakkeita Power BI Desktopissa valitsemalla **Mallinnus**-välilehdestä **Uusi sarake**. Suosittelemme **Tiedot**-näkymää (**Raportti**- tai **Suhteet**-näkymien sijasta), sillä siinä näet uuden kaavan luomisen ja **kaavarivin**, joka sisältää kaavasi perustiedot ja on valmiina DAX-kaavaasi varten.

![](media/7-2-dax-calculation-types/dax-calc-types_2a.png)

Kun napsautat **Uusi sarake** -painiketta, **kaavariville** lisätään perussarakenimi (jota muokkaat tietysti kaavasi mukaan) ja **=** -operaattori. Lisäksi uusi sarake näytetään tietoruudukossa, kuten seuraavassa kuvassa.

![](media/7-2-dax-calculation-types/dax-calc-types_3.png)

Lasketun sarakkeen pakollisia elementtejä ovat seuraavat:

* uuden sarakkeen nimi
* ainakin yksi funktio tai lauseke.

Jos viittaat lasketun sarakkeen kaavassa taulukkoon tai sarakkeeseen, sinun ei tarvitse määrittää taulukon riviä, koska Power BI laskee nykyisen rivin sarakkeen kussakin laskutoimituksessa.

## <a name="creating-calculated-measures"></a>Laskettujen mittarien luominen
Käytä **laskettua mittaria**, kun lasket prosentteja tai osuuksia tai kun tarvitset monimutkaisia koosteita. Kun haluat luoda mittarin DAX-kaavalla, valitse **Mallinnus**-välilehdestä **Uusi mitta**. Suosittelemme tässäkin yhteydessä Power BI Desktopin **Tiedot-näkymää**, sillä siinä näet **kaavarivin** ja voit kirjoittaa DAX-kaavasi helposti.

![](media/7-2-dax-calculation-types/dax-calc-types_4.png)

Kun käytät **mittareita**, näet uuden mittarin kuvakkeen **Kentät**-ruudussa. Näet myös mittarin nimen. **Kaavariville** lisätään taas DAX-kaavasi nimi (tällä kertaa mittarin kanssa).

![](media/7-2-dax-calculation-types/dax-calc-types_5.png)

Lasketun mittarin pakolliset elementit ovat samat kuin lasketussa sarakkeessa:

* uuden mittarin nimi
* ainakin yksi funktio tai lauseke.

> Videon sisällön on luonut [Alberto Ferrari, SQLBI](https://www.sqlbi.com/learning-dax).
> 
> 

