---
title: Azure SQL Data Warehouse ja DirectQuery
description: Azure SQL Data Warehouse ja DirectQuery
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/22/2018
ms.author: maghan
LocalizationGroup: Data from databases
ms.openlocfilehash: f264dadf9d9d91083094d393e1b63d9f53aaca4c
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34722355"
---
# <a name="azure-sql-data-warehouse-with-directquery"></a>Azure SQL Data Warehouse ja DirectQuery
Azure SQL Data Warehouse ja DirectQueryn avulla voit luoda dynaamisia raportteja niiden tietojen ja arvojen perusteella, joita sinulla jo on Azure SQL Data Warehousessa. DirectQueryn avulla kyselyt lähetetään takaisin Azure SQL Data Warehouseen reaaliaikaisesti tutkiessasi tietoja. Tämä yhdessä SQL Data Warehousen asteikon kanssa mahdollistaa sen, että käyttäjät voivat luoda dynaamisia raportteja muutamassa minuutissa monen teratavun edestä tietoa. Lisäksi **Avaa Power BI:ssä** -painikkeen käyttöönoton avulla käyttäjät voivat muodostaa yhdistää Power BI:n suoraan SQL Data Warehouseen ilman, että heidän tarvitsee määrittää manuaalisesti tietoja.

SQL Data Warehouse -yhdistintä käytettäessä

* Määritä palvelimen täydellinen nimi yhteyttä muodostettaessa (katso tiedot alla)
* Varmista, että palvelimen palomuurisääntöjen määrityksenä on ”Salli Azure-palvelujen käyttö”
* Jokainen toiminto, kuten sarakkeen valitseminen tai suodattimen lisääminen, tekee kyselyn suoraan tietovarastoon
* Ruudut on määritetty päivitettäväksi noin 15 minuutin välein, ja päivitystä ei tarvitse ajoittaa.  Tätä voidaan muokata Lisäasetukset-kohdassa, kun muodostat yhteyden.
* Q&A ei ole käytettävissä DirectQuery-tietojoukoissa
* Rakenteen muutoksia ei poimita automaattisesti

Nämä rajoitukset ja muistiinpanot saattavat muuttua jatkaessamme käyttökokemusten kehittämistä. Yhdistämisen vaiheet on kuvattu alla.

## <a name="using-the-open-in-power-bi-button"></a>Avaa Power BI:ssä -painikkeen käyttäminen
Helpoin tapa siirtyä SQL Data Warehousen ja Power BI:n välillä on **Avaa Power BI:ssä** -painikkeella Azuren esikatseluportaalissa. Tämän painikkeen avulla voit aloittaa saumattomasti uusien koontinäyttöjen luomisen Power BI:ssä.

1. Aloita siirtymällä SQL Data Warehouse -esiintymään Azuren esikatseluportaalissa. Huomaa, että SQL Data Warehousella on näkyvyys ainoastaan Azuren esikatseluportaalissa tällä hetkellä.
2. Napsauta **Avaa Power BI:ssä** -painiketta
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/openinpowerbi.png)
3. Jos emme voi kirjata sinua suoraan sisään tai jos sinulla ei ole Power BI -tiliä, sinun on kirjauduttava sisään.
4. Sinut ohjataan SQL Data Warehousen yhteyssivulle, ja SQL Data Warehousen tiedot on täytetty valmiiksi. Anna tunnistetietosi ja muodosta yhteys valitsemalla Yhdistä.

## <a name="connecting-through-power-bi"></a>Yhteyden muodostaminen Power BI:n kautta
SQL Data Warehouse näkyy myös Power BI:n Nouda tiedot -sivulla. 

1. Valitse vasemman siirtymisruudun alareunasta **Nouda tiedot**.  
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/getdatabutton.png)
2. Valitse **Tietokannat**-kohdassa **Nouda**.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/databases.png)
3. Valitse **SQL Data Warehouse** \> **Yhdistä**.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/azuresqldatawarehouseconnect.png)
4. Anna tarvittavat tiedot, jotta voit muodostaa yhteyden. **Parametrien etsiminen** -kohdassa alla näkyy, missä tiedot voivat sijaita Azure-portaalissa.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/servername.png)
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/servernamewithadvanced.png)
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/username.png)
   
   > [!NOTE]
   > Käyttäjänimi on käyttäjä, joka on määritetty Azure SQL Data Warehouse -esiintymässä.
   > 
   > 
5. Poraudu tietojoukkoon valitsemalla uuden ruudun tai juuri luodun tietojoukon, jonka merkkinä on tähti. Tällä tietojoukolla on sama nimi kuin tietokannalla.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/dataset2.png)
6. Voit tutkia kaikkia taulukoita ja sarakkeita. Sarakkeen valitseminen lähettää kyselyn takaisin lähteeseen luoden visualisoinnin dynaamisesti. Suodattimet myös käännetään kyselyiksi takaisin tietovarastoon. Nämä visualisoinnit voidaan tallentaa uudessa raportissa ja kiinnittää takaisin koontinäyttöön.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/explore3.png)

## <a name="finding-parameter-values"></a>Parametriarvojen etsiminen
Täydellinen palvelimen nimi ja tietokannan nimi löytyvät Azure-esikatseluportaalista. Huomaa, että SQL Data Warehousella on näkyvyys ainoastaan Azuren esikatseluportaalissa tällä hetkellä.

![](media/service-azure-sql-data-warehouse-with-direct-connect/azureportal.png)

> [!NOTE]
> Jos Power BI -vuokraaja on samalla alueella kuin Azure SQL Data Warehouse, lähtevän liikenteen maksuja ei ole. Voit etsiä Power BI -vuokraajan sijainnin [näiden ohjeiden](https://docs.microsoft.com/power-bi/service-admin-where-is-my-tenant-located) avulla.
>

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)  
[Tietojen noutaminen Power BI:hin](service-get-data.md)  
[Azure SQL Data Warehouse](https://azure.microsoft.com/documentation/services/sql-data-warehouse/)  

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)