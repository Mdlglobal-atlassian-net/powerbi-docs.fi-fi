---
title: Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla
description: Power BI on integroitu Azure Active Directory Business-to-Businessin (Azure AD B2B) kanssa, jotta Power BI -sisältöä voidaan jakaa turvallisesti organisaation ulkopuolisten vierailevien käyttäjien kanssa.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: dded0f38ccc4c871bf402240aba25b11106bac09
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973208"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla

Power BI on integroitu Azure Active Directory Business-to-Businessiin (Azure AD B2B), jotta Power BI -sisältöä voidaan jakaa turvallisesti organisaation ulkopuolisille vieraskäyttäjille säilyttäen samalla sisäisten tietojen hallinta.

## <a name="enable-access"></a>Käytön salliminen

Varmista, että [Vienti- ja jakamisasetukset](service-admin-portal.md#export-and-sharing-settings) -ominaisuus on käytössä Power BI -hallintaportaalissa ennen vieraskäyttäjien kutsumista.

## <a name="who-can-you-invite"></a>Kenet voi kutsua?

Voit kutsua vieraskäyttäjiä millä tahansa sähköpostiosoitteella, myös henkilökohtaisilla tileillä, kuten gmail.com, outlook.com tai hotmail.com. Azure AD B2B:ssä näitä osoitteita kutsutaan *sosiaalisiksi käyttäjätiedoiksi*.

## <a name="invite-guest-users"></a>Vieraskäyttäjien kutsuminen

Kutsuja edellytetään vain kun ulkoinen vieraskäyttäjä kutsutaan organisaatioon ensimmäisen kerran. Voit kutsua käyttäjiä kahdella tavalla: suunnitelluilla kutsuilla ja ad-hoc-kutsuilla.

### <a name="planned-invites"></a>Suunnitellut kutsut

Käytä suunniteltua kutsua, jos tiedät, keitä haluat kutsua. Voit lähettää kutsun Azure-portaalin tai PowerShellin avulla. Sinun on oltava vuokraajan järjestelmänvalvoja, jotta voit kutsua ihmisiä.

Näitä ohjeita noudattamalla voit lähettää kutsuja Azure-portaalissa.

1. Valitse [Azure-portaalissa](https://portal.azure.com) **Azure Active Directory**.

1. Valitse **Hallinta**, siirry kohtaan **Käyttäjät** > **Kaikki käyttäjät** > **Uusi vieraskäyttäjä**.

    ![Azure AD -portaali - Uusi vieraskäyttäjä](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

1. Kirjoita **sähköpostiosoite** ja **henkilökohtainen viesti**.

    ![Azure AD -portaali - uuden vieraskäyttäjän kutsuviesti](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

1. Valitse **Kutsu**.

Kutsuaksesi enemmän kuin yhden vieraskäyttäjän, käytä PowerShelliä. Lisätietoja on artikkelissa [Azure Active Directory B2B yhteistyökoodi and PowerShell-mallit](/azure/active-directory/b2b/code-samples/).

Vieraskäyttäjien tulee valita saapuneesta sähköpostikutsusta kohta **Aloita**. Vieraskäyttäjä lisätään tämän jälkeen vuokraajaan.

![Vieraskäyttäjän sähköpostikutsu](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Ad-hoc -kutsu

Lähettääksesi kutsun milloin tahansa, lisää ulkoinen käyttäjä koontinäyttöösi tai raporttiisi jaetun käyttöliittymän kautta, tai sovelluksen käyttöoikeussivulta. Seuraavassa esimerkki siitä, miten vieraskäyttäjän kutsuminen toimii sovelluksen kautta.

![Ulkopuolinen käyttäjä lisätään sovelluksen käyttöoikeus -listaan](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Vieraskäyttäjä saa sähköpostin, jossa ilmoitetaan, että sovellus on jaettu hänen kanssaan.

![Sovelluksen sähköposti jaetaan vieraskäyttäjälle](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

Vieraskäyttäjän tulee kirjautua sisään organisaatiossaan käyttämällä sähköpostiosoitteella. Sisäänkirjautumisen jälkeen heitä pyydetään hyväksymään kutsu. Sisäänkirjautumisen jälkeen vieraskäyttäjä ohjataan sovelluksen sisällön luo. Jotta käyttäjä voi palata sovellukseen, hän voi lisätä linkin kirjanmerkkeihin tai tallentaa sähköpostin.

## <a name="licensing"></a>Käyttöoikeudet

Vieraskäyttäjällä on oltava tarvittavat käyttöoikeudet, jotta hän voi tarkastella jaettua sovellusta. Tähän on olemassa kolme vaihtoehtoa: Power BI Premiumin käyttäminen, Power BI Pro -käyttöoikeuden määrittäminen tai vieraan Power BI Pro -käyttöoikeuden käyttäminen.

### <a name="use-power-bi-premium"></a>Power BI Premiumia käyttämällä

Sovelluksen työtilan määrittäminen [Power BI Premium -kapasiteettiin](service-premium.md) sallii vieraskäyttäjän käyttää sovellusta ilman Power BI Pro -käyttöoikeutta. Power BI Premium sallii sovellusten myös hyödyntää muita toimintoja, kuten parannettua päivitystaajuutta, varattua kapasiteettia sekä suuria malleja.

![Power BI Premiumia käyttämällä](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-a-power-bi-pro-license-to-guest-user"></a>Määritä Power BI Pro -käyttöoikeus vieraskäyttäjälle

Power BI Pro -käyttöoikeuden määrittäminen vuokraajan vieraskäyttäjälle sallii kyseisen vieraskäyttäjän tarkastella sisältöä.

![Määritä Pro -käyttöoikeus vuokraajalta](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Vieraskäyttäjä tuo oman Power BI Pro-käyttöoikeutensa

Vieraskäyttäjällä on jo vuokraajan Power BI Pro -käyttöoikeus.

![Vieraskäyttäjä tuo oman käyttöoikeutensa](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

* Ulkoisten B2B-vieraiden pääsy on rajattu pelkkään kuluttajasisältöön. Ulkoiset B2B-vieraat voivat tarkastella sovelluksia, koontinäyttöjä ja raportteja, viedä tietoja ja luoda sähköpostitilauksia koontinäytöille ja raporteille. He eivät pääse käsiksi työtilaan tai pysty julkaisemaan omaa sisältöään.

* Tämä ominaisuus ei ole tällä hetkellä käytettävissä Power BI -mobiilisovelluksissa. Jaettua Power BI -sisältöä voi tarkastella mobiililaitteella käyttämällä Azure AD B2B:ta selaimessa.

* Tämä ominaisuus ei ole tällä hetkellä käytettävissä Power BI:n SharePoint Online -raportin verkko-osiossa.

## <a name="next-steps"></a>Seuraavat vaiheet

Tarkempia tietoja, myös rivitason suojauksen toiminnasta, on teknisessä raportissa [Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla](https://aka.ms/powerbi-b2b-whitepaper).

Lisätietoja Azure AD B2B:stä on artikkelissa [Mitä tarkoittaa Azure AD B2B -yhteistyö?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b/).
