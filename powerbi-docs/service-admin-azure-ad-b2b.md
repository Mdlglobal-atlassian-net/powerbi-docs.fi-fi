---
title: Sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla
description: Power BI on integroitu Azure Active Directory Business-to-Businessin (Azure AD B2B) kanssa, jotta Power BI -sisältöä voidaan jakaa turvallisesti organisaation ulkopuolisten vierailevien käyttäjien kanssa.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 2d1e9e32fcec67647bb75ac14ed872e6c51fef96
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65101640"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla

Power BI on integroitu Azure Active Directory Business-to-Businessiin (Azure AD B2B), jotta Power BI -sisältöä voidaan jakaa turvallisesti organisaation ulkopuolisille vieraskäyttäjille säilyttäen samalla sisäisten tietojen hallinta.  

Lisäksi voit myös sallia organisaation ulkopuolisten vieraskäyttäjien muokata ja hallita organisaatiosi sisäistä sisältöä.

## <a name="enable-access"></a>Käytön salliminen

Ota [sisällön jakaminen ulkoisille käyttäjille](service-admin-portal.md#export-and-sharing-settings) ominaisuus ennen vierailevien käyttäjien kutsumista Power BI-hallintaportaalissa.

Voit myös käyttää [avulla ulkoinen vieraskäyttäjien muokkaaminen ja hallinta organisaatiossa](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) ominaisuus. Sen avulla voit valita, mitä Vieraskäyttäjä voit tarkastella ja luoda sisältöä työtiloissa, mukaan lukien selaamalla organisaatiosi Power BI.

## <a name="who-can-you-invite"></a>Kenet voi kutsua?

Voit kutsua vieraskäyttäjiä millä tahansa sähköpostiosoitteella, henkilökohtaiset tilit, kuten gmail.com, outlook.com ja hotmail.com mukaan lukien. Azure AD B2B: n kutsuu näitä osoitteita *sosiaalisen käyttäjätietojen*.

## <a name="invite-guest-users"></a>Vieraskäyttäjien kutsuminen

Vieraskäyttäjät edellyttävät kutsuja vain ne kutsu organisaatioosi ensimmäisen kerran. Voit kutsua käyttäjät kahdella tavalla: suunnitellut kutsut ja ad-hoc-kutsut.

### <a name="planned-invites"></a>Suunnitellut kutsut

Käytä suunniteltua kutsua, jos tiedät, keitä haluat kutsua. Voit lähettää kutsun Azure-portaalin tai PowerShellin avulla. Sinun on oltava vuokraajan järjestelmänvalvoja, jotta voit kutsua ihmisiä.

Näitä ohjeita noudattamalla voit lähettää kutsuja Azure-portaalissa.

1. Valitse [Azure-portaalissa](https://portal.azure.com) **Azure Active Directory**.

1. Valitse **hallinta**, valitse **käyttäjät** > **kaikkien käyttäjien** > **uusi Vieraskäyttäjä**.

    ![Näyttökuva Azure-portaalissa käyttäen uutta Vieras käyttäjän asetusta kutsutaan.](media/service-admin-azure-ad-b2b/azure-ad-portal-new-guest-user.png)

1. Kirjoita **sähköpostiosoite** ja **henkilökohtainen viesti**.

    ![Näyttökuva Azure AD Portal uusi Vieraskäyttäjä-valintaikkunassa.](media/service-admin-azure-ad-b2b/azure-ad-portal-invite-message.png)

1. Valitse **Kutsu**.

Kutsuaksesi enemmän kuin yhden vieraskäyttäjän, käytä PowerShelliä. Lisätietoja on artikkelissa [Azure Active Directory B2B yhteistyökoodi and PowerShell-mallit](/azure/active-directory/b2b/code-samples/).

Vieraskäyttäjien tulee valita saapuneesta sähköpostikutsusta kohta **Aloita**. Vieraskäyttäjä lisätään tämän jälkeen vuokraajaan.

![Näyttökuva-Vieraskäyttäjän sähköpostikutsu.](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Ad-hoc-kutsut

Jos haluat kutsua ulkoinen käyttäjä milloin tahansa, lisää ne koontinäyttöösi tai raporttiisi jaetun Käyttöliittymän kautta tai sovelluksen käyttöoikeussivulta. Seuraavassa esimerkki siitä, miten vieraskäyttäjän kutsuminen toimii sovelluksen kautta.

![Näyttökuva-Vieraskäyttäjä lisätään sovelluksen käyttöoikeus-listaan Power BI.](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Vieraskäyttäjä saa sähköpostin jakanut sovelluksen niitä.

![Näyttökuva-sovelluksen sähköposti jaetaan vieraskäyttäjälle](media/service-admin-azure-ad-b2b/guest-user-invite-email-2.png)

Vieraskäyttäjän tulee kirjautua sisään organisaatiossaan käyttämällä sähköpostiosoitteella. Ne tulee kehote, hyväksymään kutsu, kun olet kirjautunut sisään. Sisäänkirjautumisen jälkeen Vieraskäyttäjä Avaa sovellus. Jotta käyttäjä voi palata sovellukseen, hän voi lisätä linkin kirjanmerkkeihin tai tallentaa sähköpostin.

## <a name="licensing"></a>Käyttöoikeudet

Vieraskäyttäjällä on oltava tarvittavat käyttöoikeudet, voit tarkastella sisältöä, joka on jaettu. Varmista, että käyttäjällä on käyttöoikeutta kolmella: Käytä Power BI Premium, Määritä Power BI Pro-käyttöoikeus tai vieraan Power BI Pro-käyttöoikeus.

Kun käytät [Salli ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) -ominaisuutta, vieraskäyttäjät tarvitsevat Power BI Pro -käyttöoikeudet lisätäkseen sisältöä työtiloihin tai jakaakseen sisältöä toisille käyttäjille.

### <a name="use-power-bi-premium"></a>Power BI Premiumia käyttämällä

Sovelluksen työtila määrittäminen [Power BI Premium-kapasiteetin](service-premium-what-is.md) sallii vieraskäyttäjän käyttää sovellusta edellyttämättä Power BI Pro-käyttöoikeutta. Power BI Premium antaa myös hyödyntää muita toimintoja, kuten parannettua päivitystaajuutta, varattua kapasiteettia sekä suuria malleja sovelluksia.

![Vieras käyttäjän kokemusta Power BI Premium-kaavio.](media/service-admin-azure-ad-b2b/license-approach-1.png)

### <a name="assign-a-power-bi-pro-license-to-guest-user"></a>Määritä Power BI Pro -käyttöoikeus vieraskäyttäjälle

Vieras käyttäjän näkymän sisällön vuokraajan Power BI Pro-käyttöoikeuden määrittäminen vuokraajan vieraskäyttäjälle avulla.

![Määritä Pro-käyttöoikeus vuokraajalta Vieras käyttäjän kokemusta kaavio.](media/service-admin-azure-ad-b2b/license-approach-2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Vieraskäyttäjä tuo oman Power BI Pro-käyttöoikeutensa

Vieraskäyttäjällä on jo vuokraajan Power BI Pro -käyttöoikeus.

![Vieras käyttökokemus, kun ne tuo oman käyttöoikeutensa kaavio.](media/service-admin-azure-ad-b2b/license-approach-3.png)

## <a name="guest-users-who-can-edit-and-manage-content"></a>Vieraskäyttäjät, jotka voivat muokata ja hallita sisältöä 

Käytettäessä [avulla ulkoinen vieraskäyttäjien muokkaaminen ja hallinta organisaatiossa](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) uudeksi määritetty vieraskäyttäjät saavat pääsyn organisaatiosi Power BI. He näkevät sisältö, joihin heillä on käyttöoikeus. Ne käyttää Home, Selaa työtilat, asentaa sovelluksia, näet, jos ne ovat access-luetteloon ja lisätä sisältöä työtilat. He voivat luoda ja hallinnoida järjestelmänvalvojina uutta käyttökokemusta käyttäviä työtiloja. Joitakin rajoituksia sovelletaan. Huomioitavat asiat ja rajoitukset-osio luettelo rajoituksia.
 
Kirjaudu sisään Power BI-käyttäjille, joiden antaa ne vuokraajan URL-osoite. Etsi vuokraajan URL-osoite seuraavien vaiheiden mukaisesti.

1. Valitse Power BI -palvelun yläreunan valikosta ohje ( **?** ) ja sitten **Tietoja Power BI:stä**.

2. Katso arvo kohdan **Vuokraajan URL-osoite** vierestä. Arvo ei voi jakaa vierailevien käyttäjien vuokraajan URL-osoite.

    ![Näyttökuva-tietoja Power BI-valintaikkunassa URL-osoite, jota kutsutaan ulos Vieras käyttäjän vuokraajan kanssa.](media/service-admin-azure-ad-b2b/power-bi-about-dialog.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

* Oletusarvon mukaan ulkoisen Azure AD B2B rajoittaa vieraat pelkkään kuluttajasisältöön. Ulkoiset Azure AD B2B-vieraat voivat tarkastella sovelluksia, koontinäyttöjä ja raportteja, viedä tietoja ja luoda sähköpostitilauksia koontinäytöille ja raporteille. He eivät pääse käsiksi työtilaan tai pysty julkaisemaan omaa sisältöään. Kuitenkin nämä rajoitukset eivät koske vieraskäyttäjät, jotka muodostavat yhteyden kautta [avulla ulkoinen vieraskäyttäjien muokkaaminen ja hallinta organisaatiossa](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) ominaisuus.

* Vierailevien käyttäjien kautta [avulla ulkoinen vieraskäyttäjien muokkaaminen ja hallinta organisaatiossa](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) ominaisuus, jotkin ominaisuudet eivät ole käytettävissä niihin. Jos he haluavat päivittää tai julkaista raportteja, heidän tulee käyttää Power BI -palvelun verkkokäyttöliittymää, mm. Nouda tiedot, Power Bi Desktop -tiedostojen lataamiseksi verkkoon.  Seuraavia ominaisuuksia ei tueta:
    * Suorajulkaisu Power BI Desktopista Power BI -palveluun
    * Vieraskäyttäjät ei voi käyttää Power BI desktop muodostaa yhteyden palvelun tietojoukot Power BI-palvelussa
    * Office 365 -ryhmiin sidotut perinteiset työtilat:
        * Vieraskäyttäjä ei voi luoda tai järjestelmänvalvojiksi näistä työtiloista
        * Vieraskäyttäjät voivat olla jäseniä
    * Ad-hoc-pyyntöjen lähettämisen ei tueta työtilan käyttää luetteloita
    * Power BI Publisher for Excel ei tueta vieraskäyttäjät
    * Vieraskäyttäjät ei voi asentaa Power BI Gateway-ja yhdistetään organisaatioosi
    * Vieraskäyttäjät ei voi asentaa sovellusten julkaiseminen koko organisaatiolle
    * Vieraskäyttäjät ei voi käyttää, luoda, päivittää tai asenna organisaation Sisältöpaketit
    * Vieraskäyttäjät ei voi käyttää analysoi Excelissä
    * Vieraskäyttäjät ei voi olla @mentioned -kommentoinnin
    * Vieraskäyttäjät ei voi käyttää tilauksia
    * Vieraskäyttäjillä, jotka käyttävät tätä ominaisuutta, on oltava työpaikan tai oppilaitoksen tili. Vieraskäyttäjille henkilökohtaisten tilien tulla enemmän rajoituksia määräpäivä kirjautumaan sisään rajoituksia.

* Tämä ominaisuus ei ole tällä hetkellä käytettävissä Power BI SharePoint Onlinen raportin verkko-osa.

* Ei Active Directory-asetuksia, jotka voit rajoittaa ulkoisen Vieras ominaisuudet yleinen organisaatiossasi. Joka koskee myös Power BI-ympäristösi. Seuraava dokumentaatio käsittelee asetuksia:
    * [Ulkoisen yhteistyön asetusten hallinta](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations#control-who-can-invite)
    * [Salli tai estä tiettyjen organisaatioiden kutsut B2B-käyttäjille](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)  

## <a name="next-steps"></a>Seuraavat vaiheet

Tarkempia tietoja mukaan lukien miten rivitason suojaus toimii, tutustu tekninen raportti: [Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla](https://aka.ms/powerbi-b2b-whitepaper).

Katso lisätietoja Azure AD B2B [mikä Azure AD B2B-yhteistyö?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b/).
