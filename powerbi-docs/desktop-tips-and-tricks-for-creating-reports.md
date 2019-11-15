---
title: Vinkkejä raporttien luomiseen Power BI:ssä
description: Lue parhaista käytännöistä raporttien luomiseksi Power BI -palvelussa ja Power BI Desktopissa
author: davidiseminger
ms.reviewer: willthom
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
ms.openlocfilehash: a6d949f95f463cb988958551d825a4eae824fb70
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73865832"
---
# <a name="tips-and-tricks-for-creating-reports-in-power-bi-desktop"></a>Vinkkejä raporttien luomiseen Power BI Desktopissa
Joskus voi tarvita hieman ylimääräistä apua, jotta tiedoista saa kaiken hyödyn irti. Olemme koonneet yhteen muutamia vinkkejä, joita voit hyödyntää, kun luot raportteja Microsoftin Power BI Desktopissa *ja* Microsoft Excel 2016:ssa. Niistä on hyötyä myös Excel 2013 Pro Plus -versioissa, joissa Power Pivot -apuohjelma on otettu käyttöön sekä Power Query asennettuna ja käytössä. 

## <a name="learning-to-use-the-query-editor"></a>Kyselyeditorin käyttäminen
Power BI Desktopin kyselyeditori muistuttaa toiminnoiltaan Excel 2013:n Power Query -apuohjelmaa. Power BI -tuessa on tarjolla useita hyödyllisiä artikkeleita, minkä lisäksi kannattaa tutustua Power Queryn dokumentaatioon osoitteessa support.office.com.

Saat lisätietoja myös [Power Query Resource Centeristä](https://support.office.com/article/Microsoft-Power-Query-for-Excel-Help-2b433a85-ddfb-420b-9cda-fe0e60b82a94).

Tutustu myös ohjeaiheeseen [Lisätietoja kaavasta](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

## <a name="data-types-in-query-editor"></a>Kyselyeditorin tietotyypit
Kun käytät Power BI Desktopin kyselyeditoria tietojen lataamiseen, tietojen tyyppi pyritään tunnistamaan mahdollisimman tarkasti. Jos käytössä on kaavoja, sarakkeiden tietotyyppiasetuksia ei välttämättä kuitenkaan säilytetä. Varmista, että sarakkeiden tietotyyppi on oikein, kun olet ensin tehnyt seuraavat toiminnot:  lataa tiedot alustavasti Kysely-välilehdelle, aseta ensimmäinen rivi otsikoksi, lisää sarake, ryhmitä perusteen mukaan, yhdistä ja liitä. Tarkista tietotyyppi myös ennen tietojen lataamista ensimmäistä kertaa.

Muista myös, että tietoruudukossa näkyvä kursivointi ei tarkoita, että tietotyyppi olisi asetettu oikein. Se tarkoittaa vain, että tietoja ei pidetä tekstinä.

## <a name="reference-queries-in-the-query-editor"></a>Viittaukset kyselyihin kyselyeditorissa
Kun napsautat Power BI Desktopin kyselyeditorin siirtymistoiminnossa jotakin kyselyä hiiren kakkospainikkeella, näet Viittaus-vaihtoehdon. Se on hyödyllinen seuraavasta syystä:

* Kun käytät tiedostoja kyselyn tietolähteenä, absoluuttinen polku tiedostoon tallennetaan kyselyyn. Kun jaat tai siirrät Power BI Desktop -tiedostoa tai Excel-laskentataulukkoa, säästät aikaa, kun voit päivittää viittaukset kerralla sen sijaan, että päivittäisit yksittäiset polut.

Oletusarvoisesti kaikki kyselyt lataavat joko Excel-laskentataulukkoon tai tietomalliin (tai molempiin). Tietyt kyselyt ovat välivaiheita, eikä niitä ole tarkoitettu loppukäyttäjille. Tästä on usein kyse, kun kyselyihin viitataan edellä mainitulla tavalla. Voit hallita kyselyn lataamistapaa napsauttamalla kyselyä hiiren kakkospainikkeella siirtymistoiminnossa ja muuttamalla Ota lataaminen käyttöön -asetusta. Kun *Ota lataaminen käyttöön* -asetuksen vieressä ei ole valintamerkkiä, kysely on yhä käytettävissä Kysely-välilehdessä ja voit käyttää sitä muihin kyselyihin. Tämä on erityisen hyödyllinen yhdessä Yhdistä-, Liitä- ja Viittaus-muunnosten kanssa. Koska kyselytuloksia ei kuitenkaan ole ladattu tietomalliin, kysely ei tarpeettomasti täytä raportin kenttäluetteloa tai tietomallia. 

## <a name="scatter-charts-need-a-point-identifier"></a>Pistekaavio edellyttää pistetunnusta
Otetaan esimerkiksi yksinkertainen taulukko, joka sisältää lämpötiloja ja niiden mittausaikoja. Jos tiedot piirretään suoraan pistekaavioon, Power BI koostaa kaikki arvot yhdeksi pisteeksi. Jotta voit näyttää yksittäiset arvopisteet, sinun täytyy lisätä kenttä kentän Tiedot-jakaumaan. Yksinkertainen tapa tehdä tämä Power BI Desktopissa on käyttää Kysely-välilehden Lisää sarake -valintanauhan Lisää indeksisarake -vaihtoehtoa. 

## <a name="reference-lines-in-your-report"></a>Viittausrivit raportissa
Voit määrittää viittausrivin käyttämällä laskettua saraketta Power BI Desktopissa. Määritä taulukko ja sarake, johon haluat luoda viittausrivin. Valitse valintanauhasta Uusi sarake ja kirjoita kaavariville seuraava kaava:

    Target Value = 100

Tämä laskettu sarake palauttaa arvon 100 riippumatta siitä, missä sitä käytetään. Uusi sarake näkyy kenttäluettelossa. Lisää laskettu Tavoitearvo-sarake viivakaavioon, niin näet, kuinka monta sarjaa liittyy tähän tiettyyn viittausriviin. 

## <a name="sort-by-another-column"></a>Lajittelu toisen sarakkeen mukaan
Kun käytät luokittaista arvoa (merkkijonoa) Power BI:ssä kaavion akseleina tai osittajassa tai suodattimessa, oletusjärjestyksenä on aakkosjärjestys. Jos haluat ohittaa tämän järjestyksen, kun kyseessä ovat esimerkiksi viikonpäivät tai kuukaudet, voit määrittää Power BI Desktopin lajittelemaan eri sarakkeen mukaan. Lisätietoja on artikkelissa [Sarakkeen perusteella lajittelu Power BI Desktopissa](desktop-sort-by-column.md).

## <a name="building-maps-more-easily-with-hints-to-bing"></a>Karttojen luominen vaivattomasti Bing-vihjeiden avulla
Power BI integroituu Bingin kanssa, jotta voit luoda karttoja helposti oletusarvoisten karttakoordinaattien eli sijaintitietojen avulla. Bing yrittää selvittää sijainnin tiettyjen algoritmien ja vihjetietojen perusteella, mutta se on parhaimmillaankin pelkkä arvaus. Voit parantaa oikeiden sijaintitietojen lisäämisen todennäköisyyttä seuraavasti:

Kun olet luomassa karttaa, siihen on usein tarpeen mallintaa maat ja kaupungit sekä maasta riippuen mahdollisesti osavaltiot tai vastaavat alueet. Jos nimeät Power BI Desktopissa sarakkeet maantieteellisten sijaintien mukaan, autat Bingiä arvaamaan, mitä aluetta haluat esittää. Jos sinulla on esimerkiksi kenttä, joka sisältää Yhdysvaltain osavaltioiden nimiä, kuten Kalifornia tai Washington, Bing saattaa palauttaa Washington-sanan sijainniksi pääkaupunki Washingtonin (DC) Washingtonin osavaltion sijaan. Kun annat sarakkeelle nimen Osavaltio, parannat sijaintitietojen lisäämisen tuloksia. Sama pätee sarakkeisiin Maa ja Kaupunki. 

Tietyt kohteet ovat moniselitteisiä, jos niitä ilmenee useiden maiden tai alueiden kontekstissa. Tietyssä maassa tai alueella ”osavaltio” voi olla ”provinssi” tai ”maakunta” tai jokin muu vastaava määrite. Sijaintitietojen lisäämisen tarkkuutta voi parantaa luomalla sarakkeita, jotka liittävät useita kenttiä yhteen ja käyttävät niitä tietojen sijaintien esittämiseen. Ei esimerkiksi kannata käyttää tietoa ”Wiltshire”, koska ”Wiltshire, Englanti” tuottaa paremman sijaintituloksen. 

Voit toki aina antaa tarkat leveys- ja pituusastesijainnit Power BI -palvelussa tai Power BI Desktopissa. Kun teet näin, mukana täytyy olla myös Sijainti-kenttä. Muuten nämä tiedot koostetaan oletusarvoisesti, jolloin leveys- ja pituusasteet eivät toimi odotetusti.

## <a name="categorizing-geographic-fields-to-hint-bings-geocoding"></a>Maantieteellisten kenttien luokittelu Bingin sijaintitietojen lisäämisen avuksi
Toinen tapa varmistaa kenttien sijaintitietojen lisääminen oikein on määrittää tietokentille tietoluokka. Valitse haluamasi taulukko Power BI Desktopissa, valitse Lisäasetukset-valintanauha ja aseta tietoluokaksi Osoite, Kaupunki, Maanosa, Maa/alue, Maa, Postinumero, Osavaltio tai Provinssi. Nämä tietoluokkien avulla Bing voi lisätä sijaintiedot oikein. Lisätietoja on artikkelissa [Tietojen luokittelu Power BI Desktopissa](desktop-data-categorization.md).

## <a name="better-geocoding-with-more-specific-locations"></a>Entistä parempi sijaintitietojen lisääminen tarkempien sijaintien avulla
Toisinaan edes tietoluokkien asettaminen ei riitä tietojen maantieteellistä yhdistämistä varten. Muodosta entistä tarkempi sijaintitieto, kuten katuosoite, käyttämällä Power BI Desktopin kyselyeditoria. Luo mukautettu sarake Lisää sarake -toiminnolla. Muodosta sitten haluttu sijainti seuraavasti: 

    = [Field1] & " " & [Field2]

Käytä tuloksena saatavaa kenttää karttavisualisoinneissa. Tämä on erittäin kätevä tapa luoda katuosoitteita toimitusosoitekentistä, joita esiintyy tietojoukoissa usein. Kannattaa huomata, että ketjutus toimii vain tekstikenttien kanssa. Voit tarvittaessa muuntaa kadunnumeron tietotyypin tekstiksi, ennen kuin käytät sitä osoitteen koostamiseen.

## <a name="histograms-in-the-query-stage"></a>Histogrammit kyselyvaiheessa
Histogrammeja voi luoda Power BI Desktopissa useilla tavoilla. Aloitetaan ensin yksinkertaisimmasta:

Yksinkertaisimmat histogrammit – Määritä, mikä kysely sisältää histogrammin pohjaksi tarvittavan kentän. Luo uusi kysely kyselyn Viittaus-asetuksen avulla ja anna sille nimeksi ”FieldName histogrammi”. Käytä Muunna-valintanauhan Ryhmittelyperuste-vaihtoehtoa ja valitse Laske rivit -kooste. Varmista, että koostesarakkeen tietotyyppi on numero. Visualisoi nämä tiedot raporttisivulla. Tämä on nopea ja helppo tapa mutta ei toimi hyvin, jos arvopisteitä on useita, eikä sivellintoiminnon käyttöä sallita kaikissa visualisoinneissa.

Jakaumien määrittäminen histogrammin luomiseksi – Määritä, mikä kysely sisältää histogrammin pohjaksi tarvittavan kentän. Luo uusi kysely kyselyn Viittaus-asetuksen avulla ja anna sille nimeksi FieldName. Määritä nyt jakaumat ja niiden säännöt. Käytä Lisää sarake -valintanauhan Lisää mukautettu sarake -vaihtoehtoa mukautetun säännön luomiseen. Yksinkertainen jakaumanluontisääntö näyttää esimerkiksi tältä:

    if([FieldName] \< 2) then "\<2 min" else
    if([FieldName] \< 5) then "\<5 min" else
    if([FieldName] \< 10) then "\<10 min" else
    if([FieldName] \< 30) then "\<30 min" else
    "longer")

Varmista, että koostesarakkeen tietotyyppi on numero. Nyt voit käyttää yksinkertaisimman histogrammin yhteydessä kuvattua Ryhmittelyperuste-vaihtoehtoa histogrammin muodostamiseen. Tällä asetuksella käsitellään enemmän arvopisteitä, mutta se ei silti tue sivellintoiminnon käyttöä.

Sivellintä tukevan histogrammin määrittäminen – Sivellintoiminnolla tarkoitetaan linkitetyissä visualisoinneissa sitä, että kun käyttäjä valitsee yhden tietopisteen yhdessä visualisoinnissa, raporttisivun muissa visualisoinneissa korostetaan tai suodatetaan valittuun tietopisteeseen liittyvät tietopisteet. Koska käsittelemme tietoa kyselyhetkellä, meidän on luotava yhteys taulukoiden välille ja varmistettava, mikä tietokohde liittyy jakaumaan histogrammissa ja päinvastoin.

Aloita prosessi valitsemalla Viittaus-asetus siinä kyselyssä, jonka pohjalta haluat luoda histogrammin. Anna uudelle kyselylle nimeksi Jakaumat. Tässä esimerkissä annetaan alkuperäiselle kyselylle nimeksi Tiedot. Poista seuraavaksi kaikki sarakkeet lukuun ottamatta sitä, jota käytetään histogrammin jakaumana. Käytä sitten kyselyn Poista kaksoiskappaleet -toimintoa, jolloin sarakkeeseen jää jäljelle vain ainutkertaisia arvoja. Löydät toiminnon napsauttamalla saraketta hiiren kakkospainikkeella. Jos tiedoissa on desimaalilukuja, voit ensin käyttää jakaumien määrittämisen vinkkiä, jonka avulla voit luoda histogrammin helposti hallittavasta jakaumajoukosta. Tarkista nyt kyselyn esikatselussa näkyvät tiedot. Jos näet tyhjiä arvoja tai null-arvoja, ne on korjattava ennen suhteiden muodostamista. Lisätietoja on artikkelissa Suhteen luominen tyhjiä tai null-arvoja sisältävillä tiedoilla. Tämä lähestymistapa voi olla ongelmallinen lajittelutarpeen vuoksi. Jakaumien lajittelemisesta oikein on lisätietoja artikkelissa Lajittelujärjestys: luokkien näkyminen halutussa järjestyksessä. 

>[!NOTE]
>Lajittelujärjestystä kannattaa miettiä ennen visualisointien luomista. 

Prosessin seuraava vaihe on määritellä suhde Jakaumat- ja Tiedot-kyselyjen välille jakaumasarakkeessa. Valitse Power BI Desktopin valintanauhasta **Suhteiden hallinta**. Luo suhde, jossa Jakaumat-kysely on vasemmassa taulukossa ja Tiedot-kysely oikeassa taulukossa ja valitse kenttä, jota käytät histogrammiin. 

Viimeinen vaihe on histogrammin luominen. Vedä jakaumakenttä Jakaumat-taulukosta. Poista oletuskenttä tuloksena saatavasta pylväskaaviosta. Vedä histogrammikenttä samaan visualisointiin Tiedot-taulukosta. Muuta kenttäsäilössä oletuskoosteeksi Määrä. Tuloksena saat histogrammin. Jos luot Tiedot-taulukosta toisen visualisoinnin, kuten puukartan, valitse puukartasta arvopiste, niin histogrammi korostuu. Näet valitun arvopisteen histogrammin suhteessa koko tietojoukon trendiin.

## <a name="histograms"></a>Histogrammit
Power BI Desktopissa voit määrittää histogrammin lasketun kentän avulla. Määritä taulukko ja sarake, joista haluat luoda histogrammin. Kirjoita laskenta-alueelle seuraava kaava:

> Frequency:=COUNTROWS(\<sarakkeen nimi\>)
> 
> 

Tallenna muutokset ja palaa raporttiin. Lisää \<Sarakkeen nimi\>- ja Taajuus-kentät taulukkoon ja muunna se palkkikaavioksi. Varmista, että \<Sarakkeen nimi\> -kenttä on X-akselilla ja laskettu Taajuus-kenttä on Y-akselilla.

## <a name="tips-and-tricks-for-creating-relationships-in-power-bi-desktop"></a>Vinkkejä suhteiden muodostamiseen Power BI Desktopissa
Kun ladataan tietojoukkoja useista lähteistä, null-arvot, tyhjät arvot tai arvojen kaksoiskappaleet estävät usein suhteiden muodostamisen. 

Tarkastellaan esimerkkiä: 

Tietojoukkoja ladataan aktiivisista asiakastukipyynnöistä ja työkohteiden tietojoukosta, jossa on seuraavanlaiset skeemat:

> CustomerIncident-skeemat: {IncidentID, CustomerName, IssueName, OpenedDate, Status}; WorkItem-skeemat: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName } 
> 
> 

Kun haluamme seurata kaikkia tapahtumia ja työkohteita, jotka liittyvät tiettyyn CustomerName-kohteeseen, emme voi noin vain muodostaa suhdetta näiden tietojoukkojen välille. Tietyt WorkItem-tiedot eivät ehkä liity CustomerName-tietoon, joten tällainen kenttä olisi tyhjä tai arvoltaan null. WorkItem- ja CustomerIncident-skeemoihin voi sisältyä useita tietueita mille tahansa CustomerName-kohteelle. 

### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-null-or-blank-values"></a>Suhteiden muodostaminen Power BI Desktopissa, kun tiedoissa on tyhjiä tai null-arvoja
Tietojoukoissa on usein sarakkeita, jotka sisältävät tyhjiä tai null-arvoja. Se voi aiheuttaa ongelmia suhteiden käyttämisessä. Ongelman voi korjata periaatteessa kahdella tavalla. Voit poistaa rivit, jotka sisältävät tyhjiä tai null-arvoja. Sen voi tehdä joko Kysely-välilehden suodatustoiminnolla tai valitsemalla Säilytä vain vastaavat rivit -asetuksen, jos kyselyjä ollaan yhdistämässä. Vaihtoehtoisesti voit korvata null-arvoiset tai tyhjät arvot arvoilla, jotka toimivat suhteissa. Yleensä käytetään esimerkiksi merkkijonoja ”NULL” ja ”(Tyhjä)”. Mitään yhtä ja ainoaa oikeaa tapaa ei ole. Rivien suodattaminen pois kyselyvaiheessa poistaa rivejä ja voi vaikuttaa yhteenvetotilastoihin ja laskutoimituksiin. Jälkimmäisessä lähestymistavassa säilytetään kyseiset tietorivit, mutta se voi aiheuttaa liittymättömien rivien näkymisen liittyvinä mallissa, mikä aiheuttaa vääriä tuloksia laskutoimituksissa. Jos valitset jälkimmäisen ratkaisun, varmista, että käytät suodattimia näkymässä/kaaviossa aina tarpeen mukaan, jotta saat tarkkoja tuloksia. Mikä tärkeintä, arvioi tarkkaan, mitkä rivit säilytetään tai poistetaan, niin ymmärrät sen yleisen vaikutuksen analyysiin. 

### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-duplicate-values"></a>Suhteiden muodostaminen Power BI Desktopissa, kun tiedoissa on arvojen kaksoiskappaleita
Kun ladataan yksityiskohtaisia tietojoukkoja useista lähteistä, tiedoissa olevat arvojen kaksoiskappaleet estävät luomasta yhteyksiä. Voit ratkaista ongelman luomalla dimensiotaulukon, joka sisältää ainutkertaiset arvot kummastakin tietojoukosta. 

Tarkastellaan esimerkkiä: 

Tietojoukkoja ladataan aktiivisista asiakastukipyynnöistä ja työkohteiden tietojoukosta, jossa on seuraavanlaiset skeemat:

> CustomerIncident-skeemat: {IncidentID, CustomerName, IssueName, OpenedDate, Status}; WorkItem-skeemat: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName } 
> 
> 

Kun haluamme seurata kaikkia tapahtumia ja työkohteita, jotka liittyvät tiettyyn CustomerName-kohteeseen, emme voi noin vain muodostaa suhdetta näiden tietojoukkojen välille. Tietyt WorkItem-tiedot eivät ehkä liity CustomerName-tietoon, joten tällainen kenttä olisi tyhjä tai arvoltaan null. Jos sinulla on tyhjiä tai null-arvoja CustomerNames-taulukossa, et välttämättä vieläkään voi muodostaa yhteyttä. Lisätietoja on artikkelissa Suhteiden muodostaminen Power BI Desktopissa, kun tiedoissa on tyhjiä tai null-arvoja. Yhdelle CustomerName-kohteelle voi olla useita WorkItem- ja CustomerIncident-arvoja. 

Jotta voit muodostaa suhteen tässä tapauksessa, sinun on luotava looginen tietojoukko kaikista CustomerName-arvoista näissä kahdessa tietojoukossa. Luo looginen tietojoukko Kysely-välilehdellä seuraavasti:

1. Luo kaksoiskappale kummastakin kyselystä. Anna ensimmäiselle nimi **Temp** ja toiselle **CustomerNames**.
2. Poistaa jokaisesta kyselystä kaikki sarakkeet *lukuun ottamatta* CustomerName-saraketta.
3. Valitse jokaisessa kyselyssä **Poista kaksoiskappaleet**.
4. Valitse **CustomerNames** -kyselyssä valintanauhasta **Liitä**-vaihtoehto. Valitse sitten **Temp**-kysely.
5. Valitse **CustomerNames**-kyselyssä **Poista kaksoiskappaleet**.

Nyt sinulla on dimensiotaulukko, jota voit käyttää viittaamaan CustomerIndicents- ja WorkItems-kohteisiin, jotka sisältävät kummankin kaikki arvot. 

## <a name="patterns-to-jump-start-your-use-of-the-query-editor"></a>Kyselyeditorin käytön aloittaminen mallien avulla
Kyselyeditori on hyvin tehokas työkalu tietojen muokkaamiseen ja puhdistamiseen visualisointia ja mallintamista varten. Käyttäjän on kuitenkin hyvä tietää editorin muutamista toimintamalleista.

### <a name="temporary-columns-can-be-deleted-after-computing-a-result"></a>Tilapäisiä sarakkeita voidaan poistaa tuloksen laskemisen jälkeen.
Power BI Desktopissa on usein luotava laskutoimitus, joka muuntaa tietoja useista sarakkeista yksittäiseen uuteen sarakkeeseen. Tämä voi olla monimutkaista. Yksi helppo tapa ratkaista ongelma on purkaa prosessi vaiheisiinsa. Aloita kopioimalla alkuperäiset sarakkeet. Luo sitten tilapäiset sarakkeet ohjeiden mukaan. Luo seuraavaksi sarake lopullista tulosta varten. Voit sitten poistaa väliaikaiset sarakkeet, niin ne eivät häiritse lopullista tietojoukkoa. Tämä on mahdollista, koska Kysely-välilehti suorittaa vaiheet järjestyksessä. 

### <a name="duplicate-or-reference-queries-followed-by-merge-to-original-query"></a>Kaksoiskappale- tai viittauskyselyt ja niitä seuraava yhdistäminen alkuperäiseen kyselyyn
Toisinaan on hyödyllistä laskea tietojoukolle yhteenvetotilastot. Helppo tapa siihen on luoda kyselystä kaksoiskappale tai viitata siihen Kysely-välilehdellä. Käytä sitten **Ryhmittelyperuste**-toimintoa yhteenvetotilastojen laskemiseen. Yhteenvetotilastot auttavat normalisoimaan alkuperäistietojen tiedot, jotta niistä saadaan vertailukelpoisempia. Tämä on erityisen hyödyllinen verrattaessa yksittäisiä arvoja kokonaisuuteen. Voit tehdä tämän siirtymällä alkuperäiseen kyselyyn ja valitsemalla Yhdistä-vaihtoehdon. Yhdistä sitten asianmukaisia tunnisteita vastaavat tiedot yhteenvetotilaston kyselystä. Nyt olet valmis tietojen normalisointiin analyysin tarpeiden mukaisesti.

## <a name="using-dax-for-the-first-time"></a>DAX:n käyttäminen ensimmäistä kertaa
DAX on Power BI Desktopissa käytettävä laskutoimitusten kaavakieli. Se on optimoitu liiketoimintatietojen analytiikkaa varten. Se poikkeaa jonkun verran totutusta, jos olet käyttänyt vain SQL-tyyppistä kyselykieltä. DAX:n opetteluun on paljon hyvää materiaalia verkossa ja painetussa muodossa. 

[Opettele DAX-perusteet Power BI Desktopissa](desktop-quickstart-learn-dax-basics.md)

[Data Analysis Expressions (DAX) -viittaukset](https://msdn.microsoft.com/library/gg413422.aspx)

[DAX Resource Center](https://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx)
