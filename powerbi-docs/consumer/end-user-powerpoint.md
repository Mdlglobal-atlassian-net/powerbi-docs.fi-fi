---
title: Raporttien vieminen Power BI:stä PowerPointiin
description: Lue, miten voit viedä Power BI -raportin PowerPointiin.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 12/04/2019
ms.author: mihart
LocalizationGroup: Share your work
ms.openlocfilehash: 25422b2503caed78e6e6518a855f6b23a0571a8c
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "74830574"
---
# <a name="export-reports-from-power-bi-to-powerpoint"></a>Raporttien vieminen Power BI:stä PowerPointiin

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Voit julkaista Power BI:llä raportin Microsoft PowerPointiin ja luoda helposti Power BI -raporttiin perustuvan diasarjan. PowerPointiin vietäessä tapahtuu seuraavaa:

* Jokaisesta Power BI -raportin sivusta tulee yksittäinen dia PowerPointissa.
* Power BI -raportin jokainen sivu viedään yksittäisenä suuritarkkuuksisena kuvana PowerPointiin.
* Voit säilyttää raporttiin lisäämäsi suodattimet ja osittajien asetukset.
* PowerPointissa luodaan linkki Power BI -raporttiin.

**Power BI -raportin** vieminen **PowerPointiin** on nopeaa. Seuraa seuraavassa osiossa kuvailtuja vaiheita.

## <a name="export-your-power-bi-report-to-powerpoint"></a>Power BI -raportin vieminen PowerPointiin
Valitse **Power BI** -palvelussa raportti, joka näytetään kankaalla. Voit myös valita raportin **aloitussivulta**, **sovelluksista** tai siirtymisruudun mistä tahansa muusta säilöstä.

Kun PowerPointiin vietävä raportti näkyy kankaalla, valitse **Vie** > **PowerPoint** valikkoriviltä.

![Valitse Vie valikkoriviltä](media/end-user-powerpoint/power-bi-export.png)

Näkyviin tulee ponnahdusikkuna, jossa on vaihtoehtoina **Nykyiset arvot** ja **Oletusarvot**. **Nykyiset arvot** vie raportin nykyisessä tilassa, johon sisältyvät ne aktiiviset muutokset, joita olet tehnyt osittajan ja suodattimen arvoihin. Useimmat käyttäjät valitsevat tämän vaihtoehdon. Vaihtoehtoisesti voit valita **Oletusarvot**-vaihtoehdon, joka vie raportin sen alkuperäisessä tilassa (jossa *suunnittelija* on jakanut sen) eikä sisällä mitään alkuperäiseen tilaan tekemiäsi muutoksia.

> [!NOTE]
> **Nykyiset arvot** eivät sisällä visualisointien vieritystilaa.

![Valitse vietävät asiat](media/end-user-powerpoint/power-bi-current-values.png)
 
Ponnahdusikkunassa on myös valintaruutu, jossa voit valita, viedäänkö raportin piilotetut välilehdet. Valitse tämä valintaruutu, jos haluat viedä vain sellaiset raportin välilehdet, joita voit tarkastella selaimessasi. Jos haluat viedä myös kaikki piilotetut välilehdet, jätä tämä valintaruutu tyhjäksi. Jos valintaruutu näkyy harmaana, raportissa ei ole piilotettuja välilehtiä. Piilotetusta välilehdestä esimerkkinä on työkalun vihje-välilehti. [Mukautetut työkaluvihjeet](../desktop-tooltips.md) luodaan raportin *suunnittelijoiden* toimesta, eivätkä ne näy raporttivälilehtinä Power BI -palvelussa *kuluttajille*. 

Kun olet tehnyt valintasi, jatka valitsemalla **Vie**. Näet Power BI -palvelun selainikkunan oikeassa yläkulmassa ilmoituspalkin, jossa ilmoitetaan raportin viemisestä PowerPointiin. Vieminen voi kestää joitakin minuutteja. Voi jatkaa Power BI:ssä työskentelemistä raportin viemisen aikana.

![Vienti PowerPointiin on kesken -ilmoitus](media/end-user-powerpoint/power-bi-export-progress.png)

Kun Power BI -palvelu on suorittanut viennin, ilmoituspalkissa näkyy ilmoitus siitä. Tiedostosi on käytettävissä sijainnissa, jossa selain näyttää ladatut tiedostot. Seuraavassa kuvassa se näkyy selainikkunan alareunan lataukset-palkissa.

![selainilmoitus näytön alareunassa](media/end-user-powerpoint/power-bi-browsers.png)

Siinä kaikki. Voit ladata tiedoston, avata sen PowerPointissa ja sitten muokata tai parannella sitä samoin kuin mitä tahansa muuta PowerPoint-esitystä.

## <a name="check-out-your-exported-powerpoint-file"></a>Viedyn PowerPoint-tiedoston tarkastelu
Kun avaat Power BI:ssä viedyn PowerPoint-tiedoston, löydät siitä muutamia hienoja ja hyödyllisiä ominaisuuksia. Tutustu seuraavaan kuvaan ja katso sitten numeroidut elementit, joissa on kuvattu joitain näistä kätevistä ominaisuuksista.

![PowerPoint aukeaa](media/end-user-powerpoint/power-bi-powerpoint.png)

1. Diapinon ensimmäinen sivu sisältää raportin nimen ja linkin, jonka avulla voit **tarkastella Power BI:ssä** raporttia, johon diat perustuvat.
2. Saat myös joitakin hyödyllisiä tietoja raportista. **Viimeisin tietojen päivitys** ilmaisee päivämäärän ja ajan, joihin viety raportti perustuu. **Ladattu osoitteesta** -kohdassa näkyy päivämäärä ja aika, jolloin Power BI -raportti on viety PowerPoint-tiedostoon.
3. Jokainen raporttisivu on erillinen dia. Ne näkyvät siirtymisruudussa. 
4. Julkaistu raportti hahmonnetaan Power BI -asetusten mukaisella kielellä tai muussa tapauksessa selaimen kieliasetuksen mukaan. Jos haluat tarkistaa kieliasetuksesi tai muuttaa sitä, valitse hammasrataskuvake ![Hammasrataskuvake](media/end-user-powerpoint/power-bi-settings-icon.png) > **Asetukset** > **Yleiset** > **Kieli**. Kielialueiden tiedot ovat ohjeartikkelissa [Power BI:n tuetut kielet ja maat tai alueet](../supported-languages-countries-regions.md).


Kun valitset yksittäisen dian, huomaat kunkin raporttisivun olevan riippumaton kuva.

![Näyttö, jossa jokainen visualisointi näkyy erillisenä kuvana](media/end-user-powerpoint/power-bi-images.png)

Edellä olevien vaiheiden jälkeen voit tehdä PowerPoint-esitykselläsi ja sen suuritarkkuuksisilla kuvilla mitä haluat.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Ota huomioon seuraavat seikat ja rajoitukset, kun käytät **Vieminen PowerPointiin** -ominaisuutta.

* R-visualisointeja ei tällä hetkellä tueta. Tällaiset visualisoinnit viedään tyhjinä kuvina PowerPointiin mukanaan virhesanoma siitä, ettei visualisointia tueta.
* Sertifioituja mukautettuja visualisointeja tuetaan. Saat lisätietoja sertifioiduista mukautetuista visualisoinneista, mukaan lukien sertifioinnin hakemisesta visualisoinnille, artikkelista [Mukautetun visualisoinnin sertifiointi](../developer/power-bi-custom-visuals-certified.md). Mukautettuja visualisointeja, joita ei ole sertifioitu, ei tueta. Ne viedään tyhjinä kuvina PowerPointiin mukanaan virhesanoma siitä, ettei visualisointia tueta.
* Yli 30 raporttisivua sisältäviä raportteja ei tällä hetkellä voi viedä.
* Vierityspalkkien visualisoinnit viedään niiden oletustilaan. Visualisoinnissa PowerPointissa näkyy vain tietojen ylin osa. Vieritys PowerPointissa ei ole käytettävissä, koska jokainen dia on kuva. 
* Raportin vieminen PowerPointiin saattaa kestää muutamia minuutteja. Kestoon vaikuttavat esimerkiksi raportin rakenne ja Power BI -palvelun kulloinenkin kuormitus.
* Jos **Vie PowerPointiin** -valikkovaihtoehtoa ei ole käytettävissä Power BI -palvelussa, syy on todennäköisesti se, että vuokraajan järjestelmänvalvoja on poistanut toiminnon käytöstä. Saat lisätietoja ottamalla yhteyttä vuokraajan järjestelmänvalvojaan.
* Taustakuvat rajataan kaavion raja-alueen mukaiseksi. Suosittelemme poistamaan taustakuvat ennen PowerPointiin viemistä.
* PowerPoint-sivut luodaan aina 9:16-standardikoossa riippumatta alkuperäisen Power BI -raportin sivujen koosta tai mittasuhteista.
* PowerPointiin ei voi julkaista raportteja, jotka ovat vuokraajan Power BI -toimialueen ulkopuolisen käyttäjän omistamia (esimerkiksi. organisaation ulkopuolisen henkilön omistama raportti, joka on jaettu kanssasi).
* Jos jaat raporttinäkymän organisaatiosi ulkopuoliselle henkilölle (joka ei ole Power BI -vuokraajasi toimialueella), kyseinen henkilö ei voi viedä jaettuun raporttinäkymään liittyviä raportteja PowerPointiin. Jos olet esimerkiksi aaron@contoso.com, voit jakaa sisältöä käyttäjän david@cohowinery.com kanssa. Käyttäjä david@cohowinery.com ei kuitenkaan voi viedä siihen liittyviä raportteja PowerPointiin.
* Vienti ei välttämättä toimi PowerPointin aiempien versioiden kanssa.
* Kuten edellä mainittiin, kukin raporttisivu viedään PowerPoint-tiedostoon yhtenä kuvana.
* Power BI -palvelu käyttää PowerPoint-viennin kielenä Power BI:n kieliasetusta. Jos haluat tarkistaa kieliasetuksesi tai muuttaa sitä, valitse hammasrataskuvake ![Hammasrataskuvake](media/end-user-powerpoint/power-bi-settings-icon.png) > **Asetukset** > **Yleiset** > **Kieli**.
* Viedyn PowerPoint-tiedoston kansidian **Latausajankohta**-kellonajaksi määritetään tietokoneesi aikavyöhyke vientihetkellä.
* URL-suodattimia ei oteta tällä hetkellä huomioon, kun valitset viennin kohdalla **Nykyiset arvot**.

## <a name="next-steps"></a>Seuraavat vaiheet
[Raportin tulostaminen](end-user-print.md)
