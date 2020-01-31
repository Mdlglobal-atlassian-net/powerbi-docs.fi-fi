---
title: Power BI Desktopista julkaiseminen
description: Power BI Desktopista julkaiseminen
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 3a67c36b2594696e1c576693cc5808eb0227c1c7
ms.sourcegitcommit: a1409030a1616027b138128695b80f6843258168
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/24/2020
ms.locfileid: "76709629"
---
# <a name="publish-datasets-and-reports-from-power-bi-desktop"></a>Tietojoukkojen ja raporttien julkaiseminen Power BI Desktopista
Kun julkaiset Power BI Desktop -tiedoston Power BI -palvelussa, mallin tiedot julkaistaan Power BI:n työtilassasi. Sama koskee mahdollisia raportteja, jotka luot **Raportti**-näkymässä. Näet uuden tietojoukon samalla nimellä ja mahdolliset raportit Työtila-siirtymistoiminnossa.

Julkaiseminen Power BI Desktopista vaikuttaa samalla tavalla kuin **Nouda tiedot** -toiminnon käyttäminen Power BI:ssä yhdistämiseksi Power BI Desktop -tiedostoon ja sen lataamiseksi palvelimelle.

> [!NOTE]
> Power BI -raporttiin tekemiäsi muutoksia ei tallenneta alkuperäiseen Power BI Desktop -tiedostoon. Näin tapahtuu myös silloin, kun lisäät, poistat tai muutat visualisointeja raporteissa.
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>Power BI Desktop -tietojoukon ja -raporttien julkaiseminen
1. Valitse Power BI Desktopissa **Tiedosto** \> **Julkaise** \> **Julkaise Power BI:ssä** tai valitse valintanauhassa **Julkaise**.  

   ![Julkaise-painike](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)

2. Kirjaudu sisään Power BI:hin.
3. Valitse kohde.

   ![Julkaisukohteen valitseminen](media/desktop-upload-desktop-files/pbid_publish_select_destination.png)

Kun julkaiseminen on valmis, saat linkin raporttiin. Valitse linkki raportin avaamiseksi Power BI -sivustossasi.

![Julkaiseminen onnistui -valintaikkuna](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="republish-or-replace-a-dataset-published-from-power-bi-desktop"></a>Power BI Desktopista julkaistun tietojoukon julkaiseminen uudelleen tai korvaaminen
Power BI Desktopissa luomasi tietojoukko ja mahdolliset raportit ladataan Power BI -sivustoosi, kun julkaiset Power BI Desktop -tiedoston. Kun julkaiset Power BI Desktop -tiedoston uudelleen, Power BI -sivustossasi oleva tietojoukko korvataan Power BI Desktop -tiedoston päivitetyllä tietojoukolla.

Tämä prosessi on yksinkertainen, mutta seuraavat seikat kannattaa ottaa huomioon:

* Jos Power BI:ssä on jo vähintään kaksi tietojoukkoa Power BI Desktop -tiedoston kanssa samalla nimellä, julkaiseminen voi epäonnistua. Varmista, että Power BI:ssä on ainoastaan yksi tietojoukko samalla nimellä. Voit myös nimetä tiedoston uudelleen ja julkaista, jolloin luodaan uusi tietojoukko, jolla on sama nimi kuin tiedostolla.
* Jos nimeät uudelleen tai poistat sarakkeen tai mittarin, kaikki Power BI:ssä jo olevat visualisoinnit kyseisellä kentällä voivat rikkoutua. 
* Power BI ohittaa tietyt olemassa olevien sarakkeiden muotoilumuutokset. Jos esimerkiksi muutat sarakkeen muodon 0,25 %:sta 25 %:iin.
* Oletetaan, että sinulla on päivitysaikataulu, joka on määritetty aiemmin luodulle tietojoukolle Power BI:ssä. Kun lisäät uusia tietolähteitä tiedostoon ja julkaiset sitten uudelleen, sinun on kirjauduttava niihin ennen seuraavaa ajoitettua päivitystä.
* Kun julkaiset uudelleen Power BI Desktopissa julkaistun tietojoukon ja päivitysaikataulu on määritetty, tietojoukon päivitys alkaa heti uudelleenjulkaisun jälkeen. 

