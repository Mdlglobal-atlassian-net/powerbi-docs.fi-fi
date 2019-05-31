---
title: Impala-tietokantaan yhdistäminen Power BI Desktopissa
description: Impala-tietokantaan yhdistäminen ja tietokannan käyttäminen helposti Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 0befceba2651ad4f8f414d3669c5830c07ece06d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514201"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Impala-tietokantaan yhdistäminen Power BI Desktopissa
Power BI Desktopissa voit muodostaa yhteyden **Impala**-tietokantaan ja käyttää sen tietoja samaan tapaan kuin muita tietolähteitä käytetään Power BI Desktopissa.

## <a name="connect-to-an-impala-database"></a>Impala-tietokantaan yhdistäminen
Muodosta yhteys **Impala**-tietokantaan seuraavasti: 

1. Valitse **Nouda tiedot** Power BI Desktopin **Aloitus**-valintanauhasta. 

2. Valitse vasemmalla näkyvistä luokista **Tietokanta**. Näkyviin tulee **Impala**.

    ![Nouda tiedot](media/desktop-connect-impala/connect_impala_2.png)

3. Kirjoita tai liitä Impala-palvelimen nimi avautuvan **Impala**-ikkunan ruutuun. Valitse **OK**. Voit **tuoda** tiedot suoraan Power BI:hin tai käyttää **DirectQueryä**. Lue lisätietoja [DirectQueryn käyttämisestä](desktop-use-directquery.md).

    ![Impala-ikkuna](media/desktop-connect-impala/connect_impala_3a.png)

4. Kirjoita pyydettäessä tunnistetiedot tai muodosta yhteys anonyymisti. Impala-liitin tukee anonyymiä todentamista, perustodentamista (käyttäjänimi ja salasana) sekä Windows-todentamista.

    ![Impala-liitin](media/desktop-connect-impala/connect_impala_4.png)

    > [!NOTE]
    > Kun annat tietyn **Impala**-palvelimen käyttäjänimen ja salasanan, Power BI Desktop käyttää samoja tunnistetietoja, kun yhteyttä yritetään muodostaa seuraavan kerran. Voit muokata näitä tunnistetietoja valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Tietolähdeasetukset**.


5. Kun yhteys on muodostettu, näyttöön avautuu **Siirtymistoiminto**-ikkuna, jossa näkyvät palvelimella käytettävissä olevat tiedot. Valitse näistä tiedoista elementtejä, jotka tuodaan ja joita käytetään **Power BI Desktopissa**.

    ![Siirtymistoimintoikkuna](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset
Seuraavat **Impala**-liittimeen liittyvät rajoitukset ja tärkeät seikat on syytä huomioida:

* Impala-liitintä tuetaan paikallisessa tietoyhdyskäytävässä, kun käytetään mitä tahansa kolmesta tuetusta todentamistavasta.

## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden moniin eri tietolähteisiin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   

