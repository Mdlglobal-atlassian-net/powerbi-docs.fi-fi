---
title: Usein kysyttyjä kysymyksiä – Power BI:n visualisoinnit
description: Selaa Power BI -visualisointeja koskevien usein kysyttyjen kysymysten ja vastausten luetteloa
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.custom: ''
ms.date: 12/17/2018
ms.openlocfilehash: e7374ce6188792b4f4c1c5be2dd40d7694045159
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/04/2019
ms.locfileid: "71946148"
---
# <a name="frequently-asked-questions-about-power-bi-visuals"></a>Usein kysyttyjä kysymyksiä – Power BI:n visualisoinnit

## <a name="organizational-visuals"></a>Organisaation visualisoinnit

Hallintaportaalissa voit hallita organisaatiosi Power BI:n visualisointeja.

### <a name="how-can-the-admin-manage-the-organizational-power-bi-visuals"></a>Miten järjestelmänvalvoja voi hallita organisaation Power BI -visualisointeja?

Hallintaportaalin Organisaation visualisoinnit -välilehdessä järjestelmänvalvoja voi nähdä ja [hallita kaikkia organisaation Power BI -visualisointeja](service-admin-portal.md#organizational-visuals), kuten lisätä, poistaa ja ottaa käyttöön tai pois käytöstä.
Visualisointeja ei enää tarvitse jakaa sähköpostitse tai jakamalla kansioita. Kun organisaation visualisoinnit on otettu käyttöön organisaation säilössä, organisaation käyttäjät voivat helposti löytää ne ja tuoda ne raportteihinsa suoraan Power BI Desktopista tai Power BI -palvelusta. Organisaation visualisoinnit löytyvät sisäisen säilön *OMA ORGANISAATIO* -välilehdestä Power BI Desktopissa ja Power BI -palvelussa. Kun järjestelmänvalvoja lataa organisaation mukautetun visualisoinnin uuden version, kaikki organisaatiossa saavat saman päivitetyn version. Raporttien tekijöiden ei tarvitse poistaa visualisointeja raporteistaan saadakseen niiden uudet versiot, sillä kaikki niitä käyttävät raportit päivitetään automaattisesti. Päivitysmenetelmä muistuttaa Marketplacen visualisointeja.

### <a name="if-an-admin-uploads-a-custom-visual-from-the-public-marketplace-to-the-organization-store-is-it-automatically-updated-once-a-vendor-updates-the-visual-in-the-public-marketplace"></a>Jos järjestelmänvalvoja lataa mukautetun visualisoinnin julkisesta Marketplacesta organisaation sisäiseen säilöön, päivittyykö se automaattisesti, kun toimittaja päivittää visualisoinnin julkisessa Marketplacessa?

Ei. Julkisesta Marketplacesta peräisin olevia visualisointeja ei päivitetä automaattisesti.
Järjestelmänvalvojan vastuulla on päivittää organisaation visualisointien versiot.

### <a name="is-there-a-way-to-disable-the-organizational-store"></a>Voiko organisaation säilön poistaa käytöstä?

Ei. Käyttäjät näkevät aina Oma organisaatio -välilehden Power BI Desktopissa ja Power BI -palvelussa. Järjestelmänvalvoja voi poistaa tai poistaa käytöstä organisaation visualisointeja hallintaportaalissa, jolloin organisaation säilö on tyhjä.
  
### <a name="if-the-administrator-disables-power-bi-visuals-from-the-admin-portal-tenant-settings-do-users-still-have-access-to-the-organizational-visuals"></a>Jos järjestelmänvalvoja poistaa Power BI -visualisoinnit käytöstä hallintaportaalissa (vuokraajan asetuksissa), voivatko käyttäjät edelleen käyttää organisaation visualisointeja?

Kyllä. Jos järjestelmänvalvoja poistaa Power BI -visualisoinnit käytöstä hallintaportaalissa, se ei vaikuta organisaation säilöön. Joissakin organisaatioissa Power BI -visualisoinnit on poistettu käytöstä ja käytössä ovat vain valikoidut visualisoinnit, jotka järjestelmänvalvoja on tuonut ja ladannut organisaation säilöön. Power BI -visualisointien poistamista käytöstä hallintaportaalissa ei tueta Power BI Desktopissa. Desktop-käyttäjät voivat edelleen lisätä ja käyttää Power BI -visualisointeja raporteissaan julkisesta Marketplacesta. Nämä Power BI -visualisoinnit lakkaavat kuitenkin hahmontumasta, kun niitä julkaistaan Power BI -palvelussa. Julkaisemisen yrittäminen tuottaa myös virheen. Kun käytät Power BI -palvelua, et voi tuoda Power BI -visualisointeja julkisesta Marketplacesta. Vain organisaation säilössä olevia visualisointeja voi tuoda, koska Power BI -palvelussa käytetään hallintaportaalin Power BI -visualisointen asetuksia.

### <a name="why-does-the-organizational-store-and-organizational-visuals-make-a-great-enterprise-solution"></a>Miksi organisaation säilö ja organisaation visualisoinnit muodostavat toimivan yritysratkaisun?

* Jokainen saa saman version, jota hallitsee Power BI -järjestelmänvalvoja. Kun järjestelmänvalvoja päivittää visualisoinnin version hallintaportaalissa, kaikki organisaation käyttäjät saavat automaattisesti päivitetyn version.

* Visualisointitiedostoja ei enää tarvitse jakaa sähköpostitse tai kansioita jakamalla. Kaikki kirjautuneet jäsenet näkevät saman jaetun sijainnin.

* Tietoturva ja tuettavuus parantuvat, kun organisaation visualisointien uudet versiot päivitetään automaattisesti kaikkiin raportteihin Marketplacen visualisointien tapaan.

* Organisaation käyttäjien on oltava kirjautuneena, jotta he voivat tarkastella ja käyttää organisaation visualisointeja, mikä muodostaa yhden elementin organisaation suojauksessa.

* Järjestelmänvalvojat voivat hallita, mitä Power BI -visualisointeja organisaatiossa on käytettävissä.

* Järjestelmänvalvojat voivat hallintaportaalissa ottaa visualisointeja käyttöön tai poistaa niitä käytöstä testausta varten. Nämä visualisoinnit on sallittu vain organisaation jäsenille, mikä helpottaa tietoturvan valvontaa.

## <a name="certified-power-bi-visuals"></a>Sertifioidut Power BI -visualisoinnit

### <a name="what-are-certified-power-bi-visuals"></a>Mitä sertifioidut Power BI -visualisoinnit ovat?

Sertifioidut Power BI -visualisoinnit ovat [Marketplacen](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) visualisointeja, jotka täyttävät Power BI -tiimin [määrittämät](power-bi-custom-visuals-certified.md) tietyt koodi- ja testausvaatimukset.  Suoritettavat testit on suunniteltu varmistamaan, ettei visualisointi käytä ulkoisia palveluita tai resursseja. Microsoft ei kuitenkaan ole kolmannen osapuolen Power BI -visualisointien tekijä, ja se kehottaa asiakkaita ottamaan yhteyttä suoraan tekijään visualisoinnin toiminnan varmistamiseksi.

### <a name="what-tests-are-done-during-the-certification-process"></a>Millaisia testejä sertifiointiprosessin aikana tehdään?

Sertifiointiprosessin aikana tehdään muun muassa seuraavat testit: Koodin arviointeja, staattisen koodin analysointi, tietojen vuotaminen, tietojen sumea testaus, penetraatiotesti, sivustojen välisiin komentosarjoihin pääsemisen testaus, haitallisten tietojen lisääminen, syötteiden tarkistus ja toiminnallinen testaus.
 
### <a name="do-you-certify-visuals-every-submission"></a>Sertifioidaanko visualisoinnit jokaisella lähetyskerralla?

Kyllä. Aina kun sertifioidusta visualisoinnista lähetetään Marketplaceen uusi versio, visualisoinnin versiopäivitykselle tehdään samat sertifiointitarkistukset.

Huomautus kehittäjille: jos lähetät sertifioidusta visualisoinnista versiopäivityksen, sinun ei tarvitse lähettää siitä erillistä sähköpostiviestiä, kuten [ensimmäisen sertifiointipyynnön yhteydessä.](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified#process-for-submitting-a-custom-visual-for-certification) Versiopäivitysten sertifiointi tapahtuu automaattisesti, ja hylkäykseen johtaneista rikkomuksista lähetetään sähköpostitse ilmoitus, jossa kerrotaan korjaustarpeet. 

### <a name="is-it-possible-that-a-certified-visual-stops-being-certified-with-a-new-update"></a>Onko mahdollista, että sertifioitu visualisointi lakkaa olemasta sertifioitu uuden päivityksen myötä?

Ei, se ei ole mahdollista. Visualisoinnin sertifiointia ei voida purkaa uuden päivityksen perusteella. Sen sijaan päivitys voidaan hylätä.
 
### <a name="do-i-need-to-share-my-code-in-public-repository-if-i-am-submitting-to-the-certification-process"></a>Jos lähetän työni sertifioitavaksi, onko minun jaettava koodini julkiseen säilöön?

Ei, sinun ei tarvitse jakaa koodiasi julkisesti. Sinun on kuitenkin annettava meille lukuoikeudet visualisoinnin koodin tarkistamista varten, esimerkiksi yksityiseen säilöön GitHubissa.
 
### <a name="do-we-have-to-publishhttpsdocsmicrosoftcompower-bideveloperoffice-store-the-visual-in-the-marketplacehttpsappsourcemicrosoftcommarketplaceappspage1productpower-bi-visuals-to-certify-it"></a>Edellyttääkö sertifioinnin saaminen, että visualisointi on [julkaistava](https://docs.microsoft.com/power-bi/developer/office-store) [Marketplacessa](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)?

Kyllä. Visualisoinnin julkaiseminen ensin Marketplacessa on pakollinen vaatimus sertifioinnin saamiseksi.
Jos haluat, että mukautettu visualisointisi sertifioidaan, sen täytyy olla palvelimillamme. Emme voi sertifioida yksityisiä visualisointeja.
 
### <a name="how-long-does-it-take-to-certify-my-visual"></a>Miten kauan visualisoinnin sertifiointi kestää?

Jos kyseessä on versiopäivitys, sertifiointiin saattaa kulua jopa kolme viikkoa. Uusien lähetysten (ensimmäistä kertaa sertifioitavien) sertifiointi saattaa kestää jopa neljä viikkoa. 

### <a name="does-the-certification-process-ensure-that-no-data-leakage-occurs"></a>Takaako sertifiointiprosessi, ettei tietovuotoja voi tapahtua?

Suoritettavat testit on suunniteltu varmistamaan, ettei visualisointi käytä ulkoisia palveluita tai resursseja. Microsoft ei kuitenkaan ole kolmannen osapuolen Power BI -visualisointien tekijä, ja se kehottaa asiakkaita ottamaan yhteyttä suoraan tekijään visualisoinnin toiminnan varmistamiseksi.
 
### <a name="are-uncertified-power-bi-visuals-safe-to-use"></a>Onko sertifioimattomien Power BI -visualisointien käyttö turvallista?

Power BI -visualisointien sertifioimattomuus ei välttämättä tarkoita, etteivät visualisoinnit olisi turvallisia käyttää.
Jotkin visualisoinnit eivät ole sertifioituja, koska ne eivät täytä yhtä tai useampaa [sertifiointivaatimusta](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Tällaisia ovat esimerkiksi karttavisualisoinnit, jotka muodostavat yhteyden ulkoisiin palveluihin, tai visualisoinnit, jotka hyödyntävät kaupallisia kirjastoja.
 
## <a name="visuals-with-additional-purchases"></a>Lisäostoja sisältävät visualisoinnit

### <a name="what-is-a-visual-with-additional-purchases"></a>Mikä on lisäostoja sisältävä visualisointi?

Lisäostoja sisältävä visualisointi vastaa sovelluskohtaisia ostoja (IAP) Marketplacessa. Nämä apuohjelmat on merkitty hintatunnisteella**Lisäosto saatetaan vaatia**.

Power BI -IAP-visualisoinnit ovat maksuttomia ja ladattavia Power BI -visualisointeja. Niiden lataaminen Marketplacesta ei maksa mitään. IAP-visualisoinnit tarjoavat mahdollisuuden sovelluskohtaisiin ostoihin, joilla saa käyttöön lisäominaisuuksia.  

### <a name="whats-the-benefit-to-developers"></a>Mitä etua niistä on kehittäjille?

Power BI -IAP-visualisoinnit ovat AppSourcessa lukuisten päivittäisten kävijöiden löydettävissä, jolloin ne tuovat arvokasta liikennettä. Ne myös parantavat kehittämiesi Power BI -IAP-visualisointien tunnettuutta – ja tekevät tunnetuksi sinua kehittäjänä.

Jos olet hallinnut näitä visualisointeja tähän asti sivustosi kautta, voit nyt lähettää ne AppSourceen. Se parantaa niiden löydettävyyttä ja näkyvyyttä Power BI -yhteisössä.

AppSourcessa voit saada IAP-visualisoinneista suoraa palautetta niitä käyttäviltä asiakkailtasi arvostelujen ja kaupan luokitusjärjestelmän kautta.  

Kun AppSourcen vahvistustiimi on hyväksynyt IAP-visualisoinnin, voit lähettää sen myös sertifiointiin. Se on valinnainen prosessi.  

Kun Power BI -IAP-visualisointi on sertifioitu, sen voi viedä PowerPointiin ja näyttää sähköposteissa, joita käyttäjät saavat tilatessaan raporttisivuja. Täten lähettämällä Power BI -IAP-visualisointeja Marketplaceen voit saada niitä sertifioiduiksi, minkä lisäksi ne voivat tukea joukkoa lisäominaisuuksia.  

### <a name="do-iap-visuals-need-to-be-certified"></a>Onko IPA-visualisoinnit pakko sertifioida?

Sertifiointiprosessi on valinnainen. Kehittäjä päättää itse, haluaako hän sertifioida Power BI -IAP-visualisointejaan. Sama pätee maksuttomiin visualisointeihin.

### <a name="what-is-changing-in-the-submission-process"></a>Miten lähetysprosessi muuttuu?

Power BI -IAP-visualisointien lähettäminen Marketplaceen noudattaa samaa prosessia kuin maksuttomien visualisointien. Se tapahtuu myyjän koontinäytön kautta.  Lähetysprosessin ainoa muutos on, että kehittäjän on myyjän koontinäytössä lisättävä kehittäjän huomautuksiin seuraava merkintä: ”Visual with in-app purchase” (Sovelluskohtaisia ostoja sisältävä visualisointi). Sinun on myös annettava käyttöoikeusavain tai -tunnus, jos maksulliset tai lisäominaisuudet on vahvistettava.  

Myyjän koontinäytössä ei ole uutta vaihtoehtoa. Jos IAP-visualisointisi on *maksuton sovellusten sisäisten ostojen kanssa*, se on lähetettävä *maksuttomana*.

Kerro lisäksi käyttäjille kaupan pitkässä kuvauksessa, mitkä ominaisuudet ovat maksuttomia ja mitkä edellyttävät lisäostoja toimiakseen.  

### <a name="what-should-i-do-beforesubmittingmy-iap-custom-visual"></a>Mitä pitäisi tehdä ennen mukautetun IAP-visualisoinnin lähettämistä?

Jos olet tekemässä mukautettua IAP-visualisointia tai sinulla jo on sellainen, varmista, että se täyttää ohjeet.  

Jos siinä on logo, varmista, että se on ohjeiden mukainen (väri, paikka, koko ja toiminnon käynnistäminen).

Ohjeista löydät tietoa myös parhaista käytännöistä.  
> [!Note]
> Kaikki maksuttomat visualisoinnit säilyttävät ne samat maksuttomat ominaisuudet, jotka olivat aiemmin tarjolla. Voit lisätä valinnaisia maksullisia lisäominaisuuksia aiempien maksuttomien ominaisuuksien lisäksi. Suosittelemme lähettämään sovelluskohtaisten tuotteiden visualisoinnit lisäominaisuuksien kanssa uusina visualisointeina sen sijaan, että päivittäisit vanhat, maksuttomat visualisoinnit.

### <a name="can-i-get-my-iap-custom-visual-certified"></a>Miten saan mukautetun IAP-visualisointini sertifioitua?

Samalla tavalla kuin maksuttoman visualisoinnin.  Kun AppSource-tiimi on hyväksynyt mukautetun IAP-visualisointisi, voit lähettää sen sertifioitavaksi.

Visualisoinnin sertifioiminen edellyttää, että se täyttää sertifioinnin edellytykset. Se ei esimerkiksi voi käyttää ulkoisia palveluja käyttöoikeuksien vahvistamiseen.

Muista, että sertifioiminen on valinnainen prosessi. Päätät itse, haluatko sertifioida IAP-visualisointisi.

## <a name="additional-questions"></a>Lisäkysymyksiä

### <a name="how-to-get-support"></a>Miten saan tukea?

Power -visualisointien tukitiimille voit lähettää kysymyksiä ja kommentteja:  *pbicvsupport@microsoft.com*  .  

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja on kohdassa [Power BI:n Power BI -visualisointien vianmääritys](power-bi-custom-visuals-troubleshoot.md).
