---
title: Värimuotoilun ja akseliominaisuuksien käytön aloittaminen
description: Värimuotoilun ja akseliominaisuuksien käytön aloittaminen
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Visualizations
ms.openlocfilehash: 422f0ba97f5118ddc57e9102055a070deaf99b90
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2018
ms.locfileid: "39329611"
---
# <a name="getting-started-with-color-formatting-and-axis-properties"></a>Värimuotoilun ja akseliominaisuuksien käytön aloittaminen
Valitsemalla **Power BI** voit muuttaa arvosarjojen, arvopisteiden ja jopa visualisointien taustan värin. Voit myös muuttaa x- ja y-akselin esitystapaa, joten voit hallita täydellisesti raporttinäkymien ja raporttien ulkonäköä.

Aloita valitsemalla **Raportti** **Oma työtilani** -ruudusta. Valitse sitten ylävalikosta **Muokkaa raporttia**.  
![](media/service-getting-started-with-color-formatting-and-axis-properties/gettingstartedcolor_1a.png)

Kun muokkaat raporttia ja sinulla on visualisointi valittuna, näkyviin tulee **Visualisoinnit**-ruutu, jonka avulla voit lisätä tai muuttaa visualisointeja. Käytettävissä olevien visualisointien alapuolella on kolme kuvaketta: **Kentät** (palkkien pino), **Muoto** (tela) ja **Analytiikka** (suurennuslasi). Alla olevassa kuvassa näkyvä keltainen palkki kuvakkeen alapuolella osoittaa **Kentät**-kuvakkeen olevan valittuna.

![](media/service-getting-started-with-color-formatting-and-axis-properties/gettingstartedcolor_2a.png)

Kun valitset kohdan **Muoto**, sen alapuolella oleva alue näyttää ne värin ja akselin mukautukset, jotka ovat käytössä valitun visualisoinnin kanssa.  
![](media/service-getting-started-with-color-formatting-and-axis-properties/gettingstartedcolor_3a.png)

Voit mukauttaa kunkin visualisoinnin monia elementtejä:

* Selite
* X-akseli
* Y-akseli
* Tietojen värit
* Arvopisteiden otsikot
* Muodot
* Piirtoalue
* Otsikko
* Tausta
* Lukitse kuvasuhde
* Reunus

> [!NOTE]
>  
> Kaikkia näitä elementtejä ei näy jokaisen visualisointityypin kanssa. Valitsemasi visualisointi vaikuttaa käytettävissä oleviin mukautuksiin; et voi esimerkiksi mukauttaa x-akselia jos olet valinnut ympyräkaavion, sillä niissä ei ole x-akselia.
> 
> 

Huomaa myös, että jos et ole valinnut visualisointia, kuvakkeiden sijaan näkyviin tulee **Suodattimet**, josta voit asettaa suodattimia kaikkiin sivulla oleviin visualisointeihin.

Esittelemme pari esimerkkiä: ensimmäinen värien käyttämisestä ja toinen akselin ominaisuuksien muuttamisesta. Sen jälkeen sinun pitäisi olla valmis mukauttamaan värejä, akseleita ja otsikoita koko päivän.

## <a name="working-with-colors"></a>Värien käyttäminen
Käydään läpi kaavion värien mukauttamiseen tarvittavat vaiheet.

1. Valitsen raporttipohjasta kohdan **Klusteroitu pylväskaavio**.
2. Seuraavaksi valitsen **Muoto**-kuvakkeen, joka näyttää käytettävissä olevat mukautukset.
3. Seuraavaksi valitsen pienen alanuolen **Tietojen värit** -mukauttamisen vasemmalta puolelta. Tämä toiminto näyttää, miten voin mukauttaa tietojen värejä valitsemani visualisoinnin vaihtoehdoilla.
4. **Tietojen värit** laajenee alaspäin ja näyttää käytettävissä olevat mukautukset.  
   ![](media/service-getting-started-with-color-formatting-and-axis-properties/gettingstartedcolor_4a.png)

Tehdään joitain muutoksia. Voin tehdä muutoksia jokaiseen saatavilla olevaan arvosarjaan valitsemalla värin vierestä alanuolen. Laitan **Elinkustannukset**-kohdan keltaisella **Sää**-kohdan oranssilla ja **Yhteisön hyvinvointi** -kohdan vihreällä. Seuraavassa näytössä näkyy viimeinen vaiheeni, **Elinkustannukset**-kohdan muuttaminen.  

![](media/service-getting-started-with-color-formatting-and-axis-properties/gettingstartedcolor_5a.png)

Muutokset näkyvät alla olevassa kuvassa. Vau, onpa kirkas kaavio. Tässä on muutamia hyödyllisiä elementtejä koskien värien käyttöä. Luettelon numerot esiintyvät myös seuraavassa näytössä ja ne ilmaisevat, mistä näitä hyödyllisiä elementtejä pääsee käyttämään tai muuttamaan.

1. Et pidä väreistä? Ei hätää, valitse **Palauta oletusasetukseen** ja valintasi palautuvat oletusasetuksiin. Voit tehdä sen joko yhdelle värille tai koko visualisoinnille.
2. Haluatko värin, jota et näe valikoimassa? Valitse vain **Mukautettu väri** ja valitse asteikolta.  
   ![](media/service-getting-started-with-color-formatting-and-axis-properties/gettingstartedcolor_6a.png)

Etkö pidä juuri tekemistäsi muutoksista? Käytä yhdistelmää **CTRL + Z** kumoamisvaiheena, aivan kuten olet tottunut tekemään.

## <a name="changing-axis-properties"></a>Akselin ominaisuuksien muuttaminen
X- tai Y-akselin muokkaaminen on usein hyödyllistä. Seuraavassa kuvassa näytetään, miten voit muokata haluamaasi akselia valitsemalla alanuoli-kuvakkeen akselin vasemmalta puolelta, aivan kuten värejä käyttäessäsi.  
![](media/service-getting-started-with-color-formatting-and-axis-properties/gettingstartedcolor_7a.png)

Jos haluat tiivistää **X-akseli**n asetuksia, valitse vain ylänuoli-kuvake **X-akseli**n vierestä.

**X-akseli**n vieressä olevalla valintanapilla voit poistaa x-akselin otsikot kokonaan. **Otsikko**-kohdan vieressä olevalla valintanapilla voit valita ovatko akseleiden otsikot käytössä vai eivät.  

Power BI raportteihin ja raporttinäkymiin on valittavana monenlaisia värejä ja mukautuksia.

> [!NOTE]
>  
> Mukautukset, jotka ovat käytettävissä **Muoto**-kuvakkeen ollessa valittuna, ovat käytettävissä myös Power BI Desktopissa.
> 
> 

## <a name="next-step"></a>Seuraava vaihe
Katso lisätietoja seuraavasta artikkelista:  

* [Vinkkejä värimuotoiluun Power BI:ssä](service-tips-and-tricks-for-color-formatting.md)  

