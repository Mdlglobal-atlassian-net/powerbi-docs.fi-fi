---
title: Vianmäärityksen lisätietojen kirjaaminen
description: Vianmäärityksen lisätietojen kirjaaminen
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: b38e1e73b9829b4b86237f826b4245a6b95cfa36
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54292932"
---
# <a name="capturing-additional-diagnostic-information"></a>Vianmäärityksen lisätietojen kirjaaminen
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Power BI:n vianmäärityksen lisätietojen kirjaaminen
Nämä ohjeet tarjoavat kaksi mahdollista vaihtoehtoa lisädiagnostiikkatietojen keräämisen manuaalisesti Power BI-verkkoasiakkaasta.  Vain yhtä näistä vaihtoehdoista on noudatettava.

## <a name="network-capture---edge--internet-explorer"></a>Verkkosieppaus - Edge & Internet Explorer
1. Selaa [Power BI:a](https://app.powerbi.com) Edgellä tai Internet Explorerilla.
2. Avaa Edge-kehitystyökalut painamalla F12.
3. Se tuo näkyviin Kehitystyökalut-ikkunan: 
   
   ![Kehitystyökalut](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. Siirry verkko-välilehdelle. Se sisältää luettelon liikenteestä, joka on jo siepattu. 
   
   ![Edgen Verkko-välilehti](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. Voit selata ikkunassa ja jäljentää mahdollisia eteen tulevia ongelmia. Voit piilottaa ja näyttää Kehittäjän työkalut -ikkunan milloin tahansa istunnon aikana painamalla F12.
6. Voit pysäyttää sieppauksen valitsemalla punaisen neliön kehittäjien Kehittäjän työkalut-alueella Verkko-välilehdessä.
   
   ![Pysäytä sieppaus](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. Valitse levykekuvake kohdasta **Export as HAR**
   
   ![Vie tiedosto](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. Anna tiedostonimi ja tallenna HAR-tiedosto.
   
    HAR-tiedosto sisältää kaikki tiedot verkkopyynnöistä selainikkunan ja Power BI:n välillä.  Tämä sisältää aktiivisuustunnukset kullekin pyynnölle, aikaleiman kullekin pyynnölle ja asiakkaalle palautetut virhetiedot.  Tämä jäljitys sisältää myös tiedot,  joita käytetään täyttämään näytössä näkyviä visualisointeja.
9. Voit hankkia HAR-tiedoston tukemaan tarkastelua.

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

