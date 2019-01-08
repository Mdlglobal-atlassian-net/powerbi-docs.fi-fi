---
title: Yhteyden muodostaminen Project Onlineen Power BI:llä
description: Project Online Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: dd6698cab5b9fed407e6e8f45ceb160209a38fae
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007564"
---
# <a name="connect-to-project-online-with-power-bi"></a>Yhteyden muodostaminen Project Onlineen Power BI:llä
Microsoft Project Online on joustava online-ratkaisu projektiportfolion hallintaan (PPM) ja päivittäiseen työhön. Project Onlinella organisaatiot voivat aloittaa ja priorisoida projektiportfolion sijoituksia sekä toimittaa suunnitellun liiketoiminta-arvon. Power BI:n Project Online -sisältöpaketin avulla voit saada merkityksellisiä tietoja Project Onlinesta projektien, portfolioiden ja resurssien hallinnan helpottamiseksi.

Muodosta yhteys [Project Online -sisältöpakettiin](https://app.powerbi.com/getdata/services/project-online) Power BI:tä varten.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
    ![](media/service-connect-to-project-online/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-project-online/services.png)
3. Valitse **Microsoft Project Online** \> **Nouda**.
   
   ![](media/service-connect-to-project-online/mproject.png)
4. Kirjoita **Project Web Appin URL-osoite** -tekstiruutuun yhdistettävän Project Web Appin (PWA) URL-osoite ja valitse **Seuraava**. Huomaa, että se poiketa esimerkistä, jos käytössäsi on mukautettu toimialue. Valitse **PWA-sivuston kieli** -tekstiruutu ja kirjoita numero, joka vastaa PWA-sivuston kieltä. Kirjoita numero ”1” englannille, ”2” ranskalle, ”3” saksalle, ”4” portugalille (Brasilia), ”5” portugalille (Portugali) ja ”6” espanjalle. 
   
    ![](media/service-connect-to-project-online/params.png)
5. Valitse todennusmenetelmäksi **oAuth2**\>**Kirjaudu sisään**. Anna pyydettäessä Project Onlinen tunnistetietosi ja noudata todennusprosessia.
   
    ![](media/service-connect-to-project-online/creds.png)
    
Huomaa, että sinulla on oltava yhdistettävässä Project Web Appissa portfolion tarkastelijan, portfolion ylläpitäjän tai järjestelmänvalvojan oikeudet.

6. Näet ilmoituksen tietojesi lataamisesta. Lataaminen voi kestää jonkin aikaa tilin koosta riippuen. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, 13 raporttia ja tietojoukon. Tämä on oletuskoontinäyttö, jonka Power BI on luonut tietojen näyttämistä varten. Voit muokata tätä koontinäyttöä, jotta näet tiedot juuri haluamallasi tavalla.

   ![](media/service-connect-to-project-online/dashboard2.png)

7. Kun koontinäyttö ja raportit ovat valmiita, jatka eteenpäin ja aloita Project Online -tietojesi tarkasteleminen! Sisältöpaketin mukana toimitetaan 13 monipuolista ja yksityiskohtaista raporttia portfolion yleiskatsausta varten (6 raporttisivua), resurssin yleiskatsaus (5 raporttisivua) ja projektin tila (2 raporttisivua). 

   ![](media/service-connect-to-project-online/report1.png)
   
   ![](media/service-connect-to-project-online/report3.png)
   
   ![](media/service-connect-to-project-online/report2.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

**Laajenna sisältöpakettia**

Lataa [GitHub PBIT -tiedosto](https://github.com/OfficeDev/Project-Power-BI-Content-Packs), jotta voit edelleen mukauttaa ja päivittää sisältöpakettia

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

