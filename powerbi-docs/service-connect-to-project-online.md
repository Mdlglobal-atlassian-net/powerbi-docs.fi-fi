---
title: Yhteyden muodostaminen Project Onlineen Power BI:llä
description: Project Online Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 52bd4b5dc27ff127eadea49cb3e761d6cda4788d
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249156"
---
# <a name="connect-to-project-online-with-power-bi"></a>Yhteyden muodostaminen Project Onlineen Power BI:llä
Microsoft Project Online on joustava online-ratkaisu projektiportfolion hallintaan (PPM) ja päivittäiseen työhön. Project Onlinella organisaatiot voivat aloittaa ja priorisoida projektiportfolion sijoituksia sekä toimittaa suunnitellun liiketoiminta-arvon. Power BI:n Project Online -sisältöpaketin avulla voit tarkastella projektitietojasi valmiilla mittareilla. Käytettävissä on esimerkiksi portfolion tila ja projektin vaatimustenmukaisuus.

Muodosta yhteys [Project Online -sisältöpakettiin](https://app.powerbi.com/getdata/services/project-online) Power BI:tä varten.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
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

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

