---
title: Vinkkejä värimuotoiluun Power BI:ssä
description: Vinkkejä värimuotoiluun Power BI:ssä
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/10/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3865647a056e28735894e40f71045305518642c6
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880657"
---
# <a name="tips-and-tricks-for-color-formatting-in-power-bi"></a>Vinkkejä värimuotoiluun Power BI:ssä
Power BI tarjoaa useita eri tapoja koontinäyttöjen ja raporttien mukauttamiseen. Tässä artikkelissa on kokoelma vinkkejä, joiden avulla voit tehdä Power BI -visualisoinneistasi mielenkiintoisempia ja tarpeisiisi sopivampia.

Saatavilla ovat seuraavat vinkit. Haluatko antaa vinkin? Hienoa! Lähetä se meille ja saatamme lisätä sen tähän luetteloon.

* Yhden arvopisteen värin muuttaminen
* Kaavion värien pohjaaminen numeeriseen arvoon
* Arvopisteiden värin pohjaaminen kenttäarvoon
* Väriasteikossa käytettyjen värien mukauttaminen
* Erkautuvien väriasteikkojen käyttäminen
* Kumoaminen Power BI:ssä

Jos haluat tehdä muutoksia, sinun on oltava raportin muokkaustilassa. Avaa raportti ja valitse ylävalikosta **Muokkaa raporttia** kuvassa esitetyllä tavalla.

![Muokkaa-valikon sijainti](media/service-tips-and-tricks-for-color-formatting/power-bi-edit-report.png)

Kun **Suodattmet**- ja **Visualisoinnit**-ruudut näkyvät piirtoalustan oikeassa reunassa, olet valmis aloittamaan mukauttamisen. Jos ruutua ei näy, avaa se napsauttamalla oikean yläkulman nuolta.

![piirtoalusta muokkausnäkymässä](media/service-tips-and-tricks-for-color-formatting/power-bi-edit.png)

## <a name="change-the-color-of-a-single-data-point"></a>Yhden arvopisteen värin muuttaminen
Joskus saatat haluta korostaa yhtä tiettyä arvopistettä. Kyseessä voi olla myyntiluvut uuden tuotteen julkaisusta tai kasvaneet laatupistemäärät uuden ohjelman julkaisun jälkeen. Power BI:ssä voit korostaa tiettyä arvopistettä vaihtamalla sen väriä.

Seuraava visualisointi asettaa myydyt yksiköt järjestykseen tuotesegmentin mukaan. 

![Muuta tietojen värit harmaaksi](media/service-tips-and-tricks-for-color-formatting/power-bi-data.png)

Oletetaan, että haluat korostaa **Kätevyys**-segmenttiä värin avulla näyttääksesi, kuinka hyvin tämä uusi segmentti suoriutuu. Työvaiheet ovat seuraavanlaiset:

Laajenna **Tietojen värit** -osio ja aseta **Näytä kaikki** -kohdan liukusäädin Käytössä-asentoon. Tämä näyttää jokaisen tietoelementin värit visualisoinnissa. Kun pidät hiiriosoitinta arvopisteiden päällä, vieritys on käytössä, joten voit muokata kaikkia arvopisteitä.

![](media/service-tips-and-tricks-for-color-formatting/power-bi-show.png)

Määritä **Kätevyys** oranssiksi. 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-one-color.png)

Valittuna **Kätevyys**-arvopiste on kauniin oranssin sävyinen ja erottuu varmasti.

Vaikka muuttaisit visualisointityyppiä ja palaisit sitten takaisin, Power BI muistaa valintasi ja säilyttää **Kätevyyden** osanssina.

Voit vaihtaa visualisoinnissa joko yhden, useamman tai kaikkien tietoelementtien arvopisteiden värin. Saatat esimerkiksi haluta visualisoinnin heijastavan yrityksesi värejä. 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-corporate.png)

Voit tehdä kaikenlaista väreillä. Seuraavassa osassa tutustumme liukuväreihin.

## <a name="base-the-colors-of-a-chart-on-a-numeric-value"></a>Kaavion värien pohjaaminen numeeriseen arvoon
Värin määrittäminen dynaamisesti numeerisen arvon perusteella on usein hyödyllistä kaavioille. Tekemällä tämän voit näyttää eri arvon, kuin mitä palkin koossa käytetään, ja näyttää kaksi arvoa yksittäisessä kaaviossa. Voit myös käyttää tätä arvopisteiden korostamiseen tietyn arvon ylä- tai alapuolella – voit esimerkiksi korostaa pienen kannattavuuden alueita.

Seuraavissa osissa esitellään erilaisia tapoja pohjata väri numeeriseen arvoon.

## <a name="base-the-color-of-data-points-on-a-value"></a>Arvopisteiden värin pohjaaminen arvoon
Voit muuttaa värin arvon mukaiseksi avaamalla Muotoilu-ruutu ja valitse **Ehdollinen muotoilu** -vaihtoehto.  

![valitse ehdollinen muotoilu -vaihtoehto napsauttamalla kolmea päällekkäistä pistettä](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional-formatting.png)

Oletusvärit-ruudussa voit määrittää ehdolliseen muotoiluun käytettävät kentät avattavien luetteloiden avulla. Tässä esimerkissä on valittu **Myyntifaktat** > **Yksiköitä yhteensä** -kenttä sekä korostettu **Pienin arvo** vaaleansinisellä ja **Suurin arvo** tummansinisellä värillä. 

![värin mukaisen ehdollisen muotoilun asetukset](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional-formatting2-new.png)

![pylväskaavio, jossa käytetty oletusvärejä](media/service-tips-and-tricks-for-color-formatting/power-bi-default-colors.png)

Voit myös muotoilla visualisoinnin värin käyttämällä kenttää, joka ei ole visualisoinnin osa. Seuraavassa kuvassa **Markkinaprosenttiosuus samaan aikaan viime vuonna VA** on käytössä. 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional-colors.png)


Kuvasta näet, että vaikka **Tuottavuus**- ja **Äärimmäinen**-segmenttien yksiköitä on myyty enemmän (niiden pylväät ovat korkeammat), **Kohtuus**-segmentin **Markkinaprosenttiosuus samaan aikaan viime vuonna VA** on suurempi (pylvään värikylläisyys on vahvempi).

## <a name="customize-the-colors-used-in-the-color-scale"></a>Väriasteikossa käytettyjen värien mukauttaminen
Voit myös muuttaa tapaa, jolla arvot liitetään näihin väreihin. Seuraavassa kuvassa **Pienin**- ja **Suurin**-kohtien värit on määritetty oranssiksi ja vihreäksi.

Huomaa tässä ensimmäisessä kuvassa, miten kaavion palkit vastaavat palkissa näkyvää liukuväriä. Suurin arvo on vihreä, pienin arvo on oranssi ja kunkin palkin välillä on vihreän ja oranssin väliltä oleva sävy.

![](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional4.png)

Seuraavaksi katsotaan, mitä tapahtuu, jos **Pienin** ja **Suurin**-ruutuihin lisätään numeeriset arvot. Määritetään **Pienin**-kohdan arvoksi 3 500 ja **Suurin**-kohdan arvoksi 6 000.

Määrittämällä kyseiset arvot liukuväriä ei enää käytetä kaavion arvoihin, jotka ovat **Pienin**- tai **Suurin**-arvojen alapuolella. Palkki, jonka arvo on **Suurin**-arvon yläpuolella, on vihreä, ja palkki, jonka arvo on **Pienin**-arvon alapuolella, on punainen.

![](media/service-tips-and-tricks-for-color-formatting/power-bi-conditional3.png)

## <a name="use-diverging-color-scales"></a>Erkautuvien väriasteikkojen käyttäminen
Joskus tiedoissa voi olla luonnollisesti erkautuva asteikko. Esimerkiksi lauhkean alueen luonnollinen keskikohta on jäätymispiste, ja kannattavuuspistemäärällä on luonnollinen keskipiste (nolla).

Voit käyttää erkautuvia väriasteikkoja valitsemalla **Erkautuva**-vaihtoehdon. Kun **Erkautuva** on otettu käyttöön, näkyviin tulee ylimääräinen värivalitsin, jota kutsutaan **keskukseksi** (ks. seuraava kuva).

![](media/service-tips-and-tricks-for-color-formatting/power-bi-diverging2.png)

Kun **Erkauvua**-liukusäädin on käytössä, voit määrittää värit **Pienin**-, **Suurin**- ja **Keskus**-kohdille erikseen. Seuraavassa kuvassa **Keskus**-kohdan asetuksena on 0,2 **Markkinaprosenttiosuus samaan aikaan viime vuonna VA** -kohdan osalta. Tämän vuoksi pylväät, joiden arvo on suurempi kuin 0,2, näytetään vihreän eri sävyissä, ja palkit, joiden arvo on pienempi kuin yksi, näytetään punaisen eri sävyissä.

![](media/service-tips-and-tricks-for-color-formatting/power-bi-diverging.png)

## <a name="how-to-undo-in-power-bi"></a>Kumoaminen Power BI:ssä
Kuten monissa muissakin Microsoft-palveluissa ja -ohjelmistoissa, myös Power BI:ssä viimeisimmän komennon kumoaminen onnistuu helposti. Oletetaan esimerkiksi, että muutat arvopisteen tai arvopisteiden sarjan väriä etkä ole tyytyväinen väriin, kun se tulee näkyviin visualisoinnissa. Et muista täsmälleen entistä väriä, mutta tiedät haluavasi värin takaisin!

Jos haluat **kumota** yhden tai useita edellisiä toimintoja, toimi seuraavasti:

- Kirjoita CTRL+Z

## <a name="feedback"></a>Palaute
Onko sinulla vinkki, jonka haluat jakaa? Lähetä se meille ja saatamme lisätä sen tänne.

>[!NOTE]
>Nämä värin, akselin ja niihin liittyvät mukautukset, jotka ovat käytettävissä, kun **Muoto**kuvake on valittuna, ovat myös käytettävissä Power BI Desktopissa.

## <a name="next-steps"></a>Seuraavat vaiheet
[Värimuotoilun ja akseliominaisuuksien käytön aloittaminen](service-getting-started-with-color-formatting-and-axis-properties.md)

