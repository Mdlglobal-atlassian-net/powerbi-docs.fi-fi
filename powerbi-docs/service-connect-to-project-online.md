---
title: Yhteyden muodostaminen Project Onlineen Power BI:llä
description: Project Online Power BI:lle
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 1d0cb4531dca1f200adbb21514fb49df8c872ecc
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/04/2018
ms.locfileid: "30816059"
---
# <a name="connect-to-project-online-with-power-bi"></a>Yhteyden muodostaminen Project Onlineen Power BI:llä
Microsoft Project Online on joustava online-ratkaisu projektiportfolion hallintaan (PPM) ja päivittäiseen työhön. Project Onlinella organisaatiot voivat aloittaa ja priorisoida projektiportfolion sijoituksia sekä toimittaa suunnitellun liiketoiminta-arvon. Power BI:n Project Online -sisältöpaketin avulla voit tarkastella projektitietojasi valmiilla mittareilla. Käytettävissä on esimerkiksi portfolion tila ja projektin vaatimustenmukaisuus.

Muodosta yhteys [Project Online -sisältöpakettiin](https://app.powerbi.com/getdata/services/project-online) Power BI:tä varten.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunasta **Nouda tiedot**.
   
    ![](media/service-connect-to-project-online/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-project-online/services.png)
3. Valitse **Microsoft Project Online** \> **Nouda**.
   
   ![](media/service-connect-to-project-online/mproject.png)
4. Kirjoita **Project Web Appin URL-osoite** -tekstiruutuun yhdistettävän Project Web Appin (PWA) URL-osoite ja valitse **Seuraava**. Huomaa, että se poiketa esimerkistä, jos käytössäsi on mukautettu toimialue.
   
    ![](media/service-connect-to-project-online/params.png)
5. Valitse todennusmenetelmäksi **oAuth2** \> **Kirjaudu sisään**. Anna pyydettäessä Project Onlinen tunnistetietosi ja noudata todennusprosessia.
   
    ![](media/service-connect-to-project-online/creds.png)
    
Huomaa, että sinulla on oltava yhdistettävässä Project Web Appissa portfolion tarkastelijan, portfolion ylläpitäjän tai järjestelmänvalvojan oikeudet.

6. Näet ilmoituksen tietojesi lataamisesta. Lataaminen voi kestää jonkin aikaa tilin koosta riippuen. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon. Tämä on oletuskoontinäyttö, jonka Power BI on luonut tietojen näyttämistä varten. Voit muokata tätä koontinäyttöä, jotta näet tiedot juuri haluamallasi tavalla.
   
   ![](media/service-connect-to-project-online/dashboard2.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md)
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana.

## <a name="next-steps"></a>Seuraavat vaiheet
[Aloita Power BI:n käyttö](service-get-started.md)

[Nouda tietoja Power BI:ssä](service-get-data.md)

