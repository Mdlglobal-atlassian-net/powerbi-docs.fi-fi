---
title: Power BI:n Julkaise verkkoon -toiminto
description: Voit Power BI:n Julkaise verkkoon -toiminnon avulla helposti upottaa verkossa interaktiivisia Power BI -visualisointeja, kuten blogiposteja ja verkkosivustoja, sähköpostiviestien tai sosiaalisen median kautta kaikilla laitteilla.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/16/2019
LocalizationGroup: Share your work
ms.openlocfilehash: 1b5dfc0b05595e96c9a297a5be3700e71cdbe229
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051575"
---
# <a name="publish-to-web-from-power-bi"></a>Power BI:n Julkaise verkkoon -toiminto

Power BI kanssa **Julkaise verkkoon** vaihtoehto, voit helposti upottaa vuorovaikutteisia Power BI-visualisointeja, online, esimerkiksi kirjoituksia, verkkosivustoja, sähköpostiviestien tai sosiaalisen median kautta millä tahansa laitteella. Voit myös helposti muokata, päivittää ja ladata uudelleen julkaistuja visualisointeja tai poistaa niiden jakamisen.

> [!WARNING]
> Kun käytät **Julkaise verkkoon**, kuka tahansa Internetissä voi tarkastella julkaistuun raporttiin tai visualisointiin. Tämä edellyttää todennusta, ja se sisältää koostefunktion raporttien tarkasteleminen tarkemmat tiedot. Ennen julkaisemista raportin, varmista, että se on kunnossa, voit jakaa tiedot ja visualisoinnit julkisesti. Älä julkaise luottamuksellisia tai omistusoikeudellisia tietoja. Jos olet epävarma, tarkista organisaatiosi käytännöt ennen julkaisemista.

>[!Note]
>Voit upottaa sisältöä turvallisesti sisäiseen portaaliin tai sivustoon [Upota](service-embed-secure.md)- ja [Upota SharePoint Onlineen](service-embed-report-spo.md) -asetusten avulla. Näin varmistat, että kaikkien oikeuksien ja tietosuojan soveltaminen pakotetaan, kun käyttäjät tarkastelevat sisäisiä tietoja.

## <a name="how-to-use-publish-to-web"></a>Julkaise verkkoon -toiminnon käyttäminen

**Julkaise verkkoon** on käytettävissä henkilökohtaisessa tai ryhmän työtiloissa voit muokata raporteissa.  Se ei ole käytettävissä raporteille, jotka on jaettu kanssasi, tai ne varassa oleminen rivitason suojaus suojaa tiedot. Katso [ **rajoitukset** ](#limitations) osiosta täydellinen luettelo tapauksista alla jossa **Julkaise verkkoon** ei tueta. Tarkista **varoitus** tässä artikkelissa aiemmin mainittu ennen kuin käytät **Julkaise verkkoon**.

Seuraavat *lyhyt video* kerrotaan, miten tämä ominaisuus toimii. Sitten Kokeile sitä itse alla olevissa vaiheissa.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UF9QtqE7s4Y" frameborder="0" allowfullscreen></iframe>

Seuraavissa vaiheissa kuvataan, miten voit käyttää **Julkaise verkkoon** -toimintoa.

1. Avaa raportti, jota voit muokata ja valitse työtilassa **tiedosto > Julkaise verkkoon**.

   ![PtW1](media/service-publish-to-web/publish_to_web1.png)

2. Tarkista valintaikkunan sisältö ja valitse **Luo upotuskoodi**.

   ![PtW2](media/service-publish-to-web/publish_to_web2_ga.png)

3. Tarkista varoitus, kuten seuraavassa ja vahvista, että tiedot ovat voidaan Upota julkiseen sivustoon. Jos näin on, valitse **Julkaise**.

   ![PtW3](media/service-publish-to-web/publish_to_web3_ga.png)

4. Näyttöön tulee valintaikkuna, jossa on linkki. Voit lähettää tämän linkin sähköpostitse, kuten iFrame-koodi upottaminen tai liittää suoraan verkkosivustolle tai blogiin.

   ![PtW4](media/service-publish-to-web/publish_to_web4.png)

5. Jos olet aiemmin luonut raportin upotuskoodin ja valitset **Julkaise verkkoon**, et näe vaiheet 2-4-toiminnon valintaikkunoissa. Sen sijaan **upotuskoodin** tulee valintaikkuna:

   ![PtW5](media/service-publish-to-web/publish_to_web5.png)

   Voit luoda vain yhden upotuskoodin kullekin raportille.


## <a name="tips-and-tricks-for-view-modes"></a>Vihjeitä ja vinkkejä näyttötiloihin

Kun upotat sisältöä blogipostiin, sinun on yleensä sovitettava se tiettyyn näyttökokoon sisällä.  Voit muuttaa korkeutta ja leveyttä iFrame-tunnisteessa tarvittaessa. Sinun on kuitenkin, että raporttisi mahtuu annetun iFrame-alueella, joten sinun on myös Määritä asianmukainen näyttötila raporttia muokattaessa.

Seuraavassa taulukossa on ohjeita näyttötilasta ja siitä, miten se tulee näkyviin upotettuna.

| Näyttötila | Miltä se näyttää upotettuna |
| --- | --- |
| ![PtW6b](media/service-publish-to-web/publish_to_web6b.png) |**Sovita sivulle** noudattaa raportin sivun korkeutta ja leveyttä. Jos määrität sivun ”dynaamisille” suhteille, kuten 16:9 tai 4:3, sisältösi skaalautuu mahtumaan iframeen. Upotetaan Iframeen käytettäessä **Sovita sivulle** voi aiheuttaa **letterboxingin**, jossa harmaa tausta näkyy iframen alueilla sisällön jälkeen kuin skaalataan mahtumaan iframeen. Voit minimoida letterboxingin vaikutuksen määrittämällä-iframen korkeuden ja leveyden asianmukaisesti. |
| ![PtW6d](media/service-publish-to-web/publish_to_web6d.png) |**Todellinen koko** varmistaa, että raportin koko säilyy Määritä raportin sivulla. Tämä voi johtaa iframen näkyä vierityspalkkeja. Määritä iframen korkeus ja leveys siten vältät vierityspalkit. |
| ![PtW6c](media/service-publish-to-web/publish_to_web6c.png) |**Sovita leveyteen** varmistaa, että sisältö mahtuu iframen vaakasuuntaiselle alueelle. Reuna näkyy edelleen, mutta sisältö skaalataan käyttämään kaikki saatavilla olevaa vaakasuuntaista tilaa. |

## <a name="tips-and-tricks-for-iframe-height-and-width"></a>Vihjeitä ja vinkkejä iFramen korkeuteen ja leveyteen

A **Julkaise verkkoon** upottaa koodi näyttää seuraavalta:

![PtW7](media/service-publish-to-web/publish_to_web7.png)
 
Voit muokata leveyttä ja korkeutta manuaalisesti, jotta on tarkasti haluamassasi muodossa mahtumaan sivulle, johon sen upotat.

Lisää täydellisen mahduttaa, voit yrittää lisätä 56 kuvapistettä iframen korkeus alapalkissa koon mukaan. Jos raporttisivulla käytetään dynaamista kokoa, seuraavassa taulukossa on joitakin kokoja, joiden avulla voit mahduttaa sisällön ilman letterboxingia.

| Suhde | Koko | Dimensio (leveys x korkeus) |
| --- | --- | --- |
| 16:9 |Pieni |640 x 416 kuvapistettä |
| 16:9 |Keskikokoinen |800 x 506 kuvapistettä |
| 16:9 |Suuri |960 x 596 kuvapistettä |
| 4:3 |Pieni |640 x 536 kuvapistettä |
| 4:3 |Keskikokoinen |800 x 656 kuvapistettä |
| 4:3 |Suuri |960 x 776 kuvapistettä |

## <a name="manage-embed-codes"></a>Hallitse upotuskoodeja

Kun olet luonut **Julkaise verkkoon** upotuskoodin, voit hallita-koodeja **asetukset** Power BI-valikosta. Upotuskoodien hallinta sisältää kyvyn poistaa kohteen visualisoinnin tai raportin (upotuskoodin hahmontaminen käyttökelvottomia), tai upotuskoodin.

1. Voit hallita omia **Julkaise verkkoon** -upotuskoodeja avaamalla **Asetukset**-rataskuvakkeen ja valitsemalla **Hallitse upotuskoodeja**.

   ![PtW8](media/service-publish-to-web/publish_to_web8.png)

2. Upota koodit näkyvät.

   ![PtW9](media/service-publish-to-web/publish_to_web9.png)

3. Voit hakea tai poistaa upotuskoodin. Raportin tai visualisoinnin linkit sen poistaminen poistaa käytöstä.

   ![PtW10](media/service-publish-to-web/publish_to_web10.png)

4. Jos valitset **poistaa**, sinua pyydetään vahvistamaan toiminto.

   ![PtW11](media/service-publish-to-web/publish_to_web11.png)

## <a name="updates-to-reports-and-data-refresh"></a>Raporttien päivittäminen ja tietojen uudelleenlataus

Kun olet luonut oman **Julkaise verkkoon** upotuskoodin ja jakaa sen, raporttiin päivitetään kaikki muutokset teet upotuskoodi on heti aktiivinen ja kuka tahansa, joka avaa linkin voi tarkastella. Alkuperäinen toimintoa raporttien ja visualisointien päivitykset voi kuitenkin kestää noin tunnin, ennen kuin ne historiakyselyn näkyy käyttäjille. Jos haluat, että päivitykset ovat heti saatavilla, voit poistaa upotuskoodin ja luoda uuden upotuskoodin. Lisätietoja on artikkelissa [ **miten se toimii** ](#howitworks) myöhemmin tämän artikkelin kohdassa. 

## <a name="data-refresh"></a>Tietojen uudelleenlataus

Tietojen uudelleenlataukset näkyvät automaattisesti upotetussa raportissa tai visualisoinnissa. Voi kestää noin tunnin verran, ennen kuin uudelleenladatut tiedot näkyvät upotuskoodeissa. Voit poistaa automaattisen Uudelleenlatauksen käytöstä valitsemalla **eivät päivity** raportissa käytetään tietojoukon aikataulussa.  

## <a name="custom-visuals"></a>Mukautetut visualisoinnit

Mukautettuja visualisointeja tuetaan **Julkaise verkkoon** -toiminnossa. Kun käytät **Julkaise verkkoon**, käyttäjät, joiden kanssa jaat julkaistun visualisoinnin ei tarvitse ottaa käyttöön mukautettuja visualisointeja raportin tarkastelemiseksi.

## <a name="limitations"></a>Rajoitukset

**Julkaise verkkoon** tuetaan useimmissa tietolähteissä ja raporteissa Power BI-palvelun, alla on **ei tällä hetkellä tueta, tai käytettävissä** kanssa **Julkaise verkkoon** :

- Raportit, jotka käyttävät rivitason suojausta.
- Raportit, jotka käyttävät reaaliaikaisen yhteyden tietolähdettä, mukaan lukien paikallisesti isännöity Analysis Services Tabular, Analysis Services Multidimensional ja Azure Analysis Services.
- Raportit jaetaan sinulle suoraan tai organisaation sisältöpaketin kautta.
- Raportit ryhmässä, jonka muokkausjäsen et ole.
- ”R”-visualisointeja ei tällä hetkellä tueta **Julkaise verkkoon** raportteja.
- Tietojen vieminen visualisoinneista raportissa, joka on julkaistu verkkoon.
- ArcGIS Maps for Power BI-visualisointeja.
- Raporttitason DAX-mittayksikköjen sisältäviä raportteja.
- Mallien Sign-tietojen kyselyiden.
- [Luottamuksellisten tai omistusoikeudellisten tietojen](#publish-to-web-from-power-bi).
- **Upota**-vaihtoehdon tarjoama automaattisen todentamisen mahdollisuus ei toimi Power BI:n JavaScript-ohjelmointirajapinnan kanssa. Jos käytät Power BI:n JavaScript-ohjelmointirajapintaa, käytä upotuksessa [käyttäjä omistaa tiedot](developer/embed-sample-for-your-organization.md) -menetelmää. Lue lisää [käyttäjän omistamista tiedoista](developer/embed-sample-for-your-organization.md).

## <a name="tenant-setting"></a>Vuokraaja-asetukset

Power BI-järjestelmänvalvojat voivat ottaa käyttöön tai poistaa käytöstä **Julkaise verkkoon** ominaisuus. He voivat myös rajoittaa käyttöoikeuden tietyille ryhmille, mikä voi heikentää kykysi luoda upotuskoodin.

|Ominaisuus |Otettu käyttöön koko organisaatiolle |Otettu käyttöön koko organisaatiolle |Tietyt käyttöoikeusryhmät   |
|---------|---------|---------|---------|
|**Julkaise verkkoon** kohdassa raportin **tiedoston** valikko|Käytössä kaikille|Ei näkyvissä kaikille|Näkyvissä vain valtuutetuille käyttäjille tai ryhmille.|
|**Asetukset**-valikon **Upotuskoodien hallinta**|Käytössä kaikille|Käytössä kaikille|Käytössä kaikille.<br><br>* **Poista**-vaihtoehto vain valtuutetuille käyttäjille tai ryhmille.<br>* **Hae koodit** käytössä kaikille.|
|**Upotuskoodit** hallintaportaalissa|Tila ilmaisee jotain seuraavista:<br>* Aktiivinen<br>* Ei tuettu<br>* Estetty|Tilana näytetään **Ei käytössä**|Tila ilmaisee jotain seuraavista:<br>* Aktiivinen<br>* Ei tuettu<br>* Estetty<br><br>Jos käyttäjälle ei ole annettu oikeuksia vuokraaja-asetuksissa, tilana näytetään **Loukannut**.|
|Aiemmin luodut julkaistut raportit|Kaikki käytössä|Kaikki poissa käytöstä|Raportit näytetään jatkossakin kaikille.|

## <a name="understanding-the-embed-code-status-column"></a>Upotuskoodin tilan sarakkeen ymmärtäminen

**Upotettujen koodien hallinta** sivu sisältää status-sarakkeen. Oletusarvon mukaan upotuskoodit ovat **Active**, mutta myös voi olla jokin alla luetellut tiloista.

| Tila | Kuvaus |
| --- | --- |
| **Aktiivinen** |Internet-käyttäjät voivat tarkastella ja käsitellä raporttia. |
| **Estetty** |Raportin sisältö rikkoo [Power BI palveluehdot](https://powerbi.microsoft.com/terms-of-service). Microsoft on estänyt se. Ota yhteyttä tukeen, jos uskot, että sisältö on estetty virheellisesti. |
| **Ei tueta** |Raportin tietojoukko käyttää rivitason suojausta tai muuta määritystä, jota ei tueta. Katso [ **rajoitukset** ](#limitations) täydellinen luettelo-osassa. |
| **Loukannut** |Upotuskoodi on määritetyn vuokraajan käytännön ulkopuolella. Tämä tapahtuu yleensä silloin, kun upotuskoodi luotiin ja sitten **Julkaise verkkoon** vuokraaja-asetusta muutettiin sulkemalla ulkopuolelle käyttäjä, joka omistaa upotuskoodin. Jos vuokraaja-asetus on poistettu käytöstä tai käyttäjä ei enää voi luoda upotuskoodeja, aiemmin upottaa koodit Näytä **loukannut** tila. |

## <a name="how-to-report-a-concern-with-publish-to-web-content"></a>Miten voit ilmoittaa Julkaise verkkoon -sisältöä koskevan huolenaiheen

Raportin koskevan huolenaiheen käyttämällä **Julkaise verkkoon** verkkosivustoon tai blogiin upotettua sisältöä **lipun** kuvake alapalkissa, seuraavassa kuvassa esitetyllä tavalla. Sinua pyydetään lähettämään Microsoftille sähköpostiviesti joka selittää ilmoitukseen. Microsoft arvioi sitten sisällön Power BI käyttöehdot ja toteuttaa asianmukaisia toimenpiteitä.

Ilmoita huolenaiheesta valitsemalla **lipun** kuvake alas-palkista **Julkaise verkkoon** näet raportin.

![PtW12](media/service-publish-to-web/publish_to_web12_ga.png)

## <a name="licensing-and-pricing"></a>Käyttöoikeudet ja hinnoittelu

Sinun on oltava Microsoft Power BI:n käyttäjä, jotta voit käyttää **Julkaise verkkoon** -toimintoa. -Raportin katselijat ei tarvitse olla Power BI-käyttäjiä.

<a name="howitworks"></a>
## <a name="how-it-works-technical-details"></a>Miten se toimii (tekniset tiedot)

Kun luot upotuskoodin **Julkaise verkkoon**, raportti on Internet käyttäjät näkevät. Se on yleisesti saatavilla, joten tarkastelijat voivat helposti jakaa raportin sosiaalisen median kautta vastaisuudessa. Kun käyttäjät tarkastelevat raporttia joko avaamalla suoran julkisen URL-osoitteen tai tarkastelemalla sitä upotettuna verkkosivulle tai blogiin, Power BI piilottaa raportin määritelmän ja raportin tarkasteluun vaadittujen pyyntöjen tulokset. Näin voit varmistaa, että Tuhannet käyttäjät voivat tarkastella raporttia ilman suorituskykyyn.

Välimuisti on Pitkäkestoinen, joten jos päivität raportin määritelmää (esimerkiksi jos muutat sen näyttötilaa) tai raporttitietoja, voi kestää noin tunnin, ennen kuin muutokset näkyvät käyttäjien tarkastella raportin versiossa. Suosittelemme siksi, että suunnittelet työsi etukäteen, ja luot **Julkaise verkkoon** -upotuskoodin vain, kun olet tyytyväinen asetuksiin.

## <a name="next-steps"></a>Seuraavat vaiheet

- [SharePoint Online -raportin verkko-osa](service-embed-report-spo.md) 

- [Raportin upottaminen turvalliseen portaaliin tai sivustoon](service-embed-secure.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
