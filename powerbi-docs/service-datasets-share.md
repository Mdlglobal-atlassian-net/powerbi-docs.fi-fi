---
title: Tietojoukon jakaminen (esikatselu)
description: Tietojoukon omistajana voit luoda ja jakaa tietojoukkoja, jotta muutkin voivat käyttää niitä. Opi jakamaan niitä.
author: maggiesMSFT
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: ce8a404a53eebb88bbd72998f10fd94a649b8af8
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "73872480"
---
# <a name="share-a-dataset-preview"></a>Tietojoukon jakaminen (esikatselu)

Power BI Desktopin *tietomallien* luojana luot *tietojoukkoja*, joita voit jakaa Power BI -palvelussa. Sen jälkeen muut raporttien luojat voivat käyttää tietojoukkojasi omien raporttiensa pohjana. Tässä artikkelissa kerrotaan, miten tietojoukkoja jaetaan. Lisätietoja siitä, miten voit antaa ja poistaa jaettujen tietojoukkojen käyttöoikeuksia, on artikkelissa [Muodostamisoikeus](service-datasets-build-permissions.md).

## <a name="steps-to-sharing-your-dataset"></a>Tietojoukon jakamisohjeet

1. Aloita luomalla .pbix-tiedosto tietomallin avulla Power BI Desktopissa. Jos aiot tarjota tätä tietojoukkoa muille raporttien luomiseen, et ehkä edes suunnittele raporttia .pbix-tiedostossa.

    Paras käytäntö on tallentaa .pbix-tiedosto Office 365 -ryhmään.

1. Julkaise .pbix-tiedosto Power BI -palvelun [uuden käyttöliittymän työtilaan](service-create-the-new-workspaces.md).
    
    Tämän työtilan muut jäsenet voivat jo luoda raportteja muihin tähän tietojoukkoon perustuviin työtiloihin.

1. Voit myös [julkaista sovelluksen](service-create-distribute-apps.md) tästä työtilasta. Kun teet sen, voit määrittää **käyttöoikeuksien** sivulla, kenellä on mitkäkin käyttöoikeudet.

    > [!NOTE]
    > Jos valitset **Koko organisaatio**, kellään organisaatiossa ei ole muodostamisoikeutta. Tämä on jo tunnettu ongelma. Määritä sen sijaan sähköpostiosoitteet **tiettyjen henkilöiden tai ryhmien** kohdassa.  Jos haluat antaa muodostamisoikeuden koko organisaatiolle, määritä sähköpostialias koko organisaatiolle.

    ![Sovelluskäyttöoikeuksien määrittäminen](media/service-datasets-build-permissions/power-bi-dataset-app-permission-new-look.png)

1. Valitse **Julkaise sovellus**. Jos sovellus on jo julkaistu, valitse **Päivitä sovellus**.

## <a name="track-your-dataset-usage"></a>Tietojoukon käytön seuranta

Kun sinulla on työtilassasi jaettu tietojoukko, sinun täytyy ehkä tietää, mitkä muiden työtilojen raportit perustuvat siihen.

1. Valitse Tietojoukot-luettelonäkymässä **Näytä aiheeseen liittyvät**.

    ![Näytä aiheeseen liittyvä kuvake](media/service-datasets-build-permissions/power-bi-dataset-view-related-to-dataset.png)

1. Näet kaikki liittyvät kohteet **aiheeseen liittyvän sisällön** valintaikkunasta. Näet luettelosta tähän työtilaan ja **muihin työtiloihin** liittyvät kohteet.
 
    ![Aiheeseen liittyvän sisällön valintaikkuna](media/service-datasets-build-permissions/power-bi-dataset-related-workspaces.png)

## <a name="next-steps"></a>Seuraavat vaiheet

- [Tietojoukkojen käyttö eri työtiloissa (esikatselu)](service-datasets-across-workspaces.md)
- Onko sinulla kysymyksiä? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
