---
title: Sertifioidut Power BI:n Power BI -visualisoinnit
description: Mukautetun visualisoinnin sertifioinnin edellytykset ja lähettämisprosessi. Lisäksi luettelo jo sertifioiduista Power BI -visualisoinneista.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 05/9/2019
ms.openlocfilehash: c6ecb2eb2346940a22bbd6b7bff5ca0138faa290
ms.sourcegitcommit: 08b73af260ded51daaa6749338cb85db2eab587f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/15/2019
ms.locfileid: "74102590"
---
# <a name="get-a-power-bi-visual-certified"></a>Sertifioinnin hankkiminen Power BI -visualisoinnille

## <a name="what-are-_certified_-power-bi-visuals"></a>Mitä **_sertifioidut_** Power BI -visualisoinnit ovat?

Sertifioidut Power BI -visualisoinnit ovat **Marketplacen** visualisointeja, jotka täyttävät tietyt **Power BI -tiimin** testaamat ja hyväksymät **koodivaatimukset**. Kun mukautettu visualisointi on sertifioitu, se tarjoaa lisää ominaisuuksia. Voit esimerkiksi [viedä sisältöä PowerPointiin](../consumer/end-user-powerpoint.md) ja näyttää visualisoinnin [raporttisivujen tilaamisen](../consumer/end-user-subscribe.md) yhteydessä lähetettävissä sähköposteissa.

**Sertifioituja Power BI -visualisointeja** käytetään samoin kun [tavallisia Power BI -visualisointeja](power-bi-custom-visuals.md). Sertifioituja Power BI -visualisointeja voidaan lisätä **Power BI -palveluun** ja **Power BI Desktop -raporttiin**, ja niitä voidaan tarkastella **Power BI:n mobiiliversiossa** ja **Power BI Embeddedissä**.

Suoritettavat testit on suunniteltu varmistamaan, ettei visualisointi käytä ulkoisia palveluita tai resursseja. **Microsoft** *ei* ole kolmannen osapuolen Power BI -visualisointien tekijä, ja se kehottaa asiakkaita ottamaan yhteyttä suoraan tekijään visualisoinnin toiminnan varmistamiseksi.

Sertifiointiprosessi on vapaaehtoinen, ja kehittäjät voivat itse päättää, haluavatko he sertifioida Marketplacessa olevan visualisointinsa.  

**Sertifioimattomat Power BI -visualisoinnit** eivät välttämättä ole turvallisia käyttää. Jotkin visualisoinnit eivät ole sertifioituja, koska ne eivät täytä yhtä tai useampaa [sertifiointivaatimusta](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Tällaisia ovat esimerkiksi karttavisualisoinnit, jotka muodostavat yhteyden ulkoisiin palveluihin, tai visualisoinnit, jotka hyödyntävät kaupallisia kirjastoja.

Oletko web-kehittäjä ja halukas luomaan omia visualisointeja ja lisäämään niitä  **[Microsoft AppSourceen](https://appsource.microsoft.com)** ? Katso ohjeet kohdasta  **[Power BI:n mukautetun visualisoinnin kehittäminen](visuals/custom-visual-develop-tutorial.md)** .

## <a name="removal-of-power-bi-certified-power-bi-visuals"></a>Sertifioitujen Power BI -visualisointien poistaminen

Microsoft saattaa poistaa visualisoinnin [sertifioitujen luettelosta](#list-of-power-bi-visuals-that-have-been-certified) oman harkintansa mukaan.

## <a name="getting-a-custom-visualcertified"></a>Mukautetun visualisoinnin sertifioinnin hankkiminen

### <a name="certification-requirements"></a>Sertifioinnin edellytykset

Mukautetun visualisoinnin [sertifiointi](#get-a-power-bi-visual-certified) edellyttää, että se täyttää seuraavat vaatimukset:  

* Microsoft AppSourcen hyväksyntä. Mukautetun visualisoinnin on oltava [Marketplacessa](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals).
* Mukautettu visualisointi on kirjoitettu **Versioned-ohjelmointirajapinnan versiolla 2.5** tai uudemmalla versiolla.
* Power BI -tiimi voi tarkastella koodisäilöä (esimerkiksi lähdekoodia (JavaScript tai TypeScript) ihmisen luettavissa olevassa muodossa GitHubin kautta).

    >[!Note]
    > Sinun ei tarvitse jakaa koodia Githubissa julkisesti.
* Koodisäilön vaatimukset:
   * Pitää sisältää seuraavat tiedostot:
      * .gitignore
      * capabilities.json
      * pbiviz.json
      * package.json
      * package-lock.json
      * tsconfig.json
   * Ei saa sisältää node_modules-kansiota (lisää node_modules .gitingere-tiedostoon)
   * **npm install** -komento ei saa palauttaa mitään virheitä.
   * **npm audit** -komento ei saa palauttaa varoituksia, joilla on korkea tai kohtalainen taso.
   * **pbiviz package** -komento ei saa palauttaa mitään virheitä.
   * Pitää sisältää [TSlint Microsoftilta](https://www.npmjs.com/package/tslint-microsoft-contrib) ilman ohitettua määritystä, eikä tämä komento saa palauttaa mitään lint-virheitä.
   * Mukautetun visualisoinnin kootun paketin on vastattava lähetettyä pakettia (molempien tiedostojen md5-hajautusarvon on oltava sama).
* Lähdekoodi vaatimukset:
   * Visualisoinnin on tuettava [Tapahtumien hahmontaminen -ohjelmointirajapintaa](https://microsoft.github.io/PowerBI-visuals/docs/how-to-guide/rendering-events/).
   * Varmista, että mitään satunnaisia/dynaamisia koodeja ei suoriteta (huono: eval(), epäluotettava käyttö settimeout(), requestAnimationFrame(), setinterval(jokin toiminto käyttäjän syötteellä), käyttäjän syötteen/tietojen suorittaminen).
   * Varmista, että DOM-objektia manipuloidaan luotettavasti (huono: innerHTML, D3.html(<jokin käyttäjän/tietojen syöte>), käytä sanitaatiota käyttäjän syötteessä/tiedoissa, ennen kuin lisäät sen DOM-objektiin.
   * Varmista, että selainkonsolissa ei ole JavaScript-virheitä/-poikkeuksia syötetiedoille. Käyttäjät saattavat käyttää visualisointiasi odottamattomien tietojen eri alueella, joten visualisointi ei saa epäonnistua. Voit käyttää [tätä malliraporttia](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) testitietojoukkona.

* Jos capabilities.json-tiedoston ominaisuuksia muutetaan, varmista, että ne eivät riko olemassa olevan käyttäjän raportteja.

* Varmista, että visualisointi noudattaa [Power BI:n visualisointien ohjeita](./guidelines-powerbi-visuals.md#guidelines-for-power-bi-visuals-with-additional-purchases). **Vesileimoja ei sallita**.

* Visualisointi käyttää vain julkisia, tarkasteltavissa olevia OSS-komponentteja (Julkiset JS-kirjastot tai TypeScript. Lähdekoodi on tarkistettavissa eikä sisällä tunnettuja haavoittuvaisuuksia). Kaupallisia komponentteja käyttäviä mukautettuja visualisointeja ei voi vahvistaa.

* Visualisointi ei käytä ulkoisia palveluita tai resursseja. Power BI:stä ei esimerkiksi lähde HTTP/S- tai WebSocket-pyyntöjä palveluihin. 

> [!TIP]
> Suosittelemme, että esitarkistat koodisi ennen sen lähettämistä käyttämällä EsLint-tarkistusohjelmaa oletusarvoisella suojaussääntöjoukolla.

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>Mukautetun visualisoinnin sertifioitavaksi lähettämisen prosessi

Jos haluat lähettää mukautetun visualisoinnin sertifiointia varten, toimi seuraavasti:

1. Lähetä sähköpostia Power BI:n Power BI -visualisointien tukitiimille (pbicvsupport@microsoft.com). Sisällytä viestiin seuraavat tiedot:
    * Otsikko: Visualisoinnin sertifiointipyyntö
    * Linkki GitHub-säilöön, joka isännöi ihmisen luettavaa lähdekoodia
    * [Vaatimuksien noudattaminen](#certification-requirements)
    * Kooditarkastuksen läpäiseminen

2. Microsoftin Power BI -visualisointien tiimi ilmoittaa, kun mukautettu visualisointi on joko sertifioitu ja lisätty [sertifioitujen luetteloon](#list-of-power-bi-visuals-that-have-been-certified) tai hylätty, jolloin mukana toimitetaan raportti korjattavista ongelmista. On kehittäjän vastuulla pitää yllä avointa viestiyhteyttä Microsoftin kanssa ja päivittää tarvittaessa omat sertifioidut visualisointinsa.

## <a name="list-of-power-bi-visuals-that-have-been-certified"></a>Luettelo Power BI -visualisoinneista, jotka on sertifioitu

| Linkki AppSourceen | Linkki videoon |
| --- | --- |
| [3AG Systems - palkkikaavio, jossa on suhteellinen varianssi](https://appsource.microsoft.com/en/product/power-bi-visuals/WA104381912) | |
| [3AG Systems – pylväskaavio, jossa on suhteellinen varianssi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803) | |
| [Edistynyt rengasvisualisointi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941) | |
| [Edistynyt verkkovisualisointi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942) | |
| [Edistynyt TimeSeries-visualisointi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943) | |
| [Edistynyt yhdistelmävisualisointi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381944) | |
| [Asterikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759) | |
| [Beyondsoft-kalenteri](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096) | |
| [MAQ Softwaren rusettikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838) | [Video](https://youtu.be/So5xKMSpVJI) |
| [Janakuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831) | |
| [MAQ Softwaren janakuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351) | [Video](https://youtu.be/JoHaFLfhXdo) |
| [MAQ Softwaren tiilikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836) | [Video](https://youtu.be/hA3DOsvn2xY) |
| [Akvelonin kuplakaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340) | |
| [Luettelokaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755) | [Video](https://youtu.be/AOlsFYkfkcw) |
| [OKVizin luettelokaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953) | [Video](https://youtu.be/mtvUNl9bMjA) |
| [Tallanin kalenteri](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146) | |
| [OKVizin kynttilänjalkakaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952) | [Video](https://youtu.be/nT_18gyRxPo) |
| [OKVizin tilakortti](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967) | |
| [Chiclet-osittaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756) | |
| [Jänne](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761) | [Video](https://youtu.be/AQvd2FhRyCI) |
| [MAQ Softwaren pyöreä mittari](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837) | [Video](https://youtu.be/9NHXALkBXuY) |
| [Klusterikartta](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806) | |
| [MAQ Softwaren lieriömittari](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | [Video](https://youtu.be/DgdoWi7Gcxo) |
| [Osoitintaulumittari](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) | |
| [Pistekuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760) | |
| [OKVizin pistekuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949) | [Video](https://youtu.be/By16pX9KT40) |
| [Porautuva kartogrammi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045) | |
| [Porautuva koropleettikartta](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044) | |
| [Porautuva pylväskaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857) | [Video](https://youtu.be/lBy2gQQ5YsQ) |
| [Porautuva pylväskaavio aikapohjaisille tiedoille](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881) | [Video](https://youtu.be/T_mRou18vx0) |
| [Porautuva rengaskaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | [Video](https://youtu.be/AUVFrSHmPeo) |
| [Dual KPI ‑kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774) | |
| [MAQ Softwaren dynaaminen työkaluvihje](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983) | [Video](https://youtu.be/Z-tl97BpEr0) |
| [Parannettu pistekaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762) | [Video](https://youtu.be/xCfM0cjM4do) |
| [Enlightenin akvaario](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112) | |
| [Enlightenin osittaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960) | |
| [Enlightenin pinon sekoitus](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849) | |
| [Enlightenin vohvelikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850) | |
| [Devscopen luettelon mukaan suodattaminen](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413) | [Video](https://youtu.be/RetEWGwBu0I) |
| [Voimansuuntainen kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764) | [Video](https://youtu.be/YsTa7uyJ4sg) |
| [MAQ Softwaren suppilokaavio lähteiden kanssa](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334) | [Video](https://youtu.be/R_EcimsLI8U) |
| [Gantt-kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765) | [Video](https://youtu.be/qJ7s_KrGiUU) |
| [MAQ Softwaren Gantt-kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364) | [Video](https://youtu.be/vJLV9JRCpI8) |
| [Maapallon tietopalkit](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344) | |
| [MAQ Softwaren ruudukko](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825) | [Video](https://youtu.be/VOPoDJgZfOY) |
| [Akvelonin hierarkiakaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333) | [Video](https://youtu.be/0ZGzJaq_KT4) |
| [Histogrammikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776) | |
| [MAQ Softwaren histogrammi ja pisteet](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032) | [Video](https://youtu.be/-ILF--wExrw) |
| [MAQ Softwaren vaakasuuntainen suppilokaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) | [Video](https://youtu.be/SudZei68PPo) |
| [CloudScopen kuvanhallinta](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297) | |
| [Kuvaruudukko](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355) | |
| [Infografiikan suunnitteluvisualisointi](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898) | |
| [Akvelonin KPI-kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432) | |
| [MAQ Softwaren KPI-sarake](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996) | [Video](https://youtu.be/rU0xoOlIq1U) |
| [MAQ Softwaren KPI-ruudukko](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947) | [Video](https://youtu.be/dM4PvZh71V0) |
| [KPI-ilmaisin](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832) | |
| [MAQ Softwaren KPI-vaihtaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946) | [Video](https://youtu.be/cudG4gsZ2V8) |
| [MAQ Softwaren palkkimittari](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821) | [Video](https://youtu.be/7_jFaM30dkc) |
| [Viiva-pallokaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766) | |
| [Mekko-kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785) | [Video](https://youtu.be/90FLCKpgicA) |
| [Multi KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763) | |
| [CloudScopen yleiskatsaus](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477) | |
| [Akselin toisto (dynaaminen osittaja)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) | [Video](https://youtu.be/IvfIP3E6-1Q) |
| [Power KPI ‑taulukko](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299) | [Video](https://youtu.be/1enze8pcGzY) |
| [Jaksottainen kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006) | [Video](https://youtu.be/DQWdcQtjDVw) |
| [MAQ Softwaren neljänneskaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011) | [Video](https://youtu.be/ppBnyhqWNC0) |
| [Säteittäinen kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771) | |
| [MAQ Softwaren rengaskaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824) | [Video](https://youtu.be/pDToHDFHnq8) |
| [MAQ Softwaren vaihtuva kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007) | [Video](https://youtu.be/d5xBCMmb3hU) |
| [Sankey](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777) | [Video](https://youtu.be/WWP9wVUHGaA) |
| [Akvelonin pistekaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703) | |
| [Vierivä kuvaaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018) | |
| [OKVizin älykäs suodatin](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859) | [Video](https://youtu.be/gcJsDDRQq28) |
| [OKVizin sparkline-kuvaaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910) | [Video](https://youtu.be/0m3Vnvso9tY) |
| [Purokuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772) | |
| [Auringonsädekaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767) | |
| [OKVizin synoptinen paneeli](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873) | |
| [Lämpökarttataulukko](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818) | |
| [Takometri](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937) | [Video](https://youtu.be/C3OXdETbS9o) |
| [Tekstisuodatin](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309) | |
| [MAQ Softwaren tekstin rivitin](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [MAQ Softwaren lämpömittari](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847) | [Video](https://youtu.be/SPX9mgrAdBc) |
| [Aikasiveltimen osittaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798) | |
| [Aikajanan osittaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786) | [Video](https://youtu.be/ozMtZ4_NZ10) |
| [CloudScopen aikajana](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427) | [Video](https://youtu.be/szNi9YgXFJc) |
| [Tornadokuvaaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768) | [Video](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [MAQ kaupankäyntikuvaaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823) | [Video](https://youtu.be/xhTR6y6J9Ko) |
| [Ylivoimainen varianssikuvaaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140) | [Video](https://youtu.be/pDYF8iZxERs) |
| [Ylivoimainen vesiputouskuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956) | [Video](https://youtu.be/0BZsVCQdEkc) |
| [CloudScopen käyttäjäluettelo](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426) | |
| [Vohvelikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049) | [Video](https://youtu.be/1vRqYUsm3Vk) |
| [Sanapilvi](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752) | [Video](https://youtu.be/AblTenl9fqo) |

## <a name="faq"></a>Usein kysytyt kysymykset

Saat lisätietoja visualisoinneista [sertifioitujen visualisointien usein kysytyistä kysymyksistä](power-bi-custom-visuals-faq.md#certified-power-bi-visuals).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Power BI:n mukautetun visualisoinnin kehittäminen](../developer/custom-visual-develop-tutorial.md)
* [Microsoftin mukautettujen visualisointien soittoluettelo YouTubessa](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Visualisoinnit Power BI:ssä](../visuals/power-bi-report-visualizations.md)  
* [Mukautetut visualisoinnit Power BI:ssä](power-bi-custom-visuals.md)  
* [Power BI -visualisointien julkaiseminen Microsoft AppSourcessa](../developer/office-store.md)  

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)