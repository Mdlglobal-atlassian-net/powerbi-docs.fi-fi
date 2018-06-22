---
title: Yhteyden muodostaminen SparkPostiin Power BI:llä
description: Power BI:n SparkPost
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6f914a031c70c68703116083f42885e2fe79cf30
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34247891"
---
# <a name="connect-to-sparkpost-with-power-bi"></a>Yhteyden muodostaminen SparkPostiin Power BI:llä
Power BI:n SparkPost-sisältöpaketilla voit poimia arvokkaita tietojoukkoja SparkPost-tililtäsi ja yhdistää ne samaan hyödylliseen ja havainnolliseen koontinäyttöön. SparkPost-sisältöpaketin avulla voit visualisoida sähköpostitilastoja, kuten toimialueita, kampanjoita ja osallistamista Internet-palveluntarjoajan mukaan.

Muodosta yhteys [Power BI:n SparkPost-sisältöpakettiin](https://app.powerbi.com/getdata/services/spark-post).

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-sparkpost/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-sparkpost/services.png)
3. Valitse **SparkPost**-sisältöpaketti ja sitten **Nouda**. 
   
   ![](media/service-connect-to-sparkpost/sparkpost.png)
4. Anna pyydettäessä SparkPost-ohjelmointirajapinta-avain ja valitse Kirjaudu sisään. Lisätietoja [tämän parametrin etsimisestä](#FindingParams) on alla.
   
   ![](media/service-connect-to-sparkpost/creds.png)
5. Tietojen lataaminen alkaa pian. Siinä voi kestää jonkin aikaa tilin koosta riippuen. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa oletusarvoisen koontinäytön, raportin ja tietojoukon, johon on täytetty sähköpostitilastot viimeisten 90 päivän ajalta. Uudet kohteet on merkitty keltaisella tähdellä \*.
   
   ![](media/service-connect-to-sparkpost/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajoitettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana.

## <a name="whats-included"></a>Paketin sisältö
Power BI:n SparkPost-sisältöpakettiin sisältyy tietoja muun muassa yksilöllisistä napsautuksista sekä hyväksymis-, epäonnistumis-, viivästymis- ja hylkäämisasteista.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien etsiminen
Sisältöpaketti yhdistää SparkPost-tilin Power BI:hin käyttämällä ohjelmointirajapinta-avainta. Löydät ohjelmointirajapinta-avaimesi tilisi tiedoista kohdassa Tili \> Ohjelmointirajapinta ja SMTP (lisätietoja on [täällä](https://support.sparkpost.com/customer/portal/articles/1933377-create-api-keys)). Suosittelemme, että käytät ohjelmointirajapinta-avainta, jolla on käyttöoikeudet kohteisiin `Message Events: Read-only ` ja `Metrics: Read-only`.

![](media/service-connect-to-sparkpost/sparkpost1.png)

