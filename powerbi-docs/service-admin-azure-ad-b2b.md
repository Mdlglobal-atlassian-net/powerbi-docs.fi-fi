---
title: Sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla
description: Power BI mahdollistaa sisällön jakamisen ulkopuolisten vieraskäyttäjien kanssa Azure Active Directory Business-to-Businessin (Azure AD B2B:n) kautta.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: d17c6bbe5ddf6cd39626ac0038595543cd2fecfb
ms.sourcegitcommit: 220910f0b68cb1e265ccd5ac0cee4ee9c6080b26
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82841062"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla

Power BI mahdollistaa sisällön jakamisen ulkopuolisten vieraskäyttäjien kanssa Azure Active Directory Business-to-Businessin (Azure AD B2B:n) kautta.
Azure AD B2B:n avulla organisaatiosi mahdollistaa jakamisen ulkoisten käyttäjien kanssa ja hallitsee sitä yhdestä paikasta. Ulkoisilla käyttäjillä on oletusarvoisesti oikeudet ainoastaan käyttää sisältöä. Lisäksi voit myös sallia organisaation ulkopuolisten vieraskäyttäjien muokata ja hallita organisaatiosi sisäistä sisältöä.

Tässä artikkelissa annetaan perustiedot Azure AD B2B:stä Power BI:ssä. Lisätietoja saat kohdasta [Power BI ‑sisällön jakaminen ulkoisille vieraskäyttäjille Azure Active Directory B2B:n avulla](guidance/whitepaper-azure-b2b-power-bi.md).

## <a name="enable-access"></a>Käytön salliminen

Varmista, että [Jaa sisältöä ulkoisten käyttäjien kanssa](service-admin-portal.md#export-and-sharing-settings) -ominaisuus on käytössä Power BI -hallintaportaalissa, ennen kuin kutsut vieraskäyttäjiä. Vaikka asetus on käytössä, käyttäjällä on oltava Azure Active Directoryssa oikeus kutsua vieraskäyttäjiä. Oikeus määritetään Vieraiden kutsuja -roolissa. 

[Salli ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) -vaihtoehdon avulla voit antaa vieraskäyttäjille oikeudet nähdä ja luoda sisältöä työtiloissa sekä myös selata organisaatiosi Power BI:tä.

> [!NOTE]
> [Jaa sisältöä ulkoisten käyttäjien kanssa](service-admin-portal.md#export-and-sharing-settings) -asetuksella määritetään, salliko Power BI ulkoisten käyttäjien kutsumisen organisaatioosi. Kun ulkoinen käyttäjä hyväksyy kutsun, hänestä tulee organisaatiosi Azure AD B2B -vieraskäyttäjä. Vieraskäyttäjät näkyvät valittavina henkilöinä Power BI:n valitsimissa. Kun asetus on poistettu käytöstä, organisaatiosi nykyisillä vieraskäyttäjillä säilyvät oikeudet kaikkiin kohteisiin, joihin heillä oli käyttöoikeus. Lisäksi he näkyvät edelleen henkilöiden valitsimissa. Jos vieraita lisätään [suunniteltuina kutsuina](#planned-invites), he näkyvät niin ikään valittavina henkilöinä. Jos haluat estää vieraskäyttäjiä käyttämästä Power BI:tä, käytä Azure AD:n ehdollista käyttöoikeuskäytäntöä.

## <a name="who-can-you-invite"></a>Kenet voi kutsua?

Vieraskäyttäjiä sallitaan organisaatioosi useimmista sähköpostipalveluista. Myös henkilökohtaiset tilit, kuten gmail.com, outlook.com tai hotmail.com, ovat sallittuja. Azure AD B2B:ssä näitä osoitteita kutsutaan *sosiaalisiksi käyttäjätiedoiksi*.

Et voi kutsua julkishallinnon pilvipalveluun, kuten [Yhdysvaltain valtionhallinnon Power BI](service-govus-overview.md), liittyviä käyttäjiä.

## <a name="invite-guest-users"></a>Vieraskäyttäjien kutsuminen

Vieraskäyttäjät tarvitsevat kutsun vain, kun kutsut heidät organisaatioosi ensimmäisen kerran. Voit kutsua käyttäjiä suunniteltujen tai ad hoc ‑kutsujen avulla.

Käytä seuraavia ominaisuuksia, jotta voit käyttää ad hoc ‑kutsuja:
* Raporttien ja koontinäyttöjen jakaminen
* Sovelluksen käyttöoikeusluettelo

Ad hoc ‑kutsuja ei tueta työtilojen käyttöoikeusluetteloilla. Voit lisätä kyseiset käyttäjät organisaatioosi [suunniteltujen kutsujen](#planned-invites) avulla. Kun ulkoinen käyttäjä on vieras organisaatiossasi, lisää hänet työtilan käyttöoikeusluetteloon.

### <a name="planned-invites"></a>Suunnitellut kutsut

Käytä suunniteltua kutsua, jos tiedät, keitä haluat kutsua. Voit lähettää kutsun Azure-portaalin tai PowerShellin avulla. Sinun on oltava vuokraajan järjestelmänvalvoja, jotta voit kutsua ihmisiä.

Näitä ohjeita noudattamalla voit lähettää kutsuja Azure-portaalissa.

1. Valitse [Azure-portaalissa](https://portal.azure.com)**Azure Active Directory**.

1. Valitse **Hallinta**-kohdassa **Käyttäjät** > **Kaikki käyttäjät** > **Uusi vieraskäyttäjä**.

    ![Näyttökuva Azure-portaalista, jossa näkyy Uusi vieraskäyttäjä -asetus.](media/service-admin-azure-ad-b2b/azure-ad-portal-new-guest-user.png)

1. Kirjoita **sähköpostiosoite** ja **henkilökohtainen viesti**.

    ![Näyttökuva Azure AD -portaalin Uusi vieraskäyttäjä -valintaikkunasta.](media/service-admin-azure-ad-b2b/azure-ad-portal-invite-message.png)

1. Valitse **Kutsu**.

Kutsuaksesi enemmän kuin yhden vieraskäyttäjän, käytä PowerShelliä. Lisätietoja on artikkelissa [Azure Active Directory B2B yhteistyökoodi and PowerShell-mallit](/azure/active-directory/b2b/code-samples/).

Vieraskäyttäjien tulee valita saapuneesta sähköpostikutsusta kohta **Aloita**. Vieraskäyttäjä lisätään tämän jälkeen vuokraajaan.

![Näyttökuva vieraskäyttäjän sähköpostikutsusta.](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Ad hoc -kutsut

Lähettääksesi ulkoiselle käyttäjälle kutsun milloin tahansa, lisää hänet koontinäyttöösi tai raporttiisi jaetun käyttöliittymän kautta tai sovelluksen käyttöoikeussivulta. Seuraavassa esimerkki siitä, miten vieraskäyttäjän kutsuminen toimii sovelluksen kautta.

![Näyttökuva vieraskäyttäjästä, joka on lisätty sovelluksen käyttöoikeuslistaan Power BI:ssä.](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Vieraskäyttäjä saa sähköpostin, josta ilmenee että olet jakanut sovelluksen hänen kanssaan.

![Näyttökuva, jossa sovelluksen sähköposti jaetaan vieraskäyttäjälle](media/service-admin-azure-ad-b2b/guest-user-invite-email-2.png)

Vieraskäyttäjän tulee kirjautua sisään organisaatiossaan käyttämällä sähköpostiosoitteella. Sisäänkirjautumisen jälkeen he saavat kehotuksen hyväksyä kutsu. Sisäänkirjautumisen jälkeen sovellus aukeaa vieraskäyttäjälle. Jotta käyttäjä voi palata sovellukseen, hänen kannattaa lisätä linkki kirjanmerkkeihin tai tallentaa sähköposti.


## <a name="licensing"></a>Käyttöoikeudet

Vieraskäyttäjällä on oltava tarvittavat käyttöoikeudet, jotta hän voi tarkastella jakamaasi sisältöä. On kolme tapaa varmistaa, että käyttäjällä on tarvittava käyttöoikeus: Power BI Premiumin käyttäminen, Power BI Pro -käyttöoikeuden määrittäminen tai vieraan Power BI Pro -käyttöoikeuden käyttäminen.

[Vieraskäyttäjät, jotka voivat muokata ja hallita sisältöä organisaatiossa](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization), tarvitsevat Power BI Pro ‑käyttöoikeudet lisätäkseen sisältöä työtiloihin ja jakaakseen sisältöä muille.

### <a name="use-power-bi-premium"></a>Power BI Premiumia käyttämällä

Työtilan määrittäminen [Power BI Premium -kapasiteettiin](service-premium-what-is.md) sallii vieraskäyttäjän käyttää sovellusta ilman Power BI Pro -käyttöoikeutta. Power BI Premium sallii sovellusten myös hyödyntää muita toimintoja, kuten parannettua päivitystaajuutta, varattua kapasiteettia sekä suuria malleja.

![Kaavio vieraskäyttäjän käyttökokemuksesta, Power BI Premium.](media/service-admin-azure-ad-b2b/license-approach-1.png)

### <a name="assign-a-power-bi-pro-license-to-guest-user"></a>Määritä Power BI Pro -käyttöoikeus vieraskäyttäjälle

Power BI Pro -käyttöoikeuden määrittäminen vuokraajan vieraskäyttäjälle sallii kyseisen vieraskäyttäjän tarkastella sisältöä. Lisätietoja käyttöoikeuksien määrittämisestä on artikkelissa [Käyttöoikeuksien määrittäminen käyttäjille käyttöoikeussivulta](/office365/admin/manage/assign-licenses-to-users#assign-licenses-to-users-on-the-licenses-page). Ennen kuin määrität Pro-käyttöoikeuksia vieraskäyttäjille, ota yhteyttä Microsoft-tiliedustajaan varmistaaksesi, että se noudattaa Microsoft-sopimuksesi ehtoja.

![Kaavio vieraskäyttäjän käyttökokemuksesta, Pro-käyttöoikeuden määrittäminen vuokraajasta.](media/service-admin-azure-ad-b2b/license-approach-2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Vieraskäyttäjä tuo oman Power BI Pro-käyttöoikeutensa

Vieraskäyttäjällä on jo vuokraajan Power BI Pro -käyttöoikeus.

![Kaavio vieraskäyttäjän käyttökokemuksesta, oman käyttöoikeuden käyttäminen.](media/service-admin-azure-ad-b2b/license-approach-3.png)

## <a name="guest-users-who-can-edit-and-manage-content"></a>Vieraskäyttäjät, jotka voivat muokata ja hallita sisältöä

Kun käytät [salli ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) -ominaisuutta, erikseen määritetyt vieraskäyttäjät saavat organisaatiosi Power BI:n lisäkäyttöoikeudet. Sallitut vieraat näkevät kaiken sisällön, jonka käyttöoikeudet heillä on. Lisäksi he voivat käyttää aloitussivua, selata työtiloja, asentaa sovelluksia, nähdä nimensä käyttöoikeusluettelossa ja lisätä sisältöä työtiloihin. He voivat luoda ja hallinnoida järjestelmänvalvojina uutta käyttökokemusta käyttäviä työtiloja. Käyttöön liittyy joitakin rajoituksia. Rajoitukset mainitaan Huomioitavat asiat ja rajoitukset -luettelossa.
 
Voit auttaa näitä käyttäjiä kirjautumaan Power BI:hin antamalla heille vuokraajan URL-osoitteen. Etsi vuokraajan URL-osoite seuraavien vaiheiden mukaisesti.

1. Valitse Power BI -palvelun yläreunan valikosta ohje ( **?** ) ja sitten **Tietoja Power BI:stä**.

2. Katso arvo kohdan **Vuokraajan URL-osoite** vierestä. Jaa vuokraajan URL-osoite sallituille vieraskäyttäjillesi.

    ![Näyttökuva Tietoja Power BI:stä -valintaikkunassa, jossa näkyy vieraskäyttäjän vuokraajan URL-osoite.](media/service-admin-azure-ad-b2b/power-bi-about-dialog.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

* Ulkoisten Azure AD B2B -vieraiden pääsy on lähtökohtaisesti rajattu pelkkään kuluttajasisältöön. Ulkoiset Azure AD B2B -vieraat voivat tarkastella sovelluksia, koontinäyttöjä ja raportteja, viedä tietoja ja luoda sähköpostitilauksia koontinäytöille ja raporteille. He eivät pääse käsiksi työtilaan tai pysty julkaisemaan omaa sisältöään. Voit poistaa nämä rajoitukset käyttämällä [Salli ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) ‑toimintoa.

* Vieraskäyttäjien kutsumiseen tarvitaan Power BI Pro -käyttöoikeus. Pro-kokeiluversion käyttäjät eivät voi kutsua vieraskäyttäjiä Power BI:ssä.

* [Vieraskäyttäjät, jotka voivat muokata ja hallita organisaation sisältöä](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization), eivät voi käyttää joitain ominaisuuksia. Jos he haluavat päivittää tai julkaista raportteja, heidän tulee käyttää Power BI -palvelun verkkokäyttöliittymää, mm. Nouda tiedot, Power Bi Desktop -tiedostojen lataamiseksi verkkoon.  Seuraavia käyttökokemuksia ei tueta:
    * Suorajulkaisu Power BI Desktopista Power BI -palveluun
    * Vieraskäyttäjät eivät voi käyttää Power BI Desktopia yhteyden muodostamiseksi Power BI -palvelussa sijaitseviin palvelutietojoukkoihin
    * Office 365 -ryhmiin sidotut perinteiset työtilat:
        * Vieraskäyttäjät eivät voi luoda tällaisia työtiloja eivätkä hallita niitä järjestelmänvalvojina.
        * Vieraskäyttäjät voivat olla jäseniä.
    * Ad hoc -kutsujen lähettämistä ei tueta työtilojen käyttöoikeusluetteloilla.
    * Power BI Publisher for Exceliä ei tueta vieraskäyttäjillä.
    * Vieraskäyttäjät eivät voi asentaa Power BI Gatewaytä ja yhdistää sitä organisaatioosi.
    * Vieraskäyttäjät eivät voi asentaa sovelluksia julkaistaviksi koko organisaatiolle.
    * Vieraskäyttäjät eivät voi käyttää, luoda, päivittää eivätkä asentaa organisaation sisältöpaketteja.
    * Vieraskäyttäjät eivät voi käyttää Analysoi Excelissä -toimintoa.
    * Vieraskäyttäjiä ei voi mainita (@mentioned) kommentoitaessa.
    * Vieraskäyttäjät eivät voi käyttää paketteja.
    * Vieraskäyttäjillä, jotka käyttävät tätä ominaisuutta, on oltava työpaikan tai oppilaitoksen tili. 
    
* Vieraskäyttäjät, jotka käyttävät henkilökohtaista tiliä, kokevat enemmän rajoituksia kirjautumisrajoitusten vuoksi.
    * He voivat käyttää Power BI -palvelun kulutuskokemuksia verkkoselaimella
    * He eivät voi käyttää Power BI -mobiilisovelluksia.
    * He eivät voi kirjautua sisään antamaan tunnistetietoja, jos vaatimuksena on työ-tai koulutili.

* Tämä ominaisuus ei ole tällä hetkellä käytettävissä Power BI:n SharePoint Online -raportin verkko-osiossa.

* Eräät Active Directory -asetukset voivat rajoittaa ulkoisten vieraskäyttäjien toimintamahdollisuuksia yleisen organisaatiosi sisällä. Tämä koskee myös Power BI -ympäristösi. Seuraava dokumentaatio käsittelee asetuksia:
    * [Ulkoisen yhteistyön asetusten hallinta](/azure/active-directory/b2b/delegate-invitations#configure-b2b-external-collaboration-settings)
    * [Salli tai estä tiettyjen organisaatioiden kutsut B2B-käyttäjille](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)
    * [Salli tai estä vieraskäyttäjiä käyttämästä Power BI -palvelua](/azure/active-directory/conditional-access/overview)
    
* Organisaation ulkopuolista jakamista ei tueta kansallisissa pilvipalveluissa. Luo sen sijaan organisaatioosi käyttäjätilejä, joita ulkoiset käyttäjät voivat käyttää sisällön käyttämiseen. 

* Jos jaat suoraan vieraskäyttäjälle, Power BI lähettää heille linkin sähköpostitse. Jos et halua lähettää sähköpostiviestiä, lisää vieraskäyttäjä käyttöoikeusryhmään ja jaa kyseiselle käyttöoikeusryhmälle.  

## <a name="next-steps"></a>Seuraavat vaiheet

Tarkempia tietoja muun muassa siitä, miten rivitason suojaus toimii, löytyy teknisestä raportista: [Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla](https://aka.ms/powerbi-b2b-whitepaper).

Lisätietoja Azure AD B2B:stä on artikkelissa [Mitä tarkoittaa Azure AD B2B -yhteistyö?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b/).
