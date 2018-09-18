---
title: Power BI:n sertifioidut mukautetut visualisoinnit
description: Mukautetun visualisoinnin sertifioinnin edellytykset ja lähettämisprosessi. Lisäksi luettelo jo sertifioiduista mukautetuista visualisoinneista.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: mihart
ms.openlocfilehash: 4676b31a117573d1d69b5947ec2380c4abf29405
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/12/2018
ms.locfileid: "44726865"
---
# <a name="getting-a-custom-visual-certified"></a>Mukautetun visualisoinnin *sertifioinnin* hankkiminen
## <a name="what-is-meant-by-certified"></a>Mitä *sertifioinnilla* tarkoitetaan?
*Sertifioidun mukautetun visualisoinnin* koodi on täyttänyt joukon vaatimuksia ja läpäissyt tiukat tietoturvatestit.  Kun mukautettu visualisointi on sertifioitu, sen voi [viedä PowerPointiin](service-publish-to-powerpoint.md) ja näyttää sähköpostiviesteissä, kun käyttäjä [tilaa raporttisivut](service-report-subscribe.md) sähköpostitse. Lisäksi sitä voi tietysti käyttää samalla tavalla kuin [tavanomaisia mukautettuja visualisointeja](power-bi-custom-visuals.md), lisätä sen Power BI -palvelun ja Power BI Desktopin raportteihin sekä tarkastella sitä Power BI:n mobiiliversiossa ja upotettuna.

Oletko Web-kehittäjä ja kiinnostunut omien visualisointien luomisesta ja niiden lisäämisestä [Microsoft AppSourceen](https://appsource.microsoft.com)? Katso ohjeet artikkelista [Sovelluskehittäjätyökalujen käytön aloittaminen](service-custom-visuals-getting-started-with-developer-tools.md).


## <a name="certification-requirements"></a>Sertifioinnin edellytykset
* Microsoft AppSource ‑hyväksyntä    
* Mukautettu visualisointi on kirjoitettu Versioned-ohjelmointirajapinnan versiolla 1.2 tai uudemmalla versiolla    
* Koodisäilö on saatavilla arviointia varten (esim. visualisoinnin koodi annetaan käytettäväksemme GitHubin kautta)    
* Käyttää vain julkisia, tarkasteltavissa olevia OSS-komponentteja    
* Ei käytä ulkoisia palveluita tai resursseja    

> **Vinkki**: Suosittelemme, että esitarkistat koodisi ennen sen lähettämistä käyttämällä EsLint-tarkistusohjelmaa suojauksen oletusarvoisella sääntöjoukolla.
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>Mukautetun visualisoinnin sertifioitavaksi lähettämisen prosessi
Jos haluat lähettää mukautetun visualisoinnin sertifiointia varten, toimi seuraavasti:

1. Lähetä sähköpostia Power BI:n mukautettujen visualisointien tukeen (pbicvsupport@microsoft.com). Sisällytä viestiin seuraavat tiedot:    

   * Otsikko: Visual Certification Request    
   * Linkki GitHub-säilöön, joka isännöi visualisoinnin lähdekoodia    
   * Edellä mainittujen vaatimuksien noudattaminen    
   * Koodin ja tietoturvan tarkistuksen läpäiseminen    

2. Microsoftin Mukautettujen visualisointien tiimi ilmoittaa, kun mukautettu visualisointi on sertifioitu ja lisätty sertifioitujen luetteloon (alla) tai hylätty, jolloin mukana toimitetaan raportti korjattavista ongelmista. On kehittäjän vastuulla pitää yllä avointa viestiyhteyttä Microsoftin kanssa ja päivittää tarvittaessa omat sertifioidut visualisointinsa.

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Sertifioitujen mukautettujen Power BI ‑visualisointien poistaminen
Microsoft saattaa harkintansa mukaan poistaa visualisoinnin sertifioitujen luettelosta.  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>Luettelo mukautetuista visualisoinneista, jotka on sertifioitu

| Linkki AppSourceen | Linkki videoon |
| --- | --- |
| [Asterikaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759) | |
| [Beyondsoft-kalenteri](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096) | |
| [MAQ Softwaren rusettikaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380838) | [Video](https://youtu.be/So5xKMSpVJI) |
| [Janakuvio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380831) | |
| [MAQ Softwaren janakuvio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381351) | [Video](https://youtu.be/JoHaFLfhXdo) |
| [MAQ Softwaren tiilikaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | [Video](https://youtu.be/hA3DOsvn2xY) |
| [Akvelonin kuplakaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340) | |
| [Luettelokaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380755) | [Video](https://youtu.be/AOlsFYkfkcw) |
| [OKVizin luettelokaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380953) | [Video](https://youtu.be/mtvUNl9bMjA) |
| [Tallanin kalenteri](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381146) | |
| [OKVizin kynttilänjalkakaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | [Video](https://youtu.be/nT_18gyRxPo) |
| [OKVizin tilakortti](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380967) | |
| [Chiclet-osittaja](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380756) | |
| [Jänne](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380761) | [Video](https://youtu.be/AQvd2FhRyCI) |
| [MAQ Softwaren pyöreä mittari](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380837) | [Video](https://youtu.be/9NHXALkBXuY) |
| [Klusterikartta](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380806) | |
| [MAQ Softwaren lieriömittari](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | [Video](https://youtu.be/DgdoWi7Gcxo) |
| [Osoitintaulumittari](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) | |
| [Pistekuvio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760) | |
| [OKVizin pistekuvio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380949) | [Video](https://youtu.be/By16pX9KT40) |
| [Porautuva kartogrammi](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045) | |
| [Porautuva koropleettikartta](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044) | |
| [Porautuva pylväskaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380857) | [Video](https://youtu.be/lBy2gQQ5YsQ) |
| [Porautuva pylväskaavio aikapohjaisille tiedoille](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | [Video](https://youtu.be/T_mRou18vx0) |
| [Porautuva rengaskaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | [Video](https://youtu.be/AUVFrSHmPeo) |
| [Dual KPI ‑kaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380774) | |
| [MAQ Softwaren dynaaminen työkaluvihje](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380983) | [Video](https://youtu.be/Z-tl97BpEr0) |
| [Parannettu pistekaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | [Video](https://youtu.be/xCfM0cjM4do) |
| [Enlightenin akvaario](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381112) | |
| [Enlightenin osittaja](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960) | |
| [Enlightenin pinon sekoitus](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlightenin vohvelikaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Voimansuuntainen kaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) | [Video](https://youtu.be/YsTa7uyJ4sg) |
| [MAQ Softwaren suppilokaavio lähteiden kanssa](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381334) | [Video](https://youtu.be/R_EcimsLI8U) |
| [Gantt-kaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380765) | [Video](https://youtu.be/qJ7s_KrGiUU) |
| [MAQ Softwaren Gantt-kaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381364) | [Video](https://youtu.be/vJLV9JRCpI8) |
| [Maapallon tietopalkit](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381344) | |
| [MAQ Softwaren ruudukko](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380825) | [Video](https://youtu.be/VOPoDJgZfOY) |
| [Akvelonin hierarkiakaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333) | [Video](https://youtu.be/0ZGzJaq_KT4) |
| [Histogrammikaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380776) | |
| [MAQ Softwaren histogrammi ja pisteet](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381032) | [Video](https://youtu.be/-ILF--wExrw) |
| [MAQ Softwaren vaakasuuntainen suppilokaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) | [Video](https://youtu.be/SudZei68PPo) |
| [CloudScopen kuvanhallinta](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381297) | |
| [Kuvaruudukko](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381355) | |
| [Infografiikan suunnitteluvisualisointi](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898) | |
| [Akvelonin KPI-kaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381432) | |
| [MAQ Softwaren KPI-sarake](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380996) | [Video](https://youtu.be/rU0xoOlIq1U) |
| [MAQ Softwaren KPI-ruudukko](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380947) | [Video](https://youtu.be/dM4PvZh71V0) |
| [KPI-ilmaisin](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380832) | |
| [MAQ Softwaren KPI-vaihtaja](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | [Video](https://youtu.be/cudG4gsZ2V8) |
| [MAQ Softwaren palkkimittari](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821) | [Video](https://youtu.be/7_jFaM30dkc) |
| [Viiva-pallokaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766) | |
| [Mekko-kaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380785) | [Video](https://youtu.be/90FLCKpgicA) |
| [CloudScopen yleiskatsaus](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381477) | |
| [Akselin toisto (dynaaminen osittaja)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380981) | |
| [Power KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381083) | [Video](https://youtu.be/IvfIP3E6-1Q) |
| [Power KPI ‑taulukko](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381299) | [Video](https://youtu.be/1enze8pcGzY) |
| [Jaksottainen kaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | [Video](https://youtu.be/DQWdcQtjDVw) |
| [MAQ Softwaren neljänneskaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381011) | [Video](https://youtu.be/ppBnyhqWNC0) |
| [Säteittäinen kaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380771) | |
| [MAQ Softwaren rengaskaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) | [Video](https://youtu.be/pDToHDFHnq8) |
| [MAQ Softwaren vaihtuva kaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007) | [Video](https://youtu.be/d5xBCMmb3hU) |
| [Sankey](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380777) | [Video](https://youtu.be/WWP9wVUHGaA) |
| [Vierivä kuvaaja](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381018) | |
| [OKVizin älykäs suodatin](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380859) | [Video](https://youtu.be/gcJsDDRQq28) |
| [OKVizin sparkline-kuvaaja](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910) | [Video](https://youtu.be/0m3Vnvso9tY) |
| [Purokuvio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772) | |
| [Auringonsädekaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767) | |
| [OKVizin synoptinen paneeli](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380873) | |
| [Lämpökarttataulukko](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380818) | |
| [Takometri](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380937) | [Video](https://youtu.be/C3OXdETbS9o) |
| [Tekstisuodatin](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381309) | |
| [MAQ Softwaren tekstin rivitin](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [MAQ Softwaren lämpömittari](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380847) | [Video](https://youtu.be/SPX9mgrAdBc) |
| [Aikasiveltimen osittaja](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380798) | |
| [Aikajanan osittaja](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380786) | [Video](https://youtu.be/ozMtZ4_NZ10) |
| [CloudScopen aikajana](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381427) | [Video](https://youtu.be/szNi9YgXFJc) |
| [Tornadokuvaaja](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380768) | [Video](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [MAQ kaupankäyntikuvaaja](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380823) | [Video](https://youtu.be/xhTR6y6J9Ko) |
| [Ylivoimainen varianssikuvaaja](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140) | [Video](https://youtu.be/pDYF8iZxERs) |
| [Ylivoimainen vesiputouskuvio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | [Video](https://youtu.be/0BZsVCQdEkc) |
| [CloudScopen käyttäjäluettelo](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381426) | |
| [Vohvelikaavio](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049) | [Video](https://youtu.be/1vRqYUsm3Vk) |
| [Sanapilvi](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380752) | [Video](https://youtu.be/AblTenl9fqo) |

## <a name="next-steps"></a>Seuraavat vaiheet
[Mukautettujen visualisointien kehittäjätyökalujen käytön aloittaminen (esikatselu)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Microsoftin mukautettujen visualisointien soittoluettelo YouTubessa](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Visualisoinnit Power BI:ssä](visuals/power-bi-report-visualizations.md)  
[Mukautetut visualisoinnit Power BI:ssä](power-bi-custom-visuals.md)  
[Mukautettujen visualisointien julkaiseminen Microsoft AppSourcessa](developer/office-store.md)  
Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

