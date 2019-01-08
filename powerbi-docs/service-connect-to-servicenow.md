---
title: Yhteyden muodostaminen ServiceNow Power BI:lle
description: ServiceNow Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 285c22347f049e6b99cb97fa19efc6363d9b57cb
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008645"
---
# <a name="connect-to-servicenow-with-power-bi-for-incident-reporting"></a>Yhteyden muodostaminen ServiceNow Power BI:lle ongelmien raportointia varten
ServiceNow tarjoaa useita tuotteita ja ratkaisuja, kuten business, toiminnot ja IT-hallinta liiketoimintasi edistämiseksi. Tämä sisältöpaketti sisältää useita raportteja ja merkityksellisiä tietoja avoimista, äskettäin ratkaistuista ja viimeksi kuitatuista tapauksista.  

Yhteyden muodostaminen [ServiceNow-tapausten](https://app.powerbi.com/getdata/services/servicenow) Power BI-sisältöpakettiin.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-servicenow/pbi_getdata.png) 
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-servicenow/pbi_getservices.png) 
3. Valitse **ServiceNow -tapaukset** \> **Nouda**.
   
   ![](media/service-connect-to-servicenow/connect.png)
4. Anna ServiceNow URL-osoite ja päivien tai tietueiden tuotava alue. Huomaa, että heti, kun raja ylittyy, tuonti pysähtyy.
   
   ![](media/service-connect-to-servicenow/params.png)
5. Kirjoita pyydettäessä ServiceNow **Basic** -tunnistetietosi. Huomaa, että kertakirjautumista ei vielä tueta, lisätietoja järjestelmävaatimuksista on alla.
   
   ![](media/service-connect-to-servicenow/creds.png)
6. Kun kirjautuminen on valmis, tuonti alkaa. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
    ![](media/service-connect-to-servicenow/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="system-requirements"></a>Järjestelmävaatimukset
Yhteyden muodostamiseksi tarvitaan seuraavaa:  

* Tili, jolla pääset osoitteeseen yourorganization.service-now.com perustodennusta varten (kertakirjautumisen ei tueta tässä versiossa)  
* Tilillä on oltava rest_service-rooli ja tapauksen taulukon lukuoikeudet  

## <a name="troubleshooting"></a>Vianmääritys
Jos saat tunnistetietoa koskevan virheen latauksen aikana, tarkista käyttövaatimukset yltä. Jos sinulla on oikeat oikeudet ja kohtaat yhä ongelmia, käsittele asiaa ServiceNow-järjestelmänvalvojan kanssa ja varmista, että sinulla on lisäoikeudet, joita voidaan vaatia mukautettuun esiintymään.

Jos havaitset pitkä latausaikoja, tarkista tapausten määrä ja päivien määrä yhteyden aikana ja harkitse määrien pienentämistä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)

[Power BI:n peruskäsitteet](consumer/end-user-basic-concepts.md)

