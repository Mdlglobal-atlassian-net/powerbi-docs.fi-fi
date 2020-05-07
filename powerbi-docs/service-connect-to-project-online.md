---
title: Yhteyden muodostaminen Project Onlineen Power BI:llä
description: Project Online Power BI:lle
author: SarinaJoan
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 07/25/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 32d731c354d848809d336392ef51f667b14427d8
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "74565695"
---
# <a name="connect-to-project-web-app-with-power-bi"></a>Yhteyden muodostaminen Project Web Appiin Power BI:llä
Microsoft Project Web App on joustava online-ratkaisu projektisalkun hallintaan (PPM) ja päivittäiseen työhön. Project Web Appin avulla organisaatiot voivat aloittaa ja priorisoida projektisalkun sijoituksia sekä toimittaa suunnitellun liiketoiminta-arvon. Power BI:n Project Web App -mallisovelluksen avulla voit saada merkityksellisiä tietoja Project-verkkosovelluksesta projektien, salkkujen ja resurssien hallinnan helpottamiseksi.

Muodosta yhteys Power BI:n [Project Web App -mallisovellukseen](https://appsource.microsoft.com/product/power-bi/pbi_msprojectonline.pbi-microsoftprojectwebapp).

## <a name="how-to-connect"></a>Yhdistäminen

1. Valitse **Sovellukset** siirtymisruudussa > valitse **Hanki sovelluksia** oikeassa yläkulmassa.

    ![Hanki sovelluksia](media/service-connect-to-project-online/GetApps.png)

2. Valitse **Palvelut**-ruudusta **Nouda**.
   
   ![AppSource](media/service-connect-to-project-online/AppSource.png)
3. Valitse AppSourcessa **Sovellukset**-välilehti ja hae tai valitse **Microsoft Project Web App**.
   
4. Kun näkyviin tulee sanoma **Asennetaanko tämä Power BI -sovellus?** , valitse **Asenna**. 

   ![Asenna Project Web](media/service-connect-to-project-online/ProjectTile.png)
5. Valitse **Sovellukset**-ruudusta **Microsoft Project Web App** -ruutu. 
   
   ![Microsoft Project Web App](media/service-connect-to-project-online/getstarted.png)
6. Valitse **Aloita uuden sovelluksesi käyttö** -kohdassa **Yhdistä tiedot**.
   
   ![tietoihin yhdistäminen](media/service-connect-to-project-online/mproject.png)
7. Kirjoita yhdistettävän Project Web Appin (PWA) URL-osoite **Project Web Appin URL-osoite** -tekstiruutuun.  Huomaa, että se poiketa esimerkistä, jos käytössäsi on mukautettu toimialue. Valitse **PWA-sivuston kieli** -tekstiruutu ja kirjoita numero, joka vastaa PWA-sivuston kieltä. Kirjoita numero ”1” englannille, ”2” ranskalle, ”3” saksalle, ”4” portugalille (Brasilia), ”5” portugalille (Portugali) ja ”6” espanjalle. 
   
   ![Yhdistä Microsoft Project Onlineen](media/service-connect-to-project-online/params.png)
8. Valitse todennusmenetelmäksi **oAuth2** \> **Kirjaudu sisään**. Anna pyydettäessä Project Web Appin tunnistetietosi ja noudata todennusprosessia.

    > [!NOTE]
    > Sinulla on oltava yhdistettävässä Project Web Appissa portfolion tarkastelijan, portfolion ylläpitäjän tai järjestelmänvalvojan oikeudet.

9. Näet ilmoituksen tietojesi lataamisesta. Lataaminen voi kestää jonkin aikaa tilin koosta riippuen. Kun Power BI on tuonut tiedot, näet uuden työtilasi sisällön. Saatat joutua päivittämään tietojoukon, jotta saat uusimmat päivitykset. 

    Kun Power BI on tuonut tiedot, näet siirtymisruudussa 13-sivuisen raportin ja tietojoukon. 

10. Kun raportit ovat valmiita, jatka eteenpäin ja aloita Project Web App -tietojesi tarkasteleminen! Mallisovelluksen mukana toimitetaan 13 monipuolista ja yksityiskohtaista raporttia salkun yleiskatsausta varten (6 raporttisivua), resurssin yleiskatsaus (5 raporttisivua) ja projektin tila (2 raporttisivua). 

    ![Portfolion koontinäyttö](media/service-connect-to-project-online/report1.png)
   
    ![Käytettävyys](media/service-connect-to-project-online/report3.png)
   
    ![Projektin tila](media/service-connect-to-project-online/report2.png)

**Mitä nyt?**

* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana.

**Laajenna mallisovellusta**

Lataa [GitHub PBIT -tiedosto](https://github.com/OfficeDev/Project-Power-BI-Content-Packs), jotta voit edelleen mukauttaa ja päivittää sisältöpakettia.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

