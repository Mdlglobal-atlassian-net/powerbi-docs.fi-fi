---
title: Tallennustilan tilan käyttäminen Power BI Desktopissa (esikatselu)
description: Tallennustilan tilan avulla voit hallita, tallennetaanko tietoja välimuistiin Power BI Desktop -raportteja varten
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/23/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 15580cd43e4bb2d286310868a8e853daff04f280
ms.sourcegitcommit: 6faeb642721ee5abb41c04a8b729880c01c4d40e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2018
ms.locfileid: "39210905"
---
# <a name="storage-mode-in-power-bi-desktop-preview"></a>Tallennustilamoodi Power BI Desktopissa (esikatselu)

**Power BI Desktopissa** voit määrittää taulukoiden **tallennustilan tilan**. Siten voit hallita, tallennetaanko tietoja välimuistiin raportteja varten. 

![Tallennustilan tila Power BI Desktopissa](media/desktop-storage-mode/storage-mode_01.png)

**Tallennustilan tilan** määrittäminen tarjoaa monia etuja. Voit määrittää **tallennustilan tilan** mallissasi yksitellen kullekin taulukolle. Siten otat käyttöön yksittäisen tietojoukon, jonka ansiosta voit hyödyntää seuraavia etuja:

* **Kyselyn suorituskyky** – kun käyttäjät vuorovaikuttavat Power BI -raporttien visualisointien kanssa, DAX-kyselyt lähetetään tietojoukkoon. Kun tiedot tallennetaan välimuistiin **tallennustilan tilan** asianmukaisella määrittämisellä, voit tehostaa kyselyn suorituskykyä ja parantaa raporttien vuorovaikutteisuutta.
* **Suuret tietojoukot** – sellaiset taulukot, joita ei tallenneta välimuistiin, eivät kuluta välimuistille varattua muistia. Voit ottaa käyttöön vuorovaikutteisen analyysin suurille tietojoukoille, jotka ovat liian suuria tai kalliita tallennettavaksi kokonaan välimuistiin. Voit valita, mitkä taulukot ovat välimuistiin tallentamisen arvoisia.
* **Tietojen päivittämisen optimointi** – taulukoita, joita ei tallenneta välimuistiin, ei tarvitse päivittää. Voit lyhentää päivitysaikoja tallentamalla välimuistiin vain sellaiset tiedot, joita tarvitset palvelutasosopimuksen noudattamiseksi ja oman yrityksesi tarpeisiin.
* **Lähes reaaliaikaiset aikavaatimusten** – taulukot, joissa on lähes reaaliaikaisia vaatimuksia, saattavat hyötyä siitä, että niitä ei tallenneta välimuistiin. Se vähentää tietojen viivettä.
* **Takaisinkirjoitus** – takaisinkirjoituksen avulla yrityskäyttäjät voivat kokeilla entä jos -skenaarioita muuttamalla solujen arvoja. Mukautetut sovellukset voivat ottaa muutoksia käyttöön tietolähteessä. Taulukoissa, joita ei ole tallennettu välimuistiin, muutokset eivät näy välittömästi, mikä mahdollistaa vaikutusten nopean analyysin.

**Power BI Desktopin** **Tallennustila tila** -asetus on yksi kolmesta toisiinsa liittyvästä ominaisuudesta:

* **Yhdistelmämallit** – antavat mahdollisuuden sisällyttää raporttiin useita tietoyhteyksiä, kuten DirectQuery-yhteydet tai tuonnin, minä tahansa yhdistelminä.
* **Monta moneen -yhteydet** – yhdessä **yhdistelmämallien** kanssa voit muodostaa **monta moneen -yhteyksiä** taulukoiden välille ilman tarvetta yksilöllisille arvoille taulukoissa. Tämä poistaa tarpeen aiemmille kiertotavoille, kuten uusien taulukoiden lisäämiselle vain yhteyksien muodostamisen takia. 
* **Tallennustilan tila** – voit nyt määrittää, mitkä visualisoinnit edellyttävät kyselyä taustatietolähteisiin. Ne visualisoinnit, jotka eivät sitä tarvitse, tuodaan DirectQuery-kyselyyn pohjautumisesta huolimatta. Se parantaa suorituskykyä ja vähentää taustajärjestelmien kuormitusta. Aiemmin jopa osittajien kaltaiset yksinkertaiset visualisoinnit käynnistivät kyselyjä taustalähteisiin. 

Nämä kolme toisiinsa liittyvää **yhdistelmämallien** ominaisuutta on kukin kuvattu omissa artikkeleissaan:

* **Yhdistelmämallit** on kuvattu yksityiskohtaisesti [Yhdistelmämallit Power BI Desktopissa (esikatselu)](desktop-composite-models.md) -artikkelissa.
* **Monta moneen -yhteydet** on kuvattu [Monta moneen -yhteydet Power BI Desktopissa (esikatselu)](desktop-many-to-many-relationships.md) -artikkelissa.
* **Tallennustilan tila** kuvataan tässä artikkelissa.

## <a name="enabling-the-storage-mode-preview-feature"></a>Tallennustilan tila -esikatselutoiminnon käyttöönotto

**Tallennustilan tila** -ominaisuus on esikatseluvaiheessa. Sen täytyy olla käytössä **Power BI Desktopissa**. Ota **tallennustilan tila** käyttöön valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Asetukset > Esikatseluominaisuudet**. Valitse sitten **Yhdistelmämallit**-valintaruutu. 

![Esikatselutoimintojen ottaminen käyttöön](media/desktop-composite-models/composite-models_02.png)

Ominaisuuden käyttöönotto edellyttää **Power BI Desktopin** käynnistämistä uudelleen.

![Uudelleenkäynnistys vaaditaan, jotta muutokset tulevat voimaan](media/desktop-composite-models/composite-models_03.png)


## <a name="using-the-storage-mode-property"></a>Tallennustilan tila -ominaisuuden käyttäminen

**Tallennustilan tila** on ominaisuus, jonka voit määrittää mallisi kullekin taulukolle. Voit määrittää **tallennustilan tilan** valitsemalla taulukon **Kentät**-ruudusta ja avaamalla pikavalikon hiiren kakkospainikkeella. Valitse pikavalikosta **Ominaisuudet**.

![Valitse Ominaisuudet pikavalikosta](media/desktop-storage-mode/storage-mode_02.png)

**Tallennustilan tila** -valinta näkyy taulukon **Kentän ominaisuudet** -ruudussa. Siellä voit tarkastella nykyistä **tallennustilan tilaa** tai muokata sitä.

![Taulukon tallennustilan tilan määrittäminen](media/desktop-storage-mode/storage-mode_03.png)

**Tallennustilan tilalle** on kolme arvoa:

* **Tuonti** – kun arvona on **Tuonti**, tuodut taulukot tallennetaan välimuistiin. Power BI -tietojoukkoon lähetetyt kyselyt, jotka palauttavat tietoja tuoduista taulukoista, ovat täytettävissä vain välimuistiin tallennetuista tiedoista.
* **DirectQuery** – kun tämä asetus on käytössä, DirectQuery-taulukoita ei tallenneta välimuistiin. Power BI -tietojoukkoon lähetetyt kyselyt, kuten DAX-kyselyt, jotka palauttavat tietoja DirectQuery-taulukoista, ovat täytettävissä vain suorittamalla pyydettäessä saatavia kyselyjä tietolähteeseen. Tietolähteeseen lähetetyt kyselyt käyttävät kyseisen tietolähteen kyselykieltä, kuten SQL:ää.
* **Kaksoistaulukot** – kaksoistaulukot voivat toimia joko välimuistiin tallennettuina tai siihen tallentamattomina riippuen Power BI -tietojoukkoon lähetetyn kyselyn kontekstista. Joissakin tapauksissa kyselyt täytetään välimuistiin tallennetuista tiedoista. Muissa tapauksissa kyselyt täytetään suorittamalla pyydettäessä saatava kysely tietolähteeseen.

Taulukon muuttaminen tuontitilaan on *peruuttamaton* toiminto. Taulukkoa ei voi muuttaa takaisin DirectQuery- tai kaksoistaulukoksi.

## <a name="constraints-on-directquery-and-dual-tables"></a>DirectQuery- ja kaksoistaulukoiden rajoitukset

Kaksoistaulukkoja koskevat samat rajoitukset kuin DirectQuery-taulukkoja. Niitä ovat esimerkiksi rajoitetut M-muunnokset ja laskettujen sarakkeiden rajoitetut DAX-funktiot. Lisätietoja on ohjeaiheessa [DirectQueryn käyttämisen vaikutukset](desktop-directquery-about.md#implications-of-using-directquery).

## <a name="relationship-rules-on-tables-with-different-storage-modes"></a>Yhteyssäännöt eri tallennustyypin tiloilla varustetuille taulukoille

Yhteyksien on noudatettava sääntöjä, jotka perustuvat liittyvien taulukoiden **tallennustilan tilaan**. Tässä osiossa on esimerkkejä sallituista yhdistelmistä. Täydelliset tiedot ovat ohjeaiheessa [Monta moneen -yhteydet Power BI Desktopissa (esikatselu)](desktop-many-to-many-relationships.md).

Yhden tietolähteen tietojoukoissa seuraavat **yksi moneen** -yhteydet ovat sallittuja:

| **Monta**-puolen taulukko | **Yksi**-puolen taulukko |
| ------------- |----------------------| 
| Kaksoistaulukko          | Kaksoistaulukko                 | 
| Tuo        | Tuonti- tai kaksoistaulukko       | 
| DirectQuery   | DirectQuery- tai kaksoistaulukko  | 

## <a name="propagation-of-dual"></a>Välitys- tai kaksoistaulukko
Tarkastellaan esimerkkiä. Tutustu seuraavaan yksinkertaiseen malliin, jossa kaikki taulukot ovat yhdestä tuontia ja DirectQuerya tukevasta lähteestä.

![Esimerkki tallennustilan tilan yhteysnäkymästä](media/desktop-storage-mode/storage-mode_04.png)

Oletetaan, että kaikki taulukot tässä mallissa ovat DirectQuery-taulukoita. Jos vaihdamme *Kyselyvastaus*-taulukon **tallennustilan tilaksi** Tuonti, näyttöön tulee seuraava kehote:

![Tallennustilan tilan varoitusikkuna](media/desktop-storage-mode/storage-mode_05.png)

Dimensiotaulukot (*Asiakas*, *Päivämäärä* ja *Maantiede*) on määritettävä **kaksoistaulukoiksi**, jotta ne noudattavat aiemmin kuvattuja yhteyssääntöjä. Sen sijaan, että nämä taulukot olisi määritettävä **kaksoistaulukoiksi** etukäteen, ne voi määrittää yhdellä kertaa.

Välityslogiikka on suunniteltu auttamaan useita taulukoita sisältävien mallien käyttämisessä. Oletetaan, että sinulla on malli, joka sisältää 50 taulukkoa. Niistä vain tietyt (tapahtumatyyppiset) faktataulukot on tallennettava välimuistiin. **Power BI Desktopin** logiikkajärjestelmä selvittää dimensiotaulukoiden vähimmäisjoukon, joka on määritettävä **kaksoistaulukoiksi**, joten sinun ei tarvitse tehdä sitä itse.

Välityslogiikka ulottuu vain yhdelle puolelle **yhdestä moneen** -yhteyksissä.

* *Asiakas*-taulukon muuttamista **Tuonti**-taulukoksi (*Kyselyvastaus*-taulukon muuttamisen sijaan) ei ole sallittu, koska sillä on yhteys DirectQuery-tyyppisiin *Myynti*- ja *Kyselyvastaus*-taulukoihin.
* *Asiakas*-taulukon muuttaminen **kaksoistaulukoksi** (*Kyselyvastaus*-taulukon muuttamisen sijaan) on sallittu. Välityslogiikka määrittää *Maantiede*-taulukon niin ikään **kaksoistaulukoksi**.

## <a name="storage-mode-usage-example"></a>Tallennustilan tilan käyttöesimerkki
Jatketaan edellisen osion esimerkin parissa. Oletetaan, että otamme käyttöön seuraavat **tallennustilan tilan** ominaisuusasetukset:

| Taulukko                   | Tallennustilan tila         |
| ----------------------- |----------------------| 
| *Myynti*                 | DirectQuery          | 
| *Kyselyvastaus*        | Tuo               | 
| *Päivämäärä*                  | Kaksoistaulukko                 | 
| *Asiakas*              | Kaksoistaulukko                 | 
| *Maantiede*             | Kaksoistaulukko                 | 


Tallennustilan tilan ominaisuusasetusten määrittäminen tuottaa seuraavia tuloksia olettaen, että *Myynti*-taulukossa on paljon tietoja.
* Dimensiotaulukot (*Päivämäärä*, *Asiakas* ja *Maantiede*) on tallennettu välimuistiin, joten ensimmäisen raportin latausajan tulisi olla lyhyt, kun näytettäviä osittajan arvoja noudetaan.
* Jos *Myynti*-taulukkoa ei tallenneta välimuistiin, se johtaa seuraaviin tuloksiin:
    * Tietojen päivitysajat ovat entistä paremmat ja muistin käyttö vähenee.
    * *Myynti*-taulukkoon perustuvat raporttikyselyt suoritetaan DirectQuery-tilassa, mikä saattaa kestää kauemmin mutta on lähellä reaaliaikaisuutta, koska välimuistiin tallentamisen viivettä ei ole.

* *Kyselyvastaus*-taulukkoon perustuvat raporttikyselyt palautetaan välimuistista, minkä tulisi tapahtua melko nopeasti.

## <a name="queries-that-hit-or-miss-the-cache"></a>Kyselyt, jotka kohdistuvat tai ovat kohdistumatta välimuistiin

Kun **SQL Profiler** liitetään **Power BI Desktopin** diagnostiikkaporttiin, seuraaviin tapahtumiin perustuvan jäljityksen avulla voit nähdä, mitkä kyselyt kohdistuvat tai ovat kohdistumatta välimuistiin:

* Kyselytapahtumat \ kyselyn alku
* Kyselyn käsittely \ Vertipaq SE -kyselyn alku
* Kyselyn käsittely \ DirectQueryn alku

Tarkista kunkin *kyselyn alku* -tapahtuman osalta muut tapahtumat, joilla on sama *ActivityID*. Jos esimerkiksi *DirectQueryn alku* -tapahtumaa ei ole, mutta *Vertipaq SE -kyselyn alku* -tapahtuma on olemassa, kyselyyn vastattiin välimuistista.

Kyselyt, jotka viittaavat **kaksoistilassa** oleviin taulukoihin, palauttavat tiedot välimuistista, jos se on mahdollista. Muussa tapauksessa ne palautuvat DirectQueryyn.

Edellisessä esimerkissä seuraava kysely viittaa vain sarakkeeseen *Päivämäärä*-taulukossa, joka on **kaksoistilassa**. Tämän vuoksi sen tulisi kohdistua välimuistiin.

![Tallennustilan diagnostiikan komentosarja](media/desktop-storage-mode/storage-mode_06.png)

Seuraava kysely viittaa vain sarakkeeseen *Myynti*-taulukossa, joka on **DirectQuery**-tilassa. Tämän vuoksi sen *ei* tulisi kohdistua välimuistiin.

![Tallennustilan diagnostiikan komentosarja](media/desktop-storage-mode/storage-mode_07.png)

Seuraava kysely on mielenkiintoinen, koska se yhdistää molemmat sarakkeet. Tämä kysely ei kohdistu välimuistiin. Sen voisi olettaa noutavan *Kalenterivuosi*-arvoja välimuistista ja *Myyntisumma*-arvoja lähteestä sekä yhdistävän nämä tulokset. Se olisi kuitenkin vähemmän tehokasta kuin SUM/GROUP BY -toiminnon lähettäminen lähdejärjestelmään. Jos toiminto lähetetään lähteeseen, palautettavien rivien määrä on todennäköisesti paljon pienempi. 

![Tallennustilan diagnostiikan komentosarja](media/desktop-storage-mode/storage-mode_08.png)

> [!NOTE]
> Tämä toiminta poikkeaa [Power BI Desktopin monta moneen -yhteyksistä (esikatselu)](desktop-many-to-many-relationships.md), kun yhdistellään välimuistiin tallennettuja ja tallentamattomia taulukoita.

## <a name="caches-should-be-kept-in-sync"></a>Välimuistit tulisi pitää synkronoituna

Edellisessä osiossa näytyt kyselyt osoittavat, että **kaksoistaulukot** toisinaan kohdistuvat ja toisinaan eivät kohdistu välimuistiin. Tämän vuoksi saatetaan palauttaa erilaisia arvoja, jos välimuisti ei ole ajan tasalla. Kyselyn suorittaminen ei yritä peittää tieto-ongelmia esimerkiksi suodattamalla DirectQuery-tuloksia välimuistiin tallennettujen arvojen kanssa täsmäämiseksi. Sinun vastuullasi on tuntea tietovuot ja suunnitella toimet vastaavasti. On olemassa vakiintuneet tekniikoita tällaisten tapausten käsittelemiseen lähteessä.

Tallennustilan **kaksoistilassa** on kyse suorituskyvyn optimoinnista. Sitä tulisi käyttää vain tavoilla, jotka eivät vaikeuta liiketoiminnan tarpeiden toteuttamista. Vaihtoehtoisesti voit harkita artikkelissa [Monta moneen -yhteydet Power BI Desktopissa (esikatselu)](desktop-many-to-many-relationships.md) kuvattuja tekniikoita.

## <a name="data-view"></a>Tietonäkymä
Jos tietojoukon vähintään yhden taulukon **tallennustila** on määritetty joko tuonti- tai kaksoistilaan, näet **Tietonäkymä**-välilehden.

![Tietonäkymä Power BI Desktopissa](media/desktop-storage-mode/storage-mode_09.png)

*Tietonäkymässä** valitut **kaksois-** ja **tuontitaulukot** näyttävät välimuistiin tallennettuja tietoja. DirectQuery-taulukot eivät näytä tietoja, ja näet ilmoituksen, jonka mukaan DirectQuery-taulukoita ei voi näyttää.


## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

**Tallennustilan tilan** tässä versiossa ja sen korrelaatiossa **yhdistelmämalleihin** on joitakin rajoituksia.

Seuraavia monidimensioisia lähteitä ei voi käyttää **yhdistelmämallien** kanssa:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI -tietojoukot

Kun muodostetaan yhteyttä näihin monidimensioisiin lähteisiin DirectQuerylla, et voi muodostaa yhteyttä myös toiseen DirectQuery-lähteeseen tai yhdistää tuotuihin tietoihin.

DirectQueryn olemassa olevat käyttörajoitukset koskevat edelleen **yhdistelmämallien** käyttämistä. Monet näistä rajoituksista ovat nyt taulukkokohtaisia ja riippuvat taulukon **tallennustilan tilasta**. Esimerkiksi tuodun taulukon laskettu sarake voi viitata muihin taulukoihin, mutta DirectQuery-taulukon laskettu sarake on yhä rajoitettu viittaamaan vain saman taulukon sarakkeisiin. Muut rajoitukset koskevat vain mallia kokonaisuutena, jos jokin mallin taulukoista on DirectQuery-taulukko. Esimerkiksi **Nopeat merkitykselliset tiedot**- ja **Q & A** -ominaisuudet eivät ole käytettävissä mallissa, jos jollakin sen taulukoista **tallennustilan tilana** on DirectQuery. 

## <a name="next-steps"></a>Seuraavat vaiheet

Seuraavissa artikkeleissa kerrotaan lisää yhdistelmämalleista ja kuvataan myös DirectQuery yksityiskohtaisemmin.

* [Yhdistelmämallit Power BI Desktopissa (esikatselu)](desktop-composite-models.md)
* [Moni-moneen-yhteydet Power BI Desktopissa (esikatselu)](desktop-many-to-many-relationships.md)

DirectQuery-artikkeleita:

* [DirectQueryn käyttäminen Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet Power BI:ssä](desktop-directquery-data-sources.md)

