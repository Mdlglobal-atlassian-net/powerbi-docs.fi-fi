---
title: Tietoihin yhdistäminen Power BI Desktopissa
description: Tietoihin yhdistäminen Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 50a5d3d97e90879dcb542c441f129f468a95c6c7
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34285550"
---
# <a name="connect-to-data-in-power-bi-desktop"></a>Tietoihin yhdistäminen Power BI Desktopissa
Power BI Desktopilla voit helposti muodostaa yhteyden alati laajenevaan tietomaailmaan. Jos sinulla ei ole Power BI Desktopia, voit [ladata](http://go.microsoft.com/fwlink/?LinkID=521662) ja asentaa sen.

Power BI Desktopissa on käytössä *monenlaisia* tietolähteitä. Seuraavassa kuvassa näytetään, miten voit yhdistää tietoihin, valitsemalla **Tiedosto**-valintanauhan ja sitten **Nouda tiedot \> Lisää**.

![](media/desktop-connect-to-data/getdatavid_smallv2.gif)

Tässä esimerkissä muodostamme yhteyden **Web** tietolähteeseen.

Kuvittele, että jäät eläkkeelle ja haluat asumaan sinne, jossa on paljon aurinkoa, alhaiset verot ja hyvä terveydenhuolto. Tai... ehkä olet tietoanalyytikko ja haluat tietojen auttavan asiakkaita, kuten vaikka auttamalla sadetakkien valmistajaa aloittamaan kampanjan, kun sataa *paljon*.

Joka tapauksessa löydät verkkoresurssin, joka sisältää kiinnostavaa tietoa näistä ja muista aiheista:

[*http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx*](http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx)

Valitse **Nouda tiedot \> Verkko**  ja kirjoita osoite.

![](media/desktop-connect-to-data/connecttodata_3.png)

Kun valitset **OK**, Power BI Desktopin **Kysely**-toiminto käynnistyy. Power BI Desktop muodostaa yhteyden verkkoresurssiin, ja **Siirtymistoiminnon** ikkuna palauttaa verkkosivulta löydetyt tulokset. Tässä tapauksessa se löysi taulukon (Table 0) ja yleisen asiakirjan. Meitä kiinnostaa taulukko, joten valitsemme sen luettelosta. **Siirtymistoiminnon** ikkuna näyttää esikatselun.

![](media/desktop-connect-to-data/datasources_fromnavigatordialog.png)

Tässä vaiheessa voimme muokata kyselyä ennen taulukon lataamista valitsemalla ikkunan alareunassa **Muokkaa** tai voimme ladata taulukon.

Jos valitaan **Muokkaa**, taulukko ladataan ja kyselyeditori käynnistetään. **Kyselyasetukset**-ruutu avautuu (jos ei, valitse valintanauhassa **Näytä** ja avaa **Kyselyasetukset**-ruutu valitsemalla **Näytä \> kyselyasetukset**). Se näyttää tältä.

![](media/desktop-connect-to-data/designer_gsg_editquery.png)

Nämä pisteet ovat numeroiden sijaan tekstiä, vaikka niiden pitää olla lukuja meidän tarkoituksessamme. Voit vaihtaa sitä helposti napsauttamalla vain hiiren kakkospainikkeella sarakkeen otsikkoa ja valitsemalla **Muuta tyyppi \> Kokonaisluku**. Valitse useita sarakkeita, valitse ensimmäinen sarake, paina **VAIHTO**-näppäin pohjaan, valitse vierekkäisiä sarakkeita ja vaihda sitten kaikki valitut sarakkeet napsauttamalla hiiren kakkospainikkeella jotain valittua sarakeotsikkoa. Paina **CTRL**, kun valitset sarakkeita, jotka eivät ole vierekkäin.

![](media/desktop-connect-to-data/designer_gsg_changedatatype.png)

**Kyselyasetukset**-kohdassa **Käytössä olevat vaiheet** kuvastavat tehtyjä muutoksia. Samalla, kun teet muita muutoksia tietoihin, kyselyeditori tallentaa nämä muutokset kohtaan **Käytössä olevat vaiheet**, jota voit säätää, järjestää, käyttää uudelleen tai poistaa tarpeen mukaan.

![](media/desktop-connect-to-data/designer_gsg_appliedsteps_changedtype.png)

Taulukkoon voi edelleen tehdä muutoksia sen jälkeen, kun se on ladattu, mutta toistaiseksi tämä riittää. Kun kaikki on valmista, valitaan **Sulje ja ota käyttöön** **Aloitus**-valintanauhasta, ja Power BI Desktop ottaa muutokset käyttöön ja sulkee kyselyeditorin.

![](media/desktop-connect-to-data/connecttodata_closenload.png)

Kun tietomalli on ladattu, voimme Power BI Desktopin **Raportti**-näkymässä aloittaa visualisointien luomisen vetämällä kentät piirtoalustan.

![](media/desktop-connect-to-data/connecttodata_dragontoreportview.png)

Kyseessä on tietysti yksinkertainen malli, joka sisältää yhden tietoyhteyden. Useimmissa Power BI Desktop -raporteissa meillä on yhteydet eri tietolähteisiin tarpeidesi mukaan suhteilla, jotka tuottavat monipuolisen tietomallin. 

### <a name="next-steps"></a>Seuraavat vaiheet
Voit tehdä kaikenlaista Power BI Desktopilla. Saat lisätietoja sen toiminnoista seuraavista resursseista:

* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)
* [Power BI Desktopin kyselyiden yleiskatsaus](desktop-query-overview.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](desktop-common-query-tasks.md)   

Haluatko antaa palautetta? Hienoa – Käytä **Lähetä idea** -valikon kohtaa Power BI Desktopissa tai katso [yhteisön palautetta](http://community.powerbi.com/t5/Community-Feedback/bd-p/community-feedback). Odotamme kuulevamme sinusta!

![](media/desktop-connect-to-data/sendfeedback.png)

