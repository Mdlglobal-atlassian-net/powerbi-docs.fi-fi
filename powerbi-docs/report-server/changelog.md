---
title: Power BI -raporttipalvelimen muutosloki
description: Power BI -raporttipalvelimen muutoslokissa on listattu jokaisen koontiversion uudet ominaisuudet ja ohjelmavirhekorjaukset.
services: powerbi
documentationcenter: ''
author: jtarquino
manager: jonhp
backup: maggies
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/11/2017
ms.author: tankas
ms.openlocfilehash: 67b9a162d689a8615a3e2459295eab6dad6d2364
ms.sourcegitcommit: 312390f18b99de1123bf7a7674c6dffa8088529f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/16/2018
---
# <a name="changelog-for-power-bi-report-server"></a>Power BI -raporttipalvelimen muutosloki

Power BI -raporttipalvelimen muutoslokissa on listattu jokaisen koontiversion uudet ominaisuudet ja ohjelmavirhekorjaukset.

Lisätietoja uusista ominaisuuksista on artikkelissa [Power BI -raporttipalvelinten uudet ominaisuudet](whats-new.md). 

## <a name="march-2018"></a>Maaliskuu 2018
- **Power BI -raporttipalvelin**
    - *Versio 1.2.6660.39920 (koontiversio 15.0.2.389), julkaistu 28.3.2018*
        - Ohjelmavirhekorjauksia
            - Korjattu Power BI -raporttien (PBIX) ongelma, joka esti tietojen viemisen Power BI:n visualisoinneista.
            - Korjattu Power BI -raporttien (PBIX) ongelma, joka esti URL-suodattimien toiminnan.
            - Korjattu sivutettujen raporttien (RDL) ongelma, joka esti kuvien näkymisen oikein IE11:ssä Power BI -raporttipalvelimen maaliskuun päivityksen jälkeen.

    - *Versio 1.2.6648.38132 (koontiversio 15.0.2.378), julkaistu 19.3.2018*
        - Suojauspäivitykset
        - Helppokäyttötoimintojen parannuksia
        - Ohjelmavirhekorjauksia
            - Korjattu sivutettujen raporttien (RDL) ongelma, joka esti parametrien näkyvyyden linkitetyssä raportissa, kun se palautettiin ominaisuuksien muokkaamisen jälkeen.
            - Korjattu verkkoportaalin mukautettujen lomakkeiden todennuksen ongelma, joka jätti huomioimatta siirtyvän vanhenemisen evästeen.
            - Korjattu Wordiin liittyvä ongelma, joka aiheutti epätasaisen rivikorkeuden, jos rivin sisältö on tyhjä.
            - Korjattu sivutettujen raporttien (RDL) ongelma, joka poisti lausekepohjaisen yhteysmerkkijonon, kun tietolähteen tunnistetietoja muutettiin.
            - Korjattu ongelma, joka liittyi mahdollisuuteen käyttää suorituskykyilmaisinta tekstiarvojen kanssa.
            - Korjattu sivutettujen raporttien (RDL) ongelma, joka esti mahdollisuuden määrittää uusi tietojoukko olemassa olevalle sivutetulle raportille.
            - Muita vakauteen ja käytettävyyteen liittyviä korjauksia.

- **Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)**
    - Versio: 2.56.5023.1043 (maaliskuu 2018), julkaistu 19.3.2018
        - Sisältää Power BI -raporttipalvelinyhteyden edellyttämiä muutoksia (maaliskuu 2018).

## <a name="october-2017"></a>Lokakuu 2017

- **Power BI -raporttipalvelin**
    - *Versio 1.1.6582.41691 (koontiversio 14.0.600.442), julkaistu 10.1.2018*
        - Suojauspäivitykset
        - Ohjelmavirhekorjauksia
            - Korjattu Model.GetParameters-kutsu, joka palautti tilakoodin 400.
            - Korjattu virhe, joka liittyi jaetun tietojoukon asettamiseen olemassa oleviin sivutettuihin raportteihin (RDL).
            - Korjattu ilmoitukseen ExecutionNotFoundException liittyvä virhe, joka ilmeni vietäessä eri parametriarvoilla määritettyä raporttia PDF:ksi.

    - *Versio 1.1.6551.5155 (koontiversio 14.0.600.438), julkaistu 11.12.2017*
        - Ohjelmavirhekorjauksia
            - Korjattu virhe, joka esti tietojen tallentamisen tiettyjen Power BI Desktop -raporttien päivittämisen jälkeen.

    - *Versio 1.1.6530.30789 (koontiversio 14.0.600.437), julkaistu 17.11.2017*
        - Ohjelmavirhekorjauksia
            - Korjattu perustodennuksen skenaarioiden virhe. 
            - Korjattu ongelma, joka esti arkipäivien valitsemisen tilauksiin, välimuistin päivityssuunnitelmiin ja historiatilannevedoksiin portaalin aikataulusivulla.
            - Korjattu sivutettujen raporttien (RDL) ongelma, joka tuotti värien ja fonttien osalta väärin näkyviä arvoja sellaisille tekstiruudun ilmauksille, joiden CanGrow-ominaisuusjoukon arvoksi on asetettu epätosi.
            - Korjattu Power BI -raporttien (PBIX) ongelma, joka tuotti tyhjän visualisoinnin, kun viivakaavioon lisättiin selitteitä.

    - *Versio 1.1.6514.9163 (koontiversio 14.0.600.434), julkaistu 1.11.2017*
        - Ohjelmavirhekorjauksia
            - Korjattu yli 500 megatavun kokoisten PBIX-raporttien lataamisen epävakausongelma.
            - Korjattu yli gigatavun kokoisten PBIX-raporttien lataamisen ongelma.

    - *Versio 1.1.6513.3500 (koontiversio 14.0.600.433), julkaistu 31.10.2017*
        - Ominaisuudet
            - Upotettujen tietomallien tuki
            - Excel-työkirjan tarkasteleminen (Office Online Server -integrointi käytössä)
            - Ajoitettu tietojen päivittäminen (PBIX)
            - Suorien kyselyjen tuki
            - Suurten tiedostojen tuki (jopa 2 Gt)
            - Julkinen REST-ohjelmointirajapinta
            - Jaettujen tietojoukkojen tuki Power BI Desktopissa (oDatan kautta)
            - URL-parametrin tuki PBIX-tiedostoille
            - Helppokäyttötoimintojen parannuksia

- **Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)**
    - *Versio 2.51.4885.3981 (lokakuu 2017), julkaistu 10.4.2018*
        - Suojauspäivitykset

    - *Versio 2.51.4885.2501 (lokakuu 2017), julkaistu 10.1.2018*
        - Suojauspäivitykset

    - *Versio 2.51.4885.1423 (lokakuu 2017), julkaistu 17.11.2017*
        - Ohjelmavirhekorjauksia
            - Korjattu ongelma, joka esti 32-bittisen Power BI Desktopin toiminnan x86-käyttöjärjestelmässä.
            - Korjattu Power BI -raportteihin (PBIX) liittyvä ongelma, joka esti x-akselin ruudukon näkymisen.
            - Muita pieniä ohjelmavirhekorjauksia

    - *Versio 2.51.4885.1041 (lokakuu 2017), julkaistu 31.10.2017*
        - Ominaisuudet
            - Sisältää Power BI -raporttipalvelinyhteyden edellyttämiä muutoksia (maaliskuu 2017).

## <a name="june-2017"></a>Kesäkuu 2017

- **Power BI -raporttipalvelin**
    - *Versio 14.0.600.309, julkaistu 10.1.2018*
        - Suojauspäivitykset

    - *Versio 14.0.600.305, julkaistu 19.9.2017*  
        - Ohjelmavirhekorjauksia
            - Päivitys uusimpaan [Bing-karttojen verkko-ohjausobjektiin](https://msdn.microsoft.com/library/mt712542.aspx)

    - *Koontiversio 14.0.600.301, julkaistu 11.7.2017*
        - Ohjelmavirhekorjauksia
            - Korjattu ongelma, joka aiheutti {{UserId}}-tunnisteen ratkaisemisen tallennettuihin tunnistetietoihin sen sijaan, että raportti suoritettaisiin Power BI -raporteissa.
            - Korjattu ongelma, joka esti tiettyjen kuvien piirtymisen Power BI -raporttipalvelimen raportteihin.
            - Korjattu ongelma, joka esti Power BI -raportin nimen muuttamisen Power BI -raporttipalvelimessa.
            - Korjattu ongelma, joka esti mukautettujen visualisointien lataamisen Power BI -mobiilisovellukseen ilman paikallisen välimuistin tyhjentämistä asentamalla mobiilisovellus uudelleen.

    - *Koontiversio 14.0.600.271, julkaistu 12.6.2017*
        - Power BI -raporttipalvelimen ensimmäinen julkaisu

- **Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)**
    - *Versio 2.47.4766.4901 (kesäkuu 2017), julkaistu 10.1.2018*
        - Suojauspäivitykset

## <a name="next-steps"></a>Seuraavat vaiheet

[Käyttöopas](user-handbook-overview.md)  
[Järjestelmänvalvojien opas](admin-handbook-overview.md)  
[Pikaopas: Power BI -raporttipalvelimen asentaminen](quickstart-install-report-server.md)  
[Raportin muodostimen asentaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) -työkalujen lataaminen](http://go.microsoft.com/fwlink/?LinkID=616714)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
