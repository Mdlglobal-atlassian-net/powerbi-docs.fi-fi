---
title: Tietojen historiatiedot
description: Moderneissa liiketoimintatietojen projekteissa tietovirran ymmärtäminen tietolähteestä kohteeseen on tärkeä haaste monille asiakkaille.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.date: 02/27/2020
ms.author: painbar
LocalizationGroup: ''
ms.openlocfilehash: 101217023576783a32491b21ba254d54736b27db
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348202"
---
# <a name="data-lineage"></a>Tietojen historiatiedot
Moderneissa liiketoimintatietojen projekteissa tietovirran ymmärtäminen tietolähteestä kohteeseen voi olla haastavaa. Haaste on vieläkin suurempi, jos olet luonut edistyneitä analyysiprojekteja, jotka kattavat useita tietolähteitä, artefakteja ja riippuvuuksia. Esimerkiksi kysymyksiin ”Mitä tapahtuu, jos muutan näitä tietoja?” Miksi tämä raportti ei ole ajan tasalla? voi olla vaikea vastata. Niiden ymmärtäminen voi vaatia asiantuntijaryhmän tai syvällistä tutkintaa. Olemme suunnitelleet historiatietonäkymän, jonka avulla näihin kysymyksiin voi vastata.

![Power BI:n historiatietonäkymä](media/service-data-lineage/service-data-lineage-view.png)
 
Power BI sisältää useita artefaktityyppejä, kuten koontinäyttöjä, raportteja, tietojoukkoja ja tietovoita. Monet tietojoukot ja tietovuot muodostavat yhteyden ulkoisiin tietolähteisiin, kuten SQL Serveriin, ja muissa työtiloissa oleviin ulkoisiin tietojoukkoihin. Kun tietojoukko on ulkoinen työtilassasi olevaan työtilaan nähden, se saattaa olla IT:n työntekijän tai toisen analyytikon omistamassa työtilassa. Ulkoisten tietolähteiden ja tietojoukkojen takia on vaikeampi tietää, mistä tiedot ovat lopulta peräisin. Esittelemme monimutkaisia ja yksinkertaisiakin projekteja varten tietojen historiatietojen näkymän.

Tietojen historiatietojen näkymässä näet kaikkien työtilassa olevien artefaktien väliset historiatiedot ja kaikki sen ulkoiset riippuvuudet. Se näyttää yhteydet kaikkien työtilan artefaktien välillä, mukaan lukien yhteydet tietovoihin sekä ennen että jälkeen.

## <a name="explore-lineage-view"></a>Tutki tietojen historiatietojen näkymää

Jokaisessa työtilassa riippumatta siitä, onko se uusi vai perinteinen, on automaattisesti tietojen historiatietonäkymä. Sen tarkastelemiseen työtilassa tarvitaan vähintään osallistujan rooli. Katso lisätietoja tämän artikkelin kohdasta [Oikeudet](#permissions).

* Jos haluat käyttää tietojen historiatietojen näkymää, siirry työtilan luettelonäkymään. Napauta **Luettelonäkymä**-kohdan vieressä olevaa nuolta ja valitse **Tietojen historiatietojen näkymä**.

   ![Siirtyminen historiatietonäkymään](media/service-data-lineage/service-data-lineage-view-select.png)

Tässä näkymässä näkyvät kaikki työtilan artefaktit ja tiedon kulku artefaktista toiseen.

**Tietolähteet**

Näet tietolähteet, joista tietojoukot ja tietovuot saavat tietonsa. Tietolähteen korteista näet lisää tietoja, joiden avulla voit tunnistaa lähteen. Esimerkiksi Azuren SQL-palvelimesta näet myös tietokannan nimen.

![Tietojen historiatietojen näkymän tietolähde ilman yhdyskäytävää](media/service-data-lineage/service-data-lineage-data-source-card.png)
 
**Yhdyskäytävät**

Jos tietolähde on yhdistetty paikallisen yhdyskäytävän kautta, yhdyskäytävän tiedot lisätään tietolähteen korttiin. Jos sinulla on oikeudet joko yhdyskäytävän järjestelmänvalvojana tai tietolähteen käyttäjänä, näkyvissä on lisätietoja, kuten yhdyskäytävän nimi.

![Tietojen historiatietojen näkymän tietolähde ja yhdyskäytävä](media/service-data-lineage/service-data-lineage-data-gateway-card.png)

**Tietojoukot ja tietovuot**
 
Tietojoukkojen ja tietovoiden kohdalla näet viimeisimmän päivitysajan sekä sen, onko tietojoukko tai tietovuo kohteen sertifioidun tai ylennetty.

![Ylennetyt ja sertifioidut tietojoukot historiatietonäkymässä](media/service-data-lineage/service-data-lineage-promoted-certified.png)
 
Jos työtilan raportti perustuu toisessa työtilassa olevaan tietojoukkoon tai tietovuohon, lähdetyötilan nimi näkyy tietojoukon tai tietovuon kortissa. Siirry haluamaasi työtilaan valitsemalla kyseisen lähdetyötilan nimi.

* Näet asetusvalikon mistä tahansa artefaktista valitsemalla **Enemmän vaihtoehtoja** (...). Se sisältää kaikki samat toiminnot, jotka ovat käytettävissä luettelonäkymässä.

Jos haluat tarkastella minkä tahansa artefaktin metatietoja, valitse artefaktin kortti. Artefaktin lisätiedot näkyvät sivuruudussa. Alla olevassa kuvassa valitun tietojoukon metatiedot näkyvät sivuruudussa.

![Sivuruutu, jossa on lisätietoja](media/service-data-lineage/service-data-lineage-side-pane.png)
 
## <a name="show-lineage-for-any-artifact"></a>Näytä minkä tahansa artefaktin tietojen historiatiedot 

Oletetaan, että haluat tarkastella tietyn artefaktin tietojen historiatietoja.

* Valitse kaksoisnuolet artefaktin alla.

   ![Tietyn artefaktin historiatietojen korostaminen](media/service-data-lineage/service-data-lineage-specific-artifact.png)

   Power BI korostaa kaikki kyseiseen artefaktiin liittyvät artefaktit ja himmentää loput. 

## <a name="navigation-and-full-screen"></a>Siirtyminen ja koko näyttö 

Tietojen historiatietojen näkymä on vuorovaikutteinen pohja. Voit käyttää hiirtä ja kosketuslevyä pohjaan siirtymiseen sekä lähentämiseen tai loitontamiseen.

* Lähennä ja loitonna käyttämällä joko oikeassa alakulmassa olevaa valikkoa, hiirtä tai kosketuslevyä.
* Jos haluat saada enemmän tilaa kaaviolle, käytä koko näytön vaihtoehtoa oikeassa alakulmassa. 

    ![Lähennä tai loitonna tai käytä koko näyttöä](media/service-data-lineage/service-data-lineage-zoom.png)

## <a name="permissions"></a>Käyttöoikeudet

* Tietojen historiatietojen näkymän tarkastelemiseen tarvitaan Power BI Pro -käyttöoikeus.
* Tietojen historiatietojen näkymä on vain niiden käyttäjien käytettävissä, joilla on työtilan käyttöoikeus.
* Käyttäjillä on oltava järjestelmänvalvojan, jäsenen tai osallistujan rooli työtilassa. Katselijan roolissa olevat käyttäjät eivät voi siirtyä tietojen historiatietojen näkymään.


## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

- Tietojen historiatietojen näkymä ei ole käytettävissä Internet Explorerissa. Katso lisätietoja kohdasta [Power BI:n tuetut selaimet](../fundamentals/power-bi-browsers.md).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Johdanto tietojoukkojen käyttöön eri työtiloissa (esikatselu)](../connect-data/service-datasets-across-workspaces.md)
* [Tietojoukkojen vaikutusanalyysi](service-dataset-impact-analysis.md)
