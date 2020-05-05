---
title: Power BI:n Julkaise verkkoon -toiminto
description: Power BI:n Julkaise verkkoon -toiminnolla voit helposti upottaa vuorovaikutteisia Power BI -visualisointeja blogijulkaisuihin, sivustoihin, sähköpostiviesteihin tai sosiaaliseen mediaan.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/25/2020
LocalizationGroup: Share your work
ms.openlocfilehash: 1a3d4c264e343382422cbe2a881b5fcedaa19e13
ms.sourcegitcommit: 20f15ee7a11162127e506b86d21e2fff821a4aee
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/29/2020
ms.locfileid: "82585238"
---
# <a name="publish-to-web-from-power-bi"></a>Power BI:n Julkaise verkkoon -toiminto

Power BI:n **Julkaise verkkoon** -toiminnolla voit helposti upottaa vuorovaikutteisia Power BI -visualisointeja blogijulkaisuihin, sivustoihin, sähköpostiviesteihin tai sosiaaliseen mediaan. Voit myös helposti muokata, päivittää ja ladata uudelleen julkaistuja visualisointeja tai lopettaa niiden jakamisen.

> [!WARNING]
> Kun käytät **Julkaise verkkoon** -toimintoa, kuka tahansa Internetissä voi tarkastella julkaisemaasi raporttia tai visualisointia. Katseleminen ei edellytä todentamista. Tämä sisältää raportteihin yhdistetyt yksityiskohtaisen tason tiedot. Varmista ennen raportin julkaisemista, että sinulla on oikeus jakaa tiedot ja visualisoinnit julkisesti. Älä julkaise luottamuksellisia tai omistusoikeudellisia tietoja. Jos olet epävarma, tarkista organisaatiosi käytännöt ennen julkaisemista.

>[!Note]
>Voit upottaa sisältösi turvallisesti sisäiseen portaaliin tai sivustoon. Käytä [Upota](service-embed-secure.md)- tai [Upota SharePoint Onlinessa](service-embed-report-spo.md) -asetuksia. Nämä asetukset varmistavat, että kaikkien oikeuksien ja tietosuojan soveltaminen pakotetaan, kun käyttäjät tarkastelevat sisäisiä tietoja.

## <a name="create-embed-codes-with-publish-to-web"></a>Upotuskoodien luominen Julkaise verkkoon -toiminnolla

**Julkaise verkkoon** -toiminto on käytettävissä henkilökohtaisessa työtilassasi ja ryhmän työtiloissa raporteille, joita voit muokata.  Se ei ole käytettävissä raporteissa, jotka on jaettu kanssasi tai joissa tiedot suojataan rivitason suojauksella. Katso alla olevasta [**Rajoitukset**](#limitations)-osiosta täydellinen luettelo tapauksista, joissa **Julkaise verkkoon** -toimintoa ei tueta. Tutustu tässä artikkelissa aiemmin mainittuun **varoitukseen**, ennen kuin käytät **Julkaise verkkoon** -toimintoa.

Seuraavasta lyhyestä videosta, näet miten tämä toiminto toimii. Kokeile sitä sitten itse alla olevien ohjeiden mukaisesti.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UF9QtqE7s4Y" frameborder="0" allowfullscreen></iframe>

Seuraavissa vaiheissa kuvataan, miten voit käyttää **Julkaise verkkoon** -toimintoa.

1. Avaa työtilassasi raportti, jota voit muokata, ja valitse **Lisää vaihtoehtoja (...)**   > **Upota** >  **Julkaise verkkoon (julkinen)** .

   ![Lisää vaihtoehtoja -valikon Julkaise verkkoon -vaihtoehto](media/service-publish-to-web/power-bi-more-options-publish-web.png)
   
2. Jos Power BI -järjestelmänvalvojasi ei ole sallinut sinun luoda upotuskoodeja, sinun on ehkä otettava häneen yhteyttä.

   ![Yhteyden ottaminen Power BI -järjestelmänvalvojaan](media/service-publish-to-web/publish_to_web_admin_prompt.png)
   
   Jos haluat ohjeita sen henkilön löytämiseen, joka voi ottaa Julkaise verkkoon -toiminnon käyttöön organisaatiossasi, katso kohtaa [Yhteyden ottaminen Power BI -järjestelmänvalvojaasi](#find-your-power-bi-administrator) jäljempänä tässä artikkelissa.

3. Tarkista valintaikkunan sisältö ja valitse **Luo upotuskoodi**.

   ![Tarkista upottaminen julkiseen sivustoon](media/service-publish-to-web/publish_to_web2_ga.png)

4. Tarkista varoitus (joka näkyy tässä) ja varmista, että tiedot voidaan upottaa julkiselle verkkosivustolle. Jos näin on, valitse **Julkaise**.

   ![Tarkista varoitus](media/service-publish-to-web/publish_to_web3_ga.png)

5. Näyttöön avautuu valintaikkuna, jossa on linkki. Valitse sähköpostitse lähetettävä linkki tai kopioi HTML-tiedosto. Voit upottaa sen koodiin (esimerkiksi iFrame) tai liittää sen suoraan verkkosivulle tai blogiin.

   ![Onnistui: linkki ja HTML](media/service-publish-to-web/publish_to_web4.png)

6. Jos loit aiemmin raportille upotuskoodin ja valitset **Julkaise verkkoon**, et näe valintaikkunoita vaiheissa 2–4. Näet sen sijaan **upotuskoodin** valintaikkunan:

   ![Upotuskoodi-valintaikkuna](media/service-publish-to-web/publish_to_web5.png)

   Voit luoda vain yhden upotuskoodin kullekin raportille.


### <a name="tips-for-view-modes"></a>Vihjeitä näkymätiloja varten

Kun upotat sisältöä blogitekstiin, sinun on yleensä sovitettava se tiettyyn näyttökokoon.  Voit muokata leveyttä ja korkeutta iFrame-tunnisteella tarvittaessa. Sinun on kuitenkin myös varmistettava, että raporttisi mahtuu iFramelle varatulle alueelle, ja määritettävä siten asianmukainen näyttötila raporttia muokattaessa.

Seuraavassa taulukossa on ohjeita näyttötilasta ja siitä, miten se tulee näkyviin upotettuna.

| Näyttötila | Miltä se näyttää upotettuna |
| --- | --- |
| ![PtW6b](media/service-publish-to-web/publish_to_web6b.png) |**Sovita sivulle** noudattaa raportin sivun korkeutta ja leveyttä. Jos määrität sivun *dynaamisille* kuvasuhteille (esimerkiksi 16:9 tai 4:3), sisältösi skaalautuu siten, että se mahtuu iFrameen. Kun sisältö upotetaan iFrameen, **Sovita sivulle** -asetuksen käyttäminen voi aiheuttaa näyttöön *palkkeja* siten, että iFramen alueilla näkyy harmaa tausta sisällön jälkeen, koska sitä skaalataan mahtumaan iFrameen. Voit minimoida tämän vaikutuksen määrittämällä iFramen korkeuden ja leveyden asianmukaisesti. |
| ![PtW6d](media/service-publish-to-web/publish_to_web6d.png) |**Todellinen koko** varmistaa, että raportin koko säilyy siten kuin se on määritetty raporttisivulle. Tämän vuoksi iFramessa voi olla vierityspalkkeja. Määritä iFramen korkeus ja leveys siten, että vältät vierityspalkit. |
| ![PtW6c](media/service-publish-to-web/publish_to_web6c.png) |**Sovita leveyteen** -komento varmistaa, että sisältö mahtuu iFramen vaakasuuntaiselle alueelle. Reuna näkyy edelleen, mutta sisältö skaalataan siten, että se käyttää kaikkea saatavilla olevaa vaakasuuntaista tilaa. |

### <a name="tips-for-iframe-height-and-width"></a>Vihjeitä iFramen korkeuteen ja leveyteen

**Julkaise verkkoon** -upotuskoodi näyttää tältä:

![PtW7](media/service-publish-to-web/publish_to_web7.png)
 
Voit muokata leveyttä ja korkeutta manuaalisesti haluamallasi tavalla, jotta sisältö mahtuu sivulle, johon sen upotat.

Jos haluat sovittaa sisällön vieläkin paremmin, voit yrittää lisätä 56 kuvapistettä iFramen korkeuteen, jotta alapalkin nykyinen koko huomioidaan. Jos raporttisivulla käytetään dynaamista kokoa, seuraavassa taulukossa on joitakin kokoja, joiden avulla voit mahduttaa sisällön ilman palkkiutumista.

| Suhde | Koko | Dimensio (leveys x korkeus) |
| --- | --- | --- |
| 16:9 |Pieni |640 x 416 kuvapistettä |
| 16:9 |Keskitaso |800 x 506 kuvapistettä |
| 16:9 |Suuri |960 x 596 kuvapistettä |
| 4:3 |Pieni |640 x 536 kuvapistettä |
| 4:3 |Keskitaso |800 x 656 kuvapistettä |
| 4:3 |Suuri |960 x 776 kuvapistettä |

## <a name="manage-embed-codes"></a>Hallitse upotuskoodeja

Kun olet luonut **Julkaise verkkoon** -upotuskoodin, voit hallita koodeja Power BI -palvelun **Asetukset**-valikosta. Upotuskoodien hallinta sisältää mahdollisuuden poistaa koodin kohdevisualisointi tai raportti (upotuskoodia ei voida tämän jälkeen käyttää) tai upotuskoodin hakeminen.

1. Voit hallita omia **Julkaise verkkoon** -upotuskoodeja avaamalla **Asetukset**-rataskuvakkeen ja valitsemalla **Hallitse upotuskoodeja**.

   ![Hallitse upotuskoodeja](media/service-publish-to-web/publish_to_web8.png)

2. Näet upotuskoodisi.

   ![PtW9](media/service-publish-to-web/publish_to_web9.png)

3. Voit joko hakea tai poistaa upotuskoodin. Jos poistat sen, tämä poistaa kaikki linkit tähän raporttiin tai visualisointiin.

   ![PtW10](media/service-publish-to-web/publish_to_web10.png)

4. Jos valitset **Poista**, sinulta pyydetään vahvistusta.

   ![PtW11](media/service-publish-to-web/publish_to_web11.png)

## <a name="updates-to-reports-and-data-refresh"></a>Raporttien päivittäminen ja tietojen uudelleenlataus

Kun olet luonut oman **Julkaise verkkoon** -upotuskoodin ja jakanut sen, raporttiin päivitetään kaikki tekemäsi muutokset. Lisäksi upotuskoodilinkki on heti käytettävissä. Kuka tahansa linkin avaava näkee sisällön. Tämän ensimmäisen toiminnon jälkeen raporttien ja visualisointiesi päivitysten näkyminen käyttäjille saattaa kuitenkin kestää kahdesta kolmeen tuntia. Saat lisätietoja tässä artikkelissa olevasta [**Miten se toimii**](#howitworks) -osiosta. 

### <a name="data-refresh"></a>Tietojen uudelleenlataus

Tietojen uudelleenlataukset näkyvät automaattisesti upotetussa raportissa tai visualisoinnissa. Päivitettyjen tietojen näkyminen upotuskoodeissa voi kestää noin tunnin. Voit poistaa automaattisen päivityksen käytöstä valitsemalla raportin käyttämän tietojoukon aikataulussa **Älä päivitä**.  

## <a name="power-bi-visuals"></a>Power BI:n visualisoinnit

Power BI -visualisointeja tuetaan **Julkaise verkkoon** -toiminnossa. Kun käytät **Julkaise verkkoon** -toimintoa, niiden käyttäjien, joiden kanssa jaat julkaistun visualisoinnin, ei tarvitse ottaa käyttöön Power BI -visualisointeja raportin tarkastelemista varten.

## <a name="understanding-the-embed-code-status-column"></a>Upotuskoodin tilan sarakkeen ymmärtäminen

>[!Note]
>Tarkista usein julkaistut upotuskoodit. Poista ne, joiden ei enää tarvitse olla julkisesti käytettävissä.

**Hallitse upotuskoodeja** -sivulla on tilasarake. Upotuskoodit ovat oletusarvoisesti **aktiivisia**, mutta tila voi olla myös jokin alla luetelluista.

| Tila | Kuvaus |
| --- | --- |
| **Aktiivinen** |Internet-käyttäjät voivat tarkastella ja käsitellä raporttia. |
| **Estetty** |Raportin sisältö rikkoo [Power BI:n käyttöehtoja](https://powerbi.microsoft.com/terms-of-service). Microsoft on estänyt sen. Ota yhteyttä tukeen, jos uskot, että sisältö on estetty virheellisesti. |
| **Ei tueta** |Raportin tietojoukko käyttää rivitason suojausta tai muuta määritystä, jota ei tueta. Katso täydellinen luettelo [**Rajoitukset**](#limitations)-osiosta. |
| **Loukannut** |Upotuskoodi on määritetyn vuokraajan käytännön ulkopuolella. Tämä tila ilmenee yleensä, kun vuokraajan **Julkaise verkkoon** -asetusta muutetaan upotuskoodin luomisen jälkeen sulkemalla ulkopuolelle käyttäjä, joka omistaa upotuskoodin. Jos vuokraaja-asetus on poistettu käytöstä tai käyttäjä ei enää voi luoda upotuskoodeja, aiemmin luotujen upotuskoodien tilana on **Loukannut**. Katso lisätietoja tämän artikkelin kohdasta kohdasta [Yhteyden ottaminen Power BI -järjestelmänvalvojaasi](#find-your-power-bi-administrator). |

## <a name="report-a-concern-with-publish-to-web-content"></a>Julkaise verkkoon -sisältöä koskevasta huolenaiheesta ilmoittaminen

Voit ilmoittaa sivustoon tai blogiin upotettua **Julkaise verkkoon** -sisältöä koskevan huolenaiheen valitsemalla **Julkaise verkkoon** -raportin alapalkissa olevan **Lippu**-kuvakkeen.

![PtW12](media/service-publish-to-web/publish_to_web12_ga.png)

Sinua pyydetään lähettämään Microsoftille sähköpostiviesti, jossa selität huolenaiheen. Microsoft arvioi sitten sisällön [Power BI:n käyttöehtojen](https://powerbi.microsoft.com/terms-of-service) mukaisesti ja ryhtyy asianmukaisiin toimenpiteisiin.

## <a name="licensing"></a>Käyttöoikeudet

Sinun on oltava Microsoft Power BI:n käyttäjä, jotta voit käyttää **Julkaise verkkoon** -toimintoa. Raporttisi käyttäjien ei tarvitse olla Power BI:n käyttäjiä.

<a name="howitworks"></a>
## <a name="how-it-works-technical-details"></a>Miten se toimii (tekniset tiedot)

Kun luot upotuskoodin **Julkaise verkkoon** -toiminnolla, käyttäjät Internetissä näkevät raportin. Se on yleisesti saatavilla, joten käyttäjät voivat helposti jakaa raportin sosiaalisessa mediassa jatkossa. Kun käyttäjät tarkastelevat raporttia joko avaamalla suoran julkisen URL-osoitteen tai tarkastelemalla sitä upotettuna verkkosivulle tai blogiin, Power BI piilottaa raportin määritelmän ja raportin tarkasteluun vaadittujen pyyntöjen tulokset. Tämän välimuistin ansiosta tuhannet käyttäjät voivat tarkastella raporttia samanaikaisesti suorituskyvyn kärsimättä.

Välimuisti on pitkäkestoinen. Jos päivität raportin määritelmää (esimerkiksi muuttamalla sen näyttötilaa) tai lataat uudelleen raporttitietoja, voi siksi kestää noin tunnin, ennen kuin muutokset näkyvät käyttäjien tarkastelemassa raportin versiossa. Siksi suosittelemme, että suunnittelet työsi etukäteen, ja luot **Julkaise verkkoon** -upotuskoodin vain, kun olet tyytyväinen asetuksiin.

## <a name="find-your-power-bi-administrator"></a>Yhteyden ottaminen Power BI -järjestelmänvalvojaasi

Power BI -hallintaportaalissa on asetuksia, jotka ohjaavat sitä, kuka voi julkaista verkkoon. Hallintaportaalin [Julkaise verkkoon -vuokraaja-asetusten](service-admin-portal.md#publish-to-web) muuttaminen edellyttää organisaatiosi [Power BI -järjestelmänvalvojan](service-admin-role.md) apua.

Jos olet Power BI:tä käyttävä yksityishenkilö tai jos organisaatio on pieni, Power BI -järjestelmänvalvojaa ei ehkä ole määritetty. Seuraa [vuokraajan järjestelmänvalvojan haltuunoton](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover) ohjeita. Kun Power BI -järjestelmänvalvoja on määritetty, hän voi antaa sinulle oikeudet luoda upotuskoodeja.

Vakiintuneissa organisaatioissa on yleensä Power BI -järjestelmänvalvoja entuudestaan. Seuraavissa rooleissa toimivat käyttäjät voivat toimia Power BI -järjestelmänvalvojana:

- Office 365 -järjestelmänvalvojat
- Azure Active Directory -järjestelmänvalvojat
- Käyttäjät, joilla on Power BI -palvelun järjestelmänvalvojan rooli Azure Active Directoryssä

Sinun pitää [löytää joku näistä henkilöistä](https://docs.microsoft.com/office365/admin/admin-overview/admin-overview#who-has-admin-permissions-in-my-business) organisaatiossasi ja pyytää häntä päivittämään [Julkaise verkkoon -vuokraaja-asetukset](service-admin-portal.md#publish-to-web) hallintaportaalissa.

## <a name="limitations"></a>Rajoitukset

**Julkaise verkkoon** -toimintoa tuetaan suurimmassa osassa tietolähteitä ja raportteja Power BI -palvelussa. Seuraavan kaltaisia raportteja ei kuitenkaan tällä hetkellä tueta tai ne eivät ole käytettävissä **Julkaise verkkoon** -toiminnossa:

- Raportit, jotka käyttävät rivitason suojausta.
- Raportit, jotka käyttävät reaaliaikaisen yhteyden tietolähdettä, mukaan lukien paikallisesti isännöity Analysis Services Tabular, Analysis Services Multidimensional ja Azure Analysis Services.
- Raportit, jotka käyttävät [jaettua tietojoukkoa](service-datasets-across-workspaces.md), joka on tallennettu eri työtilaan kuin raportti.
- [Jaettuja ja sertifioituja tietojoukkoja ei tueta](service-datasets-share.md).
- Raportit jaetaan sinulle suoraan tai organisaation sisältöpaketin kautta.
- Raportit työtilassa, jonka muokkausjäsen et ole.
- R-visualisointeja ei tällä hetkellä tueta **Julkaise verkkoon** -raporteissa.
- Tietojen viemistä visualisoinneista raportissa, joka on julkaistu verkkoon, ei tueta.
- Power BI -visualisointien ArcGIS Maps -karttoja ei tueta.
- Raportit, jotka sisältävät raporttitason DAX-mittareita, ei tueta.
- Kertakirjautumista tietokyselymalleissa ei tueta.
- Luottamuksellisia tai omistusoikeudellisia tietoja ei tueta.
- **Upota**-vaihtoehdon tarjoama automaattisen todentamisen mahdollisuus ei toimi Power BI:n JavaScript-ohjelmointirajapinnan kanssa. Jos käytät Power BI:n JavaScript-ohjelmointirajapintaa, käytä upotuksessa [käyttäjä omistaa tiedot](developer/embedded/embed-sample-for-your-organization.md) -menetelmää.

## <a name="next-steps"></a>Seuraavat vaiheet

- [SharePoint Online -raportin verkko-osa](service-embed-report-spo.md) 

- [Raportin upottaminen turvalliseen portaaliin tai sivustoon](service-embed-secure.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
