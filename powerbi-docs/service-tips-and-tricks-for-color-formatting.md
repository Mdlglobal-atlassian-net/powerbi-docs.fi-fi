---
title: Vinkkejä värimuotoiluun Power BI:ssä
description: Vinkkejä värimuotoiluun Power BI:ssä
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Visualizations
ms.openlocfilehash: 3c91a6a70899a4a59c3d98cd9ab948284df5b662
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34298385"
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

Voidaksesi tehdä muutoksia sinun pitää olla muokkaamassa raporttia: valitse **Raportti** **Oma työtila** -ruudussa ja valitse sitten **Muokkaa raporttia** ylävalikon alueella seuraavassa kuvassa esitetyllä tavalla.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_1.png)

Kun **Visualisoinnit**-ruutu näkyy **Raportti**-piirtoalustan oikeassa reunassa, olet valmis aloittamaan mukauttaminen.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_2.png)

## <a name="change-the-color-of-a-single-data-point"></a>Yhden arvopisteen värin muuttaminen
Joskus saatat haluta korostaa yhtä tiettyä arvopistettä. Kyseessä voi olla myyntiluvut uuden tuotteen julkaisusta tai kasvaneet laatupistemäärät uuden ohjelman julkaisun jälkeen. Power BI:ssä voit korostaa tiettyä arvopistettä vaihtamalla sen väriä.

Seuraavat visualisoinnit luokittelevat tiloja elinkustannusten osalta. 

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_3.png)

Kuvittele nyt, että haluat nopeasti näyttää, mihin kohtaan luetteloa Washington sijoittuu käyttämällä väriä. Työvaiheet ovat seuraavanlaiset:

Laajenna **Tietojen värit** -osa. Seuraavat kohdat tulevat näkyviin.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_4.png)

Määritä **Näytä kaikki** -kohdan arvoksi **Käytössä**. Tämä näyttää jokaisen tietoelementin värit visualisoinnissa. Kun pidät hiiriosoitinta arvopisteiden päällä, vieritys on käytössä, joten voit muokata kaikkia arvopisteitä.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_5.png)

Tässä tapauksessa muutetaanpa **Washington** vihreäksi. Vieritetään alaspäin **Washington**-kohtaan ja valitaan sen väriruudun sisällä oleva alanuoli, jolloin värin valintaikkuna aukeaa.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_6.png)

Valittuna **Washington**-arvopiste on vihreän sävyinen ja erottuu varmasti.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_7.png)

Vaikka muutat visualisointityyppiä ja palaat sitten takaisin, Power BI muistaa valintasi ja säilyttää **Washingtonin** vihreänä.

Voit muuttaa useamman kuin yhden tietoelementin arvopisteen värin. Seuraavassa kuvassa **Arizona** on punainen ja **Washington** on edelleen vihreä.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_8.png)

Voit tehdä kaikenlaista väreillä. Seuraavassa osassa tutustumme liukuväreihin.

## <a name="base-the-colors-of-a-chart-on-a-numeric-value"></a>Kaavion värien pohjaaminen numeeriseen arvoon
Värin määrittäminen dynaamisesti numeerisen arvon perusteella on usein hyödyllistä kaavioille. Tekemällä tämän voit näyttää eri arvon, kuin mitä palkin koossa käytetään, ja näyttää kaksi arvoa yksittäisessä kaaviossa. Voit myös käyttää tätä arvopisteiden korostamiseen tietyn arvon ylä- tai alapuolella – voit esimerkiksi korostaa pienen kannattavuuden alueita.

Seuraavissa osissa esitellään erilaisia tapoja pohjata väri numeeriseen arvoon.

## <a name="base-the-color-of-data-points-on-a-value"></a>Arvopisteiden värin pohjaaminen arvoon
Voit muuttaa arvoon perustuvan värin vetämällä kenttää, johon haluat värin perustuvan, **Värikylläisyys**-alueelle **Kenttä**-ruudussa. Seuraavassa kuvassa **Voitto ennen veroja** on vedetty **Värikylläisyys**-kohtaan. Näet, että vaikka **Velon** **Bruttomyynti** on suurempi (sen sarake on korkeampi), **Amarillalla** on suurempi **Voitto ennen veroja** (sen sarakkeella on suurempi värikylläisyys).

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_9.png)

## <a name="customize-the-colors-used-in-the-color-scale"></a>Väriasteikossa käytettyjen värien mukauttaminen
Voit myös mukauttaa väriasteikossa käytettyjä värejä. Laajenna **Tietojen värit** -kohta ja näet liukuvärit, joita tietojen visualisoinnissa käytetään. Oletusarvon mukaan tietojen pienin arvo on liitetty vähiten kyllästettyyn väriin ja suurin arvo eniten kyllästettyyn väriin.

Värialue näkyy liukuväripalkissa, joka näyttää väriasteikon **Pienin**- ja **Suurin**-väriarvojen välillä niin, että **Pienin**-väriarvo on vasemmalla ja **Suurin**-väriarvo on oikealla.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_10.png)

Jos haluat muuttaa skaalausta ja käyttää eri värivalikoimaa, valitse värin avattava valikko **Pienin**- tai **Suurin**-kohdan vierestä ja valitse sitten väri. Seuraavassa kuvassa on näkyvissä **Suurin**-kohdan värin muuttuminen mustaksi, ja liukuväripalkissa näkyy uusi väriasteikko välillä **Pienin** ja **Suurin**.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_11.png)

Voit myös muuttaa tapaa, jolla arvot liitetään näihin väreihin. Seuraavassa kuvassa **Pienin**- ja **Suurin**-kohtien värit on määritetty oranssiksi ja vihreäksi.

Huomaa tässä ensimmäisessä kuvassa, miten kaavion palkit vastaavat palkissa näkyvää liukuväriä. Suurin arvo on vihreä, pienin arvo on oranssi ja kunkin palkin välillä on vihreän ja oranssin väliltä oleva sävy.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_12.png)

Katsotaan sitten, mitä tapahtuu, jos syötämme **Pienin**- ja **Suurin**-arvoruutuihin numeerisia arvoja, jotka ovat **Pienin**- ja **Suurin**-värivalitsinten alapuolella (näkyy seuraavassa kuvassa). **Pienin**-kohdan arvoksi määritetään 20 000 000 ja **Suurin**-kohdan arvoksi 20 000 000.

Määrittämällä kyseiset arvot liukuväriä ei enää käytetä kaavion arvoihin, jotka ovat **Pienin**- tai **Suurin**-arvojen alapuolella. Palkki, jonka arvo on **Suurin**-arvon yläpuolella, on vihreä, ja palkki, jonka arvo on **Pienin**-arvon alapuolella, on punainen.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_13.png)

## <a name="use-diverging-color-scales"></a>Erkautuvien väriasteikkojen käyttäminen
Joskus tiedoissa voi olla luonnollisesti erkautuva asteikko. Esimerkiksi lauhkean alueen luonnollinen keskikohta on jäätymispiste, ja kannattavuuspistemäärällä on luonnollinen keskipiste (nolla).

Jos haluat käyttää erkautuvaa väriasteikkoa, vedä **Erkautuva**-liukusäädin kohtaan **Käytössä**. Kun **Erkautuva** on otettu käyttöön, näkyviin tulee ylimääräinen värivalitsin ja arvoruutu, joita kumpaakin kutsutaan **keskukseksi**, seuraavassa kuvassa esitetyllä tavalla.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_14.png)

Kun **Erkauvua**-liukusäädin on käytössä, voit määrittää värit **Pienin**-, **Suurin**- ja **Keskus**-kohdille erikseen. Seuraavassa kuvassa **Keskus**-kohdan asetuksena on yksi, joten palkit, joiden arvo on suurempi kuin yksi, ovat vihreän sävyisiä, ja palkit, joiden arvo on pienempi kuin yksi, ovat punaisen sävyisiä.

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

