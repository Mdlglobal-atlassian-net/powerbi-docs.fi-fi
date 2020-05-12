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
ms.date: 03/08/2020
ms.openlocfilehash: b759d19046ddb375646743a50025689ab9a566c0
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82613530"
---
# <a name="get-a-power-bi-visual-certified"></a>Sertifioinnin hankkiminen Power BI -visualisoinnille

Sertifioidut Power BI -visualisoinnit ovat [AppSourcessa](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals) sijaitsevia Power BI -visualisointeja, jotka täyttävät Power BI -tiimin [koodivaatimukset](#certification-requirements). Nämä visualisoinnit testataan sen todentamiseksi, etteivät ne käytä ulkoisia palveluita eivätkä resursseja ja että ne seuraavat turvallisia koodausmalleja ja ohjeita.

Kun Power BI -visualisointi on sertifioitu, se tarjoaa lisää ominaisuuksia. Voit esimerkiksi [viedä sisältöä PowerPointiin](../../consumer/end-user-powerpoint.md) tai näyttää visualisoinnin [raporttisivujen tilaamisen](../../consumer/end-user-subscribe.md) yhteydessä lähetettävissä sähköposteissa.

Sertifiointimenettely on valinnainen. Sertifioimattomat Power BI -visualisoinnit eivät välttämättä ole turvallisuudelle vaarallisia Power BI -visualisointeja. Jotkin Power BI -visualisoinnit eivät ole sertifioituja, koska ne eivät täytä yhtä tai useampaa [sertifiointivaatimusta](power-bi-custom-visuals-certified.md#certification-requirements). Esimerkkejä voivat olla Power BI -karttavisualisointi, joka on yhteydessä ulkoiseen palveluun, tai kaupallisia kirjastoja hyödyntävä Power BI -visualisointi.

> [!NOTE]
> Microsoft ei ole kolmannen osapuolen Power BI ‑visualisointien tekijä. Kolmannen osapuolen visualisointien toiminnallisuuden todentamiseksi on otettava suoraan yhteyttä visualisoinnin tekijään.

## <a name="certification-requirements"></a>Sertifioinnin edellytykset

Jos haluat hankkia Power BI -visualisoinnillesi [sertifioinnin](#get-a-power-bi-visual-certified), Power BI -visualisointisi on oltava tässä osiossa lueteltujen vaatimusten mukainen. 

### <a name="general-requirements"></a>Yleiset vaatimukset

Power BI visualisoinnin on oltava kumppanikeskuksen hyväksymä. On suositeltavaa, että Power BI -visualisointisi on jo [AppSourcessa](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals). Katso lisätietoja Power BI -visualisoinnin julkaisemisesta AppSourcessa artikkelista [Power BI -visualisointien julkaiseminen kumppanikeskuksessa](office-store.md).

Ennen kuin lähetät Power BI -visualisoinnin sertifioitavaksi, varmista,että se noudattaa [Power BI -visualisointien ohjeita](guidelines-powerbi-visuals.md).

Kun lähetät Power BI -visualisointia, varmista, että käännetty paketti vastaa tarkasti lähetettyä pakettia.

### <a name="code-repository-requirements"></a>Koodisäilön vaatimukset

Vaikka sinun ei tarvitse julkisesti jakaa koodiasi GitHubissa, koodisäilön on oltava saatavilla Power BI -tiimin tarkistettavaksi. Paras tapa tehdä tämä on toimittamalla lähdekoodi (JavaScript tai TypeScript) GitHubissa.

Säilön on sisällettävä seuraavat:
* Koodi vain yhdelle Power BI -visualisoinnille. Se ei saa sisältää useiden Power BI -visualisointien koodia eikä asiaan liittymätöntä koodia.
* Haara, jonka nimi on **sertifiointi** (pieni alkukirjain pakollinen). Tämän haaran lähdekoodin on vastattava lähetettyä pakettia. Tätä koodia saa päivittää vain seuraavan lähetysmenettelyn yhteydessä, jos olet lähettämässä Power BI -visualisointisi uudelleen.

Jos Power BI -visualisointisi käyttää yksityisiä NPM-paketteja tai git-alityyppejä, sinun on järjestettävä käyttöoikeus tämän koodin sisältäviin lisäsäilöihin.

Jos haluat tietää, miltä Power BI -visualisointisäilö näyttää, tarkastele [Power BI -visualisointien esimerkkipalkkikaavion](https://github.com/microsoft/PowerBI-visuals-sampleBarChart) GitHub-säilöä.

### <a name="file-requirements"></a>Tiedostovaatimukset

Käytä ohjelmointirajapinnan viimeisintä versiota Power BI -visualisoinnin kirjoittamiseen.

Säilön on sisällettävä seuraavat tiedostot:
* **.gitignore**: lisää `node_modules`, `.tmp` ja  `dist` tähän tiedostoon. Koodi ei voi sisältää *node_modules*-, *.tmp*- tai *dist*-kansioita.
* **capabilities.json** - Jos olet lähettämässä uutta versiota Power BI -visualisoinnistasi ja siihen kuuluu tämän tiedoston ominaisuuksiin liittyviä muutoksia, varmista, että ne eivät ole ristiriidassa olemassa olevien käyttäjien raporttien kanssa.
* **pbiviz.json** 
* **package.json**. Visualisoinnissa on oltava asennettuna seuraava paketti:
   * ["tslint"](https://www.npmjs.com/package/tslint): versio 5.18.0 tai uudempi
   * ["typescript"](https://www.npmjs.com/package/typescript): versio 3.0.0 tai uudempi
   * ["tslint-microsoftcontrib"](https://www.npmjs.com/package/tslint-microsoft-contrib): versio 6.2.0 tai uudempi.
   * Tiedoston täytyy sisältää komento seuraavan suorittamiseksi: linter -  `"lint": "tslint -c tslint.json -p tsconfig.json"`
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
* Koodin on tuettava [Tapahtumien hahmontaminen -ohjelmointirajapintaa](event-service.md).
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

## <a name="certified-power-bi-visual-badges"></a>Sertifioitujen Power BI -visualisointien merkit

Kun Power BI -visualisointi sertifioidaan, se saa merkin tästä.

### <a name="certified-power-bi-visuals-in-appsource"></a>Sertifioidut Power BI -visualisoinnit AppSourcessa

* Kun haet [Power BI -visualisointeja verkossa AppSourcessa](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals), pieni keltainen merkki visualisoinnin kortissa ilmaisee sitä, että se on sertifioitu Power BI -visualisointi.

    ![AppSourcen sertifioitu Power BI -visualisointi](media/power-bi-custom-visuals-certified/certified-visual-yellow-small.png)

* Kun napsautat Power BI -visualisoinnin korttia AppSourcessa, keltainen merkki, jossa lukee *PBI Certified (tai PBI-sertifioitu)* ilmaisee sitä, että kyseinen Power BI -visualisointi on sertifioitu.

    ![Sovellussivu ja sertifioitu Power BI -visualisointi](media/power-bi-custom-visuals-certified/certified-visual-yellow-big.png)

### <a name="certified-power-bi-visuals-in-the-power-bi-interface"></a>Sertifioidut Power BI -visualisoinnit Power BI -käyttöliittymässä

* Kun tuot Power BI -visualisointia Power BI:stä (Desktop tai palvelu), sininen merkki ilmaisee, että Power BI -visualisointi on sertifioitu.

    ![Power BI -käyttöliittymän sertifioitu Power BI -visualisointi](media/power-bi-custom-visuals-certified/certified-visual-blue.png)

* Voit näyttää vain sertifioidut Power BI -visualisoinnit valitsemalla *Power BI -sertifioitu* -suodatinasetuksen.

## <a name="publication-timeline"></a>Julkaisun aikajana

Käyttöönotto Appsourceen on prosessi, joka voi kestää jonkin aikaa. Power BI -visualisointi on ladattavissa Appsourcesta, kun tämä prosessi on valmis.

### <a name="when-will-users-be-able-to-download-my-visual"></a>Milloin käyttäjät pystyvät lataamaan visualisoinnin?

* Jos olet lähettänyt Power BI -visualisoinnin ensimmäistä kertaa, käyttäjät voivat ladata sen muutaman tunnin kuluttua siitä, kun olet saanut sähköpostiviestin Appsourcesta.

* Jos olet lähettänyt päivityksen aiemmin luotuun Power BI -visualisointiin, käyttäjät voivat ladata sen kuukauden kuluessa lähetyksestä.

    >[!NOTE]
    > Appsourcen *Versio*-kenttä päivitetään, kun AppSource on hyväksynyt Power BI:n noin viikko sen jälkeen, kun olet lähettänyt visualisoinnin. Käyttäjät voivat ladata päivitetyn visualisoinnin, mutta päivitetyt toiminnot eivät tule voimaan. Visualisoinnin uudet toiminnot vaikuttavat käyttäjän raportteihin kuukauden jälkeen. 

### <a name="when-will-my-power-bi-visual-display-a-certification-badge"></a>Milloin Power BI -visualisointi näyttää sertifiointimerkin?

* Jos olet lähettänyt Power BI -visualisoinnin ensimmäistä kertaa, sertifiointimerkki ilmestyy päivän kuluessa siitä, kun hän saa hyväksymisestä sähköpostiviestin Appsourcesta.

* Jos pyydät varmentamista olemassa olevalle Power BI -visualisoinnille, sertifiointimerkki näkyy kuukauden kuluessa lähetyksestä.

## <a name="next-steps"></a>Seuraavat vaiheet

* Jos olet web-kehittäjä, joka on kiinnostunut omien Power BI -visualisointien luomisesta ja niiden lisäämisestä  [Microsoft AppSourceen](https://appsource.microsoft.com), aloita  [Power BI -visualisoinnin kehittäminen](custom-visual-develop-tutorial.md) -opetusohjelmasta.

* Saat lisätietoja visualisoinneista [sertifioitujen visualisointien usein kysytyistä kysymyksistä](power-bi-custom-visuals-faq.md#certified-power-bi-visuals).

* [Power BI -visualisoinnin kehittäminen](custom-visual-develop-tutorial.md)

* [Microsoftin Power BI -visualisointien soittoluettelo YouTubessa](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)

* [Visualisoinnit Power BI:ssä](power-bi-custom-visuals.md)

* [Power BI -visualisointien julkaiseminen Microsoft AppSourcessa](office-store.md)

* Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)