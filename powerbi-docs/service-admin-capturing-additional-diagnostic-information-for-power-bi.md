---
title: Vianmäärityksen lisätietojen kirjaaminen
description: Vianmäärityksen lisätietojen kirjaaminen
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 9aef989b4b61ce8c9d11fd4275d68c867791f644
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/08/2018
ms.locfileid: "30977027"
---
# <a name="capturing-additional-diagnostic-information"></a>Vianmäärityksen lisätietojen kirjaaminen
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Power BI:n vianmäärityksen lisätietojen kirjaaminen
Nämä ohjeet tarjoavat kaksi mahdollista vaihtoehtoa lisädiagnostiikkatietojen keräämisen manuaalisesti Power BI-verkkoasiakkaasta.  Vain yhtä näistä vaihtoehdoista on noudatettava.

## <a name="network-capture---edge--internet-explorer"></a>Verkkosieppaus - Edge & Internet Explorer
1. Selaa [Power BI:a](https://app.powerbi.com) Edgellä tai Internet Explorerilla.
2. Avaa Edge-kehitystyökalut painamalla F12.
3. Se tuo näkyviin Kehitystyökalut-ikkunan: 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. Siirry verkko-välilehdelle. Se sisältää luettelon liikenteestä, joka on jo siepattu. 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. Voit selata ikkunassa ja jäljentää mahdollisia eteen tulevia ongelmia. Voit piilottaa ja näyttää Kehittäjän työkalut -ikkunan milloin tahansa istunnon aikana painamalla F12.
6. Voit pysäyttää sieppauksen valitsemalla punaisen neliön kehittäjien Kehittäjän työkalut-alueella Verkko-välilehdessä.
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. Valitse levykekuvake kohdasta **Export as HAR**
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. Anna tiedostonimi ja tallenna HAR-tiedosto.
   
    HAR-tiedosto sisältää kaikki tiedot verkkopyynnöistä selainikkunan ja Power BI:n välillä.  Tämä sisältää aktiivisuustunnukset kullekin pyynnölle, aikaleiman kullekin pyynnölle ja asiakkaalle palautetut virhetiedot.  Tämä jäljitys sisältää myös tiedot,  joita käytetään täyttämään näytössä näkyviä visualisointeja.
9. Voit hankkia HAR-tiedoston tukemaan tarkastelua.

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

