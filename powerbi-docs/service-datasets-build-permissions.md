---
title: Jaettujen tietojoukkojen muodostamisoikeus (esiversio)
description: Lue ohjeet siihen, miten voit hallita tietojen käyttöä muodostamisoikeuden avulla.
author: maggiesMSFT
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/12/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 48380d40d819ea1af74430546b9548c372bd2091
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "77426606"
---
# <a name="build-permission-for-shared-datasets-preview"></a>Jaettujen tietojoukkojen muodostamisoikeus (esiversio)

Kun luot raportin Power BI Desktopissa, raportin tiedot tallennetaan *tietomalliin*. Kun julkaiset raporttisi Power BI -palvelussa, julkaiset tiedot myös *tietojoukkona*. Voit antaa muille *muodostamisoikeuden* kyseiseen raporttiin, jotta he voivat löytää jakamasi tietojoukon ja käyttää sen uudelleen. Tässä artikkelissa on ohjeet siihen, miten voit hallita tietojen käyttöä muodostamisoikeuden avulla.

Muodostamisoikeus koskee tietojoukkoja. Kun annat käyttäjille muodostamisoikeuksia, he voivat luoda uutta sisältöä tietojoukkosi perusteella, esimerkiksi raportteja, koontinäyttöjä, Q&A:n kiinnitettyjä ruutuja ja merkityksellisten tietojen hakuja. 

Käyttäjillä on myös oltava muodostamisoikeudet, jotta he voivat käsitellä tietoja Power BI:n *ulkopuolella*:

- Pohjana olevien tietojen vieminen.
- Uuden sisällön luominen tietojoukon perusteella, esimerkiksi [Analysoi Excelissä](service-analyze-in-excel.md) -toiminnolla.
- Tietojen käyttäminen XMLA-päätepisteen kautta.

## <a name="ways-to-give-build-permission"></a>Tapoja antaa muodostamisoikeus

Tietojoukon muodostamisoikeuden voi antaa muutamalla eri tavalla:

- Työtilan jäsenet, joilla on vähintään Osallistuja-rooli, saavat automaattisesti tietojoukon muodostamisoikeuden kyseiseen työtilaan sekä oikeuden kopioida raportti.
 
- Tietojoukon sisältävän työtilan jäsenet voivat määrittää oikeuden tietyille käyttäjille tai käyttöoikeusryhmille käyttöoikeuskeskuksessa. Jos olet työtilan jäsen, valitse **Enemmän vaihtoehtoja** (…) tietojoukon vierestä > **Käyttöoikeuksien hallinta**.

    ![Valitse kolme pistettä](media/service-datasets-build-permissions/power-bi-dataset-permissions-new-look.png)

    Tämä avaa kyseisen tietojoukon käyttöoikeuskeskuksen, jossa voit määrittää ja muokata käyttöoikeuksia.

    ![Käyttöoikeuskeskus](media/service-datasets-build-permissions/power-bi-dataset-remove-permissions-no-callouts.png)

- Sen työtilan, jossa tietojoukko sijaitsee, jäsen tai järjestelmänvalvoja voi päättää sovelluksen julkaisemisen yhteydessä, että sovelluksen käyttöoikeuden saavat käyttäjät saavat muodostamisoikeudet myös taustalla oleviin tietojoukkoihin. Lisätietoja on kohdassa [Tietojoukon jakaminen](service-datasets-share.md).

- Oletetaan, että sinulla on tietojoukossa oikeudet muodostamiseen ja uudelleenjakamiseen. Kun jaat raportin tai koontinäytön, joka on muodostettu tähän tietojoukkoon, voit määrittää, että myös vastaanottajat saavat muodostamisoikeudet taustalla olevaan tietojoukkoon.

    ![Muodostamisoikeus](media/service-datasets-build-permissions/power-bi-share-report-allow-users.png)

Voit poistaa henkilöltä tietojoukon muodostamisoikeuden. Jos teet näin, käyttäjät näkevät yhtä jaettuun tietojoukkoon perustuvan raportin, mutta he eivät voi enää muokata sitä. Lisätietoja on seuraavassa osiossa.

## <a name="remove-build-permission-for-a-dataset"></a>Poista tietojoukon muodostamisoikeus

Jossakin vaiheessa sinun on ehkä poistettava muodostamisoikeus joiltakin jaetun tietojoukon käyttäjiltä. 

1. Siirry työtilassa **Tietojoukot**-luettelosivulle. 
1. Valitse **Enemmän vaihtoehtoja** (...) tietojoukon vierestä > **Käyttöoikeuksien hallinta**.

    ![Käyttöoikeuksien hallinta](media/service-datasets-build-permissions/power-bi-dataset-permissions-new-look.png)

1. Valitse **Enemmän vaihtoehtoja** (...) nimen vierestä > **Poista muodostaminen**.

    ![Poista muodostamisoikeus](media/service-datasets-build-permissions/power-bi-dataset-remove-build-permissions.png)

    Käyttäjät näkevät yhtä jaettuun tietojoukkoon perustuvan raportin, mutta he eivät voi enää muokata sitä.

### <a name="remove-build-permission-for-a-dataset-in-an-app"></a>Poista tietojoukon muodostamisoikeus sovelluksessa

Oletetaan, että olet jakanut sovelluksen työtilasta ryhmälle henkilöitä. Myöhemmin päätät poistaa sovelluksen käyttöoikeuden joiltakin käyttäjiltä. Sovelluksen käyttöoikeuden poistaminen ei poista automaattisesti muodostamis-ja uudelleenjakamisoikeuksia. Tämä on ylimääräinen vaihe. 

1. Valitse työtilan luettelosivulla **Päivitä sovellus**. 

    ![Päivitä sovellus](media/service-datasets-build-permissions/power-bi-app-update.png)

1. Poista henkilö tai ryhmä valitsemalla **X** **Käyttöoikeudet**-välilehdellä. 

    ![Valitse X](media/service-datasets-build-permissions/power-bi-app-delete-user.png)
1. Valitse **Päivitä sovellus**.

    Näyttöön tulee viesti, jossa kerrotaan, että sinun on siirryttävä kohtaan **Käyttöoikeuksien hallinta**, jos haluat poistaa muodostamisoikeuden käyttäjiltä, joilla on olemassa oleva käyttöoikeus. 

    ![Käyttöoikeuksien hallinta -viesti](media/service-datasets-build-permissions/power-bi-dataset-app-remove-message.png)

1. Valitse **Päivitä**.

1. Siirry työtilassa **Tietojoukot**-luettelosivulle. 
1. Valitse **Enemmän vaihtoehtoja** (...) tietojoukon vierestä > **Käyttöoikeuksien hallinta**.

    ![Käyttöoikeuksien hallinta](media/service-datasets-build-permissions/power-bi-dataset-permissions-new-look.png)

1. Valitse **Enemmän vaihtoehtoja** (...) haluamasi nimen vierestä > **Poista muodostaminen**.

    ![Poista muodostamisoikeus](media/service-datasets-build-permissions/power-bi-dataset-remove-build-permissions.png)

    Käyttäjät näkevät yhtä jaettuun tietojoukkoon perustuvan raportin, mutta he eivät voi enää muokata sitä.

## <a name="more-granular-permissions"></a>Lisää eriytettyjä käyttöoikeuksia

Power BI:n muodostamisoikeus otettiin käyttöön kesäkuussa 2019 täydentämään olemassa olevia oikeuksia (luku- ja uudelleenjakamisoikeus). Kaikki käyttäjät, joilla oli jo lukuoikeudet tietojoukkoihin sovellusoikeuksien, jakamisen tai työtilan käytön kautta kesäkuussa 2019, saivat myös muodostamisoikeuden samoihin tietojoukkoihin. He saivat muodostamisoikeudet automaattisesti, koska lukuoikeus antoi heille jo oikeuden luoda uutta sisältöä tietojoukkoon Analysoi Excelissä -toiminnolla tai viemällä.

Tämän eriytetymmän muodostamisoikeuden avulla voit valita, ketkä voivat ainoastaan tarkastella olemassa olevaa raporttia tai koontinäyttöä ja ketkä voivat luoda sisältöä, joka on yhteydessä taustalla oleviin tietojoukkoihin.

Jos tietojoukkoasi käytetään raportissa tietojoukon työtilan ulkopuolella, et voi poistaa kyseistä työtilaa. Saat sen sijaan virheilmoituksen.

Voit poistaa muodostamisoikeuden. Jos poistat oikeuksia, käyttäjät, joiden oikeudet poistat, näkevät yhä raportin, mutta he eivät voi enää muokata sitä tai viedä pohjana olevia tietoja. Käyttäjät, joilla on vain lukuoikeus, voivat yhä viedä yhteenvedettyjä tietoja. 

## <a name="next-steps"></a>Seuraavat vaiheet

- [Tietojoukkojen käyttö eri työtiloissa (esikatselu)](service-datasets-across-workspaces.md)
- Onko sinulla kysymyksiä? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
