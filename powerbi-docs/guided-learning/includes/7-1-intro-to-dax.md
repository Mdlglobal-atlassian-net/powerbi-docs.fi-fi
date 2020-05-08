---
ms.openlocfilehash: 3966521d158c244487638be4117f98ea570e1f28
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "73799806"
---
Tervetuloa Power BI:n **ohjatun oppimisen** osioon, jossa kerromme sinulle perusasioita **DAX:stä**.

**DAX** on lyhenne sanoista **Data Analysis Expressions**. Se on kaavakieli, jota käytetään Power BI:ssä (Power BI käyttää sitä myös taustalla). DAX on käytössä myös muissa Microsoftin palveluissa (esimerkiksi Power Pivotissa ja SSAS:n taulukkomuodossa), mutta näissä ohjatun oppimisen ohjeartikkeleissa keskitytään siihen, miten DAX:ää käytetään ja miten voit itse käyttää sitä Power BI:ssä.

## <a name="dax-and-this-guided-learning-video-series"></a>DAX ja tämä ohjatun oppimisen videosarja
Tämän **ohjatun oppimisen** osion tarkoitus on opettaa sinulle DAX:n perusasiat. Käsittelemme esimerkiksi sitä, miten DAX:ään kannattaa suhtautua ja miten se toimii. Lisäksi saat lisätietoja sen hyödyllisimmistä toiminnoista tunnetulta DAX-asiantuntijalta [Alberto Ferrarilta](https://www.sqlbi.com/learning-dax) (jolla on runsaasti käytännön kokemusta niistä).

![Alberto Ferrarin kuva](media/7-1-intro-to-dax/intro_dax_6_alberto_ferrari.png)

Tämän **DAX:n** **ohjatun oppimisen** videoiden avulla opit DAX:n perusasiat DAX-kaavakielen toiminnan näkökulmasta. Tästä on hyötyä, kun luot DAX-kaavoja täysin alusta saakka, mutta tämän ansiosta ymmärrät paremmin myös sitä, miten Power BI luo tällaisia DAX-kaavoja, kun luot kyselyitä **kyselyeditorilla**.

## <a name="in-this-video---introduction-to-dax"></a>Tämän videon sisältö: johdanto DAXiin
DAX-käsitteet ovat yksinkertaisia, vaikka DAX itsessään onkin hyvin tehokas. DAX hyödyntää ainutlaatuisia ohjelmointikäsitteitä ja -malleja, minkä johdosta sen täydellinen ymmärtäminen ja kattava käyttö voi olla vaikeaa. Ohjelmointikielten perinteiset opettelutavat eivät ehkä sovellu niin hyvin DAX:lle, mutta tämän videon tavoitteena on opettaa sinulle käsitteet ja teoriaa, joista on sinulle apua myöhemmässä Power BI -käytössäsi.

DAX on *funktionaalinen kieli*, mikä tarkoittaa sitä, että täysi suoritettava koodi sisältyy funktioihin.

DAX:n funktiot voivat sisältää muita sisäkkäisiä funktioita, ehdollisia lausekkeita ja arvoviittauksia. Suoritus alkaa DAX:ssä sisimmäisestä funktiosta tai parametrista, josta sitä jatketaan ulospäin. Power BI:ssä DAX-kaavat kirjoitetaan yhdelle riville, joten funktioiden oikea muotoilu on tärkeää luettavuuden kannalta.

DAX on suunniteltu käytettäväksi taulukoiden kanssa, joten siinä on vain kaksi ensisijaista tietotyyppiä: **Numeric** eli numeeriset ja **Other** eli muut tiedot. **Numeeriset** tiedot voivat olla *kokonaislukuja*, *desimaalilukuja* ja *valuuttoja*. **Muut** tiedot voivat olla *merkkijonoja* ja *binaariobjekteja*. Tämä tarkoittaa sitä, että jos luot tietyntyyppistä numeerista tietoa käsittelevän DAX-funktion, voit olla varma siitä, että se toimii kaikkien numeeristen tietojen kanssa.

DAX käyttää operaattoreiden ylikuormitusta, minkä ansiosta voit yhdistellä tietotyyppejä laskelmissasi: tulokset vaihtelevat sen mukaan, mitä tietotyyppiä annetuissa tiedoissa käytetään. Muuntaminen tehdään automaattisesti, minkä ansiosta sinun ei tarvitse tietää niiden sarakkeiden tietotyyppejä, joita käsittelet Power BI:ssä, mutta joskus tämä voi johtaa myös yllättäviin muunnoksiin. Suosittelemme siksi, että ymmärrät käyttämäsi tiedot. Näin varmistat, että operaattorit toimivat odotetulla tavalla.

Power BI:ssä on yksi tietotyyppi, jota luultavasti käytät paljon: **Päivämäärä/aika**. **DateTime** tallennetaan liukulukuarvona sekä kokonaisluku- että desimaaliosien kanssa. DateTime-tietotyypin avulla voi laskea tarkasti mitä tahansa ajanjaksoja 1.3.1900 jälkeen.

> Videon sisällön on luonut [Alberto Ferrari, SQLBI](https://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit).
> 
> 

