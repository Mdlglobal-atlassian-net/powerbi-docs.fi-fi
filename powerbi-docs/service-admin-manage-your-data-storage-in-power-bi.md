---
title: Tietoja tallennustilan hallinta
description: Lue, miten voit hallita yksittäisten tai sovelluksen työtilan tallennustilaa ja varmistaa, että voit edelleen julkaista raportteja ja tietojoukkoja.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: maggies
LocalizationGroup: Administration
ms.openlocfilehash: 864d50d8850a8ceed964f128cea71b0daf5d8322
ms.sourcegitcommit: ac63e6a082ca8397909217837e8d98c9389b23ac
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/01/2018
ms.locfileid: "50736868"
---
# <a name="manage-your-data-storage"></a>Tietoja tallennustilan hallinta
Lue, miten voit hallita yksittäisten tai sovelluksen työtilan tallennustilaa ja varmistaa, että voit edelleen julkaista raportteja ja tietojoukkoja.

Käyttäjillä ja sovelluksen työtiloilla on omat datakapasiteettinsa

* Kaikilla käyttäjillä on enintään 10 gigatavua tallennustilaa.
* Käyttäjät, joilla on Power BI Pro -käyttöoikeus, voivat luoda sovelluksen työtiloja, joissa kussakin on enintään 10 gigatavua tallennustilaa.

Vuokraajan tasolla kokonaiskäyttö voi olla enintään 10 gigatavua Pro-käyttäjää kohden kaikkien Pro-käyttäjien osalta ja vuokraajan sovelluksen työtiloissa.

Lue lisätietoja muista ominaisuuksista [Power BI -hinnoittelumallista](https://powerbi.microsoft.com/pricing).

Tietoja tallennustila sisältää omat tietojoukkosi sekä Excel-raportit sekä tiedot, joita joku on sinulle luovuttanut. Tietojoukot ovat mitä tahansa tietolähteitä, jotka olet ladannut tai joihin olet yhteydessä, mukaan lukien Power BI Desktop -tiedostot ja Excel-työkirjat, joita käytät. Seuraavat sisältyvät myös datakapasiteettiin.

* Excel-alueet, jotka on kiinnitetty raporttinäkymään.
* Reporting Servicesin paikalliset visualisoinnit, jotka on kiinnitetty Power BI -raporttinäkymään.
* Ladatut kuvat.

Jakamasi raporttinäkymän koko vaihtelee sen mukaan, mitä siihen on kiinnitetty. Jos kiinnität kaksi raporttia, jotka ovat osa kahta eri tietojoukkoa, kokoon sisältyvät molemmat tietojoukot.

<a name="manage"/>

## <a name="manage-items-owned-by-you"></a>Omistamiesi kohteiden hallinta
Katso, miten paljon tallennustilaa käytät Power BI -tililläsi ja hallitse tiliäsi.

1. Siirry oman tallennustilan hallintaa varten kohtaan **My Workspace** vasemmassa siirtymisruudussa.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)
2. Valitse hammaspyöräkuvake ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) oikeasta yläkulmasta ja kohta \> **Henkilökohtaisen tallennustilan hallinta**.
   
    Yläpalkki näyttää kuinka paljon tallennustilaa olet käyttänyt.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    Tietojoukot ja raportit erotetaan kahdeksi välilehdeksi:
   
    **Omistamani:** nämä ovat raportteja ja tietojoukkoja, jotka olet ladannut Power BI -tilillesi, mukaan lukien palvelun tietojoukot, kuten Salesforce ja Dynamics CRM.  
    **Muiden omistamat:** muiden sinulle jakamat raportit ja tietojoukot.
3. Jos haluat poistaa raportin tai tietojoukon, valitse roskakorikuvake ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).

Pidä mielessä, että sinulla tai jollain muulla voi olla raportteja ja raporttinäkymiä tietojoukon perusteella. Jos poistat tietojoukon, kyseiset raportit ja raporttinäkymät eivät enää toimi.

## <a name="manage-your-app-workspace"></a>Sovelluksen työtilan hallinta
1. Valitse **Työtilojen** \> vieressä olevalla nuolella sovelluksen työtilan nimi.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. Valitse hammaspyöräkuvake ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) oikeasta yläkulmasta ja kohta \> **Ryhmän tallennustilan hallinta**.
   
    Yläpalkki näyttää kuinka paljon tallennustilaa ryhmän tallennustilasta on käytetty.
   
    ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    Tietojoukot ja raportit erotetaan kahdeksi välilehdeksi:
   
    **Meidän omistamamme:** nämä ovat raportteja ja tietojoukkoja, jotka joku muu on ladannut ryhmän Power BI -tilille, mukaan lukien palvelun tietojoukot, kuten Salesforce ja Dynamics CRM.
    **Muiden omistamat:** muiden sinulle jakamat raportit ja tietojoukot ryhmässäsi.
3. Jos haluat poistaa raportin tai tietojoukon, valitse roskakorikuvake ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).
   
   > [!NOTE]
   > Kuka tahansa sovelluksen työtilan jäsenellä, jolla on muokkausoikeudet, on oikeus poistaa tietojoukkoja ja raportteja sovelluksen työtilasta.
   > 
   > 

Pidä mielessä, että sinulla tai jollain muulla ryhmässä voi olla raportteja ja raporttinäkymiä tietojoukon perusteella. Jos poistat tietojoukon, kyseiset raportit ja raporttinäkymät eivät enää toimi.

## <a name="dataset-limits"></a>Tietojoukon rajoitukset
Rajoitus on 1 gigatavu tietojoukkoa kohden, joka on tuotu Power BI:lle. Jos olet valinnut Excel-toiminnon tietojen tuomisen sijaan, tietojoukkokohtainen raja on 250 Mt.

## <a name="what-happens-when-you-hit-a-limit"></a>Mitä tapahtuu, kun raja saavutetaan?
Kun saavutat tietojen kapasiteetin rajan, näkyviin tulee ohjeita palvelun sisällä. 

Kun valitset hammaspyöräkuvakkeen ![](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png), näkyviin tulee punainen palkki, joka ilmaisee, että tietoja kapasiteettiraja on ylittynyt.

![](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

Näet myös tämän kohdassa **Henkilökohtaisen tallennustilan hallinta**.

 ![](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 Kun yrität suorittaa toimintoa, jota jokin rajoituksista koskee, näkyviin tulee kehote, joka ilmaisee, että raja on ylitetty. Voit [hallita](#manage) tallennustilaasi ja pienentää tallennustilan koko rajan ohittamiseksi.

 ![](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

