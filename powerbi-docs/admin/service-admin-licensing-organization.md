---
title: Power BI -käyttöoikeudet organisaatiossasi
description: Yleiskatsaus Power BI:ssä käytettävissä olevista käyttöoikeustyypeistä sekä siitä, miten järjestelmänvalvojat ostavat ja hallinnoivat organisaationsa käyttöoikeuksia.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/08/2020
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 1bd3af61bb7c1fe525a4e5822724ccb07c57eace
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83344292"
---
# <a name="power-bi-licensing-in-your-organization"></a>Power BI -käyttöoikeudet organisaatiossasi

Käyttäjälle mahdolliset toiminnot Power BI -palvelussa määräytyvät sen mukaan, mikä heidän käyttäjäkohtainen käyttöoikeutensa on ja onko heidän käsittelemänsä sisältö Power BI Premium -kapasiteettiin määritetyssä työtilassa. Kaikilla Power BI -palvelun käyttäjillä on oltava käyttöoikeus.

Käyttäjät voivat hankkia käyttöoikeuden kahdella tavalla. Käyttäjät voivat hankkia oman maksuttoman käyttöoikeuden tai Pro-käyttöoikeuden käyttämällä omatoimisen rekisteröitymisen ja työpaikan tai oppilaitoksen tilinsä avulla. Vaihtoehtoisesti järjestelmänvalvojat voivat hankkia Power BI -tilauksen ja määrittää käyttöoikeudet käyttäjille.

Tässä artikkelissa keskitytään palvelujen ostamiseen käyttäjäkohtaiseen käyttöoikeuteen järjestelmänvalvojan näkökulmasta. Lisätietoja siitä, miten käyttäjät voivat hankkia oman käyttöoikeutensa, on artikkelissa [Rekisteröityminen Power BI:tä varten yksityishenkilönä](../fundamentals/service-self-service-signup-for-power-bi.md).

## <a name="who-can-purchase-and-assign-licenses"></a>Kuka voi ostaa ja määrittää käyttöoikeuksia?

Sinulla on oltava määritetty järjestelmänvalvojarooli, jotta voit ostaa tai määrittää käyttöoikeuksia organisaatiossasi. Järjestelmänvalvojaroolit määritetään Azure Active Directory -hallintakeskuksen tai Microsoft 365 -hallintakeskuksen avulla. Seuraavasta taulukosta näet, mikä rooli vaaditaan ostamiseen ja käyttöoikeuksiin liittyvissä tehtävissä. Lisätietoja Azure Active Directoryn järjestelmänvalvojarooleista on artikkelissa [Järjestelmänvalvojaroolien tarkasteleminen ja määrittäminen Azure Active Directoryssa](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal). Lisätietoja Microsoft 365:n järjestelmänvalvojarooleista ja parhaista käytännöistä on artikkelissa [Tietoja järjestelmänvalvojarooleista](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).

| Kuka voi ostaa palveluja ja käyttöoikeuksia? | Kuka voi hallita käyttöoikeuksia? |
| --------------- | --------------- |
| Laskutuksen järjestelmänvalvoja | Käyttöoikeuksien järjestelmänvalvoja |
| Yleinen järjestelmänvalvoja | Käyttäjäjärjestelmänvalvoja |
|  | Yleinen järjestelmänvalvoja |

Näillä rooleilla hallinnoidaan organisaatiota. Jos haluat tietoja Power BI -palvelun järjestelmänvalvojarooleista, lue artikkeli [Power BI -järjestelmänvalvojaroolien kuvaus](service-admin-role.md).

## <a name="get-power-bi-for-your-organization"></a>Hanki Power BI organisaatiolle

Yleinen järjestelmänvalvoja tai laskutuksen järjestelmänvalvoja voi rekisteröityä Power BI -palveluun ja ostaa käyttöoikeuksia organisaationsa käyttäjille. Jos et ole vielä valmis ostamaan, valitse Power BI Pro -kokeilutilaus. Saat 25 käyttöoikeutta, joita voidaan käyttää yhden kuukauden ajan. Jos haluat vaiheittaiset ohjeet rekisteröitymiseen, lue artikkeli [Power BI -tilauksen hankkiminen organisaatiollesi](service-admin-org-subscription.md).

## <a name="about-self-service-sign-up"></a>Tietoja omatoimisesta kirjautumisesta

Yksittäiset käyttäjät voivat hankkia oman Power BI -käyttöoikeutensa rekisteröitymällä työpaikan tai oppilaitoksen tilinsä avulla. Maksuttoman käyttöoikeuden avulla käyttäjät voivat tutustua Power BI:n henkilökohtaisten tietojen analysointiin ja visualisointiin Oman työtilan avulla, mutta he eivät voi tehdä yhteistyötä muiden käyttäjien kanssa. Sisällön jakamiseen tarvitaan Power BI Pro -käyttöoikeus. Käyttäjät voivat päivittää käyttöoikeustyyppinsä Pro-versioksi tai rekisteröityä suoraan Pro-käyttöoikeuteen, jos organisaatiossa käytetään kaupallista pilvipalvelua. Pro-käyttöoikeuden suora ostaminen tai siihen päivittäminen ei ole käytettävissä opetusorganisaatioilla tai organisaatioilla, jotka on otettu käyttöön valtionhallinnon tai itsenäisen pilvipalvelun esiintymissä.

Jos et halua, että omatoiminen rekisteröityminen on organisaatiosi käyttäjien käytettävissä, katso artikkelista [Omatoimisen rekisteröitymisen ottaminen käyttöön tai poistaminen käytöstä](service-admin-disable-self-service.md) ohjeet sen käytöstä poistamiseen.

Jos haluat nähdä, keillä organisaatiosi käyttäjillä saattaa jo olla käyttöoikeus, katso ohjeet artikkelista [Käyttäjien käyttöoikeuksien tarkasteleminen ja hallinta](service-admin-manage-licenses.md).

## <a name="license-types-and-capabilities"></a>Käyttöoikeustyypit ja toiminnot

Käyttäjäkohtaisia Power BI -käyttöoikeuksia on kahdentyyppisiä: maksuttomia käyttöoikeuksia ja Pro-käyttöoikeuksia. Käyttäjän tarvitsema käyttöoikeustyyppi määräytyy sen mukaan, minne sisältö tallennetaan ja miten käyttäjä käyttää sisältöä. Sisällön mahdolliset tallennussijainnit määräytyvät organisaatiosi [tilaustyypin](#subscription-types) mukaan.

Yksi tilaustyyppi, [Power BI Premium](service-admin-premium-purchase.md), sallii maksuttoman käyttöoikeuden käyttäjien käsitellä Premium-kapasiteettiin varattujen työtilojen sisältöä. Premium-kapasiteetin ulkopuolella käyttäjä, jolla on maksuton käyttöoikeus, voi käyttää Power BI -palvelua vain yhteyden muodostamiseen tietoihin ja raporttien ja koontinäyttöjen luomiseen henkilökohtaisessa työtilassa. Hän ei voi vaihtaa sisältöä muiden kanssa eikä julkaista sisältöä sovellustyötiloihin.

Power BI -vakiotilaus käyttää jaettua kapasiteettia. Kun sisältö tallennetaan jaettuun kapasiteettiin, käyttäjät, joille on määritetty Power BI Pro -käyttöoikeus, voivat tehdä yhteistyötä vain muiden Power BI Pro -käyttäjien kanssa. He voivat kuluttaa muiden käyttäjien julkaisemaa sisältöä, julkaista sisältöä sovelluksen työtiloihin, jakaa koontinäyttöjä sekä tilata koontinäyttöjä ja raportteja.  Kun työtilat ovat Premium-kapasiteetissa, Pro-käyttäjät voivat jakaa sisältöä käyttäjille, joilla ei ole Power BI Pro -käyttöoikeutta.

Alla olevassa taulukossa on yhteenveto eri käyttöoikeustyyppien perustoiminnoista. Yksityiskohtainen erittely käyttöoikeustyyppikohtaisista ominaisuuksien käytettävyydestä on artikkelissa [Ominaisuudet käyttöoikeustyypin mukaan](../fundamentals/service-features-license-type.md).

| Käyttöoikeustyyppi | Toiminnot, kun työtila on jaetussa kapasiteetissa | Lisätoiminnot, kun työtila on Premium-kapasiteetissa |
| --------- | ----------- | ----------- |
| Power BI (ilmainen) | Sisällön käyttö Omassa työtilassa | Muiden kanssa jaetun sisällön kuluttaminen |
| Power BI Pro | Sisällön julkaiseminen sovellustyötiloihin, koontinäyttöjen ja raporttien jakaminen sekä jakaminen käyttäjille, joilla on Pro-käyttöoikeus | Jakaminen käyttäjille, joilla on maksuton käyttöoikeus |

## <a name="subscription-types"></a>Tilaustyypit

Kaikki Microsoftin käyttäjäpohjaiset kaupalliset käyttöoikeustilaukset perustuvat Azure Active Directory -käyttäjätietoihin. Tämä tarkoittaa sitä, että sinun on kirjauduttava sisään käyttäjätiedoilla, joita Azure Active Directory tukee kaupallisissa käyttöoikeuksissa. Voit lisätä Power BI -tilauksen mihin tahansa Microsoft-tilaukseen, joka käyttää Azure Active Directoryn tunnistetietopalveluja. Jotkin tilaukset, kuten Office 365 E5, sisältävät Power BI Pro -käyttöoikeuden, joten erillistä Power BI -rekisteröitymistä ei tarvita.

Organisaatioita varten on kahdentyyppisiä Power BI -tilauksia: omatoiminen Power BI ja Power BI Pro sekä edistynyt analytiikka Power BI Premiumin kanssa.

Omatoimisessa Power BI Pro -vakiotilauksessa järjestelmänvalvojat määrittävät käyttäjäkohtaiset käyttöoikeudet. Power BI Pro -käyttöoikeuksissa on käyttäjäkohtainen kuukausimaksu, joka mahdollistaa yhteistyön, julkaisemisen, jakamisen ja ad hoc -analyysin. Sisältö tallennetaan jaettuun tallennuskapasiteettiin, joka on täysin Microsoftin hallitsema.

Power BI Premium -tilaus varaa organisaatiolle erillisen kapasiteetin. Premium sopii suuryrityksen liiketoimintatiedoille, massadatan analysointiin, pilviraportointiin ja paikalliseen raportointiin ja sisältää edistyneet hallinnan ja käyttöönoton ohjaustoiminnot. Organisaation kapasiteetin järjestelmänvalvojat hallinnoivat erillisiä käsittely- ja tallennus resursseja. Tästä erillisestä ympäristöstä veloitetaan kuukausimaksu. Muiden Premium-etujen lisäksi Premium-kapasiteettiin tallennettua sisältöä voi käyttää ja jakaa käyttäjille, joilla ei ole Power BI Pro -käyttöoikeutta. Vähintään yhdellä käyttäjällä on oltava Power BI Pro -käyttöoikeus, joka on määritetty käyttämään Premiumia, ja sisällöntuottajat ja kehittäjät tarvitsevat silti Power BI Pro -käyttöoikeuden.

Nämä kaksi tilaustyyppiä eivät ole toisiaan poissulkevia. Samalla käyttäjällä voi olla sekä Power BI Premium- että Power BI Pro -käyttöoikeus. Tällöin Premium-kapasiteettiin tallennettu sisältö voidaan jakaa kaikkien käyttäjien kanssa, ja myös jaettu kapasiteetti on käytettävissä. Lisätietoja kapasiteetti rajoituksista on artikkelissa [Tietojen tallennustilan hallinta Power BI -työtiloissa](service-admin-manage-your-data-storage-in-power-bi.md).

Jos haluat vertailla tuotteiden ominaisuuksia ja hinnoittelua, lue artikkeli [Power BI -hinnat](https://powerbi.microsoft.com/pricing).

## <a name="guest-user-access"></a>Vieraskäyttöoikeus

Haluat ehkä jakaa sisältöä käyttäjille, jotka ovat organisaatiosi ulkopuolella. Sisältöä voi käyttää ulkopuolisten käyttäjien kanssa kutsumalla heidät tarkastelemaan sisältöä vieraina. Azure Active Directory Business-to-Business (Azure AD B2B) mahdollistaa sisällön jakamisen ulkopuolisten vieraskäyttäjien kanssa. Jakaminen ulkoisten käyttäjien kanssa vaatii seuraavien edellytysten täyttymistä:

- Mahdollisuus vaihtaa sisältöä ulkoisten käyttäjien kanssa on otettava käyttöön.

- Vieraskäyttäjällä on oltava tarvittavat käyttöoikeudet, jotta hän voi tarkastella jaettua sisältöä.

Lisätietoja vieraskäyttöoikeudesta on artikkelissa [Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla](service-admin-azure-ad-b2b.md).

## <a name="purchase-power-bi-pro-licenses"></a>Power BI Pro- käyttöoikeuksien ostaminen

Järjestelmänvalvojana voit ostaa Power BI Pro -käyttöoikeudet Microsoft 365:n tai Microsoft-kumppanin kautta. Kun olet ostanut käyttöoikeudet, voit määrittää ne yksittäisille käyttäjille. Jos haluat lisätietoja, katso kohta [Power BI Pro -käyttöoikeuksien hankinta ja määritys](service-admin-purchasing-power-bi-pro.md).

### <a name="power-bi-pro-license-expiration"></a>Power BI Pro -käyttöoikeuden vanhentuminen

Power BI Pro -käyttöoikeuden päätyttyä alkaa lisäaika. Jos kyseessä on volyymikäyttöoikeushankinta, lisäaika on 90 päivää. Jos kyseessä on suoraan ostettu käyttöoikeus, lisäaika on 30 päivää.

Power BI Pro -tilauksen elinkaari on sama kuin Office 365:llä. Lisätietoja on artikkelissa [Mitä tiedoilleni ja käyttöoikeudelleni tapahtuu, kun Office 365 for Business -tilaus päättyy?](https://support.office.com/article/What-happens-to-my-data-and-access-when-my-Office-365-for-business-subscription-ends-4436582f-211a-45ec-b72e-33647f97d8a3).


## <a name="next-steps"></a>Seuraavat vaiheet

- [Power BI Pro -käyttöoikeuksien hankinta ja määritys](service-admin-purchasing-power-bi-pro.md)
- [Microsoft 365 Businessin tilausten ja laskutuksen dokumentaatio](https://docs.microsoft.com/microsoft-365/commerce/?view=o365-worldwide)
- [Kirjautuneiden Power BI -käyttäjien etsiminen](service-admin-access-usage.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
