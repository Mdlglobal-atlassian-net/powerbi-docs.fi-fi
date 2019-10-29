---
title: Azure Cost Management -tietoihin yhdistäminen Power BI Desktopissa
description: Voit yhdistää helposti Azureen ja saada merkityksellisiä tietoja kustannusten hallinnasta Power BI Desktopin avulla
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/14/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1ef9deac169873d7faee33abdae9f8f38aa09c6d
ms.sourcegitcommit: 549401b0e1fad15c3603fe7f14b9494141fbb100
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/14/2019
ms.locfileid: "72308003"
---
# <a name="connect-to-azure-cost-management-data-in-power-bi-desktop"></a>Azure Cost Management -tietoihin yhdistäminen Power BI Desktopissa

Power BI Desktopin Azure Cost Management -liittimellä voit luoda tehokkaita mukautettuja visualisointeja ja raportteja, joilla ymmärrät paremmin Azure-kulujasi. Azure Cost Management -liitin tukee tällä hetkellä asiakkaita, joilla on [Microsoft Customer Agreement](https://azure.microsoft.com/pricing/purchase-options/microsoft-customer-agreement/)- tai [Enterprise Agreement (EA)](https://azure.microsoft.com/pricing/enterprise-agreement/) -sopimus.  

Azure Cost Management -liitin todennetaan Azureen OAuth 2.0:lla. Jos haluat muodostaa yhteyden, sinun täytyy käyttää [yrityksen järjestelmänvalvojan](https://docs.microsoft.com/azure/billing/billing-understand-ea-roles) tiliä (Enterprise Agreement -asiakkaat) tai [laskutustilin omistajan](https://docs.microsoft.com/azure/billing/billing-understand-mca-roles) tiliä (Microsoft Customer Agreement -asiakkaat). 

> [!NOTE]
> Tämä liitin korvaa aiemmin käytössä olleen [Azure Cost Management (beeta)](desktop-connect-azure-consumption-insights.md) liittimen. Kaikki aiemmalla liittimellä luodut raportit täytyy luoda uudelleen tällä liittimellä.

## <a name="connect-using-azure-cost-management"></a>Yhdistäminen Azure Cost Managementin avulla

Jos haluat käyttää **Azure Cost Management -liitintä** Power BI Desktopissa, toimi seuraavasti:

1.  Valitse **Aloitus**-valintanauhasta **Nouda tiedot**.
2.  Valitse tietoluokkaluettelosta **Azure**.
3.  Valitse **Azure Cost Management**.

    ![Nouda tiedot](media/desktop-connect-azure-cost-management/azure-cost-management-00b.png)

4. Anna näyttöön avautuvassa valintaikkunassa **laskutusprofiilin tunnus** (**Microsoft Customer Agreement -asiakkaat**) tai **rekisteröitymisnumero** (**Enterprise Agreement -asiakkaat**). 


## <a name="connect-to-a-microsoft-customer-agreement-account"></a>Microsoft Customer Agreement -tiliin yhdistäminen 

Jos haluat yhdistää **Microsoft Customer Agreement** -tilillä, voit hakea **laskutusprofiilin tunnuksen** Azure-portaalista:

1.  Siirry [Azure-portaalissa](https://portal.azure.com/) **kustannusten hallinnan ja laskutuksen kohtaan**.
2.  Valitse laskutusprofiilisi. 
3.  Valitse valikosta **Asetukset** ja sivupalkista **Ominaisuudet**.
4.  Kopioi **laskutusprofiilin** **tunnus**. 
5.  Siirry **Valitse vaikutusalue** -kohtaan, valitse **Laskutusprofiilin tunnus** ja liitä siihen edellisessä vaiheessa kopioimasi profiilin tunnus. 
6.  Anna kuukausien määrä ja valitse **OK**.

    ![Laskutustunnuksen hakeminen](media/desktop-connect-azure-cost-management/azure-cost-management-01a.png)

7.  Kirjaudu pyydettäessä sisään Azure-käyttäjätilillä ja -salasanalla. 


## <a name="connect-to-an-enterprise-agreement-account"></a>Enterprise Agreement -tiliin yhdistäminen

Jos haluat yhdistää Enterprise Agreement (EA) -tilillä, voit hakea rekisteröitymistunnuksen Azure-portaalista:

1.  Siirry [Azure-portaalissa](https://portal.azure.com/) **kustannusten hallinnan ja laskutuksen kohtaan**.
2.  Valitse laskutustilisi.
3.  Kopioi **Yleiskatsaus**-valikosta **laskutustilin tunnus**.
4.  Siirry **Valitse vaikutusalue** -kohtaan, valitse **Rekisteröitymisnumero** ja liitä siihen edellisessä vaiheessa kopioimasi laskutustilin tunnus. 
5.  Anna kuukausien määrä ja valitse sitten **OK**.

    ![Laskutustunnuksen hakeminen](media/desktop-connect-azure-cost-management/azure-cost-management-01b.png)

6.  Kirjaudu pyydettäessä sisään Azure-käyttäjätilillä ja -salasanalla. 

## <a name="data-available-through-the-connector"></a>Liittimen avulla saatavilla olevat tiedot

Kun todennus onnistuu, näyttöön avautuu **siirtymistoiminnon** ikkuna, joka sisältää seuraavat käytettävissä olevat tietotaulukot:



| **Taulukko** | **Kuvaus** |
| --- | --- |
| **Taseen yhteenveto** | Tämä on Enterprise Agreement (EA) -sopimusten taseen yhteenveto. |
| **Laskutustapahtumat** | Tämä on uusien laskujen, hyvitysostojen ja muiden vastaavien tapahtumaloki. Tämä on saatavilla vain Microsoft Customer Agreement -asiakkaille. |
| **Budjetit** | Budjettitiedot todellisten kustannusten tai käytön tarkastelemiseksi olemassa oleviin budjettitavoitteisiin verrattuna. |
| **Veloitukset** | Tämä on yhteenveto Azuren käytöstä kuukausittain, markkinamaksuista ja erikseen laskutetuista veloituksista. Tämä on saatavilla vain Microsoft Customer Agreement -asiakkaille. |
| **Hyvitysostot** | Tieto kyseisen laskutusprofiilin Azure-hyvitysten ostotiedoista. Tämä on saatavilla vain Microsoft Customer Agreement -asiakkaille. |
| **Hintataulukot** | Nämä ovat valittua laskutusprofiilia tai EA-rekisteröitymistä koskevat hintatiedot. |
| **Varattujen esiintymien veloitukset** | Varattuihin esiintymiin liittyvät maksut viimeisten 24 kuukauden ajalta. |
| **Varattujen esiintymien suositukset (jaetut)** | Varatun esiintymän ostosuositukset kaikissa tilauksissa käyttötrendien perusteella viimeisten 7, 30 tai 60 päivän ajalta. |
| **Varattujen esiintymien suositukset (yksi)** | Varatun esiintymän ostosuositukset yhdessä tilauksessa käyttötrendien perusteella viimeisten 7, 30 tai 60 päivän ajalta. |
| **RI-käyttötiedot** | Varattujen esiintymien kulutustiedot viimeisen kuukauden ajalta. |
| **RI-käyttöyhteenveto** | Tämä on päivittäinen Azure-varausten käyttö prosentteina. |
| **Käyttötiedot** | Tämä on erittely valittua EA-rekisteröitymisen laskutusprofiilin tunnusta koskevista kulutetuista määristä ja arvioidut maksut. |
| **Kuoletetut käyttötiedot** | Tämä on erittely valittua EA-rekisteröitymisen laskutusprofiilin tunnusta koskevista kulutetuista määristä ja arvioidut kuoletetut maksut. |

Voit avata esikatseluvalintaikkuna valitsemalla taulukon. Voit valita yhden tai useamman taulukon valitsemalla taulukon nimen vieressä olevan ruudun ja valitsemalla sitten **Lataa**.

![Laskutustunnuksen hakeminen](media/desktop-connect-azure-cost-management/azure-cost-management-01c.png)

Kun valitset **Lataa**, tiedot ladataan Power BI Desktopiin. 

Kun valitsemasi tiedot on ladattu, valitsemasi taulukot ja kentät näytetään **Kentät**-ruudussa.


## <a name="next-steps"></a>Seuraavat vaiheet

Voit muodostaa yhteyden moniin eri tietolähteisiin Power BI Desktopissa. Katso lisätietoja seuraavista artikkeleista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   