---
title: Yhteyden muodostaminen Salesforceen Power BI:n avulla
description: Power BI:n Salesforce
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/30/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 02b98d807ccc84aa83826ae5e9eecdbdd1987a91
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008576"
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

Voit muokata tätä koontinäyttöä, jotta näet tiedot juuri haluamallasi tavalla. Voit esittää kysymyksiä Q&A:lla. Voit vaihtoehtoisesti napsauttaa ruutua ja [avata taustalla olevan raportin](consumer/end-user-tiles.md) ja [muokata ruutuja](service-dashboard-edit-tile.md) koontinäytössä.

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md) <<<<<<< HEAD
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu =======
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
>>>>>>> 66fe62d8f200efd9cfeb465eeb5f370dbbaa63be
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="system-requirements-and-considerations"></a>Järjestelmävaatimukset ja huomioon otettavat seikat
- Yhdistetty tuotannon Salesforce-tiliin, jossa API-ohjelmointirajapinnan käyttö on sallittu
- Käyttöoikeudet on myönnetty Power BI -sovellukselle sisäänkirjautumisen aikana
- Tilillä on käytettävissä riittävästi API-ohjelmointirajapintakutsuja tietojen vastaanottamiseen ja päivittämiseen
- Päivitystä varten tarvitaan kelvollinen todennustunnus. Varmista, että tuotuna on enintään 5 Salesforce-tietojoukkoa, koska Salesforcessa todennustunnusten enimmäisraja sovellusta kohden on 5.
- Salesforce-raporttien ohjelmointirajapinnassa on rajoitus, joka tukee enintään 2 000 riviä tietoja.


## <a name="troubleshooting"></a>Vianmääritys
Jos kohtaat virheitä, tarkista edellä mainitut vaatimukset. Huomaa myös, että kirjautumista mukautettuun tai eristettyyn toimialueeseen ei tueta tällä hetkellä.

### <a name="unable-to-connect-to-the-remote-server-message"></a>”Yhteyden muodostaminen etäpalvelimeen ei onnistu” -sanoma

Jos saat sanoman ”Yhteyden muodostaminen etäpalvelimeen ei onnistu”, kun yrität muodostaa yhteyden Salesforce-tiliin, katso tätä ratkaisua Outsystems-foorumissa: [Salesforce-liittimen loki virhesanomassa: Yhteyden muodostaminen etäpalvelimeen ei onnistu](https://www.outsystems.com/forums/Forum_TopicView.aspx?TopicId=17674&TopicName=log-in-error-message-unable-to-connect-to-the-remote-server&)


## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)

[Nouda tiedot](service-get-data.md)

