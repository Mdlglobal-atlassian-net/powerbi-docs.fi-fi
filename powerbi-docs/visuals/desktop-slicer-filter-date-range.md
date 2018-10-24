---
title: Suhteellisen päivämääräosittajan tai suodattimen käyttö Power Bi Desktopissa
description: Opi miten osittajaa tai suodatinta käytetään rajoittamaan suhteellisia päivämääräjoukkoja Power Bi Desktopissa
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 692d752756590945eb17e2f512929f7303727e94
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/22/2018
ms.locfileid: "46564804"
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi-desktop"></a>Suhteellisen päivämääräosittajan ja -suodattimen käyttö Power Bi Desktopissa
**Suhteellisen päivämääräosittajan** tai **suhteellisen päivämääräsuodattimen** avulla voit käyttää aikasidonnaisia suodattimia missä tahansa tietomallisi päivämääräsarakkeessa. Voit esimerkiksi käyttää **suhteellisen päivämäärän osittajaa** näyttääksesi vain viimeisten 30 päivän (tai kuukauden tai kalenterikuukausien jne.) aikana tapahtuneen myynnin tiedot. Kun päivität tiedot, suhteellinen ajanjakso käyttää automaattisesti soveltuvaa suhteellisen päivämäärän rajoitusta.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_01.png)

## <a name="using-the-relative-date-range-slicer"></a>Suhteellisen päivämääräalueen osittajan käyttäminen
Voit käyttää suhteellisen päivämäärän osittajaa kuten mitä muuta tahansa osittajaa. Luo yksinkertaisesti **osittaja**raportillesi ja valitse sitten päivämääräarvo **Kenttä**-arvoksi. Seuraavassa kuvassa valittuna on *OrderDate*-kenttä.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_02.png)

Valitse **suhteellisen päivämäärän osittajan** oikeassa yläkulmassa oleva merkki, jolloin näytölle avautuu valikko.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_03.png)

Valitse *Suhteellinen* suhteellisen päivämäärän osittajaa varten.

Voit sitten valita haluamasi asetukset. *Suhteellisen päivämäärän osittajan* ensimmäisessä pudotusvalikossa on seuraavat vaihtoehdot:

* Viimeinen
* Seuraava
* Tämä

Nämä valinnat on esitetty seuraavassa kuvassa.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_04.png)

*Suhteellisen päivämäärän osittajan* seuraavat (keskimmäiset) asetukset sallivat numeron kirjoittamisen suhteellisen päivämääräalueen määrittelemiseksi.

Kolmannen asetuksen avulla voit valita päivämäärämitan. Sinulla on seuraavat vaihtoehdot:

* Päivät
* Viikot
* Viikot (kalenteri)
* Kuukautta
* Kuukaudet (kalenteri)
* Vuodet
* Vuodet (kalenteri)

Nämä valinnat on esitetty seuraavassa kuvassa.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_05.png)

Jos valitset tästä luettelosta vaihtoehdon *Kuukaudet* ja syötät keskimmäiselle asetukselle arvon 2, tapahtuu seuraavaa: jos päivämäärä on esimerkiksi 20.7., osittajan rajoittamassa taulukossa näytetään tiedot kahdelta edeltävältä kuukaudelta, alkaen 20.5. ja jatkuen aina 20.7. eli kyseisen päivän päivämäärään asti.

Toisaalta, jos valitsit *Kuukaudet (Kalenteri)* rajoitettu näyttö esittäisi tiedot 1.5. - 30.6. (viimeiset kaksi täyttä kalenterikuukautta).

## <a name="using-the-relative-date-range-filter"></a>Suhteellisen päivämääräalueen suodattimen käyttäminen
Voit myös luoda raporttisivullesi tai koko raportillesi suhteellisen päivämääräalueen suodattimen. Tee niin raahaamalla päivämääräkentän **sivutason suodattimien** tai **raporttitason alueen suodattimien** alueille **Kenttä**-ruudussa, kuten seuraavassa kuvassa on esitetty.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_06.png)

Kun suodatin on luotu, voit muuttaa suhteellista päivämääräaluetta samalla tavalla kuin **suhteellisen päivämäärän osittajaa**. Valitse **Suodatintyypin** pudotusvalikosta **Suhteellisen päivämäärän suodatus**.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_07.png)

Kun **Suhteellisen päivämäärän suodatus** on valittu, näet kolme muokattavaa kohtaa, mukaan lukien numerolaatikon keskellä, aivan kuten osittajankin kohdalla.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_08.png)

Sen enempää ei tarvita, jotta voisit käyttää näitä suhteellisen päivämäärän rajoituksia raporteissasi.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat
**Suhteellisen päivämäärän osittajaa** ja suodatinta koskevat seuraavat rajoitukset ja huomioon otettavat seikat.

* **Power BI:n** tietomallit eivät sisällä aikavyöhyketietoja. Mallit voivat tallentaa aikoja, mutta niistä ei selviä mistä aikavyöhykkeestä on kyse.
* Osittaja ja suodatin perustuvat aina aikaan UTC-muodossa, joten jos muokkaat suodatinta raportissa ja lähetät sen toisella aikavyöhykkeellä olevalle kollegalle, näette molemmat saman ajan. Toisaalta, jos et ole UTC-aikavyöhykkeellä, saatat nähdä eri aikasiirtymän mukaisia tietoja kuin oletit.
* Paikallisen aikavyöhykkeen ajan mukaisesti talletetut tiedot voidaan muuttaa UTC-ajaksi **Kyselyeditoria** käyttäen.
