---
title: Yhteyden muodostaminen SendGridiin Power BI:lla
description: SendGrid Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: a0ae99e2dfad889840cc29ca4fa9f0f29397bf04
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2018
ms.locfileid: "37135371"
---
# <a name="connect-to-sendgrid-with-power-bi"></a>Yhteyden muodostaminen SendGridiin Power BI:lla
SendGrid Power BI -sisältöpaketin avulla voit poimia merkityksellisiä tietoja ja tilastoja SendGrid-tililtäsi. Käyttämällä SendGrid-sisältöpakettia voit visualisoida SendGrid-tilastoja koontinäytössä.

Muodosta yhteys [SendGrid-sisältöpakettiin](https://app.powerbi.com/getdata/services/sendgrid) Power BI:lle.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-sendgrid/pbi_getdata.png) 
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-sendgrid/pbi_getservices.png) 
3. Valitse **SendGrid**-sisältöpaketti ja sitten **Nouda**.
   
   ![](media/service-connect-to-sendgrid/sendgrid.png) 
4. Anna pyydettäessä SendGrid-käyttäjänimi ja salasana. Valitse **Kirjaudu sisään**.
   
   ![](media/service-connect-to-sendgrid/pbi_sendgridsignin.png)
5. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon, johon on täytetty sähköpostitilastot viimeisten 90 päivän ajalta. Uudet kohteet on merkitty keltaisella tähdellä \*.
   
   ![](media/service-connect-to-sendgrid/pbi_sendgriddash.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Seuraavat arvot ovat käytettävissä SendGrid-koontinäytössä:

* Yleisiä sähköpostitilastoja - pyynnöt, toimitetut, palautetut, roskaposti estetty, roskapostiraportit jne.
* Sähköpostitilastot luokan mukaan
* Sähköpostitilastot maantieteellisen sijainnin mukaan
* Sähköpostitilastot ISP:n mukaan
* Sähköpostitilastot laitteen, asiakkaan ja selaimen mukaan

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)

[Nouda tiedot](service-get-data.md)

