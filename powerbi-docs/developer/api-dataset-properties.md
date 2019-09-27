---
title: Power BI -tietojoukon ominaisuudet
description: Lisätietoja Power BI -tietojoukon ohjelmointirajapintojen ominaisuuksista
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 508f304e2f5033c301db683e3b7557856fb3731b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61386289"
---
# <a name="dataset-properties"></a>Tietojoukon ominaisuudet

Nykyinen tietojoukkojen ohjelmointirajapinnan v1 sallii tietojoukkoja luotavan vain nimen ja taulukkokokoelman kanssa. Kullakin taulukolla voi olla nimi ja sarakekokoelma. Kullakin sarakkeella on nimi ja tietotyyppi. Laajennamme näitä ominaisuuksia etenkin lisäämällä mittarien ja taulukkojen välisten suhteiden tuen. Seuraavassa on täydellinen luettelo tuetuista ominaisuuksista tätä julkaisua varten:

> [!IMPORTANT]
> Siihen pääsee [Tietojoukkojen toimintaryhmät](https://docs.microsoft.com/rest/api/power-bi/datasets) -sivulta.

## <a name="dataset"></a>Tietojoukko

Nimi  |Tyyppi  |Kuvaus  |Vain luku  |Pakollinen
---------|---------|---------|---------|---------
tunnus     |  GUID-tunnus       | Järjestelmän laajuinen yksilöllinen tunnus tietojoukolle.        | Tosi        | Epätosi        
nimi     | Merkkijono        | Käyttäjän määrittämä tietojoukon nimi.        | Epätosi        | Tosi        
taulukot     | Table[]        | Taulukkokokoelma.        |  Epätosi       | Epätosi        
suhteet     | Relationship[]        | Taulukkojen välisten suhteiden kokoelma.        | Epätosi        |  Epätosi  
defaultMode     | Merkkijono        | Määrittää, onko tietojoukkoon työnnetty tai virtautettu tai sekä työnnetty että virtautettu arvot ”Push” ja ”Streaming”.         | Epätosi        |  Epätosi

## <a name="table"></a>Taulukko

Nimi  |Tyyppi  |Kuvaus  |Vain luku  |Pakollinen
---------|---------|---------|---------|---------
nimi     | Merkkijono        |  Käyttäjän määrittämä taulukon nimi. Sitä käytetään myös taulun tunnuksena.       | Epätosi        |  Tosi       
sarakkeet     |  sarake[]       |  Sarakekokoelma.       | Epätosi        |  Tosi       
mittarit     | mittari[]        |  Mittarikokoelma.       | Epätosi        |  Epätosi       
isHidden     | Totuusarvo        | Jos arvo on tosi, taulukko on piilotettu asiakastyökaluilta.        | Epätosi        | Epätosi        

## <a name="column"></a>Sarake

Nimi  |Tyyppi  |Kuvaus  |Vain luku  |Pakollinen
---------|---------|---------|---------|---------
nimi     |  Merkkijono        | Käyttäjän määrittämä sarakkeen nimi.        |  Epätosi       | Tosi       
dataType     |  Merkkijono       |  Tuetut [EDM-tietotyypit](https://msdn.microsoft.com/library/ee382832.aspx) ja rajoitukset. Katso [Tietotyypin rajoitukset](#DataTypeRestrictions).      |  Epätosi       | Tosi        
formatString     | Merkkijono        | Merkkijono, joka kuvaa, miten arvoa olisi muotoiltava, kun se näytetään. Lisätietoja merkkijonon muotoilemisesta on artikkelissa [Merkkijonon sisällön muotoileminen](https://msdn.microsoft.com/library/ms146084.aspx).      | Epätosi        | Epätosi        
sortByColumn    | Merkkijono        |   Sarakkeen merkkijonon nimi samassa taulukossa, jota käytetään nykyisen sarakkeen järjestämiseen.     | Epätosi        | Epätosi       
dataCategory     | Merkkijono        |  Merkkijonon arvo, jota käytetään tietoluokalle, joka kuvaa tässä sarakkeessa olevia tietoja. Joitakin yleisiä arvoja ovat: Address, City, Continent, Country, Image, ImageUrl, Latitude, Longitude, Organization, Place, PostalCode, StateOrProvince, WebUrl       |  Epätosi       | Epätosi        
isHidden    |  Totuusarvo       |  Ominaisuus, joka ilmaisee, onko sarake piilotettu näkyvistä. Oletusarvona on epätosi.       | Epätosi        | Epätosi        
summarizeBy     | Merkkijono        |  Sarakkeen oletusarvoinen koostemenetelmä. Arvoja ovat: default, none, sum, min, max, count, average, distinctCount     |  Epätosi       | Epätosi

## <a name="measure"></a>Mittari

Nimi  |Tyyppi  |Kuvaus  |Vain luku  |Pakollinen
---------|---------|---------|---------|---------
nimi     | Merkkijono        |  Käyttäjän määrittämä mittarin nimi.       |  Epätosi       | Tosi        
lauseke     | Merkkijono        | Kelvollinen DAX-lauseke.        | Epätosi        |  Tosi       
formatString     | Merkkijono        |  Merkkijono, joka kuvaa, miten arvoa olisi muotoiltava, kun se näytetään. Lisätietoja merkkijonon muotoilemisesta on artikkelissa [Merkkijonon sisällön muotoileminen](https://msdn.microsoft.com/library/ms146084.aspx).       | Epätosi        | Epätosi        
isHidden     | Merkkijono        |  Jos arvo on tosi, taulukko on piilotettu asiakastyökaluilta.       |  Epätosi       | Epätosi       

## <a name="relationship"></a>Suhde

Nimi  |Tyyppi  |Kuvaus  |Vain luku  |Pakollinen 
---------|---------|---------|---------|---------
nimi     | Merkkijono        | Käyttäjän määrittämä suhteen nimi. Sitä käytetään myös suhteen tunnuksena.        | Epätosi       | Tosi        
crossFilteringBehavior     | Merkkijono        |    Yhteyden suodatussuunta: OneDirection (oletus), BothDirections, Automatic       | Epätosi        | Epätosi        
fromTable     | Merkkijono        | Viiteavaintaulukon nimi.        | Epätosi        | Tosi         
fromColumn    | Merkkijono        | Viiteavainsarakkeen nimi.        | Epätosi        | Tosi         
toTable    | Merkkijono        | Ensisijaisen avaintaulukon nimi.        | Epätosi        | Tosi         
toColumn     | Merkkijono        | Ensisijaisen avainsarakkeen nimi.        | Epätosi        | Tosi        

<a name="DataTypeRestrictions"/>

## <a name="data-type-restrictions-applies-to-datatype-property"></a>Tietotyypin rajoitukset (sovelletaan dataType-ominaisuuteen)

Tietotyyppi  |Rajoitukset  
---------|---------
Int64     |   Int64.MaxValue ja Int64.MinValue eivät ole sallittuja.      
Double     |  Double.MaxValue- ja Double.MinValue-arvoja ei sallita. NaN:ää ei tueta. Komentoja +Infinity ja -Infinity ei tueta tietyissä funktioissa (esim. Min, Max).       
Totuusarvo     |   Tosi tai epätosi.
Päivämäärä ja aika    |   Tietojen lataamisen aikana arvot muutetaan määrällisiksi 1/300 sekunnin (3,33 ms) kerrannaisten päiväosiin.      
Merkkijono     |  Tällä hetkellä sallii enintään 4 000 merkkiä merkkijonoarvoa kohden.
Desimaali|tarkkuus = 28, mittakaava = 4

## <a name="example"></a>Esimerkki
Seuraava koodiesimerkki sisältää useita tällaisia ominaisuuksia:

```json
{

  "name": "PushAdvanced",

  "tables": [

    {

      "name": "Date",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        }

      ]

    },

    {

      "name": "sales",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "Sales",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ],

      "measures": [

        {

          "name": "percent to forecast",

          "expression": "SUM(sales[Sales])/SUM(forecast[forecast])",

          "formatString": "0.00 %;-0.00 %;0.00 %"

        }

      ]

    },

    {

      "name": "forecast",

      "columns": [

        {

          "name": "date",

          "dataType": "dateTime",

          "formatString": "m/d/yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "forecast",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ]

    }

  ],

  "relationships": [

    {

      "name": "2ea345ce-b147-436e-8ac2-9d3c4d82af8d",

      "fromTable": "sales",

      "fromColumn": "Date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    },

    {

      "name": "5d95f419-e589-4345-9581-6e70670b1bba",

      "fromTable": "forecast",

      "fromColumn": "date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    }

  ]

}
```