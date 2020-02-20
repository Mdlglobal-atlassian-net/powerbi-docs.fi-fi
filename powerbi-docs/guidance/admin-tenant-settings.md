---
title: Vuokraajan järjestelmänvalvojan asetuksia koskevat ohjeet
description: Power BI -vuokraajan asetuksia koskevat ohjeet.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: v-pemyer
ms.openlocfilehash: f9832948fdd25d1bd807e0ff5d916b08b55aea95
ms.sourcegitcommit: e27d40054949421701f829113c4a5f6d260c8d5f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/12/2020
ms.locfileid: "77155015"
---
# <a name="tenant-admin-settings-guidance"></a>Vuokraajan järjestelmänvalvojan asetuksia koskevat ohjeet

Tämä artikkeli on tarkoitettu Power BI -järjestelmänvalvojille, jotka vastaavat Power BI -käyttöympäristön asettamisesta ja määrittämisestä organisaatiossaan.

Annamme erityisiä vuokraajan asetuksia koskevia ohjeita Power BI:n käyttökokemuksen parantamiseksi. Nämä asetukset saattavat myös altistaa organisaatiosi riskeille. Suosittelemme, että määrität aina vuokraajasi organisaatiosi käytäntöjen ja prosessien mukaisesti.

[Vuokraaja-asetuksia](../service-admin-portal.md#tenant-settings) hallitaan [järjestelmänvalvojan portaalissa](https://app.powerbi.com/admin-portal/tenantSettings), ja ne määrittää [Power BI -palvelun järjestelmänvalvoja](../service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi). Useiden vuokraaja-asetusten avulla voidaan rajoittaa ominaisuuksien käyttöä tietyille käyttäjille. Suosittelemme, että tutustut ensin asetuksiin, jotta voit suunnitella tarvitsemasi käyttöoikeusryhmät. Saatat huomata, että voit käyttää samaa käyttöoikeusryhmää useisiin asetuksiin.

## <a name="improve-power-bi-experience"></a>Paranna Power BI:n käyttökokemusta

### <a name="publish-get-help-information"></a>Julkaise ”Hanki apua” -tiedot

Kehotamme määrittämään sisäisiä Power BI:hin liittyviä sivustoja [Microsoft Teamsin](/microsoftteams) tai muun yhteistyöalustan avulla. Voit näiden sivustojen avulla tallentaa koulutusasiakirjoja, isännöidä keskusteluja, tehdä käyttöoikeuspyyntöjä tai reagoida tukipyyntöön.

Suosittelemme tässä tapauksessa ottamaan käyttöön **Julkaise ”Hanki apua” -tiedot** -asetuksen _koko organisaatiolle_. Se löytyy **Ohje ja tuki -asetukset** -ryhmästä. Voit määrittää URL-osoitteita seuraaville:

- Koulutusasiakirjat
- Keskustelupalsta
- Käyttöoikeuspyynnöt
- Tukipalvelu

Nämä URL-osoitteet ovat saatavilla linkkeinä Power BI:n ohjevalikossa.

> [!NOTE]
> **Käyttöoikeuspyyntöjen** URL-osoitteiden avulla estät yksittäisiä käyttäjiä rekisteröitymästä ilmaiseen 60 päivän Power BI Pro -kokeiluversioon. Käyttäjät ohjataan sen sijaan sisäiseen sivustoosi, jossa kerrotaan, miten he voivat hankkia maksuttoman tai Pro-käyttöoikeuden.

![Kuvassa näytetään Julkaise ”Hanki apua” -tiedot -asetus.](media/admin-tenant-settings/publish-get-help-information.png)

## <a name="manage-risk"></a>Hallitse riskejä

### <a name="receive-email-notification-service-outages-or-incidents"></a>Ota vastaan sähköposti-ilmoituksia palvelukatkoista tai -tapauksista

Voit saada ilmoituksen sähköpostitse, jos palvelukatkos tai -tapaus vaikuttaa vuokraajaasi. Tällä tavalla voit reagoida tapauksiin ennakoivasti.

Suosittelemme, että otat käyttöön **Vastaanota sähköposti-ilmoituksia palvelukatkoista tai -tapauksista** -asetuksen. Se löytyy **Ohje ja tuki -asetukset** -ryhmästä. Määritä vähintään yksi _sähköpostia käyttävä_ käyttöoikeusryhmä.

![Kuvassa näytetään ”Vastaanota sähköposti-ilmoituksia palvelukatkoista tai -tapauksista” -asetus.](media/admin-tenant-settings/receive-email-notifications-for-service-outages-or-incidents.png)

### <a name="information-protection"></a>Tietojen suojaaminen

Tietojen suojaamisen avulla voidaan pakottaa suojausasetukset (kuten salaus ja vesileimat), kun tietoja viedään Power BI -palvelusta.

Tietojen suojaamiseen liittyy kaksi vuokraaja-asetusta. Oletusarvoisesti molemmat asetukset on poistettu käytöstä koko organisaatiolle.

Suosittelemme ottamaan nämä asetukset käyttöön, kun haluat käsitellä ja suojata arkaluontoisia tietoja. Lisätietoja on artikkelissa [Power BI:n tietosuoja](../admin/service-security-data-protection-overview.md).

### <a name="create-workspaces"></a>Työtilojen luominen

Voit rajoittaa käyttäjiä luomasta työtiloja. Näin voit hallita sitä, mitä sisältöä organisaatiossasi luodaan.

> [!NOTE]
> Tällä hetkellä vanhan ja uuden työtilakokemuksen välillä on siirtymäjakso. Tämä vuokraaja-asetus koskee vain uutta käyttökokemusta.

**Luo työtiloja** -asetus on oletusarvoisesti käytössä koko organisaatiolle. Se löytyy **Työtilan asetukset** -ryhmästä.

Suosittelemme, että määrität vähintään yhden käyttöoikeusryhmän. Näille ryhmille voidaan myöntää _tai hylätä_ työtilojen luomisen käyttöoikeus.

Muista sisällyttää asiakirjoihin ohjeet siitä, miten käyttäjät (joilla ei ole työtilan luomisoikeuksia) voivat pyytää uutta työtilaa.

![Kuvassa näytetään ”Luo työtilat” -asetus.](media/admin-tenant-settings/create-workspaces.png)

### <a name="share-content-with-external-users"></a>Jaa sisältöä ulkoisten käyttäjien kanssa

Käyttäjät voivat jakaa raportit ja koontinäytöt organisaatiosi ulkopuolisille henkilöille.

**Jaa sisältö ulkoisten käyttäjien kanssa** -asetus on otettu käyttöön oletusarvoisesti koko organisaatiolle. Se löytyy **Vienti- ja jakamisasetukset** -ryhmästä.

Suosittelemme, että määrität vähintään yhden käyttöoikeusryhmän. Näille ryhmille voidaan myöntää _tai hylätä_ käyttöoikeus jakaa sisältöä ulkoisten käyttäjien kanssa.

![Kuvassa näytetään ”Jaa sisältöä ulkoisten käyttäjien kanssa” -asetus.](media/admin-tenant-settings/share-content-with-external-users.png)

### <a name="publish-to-web"></a>Julkaise verkkoon

[Julkaise verkkoon](../service-publish-to-web.md) -ominaisuuden avulla voit julkaista julkisia raportteja verkossa. Jos sitä käytetään väärin, on olemassa riski siitä, että luottamukselliset tiedot asetetaan saataville verkossa.

**Julkaise verkkoon** -asetus on oletusarvoisesti otettu käyttöön koko organisaatiolle, mutta se rajoittaa muiden kuin järjestelmänvalvojana toimivien käyttäjien kykyä luoda upotettuja koodeja. Se löytyy **Vienti- ja jakamisasetukset** -ryhmästä.

Suosittelemme, että määrität vähintään yhden käyttöoikeusryhmän. Näille ryhmille voidaan myöntää _tai hylätä_ raporttien julkaisemisen käyttöoikeus.

Lisäksi voit valita, miten upotetut koodisi toimivat. Oletusarvoinen asetus on **Salli vain olemassa olevat koodit**. Se tarkoittaa, että käyttäjiä pyydetään ottamaan yhteyttä Power BI -järjestelmänvalvojaan upotetun koodin luomiseksi.

![Kuvassa näytetään ”Julkaise verkkoon” -asetus.](media/admin-tenant-settings/publish-to-web.png)

Suosittelemme myös tarkistamaan [Julkaise verkkoon -asetuksen upotetut koodit](https://app.powerbi.com/admin-portal/embedCodes) säännöllisesti. Poista koodit, jos ne johtavat yksityisten tai luottamuksellisten tietojen julkaisemiseen.

### <a name="export-data"></a>Vie tiedot

Voit rajoittaa käyttäjiä viemästä tietoja koontinäytön ruuduista tai raportin visualisoinneista.

**Vie tiedot** -asetus on oletusarvoisesti käytössä koko organisaatiolle. Se löytyy **Vienti- ja jakamisasetukset** -ryhmästä.

Suosittelemme, että määrität vähintään yhden käyttöoikeusryhmän. Näille ryhmille voidaan myöntää _tai hylätä_ raporttien julkaisemisen käyttöoikeus.

> [!IMPORTANT]
> Tämän asetuksen poistaminen käytöstä rajoittaa myös [Analysoi Excelissä](../service-analyze-in-excel.md) -ominaisuuden ja Power BI -palvelun [reaaliaikaisen yhteysominaisuuden](../desktop-report-lifecycle-datasets.md#using-a-power-bi-service-live-connection-for-report-lifecycle-management) käyttöä.

![Kuvassa näytetään ”Vie tiedot” -asetus.](media/admin-tenant-settings/export-data.png)

> [!NOTE]
> Jos käyttäjät sallivat toisten käyttäjien viedä tietoja, voit lisätä suojauskerroksen pakottamalla [tietosuojan](../admin/service-security-data-protection-overview.md). Kun se on määritetty, luvattomia käyttäjiä estetään viemästä sisältöä, johon liittyy luottamuksellisuustunnisteita.

### <a name="allow-external-guest-users-to-edit-and-manage-content-in-the-organization"></a>Salli ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa

Ulkoiset vieraskäyttäjät voivat muokata ja hallita Power BI:n sisältöä. Lisätietoja on artikkelissa [Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla](../service-admin-azure-ad-b2b.md).

**Salli ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa** -asetus on oletusarvoisesti poistettu käytöstä koko organisaatiolle. Se löytyy **Vienti- ja jakamisasetukset** -ryhmästä.

Jos haluat valtuuttaa ulkoiset käyttäjät muokkaamaan ja hallitsemaan sisältöä, suorittelemme määrittämään vähintään yhden käyttöoikeusryhmän. Näille ryhmille voidaan myöntää _tai hylätä_ raporttien julkaisemisen käyttöoikeus.

![Kuvassa näytetään ”Salli ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa” -asetus.](media/admin-tenant-settings/allow-external-guest-users.png)

### <a name="developer-settings"></a>Kehittäjäasetukset

[Power BI:n sisällön upottamiseen](../developer/embedding.md)liittyy kaksi vuokraaja-asetusta. Ne ovat seuraavat:

- Upota sisältö sovelluksiin (oletusarvoisesti käytössä)
- Salli palveluobjektien käyttää Power BI -ohjelmointirajapintoja (oletusarvoisesti poistettu käytöstä)

Jos et aio käyttää kehittäjien ohjelmointirajapintoja sisällön upottamiseen, suosittelemme poistamaan ne käytöstä tai ainakin määrittämään tietyt käyttöoikeusryhmät tähän tehtävään.

![Kuvassa näytetään kehittäjän asetukset.](media/admin-tenant-settings/developer-settings.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Mitä on Power BI:n hallinta?](../service-admin-administering-power-bi-in-your-organization.md)
- [Power BI:n hallinta hallintaportaalissa](../service-admin-portal.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com)
