---
title: SQL Server Analysis Servicesin reaaliaikaiset tiedot Power BI:ssä
description: SQL Server Analysis Servicesin reaaliaikaiset tiedot Power BI:ssä Tämä toteutetaan yritysyhdyskäytävää varten määritetyn tietolähteen avulla.
services: powerbi
documentationcenter: ''
author: markingmyname
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
ms.date: 08/10/2017
ms.author: maghan
LocalizationGroup: Data from databases
ms.openlocfilehash: d9124479b429c15857199b20cb6ffe980478c126
ms.sourcegitcommit: 65426de556cd7207cbc4f478198664e25c33a769
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/30/2018
---
# <a name="sql-server-analysis-services-live-data-in-power-bi"></a>SQL Server Analysis Servicesin reaaliaikaiset tiedot Power BI:ssä
Power BI:ssä on käytössä kaksi tapaa muodostaa reaaliaikainen yhteys SQL Server Analysis Services -palvelimeen. **Nouda tiedot** -osassa voit muodostaa yhteyden joko suoraan SQL Server Analysis Services -palvelimeen tai vaihtoehtoisesti [Power BI Desktop -tiedostoon](service-desktop-files.md) tai [Excel-työkirjaan](service-excel-workbook-files.md), joka on jo yhteydessä Analysis Services -palvelimeen.

 >[!IMPORTANT]
 >* Jotta voit muodostaa reaaliaikaisen yhteyden Analysis Services -palvelimeen, järjestelmänvalvojan on asennettava ja määritettävä paikallinen tietoyhdyskäytävä. Lisätietoja on ohjeaiheessa [Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md).
 >* Paikallista yhdyskäytävää käytettäessä tiedot pysyvät paikallisina.  Näistä tiedoista luodut raportit tallennetaan Power BI -palveluun. 
 >* [Luonnollisella kielellä tehtävät kyselyt](service-q-and-a-direct-query.md) ovat reaaliaikaisissa Analysis Services -yhteyksissä käytettävissä esiversiona.

## <a name="to-connect-to-a-model-from-get-data"></a>Yhteyden muodostaminen Nouda tiedot -osan malliin
1. Valitse **Oma työtila** -osassa **Nouda tiedot**. Voit myös vaihtaa ryhmän työtilaan, jos sellainen on käytettävissä.
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdatabutton.png)
2. Valitse **Tietokannat ja muut**.
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_1.png)
3. Valitse **SQL Server Analysis Services**  >  **Yhdistä**. 
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_2.png)
4. Valitse palvelin. Jos et näe palvelinten luetteloa, yhdyskäytävää ja tietolähdettä ei ole määritetty tai tiliäsi ei ole listattu tietolähteen **Käyttäjät**-välilehdellä yhdyskäytävässä. Pyydä apua järjestelmänvalvojalta.
5. Valitse malli, johon haluat muodostaa yhteyden. Se voi olla joko taulukko- tai monidimensiomalli.

Yhteyden muodostamisen jälkeen malli näkyy Power BI -sivustosi kohdassa **Oma työtila -> Tietojoukot**. Jos olit vaihtanut ryhmän työtilaan, tietojoukko näkyy ryhmässä.

![](media/sql-server-analysis-services-tabular-data/connecttoas_dataset_5.png)

## <a name="dashboard-tiles"></a>Koontinäytön ruudut
Jos kiinnität visualisointeja raportista koontinäyttöön, kiinnitetyt ruudut päivitetään automaattisesti aina 10 minuutin välein. Jos paikallisen Analysis Services -palvelimen tiedot päivitetään, ruudut päivitetään automaattisesti 10 minuutin kuluttua.

## <a name="next-steps"></a>Seuraavat vaiheet
[Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)  
[Analysis Services -tietolähteiden hallinta](service-gateway-enterprise-manage-ssas.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

