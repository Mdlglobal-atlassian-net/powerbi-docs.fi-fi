---
title: Hallitse tietojoukkojen käyttöä kaikissa työtiloissa (esikatselu) – Power BI
description: Lue ohjeet siihen, miten voit rajoittaa tiedonkulkua Power BI -vuokraajassa.
author: maggiesMSFT
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d1ad29bebc148d9f30e8d22240dd149787251a0a
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83285436"
---
# <a name="control-the-use-of-datasets-across-workspaces-preview"></a>Tietojoukkojen käytön hallinta työtiloissa (esikatselu)

Tietojen käyttö työtiloissa on tehokas tapa edistää tietokulttuuria ja tietojen demokratisoitumista organisaatiossasi. Jos olet Power BI -järjestelmänvalvoja, haluat kuitenkin ehkä joskus rajoittaa tietojen kulkua Power BI -vuokraajassasi. Vuokraajan **Käytä tietojoukkoja eri työtiloissa** -asetuksella voit rajoittaa tietojoukon uudelleenkäytön kokonaan tai osittain käyttöoikeusryhmien mukaan.

![Power BI -järjestelmän työtila-asetukset](media/service-datasets-admin-across-workspaces/power-bi-admin-workspace-settings.png)

Jos poistat tämän asetuksen käytöstä, se vaikuttaa raporttien luojiin seuraavasti:

- Painike raporttien kopioimiseksi työtilojen välillä ei ole käytettävissä. 
- **Muokkaa raporttia** -painike ei ole käytettävissä jaettuun tietojoukkoon perustuvassa raportissa.
- Power BI -palvelun resurssienetsintä näyttää vain nykyisen työtilan tietojoukot.
- Power BI Desktopin resurssienetsintä näyttää tietojoukot vain niistä työtiloista, joiden jäsen olet.
- Jos käyttäjät avaavat Power BI Desktopissa .pbix-tiedoston, jossa on reaaliaikainen yhteys tietojoukkoon sellaisessa työtilassa, jonka jäsen käyttäjä ei ole, käyttäjä saa virheilmoituksen, jossa häntä pyydetään muodostamaan yhteys toiseen tietojoukkoon.

## <a name="provide-a-link-for-the-certification-process"></a>Anna linkki sertifiointiprosessiin

Vuokraajan järjestelmänvalvojana voit antaa **Lisätietoja**-linkin URL-osoitteen **Tukeminen**-asetussivulla.  Linkki voi viedä sertifiointiprosessin ohjeisiin. Jos et anna kohdetta **Lisätietoja**-linkille, se osoittaa oletusarvoisesti [tietojoukon sertifiointia](service-datasets-certify.md) käsittelevään ohjeartikkeliin.

![Tietojoukon sertifiointi Lisätietoja](media/service-datasets-certify-promote/power-bi-dataset-learn-more-certification.png)

## <a name="next-steps"></a>Seuraavat vaiheet

- [Tietojoukkojen käyttö eri työtiloissa (esikatselu)](service-datasets-across-workspaces.md)
- Onko sinulla kysymyksiä? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
