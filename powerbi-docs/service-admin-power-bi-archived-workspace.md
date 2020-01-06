---
title: Power BI:n arkistoitu työtila
description: Power BI arkistoitu työtila Office 365 -vuokraajan hallinnan jälkeen
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/18/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 403bf213cc2da7ad803780946e606433166e3484
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "74699954"
---
# <a name="power-bi-archived-workspace"></a>Power BI:n arkistoitu työtila

> [!IMPORTANT]
> Power BI ei enää tue Arkistoitu työtila -ominaisuutta, joka poistetaan käytöstä vuoden 2019 lopussa. Jos käytät arkistoitua työtilaa, sinun tulee heti luoda uudelleen sisältö, jonka haluat säilyttää, uudessa työtilassa nykyisessä vuokraajassasi. Et voi luottaa siihen, että arkistoitu työtila on edelleen käytettävissä. Power BI ei enää tue siihen liittyvää ominaisuutta [Azure AD -vuokraajan ulkoista haltuunottoa](service-admin-faq.md#what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users).

Power BI:n avulla kuka tahansa voi rekisteröityä ja aloittaa palvelun käytön muutamassa minuutissa.  Myöhemmin organisaatiosi IT-osasto voi halutessaan ottaa haltuun Power BI:n hallinnan organisaation käyttäjille.  Jos näin tapahtuu, etuna on käyttäjien ja käyttöoikeuksien keskitetty hallinta organisaatiossasi. Saatat myös pystyä hyödyntämään virtaviivaistettua sisäänkirjautumista samalla käyttäjänimellä ja salasanalla, joita käytät organisaation muissakin palveluissa.

Sisältö, jonka loit ennen kuin IT-osastosi aloitti Power BI:n hallinnan, sijoitetaan Power BI:n arkistoituun työtilaan, joka on käytettävissä [Power BI:n](https://app.powerbi.com) siirtymisruudussa. Sinun kannattaa aloittaa luomaan uutta Power BI -sisältöä omassa työtilassa, jota organisaation IT-osasto suojaa ja hallitsee.  Arkistoitu työtila on edelleen olemassa, mutta käytössä on rajoituksia arkistoidun työtilan sisältöön tehtävissä toiminnoissa.  Jos haluat poistaa nämä rajoitukset, sinun on siirrettävä sisältö arkistoidusta työtilasta omaan työtilaasi, jota IT-osastosi hallitsee.

## <a name="restrictions-in-your-archived-workspace"></a>Arkistoidun työtilan rajoitukset

Power BI ei poista sisältöä arkistoidusta työtilasta. Voit jatkaa tietojen hankkimista, raporttien ja koontinäyttöjen luomista ja tietojoukkojen päivittämistä. Nykyiset käyttäjät, joiden kanssa olet jakanut sisältöä, voivat myös edelleen tarkastella sisältöä arkistoidussa työtilassa. Arkistoidun työtilan sisältöön on kuitenkin joitakin rajoituksia:

* **OneDrive for Business**: Et enää saa tietoja tai päivityksiä OneDrive for Businessistä arkistoidun työtilan tietojoukoille.  Jos yrität muodostaa yhteyden tähän lähteeseen, näyttöön tulee varoitus.

* **Raporttinäkymien jakaminen**: Et voi jakaa raporttinäkymiä muiden käyttäjien kanssa arkistoidusta työtilasta.  Käyttäjät, joilla on jo käyttöoikeus, voivat edelleen tarkastella jaettuja koontinäyttöjä arkistoidussa työtilassaan.

* **Ryhmien luominen**: Et voi luoda ryhmiä arkistoidussa työtilassa.

* **Power BI -mobiilisovellusten käyttäminen**: Vaikka voit yhä tarkastella sisältöä verkossa arkistoidussa työtilassa, tämä sisältö ei enää näy Power BI -mobiilisovelluksissa.

## <a name="migrating-content-in-your-archived-workspace"></a>Sisällön siirtäminen arkistoidussa työtilassa

Jotta voit jatkaa Power BI:n käyttämistä, sinun on luotava uutta sisältöä omaan työtilassasi. Sinun on myös siirrettävä arkistoidun työtilan sisältö omaan työtilaan.  Sisällön siirtämistapa riippuu sisällön tyypistä:

* **Excel- tai Power BI Desktop -tietojoukot**: Siirrä nämä tietojoukot vaihtamalla arkistoidusta työtilasta omaan työtilaan ja lataamalla uudelleen Excel- tai Power BI Desktop -tiedosto napsauttamalla **Omat tiedot** -painiketta.  Jos olet määrittänyt ajoitetun päivityksen, sinun on määritettävä nämä asetukset uudelleen uudelle tietojoukolle omassa työtilassa.

* **Muut tietojoukot**: Vaihda omaan työtilaan ja valitse sitten **Nouda tiedot** -painike muodostaaksesi yhteyden muihin tietojoukkoihin, jotka olet luonut arkistoidussa työtilassa.  Voit joutua antamaan suojaus- tai yhdistämistiedot uudelleen.

* **Raportit**: Excel- tai Power BI Desktop -tiedostoihin sisältyvät raportit luodaan automaattisesti uudelleen, kun lataat vastaavan Excel- tai Power BI Desktop -tiedoston uudelleen. Sisältöpaketin osana asennetut raportit luodaan myös uudelleen, kun muodostat yhteyden sisältöpakettiin. Jos olet luonut omia raportteja Power BI -palvelun kautta, sinun on luotava kyseiset raportit uudelleen omassa työtilassa.

* **Raporttinäkymät**: Sisältöpakettien osana asennetut raporttinäkymät luodaan automaattisesti uudelleen, kun yhdistät uudelleen sisältöpakettiin omassa työtilassa. Jos olet luonut omia koontinäyttöjä Power BI -palvelun kautta, sinun on luotava kyseiset koontinäytöt uudelleen omassa työtilassa.

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

