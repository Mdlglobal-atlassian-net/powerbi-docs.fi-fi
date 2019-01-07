---
title: Usein kysyttyjä kysymyksiä – Power BI:n mukautetut visualisoinnit
description: Selaa Power BI:n mukautettuja visualisointia koskevien usein kysyttyjen kysymysten ja vastausten luetteloa.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 12/17/2018
ms.openlocfilehash: c17f9b9841335420db67abb62c92603bf804f275
ms.sourcegitcommit: 13fdc8d62960f20c6d9ca1ab292f98992b47083b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/18/2018
ms.locfileid: "53553900"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Usein kysyttyjä kysymyksiä – Power BI:n mukautetut visualisoinnit

## <a name="organizational-custom-visuals"></a>Organisaation mukautetut visualisoinnit

### <a name="how-can-the-admin-manage-the-organizational-custom-visuals"></a>Miten järjestelmänvalvoja voi hallita organisaation mukautettuja visualisointeja?

Hallintaportaalin Organisaation mukautetut visualisoinnit -välilehdellä järjestelmänvalvoja voi nähdä ja [hallita kaikkia organisaation mukautettuja visualisointeja](https://docs.microsoft.com/power-bi/service-admin-portal#organization-visuals), kuten lisätä, poistaa ja ottaa käyttöön tai pois käytöstä.
Visualisointeja ei enää tarvitse jakaa sähköpostitse tai jakamalla kansioita. Kun ne on otettu käyttöön organisaation säilössä, organisaation käyttäjät voivat helposti löytää ne ja tuoda ne raportteihinsa suoraan Power BI Desktopista tai Power BI -palvelusta. Organisaation mukautetut visualisoinnit löytyvät sisäisen säilön *OMA ORGANISAATIO* -välilehdeltä Power BI Desktopissa ja Power BI -palvelussa. Kun järjestelmänvalvoja lataa organisaation mukautetun visualisoinnin uuden version, kaikki organisaatiossa saavat saman päivitetyn version. Raporttien tekijöiden ei tarvitse poistaa visualisointeja raporteistaan saadakseen niiden uudet versiot, sillä kaikki niitä käyttävät raportit päivitetään automaattisesti. Päivitysmenetelmä muistuttaa Marketplacen visualisointeja.

### <a name="if-an-admin-uploads-a-custom-visual-from-the-public-marketplace-to-the-organization-store-is-it-automatically-updated-once-a-vendor-updates-the-visual-in-the-public-marketplace"></a>Jos järjestelmänvalvoja lataa mukautetun visualisoinnin julkisesta Marketplacesta organisaation sisäiseen säilöön, päivittyykö se automaattisesti, kun toimittaja päivittää visualisoinnin julkisessa Marketplacessa?

Ei. Julkisesta Marketplacesta peräisin olevia visualisointeja ei päivitetä automaattisesti.
Järjestelmänvalvojan vastuulla on päivittää organisaation mukautettujen visualisointien versiot.

### <a name="is-there-a-way-to-disable-the-organizational-store"></a>Voiko organisaation säilön poistaa käytöstä?

Ei. Käyttäjät näkevät aina Oma organisaatio -välilehden Power BI Desktopissa ja Power BI -palvelussa. Järjestelmänvalvoja voi poistaa tai poistaa käytöstä organisaation mukautettuja visualisointeja hallintaportaalissa, jolloin organisaation säilö on tyhjä.
  
### <a name="if-the-administrator-disables-custom-visuals-from-the-admin-portal-tenant-settings-do-users-still-have-access-to-the-organizational-custom-visuals"></a>Jos järjestelmänvalvoja poistaa mukautetut visualisoinnit käytöstä hallintaportaalissa (vuokraajan asetuksissa), voivatko käyttäjät edelleen käyttää organisaation mukautettuja visualisointeja?

Kyllä. Jos järjestelmänvalvoja poistaa mukautetut visualisoinnit käytöstä hallintaportaalissa, se ei vaikuta organisaation säilöön. Joissakin organisaatioissa mukautetut visualisoinnit on poistettu käytöstä ja käytössä ovat vain valikoidut visualisoinnit, jotka on tuotu ja ladattu organisaation säilöön järjestelmänvalvojan toimesta. Mukautettujen visualisointien poistamista käytöstä hallintaportaalissa ei tueta Power BI Desktopissa. Desktop-käyttäjät voivat edelleen lisätä ja käyttää mukautettuja visualisointeja raporteissaan julkisesta Marketplacesta. Nämä mukautetut visualisoinnit lakkaavat kuitenkin hahmontumasta, kun niitä julkaistaan Power BI -palvelussa. Julkaisemisen yrittäminen tuottaa myös virheen. Kun käytät Power BI -palvelua, et voi tuoda mukautettuja visualisointeja julkisesta Marketplacesta. Vain organisaation säilössä olevia visualisointeja voi tuoda, koska Power BI -palvelussa käytetään hallintaportaalin mukautettujen visualisointen asetuksia.

### <a name="why-does-the-organizational-store-and-organizational-custom-visuals-make-a-great-enterprise-solution"></a>Miksi organisaation säilö ja organisaation mukautetut visualisoinnit muodostavat toimivan yritysratkaisun?

* Jokainen saa saman version, jota hallitsee Power BI -järjestelmänvalvoja. Kun järjestelmänvalvoja päivittää visualisoinnin version hallintaportaalissa, kaikki organisaation käyttäjät saavat automaattisesti päivitetyn version.

* Visualisointitiedostoja ei enää tarvitse jakaa sähköpostitse tai kansioita jakamalla. Kaikki kirjautuneet jäsenet näkevät saman jaetun sijainnin.

* Tietoturva ja tuettavuus parantuvat, kun organisaation mukautettujen visualisointien uudet versiot päivitetään automaattisesti kaikkiin raportteihin Marketplacen visualisointien tapaan.

* Organisaation käyttäjien on oltava kirjautuneena, jotta he voivat tarkastella ja käyttää organisaation mukautettuja visualisointeja, mikä muodostaa yhden elementin organisaation suojauksessa.

* Järjestelmänvalvojat voivat hallita, mitä mukautettuja visualisointeja organisaatiossa on käytettävissä.

* Järjestelmänvalvojat voivat hallintaportaalissa ottaa visualisointeja käyttöön tai poistaa niitä käytöstä testausta varten. Nämä visualisoinnit on sallittu vain organisaation jäsenille, mikä helpottaa tietoturvan valvontaa.

## <a name="certified-custom-visuals"></a>Sertifioidut mukautetut visualisoinnit

### <a name="what-are-certified-custom-visuals"></a>Mitä ovat sertifioidut mukautetut visualisoinnit?

Sertifioidut mukautetut visualisoinnit ovat [Marketplacen](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) visualisointeja, jotka täyttävät Power BI-tiimin [määrittämät](power-bi-custom-visuals-certified.md) tietyt koodi- ja testausvaatimukset.  Suoritettavat testit on suunniteltu varmistamaan, ettei visualisointi käytä ulkoisia palveluita tai resursseja. Microsoft ei kuitenkaan ole kolmannen osapuolen mukautettujen visualisointien tekijä. Kehotamme asiakkaita ottamaan yhteyttä suoraan tekijään visualisoinnin toiminnan varmistamiseksi.

## <a name="visuals-with-additional-purchases"></a>Lisäostoja sisältävät visualisoinnit

### <a name="what-is-a-visual-with-additional-purchases"></a>Mikä on lisäostoja sisältävä visualisointi?

Lisäostoja sisältävä visualisointi vastaa sovelluskohtaisia ostoja (IAP) Marketplacessa. Nämä apuohjelmat on merkitty hintatunnisteella  **Lisäosto saatetaan vaatia**.

Mukautetut IAP-visualisoinnit ovat maksuttomia ja ladattavia mukautettuja visualisointeja. Niiden lataaminen Marketplacesta ei maksa mitään. IAP-visualisoinnit tarjoavat mahdollisuuden sovelluskohtaisiin ostoihin, joilla saa käyttöön lisäominaisuuksia.  

### <a name="whats-the-benefit-to-developers"></a>Mitä etua niistä on kehittäjille?

Mukautetut IAP-visualisoinnit ovat AppSourcessa lukuisten päivittäisten kävijöiden löydettävissä, jolloin ne tuovat arvokasta liikennettä. Ne myös parantavat kehittämiesi IAP-visualisointien tunnettuutta – ja tekevät tunnetuksi sinua kehittäjänä.

Jos olet hallinnut näitä visualisointeja tähän asti sivustosi kautta, voit nyt lähettää ne AppSourceen. Se parantaa niiden löydettävyyttä ja näkyvyyttä Power BI -yhteisössä.

AppSourcessa voit saada IAP-visualisoinneista suoraa palautetta niitä käyttäviltä asiakkailtasi arvostelujen ja kaupan luokitusjärjestelmän kautta.  

Kun AppSourcen vahvistustiimi on hyväksynyt IAP-visualisoinnin, voit lähettää sen myös sertifiointiin. Se on valinnainen prosessi.  

Kun mukautettu IAP-visualisointi on sertifioitu, sen voi viedä PowerPointiin ja näyttää sähköposteissa, joita käyttäjät saavat tilatessaan raporttisivuja. Joten lähettämällä IAP-visualisointeja Marketplaceen voit saada niitä sertifioiduiksi, minkä lisäksi ne voivat tukea joukkoa lisäominaisuuksia.  

### <a name="do-iap-visuals-need-to-be-certified"></a>Onko IPA-visualisoinnit pakko sertifioida?

Sertifiointiprosessi on valinnainen. Kehittäjä päättää itse, haluaako hän sertifioida mukautettuja IAP-visualisointejaan. Sama pätee maksuttomiin visualisointeihin.

### <a name="what-is-changing-in-the-submission-process"></a>Miten lähetysprosessi muuttuu?

Mukautettujen IAP-visualisointien lähettäminen Marketplaceen noudattaa samaa prosessia kuin maksuttomien visualisointien. Se tapahtuu myyjän koontinäytön kautta.  Lähetysprosessin ainoa muutos on, että kehittäjän on myyjän koontinäytössä lisättävä kehittäjän huomautuksiin seuraava merkintä: ”Visual with in-app purchase” (Sovelluskohtaisia ostoja sisältävä visualisointi). Sinun on myös annettava käyttöoikeusavain tai -tunnus, jos maksulliset tai lisäominaisuudet on vahvistettava.  

Myyjän koontinäytössä ei ole uutta vaihtoehtoa. Jos IAP-visualisointisi on *maksuton sovellusten sisäisten ostojen kanssa*, se on lähetettävä *maksuttomana*.

Kerro lisäksi käyttäjille kaupan pitkässä kuvauksessa, mitkä ominaisuudet ovat maksuttomia ja mitkä edellyttävät lisäostoja toimiakseen.  

### <a name="what-should-i-do-beforesubmittingmy-iap-custom-visual"></a>Mitä pitäisi tehdä ennen mukautetun IAP-visualisoinnin lähettämistä?

Jos olet tekemässä mukautettua IAP-visualisointia tai sinulla jo on sellainen, varmista, että se täyttää ohjeet.  

Jos siinä on logo, varmista, että se on ohjeiden mukainen (väri, paikka, koko ja toiminnon käynnistäminen).

Ohjeista löydät tietoa myös parhaista käytännöistä.  

### <a name="can-i-get-my-iap-custom-visual-certified"></a>Miten saan mukautetun IAP-visualisointini sertifioitua?

Samalla tavalla kuin maksuttoman visualisoinnin.  Kun AppSource-tiimi on hyväksynyt mukautetun IAP-visualisointisi, voit lähettää sen sertifioitavaksi.

Visualisoinnin sertifioiminen edellyttää, että se täyttää sertifioinnin edellytykset. Se ei esimerkiksi voi käyttää ulkoisia palveluja käyttöoikeuksien vahvistamiseen.

Muista, että sertifioiminen on valinnainen prosessi. Päätät itse, haluatko sertifioida IAP-visualisointisi.

## <a name="additional-questions"></a>Lisäkysymyksiä

### <a name="how-to-get-support"></a>Miten saan tukea?

Mukautettujen visualisointien tukitiimille voit lähettää kysymyksiä ja kommentteja:  *pbicvsupport@microsoft.com* .  

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja on kohdassa [Power BI:n mukautettujen visualisointien vianmääritys](power-bi-custom-visuals-troubleshoot.md).
