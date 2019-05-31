---
ms.openlocfilehash: 033436e7078723508d6b9481807ace424c3f109f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61396886"
---
Power BI:ssä on kaksi erityyppistä karttavisualisointia: kuplakartta, jossa maantieteellisen pisteen päälle asetetaan kupla, ja muotokartta, joka näyttää visualisoitavan alueen ääriviivat.

![](media/3-5-create-map-visualizations/3-5_1.png)

> [!NOTE]
> Kun käsittelet maita tai alueita, käytä kolmikirjaimisia lyhenteitä, jotta sijaintitietojen lisääminen toimii varmasti oikein karttavisualisoinneissa. *Älä* käytä kaksikirjaimisia lyhenteitä, koska silloin joitakin maita tai alueita ei välttämättä tunnisteta oikein.
> Jos käytettävissäsi on vain kaksikirjaimisia lyhenteitä, lue [tämä ulkoinen blogikirjoitus](https://blog.ailon.org/how-to-display-2-letter-country-data-on-a-power-bi-map-85fc738497d6#.yudauacxp), jossa kerrotaan, miten voit yhdistää kaksikirjaimiset maa-/aluelyhenteet kolmikirjaimisiin.
> 
> 

## <a name="create-bubble-maps"></a>Kuplakarttojen luominen
Luo kuplakartta valitsemalla **Kartta**-vaihtoehto **Visualisointi**-ruudusta. Sinun on lisättävä arvo **Visualisoinnit**-vaihtoehtojen *Sijainti*-ryhmään, jotta voit käyttää karttavisualisointia.

![](media/3-5-create-map-visualizations/3-5_2.png)

Power BI on joustava hyväksyttävän sijaintiarvon tyypin suhteen: sijaintiarvo voi olla yleisempi, kuten kaupungin nimi tai lentokentän koodi, tai erittäin tarkka leveys- ja pituusastetieto. Muuta kuplan kokoa kunkin karttasijainnin mukaan lisäämällä kenttä **Koko**-ryhmään.

![](media/3-5-create-map-visualizations/3-5_3.png)

## <a name="create-shape-maps"></a>Muotokarttojen luominen
Luo muotokartta valitsemalla **Täytetty kartta** -vaihtoehto Visualisointi-ruudusta. Kuten kuplakartoissakin, sinun on lisättävä jonkinlainen arvo Sijainti-ryhmään, jotta voit käyttää tätä visualisointia. Lisää kenttä Koko-ryhmään täyttövärin voimakkuuden muuttamiseksi.

![](media/3-5-create-map-visualizations/3-5_4.png)

Visualisoinnin vasemmassa yläkulmassa oleva varoituskuvake ilmaisee, että karttaan on lisättävä sijaintitietoja, jotta arvot voidaan merkitä tarkasti. Tämä on erityisen yleinen ongelma, kun sijaintikentän tiedot ovat monitulkintaisia, esimerkiksi jos alueen nimenä on *Washington*, joka voi tarkoittaa osavaltiota tai kaupunkia. Yksi tapa ratkaista tämä ongelma on nimetä pylväs tarkemmin uudelleen, esimerkiksi *Osavaltioksi*. Toinen ratkaisukeino on nollata tietoluokka manuaalisesti valitsemalla **Tietoluokka** Mallinnus-välilehdeltä. Siellä voit määrittää tiedoillesi luokan, esimerkiksi Osavaltio tai Kaupunki.

![](media/3-5-create-map-visualizations/3-5_5.png)

