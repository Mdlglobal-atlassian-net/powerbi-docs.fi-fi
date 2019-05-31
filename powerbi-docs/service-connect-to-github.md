---
title: Yhteyden muodostaminen GitHubin Power BI:n välillä
description: GitHub for Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: sarinas
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: b0f2bd53f1d8b82b70072446723c2ca3723eeacd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65608423"
---
# <a name="connect-to-github-with-power-bi"></a>Yhteyden muodostaminen GitHubin Power BI:n välillä
Tässä artikkelissa käydään läpi GitHub-tilin sovelluksessa Power BI-mallin tiedot vetämällä. Malli, sovellus muodostaa työtilan koontinäytön, raportteja ja tietojoukon, joiden avulla voit tarkastella GitHub-tietoihin. Power BI GitHub-sovellus näyttää GitHub-säilön tunnetaan myös säilössä panoksestasi, ongelmia, pull-pyynnöt ja aktiivisten käyttäjien merkityksellisiä tietoja.

Kun olet asentanut sovelluksen mallin, voit muuttaa koontinäyttöä ja raporttia. Sitten voit jakaa sen sovelluksena työtovereiden organisaatiossasi.

Muodosta yhteys [GitHub-mallin sovellus](https://app.powerbi.com/getdata/services/github) tai Lue lisää [GitHub-integrointi](https://powerbi.microsoft.com/integrations/github) kanssa Power BI.

Voit myös kokeilla [GitHub-opetusohjelma](service-tutorial-connect-to-github.md). Todellinen GitHub-tietoja Power BI-dokumentaation julkisen säilön asentaa siihen.

>[!NOTE]
>Malli-sovellus edellyttää pääsyä säilön GitHub-tili. Lisätietoja vaatimuksista on alla.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]
   
3. Valitse **GitHub** \> **hanki se nyt**.
4. - **Asentaa Power BI-sovelluksesta?** Valitse **asentaa**.
4. - **Sovelluksia** ruudussa **GitHub** ruudun.

    ![Power BI GitHub-ruutu](media/service-connect-to-github/power-bi-github-tile.png)

6. - **Uuden sovelluksen käytön aloittaminen**, valitse **yhdistää tiedot**.

    ![Aloita uuden sovelluksesi käyttö](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

5. Kirjoita säilön nimi ja omistaja. Lisätietoja [näiden parametrien löytämisestä](#FindingParams) on alla.
   
    ![Power BI GitHub-säilön nimi](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. Anna GitHub-tunnistetietosi (tämä vaihe voidaan ohittaa, jos olet jo kirjautunut sisään selaimellasi). 
6. Valitse **todennusmenetelmäksi** **oAuth2** \> **Kirjaudu sisään**. 
7. Noudata Githubin todennusnäyttöjä. Myönnä Power BI-mallin sovelluksen käyttöoikeus GitHub-tietojen GitHub.
   
   ![Power BI GitHub-valtuutus](media/service-connect-to-github/github_authorize.png)
   
    Power BI muodostaa yhteyden GitHub ja tiedot.  Tiedot päivitetään kerran päivässä. Kun Power BI on tuonut tiedot, näkyviin tulee uusi GitHub-työtila sisällön.

## <a name="modify-and-distribute-your-app"></a>Muokata ja jakaa sovelluksen

Olet asentanut mallin GitHub-sovellus. Tämä tarkoittaa myös luomasi GitHub-sovelluksen työtilassa. Työtilassa voit muuttaa raportin ja koontinäytön ja jakaa sen *sovelluksen* työtovereiden organisaatiossasi. 

1. Valitse vasemmassa siirtymispalkissa työtilan nimen vieressä olevaa nuolta. Näet työtila sisältää koontinäytön ja raportin.

    ![Sovelluksen vasemmasta siirtymisruudusta](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

8. Valitse uusi [GitHub-koontinäyttö](https://powerbi.microsoft.com/integrations/github).    
    ![Power BI GitHub-koontinäyttö](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

3. Tarkastele uusi GitHub-työtila sisällön vasemmassa siirtymispalkissa valitsemalla **työtilat** > **GitHub**.
 
   ![GitHub-työtilan vasemmanpuoleisessa siirtymisruudussa](media/service-connect-to-github/power-bi-github-left-nav.png)

    Tämä näkymä on työtilan sisältöluettelosta. Näet oikeassa yläkulmassa, **Päivitä sovellus**. Kun olet valmis jakamaan sovelluksesi työtovereillesi, joka on jossa aloitat. 

    ![GitHub-sisältöluettelo](media/service-connect-to-github/power-bi-github-content-list.png)

2. Valitse **raporttien** ja **tietojoukkoja** Nähdäksesi työtilan muut elementit.

    Lue [jakaminen sovellusten](service-create-distribute-apps.md) työtovereillesi.

## <a name="whats-included-in-the-app"></a>Mitä sisällytetään sovellus
Seuraavat tiedot ovat käytettävissä GitHubista Power BI:ssä:     

| Taulukon nimi | Kuvaus |
| --- | --- |
| Osallistumiset |Osallistumiset-taulukko antaa kokonaismäärän, poistot ja vahvistaa osallistujan koostetaan viikoittain tekijä. Ensimmäiset 100 osallistujaa lasketaan mukaan. |
| Ongelmat |Listaa kaikki valitun säilön ongelmat ja sisältää laskelmia, kuten kokonaisajan ja keskimääräisen ongelman sulkemiseen käytetyn ajan, avoimien ongelmien kokonaismäärän ja suljettujen ongelmien kokonaismäärän. Tämä taulukko on tyhjä, jos säilössä ei ole ongelmia. |
| Noutopyynnöt |Tämä taulukko sisältää kaikki säilöön kohdistetut noutopyynnöt, sekä tiedot siitä, kuka pyynnön on tehnyt. Se sisältää myös laskelmia, kuten montako Avaa suljettu ja yhteensä pull-pyynnöt, miten kauan noutopyynnön kestänyt ja miten kauan noutopyynnön keskimääräisesti. Tämä taulukko on tyhjä, jos säilössä ei ole ongelmia. |
| Käyttäjät |Tämä taulukko sisältää luettelon GitHub-käyttäjät tai osallistujat on tehty panoksestasi, Arkistoidut ongelmat tai toteutetut noutopyynnöt valitusta säilöstä. |
| Välitavoitteet |Siinä ovat kaikki valitun säilön välitavoitteet. |
| DateTable |Tämä taulukko sisältää päivämääriä tästä päivästä aikaisempiin aiemmin, joiden avulla voit analysoida GitHub-tietojasi päivämäärän mukaan. |
| ContributionPunchCard |Tätä taulukkoa voidaan käyttää valitun osallistumisreikäkorttina valitulle säilölle. Se näyttää vahvistetut muutokset viikonpäivän ja kellonajan mukaan järjestettyinä. Tätä taulukkoa ei ole yhdistetty muihin mallin taulukoihin. |
| RepoDetails |Tämä taulukko sisältää yksityiskohtaisia tietoja valitusta säilöstä. |

## <a name="system-requirements"></a>Järjestelmävaatimukset
* GitHub-tili, jolla on pääsy säilöön.  
* Ensimmäisen sisäänkirjautumisen aikana myönnetyt käyttöoikeudet on Power BI:n GitHub-sovellukseen. Katso lisätietoja käyttöoikeuksien perumisesta alapuolelta.  
* Riittävästi käytettävissä olevia API-ohjelmointirajapintakutsuja tietojen vastaanottamista ja päivittämistä varten.  

### <a name="de-authorize-power-bi"></a>Power BI:n valtuutuksien poisto
Estääksesi yhteyden GitHub-säilöön valtuutukset Power BI, ja voit kumota käyttöoikeudet githubissa. Tutustu tähän [GitHub-apu](https://help.github.com/articles/keeping-your-ssh-keys-and-application-access-tokens-safe/#reviewing-your-authorized-applications-oauth) ohjeaiheen.

<a name="FindingParams"></a>
## <a name="finding-parameters"></a>Parametrien löytäminen
Voit määrittää omistajan ja säilön tarkastelemalla säilöä GitHubissa:

![Säilön nimi ja omistaja](media/service-connect-to-github/github_ownerrepo.png)

Ensimmäisen osan ”Azure” on omistaja ja toisen osan ”azure-sdk-for-php” on säilö itse.  Nämä kaksi asiaa näkyvät myös säilön URL-osoitteessa:

    <https://github.com/Azure/azure-sdk-for-php> .

## <a name="troubleshooting"></a>Vianmääritys
Voit tarvittaessa varmistaa GitHub-tunnistetietosi.  

1. Toisessa selainikkunassa GitHub-sivustossa ja kirjaudu sisään GitHub. Näet, oletko kirjautuneena sisään, GitHub-sivuston oikeasta yläkulmasta.    
2. Siirry GitHubissa säilön URL-osoitteeseen, jota aiot käyttää Power BI:ssä. Esimerkki: https://github.com/dotnet/corefx.  
3. Koita seuraavaksi yhdistää GitHubiin Power BI:ssä. Käytä määritä GitHub -valintaikkunassa säilön ja säilön omistajan nimiä samalle säilölle.  

## <a name="next-steps"></a>Seuraavat vaiheet

* [Opetusohjelma: Power BI-ja GitHub-säilön yhdistäminen](service-tutorial-connect-to-github.md)
* [Luo uusi työtilat Power BI](service-create-the-new-workspaces.md)
* [Asenna ja käytä sovelluksia Power BI:ssä](consumer/end-user-apps.md)
* [Power BI-sovelluksista ulkoisiin palveluihin yhdistäminen](service-connect-to-services.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

