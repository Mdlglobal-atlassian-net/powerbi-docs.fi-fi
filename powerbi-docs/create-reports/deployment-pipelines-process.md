---
title: Käyttöönottojakson prosessi
description: Tutustu Power BI -käyttöönottojakson prosessiin
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.date: 05/06/2020
ms.openlocfilehash: c4a823b0b41def6c10cd8f932bb97e91eb977ecb
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83148614"
---
# <a name="understand-the-deployment-process-preview"></a>Käyttöönottoprosessin ymmärtäminen (esikatselu)

Käyttöönottoprosessin avulla voit kloonata sisältöä jakson yhdestä vaiheesta toiseen, tavallisesti kehityksestä testaukseen ja testauksesta tuotantoon.

Power BI kopioi käyttöönoton aikana nykyisen vaiheen sisällön kohteeksi yksi. Kopioitujen kohteiden väliset yhteydet säilytetään kopiointiprosessin aikana. Power BI soveltaa myös määritettyjä tietojoukkosääntöjä kohdevaiheen päivitettyyn sisältöön. Sisällön ottaminen käyttöön voi kestää jonkin aikaa riippuen siitä, montako kohdetta otetaan käyttöön. Tällä välin voit siirtyä muille sivuille Power BI -portaalissa, mutta et voi käyttää sisältöä kohdevaiheessa.

## <a name="deploying-content-to-an-empty-stage"></a>Sisällön ottaminen käyttöön tyhjässä vaiheessa

Kun otat sisältöä käyttöön tyhjässä vaiheessa, niiden raporttien, koontinäyttöjen ja tietojoukkojen metatiedot, joita olet ottamassa käyttöön, kopioidaan vaiheeseen, johon olet ottamassa niitä käyttöön. Uuteen työtilaan käyttöön otetulle tilalle luodaan Premium-kapasiteetti.

Voit ottaa sisällön käyttöön vaiheesta seuraavaan kahdella tavalla. Voit ottaa käyttöön koko sisällön tai voit [valita, mitkä sisältökohteet otetaan käyttöön](deployment-pipelines-get-started.md#selective-deployment).

Voit myös ottaa käyttöön sisältöä käyttöönottojakson myöhemmässä vaiheessa taaksepäin aiempaan versioon.

Kun käyttöönotto on valmis, päivitä tietojoukot niin, että voit käyttää uutta, kopioitua sisältöä. Tietojoukon päivitystä vaaditaan, koska tietoja ei kopioida yhdestä vaiheesta toiseen. Jos haluat tietää, mitkä kohteen ominaisuudet kopioidaan käyttöönottoprosessin aikana ja mitä kohteen ominaisuuksia ei kopioida, tarkista osio [Kopioitavat kohteen ominaisuudet käyttöönoton aikana](#item-properties-copied-during-deployment).

### <a name="creating-a-premium-capacity-workspace"></a>Premium-kapasiteetin työtilan luominen

Käyttöönottojaksot tarkistetaan ensimmäisen käyttöönottokerran aikana, jos sinulla on Premium-kapasiteetin käyttöoikeudet.  

Jos sinulla on kapasiteetin käyttöoikeudet, työtilan sisältö kopioidaan siihen vaiheeseen, johon olet ottamassa sitä käyttöön, ja tämän vaiheen uusi työtila luodaan Premium-kapasiteettiin.

Jos sinulla ei ole kapasiteetin käyttöoikeuksia, työtila luodaan, mutta sisältöä ei kopioida. Voit pyytää kapasiteetin järjestelmänvalvojaa lisäämään työtilasi kapasiteettiin tai pyytämällä kapasiteetin määrityksen käyttöoikeuksia. Myöhemmin, kun työtila on määritetty kapasiteettiin, voit ottaa sisältöä käyttöön tässä työtilassa.

### <a name="workspace-and-content-ownership"></a>Työtila ja sisällön omistajuus

Käyttöön ottavasta käyttäjästä tulee automaattisesti kloonattujen tietojoukkojen tietojoukon omistaja ja vain uuden työtilan järjestelmänvalvoja.

## <a name="deploy-content-to-an-existing-workspace"></a>Sisällön käyttöönotto aiemmin luotuun työtilaan

Sisällön käyttöönotto toimivassa tuotantojaksossa vaiheeseen, jolla on olemassa oleva työtila, sisältää seuraavaa:

* Uuden sisällön käyttöönotto lisäyksenä vaiheeseen, joka sisältää jo sisältöä.

* Uusi sisältö asennetaan vanhan sisällön korvaamiseksi nykyisessä työvaiheessa.

### <a name="deployment-process"></a>Käyttöönottoprosessi

Nykyisen vaiheen sisältö kopioidaan kohdevaiheeseen. Power BI tunnistaa kohdevaiheen olemassa olevan sisällön ja korvaa sen. Jos haluat selvittää, mikä sisältökohde on korvattava, käyttöönottojaksot käyttävät pääkohteen ja sen kloonien välistä suhdetta. Tämä yhteys säilytetään, kun uutta sisältöä luodaan. Korvaustoiminto korvaa vain kohteen sisällön. Kohteen tunnus, URL-osoite ja käyttöoikeudet pysyvät muuttumattomina.

Kohdevaiheessa [kohteen ominaisuudet, joita ei kopioida](deployment-pipelines-process.md#item-properties-that-are-not-copied), pysyvät sellaisina kuin ne olivat ennen käyttöönottoa. Uusi sisältö ja uudet kohteet kopioidaan nykyisestä vaiheesta kohdevaiheeseen.

### <a name="refreshing-the-dataset"></a>Tietojoukon päivittäminen

Kohdetietojoukon tiedot säilytetään, kun se on mahdollista. Jos tietojoukkoon ei ole tehty muutoksia, tiedot säilytetään sellaisina kuin ne olivat ennen käyttöönottoa.

Pieniä muutoksia, kuten taulukon tai laskettujen mittareiden lisäämistä lukuun ottamatta Power BI säilyttää alkuperäiset tiedot, ja päivitys on optimoitu päivittämään vain tarvittavat tiedot. Jotta rakenteen muutokset tai tietolähteen yhteyteen tehdyt muutokset voidaan katkaista, vaaditaan täydellinen päivitys.

### <a name="requirements-for-deploying-to-a-stage-with-an-existing-workspace"></a>Vaatimukset käyttöönottamisessa vaiheeseen, jossa on aiemmin luotu työtila

Kunhan käyttöönotettu sisältö sijaitsee [Premium-kapasiteetissa](../admin/service-premium-what-is.md), käyttäjä, joka täyttää seuraavat ehdot, voi ottaa sen käyttöön vaiheeseen, jolla on aiemmin luotu työtila:

* [Pro-käyttäjä](../admin/service-admin-purchasing-power-bi-pro.md), joka on molempien työtilojen jäsen käyttöönoton lähde- ja kohdevaiheissa.

* Kaikkien käyttöönotettavan kohdetyötilan tietojoukkojen omistaja.

Lisätietoja on [käyttöoikeuksia](#permissions) käsittelevässä osassa.

## <a name="deployed-items"></a>Käyttöönotetut kohteet

Kun otat sisältöä käyttöön yhdestä jakson vaiheesta toiseen, kopioitu sisältö sisältää seuraavat Power BI -kohteet:

* Tietojoukot

* raportit

* Koontinäytöt

### <a name="unsupported-items"></a>Kohteet, joita ei tueta

Käyttöönottojaksot eivät tue seuraavia kohteita:

* Tietojoukot, jotka eivät ole peräisin kohteesta. pbix

* Raportit, jotka perustuvat tietojoukkoihin, joita ei tueta

* Työtila ei voi käyttää mallisovellusta

* Sivutetut raportit

* Tietovuot

* PUSH-tietojoukot

* Työkirjat

## <a name="item-properties-copied-during-deployment"></a>Käyttöönoton aikana kopioidut kohteen ominaisuudet

Käyttöönoton aikana seuraavat kohteen ominaisuudet kopioidaan, ja ne korvaavat kohteen ominaisuudet kohdevaiheessa:

* Tietolähteet ([tietojoukkosääntöjä](deployment-pipelines-get-started.md#step-4---create-dataset-rules) tuetaan)

* Parametrit ([tietojoukkosääntöjä](deployment-pipelines-get-started.md#step-4---create-dataset-rules) tuetaan)

* Raportin visualisoinnit

* Raporttisivut

* Koontinäytön ruudut

* Mallin metatiedot

* Kohteiden yhteydet

### <a name="item-properties-that-are-not-copied"></a>Kohteen ominaisuudet, joita ei kopioida

Seuraavia kohteen ominaisuuksia ei kopioida käyttöönoton aikana:

* Tiedot - Tietoja ei kopioida, vain metatiedot kopioidaan

* URL-OSOITE

* Tunnus

* Käyttöoikeudet – Työtilaan tai tiettyyn kohteeseen

* Työtilan asetukset –Jokaisella vaiheella on oma työtila

* Sovelluksen sisältö ja asetukset – Jos haluat ottaa sovelluksesi käyttöön, tutustu kohtaan [Power BI sovellusten käyttöönotto](#deploying-power-bi-apps)

Seuraavat tietojoukon ominaisuudet kopioidaan käyttöönoton aikana:

* Roolimääritys
    
* Päivitysaikataulu
    
* Tietolähteen tunnistetiedot
    
* Kyselyn välimuistiin tallentamisen asetukset (voidaan periä kapasiteetista)
    
* Käyttöönottoasetukset

## <a name="deploying-power-bi-apps"></a>Power BI -sovellusten käyttöönotto

[Power BI -sovellukset](../consumer/end-user-apps.md) ovat suositeltu tapa jakaa sisältöä maksuttomille Power BI -kuluttajille. Käyttöönottojaksojen avulla voit hallita Power BI -sovelluksia käyttöönottojaksossa, jotta saat lisää hallintaa ja joustavuutta sovelluksen elinkaaren suhteen.

Luo sovellus kullekin käyttöönottojakson vaiheelle, jotta voit testata kunkin sovelluksen päivityksen käyttäjän näkökulmasta. Käyttöönottojakson avulla voit hallita tätä prosessia helposti. Käytä työtilakortin Julkaise- tai Näytä-painiketta, jos haluat julkaista tai tarkastella sovellusta tietyssä jakson vaiheessa.

[![](media/deployment-pipelines-process/publish.png "Publish app")](media/deployment-pipelines-process/publish.png#lightbox)

Tuotantovaiheessa vasemmassa alakulmassa oleva päätoimintopainike avaa Päivitä sovellus -sivun Power BI:ssa, jotta sovelluksen käyttäjät voivat käyttää sisältöpäivityksiä.

[![](media/deployment-pipelines-process/update-app.png "Update app")](media/deployment-pipelines-process/update-app.png#lightbox)

>[!IMPORTANT]
>Käyttöönottoprosessi ei sisällä sovelluksen sisällön tai asetusten päivittämistä. Jos haluat ottaa muutokset käyttöön sisällössä tai asetuksissa, sinun on päivitettävä sovellus manuaalisesti asianomaisessa jakson vaiheessa.

## <a name="permissions"></a>Käyttöoikeudet

Jakson käyttöoikeudet ja työtilan käyttöoikeudet myönnetään ja niitä hallitaan erikseen. Esimerkiksi käyttäjällä, jolla on jakson käyttöoikeus mutta ei työtilan käyttöoikeuksia, on mahdollisuus tarkastella jaksoa ja jakaa se muille. Tämä käyttäjä ei kuitenkaan pysty lukemaan työtilan sisältöä jakso- tai työtilasivulla, eikä se pysty suorittamaan käyttöönottoja.

### <a name="user-with-pipeline-access"></a>Käyttäjä, jolla on jakson käyttöoikeus

Käyttäjillä, joilla on jakson käyttöoikeus, on seuraavat käyttöoikeudet:

* Jakson tarkastelu
    
* Jakson jakaminen muille
    
* Jakson muokkaaminen ja poistaminen

>[!NOTE]
>Jakson käyttöoikeus ei takaa oikeuksia tarkastella tai suorittaa toimintoja työtilan sisällössä.

### <a name="workspace-viewer"></a>Työtilan katselija

Työtilan katselijat, joilla on *jakson käyttöoikeus*, voivat myös tehdä seuraavaa:

* Kuluttaa sisältöä

>[!NOTE]
>Työtilan katselijat eivät voi käyttää tietojoukkoa tai muokata työtilan sisältöä.

### <a name="workspace-contributor"></a>Työtilaan osallistuja

Työtilaan osallistujat, joilla on *jakson käyttöoikeus*, voivat myös tehdä seuraavaa:

* Kuluttaa sisältöä

* Verrata vaiheita

* Katsella tietojoukkoja

### <a name="workspace-member"></a>Työtilan jäsen

Työtilan jäsenet, joilla on *jakson käyttöoikeus*, voivat myös tehdä seuraavaa:

* Katsella työtilan sisältöä
    
* Verrata vaiheita
    
* Ottaa käyttöön raportteja ja koontinäyttöjä

* Poistaa työtiloja

### <a name="workspace-admin"></a>Työtilan järjestelmänvalvoja

Työtilan järjestelmänvalvojat, joilla on *jakson käyttöoikeus*, voivat suorittaa *työtilan jäsenen* toimintoja ja myös tehdä seuraavaa:

* Määritä työtilat

* Poistaa työtiloja

### <a name="dataset-owner"></a>Tietojoukon omistaja

Tietojoukon omistajat, jotka ovat joko työtilan jäseniä tai järjestelmänvalvojia, voivat myös tehdä seuraavaa:

* Päivittää tietojoukkoja
    
* Määrittää sääntöjä

>[!NOTE]
>Tässä osiossa kuvataan käyttöönottojaksojen käyttöoikeuksia. Tässä osiossa luetelluilla käyttöoikeuksilla voi olla eri sovelluksia toisissa Power BI -ominaisuuksissa.

## <a name="limitations"></a>Rajoitukset

Tässä osiossa luetellaan suurin osa käyttöönottojaksojen rajoituksista.

* Työtilan on sijaittava  [Premium-kapasiteetissa](../admin/service-premium-what-is.md).

* Power BI -kohteita, kuten raportteja ja koontinäyttöjä, joissa on Power BI [-luottamuksellisuustunniste](../admin/service-security-data-protection-overview.md#sensitivity-labels-in-power-bi), ei voi ottaa käyttöön.

* Tietojoukkoja, jotka on määritetty [lisäävään päivitykseen](../admin/service-premium-incremental-refresh.md), ei voi ottaa käyttöön.

* Työtilan rajoitusten luettelo on kohdassa [Työtilan määrityksen rajoitukset](deployment-pipelines-get-started.md#workspace-assignment-limitations).

* Luettelo tietojoukon sääntörajoituksista on kohdassa [Tietojoukkosääntöjen rajoitukset](deployment-pipelines-get-started.md#dataset-rule-limitations)

* Luettelo kohteista, joita ei tueta, on kohdassa [Kohteet, joita ei tueta](#unsupported-items).

## <a name="next-steps"></a>Seuraavat vaiheet

>[!div class="nextstepaction"]
>[Käyttöönottojaksojen esittely](deployment-pipelines-overview.md)

>[!div class="nextstepaction"]
>[Käyttöönottojaksojen parhaat käytännöt](deployment-pipelines-best-practices.md)

>[!div class="nextstepaction"]
>[Käyttöönottojaksojen käytön aloittaminen](deployment-pipelines-get-started.md)

>[!div class="nextstepaction"]
>[Käyttöönottojaksojen vianmääritys](deployment-pipelines-troubleshooting.md)