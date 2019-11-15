---
title: Yhteyden muodostaminen Salesforceen Power BI:n avulla
description: Power BI:n Salesforce
author: SarinaJoan
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/30/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6fedd3994a9e6a14ea89637a0c12aa8dd47928a9
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73854637"
---
# <a name="connect-to-salesforce-with-power-bi"></a>Yhteyden muodostaminen Salesforceen Power BI:n avulla
Power BI:ssä voit muodostaa helposti yhteyden Salesforce.com-tiliisi. Tämän yhteyden avulla voit noutaa Salesforce-tietosi. Raporttinäkymät ja raportit tarjotaan automaattisesti.

Lue lisää [Salesforcen integroinnista](https://powerbi.microsoft.com/integrations/salesforce) Power BI:hin.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse Power BI:ssä siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. Valitse **Salesforce-analyysi** ja valitse **Hae**.  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. Valitse **Kirjaudu sisään** aloittaaksesi kirjautumisen.
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. Anna Salesforce-tunnistetietosi pyydettäessä. Valitse **Salli**, jotta Power BI voi käyttää Salesforce-perustietoja ja muita tietoja.
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. Määritä avattavan luettelon vaihtoehdolla, mitä haluat tuoda Power BI:hin:
   
   * **Koontinäyttö**
     
     Valitse valmis koontinäyttö henkilöroolin mukaan (esimerkiksi **Myyntipäällikkö**). Nämä raporttinäkymät tuovat määrätyt vakiotiedot Salesforcesta. Ne eivät sisällä mukautettuja kenttiä.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **Raportit**
     
     Valitse vähintään yksi mukautettu raportti Salesforce-tililtäsi. Nämä raportit vastaavat näkymiä Salesforcessa ja ne voivat sisältää mukautettujen kenttien tai objektien tietoja.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     Jos et näe raportteja, lisää tai luo niitä Salesforce-tilissäsi ja yritä muodostaa yhteys uudelleen.

7. Aloita tuontiprosessi valitsemalla **Yhdistä**. Näet tuonnin aikana ilmoituksen, joka kertoo tuonnin on käynnissä. Kun tuonti on valmis, näet Salesforce-tietojesi koontinäytön, raportin ja tietojoukon siirtymisruudussa.
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

Voit muokata tätä raporttinäkymää niin, että näet tiedot juuri haluamallasi tavalla. Voit esittää kysymyksiä Q&A:lla. Voit vaihtoehtoisesti [napsauttaa ruutua](consumer/end-user-tiles.md) avataksesi taustalla olevan raportin ja [muokata tai poistaa raporttinäkymän ruutuja](service-dashboard-edit-tile.md).

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muokkaa raporttinäkymän ruutua tai poista sellainen](service-dashboard-edit-tile.md)
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla

## <a name="system-requirements-and-considerations"></a>Järjestelmävaatimukset ja huomioon otettavat seikat

- Yhdistetty tuotannon Salesforce-tiliin, jossa API-ohjelmointirajapinnan käyttö on sallittu

- Käyttöoikeudet on myönnetty Power BI -sovellukselle sisäänkirjautumisen aikana

- Tilillä on käytettävissä riittävästi API-ohjelmointirajapintakutsuja tietojen vastaanottamiseen ja päivittämiseen

- Päivitystä varten tarvitaan kelvollinen todennustunnus. Varmista, että tuotuna on enintään viisi Salesforce-tietojoukkoa, koska Salesforcessa todennustunnusten enimmäisraja sovellusta kohden on viisi.

- Salesforce-raporttien ohjelmointirajapinnassa on rajoitus, joka tukee enintään 2 000 riviä tietoja.


## <a name="troubleshooting"></a>Vianmääritys

Jos kohtaat virheitä, tarkista edellä mainitut vaatimukset. 

Tällä hetkellä kirjautumista mukautettuun tai eristettyyn toimialueeseen ei tueta.

### <a name="unable-to-connect-to-the-remote-server-message"></a>”Yhteyden muodostaminen etäpalvelimeen ei onnistu” -sanoma

Jos saat sanoman ”Yhteyden muodostaminen etäpalvelimeen ei onnistu”, kun yrität muodostaa yhteyden Salesforce-tiliin, katso seuraava ratkaisu foorumilla: [Salesforce-liittimen kirjautumisvirheilmoitus: Yhteyden muodostaminen etäpalvelimeen ei onnistu](https://www.outsystems.com/forums/Forum_TopicView.aspx?TopicId=17674&TopicName=log-in-error-message-unable-to-connect-to-the-remote-server&)


## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](fundamentals/power-bi-overview.md)

[Power BI -palvelun tietolähteet](service-get-data.md)

