---
title: Suhteellisen päivämääräosittajan tai suodattimen käyttö Power BI:ssä
description: Opi miten osittajaa tai suodatinta käytetään rajoittamaan suhteellisia päivämääräjoukkoja Power BI:ssä.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/06/2020
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 9ce36bfa61b16bd30e59bc8491af80efdfdc8a35
ms.sourcegitcommit: 915cb7d8088deb0d9d86f3b15dfb4f6f5b1b869c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/10/2020
ms.locfileid: "81006780"
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi"></a>Suhteellisen päivämääräosittajan ja -suodattimen käyttö Power BI:ssä

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

**Suhteellisen päivämääräosittajan** tai **suhteellisen päivämääräsuodattimen** avulla voit käyttää aikasidonnaisia suodattimia missä tahansa tietomallisi päivämääräsarakkeessa. Voit esimerkiksi käyttää **suhteellisen päivämäärän osittajaa** näyttääksesi vain viimeisten 30 päivän (tai kuukauden tai kalenterikuukausien jne.) aikana tapahtuneen myynnin tiedot. Kun päivität tiedot, suhteellinen ajanjakso käyttää automaattisesti soveltuvaa suhteellisen päivämäärän rajoitusta.

![Näyttökuvassa on raportti, jossa näkyy suhteelliseen päivämäärän osittajaan osoittava nuoli.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-01.png)

## <a name="use-the-relative-date-range-slicer"></a>Suhteellisen päivämääräalueen osittajan käyttäminen

Voit käyttää suhteellisen päivämäärän osittajaa kuten mitä muuta tahansa osittajaa. Luo **osittaja** raportillesi ja valitse sitten päivämääräarvo **Kenttä**-arvoksi. Seuraavassa kuvassa valitsimme *OrderDate*-kentän.

![Näyttökuvassa on Visualisoinnit-ruutu, jossa näkyy osittajavisualisointikuvakkeeseen ja kenttään osoittavia nuolia.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-02.png)

Valitse osittaja pohjalta ja valitse sitten osittajavisualisoinnin oikeassa yläkulmassa oleva merkki. Jos visualisoinnissa on päivämäärätietoja, valikossa näkyy **Suhteellinen**-vaihtoehto.

![Näyttökuvassa on osittajavisualisointi, jossa on korostettuna oikean yläkulman merkki ja nuoli Suhteellinen-valikkokohtaan.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-03.png)

Valitse *Suhteellinen* suhteellisen päivämäärän osittajaa varten.

Voit sitten valita haluamasi asetukset.

*Suhteellisen päivämäärän osittajan* ensimmäisellä asetuksella on seuraavat vaihtoehdot:

![Näyttökuvassa näkyvät Suhteellinen-asetuksen ensimmäiset vaihtoehdot.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-04.png)

* Viimeinen

* Seuraava

* Tämä

*Suhteellisen päivämäärän osittajan* toisella (keskimmäinen) asetuksella voit antaa numeron suhteellisen päivämääräalueen määrittelemiseksi.

![Näyttökuvassa näkyvät Suhteellinen-asetuksen toiset vaihtoehdot.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-04a.png)

Kolmannen asetuksen avulla voit valita päivämäärämittarin. Sinulla on seuraavat vaihtoehdot:

![Näyttökuvassa näkyvät Suhteellinen-asetuksen kolmannet vaihtoehdot.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-05.png)

* Päivät

* Viikot

* Viikot (kalenteri)

* Kuukautta

* Kuukaudet (kalenteri)

* Vuodet

* Vuodet (kalenteri)

Jos valitset luettelosta **Kuukaudet** ja annat keskimmäiseksi asetukseksi *2*, tapahtuu seuraavaa:

* Jos tänään on 20. heinäkuuta,

* osittajan rajoittamiin visualisointeihin sisältyvät tiedot näyttävät tiedot kahdelta edelliseltä kuukaudelta:

* 21. toukokuuta – 20. heinäkuuta (tämä päivä)

Jos taas valitsit *Kuukaudet (Kalenteri)* , rajoitettu näyttö esittäisi tiedot ajalta 1.5.–30.6. (viimeiset kaksi täyttä kalenterikuukautta).

## <a name="using-the-relative-date-range-filter"></a>Suhteellisen päivämääräalueen suodattimen käyttäminen

Voit myös luoda raporttisivullesi tai koko raportillesi suhteellisen päivämääräalueen suodattimen. Tee niin vetämällä päivämääräkenttä **sivutason suodattimien** tai **raporttitason alueen suodattimien** kohtiin **Kenttä**-ruudussa:

![Näyttökuvassa on OrderDate-kenttä, jota vedetään sivutason suodattimien kohtaan.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-06.png)

Siellä voit vaihtaa suhteellinen päivämääräaluetta. Tämä toimii samalla tavalla kuin **suhteellisen päivämääräosittajan** muokkaaminen. Valitse **Suodatintyypin** pudotusvalikosta **Suhteellisen päivämäärän suodatus**.

![Näyttökuvassa näkyy suodatintyypin avattava valikko sekä hiiren osoitin, joka on suhteellisen päivämääräsuodatuksen kohdalla.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-07.png)

Kun valitset **suhteellisen päivämääräsuodatuksen**, näet kolme muokattavaa kohtaa, mukaan lukien numerolaatikon keskellä, aivan kuten osittajankin kohdalla.

![Näyttökuvassa näkyy raporttitason suodattimia sekä nuolia osoittamassa kohteiden näyttämisen kohteen.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-08.png)

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

**Suhteellisen päivämäärän osittajaa** ja suodatinta koskevat seuraavat rajoitukset ja huomioon otettavat seikat.

* **Power BI:n** tietomallit eivät sisällä aikavyöhyketietoja. Mallit voivat tallentaa aikoja, mutta niistä ei selviä mistä aikavyöhykkeestä on kyse.

* Osittaja ja suodatin perustuvat aina UTC-aikaan. Jos siis muokkaat suodatinta raportissa ja lähetät sen toisella aikavyöhykkeellä olevalle kollegalle, näette molemmat saman ajan. Jos ette ole UTC-aikavyöhykkeellä, sekä sinun että kollegasi täytyy huomioida aikaero.

* Voit muuntaa paikallisen aikavyöhykkeen ajan mukaisesti talletetut tiedot UTC-ajaksi **kyselyeditorilla**.

## <a name="next-steps"></a>Seuraavat vaiheet

Opettele [käyttämään ryhmittely ja lokerointia Power BI Desktopissa](../desktop-grouping-and-binning.md).
