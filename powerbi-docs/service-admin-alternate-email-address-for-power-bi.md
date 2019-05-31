---
title: Käytä vaihtoehtoinen sähköpostiosoite
description: Käytä vaihtoehtoinen sähköpostiosoite
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 88432f55fc8cfeefa07b66ea68437bbb23f12531
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906636"
---
# <a name="use-an-alternate-email-address"></a>Käytä vaihtoehtoinen sähköpostiosoite

Kun rekisteröidyt Power BI:n käyttäjäksi, sinun tulee antaa sähköpostiosoite. Oletusarvon mukaan Power BI käyttää tätä osoitetta lähettäessään palvelun toimintaa koskevia päivityksiä. Jos joku esimerkiksi lähettää sinulle jakamiskutsun, se lähetetään sinulle kyseiseen osoitteeseen.

Joissakin tapauksissa haluat ehkä, että nämä viestit lähetetään muuhun kuin siihen sähköpostiosoitteeseen, jota käytit rekisteröitymiseen. Tässä artikkelissa kerrotaan, miten voit määrittää vaihtoehtoisen osoitteen Office 365:ssä ja PowerShellissa. Artikkelissa kerrotaan myös, kuinka Azure Active Directory (Azure AD) korjaa sähköpostiosoite.

> [!NOTE]
> Vaihtoehtoisen osoitteen määrittäminen ei vaikuta siihen, mitä sähköpostiosoitetta Power BI käyttää palvelupäivityksien, uutiskirjeiden ja muiden markkinointiviestien lähettämisessä. Ilmoituksissa lähetetään aina määritettyyn sähköpostiosoitteeseen, kun olet rekisteröitynyt Power BI käyttää.

## <a name="use-office-365"></a>Office 365:n käyttäminen

Jos haluat määrittää vaihtoehtoisen osoitteen Office 365:ssä, toimi seuraavasti.

1. Avaa [Office 365:n Henkilökohtaiset tiedot ‑sivu](https://portal.office.com/account/#personalinfo). Jos sovellus pyytää, kirjaudu sisään sähköpostiosoitteesi ja salasanasi, voit käyttää Power BI.

1. Valitse vasemmasta valikosta **Henkilökohtaiset tiedot**.

1. Valitse **Yhteystiedot**-osiossa **Muokkaa**.

    Jos et voi muokata Omat tiedot, tämä tarkoittaa Office 365-järjestelmänvalvoja hallitsee sähköpostiosoitettasi. Ota yhteyttä järjestelmänvalvojaasi ja päivittää sähköpostiosoitteen.

    ![Yhteystiedot](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)

1. Tässä **vaihtoehtoinen sähköpostiosoite** kentän, Anna sähköpostiosoite, jota haluat käyttää Power BI-päivitykset Office 365: ssä.

## <a name="use-powershell"></a>PowerShellin käyttäminen

Voit määrittää vaihtoehtoisen osoitteen PowerShellissa [Set-AzureADUser](/powershell/module/azuread/set-azureaduser/)-komennolla.

```powershell
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

## <a name="email-address-resolution-in-azure-ad"></a>Sähköpostiosoitteen tulkinta Azure AD:ssä

Sieppaa Azure AD upotustunnus Power BI, voit käyttää jotakin kolmentyyppisiä sähköpostiosoitteet:

* Käyttäjän Azure AD-tiliisi liittyvä ensisijainen sähköpostiosoite

* UserPrincipalName (UPN) ‑sähköpostiosoite

* *muu sähköpostiosoite* -matriisimäärite

Power BI valitsee seuraavan järjestyksen mukaisesti, mitä niistä käytetään:

1. Jos Azure AD -vuokraajan käyttäjäobjektissa on olemassa postimäärite, Power BI käyttää kyseistä postimääritettä sähköpostiosoitteena.

1. Jos UPN-sähköpostiosoite *ei* ole **\*.onmicrosoft.com**-toimialueen sähköpostiosoite (tiedot \@-merkin jälkeen), Power BI käyttää kyseistä postimääritettä sähköpostiosoitteena.

1. Jos *muulla sähköpostiosoitteella* -Azure AD-käyttäjäobjektissa on matriisimäärite ja Power BI käyttää luettelon ensimmäistä sähköpostiosoitetta, (sillä voi olla tässä määritteessä luettelo).

1. Jos mikään edellä mainituista ehdoista ei täyty, Power BI käyttää UPN-osoitetta.

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)