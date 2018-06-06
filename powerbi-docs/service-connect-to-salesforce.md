---
title: Yhteyden muodostaminen Salesforceen Power BI:n avulla
description: Power BI:n Salesforce
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 8089c796441fd4200b146da6330dd5c208bf8b30
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815674"
---
# <a name="connect-to-salesforce-with-power-bi"></a>Yhteyden muodostaminen Salesforceen Power BI:n avulla
Power BI:ssä voit muodostaa helposti yhteyden Salesforce.com-tiliisi. Kun yhteys on luotu, tietosi noudetaan ja koontinäyttö sekä tietoihisi perustuvat raportit esitetään automaattisesti.

Muodosta yhteys Power BI:n [Salesforce-sisältöpakettiin](https://app.powerbi.com/getdata/services/salesforce) tai lue lisätietoja Power BI:n [Salesforce-integroinnista](https://powerbi.microsoft.com/integrations/salesforce).

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunasta **Nouda tiedot**.
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. Valitse **Salesforce** ja valitse **Nouda**.  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. Aloita kirjautuminen valitsemalla **Kirjaudu sisään**.
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. Anna Salesforce-tunnistetietosi pyydettäessä. Valitse **Salli**, jotta Power BI voi käyttää Salesforce-perustietoja ja muita tietoja.
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. Määritä avattavan luettelon vaihtoehdolla, mitä haluat tuoda Power BI:hin:
   
   * **Koontinäyttö**
     
     Valitse valmis koontinäyttö henkilöroolin mukaan (esimerkiksi **Myyntipäällikkö**). Nämä koontinäytöt tuovat määrätyt vakiotiedot Salesforcesta. Ne eivät sisällä mukautettuja kenttiä.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **Raportit**
     
     Valitse vähintään yksi mukautettu raportti Salesforce-tililtäsi. Nämä raportit vastaavat näkymiä Salesforcessa ja ne voivat sisältää mukautettujen kenttien tai objektien tietoja.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     Jos et näe raportteja, lisää tai luo niitä Salesforce-tilissäsi ja yritä muodostaa yhteys uudelleen.
7. Aloita tuontiprosessi valitsemalla **Yhdistä**. Näet tuonnin aikana ilmoituksen, jonka mukaan tuonti on käynnissä. Kun tuonti on valmis, näet Salesforce-tietojesi koontinäytön, raportin ja tietojoukon vasemmalla olevassa siirtymisruudussa.
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

Voit muokata tätä koontinäyttöä, jotta näet tiedot juuri haluamallasi tavalla. Voit esittää kysymyksiä Q&A:lla. Voit vaihtoehtoisesti napsauttaa ruutua ja [avata taustalla olevan raportin](service-dashboard-tiles.md) ja [muokata ruutuja](service-dashboard-edit-tile.md) koontinäytössä.

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana.

## <a name="system-requirements"></a>Järjestelmävaatimukset
* Yhdistetty tuotannon Salesforce-tiliin, jossa API-ohjelmointirajapinnan käyttö on sallittu
* Käyttöoikeudet on myönnetty Power BI -sovellukselle sisäänkirjautumisen aikana
* Tilillä on käytettävissä riittävästi API-ohjelmointirajapintakutsuja tietojen vastaanottamiseen ja päivittämiseen
* Päivitystä varten tarvitaan kelvollinen todennustunnus. Varmista, että tuotuna on enintään 5 Salesforce-tietojoukkoa, koska Salesforcessa todennustunnusten enimmäisraja sovellusta kohden on 5.

## <a name="troubleshooting"></a>Vianmääritys
Jos kohtaat virheitä, tarkista edellä mainitut vaatimukset. Huomaa myös, että kirjautumista mukautettuun tai eristettyyn toimialueeseen ei tueta tällä hetkellä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Aloita Power BI:n käyttäminen](service-get-started.md)

[Nouda tiedot](service-get-data.md)

