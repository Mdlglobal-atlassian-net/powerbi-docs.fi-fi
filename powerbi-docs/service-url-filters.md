---
title: Lisää Power BI-raporttiparametreja URL-osoitteen kautta
description: Voit suodattaa raportin käyttämällä URL-osoitteen kyselyparametreja ja jopa suodattaa useamman kuin yhden kentän.
author: mihart
manager: annebe
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/09/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 99df72454fce76c648cf2f354f3a8ec225284c09
ms.sourcegitcommit: 52278d8e0c23ae5eaf46b10a6a2f1fb071a0f1cc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2018
ms.locfileid: "40257216"
---
# <a name="filter-a-report-using-query-string-parameters-in-the-url"></a>Raportin suodattaminen URL-osoitteen kyselymerkkijonoparametrien avulla
Kun avaat raportin Power BI -palvelussa, raportin jokaisella sivulla on oma yksilöllinen URL-osoitteensa. Voit suodattaa raporttisivun käyttämällä Suodattimet-ruutua raportin alustalla.  Voit myös lisätä kyselymerkkijonoparametrit URL-osoitteeseen, jolloin raportti suodatetaan jo etukäteen. Ehkäpä sinulla on raportti, jonka haluat näyttää työtovereille, ja haluat suodattaa sen heille valmiiksi. Eräs tapa tehdä tämä on aloittaa raportin oletusarvoisesta URL-osoitteesta, lisätä suodatinparametreja URL-osoitteeseen ja lähettää sitten heille uusi URL-osoite kokonaisuudessaan sähköpostilla.

![Power BI -raportti palvelussa](media/service-url-filters/power-bi-report2.png)

## <a name="uses-for-query-string-parameters"></a>Kyselymerkkijonoparametrien käyttötavat
Oletetaan, että käytät Power BI Desktopia ja haluat luoda raportin, jossa on linkit muihin Power BI -raportteihin – mutta haluat näyttää vain joitakin muiden raporttien tietoja. Suodata raportit ensin kyselymerkkijonoparametrien avulla ja tallenna URL-osoitteet. Luo seuraavaksi Desktopissa taulukko, jossa käytät uusien raporttien URL-osoitteita.  Sitten voit julkaista ja jakaa raportin.

Toinen kyselymerkkijonoparametrien käyttötapa on hyödyllinen edistynyttä Power BI -ratkaisua luotaessa.  DAX-kielen avulla voit luoda raportin, joka luo suodatetun raportin URL-osoitteen dynaamisesti asiakkaan nykyisessä raportissa tekemän valinnan perusteella. Kun asiakas valitsee URL-osoitteen, hän näkee vain itselleen tarkoitetut tiedot. 

## <a name="query-string-parameter-syntax-for-filtering"></a>Kyselyn merkkijonon parametrisyntaksi suodattamista varten
Parametreilla voit suodattaa raportista yhden arvon tai useita arvoja, vaikka kyseiset arvot sisältäisivät välilyöntejä tai erikoismerkkejä. Perussyntaksi on melko yksinkertainen: aloita raportin URL-osoitteella, lisää kysymysmerkki ja lisää sitten suodattimen syntaksi.

URL?filter=***Table***/***Field*** eq '***value***'

![URL-osoite ja suodatin](media/service-url-filters/power-bi-filter-urls7b.png)

* **Table** (Taulukko)- ja **Field** (Kenttä) -nimissä merkkikoko on merkitsevä, kun taas **value** (arvo) -kohdassa näin ei ole.
* Kentät, jotka on piilotettu raporttinäkymästä, voidaan edelleen suodattaa.

### <a name="field-types"></a>Kenttätyypit
Kenttätyyppi voi olla luku, päivämäärä ja aika tai merkkijono, ja käytetyn tyypin on vastattava tietojoukossa määritettyä tyyppiä.  Esimerkiksi taulukon sarakkeen määrittäminen Merkkijono-tyyppiseksi ei ole toimiva ratkaisu, jos etsit Päivämäärä-tyyppiseksi määritetyssä tietojoukon sarakkeessa sijaitsevaa päivämäärä/aika-tietoa tai numeerista arvoa (esimerkiksi Table/StringColumn eq 1).

* **Merkkijonot** on sijoitettava puolilainausmerkkeihin – 'esimiehen nimi'.
* **Luvut** eivät edellytä erityistä muotoilua.
* **Päivämäärät ja ajat** on sijoitettava puolilainausmerkkeihin ja niiden edellä on oltava sana **DateTime**.

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

Raporttimme on suodatettu Pohjois-Carolinassa. Kaikki raporttisivun visualisoinnit näkyvät vain Pohjois-Carolinassa.

![](media/service-url-filters/power-bi-report4.png)

## <a name="filter-on-multiple-fields"></a>Useiden kenttien suodattaminen
Voit myös suodattaa useita kenttiä lisäämällä lisäparametrit URL-osoitteeseesi. Palataan takaisin alkuperäisen suodattimen parametriin.

```
?filter=Store/Territory eq 'NC'
```

Voit suodattaa lisäkenttiä lisäämällä **and**-sanan ja toisen kentän samassa muodossa kuin edellä. Tässä esimerkki:

```
?filter=Store/Territory eq 'NC' and Store/Chain eq 'Fashions Direct'
```

<iframe width="640" height="360" src="https://www.youtube.com/embed/0sDGKxOaC8w?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="operators"></a>Operaattorit
Power BI tukee useita muitakin operaattoreita kuin **and**. Seuraavassa taulukossa on lueteltu kyseiset operaattorit ja niiden tukemat sisältötyypit.

|operaattori  | määritelmä | merkkijono  | luku | Päivämäärä |  Esimerkki|
|---------|---------|---------|---------|---------|---------|
|**and**     | ja |  kyllä      | kyllä |  kyllä|  product/price le 200 and price gt 3.5 |
|**eq**     | yhtä suuri kuin |  kyllä      | kyllä   |  kyllä       | Address/City eq 'Redmond' |
|**ne**     | eri suuri kuin |   kyllä      | kyllä  | kyllä        |  Address/City ne 'London' |
|**ge**     |  suurempi tai yhtä suuri kuin       | ei | kyllä |kyllä |  product/price ge 10
|**gt**     | suurempi kuin        |ei | kyllä | kyllä  | product/price gt 20
|**le**     |   pienempi tai yhtä suuri kuin      | ei | kyllä | kyllä  | product/price le 100
|**lt**     |  pienempi kuin       | ei | kyllä | kyllä |  product/price lt 20
|**in****     |  mukaan lukien       | ei | ei |  kyllä | Student/Age in (27, 29)


\** Käytettäessä **in**-operaattoria **in**-operaattorin oikealla puolella olevat arvot voidaan merkitä sulkeiden sisälle pilkuilla erotettuna luettelona tai yksittäisenä lausekkeena, joka palauttaa kokoelman.

### <a name="numeric-data-types"></a>Numeeriset tietotyypit
Power BI:n URL-suodatin voi sisältää lukuja seuraavissa muodoissa.

|Luvun tyyppi  |Esimerkki  |
|---------|---------|
|**kokonaisluku**     |   5      |
|**pitkä**     |   5L tai 5l      |
|**kaksinkertainen**     |   5.5 tai 55e-1 tai 0.55e+1 tai 5D tai 5d tai 0.5e1D tai 0.5e1d tai 5.5D tai 5.5d tai 55e-1D tai 55e-1d     |
|**desimaaliluku**     |   5M tai 5m tai 5.5M tai 5.5m      |
|**liukuluku**     | 5F tai 5f tai 0.5e1F tai 0.5e-1d        |

### <a name="date-data-types"></a>Päivämäärän tietotyypit
Power BI tukee sekä OData V3- että V4-versioita **Date**- ja **DateTimeOffset**-tietotyypeille.  Päivämäärät esitetään EDM-muodossa (2019-02-12T00:00:00). Käytännössä tämä tarkoittaa, että kun määrität päivämäärän muodossa VVVV-KK-PP, Power BI tulkitsee sen muodossa VVVV-KK-PPT00:00:00.

Miksi tämä ero on merkityksellinen? Oletetaan, että luot kyselymerkkijonoparametrin **Table/Date gt 2018-08-03**.  Sisältävätkö tulokset elokuun kolmannen päivän 2018 vai alkavatko ne elokuun neljännestä 2018? Koska Power BI kääntää kyselyn muotoon **Table/Date gt 2018-08-03T00:00:00**, tulokset sisältävät päivämäärät, joilla on nollasta poikkeava aikaosa, koska nämä päivämäärät ovat suurempia kuin **2018-08-03T00:00:00**.

## <a name="special-characters-in-url-filters"></a>URL-suodattimien erikoismerkit
Erikoismerkit ja välilyönnit edellyttävät lisämuotoiluja. Kun kysely sisältää välilyöntejä, ajatusviivoja tai muita kuin ASCII-merkkejä, lisää kyseisiin erikoismerkkeihin etuliitteeksi *ohjauskoodi* (**_x**) ja 4-numeroinen **Unicode-tunnus**. Jos Unicode-tunnuksessa on alle 4 merkkiä, sinun on täydennettävä sitä nollilla. Seuraavassa on joitakin esimerkkejä.

|Tunniste  |Unicode  | Koodaus Power BI:ssä  |
|---------|---------|---------|
|**Taulukon nimi**     | Välilyönti: 0x20        |  Taulukon_x0020_nimi       |
|**Sarakkeen**@**numero**     |   @: 0x40     |  Sarakkeen_x0040_numero       |
|**[Sarake]**     |  [:0x005B ]:0x0050       |  _x0058_Sarake_x0050       |
|**Sarake+Plus**     | +:0x2B        |  Sarake_x002B_Plus       |

Table_x0020_Name/Column_x002B_Plus eq 3 ![erikoismerkkejä hahmontava taulukkovisualisointi](media/service-url-filters/power-bi-special-characters1.png)


Table_x0020_Special/_x005B_Column_x0020_Brackets_x005D_ eq '[C]' ![erikoismerkkejä hahmontava taulukkovisualisointi](media/service-url-filters/power-bi-special-characters2.png)

### <a name="use-dax-to-filter-on-multiple-values"></a>DAX-kielen käyttäminen useiden arvojen suodattamisessa
Toinen tapa suodattaa useita kenttiä on luoda laskettu sarake, joka yhdistää kaksi kenttää yhdeksi arvoksi. Sitten voit suodattaa tuon arvon.

Meillä on esimerkiksi kaksi kenttää: Alue ja Ketju. Luo Power BI Desktopissa [uusi laskettu sarake](desktop-tutorial-create-calculated-columns.md) (kenttä), jota kutsutaan nimellä TerritoryChain (alueketju). Muista, että **kentän** nimessä ei voi olla välilyöntejä. Tässä on kyseisen sarakkeen DAX-kaava.

TerritoryChain = [Territory] & " - " & [Chain]

Julkaise raportti Power BI -palvelussa ja suodata URL-kyselymerkkijonon avulla näyttämään vain Lindseys- myymälät, NC.

    https://app.powerbi.com/groups/me/reports/8d6e300b-696f-498e-b611-41ae03366851/ReportSection3?filter=Store/TerritoryChain eq 'NC–Lindseys'

## <a name="pin-a-tile-from-a-filtered-report"></a>Kiinnitä ruutu suodatetusta raportista
Kun olet suodattanut raportin käyttämällä kyselymerkkijonon parametreja, voit kiinnittää visualisointeja kyseisestä raportista raporttinäkymääsi.  Raporttinäkymän ruutu tuo näkyviin suodatetut tiedot, ja valitsemalla kyseisen raporttinäkymän ruutu avaa raportin, jota käytettiin sen luomiseen.  Kuitenkin URL-osoitteen kautta tehtyä suodatusta ei tallenneta raportin kanssa, ja raporttinäkymä-ruutu on valittuna, jolloin raportti avautuu suodattamattomassa tilassa.  Tämä tarkoittaa, että raporttinäkymäruudussa näytettävät tiedot eivät vastaa raportin visualisoinnissa näkyviä tietoja.

Tästä on hyötyä, kun haluat nähdä eri tuloksia: raporttinäkymässä suodatettuna ja raportissa suodattamattomana.

> [!NOTE]
> Kiinnitetyt [reaaliaikaisen raporttisivun](service-dashboard-pin-live-tile-from-report.md) ruudut eivät vielä tue URL-suodattimia. 

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
On muutamia asioita, jotka tulee ottaa huomioon merkkijonon kyselyparametreja käytettäessä.

* Käytettäessä *in*-operaattoria *in*-operaattorin oikealla puolella olevat arvot on esitettävä sulkeissa olevana pilkuin eroteltuna luettelona.    
* Power BI -raporttipalvelimessa voit [välittää raporttiparametrit](https://docs.microsoft.com/sql/reporting-services/pass-a-report-parameter-within-a-url?view=sql-server-2017.md) sisällyttämällä ne raportin URL-osoitteeseen. Näissä URL-parametreissa ei ole etuliitettä, koska ne on välitetty suoraan raportin käsittelymoduuliin.    
* Kyselyn merkkijonon suodatus ei toimi toiminnoissa [Julkaise verkkoon](service-publish-to-web.md) tai Power BI Embedded.   
* Pitkä tietotyyppi on (2^53-1) JavaScriptin rajoitusten vuoksi.
* Kiinnitetyt *reaaliaikaisen raporttisivun* ruudut eivät vielä tue URL-suodattimia. 
 
## <a name="next-steps"></a>Seuraavat vaiheet
[Visualisoinnin kiinnittäminen koontinäyttöön](service-dashboard-pin-tile-from-report.md)  
[Rekisteröi ilmainen kokeiluversio](https://powerbi.microsoft.com/get-started/)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

