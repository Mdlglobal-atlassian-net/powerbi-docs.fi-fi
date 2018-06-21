---
title: SAP BW -yhdistimen käyttö Power BI Desktopissa
description: SAP BW -yhdistimen käyttö Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/09/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 79fcd556827c0c5c34615021e45e3abfadfd50e2
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34288149"
---
# <a name="use-the-sap-bw-connector-in-power-bi-desktop"></a>SAP BW -yhdistimen käyttö Power BI Desktopissa
Voit nyt käyttää **SAP Business Warehouse (BW)** -tietoja Power BI Desktopilla.

Tietoja siitä, miten SAP-asiakkaat voivat hyötyä yhdistämällä Power BI:n SAP Business Warehouse (BW) -järjestelmäänsä, saat [Power BI ja SAP BW -teknisestä raportista](https://aka.ms/powerbiandsapbw).

## <a name="installation-of-sap-bw-connector"></a>SAP BW -yhdistimen asentaminen
Käyttääksesi **SAP BW -yhdistintä**, suorita asennus seuraavasti:

1. Asenna **SAP NetWeaver** -kirjasto tietokoneellesi. Voit saada **SAP Netweaver** -kirjaston SAP-järjestelmänvalvojaltasi tai suoraan [SAP-ohjelmiston latauskeskuksesta](https://support.sap.com/swdc). Koska **SAP-ohjelmiston latauskeskus** muuttaa rakennettaan usein, emme voi antaa tarkempia ohjeita kyseisellä sivulla navigoimiseen. **SAP NetWeaver** kirjasto sisältyy yleensä myös SAP-asiakastyökalujen asennukseen.
   
   Saata löytää viimeisimmän version latauspaikan hakulausekkeella *SAP Note #1025361*. Varmista, että **SAP NetWeaver** -kirjaston rakenne (32-bittinen tai 64-bittinen) vastaa **Power BI Desktop** -asennustasi ja asenna sitten kaikki **SAP NetWeaver RFC SDK** -latauksessa olevat tiedostot, mukaan lukien SAP Note.
2. **Hae tiedot** -valintaikkuna sisältää valinnan **SAP Business Warehouse -sovelluspalvelimelle** ja **SAP Business Warehouse -viestipalvelimelle** **Tietokanta**-luokassa.
   
   ![](media/desktop-sap-bw-connector/sap_bw_2a.png)

## <a name="sap-bw-connector-features"></a>SAP BW -yhdistimen ominaisuudet
Power BI Desktopin **SAP BW -yhdistimet** mahdollistavat tietojen tuomisen **SAP Business Warehouse -palvelimen** kuutioissa tai DirectQuerya käyttäen. 

Lisätietoja **SAP BW -yhdistimestä** ja sen käyttämisestä DirectQueryn kanssa löytyy artikkelista [DirectQuery ja SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md).

Kun yhteys muodostetaan, sinun on määritettävä *palvelin*, *järjestelmän numero* ja *asiakastunnus*.

![](media/desktop-sap-bw-connector/sap_bw_3a.png)

Voit myös määrittää kaksi muuta **lisäasetusta**: kielikoodi ja mukautettua MDX-lauseke, joka suoritetaan kyseisellä palvelimella.

![](media/desktop-sap-bw-connector/sap_bw_4a.png)

Jos MDX-lauseketta ei ole määritelty, näytölle aukeaa **Navigator**-ikkuna, jossa näkyy lista palvelimella olevista kuutioista, mahdollisuus porautua ja valita tietoyksikköjä valittavissa olevista kuutioista, mukaan lukien mitat ja mittayksiköt. Power BI tuo esiin kyselyt ja kuutiot, jotka [BW Open Analysis Interface OLAP -sovellusympäristöt](https://help.sap.com/saphelp_nw70/helpdata/en/d9/ed8c3c59021315e10000000a114084/content.htm) ovat paljastaneet.

Kun valitset yhden tai useamman tietoyksikön palvelimelta, tulostetaulukosta luodaan esikatselu, joka perustuu valintaan.

![](media/desktop-sap-bw-connector/sap_bw_5.png)

**Navigator**-ikkunassa on myös **näyttövalintoja**, jotka mahdollistavat seuraavat toiminnot:

* **Näytä *vain valitut tietoyksiköt* tai *Kaikki tietoyksiköt* (oletusnäkymä):** Tämä valinta on kätevä vahvistettaessa lopullista valittujen tietoyksiköiden listaa. Vaihtoehtoinen tapa nähdä tämä on valita *Sarakenimet* *Esikatselu*-alueella.
* **Ota tietojen esikatselut käyttöön (oletustoiminto):** Voit myös hallita näytetäänkö tietojen esikatselu tässä dialogissa. Tietojen esikatselun ottaminen pois käytöstä vähentää palvelinkutsujen määrää, koska palvelin ei enää pyydä tietoja esikatseluita varten.
* **Tekniset nimet:** SAP BW tukee *teknisten nimien* käsitettä kuution sisältämille tietoyksiköille. Tekniset nimet mahdollistavat sen, että kuution omistaja voi näyttää *käyttäjäystävällisiä* nimiä kuution objekteille pelkästään *fyysisten nimien* sijaan.

![](media/desktop-sap-bw-connector/sap_bw_6.png)

Kun olet valinnut **Navigator**-ikkunassa kaikki tarvittavat objektit, voit päättää mitä teet seuraavaksi valitsemalla seuraavista **Navigator**-ikkunan alaosassa olevista painikkeista:

* **Lataus**-painikkeen valitseminen käynnistää kaikkien valittujen rivien lataamisen tulostetaulukosta Power BI Desktop -tietomalliin ja vie sinut sitten  **raportti**-näkymään, jossa voit aloittaa tietojen visualisoinnin tai tehdä muutoksia **tieto-** tai **suhde**-näkymissä.
* **Muokkaus**-painikkeen valitseminen avaa **kyselyeditorin**, jos voit suorittaa tietojen muutos- ja suodatusvaiheita ennen kuin rivit tuodaan Power BI Desktop -tietomalliin.

Muista, että sen lisäksi, että voit tuoda tietoja **SAP BW** -kuutioista, voit myös tuoda Power BI Desktopiin tietoja laajasta valikoimasta muita tietolähteitä ja yhdistää ne sitten yhdeksi raportiksi. Tämä tarjoaa monia kiinnostavia vaihtoehtoja raportointiin ja analyysiin **SAP BW** -tietojen lisäksi.

## <a name="troubleshooting"></a>Vianmääritys
Tämä osio sisältää vianmäärityksen tilanteita ja ratkaisuja käytettäessä tätä **SAP BW** -yhdistimen esikatseluversiota.

1. **SAP BW** -yhdistimen numeeriset tiedot palauttavat desimaalipisteitä pilkkujen sijaan. Esimerkiksi 1,000,000 palautetaan muodossa 1.000.000.
   
   **SAP BW** -yhdistin palauttaa desimaalitiedot joko desimaalierottimella *,* (pilkku) tai desimaalierottimella *.* (piste). Määrittääkseen kumpaa **SAP BW** -yhdistimen tulisi käyttää desimaalierottimena **Power BI Desktopin** käyttämä ajuri lähettää kutsun *BAPI_USER_GET_DETAIL*. Tämä kutsu palauttaa rakenteen nimeltä **DEFAULTS**, jossa on kenttä nimeltä *DCPFM*, johon on tallennettu *desimaalimuodon merkintä*. Tämä voi olla yksi seuraavista kolmesta arvosta:
   
       ‘ ‘ (space) = Decimal point is comma: N.NNN,NN
       'X' = Decimal point is period: N,NNN.NN
       'Y' = Decimal point is N NNN NNN,NN
   
   Asiakkaat, jotka ovat ilmoittaneet tästä ongelmasta, havaitsivat, että kutsu *BAPI_USER_GET_DETAIL* epäonnistuu tietyn käyttäjän (käyttäjän, jolla näkyy virheellisiä tietoja) kohdalla ja tuottaa vikaviestin, joka muistuttaa seuraavaa:
   
       You are not authorized to display users in group TI:
           <item>
               <TYPE>E</TYPE>
               <ID>01</ID>
               <NUMBER>512</NUMBER>
               <MESSAGE>You are not authorized to display users in group TI</MESSAGE>
               <LOG_NO/>
               <LOG_MSG_NO>000000</LOG_MSG_NO>
               <MESSAGE_V1>TI</MESSAGE_V1>
               <MESSAGE_V2/>
               <MESSAGE_V3/>
               <MESSAGE_V4/>
               <PARAMETER/>
               <ROW>0</ROW>
               <FIELD>BNAME</FIELD>
               <SYSTEM>CLNTPW1400</SYSTEM>
           </item>
   
   Ratkaistakseen tämän vian, käyttäjien tulee pyytää SAP-järjestelmänvalvojaansa antamaan Power BI:ssä käytettävälle SAPBW-käyttäjälle oikeuden suorittaa kutsu *BAPI_USER_GET_DETAIL*. Kannattaa myös tarkistaa, että käyttäjällä on tarvittava *DCPFM*-arvo, joka kuvattiin aikaisemmin tämän vianmäärityksen ratkaisussa.
2. **SAP BEx -kyselyiden yhteydet**
   
   Voit suorittaa Power BI Desktopilla **BEx**-kyselyitä ottamalla käyttöön tietty ominaisuus, joka on esitetty seuraavassa kuvassa:
   
   ![](media/desktop-sap-bw-connector/sap_bw_8.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Lisätietoja SAP HANA -tietokannoista ja DirectQuery-kyselystä saat seuraavista lähteistä:

* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [Power BI ja SAP BW tekninen raportti](https://aka.ms/powerbiandsapbw)
