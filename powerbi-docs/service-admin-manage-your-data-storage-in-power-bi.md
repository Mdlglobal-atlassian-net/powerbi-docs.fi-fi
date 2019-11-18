---
title: Tallennustilan hallinta työtiloissa
description: Lue, miten voit hallita yksittäisten tai työtilan tallennustilaa ja varmistaa, että voit edelleen julkaista raportteja ja tietojoukkoja.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2018
ms.author: maggies
LocalizationGroup: Administration
ms.openlocfilehash: ea187de55eec2667abe2eed017481180910b7619
ms.sourcegitcommit: 8cc2b7510aae76c0334df6f495752e143a5851c4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/01/2019
ms.locfileid: "73431377"
---
# <a name="manage-data-storage-in-power-bi-workspaces"></a>Tallennustilan hallinta Power BI -työtiloissa

Lue, miten voit hallita yksittäisten tai työtilan tallennustilaa ja varmistaa, että voit edelleen julkaista raportteja ja tietojoukkoja.

Käyttäjillä ja työtiloilla on omat tietokapasiteettinsa:

* Kaikilla käyttäjillä on enintään 10 gigatavua tietojen tallennustilaa.
* Käyttäjät, joilla on Power BI Pro -käyttöoikeus, voivat luoda työtiloja, joissa kussakin on enintään 10 gigatavua tietojen tallennustilaa.
* Työtilan Premium-kapasiteettia ei lasketa mukaan Power BI Pro -käyttäjän tallennustilaan.

Vuokraajan tasolla kokonaiskäyttö voi olla enintään 10 gigatavua Pro-käyttäjää kohden kaikkien Pro-käyttäjien osalta ja vuokraajan työtiloissa.

Lue lisätietoja muista ominaisuuksista [Power BI -hinnoittelumallista](https://powerbi.microsoft.com/pricing).

Tietojen tallennustila sisältää omat tietojoukkosi ja Excel-raportit sekä tiedot, jotka joku toinen on jakanut kanssasi. Tietojoukot ovat mitä tahansa tietolähteitä, jotka olet ladannut tai joihin olet muodostanut yhteyden. Nämä tietolähteet sisältävät Power BI Desktop -tiedostot ja Excel-työkirjat, joita käytät. Seuraavat sisältyvät myös datakapasiteettiin.

* Excel-alueet, jotka on kiinnitetty raporttinäkymään.
* Reporting Servicesin paikalliset visualisoinnit, jotka on kiinnitetty Power BI -raporttinäkymään.
* Ladatut kuvat.

Jakamasi koontinäytön koko vaihtelee sen mukaan, mitä siihen on kiinnitetty. Jos esimerkiksi kiinnität kohteita kahdesta raportista, jotka ovat osa kahta eri tietojoukkoa, kokoon sisältyvät molemmat tietojoukot.

<a name="manage"/>

## <a name="manage-items-you-own"></a>Omistamiesi kohteiden hallinta

Katso, miten paljon tallennustilaa käytät Power BI -tililläsi ja hallitse tiliäsi.

1. Siirry oman tallennustilan hallintaa varten kohtaan **My Workspace** vasemmassa siirtymisruudussa.
   
    ![Oma työtila](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)
2. Valitse rataskuvake ![rataskuvake](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) oikeasta yläkulmasta \> **Henkilökohtaisen tallennustilan hallinta**.
   
    Yläpalkki näyttää kuinka paljon tallennustilaa olet käyttänyt.
   
    ![Tallennustilan rajan hallinta](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    Tietojoukot ja raportit erotetaan kahdeksi välilehdeksi:
   
    **Omistamani:** Nämä ovat raportteja ja tietojoukkoja, jotka olet ladannut Power BI -tilillesi, mukaan lukien palvelun tietojoukot, kuten Salesforce ja Dynamics CRM.  
    **Muiden omistamat:** Muiden sinulle jakamat raportit ja tietojoukot.
1. Jos haluat poistaa tietojoukon tai raportin, valitse roskakorikuvake ![roskakorikuvake](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).

Pidä mielessä, että sinulla tai jollain muulla voi olla raportteja ja raporttinäkymiä tietojoukon perusteella. Jos poistat tietojoukon, kyseiset raportit ja raporttinäkymät eivät enää toimi.

## <a name="manage-your-workspace"></a>Työtilan hallinta
1. Valitse **Työtilojen** \> vieressä olevalla nuolella työtilan nimi.
   
    ![Valitse työtila](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. Valitse rataskuvake ![rataskuvake](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) oikeasta yläkulmasta \> **Ryhmän tallennustilan hallinta**.
   
    Yläpalkki näyttää kuinka paljon tallennustilaa ryhmän tallennustilasta on käytetty.
   
    ![Työtilan tallennustilan hallinta](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    Tietojoukot ja raportit erotetaan kahdeksi välilehdeksi:
   
    **Meidän omistamamme:** Nämä ovat raportteja ja tietojoukkoja, jotka sinä olet ladannut tai joku muu on ladannut ryhmän Power BI -tilille, mukaan lukien palvelun tietojoukot, kuten Salesforce ja Dynamics CRM.
    **Muiden omistamat:** Muiden ryhmälle jakamat raportit ja tietojoukot.
3. Jos haluat poistaa tietojoukon tai raportin, valitse roskakorikuvake ![roskakorikuvake](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).
   
   > [!NOTE]
   > Kenellä tahansa työtilan jäsenellä, jolla on muokkausoikeudet, on oikeus poistaa tietojoukkoja ja raportteja työtilasta.
   > 
   > 

Pidä mielessä, että sinulla tai jollain muulla ryhmässä voi olla raportteja ja raporttinäkymiä tietojoukon perusteella. Jos poistat tietojoukon, kyseiset raportit ja raporttinäkymät eivät enää toimi.

## <a name="dataset-limits"></a>Tietojoukon rajoitukset
Rajoitus on 1 gigatavu tietojoukkoa kohden, joka on tuotu Power BI:lle. Jos olet valinnut Excel-kokemuksen säilyttämisen tietojen tuomisen sijaan, tietojoukkokohtainen raja on 250 Mt.

## <a name="what-happens-when-you-reach-a-limit"></a>Mitä tapahtuu, kun raja saavutetaan?
Kun saavutat tietojen kapasiteetin rajan, näkyviin tulee ohjeita palvelun sisällä. 

Kun valitset rataskuvakkeen ![rataskuvake](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png), näkyviin tulee punainen palkki, joka ilmaisee, että tietojen kapasiteettiraja on ylittynyt.

![Tallennustilan raja saavutettu](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

Tämä raja on myös ilmoitettu kohdassa **Henkilökohtaisen tallennustilan hallinta**.

 ![Hallitse henkilökohtaista tallennustilaa, tallennustilan raja saavutettu](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 Kun yrität suorittaa toimintoa, joka saavuttaa yhden rajoista, näet viestin, jonka mukaan raja on ylitetty. Voit [hallita](#manage) tallennustilaasi tallennusmäärän pienentämiseksi ja rajan ohittamiseksi.

 ![Tallennustilarajoituksesi on ylittynyt](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

