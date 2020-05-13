---
title: Vinkkejä laadukkaiden Power BI -koontinäyttöjen suunnitteluun
description: Vinkkejä laadukkaiden Power BI -koontinäyttöjen suunnitteluun
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/14/2019
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: a989d0e31faf5bbe919782df82e90b0943f562ff
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348823"
---
# <a name="tips-for-designing-a-great-power-bi-dashboard"></a>Vinkkejä laadukkaiden Power BI -koontinäyttöjen suunnitteluun
Nyt kun olet luonut koontinäytön ja lisännyt siihen ruutuja, mieti, miten voisit parantaa sen toiminnallisuutta. Yleensä tämä tarkoittaa tärkeimpien tietojen korostamista ja koontinäytön selkeyttämistä.

![Markkinoinnin ja myynnin mallikoontinäyttö](media/service-dashboards-design-tips/power-bi-marketing-sample-dashboard.png)

> [!TIP]
> Pidätkö tästä koontinäytöstä? Voit ladata sen ja siihen liittyvät raportit AppSourcesta. Siirry kohtaan **Nouda tiedot** > **Palvelut**. Tee haku **Microsoft Sample – myynti ja markkinointi** > **Hanki se nyt**.

Seuraavassa on muutamia koontinäyttöjä koskevia vinkkejä.

## <a name="dashboard-design-best-practices-video"></a>Koontinäytön suunnittelun parhaiden käytäntöjen video

SQLBI.comin Marco Russo antaa suunnitteluvinkkejä videolla [koontinäytön suunnittelun parhaat käytännöt Power BI:ssä](https://www.youtube.com/watch?v=-tdkUYrzrio).

## <a name="consider-your-audience"></a>Mieti yleisöäsi
Mitä ovat tärkeimpiä mittareita, jotka auttavat heitä tekemään päätöksiä? Miten koontinäyttöä käytetään? Mitkä opitut tai kulttuuriset olettamat saattavat vaikuttaa visualisointivalintoihin? Mitä tietoja yleisö tarvitsee onnistumiseen ja menestymiseen?

Koontinäyttö on yhteenveto tietojen nykyisestä tilasta. Koontinäyttö perustuu pohjana oleviin raportteihin ja tietojoukkoihin, jotka usein sisältävät paljon tietoja. Lukijat voivat siirtyä raportteihin koontinäytöstä. Älä siis sijoita yksityiskohtia koontinäyttöön, ellet halua lukijoiden keskittyvän juuri niihin.

Missä koontinäyttöä näytetään? Jos sitä näytetään suurikokoisessa näytössä, siihen voi lisätä paljon sisältöä. Mutta jos lukijat tarkastelevat sitä tablet-laitteissa, vähemmän ruutuja sisältävä koontinäyttö on helpommin luettavissa.

## <a name="tell-a-story-on-one-screen"></a>Kerro tarina yhdellä ruudulla
Koska koontinäytöt on tarkoitettu tärkeiden tietojen tarkasteluun yhdellä silmäyksellä, kaikki ruudut yhdessä näytössä toimii parhaiten. Voitko välttää vierityspalkkien käyttämisen koontinäytössä?

Onko koontinäyttö sekava?  Poista kaikki muut paitsi olennaisimmat tiedot, joita voi lukea ja tulkita helposti.

## <a name="make-use-of-full-screen-mode"></a>Käytä koko näytön tilaa
Kun esität koontinäytön, näytä se [koko näytön tilassa](../consumer/end-user-focus.md) ilman häiriötekijöitä.

## <a name="accent-the-most-important-information"></a>Näytä tärkeimmät tiedot suurimmassa koossa
Jos koontinäytön teksti ja visualisoinnit ovat kaikki samaa kokoa, lukijan on vaikea keskittyä tärkeimpään asiaan. Esimerkiksi korttivisualisoinnit ovat hyvä tapa esittää tärkeitä lukuja näkyvästi:  
![Korttivisualisointi](media/service-dashboards-design-tips/pbi_card.png)

Muista tarjota konteksti.  

Lue lisätietoja [vain luvun sisältävän ruudun luonnista](../visuals/power-bi-visualization-card.md).

## <a name="place-the-most-important-information"></a>Sijoita tärkeimmät tiedot järkevästi
Useimmat henkilöt lukevat ylhäältä alas. Sijoita tärkein tieto vasempaan yläkulmaan ja näytä lisää yksityiskohtia katsojan lukusuunnan mukaisesti (vasemmalta oikealle, ylhäältä alas).

## <a name="use-the-right-visualization-for-the-data"></a>Käytä tiedoissa oikeaa visualisointia
Vältä erilaisten visualisointien lisäämistä vain vaihtelun vuoksi.  Visualisointien pitäisi maalata tietty kuva, joka on helppo sisäistää ja ymmärtää.  Joillekin tiedoille ja visualisoinneille riittää hyvin yksinkertainen grafiikka. Jotkin muut tiedot edellyttävät monimutkaisempaa visualisointia. Muista silloin käyttää otsikoita, nimiä ja muita lukijaa auttavia mukautuksia.  

* Käytä varoen visualisointeja, jotka näyttävät kauniilta, mutta joita on vaikea lukea. Tällaisia ovat esimerkiksi kolmiulotteiset kaaviot. 
* Ympyräkaaviot, rengaskaaviot, mittarit ja muut pyöreät kaaviotyypit ovat hienoja, mutta ne eivät valitettavasti ole paras vaihtoehto tietojen visualisointiin. Ympyräkaaviot ovat parhaimmillaan, kun niissä on alle kahdeksan luokkaa. Koska arvoja ei voi tarkastella rinnakkain ympyräkaaviossa, niiden vertaaminen on vaikeampaa kuin palkki- ja pylväskaavioissa. Ympyräkaaviot toimivat parhaiten, kun osien vertailun sijaan tarkastellaan tietyn osan suhdetta kokonaisuuteen. Mittarikaaviot puolestaan ovat hyviä nykyisen tilanteen esittämisessä suhteessa tavoitteeseen.
* Käytä akselien asteikkoja, ulottuvuuksien järjestystä ja dimensioarvoja kuvaavia värejä johdonmukaisesti kaaviosta toiseen.
* Esitä kvantitatiiviset tiedot kompaktisti ja siististi. Älä käytä luvuissa yli kolmea tai neljää numeroa. Vältä runsasta desimaalien käyttöä ja skaalaa luvut mahdollisimman suuriin mittareihin, kuten tuhansista miljooniin: ”3,4 miljoonaa” mieluummin kuin ”3 400 000”.
* Älä yhdistä eri tarkkuuksia ja aikoja. Varmista, että käytetyt ajanjaksot on helppo käsittää. Älä esimerkiksi laita samaan visualisointiin viime kuukautta kuvaavaa kaaviota ja suodatettuja kaavioita vuoden joltain muulta kuukaudelta rinnakkain.
* Vältä myös suurten ja pienten mittarien yhdistelemistä samalle asteikolle esimerkiksi viivakaaviona ja palkkikaaviona. Esimerkki tällaisesta on, että yksi mittari on miljoonia ja toinen tuhansia. Tällöin tuhansia mittaavan kaavion eroja voi olla vaikea havaita. Jos yhdistely on välttämätöntä, valitse visualisointi, jossa voi käyttää toista akselia.
* Vältä kaavioiden täyttämistä arvopisteiden otsikoilla, jotka eivät ole välttämättömiä. Palkkikaavioissa arvot ovat yleensä ymmärrettävissä ilman varsinaisia lukuja.
* Kiinnitä huomiota [kaavioiden lajitteluun](../consumer/end-user-change-sort.md). Jos haluat kiinnittää huomiota suurimpaan tai pienimpään lukuun, lajittele mittarin mukaan. Jos haluat, että tietty luokka on nopeasti löydettävissä useiden muiden joukosta, lajittele akselin mukaan.  

Lisää visualisointikohtaisia ohjeita on artikkelissa [Visualisointityypit Power BI:ssä](../visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).  

## <a name="learn-more-about-dashboard-design"></a>Lisätietoja koontinäyttörakenteesta
Koontinäyttöjen rakenne liittyy läheisesti yleisiin hahmottamisen ja ryhmittelyn periaatteisiin ja käytäntöihin. Suosittelemme tähän liittyen opiskelemaan käytännöllisen tiedon esittämistä asiayhteydessä. Meidän blogitekstiemme lisäksi myös muualla verkossa on paljon avointa tietoa ja valmiita resursseja tähän liittyen. Suosittelemiamme teoksia:

* Stephen Few: *Information Dashboard Design*  
* Stephen Few: *Show Me the Numbers*  
* Stephen Few: *Now You See It*  
* Edward Tufte: *Envisioning Information*  
* Andrew Abela: *Advanced Presentations by Design*   

## <a name="next-steps"></a>Seuraavat vaiheet
[Koontinäytön luominen raportista](service-dashboard-create.md)  
[Power BI -palvelun peruskäsitteitä suunnittelijoille](../fundamentals/service-basic-concepts.md)  
Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
