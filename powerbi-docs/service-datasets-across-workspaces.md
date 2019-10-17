---
title: Johdanto tietojoukkojen käyttöön eri työtiloissa (esikatselu)
description: Lue ohjeet siihen, miten voit jakaa tietojoukon koko organisaation käyttäjien kanssa. Tämän ansiosta he voivat luoda omissa työtiloissaan raportteja, jotka perustuvat sinun tietojoukkoosi.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: e086cc89a24760bce0c4a45efd558dc47495bd04
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "72020778"
---
# <a name="intro-to-datasets-across-workspaces-preview"></a>Johdanto tietojoukkojen käyttöön eri työtiloissa (esikatselu)

Liiketoimintatiedon hallinta on yhteistyötä. On tärkeää luoda standardoituja tietojoukkoja, joita voidaan pitää eräänlaisina totuuden lähteinä. Näiden standardoitujen tietojoukkojen löytäminen ja uudelleenkäyttö ovat avainasemassa. Kun organisaatiosi parhaat tietomallintajat luovat ja jakavat standardoituja tietojoukkoja, raporttien tekijät voivat luoda tarkkoja raportteja näiden tietojoukkojen pohjalta. Tällä tavalla organisaatiosi saa käyttöönsä johdonmukaisia tietoja päätöksenteon tueksi. Tämä myös edistää tervettä tietokulttuuria.

![Valitse jaettu tietojoukko](media/service-datasets-across-workspaces/power-bi-select-shared-dataset.png)

Power BI:ssä tietojoukkojen tekijät voivat hallita tietojensa käyttöä [muodostamiskäyttöoikeuden](service-datasets-build-permissions.md) avulla. Tietojoukkojen tekijät voivat myös *sertifioida* ja *ylentää* tietojoukkoja, jotta muut löytävät ne. Näin raporttien tekijät tietävät, mitkä tietojoukot ovat laadukkaita ja virallisia, ja he voivat käyttää kyseisiä tietojoukkoja aina, kun tekevät töitä Power BI:ssä. Vuokraajan järjestelmänvalvojilla on uusi vuokraaja-asetus, jolla he voivat [hallita tietojoukkojen käyttöä eri työtiloissa](service-datasets-admin-across-workspaces.md).

## <a name="dataset-sharing-and-the-new-workspace-experience"></a>Tietojoukkojen jakaminen ja uudenlaiset työtilat

Raporttien luominen eri työtilojen tietojoukkojen pohjalta ja raporttien kopioiminen eri työtiloihin liittyvät tiukasti [uudenlaisiin työtiloihin](service-create-the-new-workspaces.md):

- Kun avaat palvelussa tietojoukkoluettelon uudenlaisessa työtilassa, tietojoukkoluettelossa näytetään oman työtilasi tietojoukot sekä muiden uudenlaisten työtilojen tietojoukot. 
- Kun avaat tietojoukkoluettelon perinteisessä työtilassa, näet vain tämän työtilan tietojoukot, et muiden työtilojen tietojoukkoja.
- Power BI Desktopissa voit julkaista reaaliaikaisen yhteyden raportteja eri työtiloihin, kunhan niiden tietojoukot ovat uudenlaisissa työtiloissa.
- Kun kopioit raportteja työtilasta toiseen, kohdetyötilan täytyy olla uudenlainen työtila.

## <a name="discover-datasets-preview"></a>Tietojoukkojen löytäminen (esikatselu)

Kun luot raporttia olemassa olevan tietojoukon avulla, ensimmäinen vaihe on yhteyden muodostaminen tietojoukkoon (joko Power BI -palvelussa tai Power BI Desktopissa). Lue lisätietoja [eri työtilojen tietojoukkojen etsimisestä (esikatselu)](service-datasets-discover-across-workspaces.md).

## <a name="copy-a-report"></a>Raportin kopioiminen

Kun löydät työtilasta tai sovelluksesta raportin, josta pidät, voit ottaa siitä kopion ja muokata sitä omiin tarpeisiisi. Sinun ei tarvitse huolehtia tietomallin luomisesta. Se on jo luotu sinulle. Lisäksi on paljon helpompaa muokata aiemmin luotua raporttia kuin aloittaa kokonaan alusta. Lue lisätietoja [raporttien kopioimisesta](service-datasets-copy-reports.md).

## <a name="build-permission-for-datasets"></a>Tietojoukkojen muodostamisoikeudet

Muodostamisoikeuden avulla voit tietojoukon tekijänä määrittää, ketkä organisaatiossa voivat luoda uutta sisältöä tietojoukkojesi pohjalta. Muodostamisoikeuden saaneet käyttäjät voivat luoda uutta sisältöä tietojoukkoon myös Power BI:n ulkopuolella, esimerkiksi Excel-laskentataulukoita Analysoi Excelissä -toiminnolla, XMLA:lla ja viemällä. Lue lisätietoja [muodostamisoikeudesta](service-datasets-build-permissions.md).

## <a name="promotion-and-certification"></a>Ylentäminen ja sertifiointi

Jos luot tietojoukkoja, voit luoda niitä myös muiden käyttöön. Voit helpottaa tietojoukkojen löytämistä [ylentämällä niitä](service-datasets-promote.md). Voit myös pyytää organisaatiosi asiantuntijoita [sertifioimaan tietojoukon](service-datasets-certify.md).

## <a name="licensing"></a>Käyttöoikeudet

Jaettuihin tietojoukkoihin perustuvien toimintojen ja ominaisuuksien käyttöoikeudet perustuvat niiden nykyisiin käyttötarkoituksiin. Esimerkki:

- Yleensä tietojoukkojen etsiminen ja niihin yhdistäminen on mahdollista kaikille – se ei ole Premium-käyttäjille rajoitettu ominaisuus.
- Käyttäjät, joilla ei ole Pro-käyttöoikeutta, voivat käyttää tietojoukkoja työtiloissa raportin luontia varten vain, jos nämä tietojoukot sijaitsevat käyttäjien henkilökohtaisessa Omassa työtilassa tai Premium-tilassa olevassa työtilassa. Sama käyttöoikeusrajoitus on käytössä riippumatta siitä, onko raportti kirjoitettu Power BI Desktopissa vai Power BI -palvelussa.
- Raporttien kopioimiseen työtilojen välillä tarvitaan Pro-käyttöoikeus.
- Raporttien kopiointi sovelluksesta edellyttää Pro-käyttöoikeutta (kuten organisaation sisältöpaketit).
- Tietojoukkojen ylentämiseen ja sertifioimiseen tarvitaan Pro-käyttöoikeus.

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

- Sovelluksen julkaisijana sinun on varmistettava, että yleisösi voi käyttää sovellustyötilan ulkopuolisia tietojoukkoja. Muussa tapauksessa käyttäjät voivat kohdata ongelmia käyttäessään sovellustasi: raportteja ei voi avata ilman tietojoukon käyttöoikeutta, ja koontinäytön ruudut näkyvät lukittuina. Käyttäjät eivät myöskään pysty avaamaan sovellusta, jos ensimmäinen siirtymiskohde on raportti, jolla ei ole tietojoukon käyttöoikeutta.
- Raportin luominen eri työtilan tietojoukon pohjalta edellyttää uudenlaisia työtiloja molemmissa päissä: raportin täytyy olla uudessa työtilassa ja tietojoukon täytyy olla uudessa työtilassa.
- Perinteisessä työtilassa tietojoukkojen etsintätoiminnossa näytetään vain nykyisen työtilan tietojoukot.
- Julkaise verkkoon -toiminto ei tarkoituksella toimi jaettuun tietojoukkoon perustuvassa raportissa.
- Jos kaksi ihmistä on jäsen työtilassa, joka käyttää jaettua työtilaa, ei ole mahdollista, että vain toinen heistä näkee liittyvän tietojoukon työtilassa. Vain käyttäjät, joilla on vähintään lukuoikeudet tietojoukkoon, näkevät jaetun tietojoukon. 

## <a name="next-steps"></a>Seuraavat vaiheet

- [Tietojoukkojen ylentäminen](service-datasets-promote.md)
- [Tietojoukkojen sertifioiminen](service-datasets-certify.md)
- [Tietojoukkojen käytön hallinta eri työtiloissa](service-datasets-admin-across-workspaces.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
