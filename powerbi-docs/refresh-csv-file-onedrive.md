---
title: OneDriven .csv-tiedostosta luodun tietojoukon päivittäminen
description: OneDriven .csv-tiedostosta luodun tietojoukon päivittäminen
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: 42f5353c49d562f4fefeec81867fd9e9ff4831c2
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34239021"
---
# <a name="refresh-a-dataset-created-from-a-csv-file-on-onedrive-or-sharepoint-online"></a>OneDriven .csv-tiedostosta tai SharePoint Onlinesta luodun tietojoukon päivittäminen
## <a name="what-are-the-advantages"></a>Mitkä ovat edut?
Kun muodostat yhteyden OneDriven .csv-tiedostoon tai SharePoint Onlineen, Power BI:ssa luodaan tietojoukko. Tämän jälkeen .csv-tiedosto tuodaan Power BI -tietojoukkoon. Power BI muodostaa sitten automaattisesti yhteyden tiedostoon ja päivittää mahdolliset muutokset Power BI:n tietojoukossa. Jos haluat muokata .csv-tiedostoa Onedrivessa tai SharePoint Onlinessa, kerran niitä tallennetaan, muutokset näkyvät Power BI:ssa yleensä noin tunnin kuluessa. Tietojoukkoon perustuvat Power BI:n kaikki visualisoinnit päivittyvät myös automaattisesti.

Jos tiedostot ovat OneDrive for Business- tai SharePoint Onlinen jaetussa kansiossa, muut käyttäjät voivat työstää samaa tiedostoa. Kun muutokset on tallennettu, tehdyt muutokset päivitetään automaattisesti Power BI -palveluun yleensä tunnin kuluessa.

Monet organisaatiot suorittavat prosesseja, jotka kyselevät automaattisesti tietokannoista tietoja, jotka sitten tallennetaan .csv-tiedostoon päivittäin. Jos tiedosto on tallennettu OneDriveeen tai SharePoint Onlineen ja sama tiedoston korvataan joka päivä sen sijaan, etä luotaisiin uusi tiedosto kunakin päivänä eri nimellä, voit muodostaa yhteyden tähän tiedostoon Power BI:ssä. Tietojoukkosi, joka muodostaa yhteyden tiedostoon, synkronoidaan pian sen jälkeen, kun tiedosto on päivitetty Onedriveen tai SharePoint Onlineen. Tietojoukkoon perustuvat kaikki visualisoinnit päivittyvät myös automaattisesti.

## <a name="whats-supported"></a>Tuetut toiminnot:
Pilkuilla erotetut arvotiedostot ovat yksinkertaisia tekstitiedostoja, joten yhteyksiä ulkoisiin tietolähteisiin ja raportteihin ei tueta. Et voi ajoittaa pilkulla erotetusta tiedostosta luodun tietojoukon päivitystä. Kun tiedosto on OneDrivessa tai SharePoint Onlinessa, Power BI synkronoi tietojoukon sisältämän tiedoston muutokset automaattisesti noin tunnin välein.

## <a name="onedrive-or-onedrive-for-business-whats-the-difference"></a>OneDrive tai OneDrive for Business? Mikä niiden ero on?
Jos sinulla on sekä henkilökohtainen OneDrive että OneDrive for Business, on suositeltavaa säilyttää tiedostot, jotka haluat yhdistää BI:ssa OneDrive for Business -palveluun. Syynä on se, että todennäköisesti käytät kahta eri tiliä niille kirjautumista varten.

Yhteyden muodostaminen OneDrive for Business -palveluun Power BI:ssa on yleensä saumaton, koska tili, jota käytit Power BI -kirjautumiseen on usein sama tili, jota käytetään kirjauduttaessa OneDrive for Business -palveluun. Henkilökohtaisen OneDrive olet todennäköisesti kuitenkin kirjautunut sisään toisella [Microsoft-tilillä](http://www.microsoft.com/account/default.aspx).

Kun olet kirjautunut sisään Microsoft-tilillesi, muista valita Pysy kirjautuneena -vaihtoehto. Power BI voi sitten synkronoida kaikki päivitykset Power BI:n tietojoukkoihin

![](media/refresh-csv-file-onedrive/refresh_signin_keepmesignedin.png)

Jos teet muutoksia OneDrive .csv-tiedostoon, joita ei voi synkronoida tietojoukkoon Power BI:ssa, koska Microsoft-tilisi tunnistetiedot ovat ehkä muuttuneet, sinun pitää muodostaa yhteys tiedostoon ja tuoda se takaisin omasta OneDrivesta.

## <a name="when-things-go-wrong"></a>Jos ilmenee ongelmia
Jos .csv-tiedoston tiedot OneDrivessa muuttuvat eivätkä kyseiset muutokset heijastu Power BI -palveluun, se johtuu siitä todennäköisimmin siitä, ettei Power BI pysty yhdistämään OneDriveesi. Yritä muodostaa yhteys tiedostoon ja tuoda se uudelleen. Jos sinua pyydetään kirjautumaan sisään, varmista, että valitset vaihtoehdon **Pysy kirjautuneena**.

## <a name="next-steps"></a>Seuraavat vaiheet
[Työkalut päivitysongelmien vianmääritysohjeita varten](service-gateway-onprem-tshoot.md)
[Päivityksiä koskeva vianmääritys](refresh-troubleshooting-refresh-scenarios.md)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
