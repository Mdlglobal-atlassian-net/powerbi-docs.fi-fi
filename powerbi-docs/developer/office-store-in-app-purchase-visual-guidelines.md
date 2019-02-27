---
title: Käyttö saattaa edellyttää lisäostoja – Power BI:n visualisointien ohjeet
description: Lue ohjeet siihen, miten voit julkaista omia visualisointejasi AppSourcessa muiden löydettäviksi ja käytettäviksi maksua vastaan.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 11/26/2018
ms.openlocfilehash: 92d4320026164e523297cbe48ee87ce33d9ab2f7
ms.sourcegitcommit: 796bf513bf8669676e2a44627b56221b1629a6a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/26/2019
ms.locfileid: "56826579"
---
# <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Ohjeet Power BI -visualisointeihin, jotka sisältävät lisäostoja

Viime aikoihin asti Marketplace (AppSource) hyväksyi ainoastaan maksuttomia Power BI -visualisointeja. Tämä käytäntö on muuttunut, joten voit nyt lähettää AppSourceen myös visualisointeja, joissa on ”lisäosto saattaa olla tarpeen” -hintalappu. 

”Lisäosto saattaa olla tarpeen” -visualisoinnit ovat samankaltaisia kuin Office-kaupan apuohjelmien sovelluskohtaiset ostokset. Kehittäjät voivat lähettää visualisointeja myös sertifioitaviksi sen jälkeen, kun AppSource-tiimi on hyväksynyt ne, ja varmistettuaan, että visualisoinnit täyttävät sertifiointivaatimukset. Lisätietoja löytyy aiheesta [Sertifioidut mukautetut visualisoinnit](../power-bi-custom-visuals-certified.md).

> [!NOTE]
> * Visualisoinnin sertifiointi edellyttää, ettei siinä käytetä ulkoisia palveluita tai resursseja.
> * Kaikki maksuttomat visualisoinnit säilyttävät ne samat maksuttomat ominaisuudet, jotka olivat aiemmin tarjolla. Voit lisätä valinnaisia maksullisia lisäominaisuuksia aiempien maksuttomien ominaisuuksien lisäksi. Suosittelemme lähettämään sovelluskohtaisten tuotteiden visualisoinnit lisäominaisuuksien kanssa uusina visualisointeina sen sijaan, että päivittäisit aiemmat, maksuttomat visualisoinnit.


## <a name="what-changed-in-the-submission-process"></a>Miten lähetysprosessi on muuttunut?

Kehittäjät lataavat ostoja sisältävät visualisointinsa AppSourceen myyjien koontinäytön kautta aivan samoin kuin maksuttomien visualisointien kohdalla. Kehittäjien tulee ilmoittaa visualisointinsa sisältämistä sovelluskohtaisia ostoja edellyttävistä ominaisuuksista kirjoittamalla myyjän koontinäytön muistiinpanokohtaan ”Visual with in-app purchase” (Sovelluskohtaisia ostoja sisältävä visualisointi). Lisäksi kehittäjien tulee antaa käyttöoikeusavain tai -tunnus, jotta vahvistustiimi voi vahvistaa sovelluskohtaisia ostoja edellyttävät ominaisuudet. Kun visualisointi on vahvistettu ja hyväksytty, AppSourcessa ilmoitetaan sovelluskohtaisia ostoja sisältävän visualisoinnin hinnoitteluvaihtoehtojen kohdalla, että käyttö saattaa edellyttää lisäostoja.

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>Mikä on sovelluskohtaisia ostoja sisältävä Power BI -visualisointi?

Sovelluskohtaisia ostoja sisältävä visualisointi on ilmainen visualisointi, jossa on maksuttomia ominaisuuksia. Siihen liittyy myös lisäominaisuuksia, joiden käyttäminen saattaa vaatia lisämaksuja. Kehittäjien on ilmoitettava käyttäjille visualisoinnin kuvauksessa siitä, minkä ominaisuuksien käyttö edellyttää lisäostoja. Microsoft ei tällä hetkellä tarjoa omia ohjelmointirajapintoja, jotka tukisivat ostoja sovelluksissa ja apuohjelmissa.

Kehittäjät voivat käyttää ostoihin haluamaansa kolmannen osapuolen maksujärjestelmää. Lisätietoja on [Microsoftin myymälä-käytännössä](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads).

> [!NOTE]
> Vesileimoja ei sallita ilmaisissa ominaisuuksissa. Kehittäjät saattavat näyttää ponnahdusikkunan tai vesileiman, jos valinnaisia maksullisia lisäominaisuuksia käytetään ilman kelvollista käyttöoikeutta.  

## <a name="logo-guidelines"></a>Logo-ohjeet

Tässä osiossa annetaan ohjeet visualisoinnin logojen ja logotyyppien lisäämiseen.

> [!NOTE]
> Logot sallitaan ainoastaan muokkaustilassa. Logoja ei voi näyttää tarkastelutilassa.

![Määritelmät](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![Huomioitavia seikkoja](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![Mitä kannattaa välttää](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![Koko ja muotoilu](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![Reunukset ja koko](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![Muokkaustila](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>Parhaat käytännöt

### <a name="visual-landing-page"></a>Visualisoinnin aloitussivu

Aloitussivulla kerrot käyttäjille, miten visualisointia voi käyttää ja mistä sen käyttöoikeuden voi ostaa. Älä lisää automaattisesti toistettavia videoita. Lisää ainoastaan sellaista sisältöä, joka parantaa käyttökokemusta, esimerkiksi käyttöoikeuden ostamiseen liittyviä ohjeita tai linkkejä ja sovelluskohtaisia ostoja edellyttävien ominaisuuksien käyttöohjeita.

### <a name="license-key-and-token"></a>Käyttöoikeusavain ja -tunnus

Lisää käyttömukavuuden parantamiseksi käyttöoikeusavainta tai -tunnusta koskevat kentät muokkausruudun yläreunaan.

## <a name="faq"></a>Usein kysytyt kysymykset

Saat lisätietoja visualisoinneista [lisäostoja sisältävien visualisointien usein kysytyistä kysymyksistä](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#visuals-with-additional-purchases).

## <a name="next-steps"></a>Seuraavat vaiheet

Lue ohjeet siihen, miten voit julkaista omia visualisointejasi [AppSourcessa](office-store.md) muiden löydettäväksi ja käytettäväksi.
