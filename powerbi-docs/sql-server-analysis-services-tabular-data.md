---
title: SQL Server Analysis Servicesin reaaliaikaiset tiedot Power BI:ssä
description: SQL Server Analysis Servicesin reaaliaikaiset tiedot Power BI:ssä Tämä toteutetaan yritysyhdyskäytävää varten määritetyn tietolähteen avulla.
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: Minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 08/10/2017
LocalizationGroup: Data from databases
ms.openlocfilehash: 51efec6c78dbb29b9c3dc760284c7bb3c8711bdc
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "64769920"
---
# <a name="sql-server-analysis-services-live-data-in-power-bi"></a>SQL Server Analysis Servicesin reaaliaikaiset tiedot Power BI:ssä

Power BI:ssä on käytössä kaksi tapaa muodostaa reaaliaikainen yhteys SQL Server Analysis Services -palvelimeen. **Nouda tiedot** -osassa voit muodostaa yhteyden joko suoraan SQL Server Analysis Services -palvelimeen tai vaihtoehtoisesti [Power BI Desktop -tiedostoon](service-desktop-files.md) tai [Excel-työkirjaan](service-excel-workbook-files.md), joka on jo yhteydessä Analysis Services -palvelimeen. Parhaana käytäntönä Microsoft suosittelee käyttämään Power BI Desktopia, sillä siinä on hyvä työkaluvalikoima ja mahdollisuus ylläpitää Power BI Desktop -tiedoston paikallista varmuuskopiota.

>[!IMPORTANT]
> * Jotta voit muodostaa reaaliaikaisen yhteyden Analysis Services -palvelimeen, järjestelmänvalvojan on asennettava ja määritettävä paikallinen tietoyhdyskäytävä. Lisätietoja on ohjeaiheessa [Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md).
> * Paikallista yhdyskäytävää käytettäessä tiedot pysyvät paikallisina.  Näistä tiedoista luodut raportit tallennetaan Power BI -palveluun. 
> * [Luonnollisella kielellä tehtävät kyselyt](service-q-and-a-direct-query.md) ovat reaaliaikaisissa Analysis Services -yhteyksissä käytettävissä esiversiona.

## <a name="to-connect-to-a-model-from-get-data"></a>Yhteyden muodostaminen Nouda tiedot -osan malliin

1. Valitse **Oma työtila** -osassa **Nouda tiedot**. Voit myös vaihtaa ryhmän työtilaan, jos sellainen on käytettävissä.

   ![Yhteyden muodostaminen Nouda tiedot-painike](media/sql-server-analysis-services-tabular-data/connecttoas_getdatabutton.png)

2. Valitse **Tietokannat ja muut**.

   ![Yhteyden muodostaminen Nouda tiedot 1](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_1.png)

3. Valitse **SQL Server Analysis Services**  >  **Yhdistä**.

   ![Yhteyden muodostaminen Nouda tiedot 2](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_2.png)

4. Valitse palvelin. Jos et näe palvelinten luetteloa, yhdyskäytävää ja tietolähdettä ei ole määritetty tai tiliäsi ei ole listattu tietolähteen **Käyttäjät**-välilehdellä yhdyskäytävässä. Tarkista asia järjestelmänvalvojalta.

5. Valitse malli, johon haluat muodostaa yhteyden. Se voi olla joko taulukko- tai monidimensiomalli.

Yhteyden muodostamisen jälkeen malli näkyy Power BI -sivustosi kohdassa **Oma työtila -> Tietojoukot**. Jos vaihdoit ryhmän työtilaan, tietojoukko näkyy silloin ryhmässä.

![Yhteyden muodostaminen tietojoukkoon](media/sql-server-analysis-services-tabular-data/connecttoas_dataset_5.png)

## <a name="dashboard-tiles"></a>Koontinäytön ruudut

Jos kiinnität visualisointeja raportista koontinäyttöön, kiinnitetyt ruudut päivitetään automaattisesti aina 10 minuutin välein. Jos paikallisen Analysis Services -palvelimen tiedot päivitetään, ruudut päivitetään automaattisesti 10 minuutin kuluttua.

## <a name="common-issues"></a>Yleisiä ongelmia

* Mallin rakenteen lataus ei onnistu -virhe - Tämä virhe ilmenee, kun SSAS:ään yhteyttä muodostavalla käyttäjällä ei ole pääsyä SSAS-tietokantaan, -kuutioon ja -malliin.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)  
* [Analysis Services -tietolähteiden hallinta](service-gateway-enterprise-manage-ssas.md)  
* [Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)