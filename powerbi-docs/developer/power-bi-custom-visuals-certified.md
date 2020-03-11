---
title: Sertifioidut Power BI -visualisoinnit
description: Mukautetun visualisoinnin sertifioinnin edellytykset ja lähettämisprosessi, lisäksi luettelo sertifioiduista Power BI -visualisoinneista.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 03/01/2020
ms.openlocfilehash: 8aea9041665de69b2c5be954dc8f13a6402a06e0
ms.sourcegitcommit: d55d3089fcb3e78930326975957c9940becf2e76
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260757"
---
# <a name="get-a-power-bi-visual-certified"></a>Sertifioinnin hankkiminen Power BI -visualisoinnille

Sertifioidut Power BI -visualisoinnit ovat [AppSourcessa](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals) sijaitsevia Power BI -visualisointeja, jotka täyttävät Power BI -tiimin [koodivaatimukset](#certification-requirements). Nämä visualisoinnit testataan sen todentamiseksi, etteivät ne käytä ulkoisia palveluita eivätkä resursseja ja että ne seuraavat turvallisia koodausmalleja ja ohjeita.

Kun Power BI -visualisointi on sertifioitu, se tarjoaa lisää ominaisuuksia. Voit esimerkiksi [viedä sisältöä PowerPointiin](../consumer/end-user-powerpoint.md) tai näyttää visualisoinnin [raporttisivujen tilaamisen](../consumer/end-user-subscribe.md) yhteydessä lähetettävissä sähköposteissa.

Sertifiointimenettely on valinnainen. Sertifioimattomat Power BI -visualisoinnit eivät välttämättä ole turvallisuudelle vaarallisia Power BI -visualisointeja. Jotkin Power BI -visualisoinnit eivät ole sertifioituja, koska ne eivät täytä yhtä tai useampaa [sertifiointivaatimusta](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Esimerkkejä voivat olla Power BI -karttavisualisointi, joka on yhteydessä ulkoiseen palveluun, tai kaupallisia kirjastoja hyödyntävä Power BI -visualisointi.

> [!NOTE]
> Microsoft ei ole kolmannen osapuolen Power BI ‑visualisointien tekijä. Kolmannen osapuolen visualisointien toiminnallisuuden todentamiseksi on otettava suoraan yhteyttä visualisoinnin tekijään.

## <a name="certification-requirements"></a>Sertifioinnin edellytykset

Jos haluat hankkia Power BI -visualisoinnillesi [sertifioinnin](#get-a-power-bi-visual-certified), Power BI -visualisointisi on oltava tässä osiossa lueteltujen vaatimusten mukainen. 

### <a name="general-requirements"></a>Yleiset vaatimukset

Power BI visualisoinnin on oltava myyjän koontinäytön tai kumppanikeskuksen hyväksymä. On suositeltavaa, että Power BI -visualisointisi on jo [AppSourcessa](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals). Katso lisätietoja Power BI -visualisoinnin julkaisemisesta AppSourcessa artikkelista [Power BI -visualisointien julkaiseminen kumppanikeskuksessa](office-store.md).

Ennen kuin lähetät Power BI -visualisoinnin sertifioitavaksi, varmista,että se noudattaa [Power BI -visualisointien ohjeita](./guidelines-powerbi-visuals.md).

Kun lähetät Power BI -visualisointia, varmista, että käännetty paketti vastaa tarkasti lähetettyä pakettia.

### <a name="code-repository-requirements"></a>Koodisäilön vaatimukset

Vaikka sinun ei tarvitse julkisesti jakaa koodiasi GitHubissa, koodisäilön on oltava saatavilla Power BI -tiimin tarkistettavaksi. Paras tapa tehdä tämä on toimittamalla lähdekoodi (JavaScript tai TypeScript) GitHubissa.

Säilön on sisällettävä seuraavat:
* Koodi vain yhdelle Power BI -visualisoinnille. Se ei saa sisältää useiden Power BI -visualisointien koodia eikä asiaan liittymätöntä koodia.
* Haara, jonka nimi on **sertifiointi** (pieni alkukirjain pakollinen). Tämän haaran lähdekoodin on vastattava lähetettyä pakettia. Tätä koodia saa päivittää vain seuraavan lähetysmenettelyn yhteydessä, jos olet lähettämässä Power BI -visualisointisi uudelleen.

Jos Power BI -visualisointisi käyttää yksityisiä NPM-paketteja tai git-alityyppejä, sinun on järjestettävä käyttöoikeus tämän koodin sisältäviin lisäsäilöihin.

Jos haluat tietää, miltä Power BI -visualisointisäilö näyttää, tarkastele [Power BI -visualisointien esimerkkipalkkikaavion](https://github.com/microsoft/PowerBI-visuals-sampleBarChartgi) GitHub-säilöä.

### <a name="file-requirements"></a>Tiedostovaatimukset

Käytä ohjelmointirajapinnan viimeisintä versiota Power BI -visualisoinnin kirjoittamiseen.

Säilön on sisällettävä seuraavat tiedostot:
* **.gitignore** - Lisää `node_modules`, `.tmp`, `dist` tähän tiedostoon. Koodi ei voi sisältää *node_modules*-, *.tmp*- tai *dist*-kansioita.
* **capabilities.json** - Jos olet lähettämässä uutta versiota Power BI -visualisoinnistasi ja siihen kuuluu tämän tiedoston ominaisuuksiin liittyviä muutoksia, varmista, että ne eivät ole ristiriidassa olemassa olevien käyttäjien raporttien kanssa.
* **pbiviz.json** 
* **package.json**. Visualisoinnissa on oltava asennettuna seuraava paketti:
   * [tslint](https://www.npmjs.com/package/tslint): 5.18.0 tai uudempi
   * [typescript](https://www.npmjs.com/package/typescript): 3.0.0 tai uudempi
   * [tslint-microsoftcontrib](https://www.npmjs.com/package/tslint-microsoft-contrib): 6.2.0 tai uudempi
   * Tiedoston on sisällettävä komento lint-toiminnon suorittamiseen:  lint: tslint -c tslint.json -p tsconfig.json
* **package-lock.json**
* **tsconfig.json**

### <a name="command-requirements"></a>Komentovaatimukset

Varmista, että seuraavat komennot eivät palauta mitään virheitä.

* `npm install`
* `pbiviz package`
* `npm audit` - Ei saa palauttaa korkean tai kohtalaisen tason varoituksia.
* [TSlint Microsoftilta](https://www.npmjs.com/package/tslint-microsoft-contrib) ja [vaadittu määritys](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/master/tslint.json). Tämä komento ei saa palauttaa mitään lint-virheitä.

### <a name="compiling-requirements"></a>Kääntämisvaatimukset

Käytä viimeisintä [powerbi-visuals-tools](https://www.npmjs.com/package/powerbi-visuals-tools)-versiota Power BI -visualisoinnin kirjoittamiseen.

Sinun on käännettävä Power BI -visualisointisi apunasi `pbiviz package`. Jos käytät omia koontikomentosarjojasi, järjestä mukautettu `npm run package`-koontikomento.



### <a name="source-code-requirements"></a>Lähdekoodivaatimukset

Varmista, että noudatat [Power BI -visualisointien lisäsertifioinnin](https://docs.microsoft.com/legal/marketplace/certification-policies#1200-power-bi-visuals-additional-certification) käytäntöjen luetteloa. Jos lähetyksesi ei noudata näitä ohjeita, kumppanikeskuksen hylkäyssähköpostiviesti sisältää tässä linkissä luetteloidut käytäntöjen numerot.

Noudata alla lueteltuja koodivaatimuksia sen varmistamiseksi, että koodisi on Power BI -sertifiointikäytäntöjen mukainen.  

**Pakollista**
* Käytä vain julkisesti tarkistettavissa olevia OSS-komponentteja, kuten julkisia JavaScript- tai TypeScript-kirjastoja.
* Koodin on tuettava [Tapahtumien hahmontaminen -ohjelmointirajapintaa](./visuals/event-service.md).
* Varmista, että DOM-objektia manipuloidaan luotettavasti. Käytä sanitaatiota käyttäjän syötteessä tai käyttäjätiedoissa, ennen kuin lisäät sen DOM-objektiin.
* Käytä tätä [malliraporttia](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) testitietojoukkona.

**Ei sallittua**
* Ulkoisten palvelujen tai resurssien käyttö. Power BI:stä ei esimerkiksi lähde HTTP/S- tai WebSocket-pyyntöjä palveluihin.
* Kohteiden `innerHTML` tai `D3.html(user data or user input)` käyttäminen.
* Selainkonsolissa olevat JavaScript-virheet tai -poikkeukset syötetiedoille.
* Mielivaltainen tai dynaaminen koodi, kuten `eval()`, kohteen `settimeout()` suojaamaton käyttö, `requestAnimationFrame()`, `setinterval(user input function)` ja käyttäjän syöte tai käyttäjän tiedot.
* Minified JavaScript -tiedostot tai -projektit.

## <a name="submitting-a-power-bi-visual-for-certification"></a>Power BI -visualisoinnin lähettäminen sertifioitavaksi

Voit pyytää, että Power BI -tiimi sertifioi Power BI -visualisointisi kumppanikeskuksen kautta.

>[!TIP]
>Power BI:n sertifiointiprosessi saattaa kestää jonkin aikaa. Jos olet luomassa uutta Power BI -visualisointia, suosittelemme sinua julkaisemaan Power BI -visualisointisi kumppanikeskuksen kautta, ennen kuin pyydät Power BI -sertifiointia. Näin varmistat sen, ettei visualisointisi julkaiseminen viivästy.

Power BI -sertifioinnin pyytäminen:

1. Kirjaudu sisään kumppanikeskukseen.
2. Valitse **Yleiskatsaus-sivulla**Power BI -visualisointi, ja siirry **Tuotteen asennus** -sivulle.
3. Valitse **Pyydä Power BI -sertifiointia** -valintaruutu.
4. Anna **Tarkista ja julkaise** -sivun **Sertifiointia koskevat huomautukset** -tekstiruutuun linkki lähdekoodiin ja sen käyttämiseen tarvittavat tunnistetiedot.

>[!NOTE]
> Jos Power BI -visualisoinnin lähettämisprosessi on kesken ja sinun on käytettävä [myyjän koontinäyttöä](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store) (vanhaa hallintatyökalua), katso ohjeet kohdasta [Myyjän koontinäytön sertifioinnin lähettämisprosessi](seller-dashboard.md#seller-dashboard-certification-submission-process).

### <a name="private-repository-submission-process"></a>Yksityisen säilön lähettämisprosessi

Jos käytät yksityistä säilöä, kuten GitHub-säilöä, joka lähettää Power BI -visualisoinnin varmentamista varten, noudata tämän osan ohjeita.
1. Luo uusi tili vahvistustiimiä varten.
2. Määritä tiliisi [kaksivaiheinen todentaminen](https://help.github.com/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa).
3. [Luo uusi palautuskoodijoukko](https://help.github.com/github/authenticating-to-github/configuring-two-factor-authentication-recovery-methods#generating-a-new-set-of-recovery-codes).
4. Kun lähetät Power BI -visualisoinnin, anna seuraavat tiedot:
    * Linkki säilöön
    * Kirjautumisen tunnistetiedot (salasana mukaan lukien)
    * Palautuskoodit
    * Vain luku -oikeudet tiliimme ([pbidvsupport](https://github.com/pbicvsupport))

## <a name="certified-power-bi-visuals"></a>Sertifioidut Power BI -visualisoinnit

Sertifioidut Power BI -visualisoinnit on lueteltu seuraavassa. Avaa Power BI -visualisointi Appsourceen napsauttamalla linkkiä. Jos käytettävissä on video, voit katsoa sen napsauttamalla videon linkkiä.

* [3AG Systems - palkkikaavio, jossa on suhteellinen varianssi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381802)
*  [3AG Systems - palkkikaavio, jossa on suhteellinen varianssi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381912)
*  [3AG Systems – pylväskaavio, jossa on suhteellinen varianssi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803)
*  [3AG Systems – pylväskaavio, jossa on suhteellinen varianssi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381724)
* [Edistynyt rengasvisualisointi (täysi versio)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941)
*  [Edistynyt rengasvisualisointi (kevyt versio)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858)
*  [Edistynyt kaaviovisualisointi](https://appsource.microsoft.com/product/power-bi-visuals/WA104382086)
*  [Edistynyt verkkovisualisointi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942)
*  [Edistynyt TimeSeries-visualisointi (täysi versio)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943)
*  [Asterikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759)
*  [Beyondsoft-kalenteri](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096)
*  [MAQ Softwaren rusettikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838)
*  [Janakuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831)
* [MAQ Softwaren janakuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351)
*  [MAQ Softwaren tiilikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836)
*  [Akvelonin kuplakaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340)
*  [Luettelokaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755), **[videolinkki](https://youtu.be/AOlsFYkfkcw)**
* [Luettelokaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755)
*  [OKVizin luettelokaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953), **[videolinkki](https://youtu.be/mtvUNl9bMjA)**
* [MAQ Softwaren kalenteri](https://appsource.microsoft.com/product/power-bi-visuals/WA104381844)
*  [Tallanin kalenteri](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146)
*  [OKVizin kynttilänjalkakaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952), **[videolinkki](https://youtu.be/nT_18gyRxPo)**
*  [OKVizin tilakortti](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967)
*  [Chiclet-osittaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756)
*  [Jännekaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761), **[videolinkki](https://youtu.be/AQvd2FhRyCI)**
*  [MAQ Softwaren pyöreä mittari](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837)
*  [Klusterikartta](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806)
* [Akvelonin mukautettu kalenteri](https://appsource.microsoft.com/product/power-bi-visuals/WA104381179)
* [MAQ Softwaren lieriömittari](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874)
*  [Osoitintaulumittari](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184)
[Pistekaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760)
*  [OKVizin pistekaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949), **[videolinkki](https://youtu.be/By16pX9KT40)**
*  [Porautuva kartogrammi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045)
*  [Porautuva koropleettikartta](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044)
*  [Porautuva pylväskaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857), **[videolinkki](https://youtu.be/lBy2gQQ5YsQ)**
*  [Porautuva pylväskaavio aikapohjaisille tiedoille](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881), **[videolinkki](https://youtu.be/T_mRou18vx0)**
*  [Porautuva rengaskaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858), **[videolinkki](https://youtu.be/AUVFrSHmPeo)**
*  [Dual KPI ‑kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774)
*  [MAQ Softwaren dynaaminen työkaluvihje](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983)
*  [Parannettu pistekaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762) **[videolinkki](https://youtu.be/xCfM0cjM4do)**
*  [Enlightenin akvaario](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112)
*  [Enlightenin osittaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960)
*  [Enlightenin pinon sekoitus](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849)
*  [Enlightenin vohvelikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850)
*  [Devscopen luettelon mukaan suodattaminen](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413), **[videolinkki](https://youtu.be/RetEWGwBu0I)**
*  [Voimasuuntainen kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764), **[videolinkki](https://youtu.be/YsTa7uyJ4sg)**
*  [MAQ Softwaren suppilokaavio lähteiden kanssa](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334)
*  [Gantt](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765), **[videolinkki](https://youtu.be/qJ7s_KrGiUU)**
* [MAQ Softwaren Gantt-kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364)
*  [Maapallon tietopalkit](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344)
*  [MAQ Softwaren ruudukko](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825)
*  [Akvelonin hierarkiakaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333), **[videolinkki](https://youtu.be/0ZGzJaq_KT4)**
*  [Histogrammikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776)
*  [MAQ Softwaren histogrammi ja pisteet](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032)
* [Vaakasuuntainen palkkikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381230)
*  [MAQ Softwaren vaakasuuntainen suppilokaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846)
*  [CloudScopen kuvanhallinta](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297)
*  [Kuvaruudukko](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355)
*  [Infografiikan suunnitteluvisualisointi](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898)
*  [Akvelonin KPI-kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432)
*  [MAQ Softwaren KPI-sarake](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996)
*  [MAQ Softwaren KPI-ruudukko](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947)
*  [KPI-ilmaisin](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832)
*  [MAQ Softwaren KPI-vaihtaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946)
* [MAQ Softwaren palkkimittari](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821)
*  [Viiva-pallokaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766)
*  [Mekko-kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785), **[videolinkki](https://youtu.be/90FLCKpgicA)**
*  [Multi KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763)
*  [CloudScopen yleiskatsaus](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477)
*  [Akselin toisto (dynaaminen osittaja)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981)
*  [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083), [videolinkki](https://youtu.be/IvfIP3E6-1Q)
*  [Power KPI Matrix](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299), **[videolinkki](https://youtu.be/1enze8pcGzY)**
*  [Jaksottainen kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006), **[videolinkki](https://youtu.be/DQWdcQtjDVw)**
*  [MAQ Softwaren neljänneskaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011)
*  [Säteittäinen kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771)
*  [MAQ Softwaren rengaskaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824)
*  [MAQ Softwaren vaihtuva kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007)
*  [Sankey-kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777), **[videolinkki](https://youtu.be/WWP9wVUHGaA)**
*  [Akvelonin pistekaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703)
*  [Vierivä kuvaaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018)
*  [OKVizin älykäs suodatin](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859), **[videolinkki](https://youtu.be/gcJsDDRQq28)**
*  [OKVizin sparkline-kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910), **[videolinkki](https://youtu.be/0m3Vnvso9tY)**
*  [Purokuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772)
*  [Auringonsädekaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767)
*  [OKVizin synoptinen paneeli](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873)
*  [Lämpökarttataulukko](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818)
*  [Takometri](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937), **[videolinkki](https://youtu.be/C3OXdETbS9o)**
*  [Tekstisuodatin](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309)
*  [MAQ Softwaren tekstin rivitin](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826)
*  [MAQ Softwaren lämpömittari](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847)
*  [Aikasiveltimen osittaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798)
*  [Aikajanan osittaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786), **[videolinkki](https://youtu.be/ozMtZ4_NZ10)**
*  [CloudScopen aikajana](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427), [videolinkki](https://youtu.be/szNi9YgXFJc)
*  [Tornadokaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768), **[videolinkki](https://www.youtube.com/watch?v=AQvd2FhRyCI)**
*  [MAQ kaupankäyntikuvaaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823)
* [Ultimate KPI Card](https://appsource.microsoft.com/product/power-bi-visuals/WA104381977)
*  [Ylivoimainen varianssikuvaaja](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140), **[videolinkki](https://youtu.be/pDYF8iZxERs)**
*  [Ylivoimainen vesiputouskuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956), **[videolinkki](https://youtu.be/0BZsVCQdEkc)**
*  [CloudScopen käyttäjäluettelo](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426)
*  [MAQ Softwaren Venn-kaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381231)
*  [Viulukuvio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381947)
*  [Vision visualisointi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381132)
*  [Vohvelikaavio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049), **[videolinkki](https://youtu.be/1vRqYUsm3Vk)**
*  [Sanapilvi](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752), **[videolinkki](https://youtu.be/AblTenl9fqo)**

## <a name="faq"></a>Usein kysytyt kysymykset

Saat lisätietoja visualisoinneista [sertifioitujen visualisointien usein kysytyistä kysymyksistä](power-bi-custom-visuals-faq.md#certified-power-bi-visuals).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Power BI:n mukautetun visualisoinnin kehittäminen](../developer/custom-visual-develop-tutorial.md)
* [Microsoftin mukautettujen visualisointien soittoluettelo YouTubessa](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Visualisoinnit Power BI:ssä](../visuals/power-bi-report-visualizations.md)  
* [Mukautetut visualisoinnit Power BI:ssä](power-bi-custom-visuals.md)  
* [Power BI -visualisointien julkaiseminen Microsoft AppSourcessa](../developer/office-store.md) 
* Jos olet web-kehittäjä, joka on kiinnostunut omien Power BI -visualisointien luomisesta ja niiden lisäämisestä  [Microsoft AppSourceen](https://appsource.microsoft.com), aloita  [Power BI -visualisoinnin kehittäminen](visuals/custom-visual-develop-tutorial.md) -opetusohjelmasta. 

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
