---
title: Lisää Power BI-raporttiparametreja URL-osoitteen kautta
description: Voit suodattaa raportin käyttämällä URL-osoitteen kyselyparametreja ja jopa suodattaa useamman kuin yhden kentän.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: aeaea6d14cf8f4fd62fbbf5098e68429fe40b96a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34471935"
---
# <a name="filter-a-report-using-query-string-parameters-in-the-url"></a>Raportin suodattaminen URL-osoitteen kyselymerkkijonoparametrien avulla
Kun avaat raportin Power BI -palvelussa, raportin jokaisella sivulla on oma yksilöllinen URL-osoitteensa. Voit suodattaa raporttisivun käyttämällä Suodattimet-ruutua raportin alustalla.  Voit myös lisätä kyselyparametrit URL-osoitteeseen raportin suodattamiseksi. Ehkäpä sinulla on raportti, jonka haluat näyttää työtovereille, ja haluat suodattaa sen heille valmiiksi. Eräs tapa tehdä tämä on aloittaa raportin oletusarvoisesta URL-osoitteesta ja lisätä suodatinparametreja URL-osoitteeseen ja lähettää sitten heille koko URL-osoite sähköpostilla.

![Power BI -raportti palvelussa](media/service-url-filters/power-bi-report2.png)

<iframe width="640" height="360" src="https://www.youtube.com/embed/WQFtN8nvM4A?list=PLv2BtOtLblH3YE_Ycas5B1GtcoFfJXavO&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="query-string-parameter-syntax-for-filtering"></a>Kyselyn merkkijonon parametrisyntaksi suodattamista varten
Syntaksi on melko yksinkertainen: aloita raportin URL-osoitteella, lisää kysymysmerkki ja lisää sitten suodattimen syntaksi.

URL?filter=***Table***/***Field*** eq '***value***'

![URL-osoite ja suodatin](media/service-url-filters/power-bi-filter-urls7b.png)

* **Taulukon** ja **kentän** nimissä kirjainkoko on merkitsevä, **arvo** ei ole.
* Kentät, jotka on piilotettu raporttinäkymästä, voidaan edelleen suodattaa.
* **Arvo** on sijoitettava puolilainausmerkkeihin.
* Kenttätyypin on oltava luku tai merkkijono
* Taulukoiden ja kenttien nimissä ei voi olla välilyöntejä.

Jos tuntuu sekavalta, jatka lukemista, kohta asia selviää.  

## <a name="filter-on-a-field"></a>Kentän suodattaminen
Oletetaan, että raportin URL-osoite on seuraava.

![alkava URL](media/service-url-filters/power-bi-filter-urls6.png)

Näemme karttavisualisoinnissa (edellä), että meillä on varastoja Pohjois-Carolinassa.

>[!NOTE]
>Tämä esimerkissä perustuu [Jälleenmyyntianalyysimalliin](sample-datasets.md).
> 

Jos haluat suodattaa raportin näyttämään tiedot vain myymälöille ”NC” (Pohjois-Carolina), lisää URL-osoitteeseen

?filter=Store/Territory eq 'NC'

![URL-osoite ja suodatin](media/service-url-filters/power-bi-filter-urls7.png)

>[!NOTE]
>*NC* on tallennettu arvo **Alue**-kenttään **Store**-taulukossa.
> 
> 

Raporttimme on suodatettu Pohjois-Carolinassa. Kaikki raporttisivun visualisoinnit näkyvät vain Pohjois-Carolinassa.

![](media/service-url-filters/power-bi-report4.png)

## <a name="filter-on-multiple-fields"></a>Useiden kenttien suodattaminen
Voit myös suodattaa useita kenttiä lisäämällä lisäparametrit URL-osoitteeseesi. Palataan takaisin alkuperäisen suodattimen parametriin.

```
?filter=Store/Territory eq 'NC'
```

Voit suodattaa lisäkenttiä, lisätä `and` ja toisen kentän samassa muodossa kuin edellä. Tässä esimerkki:

```
?filter=Store/Territory eq 'NC' and Store/Chain eq 'Fashions Direct'
```

<iframe width="640" height="360" src="https://www.youtube.com/embed/0sDGKxOaC8w?showinfo=0" frameborder="0" allowfullscreen></iframe>


### <a name="using-dax-to-filter-on-multiple-values"></a>DAX-kielen käyttäminen useiden arvojen suodattamisessa
Toinen tapa suodattaa useita kenttiä on luoda laskettu sarake, joka yhdistää kaksi kenttää yhdeksi arvoksi. Sitten voit suodattaa tuon arvon.

Meillä on esimerkiksi kaksi kenttää: Alue ja Ketju. Luo Power BI Desktopissa [uusi laskettu sarake](desktop-tutorial-create-calculated-columns.md) (kenttä), jota kutsutaan nimellä TerritoryChain (alueketju). Muista, että **kentän** nimessä ei voi olla välilyöntejä. Tässä on kyseisen sarakkeen DAX-kaava.

TerritoryChain = [Territory] & " - " & [Chain]

Julkaise raportti Power BI -palvelussa ja suodata URL-kyselymerkkijonon avulla näyttämään vain Lindseys- myymälät, NC.

    https://app.powerbi.com/groups/me/reports/8d6e300b-696f-498e-b611-41ae03366851/ReportSection3?filter=Store/TerritoryChain eq 'NC–Lindseys'

## <a name="pin-a-tile-from-a-filtered-report"></a>Kiinnitä ruutu suodatetusta raportista
Kun olet suodattanut raportin käyttämällä kyselymerkkijonon parametreja, voit kiinnittää visualisointeja kyseisestä raportista raporttinäkymääsi. Raporttinäkymän ruutu tuo näkyviin suodatetut tiedot, ja valitsemalla kyseisen raporttinäkymän ruutu avaa raportin, jota käytettiin sen luomiseen.  Kuitenkin URL-osoitteen kautta tehtyä suodatusta ei tallenneta raportin kanssa, ja raporttinäkymä-ruutu on valittuna, jolloin raportti avautuu suodattamattomassa tilassa.  Tämä tarkoittaa, että raporttinäkymäruudussa näytettävät tiedot eivät vastaa raportin visualisoinnissa näkyviä tietoja.

Saattaa olla tapauksia, joissa tästä on hyötyä, kun haluat nähdä eri tuloksia suodatettuna raporttinäkymässä ja suodattamattomana raportissa.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
On muutamia asioita, jotka tulee ottaa huomioon merkkijonon kyselyparametreja käytettäessä.

* Power BI -raporttipalvelimessa voit [välittää raporttiparametrit](https://docs.microsoft.com/sql/reporting-services/pass-a-report-parameter-within-a-url?view=sql-server-2017.md) sisällyttämällä ne raportin URL-osoitteeseen. Näissä URL-parametreissa ei ole etuliitettä, koska ne on välitetty suoraan raportin käsittelymoduuliin. 
* Kyselyn merkkijonon suodatus ei toimi toiminnoissa [Julkaise verkkoon](service-publish-to-web.md) tai Power BI Embedded.   
* Kenttätyypin on oltava luku tai merkkijono.
* Taulukoiden ja kenttien nimissä ei voi olla välilyöntejä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Visualisoinnin kiinnittäminen koontinäyttöön](service-dashboard-pin-tile-from-report.md)  
[Kokeile sitä – se on ilmainen!](https://powerbi.com/)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

