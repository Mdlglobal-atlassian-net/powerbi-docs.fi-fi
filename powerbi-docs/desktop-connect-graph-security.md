---
title: Yhdistä kohteeseen Microsoft Graph Security Power BI Desktopissa
description: Luo helposti yhteys Microsoft Graph Security -ohjelmointirajapintaan Power BI Desktopissa
author: cpopell
manager: kfile
ms.reviewer: ''
ms.custom: seojan19
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/29/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 1594935d9dc156b03daff9e4447752bce2c0f06c
ms.sourcegitcommit: 88ac51106ec7d0ead8c2a1550a11afae0d502bb9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/12/2019
ms.locfileid: "56086674"
---
# <a name="connect-to-microsoft-graph-security-in-power-bi-desktop"></a>Yhdistä kohteeseen Microsoft Graph Security Power BI Desktopissa

Voit käyttää Power BI Desktopia yhteyden luomiseen Microsoft Graph Security -ohjelmointirajapintaan käyttämällä Microsoft Graph Security Power BI -liitintä. Sen avulla voit luoda koontinäyttöjä ja raportteja, joista saat tietoja tietoturvaan liittyvistä [ilmoituksista](https://docs.microsoft.com/graph/api/resources/alert?view=graph-rest-1.0) ja [suojauspisteistä](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta). [Microsoft Graph Security -ohjelmointirajapinta](https://aka.ms/graphsecuritydocs) yhdistää [useat tietoturvaratkaisut](https://aka.ms/graphsecurityalerts), sekä Microsoftin omat että ekosysteemikumppanien luomat, jolloin mahdollistetaan ilmoitusten helpompi korrelointi, päästään käyttämään monipuolisia kontekstitietoja ja yksinkertaistetaan automaatiota. Tämä voimauttaa organisaatiot saamaan nopeasti merkityksellisiä tietoja ja ryhtymään kaikkia tietoturvatuotteita koskeviin toimenpiteisiin samalla kun vähennetään moninkertaisten integrointien rakentamisen ja ylläpidon edellyttämiä kustannuksia ja mutkikkuutta.

## <a name="prerequisites-to-connect-with-the-microsoft-graph-security-connector"></a>Microsoft Graph Security -liittimeen luotavan yhteyden edellytykset

* Microsoft Graph Security -liittimen käyttämiseksi tarvitset *yksiselitteisesti ilmaistun* Azure Active Directoryn (AD) vuokralaisen järjestelmänvalvojan suostumuksen, joka on osa [Microsoft Graph Security -todentamisvaatimuksia](https://aka.ms/graphsecurityauth). Tämä suostumus edellyttää Microsoft Graph Security Power BI -liittimen sovellustunnusta ja nimeä, jotka löydät myös [Azure-portaalista](https://portal.azure.com):

   | Ominaisuus | Arvo |
   |----------|-------|
   | **Sovelluksen nimi** | `MicrosoftGraphSecurityPowerBIConnector` |
   | **Sovelluksen tunnus** | `cab163b7-247d-4cb9-be32-39b6056d4189` |
   |||

   Azure AD -vuokraajan järjestelmänvalvoja voi antaa suostumuksensa liittimelle joko seuraavat vaiheet suorittamalla:

   * [Myöntää vuokraajan järjestelmänvalvojan suostumuksen Azure AD -sovelluksille](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).

   * Logiikkasovelluksesi ensimmäisen suorituksen yhteydessä sovellus voi hakea suostumusta Azure AD -vuokraajan järjestelmänvalvojalta [sovellussuostumuskokemuksen](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience) avulla.
   
* Käyttäjätilin, jota käytetään Microsoft Graph Security Power BI -liittimeen kirjauduttaessa, on oltava suojauksenlukijan rajoitetun järjestelmänvalvojan rooliryhmän jäsen Azure AD:ssa (joko suojauksen lukija tai suojauksen järjestelmänvalvoja). Noudata vaiheita osiossa [Azure AD -roolien määrittäminen käyttäjille](https://docs.microsoft.com/graph/security-authorization#assign-azure-ad-roles-to-users). 

## <a name="using-the-microsoft-graph-security-connector"></a>Microsoft Graph Security -liittimen käyttäminen

Seuraamalla näitä ohjeita voit käyttää **Microsoft Graph Security** -liitintä:

1. Valitse **Nouda tiedot -> Lisää…** Power BI Desktopin **Aloitus**-valintanauhasta.
2. Valtse vasemmalla näkyvistä luokista **Online-palvelut**,
3. Napsauta **Microsoft Graph Security (Beta)**.

    ![Nouda tiedot](media/desktop-connect-graph-security/GetData.PNG)
    
4. Valitse näkyviin tulevasta **Microsoft Graph Security** -ikkunasta Microsoft Graph -ohjelmointirajapintaversio kyselyyn. Vaihtoehdot ovat v1.0 ja beta.

    ![Valitse versio](media/desktop-connect-graph-security/selectVersion.PNG)
    
5. Kirjaudu sisään Azure Active Directory -tiliisi, kun sitä pyydetään. Tällä tilillä on oltava **Suojauksen lukija** -rooli, kuten yllä on mainittu edellytyksien yhteydessä.

    ![Kirjaudu sisään](media/desktop-connect-graph-security/SignIn.PNG)
    
6. Jos olet vuokraajan järjestelmänvalvoja **ja** jos et vielä ole antanut suostumusta Microsoft Graph Security Power BI -liittimelle (sovellukselle) edellytyksissä kuvatulla tavalla, saat seuraavan valintaikkunan. Varmista, että valitset ”**Suostumus organisaatiosi puolesta**”.

    ![Järjestelmänvalvojan suostumus](media/desktop-connect-graph-security/AdminConsent.PNG)
    
7. Kun olet kirjautunut sisään, näet seuraavan ikkunan, joka osoittaa, että todentaminen onnistui. Valitse **Muodosta yhteys**.

    ![Kirjautunut sisään](media/desktop-connect-graph-security/SignedIn.PNG)
    
8. Kun yhteyden muodostaminen onnistuu, näyttöön tulee **Siirtymistoiminto**-ikkuna seuraavassa kuvatulla tavalla ja näyttää entiteetit, kuten ilmoitukset ym., edellisissä vaiheissa valitsemasi version [Microsoft Graph Security -ohjelmointirajapinnassa](https://aka.ms/graphsecuritydocs). Valitse yksi tai useampia entiteettejä tuotavaksi ja käytettäväksi **Power BI Desktop**issa. Napsauttamalla **Lataa** saat vaiheessa 10 kuvatun mukaisen tulosnäkymän.

   ![Siirtymistaulukko](media/desktop-connect-graph-security/NavTable.PNG)
    
9. Jos haluat tehdä lisäkyselyn Microsoft Graph Security -ohjelmointirajapinnalle, valitse toiminto **Määritä mukautettu Microsoft Graph Security -URL-osoite tulosten suodattamiseksi**. Tämän avulla voit tehdä [OData.Feed](https://docs.microsoft.com/power-bi/desktop-connect-odata)-kyselyn Microsoft Graph Security -ohjelmointirajapinnalle, kun sinulla on tarvittavat oikeudet käyttää ohjelmointirajapintaa.

   > [!NOTE]
   > Seuraavassa käytettävä palvelun esimerkki-URL on `https://graph.microsoft.com/v1.0/security/alerts?$filter=Severity eq 'High'`. Viittaa [Graph-tuettuihin ODATA-kyselyparametreihin](https://docs.microsoft.com/graph/query-parameters), kun haluat rakentaa kyselyjä suodattaaksesi, tilataksesi tai hakeaksesi tuoreimmat tulokset.

   ![Odata-syöte](media/desktop-connect-graph-security/ODataFeed.PNG)
    
   Kun valitset **Käynnistä**, OData.Feed-toiminto lähettää kutsun ohjelmointirajapinnalle niin, että kyselyeditori aukeaa ja voit suodattaa ja tarkentaa käytettäväksi haluamasi tietoja ja ladata sitten tarkennetun tietojoukon Power BI Desktopiin.

10. Seuraava kuva havainnollistaa sen tai niiden Microsoft Graph Security -entiteetin tai entiteettien tulosikkunaa, joita kyselysi koskee.

   ![Tulos](media/desktop-connect-graph-security/Result.PNG)
    

Olet nyt valmiina käyttämään Microsoft Graph Security -liittimestä tuotuja tietoja Power BI Desktopissa visualisointien tai raporttien luomiseen tai vuorovaikutukseen muiden tietojen kanssa, joihin haluat olla yhteydessä ja joita haluat tuoda esimerkiksi muista Excel-työkirjoista, tietokannoista tai mistä tahansa muista tietolähteistä.

## <a name="next-steps"></a>Seuraavat vaiheet
* Tutustu Power BI -näytteisiin ja -malleihin käyttämällä tätä liitintä [Microsoft Graph Security GitHub Power BI -näytesäilössä](https://aka.ms/graphsecuritypowerbiconnectorsamples).

* Tutustu käyttäjäskenaarioihin ja lisätietoihin [Microsoft Graph Security Power BI -liitintä koskevassa blogimerkinnässä](https://aka.ms/graphsecuritypowerbiconnectorblogpost).

* Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

    * [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
    * [Power BI Desktopin tietolähteet](desktop-data-sources.md)
    * [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
    * [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)
    * [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)
