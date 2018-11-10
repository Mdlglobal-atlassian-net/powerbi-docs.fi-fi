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
ms.date: 10/29/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: 064d32944f52f6e391d4a7ec4df41ecbf09b7e3f
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223072"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Usein kysyttyjä kysymyksiä – Power BI:n mukautetut visualisoinnit

## <a name="organizational-custom-visuals"></a>Organisaation mukautetut visualisoinnit

**Miten järjestelmänvalvoja voi hallita organisaation mukautettuja visualisointeja?**

Hallintaportaalin Organisaation mukautetut visualisoinnit -välilehdellä järjestelmänvalvoja voi nähdä ja [hallita kaikkia organisaation mukautettuja visualisointeja](https://docs.microsoft.com/power-bi/service-admin-portal#organization-visuals), kuten lisätä, poistaa ja ottaa käyttöön tai pois käytöstä.
Visualisointeja ei enää tarvitse jakaa sähköpostitse tai jakamalla kansioita. Kun ne on otettu käyttöön organisaation säilössä, organisaation käyttäjät voivat helposti löytää ne ja tuoda ne raportteihinsa suoraan Power BI Desktopista tai Power BI -palvelusta. Organisaation mukautetut visualisoinnit löytyvät sisäisen säilön Oma organisaatio -välilehdeltä Power BI Desktopissa ja Power BI -palvelussa. Kun järjestelmänvalvoja lataa organisaation mukautetun visualisoinnin uuden version, kaikki organisaatiossa saavat saman päivitetyn version. Raporttien tekijöiden ei tarvitse poistaa visualisointeja raporteistaan saadakseen niiden uudet versiot, sillä kaikki niitä käyttävät raportit päivitetään automaattisesti. Päivitysmenetelmä muistuttaa Marketplacen visualisointeja.

**Jos järjestelmänvalvoja lataa mukautetun visualisoinnin julkisesta Marketplacesta organisaation sisäiseen säilöön, päivittyykö se automaattisesti, kun toimittaja päivittää visualisoinnin julkisessa Marketplacessa?**

Ei. Julkisesta Marketplacesta peräisin olevia visualisointeja ei päivitetä automaattisesti.
Järjestelmänvalvojan vastuulla on päivittää organisaation mukautettujen visualisointien versiot, jos se on tarpeen.

**Voiko organisaation säilön poistaa käytöstä?**

Ei. Käyttäjät näkevät aina Oma organisaatio -välilehden Power BI Desktopissa ja Power BI -palvelussa. Järjestelmänvalvoja voi poistaa tai poistaa käytöstä organisaation mukautettuja visualisointeja hallintaportaalissa, jolloin organisaation säilö on tyhjä.
  
**Jos järjestelmänvalvoja poistaa mukautetut visualisoinnit käytöstä hallintaportaalissa (vuokraajan asetuksissa), voivatko käyttäjät edelleen käyttää organisaation mukautettuja visualisointeja?**

Kyllä. Jos järjestelmänvalvoja poistaa mukautetut visualisoinnit käytöstä hallintaportaalissa, se ei vaikuta organisaation säilöön. Joissakin organisaatioissa mukautetut visualisoinnit on poistettu käytöstä ja käytössä ovat vain valikoidut visualisoinnit, jotka on tuotu ja ladattu organisaation säilöön järjestelmänvalvojan toimesta. Mukautettujen visualisointien poistamista käytöstä hallintaportaalissa ei tueta Power BI Desktopissa. Desktop-käyttäjät voivat lisätä ja käyttää mukautettuja visualisointeja raporteissaan julkisesta Marketplacesta. Nämä mukautetut visualisoinnit lakkaavat kuitenkin hahmontumasta, kun niitä julkaistaan Power BI -palvelussa. Julkaisemisen yrittäminen tuottaa myös virheen. Kun käytät Power BI -palvelua, et voi tuoda mukautettuja visualisointeja julkisesta Marketplacesta. Vain organisaation säilössä olevia visualisointeja voi tuoda, koska Power BI -palvelussa käytetään hallintaportaalin mukautettujen visualisointen asetuksia.

**Miksi organisaation säilö ja organisaation mukautetut visualisoinnit muodostavat toimivan yritysratkaisun?**

* Jokainen saa saman version, jota hallitsee Power BI -järjestelmänvalvoja. Kun järjestelmänvalvoja päivittää visualisoinnin version hallintaportaalissa, kaikki organisaation käyttäjät saavat automaattisesti päivitetyn version.

* Visualisointitiedostoja ei enää tarvitse jakaa sähköpostitse tai kansioita jakamalla. Kaikki kirjautuneet jäsenet näkevät saman jaetun sijainnin.

* Tietoturva ja tuettavuus parantuvat, kun organisaation mukautettujen visualisointien uudet versiot päivitetään automaattisesti kaikkiin raportteihin Marketplacen visualisointien tapaan.

* Organisaation käyttäjien on oltava kirjautuneena, jotta he voivat tarkastella ja käyttää organisaation mukautettuja visualisointeja, mikä muodostaa yhden elementin organisaation suojauksessa.

* Järjestelmänvalvojat voivat hallita, mitä mukautettuja visualisointeja organisaatiossa on käytettävissä.

* Järjestelmänvalvojat voivat hallintaportaalissa ottaa visualisointeja käyttöön tai poistaa niitä käytöstä testausta varten. Nämä visualisoinnit on sallittu vain organisaation jäsenille, mikä helpottaa tietoturvan valvontaa.

## <a name="certified-custom-visuals"></a>Sertifioidut mukautetut visualisoinnit

**Mitä ovat sertifioidut mukautetut visualisoinnit?**

Sertifioidut mukautetut visualisoinnit ovat [Marketplacen](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) visualisointeja, jotka täyttävät Power BI-tiimin [määrittämät](power-bi-custom-visuals-certified.md) tietyt koodi- ja testausvaatimukset.  Suoritettavat testit on suunniteltu tarkistamaan, että visualisointi ei käytä ulkoisia palveluita tai resursseja. Microsoft ei kuitenkaan ole kolmannen osapuolen mukautettujen visualisointien tekijä, joten kehotamme asiakkaita vahvistamaan tällaisen visualisoinnin toiminnot suoraan sen tekijältä.

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja vianmäärityksestä on kohdassa [Power BI:n mukautettujen visualisointien vianmääritys](power-bi-custom-visuals-troubleshoot.md).
