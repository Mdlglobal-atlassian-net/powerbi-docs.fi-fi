---
title: Power BI -raporttien parantaminen visuaalisia elementtejä käyttämällä
description: Paranna raportteja visuaalisilla elementeillä, kuten taustakuvalla ja visuaalisilla ylätunnisteilla.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: a51c7f4b305fb8aab4112de3b5426d12b0e21b50
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83349122"
---
# <a name="use-visual-elements-to-enhance-power-bi-reports"></a>Power BI -raporttien parantaminen visuaalisia elementtejä käyttämällä

**Power BI Desktopin** raporttien ulkoasua voi parantaa käyttämällä visualisoinneissa visuaalisia elementtejä, kuten taustakuvia ja parannettuja visuaalisia ylätunnisteita.

![Taustakuvan ja pienten visuaalisten ylätunnisteiden lisääminen raporttien parantamiseksi](media/desktop-visual-elements-for-reports/visual-elements-for-reports_01.png)

**Power BI Desktopin** heinäkuun 2018 julkaisusta alkaen voit tehdä raporteistasi ja analyyseistasi entistäkin kiinnostavamman näköisiä erilaisia parannuksia lisäämällä. Tässä artikkelissa kuvattuja parannuksia: 

* Lisäämällä **taustakuvan** raportteihin voit parantaa niitä tai korostaa tietojen elementtejä.
* Yksittäisiin visualisointeihin voit lisätä parannettuja **visuaalisia ylätunnisteita**, niin voit luoda niille yhdenmukaisen raporttikankaalla. 

Seuraavissa osioissa kuvataan parannusten käyttäminen ja lisääminen raportteihin.

## <a name="using-wallpaper-in-power-bi-reports"></a>Taustakuvan käyttäminen Power BI -raporteissa

Voit muotoilla raporttisivun ulkopuolista harmaata aluetta käyttämällä **taustakuvaa**. Seuraavassa kuvassa on nuoli, joka näyttää taustakuvan alueen. 

![Taustakuva peittää raporttia ympäröivän harmaan alueen](media/desktop-visual-elements-for-reports/visual-elements-for-reports_02.png)

Voit asettaa taustakuvan sivukohtaisesti tai käyttää raportin jokaisella sivun samaa taustakuvaa. Jos haluat asettaa taustakuvan, valitse **muotoilukuvake**, kun raportissasi ei ole visualisointia valittuna. **Taustakuva**-kortti avautuu ruutuun.

![Taustakuvan alue Muotoilu-ruudussa](media/desktop-visual-elements-for-reports/visual-elements-for-reports_03.png)

Voit valita **taustakuvaksi** värin valitsemalla avattavan **Väri**-valikon. Voit valita taustakuvaksi kuvan valitsemalla **Lisää kuva**. Voit myös käyttää taustakuvassa läpinäkyvyyttä, olipa kyseessä väri tai kuva. Se tapahtuu **Läpinäkyvyys**-liukusäätimellä.

On hyvä pitää mielessä **taustakuvaa** koskevat seuraavat määritelmät:

* Raporttialueen ulkopuolella oleva harmaa alue on **taustakuvan** alue.
* Kankaan aluetta, johon visualisoinnit sijoitetaan, kutsutaan **raporttisivuksi**. Sitä voi mukauttaa **Muotoilu-ruudun** avattavan **Sivun tausta** -luettelon kautta.

**Raporttisivu** on aina edustalla (taustakuvaan verrattuna) ja **taustakuva** on sen takana. Se on taaimmainen elementti raporttisivulla. Kun otat käyttöön läpinäkyvyyden sivulle, myös raportin visualisointeihin käytetään läpinäkyvyyttä. Siten taustakuva voi näkyä taustalla visualisointien läpi.

Kaikkien uusien raporttien oletusasetukset ovat seuraavat:

* Raportin **sivu** on määritetty **valkoiseksi** ja sen läpinäkyvyytenä on **100 %**
* **Taustakuva** on määritetty **valkoiseksi** ja läpinäkyvyytenä on **0 %**

Kun sivun taustan läpinäkyvyys on suurempi kuin 50 %, näet raporttia luodessasi tai muokatessasi pisteviivan, joka näyttää raporttikankaan reunan. 

![Yli 50 %:n läpinäkyvyys tuo esiin pisteviivareunan](media/desktop-visual-elements-for-reports/visual-elements-for-reports_04.png)

On tärkeää huomata, että pisteviivareuna näkyy *vain* raporttia muokattaessa. Sitä *ei* näytetä julkaistua raporttiasi esimerkiksi **Power BI -palvelussa** tarkasteleville.

> [!NOTE]
> Jos käytät taustakuvalle mustaa taustaa ja tekstivärinä valkoista tai hyvin vaaleaa väriä, muista, että **Vie PDF-tiedostoon** -ominaisuus ei sisällä taustakuvaa, joten valkoisia fontteja sisältävät viennit ovat lähes näkymättömiä viedyssä PDF-tiedostossa. Katso lisätietoja [viennistä PDF-tiedostoon](desktop-export-to-pdf.md) kohdasta **Vienti PDF-tiedostoon**.


## <a name="using-improved-visual-headers-in-power-bi-reports"></a>Parannettujen visuaalisten ylätunnisteiden käyttäminen Power BI -raporteissa

**Power BI Desktopin** raporttien visualisointien ylätunnisteita on parannettu merkittävästi heinäkuun 2018 julkaisusta alkaen. Ensisijaisena parannuksena ylätunniste on irrotettu visualisoinnista, jotta sen paikkaa voi muuttaa halutun asettelun ja sijoittelun saavuttamiseksi. Ylätunniste lisäksi näkyy itse visualisoinnin sisällä sen sijaan että kelluisi sen yläpuolella. 

Ylätunniste näkyy oletusarvoisesti visualisoinnin sisällä tasattuna otsikon kanssa. Seuraavassa kuvassa näet ylätunnisteen (kiinnityskuvake, laajennuskuvake ja ellipsikuvake) visualisoinnin sisällä tasattuna oikealle samaan vaakatasoon kuin visualisoinnin otsikko.

![Visuaaliset ylätunnisteet voivat nyt sijaita visualisoinnin sisällä tai niitä voi siirtää](media/desktop-visual-elements-for-reports/visual-elements-for-reports_05.png)

Jos visualisoinnilla ei ole otsikkoa, ylätunniste kelluu visualisoinnin oikean yläkulman päällä seuraavassa kuvassa esitetyllä tavalla. 

![Visuaalinen ylätunniste kelluu visualisoinnin yläpuolella, jos otsikkoa ei ole](media/desktop-visual-elements-for-reports/visual-elements-for-reports_07.png)

Jos visualisointi sijoitetaan aivan raportin yläreunaan, visuaalinen ylätunniste siirtyy visualisoinnin alaosaan. 

![Visuaalinen ylätunniste siirtyy alaosaan raportin yläreunan tieltä](media/desktop-visual-elements-for-reports/visual-elements-for-reports_08.png)

Jokaisella visualisoinnilla on **Visuaalinen ylätunniste** -kortti **Visualisoinnit**-ruudun **Muotoilu**-osiossa. Tässä kortissa voit säätää visuaalisen ylätunnisteen kaikenlaisia piirteitä.

![Jokaisella visualisoinnilla on Visuaalinen ylätunniste -kortti Muotoilu-osiossa](media/desktop-visual-elements-for-reports/visual-elements-for-reports_09.png)

> [!NOTE]
> Vaihtopainikkeiden näkyvyys ei vaikuta raporttiin, kun olet luomassa tai muokkaamassa raporttia. Näet vaikutuksen, kun julkaiset raportin ja tarkastelet sitä lukutilassa. Tällä tavalla varmistetaan, että visuaalisten ylätunnisteiden monet tärkeät vaihtoehdot ovat muokkaamisen aikana näkyvillä – erityisesti ongelmista ilmoittavat varoituskuvakkeet.

Vain **Power BI -palvelussa** näkyvien raporttien visuaalisten ylätunnisteiden käyttöä voi säätää valitsemalla **Oma työtila > Raportit** ja valitsemalla sitten **asetuskuvakkeen**. Näet asetukset sille raportille, jonka valitsit **Asetukset**-osiossa. Voit muuttaa asetuksia seuraavassa kuvassa esitetyllä tavalla.

![Power BI -palvelun asetukset parannettujen visuaalisten ylätunnisteiden käyttämiseen](media/desktop-visual-elements-for-reports/visual-elements-for-reports_10.png)

### <a name="enabling-improved-visual-headers-for-existing-reports"></a>Parannettujen visuaalisten ylätunnisteiden käyttäminen aiemmin luoduissa raporteissa

Uudet visuaaliset ylätunnisteet on otettu oletusarvoisesti käyttöön kaikissa uusissa raporteissa. Aiemmin luotujen raporttien osalta sinun on otettava ne käyttöön **Power BI Desktopissa** valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Asetukset**. Valitse **Raportin asetukset** -osiossa **Käytä nykyaikaista visuaalista ylätunnistetta ja päivitettyjä tyyliasetuksia** -valintaruutu.

![Aiemmin luoduissa raporteissa Asetukset-valintaruutu on valittava parannettujen visuaalisten ylätunnisteiden käyttämiseksi](media/desktop-visual-elements-for-reports/visual-elements-for-reports_06.png)


## <a name="next-steps"></a>Seuraavat vaiheet
Saat lisätietoja **Power BI Desktopista** ja käytön aloittamisesta tutustumalla seuraaviin artikkeleihin.

* [Mikä on Power BI Desktop?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktopin kyselyiden yleiskatsaus](../transform-model/desktop-query-overview.md)
* [Power BI Desktopin tietolähteet](../connect-data/desktop-data-sources.md)
* [Tietoihin yhdistäminen Power BI Desktopissa](../connect-data/desktop-connect-to-data.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](../connect-data/desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](../transform-model/desktop-common-query-tasks.md)   
