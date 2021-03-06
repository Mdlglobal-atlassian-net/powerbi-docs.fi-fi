---
title: OData-syötteeseen yhdistäminen Power BI Desktopissa
description: OData-syötteeseen yhdistäminen ja sen käyttäminen helposti Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6797aa994aeaaec450155f4e442b2f6bd112f018
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83347719"
---
# <a name="connect-to-odata-feeds-in-power-bi-desktop"></a>OData-syötteisiin yhdistäminen Power BI Desktopissa
Power BI Desktopissa voi muodostaa yhteyden **OData-syötteeseen** ja käyttää sen tietoja samaan tapaan kuin muita tietolähteitä käytetään Power BI Desktopissa.

Jos haluat muodostaa yhteyden OData-syötteeseen, valitse **Nouda tiedot > OData-syöte** Power BI Desktopin**Aloitus**-valintanauhasta.

![](media/desktop-connect-odata/connect-to-odata_1.png)

Näyttöön tulevassa **OData-syöte**-ikkunassa kirjoita tai liitä OData-syötteen URL-osoite ruutuun ja valitse **OK**.

![](media/desktop-connect-odata/connect-to-odata_2.png)

Power BI Desktop muodostaa yhteyden OData-syötteeseen ja näyttää käytettävissä olevat taulukot ja muut tietoelementit **Siirtymistoiminto**-ikkunassa. Kun valitset elementin, **Siirtymistoiminto**-ikkunan oikeanpuoleisessa ruudussa näkyy tietojen esikatselu. Voit valita tuontia varten niin monta taulukkoa kuin haluat. **Siirtymistoiminto**-ikkuna näyttää valittuna olevan taulukon esikatselunäkymän.

![](media/desktop-connect-odata/connect-to-odata_3.png)

**Muokkaa**-painikkeen valitseminen käynnistää **Kyselyeditorin**, jossa voit muotoilla ja muuntaa ODatan tietoja ennen niiden tuomista Power BI Desktopiin. Voit vaihtoehtoisesti valita **Lataa**-painikkeen ja tuoda kaikki vasemmassa ruudussa valitsemasi tietoelementit.

Kun **Lataa** valitaan, Power BI Desktop tuo valitut kohteet ja näyttää tuonnin edistymisen **Lataa**-ikkunan.

![](media/desktop-connect-odata/connect-to-odata_4.png)

Kun toiminto on valmis, Power BI Desktop tuo valitut taulukot ja muut tietoelementit käytettäviksi **Kentät**-ruudussa, joka näkyy Power BI Desktopin *Raportit*-näkymän oikeassa reunassa.

![](media/desktop-connect-odata/connect-to-odata_5.png)

Siinä kaikki!

Olet nyt valmis käyttämään OData-syötteestä tuotuja tietoja Power BI Desktopissa visualisointien tai raporttien luomiseen tai vuorovaikutukseen muiden tietojen kanssa, joihin ehkä haluat olla yhteydessä ja joita tuot, kuten Excel-työkirjat, tietokannat tai muut tietolähteet.

## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Mikä on Power BI Desktop?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   
