---
title: Suhteellisen päivämääräosittajan tai suodattimen käyttö Power Bi Desktopissa
description: Opi miten osittajaa tai suodatinta käytetään rajoittamaan suhteellisia päivämääräjoukkoja Power Bi Desktopissa
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 12/05/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 0432998e44cdb1bf95a41225b73d805ec2a2379f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973892"
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi-desktop"></a>Suhteellisen päivämääräosittajan ja -suodattimen käyttö Power Bi Desktopissa
**Suhteellisen päivämääräosittajan** tai **suhteellisen päivämääräsuodattimen** avulla voit käyttää aikasidonnaisia suodattimia missä tahansa tietomallisi päivämääräsarakkeessa. Voit esimerkiksi käyttää **suhteellista päivämääräosittajaa** näyttääksesi vain viimeisten 30 päivän (tai kuukauden tai kalenterikuukausien jne.) aikana tapahtuneen myynnin tiedot. Ja kun päivität tiedot, suhteellinen ajanjakso käyttää automaattisesti soveltuvaa suhteellisen päivämäärän rajoitusta.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_01.png)

## <a name="using-the-relative-date-range-slicer"></a>Suhteellisen päivämääräalueen osittajan käyttäminen
Voit käyttää suhteellisen päivämäärän osittajaa kuten mitä muuta tahansa osittajaa. Luo yksinkertaisesti **osittaja**raportillesi ja valitse sitten päivämääräarvo **Kentän** arvoksi. Seuraavassa kuvassa valittuna on *OrderDate*-kenttä.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_02.png)

Valitse **suhteellisen päivämäärän osittajan** oikeassa yläkulmassa oleva merkki, jolloin näytölle avautuu valikko.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_03.png)

Valitse *Suhteellinen* suhteellisen päivämäärän osittajaa varten.

Voit sitten valita haluamasi asetukset. *Suhteellisen päivämäärän osittajan* ensimmäisessä pudotusvalikossa voit valita seuraavista:

* Viimeinen
* Seuraava
* Tämä

Nämä valinnat on esitetty seuraavassa kuvassa.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_04.png)

*Suhteellisen päivämäärän osittajan* seuraavat (keskimmäiset) asetukset sallivat numeron kirjoittamisen suhteellisen päivämääräalueen määrittelemiseksi.

Kolmas asetus salli päivämäärämitan valitsemisen, ja voit valita seuraavista vaihtoehdoista:

* Päivät
* Viikot
* Viikot (kalenteri)
* Kuukautta
* Kuukaudet (kalenteri)
* Vuodet
* Vuodet (kalenteri)

Nämä valinnat on esitetty seuraavassa kuvassa.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_05.png)

Jos valitset listasta *Kuukaudet* ja syötät keskimmäiseksi asetukseksi 2, tapahtuu seuraavaa: Jos päivämäärä on 20.7., osittajan rajoittamassa taulukossa näytettäisiin tiedot kahdelta edeltävältä kuukaudelta, alkaen 20.5. ja jatkuen aina 20.7. eli kyseisen päivän päivämäärään asti.

Toisaalta, jos valitsit *Kuukaudet (Kalenteri)* rajoitettu näyttö esittäisi tiedot 1.5. - 30.6. (viimeiset kaksi täyttä kalenterikuukautta).

## <a name="using-the-relative-date-range-filter"></a>Suhteellisen päivämääräalueen suodattimen käyttäminen
Voit myös luoda raporttisivullesi tai koko raportillesi suhteellisen päivämääräalueen suodattimen. Tee niin raahaamalla päivämääräkentän **sivutason suodattimien** tai **raporttitason alueen suodattimien** alueille **Kenttä**-ruudussa, kuten seuraavassa kuvassa on esitetty.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_06.png)

Kun suodatin on luotu, voit muuttaa suhteellista päivämääräaluetta samalla tavalla kuin **suhteellisen päivämäärän osittajaa**. Valitse **Suodatintyypin** pudotusvalikosta **Suhteellisen päivämäärän suodatus**.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_07.png)

Kun **Suhteellisen päivämäärän suodatus** on valittu, näet kolme muokattavaa kohtaa, mukaan lukien numerolaatikon keskellä, aivan kuten osittajankin kohdalla.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_08.png)

Sen enempää ei tarvita, jotta voisit käyttää näitä suhteellisen päivämäärän rajoituksia raporteissasi.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioon otettavat seikat
**Suhteellisen päivämäärän osittajaa** ja suodatinta koskevat seuraavat rajoitukset ja huomioon otettavat seikat.

* **Power BI:n** tietomallit eivät sisällä aikavyöhyketietoja. Mallit voivat tallentaa aikoja, mutta niistä ei selviä mistä aikavyöhykkeestä on kyse.
* Osittaja ja suodatin perustuvat aina aikaan UTC-muodossa, joten jos muokkaat suodatinta raportissa ja lähetät sen toisella aikavyöhykkeellä olevalle kollegalle, näette molemmat saman ajan. Toisaalta, jos et ole UTC-aikavyöhykkeellä, saatat nähdä eri aikasiirtymän mukaisia tietoja kuin oletit.
* Paikallisen aikavyöhykkeen ajan mukaisesti talletetut tiedot voidaan muuttaa UTC-ajaksi **Kyselyeditoria** käyttäen.

