---
title: Vaihtoehtoisen sähköpostiosoitteen käyttö
description: Vaihtoehtoisen sähköpostiosoitteen käyttö
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
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906636"
---
# <a name="use-an-alternate-email-address"></a>Vaihtoehtoisen sähköpostiosoitteen käyttö

Kun rekisteröidyt Power BI:n käyttäjäksi, sinun tulee antaa sähköpostiosoite. Oletusarvon mukaan Power BI käyttää tätä osoitetta lähettäessään palvelun toimintaa koskevia päivityksiä. Jos joku esimerkiksi lähettää sinulle jakamiskutsun, se lähetetään sinulle kyseiseen osoitteeseen.

Joissakin tapauksissa haluat ehkä, että nämä viestit lähetetään muuhun kuin siihen sähköpostiosoitteeseen, jota käytit rekisteröitymiseen. Tässä artikkelissa kerrotaan, miten voit määrittää vaihtoehtoisen osoitteen Office 365:ssä ja PowerShellissa. Artikkelissa kerrotaan myös, miten sähköpostiosoite tulkitaan Azure Active Directoryssa (Azure AD).

> [!NOTE]
> Vaihtoehtoisen osoitteen määrittäminen ei vaikuta siihen, mitä sähköpostiosoitetta Power BI käyttää palvelupäivityksien, uutiskirjeiden ja muiden markkinointiviestien lähettämisessä. Nämä viestit lähetetään aina siihen sähköpostiosoitteeseen, jolla rekisteröidyit Power BI:n käyttäjäksi.

## <a name="use-office-365"></a>Office 365:n käyttäminen

Jos haluat määrittää vaihtoehtoisen osoitteen Office 365:ssä, toimi seuraavasti.

1. Avaa [Office 365:n Henkilökohtaiset tiedot ‑sivu](https://portal.office.com/account/#personalinfo). Jos sovellus antaa kehotteen, kirjaudu sisään käyttämällä sähköpostiosoitetta ja salasanaa, joilla kirjaudut Power BI:hin.

1. Valitse vasemmasta valikosta **Henkilökohtaiset tiedot**.

1. Valitse **Yhteystiedot**-osiossa **Muokkaa**.

    Jos et voi muokata omia tietojasi, tämä tarkoittaa, että Office 365 -järjestelmänvalvoja hallitsee sähköpostiosoitettasi. Pyydä järjestelmänvalvojaa päivittämään sähköpostiosoitteesi.

    ![Yhteystiedot](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)

1. Kirjoita **Vaihtoehtoinen sähköposti**  ‑kenttään sähköpostiosoite, jota haluat Office 365:n käyttävän Power BI ‑päivityksissä.

## <a name="use-powershell"></a>PowerShellin käyttäminen

Voit määrittää vaihtoehtoisen osoitteen PowerShellissa [Set-AzureADUser](/powershell/module/azuread/set-azureaduser/)-komennolla.

```powershell
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

## <a name="email-address-resolution-in-azure-ad"></a>Sähköpostiosoitteen tulkinta Azure AD:ssä

Voit siepata Azure AD:hen upotettavan tunnuksen Power BI:tä varten käyttämällä jotakin kolmesta erityyppisestä sähköpostiosoitteesta:

* ensisijainen sähköpostiosoite, joka on liitetty käyttäjän Azure AD -tiliin

* UserPrincipalName (UPN) ‑sähköpostiosoite

* *muu sähköpostiosoite* -matriisimäärite

Power BI valitsee seuraavan järjestyksen mukaisesti, mitä niistä käytetään:

1. Jos Azure AD -vuokraajan käyttäjäobjektissa on olemassa postimäärite, Power BI käyttää kyseistä postimääritettä sähköpostiosoitteena.

1. Jos UPN-sähköpostiosoite *ei* ole **\*.onmicrosoft.com**-toimialueen sähköpostiosoite (tiedot \@-merkin jälkeen), Power BI käyttää kyseistä postimääritettä sähköpostiosoitteena.

1. Jos Azure AD -käyttäjäobjektissa on matriisimäärite *muu sähköpostiosoite*, Power BI käyttää luettelon ensimmäistä sähköpostiosoitetta (sillä tässä määritteessä voi olla sähköpostiosoitteista luettelo).

1. Jos mikään edellä mainituista ehdoista ei täyty, Power BI käyttää UPN-osoitetta.

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)