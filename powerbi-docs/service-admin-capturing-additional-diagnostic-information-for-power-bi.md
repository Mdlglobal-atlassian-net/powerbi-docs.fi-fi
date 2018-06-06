---
title: Vianmäärityksen lisätietojen kirjaaminen
description: Vianmäärityksen lisätietojen kirjaaminen
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 76860e740d43a1907692a7cd4fed1a6df68c93d4
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34239218"
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

