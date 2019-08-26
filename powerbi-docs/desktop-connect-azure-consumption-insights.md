---
title: Azuren kustannus- ja käyttötietojen analysointi Power BI Desktopissa
description: Voit yhdistää helposti Azureen ja saada merkityksellisiä tietoja kulutuksesta ja käytöstä Power BI Desktopin avulla
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/14/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 80eb366015de3822b9c8c455f1ee386a34e1f457
ms.sourcegitcommit: f6ac9e25760561f49d4257a6335ca0f54ad2d22e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2019
ms.locfileid: "69561017"
---
# <a name="analyze-azure-cost-and-usage-data-in-power-bi-desktop"></a>Azuren kustannus- ja käyttötietojen analysointi Power BI Desktopissa

Voit yhdistää Power BI Desktopin Azureen ja saada tarkempia tietoja Azuren käytöstä organisaatiossasi. Tietojen avulla voit luoda mukautettuja raportteja ja mittareita, joiden avulla saat entistä paremman käsityksen ja analyysit Azuren käytöstä.

Power BI tukee tällä hetkellä Enterprise Agreement -sopimusten ja asiakassopimusten laskutustileihin yhdistämistä.

* **Enterprise Agreement** -sopimusten käyttäjien tulee muodostaa yhteys **Azure Consumption Insights** -liittimellä (alla).

* **Asiakassopimusten** käyttäjien tulee muodostaa yhteys [**Azure Cost Management -liittimellä**](#connect-with-azure-cost-management).

## <a name="connect-with-azure-consumption-insights"></a>Yhteyden muodostaminen Azure Consumption Insightsin avulla

Azure Consumption Insightsin avulla voit muodostaa yhteyden Azure Enterprise Agreement -sopimuksen laskutustileihin.

Tässä osiossa on ohjeita siirrettävien tietojen saamisesta Azure Enterprise -liittimen avulla. Lisäksi *käyttötietosarakkeiden* yhteenveto on saatavilla **ACI** (Azure Consumption Insights) -ohjelmointirajapinnassa.

**Azure Consumption Insights** -liittimen käyttö edellyttää, että sinulla on pääsy Azure-portaalin yritysominaisuuksiin.

**Azure Consumption Insights** -liittimen käyttäminen **Power BI Desktopissa**: 

1. Valitse **Aloitus**-valintanauhasta **Nouda tiedot**.

1. Valitse vasemmalla näkyvistä luokista **Online-palvelut**.  

1. Valitse **Microsoft Azure Consumption Insights (beeta)** . 

1. Valitse **Muodosta yhteys**.

   ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_01b.png)

   Anna avautuvaan valintaikkunaan oma **Azure-rekisteröintinumerosi**.

   ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_02.png)

   * Löydät rekisteröintinumerosi [Azure Enterprise Portalista](https://ea.azure.com) seuraavassa kuvassa näkyvästä sijainnista:

  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_08.png)

   Tämä liitinversio tukee vain yritysrekisteröintejä osoitteesta https://ea.azure.com. Kiinassa tehtyjä rekisteröintejä ei tueta tällä hetkellä.

   Anna seuraavaksi *tiliavaimesi* yhteyden muodostamista varten.

   ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_03.png)

   * Löydät rekisteröintiin tarvittavan tiliavaimesi [Azure Enterprise Portalista](https://ea.azure.com).

  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_09.png)

Kun annat *tiliavaimesi* ja valitset **Yhdistä**, näyttöön avautuu **Navigator**, jossa on yhdeksän käytettävissä olevaa taulukkoa:

| Taulukko        | Kuvaus |
|------------- | -------------------------------------------------------------|
| **Budjetit** | Budjettitiedot todellisten kustannusten tai käytön tarkastelemiseksi olemassa oleviin budjettitavoitteisiin verrattuna. |
| **MarketPlace** | Käyttöön perustuvat Azure Marketplace -maksut. |
| **PriceSheets** | Käytettävissä olevat hinnat mittarin mukaan rekisteröintiä varten. |
| **RICharges** | Varattuihin esiintymiin liittyvät maksut viimeisten 24 kuukauden ajalta. |
| **RIRecommendations_Single** | Varatun esiintymän ostosuositukset yhdessä tilauksessa käyttötrendien perusteella viimeisten 7, 30 tai 60 päivän ajalta. |
| **RIRecommendations_Shared** | Varatun esiintymän ostosuositukset käyttötrendien perusteella kaikissa tilauksissa viimeisten 7, 30 tai 60 päivän ajalta. |
| **RIUsage** | Varattujen esiintymien kulutustiedot viimeisen kuukauden ajalta. |
| **Summaries** | Kuukausittainen yhteenveto saldoista, uusista ostoista, Microsoft Azure Marketplacen palvelumaksuista, muutoksista ja ylitysmaksuista. |
| **UsageDetails** | Kulutettujen määrien erittely ja arvioidut rekisteröintimaksut. |

Voit avata esikatselun valitsemalla minkä tahansa taulukon vieressä olevan valintaruudun. Voit valita yhden tai useamman taulukon valitsemalla taulukon nimen vieressä olevan ruudun ja sen jälkeen **Lataa**.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_04b.png)

> [!NOTE]
> *Summary* (Yhteenveto)- ja *PriceSheet* (Hinnasto) -taulukot ovat käytettävissä vain rekisteröintitason ohjelmointirajapinta-avaimelle. Lisäksi näiden taulukoiden tiedot sisältävät oletusarvoisesti kuluvan kuukauden käyttöä koskevat *Usage* (Käyttö) -tiedot ja *PriceSheet* (Hinnasto) -tiedot. *Summary* (Yhteenveto)- ja *MarketPlace*-taulukot eivät rajoitu kuluvaan kuukauteen.
>
>

Kun valitset **Lataa**, tiedot ladataan **Power BI Desktopiin**.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_05.png)

Kun valitsemasi tiedot on ladattu, valitsemasi taulukot ja kentät näkyvät **Kentät**-ruudussa.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_06.png)

## <a name="using-azure-consumption-insights"></a>Azure Consumption Insightsin käyttö
**Azure Consumption Insights** -liittimen käyttö edellyttää, että sinulla on pääsy Azure-portaalin yritysominaisuuksiin.

Kun olet ladannut tiedot onnistuneesti **Azure Consumption Insights** -liittimen avulla, voit luoda omia mukautettuja mittareita ja sarakkeita käyttämällä **kyselyeditoria**. Voit myös luoda visualisointeja, raportteja ja koontinäyttöjä, joita voit jakaa **Power BI -palvelussa**.

Tyhjän kyselyn avulla voit noutaa mukautetun Azure-mallikyselykokoelman. Voit noutaa sen kahdella tavalla: 

**Power BI Desktopissa**: 

1. Valitse **Aloitus**-valintanauha 
2. Valitse **Nouda tiedot** > **Tyhjä kysely** 

Tai **kyselyeditorissa**: 

1. Napsauta hiiren kakkospainikkeella vasemmanpuoleista **Kyselyt**-ruutua 
2. Valitse avautuvasta valikosta **Uusi kysely > Tyhjä kysely**

Kirjoita **kaavariville**:

    = MicrosoftAzureConsumptionInsights.Contents

Seuraavassa kuvassa näkyy esimerkkikokoelma, joka tulee näkyviin.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_07.png)

Kun käsittelet raportteja ja luot kyselyitä, voit käyttää seuraavia:

* Voit määrittää kuukausien määrän alkaen nykyisestä päivämäärästä käyttämällä *numberOfMonth*-parametria.
  * Käytä arvoa välillä 1–36. Ilmoita kuukausien määrä, jonka haluat tuoda, kuluvasta päivämäärästä alkaen. Suosittelemme enintään 12 kuukauden tietojen noutamista. Tämä rajoituksen ansiosta vältetään Power BI:n kyselyiden tuonnin rajoitukset ja tietomäärän kynnysarvot.
* Voit määrittää historiallisen aikaikkunan kuukausijakson käyttämällä parametreja *startBillingDataWindow* ja *endBillingDataWindow*.
* Älä käytä *numberOfMonth*-parametria yhdessä *startBillingDataWindow*- tai *endBillingDataWindow*-parametrin kanssa

## <a name="migrate-from-the-azure-enterprise-connector"></a>Siirtyminen Azure Enterprise -liittimestä

Osa asiakkaista on luonut visualisointeja *Azure Enterprise -liittimen (beeta)* avulla. Se korvataan lopulta **Azure Consumption Insights** -liittimellä. Uudessa liittimessä on esimerkiksi seuraavia ominaisuuksia ja parannuksia:

* *taseen yhteenvetoa* ja *Marketplace-ostoksia* varten saatavilla olevat lisätietolähteet
* uudet ja edistykselliset parametrit, kuten *startBillingDataWindow* ja *endBillingDataWindow*
* parempi suorituskyky ja vasteaika.

Seuraavissa vaiheissa näytetään, miten siirrytään **Azure Consumption Insights** -liittimeen. Näissä vaiheissa mukautettujen koontinäyttöjen tai raporttien luomiseen tehty työ säilytetään.

### <a name="step-1-connect-to-azure-using-the-new-connector"></a>Vaihe 1: Yhdistä Azureen uuden liittimen avulla
Ensimmäinen vaihe on käyttää **Azure Consumption Insights** -liitintä, mikä on jo kuvattu yksityiskohtaisesti tässä artikkelissa. Valitse tässä vaiheessa **Power BI Desktopin** **Aloitus**-valintanauhasta **Nouda tiedot > Tyhjä kysely**.

### <a name="step-2-create-a-query-in-advanced-editor"></a>Vaihe 2: Luo kysely laajennetun editorin avulla
Valitse **kyselyeditorin** **Aloitus**-valintanauhan **Kysely**-osasta **Laajennettu editori**. Syötä avautuvaan **Laajennettu editori** -ikkunaan seuraava kysely:

    let    
        enrollmentNumber = "100",
        optionalParameters = [ numberOfMonth = 6, dataType="DetailCharges" ],
        data = MicrosoftAzureConsumptionInsights.Contents(enrollmentNumber, optionalParameters)   
    in     
        data

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_10.png)

Sinun on korvattava *enrollmentNumber*-arvo omalla rekisteröintinumerollasi. Löydät numerosi [Azure Enterprise -portaalista](https://ea.azure.com). Parametri *numberOfMonth* tarkoittaa, kuinka monen kuukauden tiedot nykyisestä päivämäärästä taaksepäin haluat. Käytä nykyisestä kuukaudesta arvoa nolla (0).

Kun valitset **Laajennettu editori** -ikkunan **Valmis**-painikkeen, esikatselu päivittyy ja näet taulukossa tiedot määrittämältäsi kuukausiväliltä. Valitse **Sulje ja ota käyttöön** ja palaa.

### <a name="step-3-move-measures-and-custom-columns-to-the-new-report"></a>Vaihe 3: Siirrä mittarit ja mukautetut sarakkeet uuteen raporttiin
Seuraavaksi on siirrettävä luomasi mukautetut sarakkeet tai mittarit uuteen tietotaulukkoon. Vaiheet ovat seuraavat:

1. Avaa Muistio (tai muu tekstieditori).
2. Valitse mittari, jonka haluat siirtää, kopioi teksti *Kaava*-kentästä ja lisää se Muistioon.

   ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_11.png)
3. Muuta *Kysely1*:n nimeksi alkuperäisen tietotaulukon nimi.
4. Jos haluat luoda uusia taulukkomittareita ja mukautettuja sarakkeita, napsauta taulukkoa hiiren kakkospainikkeella ja valitse **Uusi mittari**. Leikkaa ja liitä tallennetut mittarit ja sarakkeet, kunnes kaikki on siirretty.

### <a name="step-4-relink-tables-that-had-relationships"></a>Vaihe 4: Linkitä uudelleen suhteita sisältäneet taulukot
Monissa koontinäytöissä on lisäksi taulukoita, joita käytetään hakuun tai suodatukseen, kuten päivämäärätaulukoita tai mukautettuihin projekteihin käytettyjä taulukoita. Näiden suhteiden muodostaminen uudelleen ratkaisee useimmat jäljellä olevat ongelmat. Näin voit tehdä sen.

- Valitse **Power BI Desktopin** **Mallinnus**-välilehdeltä **Suhteiden hallinta**, jolloin näyttöön avautuu ikkuna, jossa voit hallita mallin sisältämiä suhteita. Linkitä taulukot uudelleen tarpeen mukaan.

    ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_12.png)

### <a name="step-5-verify-your-visuals-and-adjust-field-formatting-as-needed"></a>Vaihe 5: Tarkista visualisoinnit ja säädä kentän muotoilua tarpeen mukaan
Tässä vaiheessa alkuperäisten visualisointiesi, taulukoiden ja yli- ja alirakenteiden pitäisi pääasiassa toimia odotetusti. Vähäinen hienosäätö saattaa kuitenkin olla tarpeen ulkoasun ja tuntuman viimeistelyssä. Silmäile kaikki koontinäytöt ja visualisoinnit läpi varmistaaksesi, että ne näyttävät siltä kuin haluat.

## <a name="using-the-azure-consumption-and-insights-aci-api-to-get-consumption-data"></a>Azure Consumption and Insights (ACI) -ohjelmointirajapinnan käyttö kulutustietojen saamiseen
Azure tarjoaa myös [**Azure Consumption and Insights (ACI) -ohjelmointirajapinnan**](https://azure.microsoft.com/blog/announcing-general-availability-of-consumption-and-charge-apis-for-enterprise-azure-customers/). Voit luoda omia mukautettuja ratkaisuja ja kerätä, raportoida ja visualisoida Azuren kulutustietoja ACI-ohjelmointirajapinnan avulla.

### <a name="mapping-names-and-usage-details-between-the-portal-the-connector-and-the-api"></a>Nimien ja käyttötietojen vastaavuudet portaalin, liittimen ja ohjelmointirajapinnan välillä
Azure-portaalin sarakkeet ja tietojen nimet ovat vastaavat ohjelmointirajapinnassa ja liittimessä, mutta ne eivät aina ole identtisiä. Seuraavassa taulukossa on yhteenveto, joka helpottaa tietojen selvittämistä. Taulukko kertoo myös, onko sarake vanhentunut. Lisätiedot ja termien määritelmät ovat [Azure-laskutuksen tietohakemistossa](https://docs.microsoft.com/azure/billing/billing-enterprise-api-usage-detail).

| ACI-liittimen / sisältöpaketin sarakkeen nimi | ACI-ohjelmointirajapinnan sarakkeen nimi | EA-sarakkeen nimi | Vanhentunut / käytössä yhteensopivuuden vuoksi aiempien versioiden kanssa |
| --- | --- | --- | --- |
| AccountName |accountName |Tilin nimi |Ei |
| AccountId |accountId | |Kyllä |
| AcccountOwnerId |accountOwnerEmail |AccountOwnerId |Ei |
| AdditionalInfo |additionalInfo |AdditionalInfo |Ei |
| AdditionalInfold | | |Kyllä |
| Consumed Quantity |consumedQuantity |Consumed Quantity |Ei |
| Consumed Service |consumedService |Consumed Service |Ei |
| ConsumedServiceId |consumedServiceId | |Kyllä |
| Cost |cost |ExtendedCost |Ei |
| Cost Center |costCenter |Cost Center |Ei |
| Date |date |Date |Ei |
| Päivä | |Päivä |Ei |
| DepartmentName |departmentName |Department Name |Ei |
| DepartmentID |departmentId | |Kyllä |
| Instance ID | | |Kyllä |
| InstanceId |instanceId |Instance ID |Ei |
| Location | | |Kyllä |
| Meter Category |meterCategory |Meter Category |Ei |
| Meter ID | | |Kyllä |
| Meter Name |meterName |Meter Name |Ei |
| Meter Region |meterRegion |Meter Region |Ei |
| Meter Sub-Category |meterSubCategory |Meter Sub-Category |Ei |
| MeterId |meterId |Meter ID |Ei |
| Kuukausi | |Kuukausi |Ei |
| Product |product |Product |Ei |
| ProductId |productId | |Kyllä |
| Resource Group |resourceGroup |Resource Group |Ei |
| Resource Location |resourceLocation |Resource Location |Ei |
| ResourceGroupId | | |Kyllä |
| ResourceLocationId |resourceLocationId | |Kyllä |
| ResourceRate |ResourceRate |ResourceRate |Ei |
| ServiceAdministratorId |serviceAdministratorId |ServiceAdministratorId |Ei |
| ServiceInfo1 |serviceInfo1 |ServiceInfo1 |Ei |
| ServiceInfo1Id | | |Kyllä |
| ServiceInfo2 |serviceInfo2 |ServiceInfo2 |Ei |
| ServiceInfo2Id | | |Kyllä |
| Store Service Identifier |storeServiceIdentifier |Store Service Identifier |Ei |
| StoreServiceIdentifierId | | |Kyllä |
| Subscription Name |subscriptionName |Subscription Name |Ei |
| Tags |tags |Tags |Ei |
| TagsId | | |Kyllä |
| Mittayksikkö |unitOfMeasure |Mittayksikkö |Ei |
| Vuosi | |Vuosi |Ei |
| SubscriptionId |subscriptionId |SubscriptionId |Kyllä |
| SubscriptionGuid |subscriptionGuid |SubscriptionGuid |Ei |

## <a name="connect-with-azure-cost-management"></a>Yhdistäminen Azure Cost Managementin avulla

Tässä osiossa opit muodostamaan yhteyden asiakassopimusten laskutustiliin.

> [!NOTE]
> Azure Cost Management -liitin tukee tällä hetkellä **asiakassopimusten** asiakkaita.  **Enterprise Agreement** -sopimusten käyttäjien tulee käyttää Microsoft Azure Consumption Insights -liitintä.
>
>

**Azure Cost Management** -liittimen käyttäminen **Power BI Desktopissa**:

1. Valitse **Aloitus**-valintanauhasta **Nouda tiedot**.

1. Valitse vasemmalla näkyvistä luokista **Azure**.

1. Valitse oikealta **Azure Cost Management (beeta)** .

1. Valitse **Muodosta yhteys**.


   ![](media/desktop-connect-azure-consumption-insights/azure-cost-management-00.png)

   Kirjoita avautuvaan valintaikkunaan oman **laskutusprofiilisi tunnus**.

   ![](media/desktop-connect-azure-consumption-insights/azure-cost-management-01.png)

Voit hakea tunnuksen [Azure-portaalista](https://portal.azure.com):

1. Siirry kohtaan **Cost Management ja laskutus**.

1. Valitse laskutustilisi.

1. Valitse sivupalkista **Laskutusprofiilit**.

1. Valitse laskutusprofiilisi.

1. Valitse sivupalkista **Ominaisuudet**.

1. Kopioi laskutusprofiilin tunnus.

   ![](media/desktop-connect-azure-consumption-insights/azure-cost-management-02.png)

   Sinua pyydetään kirjautumaan sisään Azure-sähköpostiosoitteella ja -salasanalla.  Kun olet kirjautunut, näet **Navigator**-ikkunan, jossa on 12 taulukkoa:

| Taulukko        | Kuvaus |
|-------------------- | -------------------------------------------------------------|
| **Laskutustapahtumat** | Uusien laskujen, hyvitysostojen ja muiden tietojen tapahtumaloki. |
| **Budjetit** | Budjettitiedot todellisten kustannusten tai käytön tarkastelemiseksi olemassa oleviin budjettitavoitteisiin verrattuna. |
| **Veloitukset** | Yhteenveto Azuren käytöstä kuukausittain, markkinamaksuista ja erikseen laskutetuista veloituksista. |
| **Hyvitysostot** | Tieto kyseisen laskutusprofiilin Azure-hyvitysten ostotiedoista. |
| **Hyvitysten yhteenveto** | Yhteenveto kyseisen laskutusprofiilin hyvityksistä. |
| **Marketplace** | Käyttöön perustuvat Azure Marketplace -maksut. |
| **Hintataulukot** | Valittua laskutusprofiilia koskevat hintatiedot. |
| **Varattujen esiintymien veloitukset** | Varattuihin esiintymiin liittyvät maksut viimeisten 24 kuukauden ajalta. |
| **Varattujen esiintymien suositukset (yksi)** | Varatun esiintymän ostosuositukset yhdessä tilauksessa käyttötrendien perusteella viimeisten 7, 30 tai 60 päivän ajalta. |
| **Varattujen esiintymien suositukset (jaetut)** | Varatun esiintymän ostosuositukset kaikissa tilauksissa käyttötrendien perusteella viimeisten 7, 30 tai 60 päivän ajalta. |
| **Varattujen esiintymien käyttö** | Varattujen esiintymien kulutustiedot viimeisen kuukauden ajalta. |
| **Käyttötiedot** | Erittely valittua laskutusprofiilin tunnusta koskevista kulutetuista määristä ja arvioidut maksut. |

Voit avata esikatselun valitsemalla taulukon vieressä olevan valintaruudun.  Voit valita yhden tai useamman taulukon valitsemalla taulukon nimen vieressä olevan ruudun ja sen jälkeen **Lataa**.

![](media/desktop-connect-azure-consumption-insights/azure-cost-management-03.png)

Kun valitset **Lataa**, tiedot ladataan **Power BI Desktopiin**.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_05.png)

Kun valitsemasi tiedot on ladattu, valitsemasi taulukot ja kentät näkyvät **Kentät**-ruudussa.

![](media/desktop-connect-azure-consumption-insights/azure-cost-management-05.png)

Katso video [kulujen analysoinnista Power BI:ssä Azure Consumption Insightsin avulla](https://www.youtube.com/watch?v=QKBMXXrlpEk). Video sisältää lisätietoja kustannustietojen tarkastelusta Power BI Desktopissa Azure Consumption Insights -liittimen avulla.

## <a name="writing-custom-queries"></a>Mukautettujen kyselyjen kirjoittaminen

Voit luoda mukautetun [M-kyselyn](/powerquery-m/power-query-m-reference), jos haluat mukauttaa kuukausien määrää, muuttaa ohjelmointirajapinnan versiota tai käyttää palautetuissa tiedoissa edistynyttä logiikkaa.

**Power BI Desktopissa**:

1. Valitse **Aloitus**-valintanauha
2. Valitse **Nouda tiedot** > **Tyhjä kysely**

Tai **kyselyeditorissa**:

1. Napsauta hiiren kakkospainikkeella vasemmanpuoleista **Kyselyt**-ruutua
2. Valitse avautuvasta valikosta **Uusi kysely > Tyhjä valikko**

Kirjoita **Kaavariviin** seuraava haku, ja korvaa `billingProfileId` omalla tunnuksellasi sekä ”veloitukset” minkä tahansa kelvollisen taulukon nimellä (luettelo yllä).

```
let
    Source = AzureCostManagement.Tables(billingProfileId, [ numberOfMonths = 3 ]),
    charges = Source{[Key="charges"]}[Data]
in
    charges
```

Voit muokata `numberOfMonths`-arvoksi minkä tahansa arvon välillä 1–36, ja lisäksi voit myös antaa:

* `apiVersion`, jos haluat mukauttaa sitä, minkä ohjelmointirajapinnan version kysely kutsuu.
* `lookbackWindow`, jos haluat käyttää RI-suosituksia (yksittäisiä tai jaettuja) ja muokata aikaväliä, johon suositukset perustuva (kelvolliset vaihtoehdot: 7, 30 ja 60 päivää).

## <a name="next-steps"></a>Seuraavat vaiheet

Voit muodostaa yhteyden moniin eri tietolähteisiin Power BI Desktopissa. Katso lisätietoja seuraavista artikkeleista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   
