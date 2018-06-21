---
title: Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla
description: Power BI on integroitu Azure Active Directory Business-to-Businessin (Azure AD B2B) kanssa, jotta Power BI -sisältöä voidaan jakaa turvallisesti organisaation ulkopuolisten vierailevien käyttäjien kanssa.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 6e1665b6e9c9ff0a756d9ccdaf9e6feb4ed9eb39
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34722220"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Power BI -sisällön jakaminen ulkoisille vieraskäyttäjille Azure AD B2B:n avulla

Power BI on integroitu Azure Active Directory Business-to-Businessin (Azure AD B2B) kanssa, jotta Power BI -sisältöä voidaan jakaa turvallisesti organisaation ulkopuolisten vierailevien käyttäjien kanssa, säilyttäen samalla sisäisten tietojen hallinnan.

> [!VIDEO https://www.youtube.com/embed/xxQWEQ1NnlY]

> [!NOTE]
> Sinun on **otettava käyttöön** [Vienti- ja jakamisasetukset](service-admin-portal.md#export-and-sharing-settings) -ominaisuus Power BI -järjestelmävalvojaportaalin vuokraaja-asetuksista ennen vierailevien käyttäjien kutsumista.

> [!NOTE]
> Tämä ominaisuus ei ole tällä hetkellä käytettävissä Power BI -mobiilisovelluksissa. Jaettua Power BI -sisältöä voi tarkastella mobiililaitteella käyttämällä Azure AD B2B:ta selaimessa. 

## <a name="who-can-you-invite"></a>Kenet voi kutsua?

Voit kutsua vieraskäyttäjiä, millä tahansa sähköpostiosoitteella, mukaan lukien henkilökohtaiset tilit, kuten gmail.com, outlook.com tai hotmail.com. Azure B2B:ssä näitä kutsutaan nimellä ”Yhteisö tunnukset”. Lisätietoja löytyy [Azure B2B](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)-viitteestä.

## <a name="invite-guest-users"></a>Vieraskäyttäjien kutsuminen

Power BI -vuokraajaan voi kutsua vieraskäyttäjiä kahdella tavalla: suunnitellut kutsut tai ad-hoc -kutsut. Kutsuja tarvitaan vain kun ulkopuolinen käyttäjä kutsutaan organisaatioosi ensimmäisen kerran.

### <a name="planned-invites"></a>Suunnitellut kutsut

Suunniteltu kutsu toteutetaan Azure AD:n Microsoft Azure -portaalista tai PowerShelliä käyttämällä. Tätä menetelmää voi käyttää, jos tiedetään mitkä käyttäjät pitää kutsua. 

**Uusien käyttäjien luominen Azure AD -portaaliin edellyttää, että olet vuokraajan järjestelmävalvoja.**

1. Siirry [Azure-portaaliin](https://portal.azure.com) ja valitse **Azure Active Directory**.

2. Siirry **Käyttäjät ja ryhmät** > **Kaikki käyttäjät** > **Uusi vieraskäyttäjä**.

    ![Azure AD -portaali - Uusi vieraskäyttäjä](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

3. Syötä **sähköpostiosoite** ja **henkilökohtainen viesti**.

    ![Azure AD -portaali - uuden vieraskäyttäjän kutsuviesti](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

4. Valitse **Kutsu**.

Kutsuaksesi enemmän kuin yhden vieraskäyttäjän, käytä PowerShelliä. Lisätietoja saat [Azure Active Directory B2B yhteistyökoodi and PowerShell-mallit](https://docs.microsoft.com/azure/active-directory/b2b/code-samples) -artikkelista.

Vieraskäyttäjien tulee valita saapuneesta sähköpostikutsusta kohta **Aloita**. Vieraskäyttäjä lisätään tämän jälkeen vuokraajaan.

![Vieraskäyttäjän sähköpostikutsu](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Ad-hoc -kutsu

Lähettääksesi kutsun milloin tahansa, lisää ulkoinen käyttäjä koontinäyttöösi tai raporttiisi jaetun käyttöliittymän kautta, tai sovelluksen käyttöoikeussivulta.

Seuraavassa esimerkki siitä, miten vieraskäyttäjän kutsuminen toimii sovelluksen kautta.
![Vieraskäyttäjä lisätään sovelluksen käyttöoikeus -listaan](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Vieraskäyttäjä saa sähköpostin, josta ilmenee että sovellus on jaettu hänen kanssaan.

![Sovelluksen sähköposti jaetaan vieraskäyttäjälle](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

Vieraskäyttäjän tulee kirjautua sisään organisaatiossaan käyttämällä sähköpostiosoitteella. Sisäänkirjautumisen jälkeen heitä pyydetään hyväksymään kutsu. Sisäänkirjautumisen jälkeen vieraskäyttäjä ohjataan sovelluksen sisällön luo. Palataksesi sovellukseen, lisää linkki kirjanmerkkeihin tai tallenna sähköposti.

## <a name="licensing"></a>Käyttöoikeudet

Vieraskäyttäjällä on oltava tarvittavat käyttöoikeudet, jotta hän voi tarkastella jaettua sovellusta. Tämän saavuttamiseksi on olemassa kolme vaihtoehtoa.

### <a name="use-power-bi-premium"></a>Power BI Premiumia käyttämällä

Sovelluksen työtilan määrittäminen Power BI Premium-kapasiteettiin sallii vieraskäyttäjän käyttää sovellusta edellyttämättä Power BI Pro -käyttöoikeutta. Power BI Premium sallii sovellusten myös hyödyntää muita toimintoja, kuten parannettua päivitystaajuutta, varattua kapasiteettia sekä suuria malleja.

![Power BI Premiumia käyttämällä](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-power-bi-pro-license-to-guest-user"></a>Määritä Power BI Pro-käyttöoikeus vieraskäyttäjälle

Power BI Pro -käyttöoikeuden määrittäminen vuokraajan vieraskäyttäjälle sallii kyseisen vieraskäyttäjän tarkastella sisältöä.

> [!NOTE]
> Vuokraajan Power BI Pro -käyttöoikeus koskee vieraskäyttäjää vain silloin kun he tarkastelevat vuokraajan sisältöä.

![Määritä Pro -käyttöoikeus vuokraajalta](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Vieraskäyttäjä tuo oman Power BI Pro-käyttöoikeutensa

Vieraskäyttäjällä on jo vuokraajan Power BI Pro -käyttöoikeus.

![Vieraskäyttäjä tuo oman käyttöoikeutensa](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

* Kun kutsut vieraskäyttäjät, jotka käyttävät henkilökohtaisia sähköpostitilejä, kuten gmail.com, outlook.com tai hotmail.com, voit seurata tätä [upotettu videota](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-redemption-experience) nähdäksesi esimerkin siitä, miten käyttäjä rekisteröinti tapahtuu.
* Ulkoisten B2B-vieraiden pääsy on rajattu pelkkään kuluttajasisältöön. Ulkoiset B2B-vieraat voivat tarkastella sovelluksia, koontinäyttöjä ja raportteja, viedä tietoja ja luoda sähköpostitilauksia koontinäytöille ja raporteille. He eivät pääse käsiksi työtilaan tai pysty julkaisemaan omaa sisältöään.
* Tämä ominaisuus ei ole tällä hetkellä käytettävissä Power BI -mobiilisovelluksissa. Jaettua Power BI -sisältöä voi tarkastella mobiililaitteella käyttämällä Azure AD B2B:ta selaimessa.
* Tämä ominaisuus ei ole tällä hetkellä käytettävissä Power BI:n SharePoint Online -raportin verkko-osiossa.

## <a name="next-steps"></a>Seuraavat vaiheet

Tarkempia tietoja mm. siitä, miten rivitason suojaus toimii, löytyy [teknisestä raportista](https://aka.ms/powerbi-b2b-whitepaper).

Lisätietoa Azure Active Directory B2B:stä löytyy [Mitä tarkoittaa Azure AD B2B -yhteistyö?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) -artikkelista
