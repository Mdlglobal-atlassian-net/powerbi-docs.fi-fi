---
title: Työtilan hallinta Power BI:ssä ja Office 365:ssä
description: Power BI:n työtilat ovat Office 365 -ryhmiin perustuva yhteistyötoiminto. Voit hallita työtiloja Power BI:ssä sekä Office 365:ssä.
author: maggiesMSFT
ms.reviewer: lukasz
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 27f3c88607f57be8b5abffdbec71ecfe80beea23
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348064"
---
# <a name="manage-your-workspace-in-power-bi-and-office-365"></a>Työtilan hallinta Power BI:ssä ja Office 365:ssä

[Power BI:ssä](service-create-distribute-apps.md) tai Office 365:ssä olevan työtilan luojana tai järjestelmänvalvojana voit hallita työtilan tiettyjä ominaisuuksia Power BI:ssä. Muita ominaisuuksia hallitaan Office 365:ssä.

> [!NOTE]
> Uusi työtilakokemus muuttaa Power BI -työtilojen ja Office 365:n ryhmien välistä suhdetta. Et automaattisesti luo Office 365 -ryhmää aina, kun luot uuden työtilan. Lue tietoja [uusien työtilojen luomisesta](service-create-the-new-workspaces.md).

**Power BI:ssä** suoritettavia toimintoja:

* Lisää tai poista työtilan jäseniä. Voit myös tehdä työtilan jäsenestä järjestelmänvalvojan.
* Muokkaa työtilan nimeä.
* Poista työtila, jolloin myös Office 365 -ryhmä poistetaan.

**Office 365:ssä** suoritettavia toimintoja:

* Lisää tai poista työtilan ryhmän jäseniä. Voit myös tehdä jäsenestä omistajan.
* Muokkaa ryhmän nimeä, kuvaa, kuvausta ja muita asetuksia.
* Tarkastele ryhmän sähköpostiosoitetta.
* Poista ryhmä.

Tarvitset [Power BI Pro -käyttöoikeuden](../fundamentals/service-features-license-type.md), jotta voit olla työtilan järjestelmänvalvoja tai jäsen. Sovelluksen käyttäjät tarvitsevat niin ikään Power BI Pro -käyttöoikeuden paitsi siinä tapauksessa, että työtilasi on Power BI Premium -ominaisuus. Lisätietoja on artikkelissa [Mikä on Power BI Premium?](../admin/service-premium-what-is.md)

## <a name="edit-your-workspace-in-power-bi"></a>Työtilan muokkaaminen Power BI:ssä

1. Valitse Power BI -palvelun **Työtilat**-kohdan vieressä oleva nuoli. Valitse **Lisää vaihtoehtoja** (...) työtilan nimen vieressä ja valitse **Muokkaa työtilaa**.

   ![Muokkaa työtilaa Power BI:ssä](media/service-manage-app-workspace-in-power-bi-and-office-365/power-bi-app-ellipsis.png)

   > [!NOTE]
   > Näet **Muokkaa työtilaa** -vaihtoehdon vain, jos olet työtilan järjestelmänvalvoja.

1. Täällä voit nimetä työtilan uudelleen, lisätä tai poistaa sen jäseniä tai poistaa työtilan.

   ![Muokkaa työtilaa -valintaikkuna](media/service-manage-app-workspace-in-power-bi-and-office-365/power-bi-app-edit-workspace.png)

1. Valitse **Tallenna** tai **Peruuta**.

## <a name="edit-power-bi-workspace-properties-in-office-365"></a>Power BI -työtilan ominaisuuksien muokkaaminen Office 365:ssä

Voit myös muokata työtilan ominaisuuksia suoraan Outlook for Office 365:ssä.

### <a name="edit-the-members-of-the-workspace-group"></a>Työtilaryhmän jäsenten muokkaaminen

1. Valitse Power BI -palvelun **Työtilat**-kohdan vieressä oleva nuoli. Valitse **Lisää vaihtoehtoja** (...) työtilan nimen vieressä ja valitse **Jäsenet**.

   ![Muokkaa työtilaa Power BI:ssä](media/service-manage-app-workspace-in-power-bi-and-office-365/power-bi-app-ellipsis-members.png)

   Tämä avaa työtilan Office 365:n Outlookin ryhmänäkymän. Voit joutua kirjautumaan sisään yritystililläsi.

1. Valitse rooli tiimin jäsenen nimen vieressä, jos haluat tehdä hänestä **jäsenen** tai **omistajan**. Valitse **X**, jos haluat poistaa henkilön ryhmästä.

   ![Muokkaa ryhmää Office 365:ssä](media/service-manage-app-workspace-in-power-bi-and-office-365/pbi_managegroupo365.png)

### <a name="add-an-image-and-set-other-workspace-properties"></a>Kuvan lisääminen ja työtilan muiden ominaisuuksien määrittäminen

Kun jakelet sovellustasi työtilasta, tässä lisäämäsi kuva näkyy sovelluksen kuvana. Lisätietoja on [Uusien työtilojen luominen](service-create-workspaces.md#add-an-image-to-your-office-365-workspace-optional) -artikkelin osiossa **Kuvan lisääminen Office 365:n uusiin työtiloihin**.

1. Siirry työtilasi Outlook for Office 365 -näkymässä **Tietoja**-välilehdelle ja valitse **Muokkaa**.

    ![Muokkaa ryhmää -kuvake](media/service-manage-app-workspace-in-power-bi-and-office-365/pbi_editgroupo365.png)
1. Voit muokata ryhmään liittyvien ilmoitusten nimeä, kuvausta ja kieltä. Voit myös lisätä kuvan ja valita muita ominaisuuksia täällä.

   ![Muokkaa ryhmää -valintaikkuna](media/service-manage-app-workspace-in-power-bi-and-office-365/pbi_editgrpo365dialog.png)

1. Valitse **Tallenna** tai **Hylkää**.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Julkaise sovellus Power BI:ssä](service-create-distribute-apps.md)

* Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
