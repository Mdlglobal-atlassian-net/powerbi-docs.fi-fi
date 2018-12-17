---
title: Raporttien vieminen Power BI kuluttajille -versiosta PowerPointiin
description: Lue, miten voit viedä Power BI -raportin PowerPointiin.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/13/2018
ms.author: mihart
LocalizationGroup: Share your work
ms.openlocfilehash: a865c98a5bacd526a553354ea828e86fa0155a79
ms.sourcegitcommit: 4f46d71ff6026c1c158f007425aefdcb501f48ee
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/06/2018
ms.locfileid: "52979256"
---
# <a name="export-reports-from-power-bi-to-powerpoint"></a>Raporttien vieminen Power BI:stä PowerPointiin
Voit julkaista Power BI:llä raportin **Microsoft PowerPointiin** ja luoda helposti Power BI -raporttiin perustuvan diasarjan. **PowerPointiin vietäessä** tapahtuu seuraavaa:

* Jokaisesta Power BI -raportin sivusta tulee yksittäinen dia PowerPointissa
* Power BI -raportin jokainen sivu viedään yksittäisenä, korkean resoluution kuvana PowerPointiin <!-- * The filters and slicers settings that you added to the report are preserved. -->
* PowerPointissa luodaan linkki Power BI -raporttiin 

**Power BI -raportin** vieminen **PowerPointiin** on nopeaa. Seuraa seuraavassa osiossa kuvailtuja vaiheita.

## <a name="how-to-export-your-power-bi-report-to-powerpoint"></a>Power BI -raportin vieminen PowerPointiin
Valitse Power BI -palvelussa raportti, joka näytetään kankaalla. Voit myös valita raportin **aloitussivulta**, **sovelluksista** tai vasemman siirtymisruudun mistä tahansa osasta.

![](media/end-user-powerpoint/power-bi-publish.png)

Kun PowerPointiin vietävä raportti näkyy kankaalla, valitse **Tiedosto > Vie PowerPointiin** Power BI -palvelun valikkoriviltä.

![](media/end-user-powerpoint/powerbi_to_powerpoint_1.png)

Näet Power BI -palvelun selainikkunan oikeassa yläkulmassa ilmoituspalkin, jossa ilmoitetaan raportin viemisestä PowerPointiin. Raportin vieminen voi kestää muutamia minuutteja, minkä aikana voit jatkaa Power BI:ssä työskentelemistä.

![](media/end-user-powerpoint/powerbi_to_powerpoint_2.png)

Kun vieminen on valmis, ilmoituspalkissa kerrotaan, että Power BI -palvelu on suorittanut viennin.

![](media/end-user-powerpoint/powerbi_to_powerpoint_3.png)

Tiedostosi on käytettävissä sijainnissa, jossa selain näyttää ladatut tiedostot. Seuraavassa kuvassa se näkyy selainikkunan alareunan lataukset-palkissa.

![](media/end-user-powerpoint/powerbi_to_powerpoint_4.png)

Siinä kaikki. Voit ladata tiedoston, avata sen PowerPointissa ja sitten muokata tai parannella sitä aivan kuin mitä tahansa muuta PowerPoint-esitystä.

## <a name="checking-out-your-exported-powerpoint-file"></a>Viedyn PowerPoint-tiedoston tarkastelu
Kun avaat Power BI:ssä viedyn PowerPoint-tiedoston, löydät siitä muutamia hienoja ja hyödyllisiä ominaisuuksia. Tutustu seuraavaan kuvaan ja katso sitten alla olevat numeroidut elementit, joissa on kuvattu joitain näistä ominaisuuksista.

![](media/end-user-powerpoint/powerbi_to_powerpoint_5.png)

1. Diapinon ensimmäinen sivu sisältää raportin nimen ja linkin, jonka avulla voit **tarkastella Power BI:ssä** raporttia, johon diat perustuvat.
2. Lisäksi saat käyttöösi joitakin hyödyllisiä raporttia koskevia tietoja, kuten viedyn raportin pohjana olleiden *tietojen viimeisimmän päivitysajankohdan* sekä *latauksen ajankohdan* eli sen päivämäärän ja kellonajan, jolloin Power BI -raportti vietiin PowerPoint-tiedostoon.
3. Jokainen raporttisivu on erillinen dia. Ne näkyvät vasemmassa siirtymisruudussa. 
4. Julkaistu raportti hahmonnetaan Power BI -asetusten mukaisella kielellä tai muussa tapauksessa selaimen kieliasetuksen mukaan. Jos haluat nähdä kieliasetuksesi tai muuttaa sitä, valitse hammasrataskuvake ![](media/end-user-powerpoint/power-bi-settings-icon.png) **> Asetukset > Yleiset > Kieli**. Kielialueiden tiedot ovat ohjeartikkelissa [Power BI:n tuetut kielet ja maat tai alueet](../supported-languages-countries-regions.md).
5. PowerPoint-esitys sisältää kansilehden, jossa viennin kellonaika näytetään oikealla aikavyöhykkeen ajassa.

Kun valitset yksittäisen dian, huomaat kunkin raporttisivun olevan riippumaton kuva.

>[!NOTE]
> Yhden kuvan luominen jokaista raportin sivua kohden on uusi ominaisuus. Aiemmin jokaisesta visualisoinnista luotiin erillinen kuva. Tätä ominaisuutta ei enää käytetä. 
 

![](media/end-user-powerpoint/powerbi_to_powerpoint_6.png)

Edellä olevien vaiheiden jälkeen voit tehdä PowerPoint-esitykselläsi ja sen korkearesoluutioisilla kuvilla mitä ikinä haluat.

## <a name="limitations"></a>Rajoitukset
Huomioi seuraavat seikat ja rajoitukset, kun käytät **Vieminen PowerPointiin** -ominaisuutta.

* Istunnon sisäinen vuorovaikutteisuus, kuten korostus ja suodatus sekä porautuminen, eivät vielä ole vielä tuettuja ominaisuuksia PowerPointiin vietäessä. Viety PowerPoint näyttää alkuperäiset visualisoinnit sellaisina kuin ne tallennettiin raporttiin. Jos olet käyttänyt suodattimia ja osittajia ja haluat säilyttää ne viennissä, tallenna raportti ja vie se tallentamisen jälkeen.
* **R-visualisointeja** ei tällä hetkellä tueta. Tällaiset visualisoinnit viedään tyhjinä kuvina PowerPointiin virhesanoman kanssa, jossa ilmoitetaan, ettei visualisointia tueta.
* **Sertifioituja** **mukautettuja visualisointeja** tuetaan. Saat lisätietoja sertifioiduista mukautetuista visualisoinneista, mukaan lukien sertifioinnin hakemisesta visualisoinnille, artikkelista [Mukautetun visualisoinnin sertifiointi](../power-bi-custom-visuals-certified.md). Ei-sertifioidut mukautetut visualisoinnit viedään tyhjinä kuvina PowerPointiin virhesanoman kanssa, jossa ilmoitetaan, ettei visualisointia tueta.
* Yli 30 raporttisivua sisältäviä raportteja ei tällä hetkellä voi viedä.
* Raportin vieminen PowerPointiin saattaa kestää muutamia minuutteja. Kestoon vaikuttavat mm. raportin rakenne ja Power BI -palvelun senhetkinen kuormitus.
* Jos **Vie PowerPointiin** -valikkovaihtoehtoa ei ole käytettävissä Power BI -palvelussa, syy on todennäköisesti se, että vuokraajan järjestelmänvalvoja on poistanut toiminnon käytöstä. Saat lisätietoja ottamalla yhteyttä vuokraajan järjestelmänvalvojaan.
* Taustakuvat rajataan kaavion raja-alueen mukaiseksi. Suosittelemme poistamaan taustakuvat ennen PowerPointiin viemistä.
* PowerPoint-sivut luodaan aina 9:16-standardikoossa riippumatta alkuperäisen Power BI -raportin sivujen koosta tai mittasuhteista.
* PowerPointiin ei voi julkaista raportteja, jotka ovat vuokraajan Power BI -toimialueen ulkopuolisen käyttäjän omistamia (esim. organisaation ulkopuolisen henkilön omistama raportti, joka on jaettu kanssasi).
* Jos jaat raporttinäkymän organisaatiosi ulkopuoliselle henkilölle (joka ei ole Power BI -vuokraajasi toimialueella), kyseinen henkilö ei voi viedä jaettuun raporttinäkymään liittyviä raportteja PowerPointiin. Jos olet esimerkiksi aaron@contoso.com, voit jakaa sisältöä käyttäjän david@cohowinery.com kanssa. david@cohowinery.com ei kuitenkaan voi viedä siihen liittyviä raportteja PowerPointiin.
* Kuten edellä mainittiin, kukin raporttisivu viedään PowerPoint-tiedostoon yhtenä kuvana.
* Power BI -palvelu käyttää PowerPoint-viennin kielenä Power BI:n kieliasetusta. Jos haluat nähdä kieliasetuksesi tai muuttaa sitä, valitse hammasrataskuvake ![](media/end-user-powerpoint/power-bi-settings-icon.png) **> Asetukset > Yleiset > Kieli**.
* Viedyn PowerPoint-tiedoston kansidian **Latausajankohta**-kellonajaksi määritetään tietokoneesi aikavyöhyke vientihetkellä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Raportin tulostaminen](end-user-print.md)