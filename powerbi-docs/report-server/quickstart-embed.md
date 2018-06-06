---
title: Raportin upottaminen iFramea käyttäen
description: Power BI -raporttipalvelimen asentaminen käy erittäin nopeasti. Palvelimen pitäisi toimia muutamassa minuutissa, kun tarvittavat tiedot on ladattu, asennettu ja määritetty.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/09/2017
ms.author: maghan
ms.openlocfilehash: 56835bfb25c8c930099fadf710137f69fa89fc2e
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2018
ms.locfileid: "30973107"
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>Pikaopas: Power BI -raportin upottaminen iFrame- ja URL-parametreja käyttäen

Voit upottaa minkä tahansa raportin käyttämällä iFramea sovelluksessasi. 

## <a name="url-parameter"></a>URL-parametri

Voit lisätä minkä tahansa URL-osoite raporttiin kyselymerkkijonoparametrin `?rs:Embed=true`.

Esimerkki:

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

Tämä toimii kaikilla Power BI -raporttipalvelimen raporttityypeillä.

## <a name="iframe"></a>iFrame

Kun sinulla on URL-osoite, voit luoda verkkosivustolla iFramen, jonka sisällä raportti isännöidään.

Esimerkki:

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>URL-suodatin

Voit lisätä merkkijonon kyselyparametrin URL-osoitteeseen suodattamaan Power BI -raportilta palautetut tiedot.

Syntaksi on yksinkertainen: aloita raportin URL-osoitteella, lisää kysymysmerkki ja lisää sitten suodattimen syntaksi.

URL?filter=***Table***/***Field*** eq '***value***'

Pidä seuraavat asiat mielessä:

- **Taulukko-** ja **Kenttä**-nimissä merkkikoko on merkitsevä, **arvo** ei ole.
- Voit suodattaa raportilla kenttiä, jotka on piilotettu raporttinäkymässä.
- **Arvo** on sijoitettava puolilainausmerkkeihin.
- Kenttätyypin on oltava merkkijono.
- Taulukoiden ja kenttien nimissä ei voi olla välilyöntejä.

###  <a name="example-filter-on-a-field"></a>Esimerkki: Kentän suodattaminen

Otetaan esimerkiksi [Jälleenmyyntianalyysimalli](../sample-datasets.md). Jos tämä olisi raportin URL-osoite raporttipalvelimella kansiossa, jonka nimi on ”power-bi”:

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

Näet, että jälleenmyyntianalyysimallin karttavisualisoinnissa näkyvät Pohjois-Carolinan ja muiden Yhdysvaltojen osavaltioiden myymälät.

![Jälleenmyyntianalyysimallin karttavisualisointi](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

*NC* on Pohjois-Carolinan myymälöille tallennettu arvo **Store**-taulukon **Alue**-kentässä. Jos haluat suodattaa raportin näyttämään tiedot vain Pohjois-Carolinan myymälöille, lisää URL-osoitteeseen seuraava:

?filter=Store/Territory eq 'NC'

Nyt raportti on suodatettu Pohjois-Carolinassa. Kaikki raporttisivun visualisoinnit näkyvät vain Pohjois-Carolinassa.

![Jälleenmyyntianalyysimallin suodatetut visualisoinnit](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>DAX-kaavan luominen useiden arvojen suodattamiseksi

Toinen tapa suodattaa useita kenttiä on luoda Power BI Desktopissa laskettu sarake, joka yhdistää kaksi kenttää yhdeksi arvoksi. Sitten voit suodattaa tuon arvon.

Meillä on esimerkiksi Jälleenmyyntianalyysimallissa kaksi kenttää: Alue ja Ketju. Voit luoda Power BI Desktopissa [lasketun sarakkeen](../desktop-tutorial-create-calculated-columns.md) (kenttä), jota kutsutaan nimellä TerritoryChain (alueketju). Muista, että **kentän** nimessä ei voi olla välilyöntejä. Tässä on kyseisen sarakkeen DAX-kaava.

TerritoryChain = [Territory] & "-" & [Chain]

Julkaise raportti Power BI -raporttipalvelimella ja suodata URL-kyselymerkkijonon avulla näyttämään vain Lindseys- myymälät, NC.

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>Seuraavat vaiheet

[Pikaopas: Power BI -raportin luominen Power BI -raporttipalvelimeen](quickstart-create-powerbi-report.md)  
[Pikaopas: Sivutetun raportin luominen Power BI -raporttipalvelimeen](quickstart-create-paginated-report.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)