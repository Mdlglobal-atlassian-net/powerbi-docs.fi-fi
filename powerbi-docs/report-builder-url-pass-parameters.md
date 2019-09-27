---
title: Raporttiparametrin välittäminen URL-osoitteessa sivutetuissa raporteissa – Power BI:n raportin muodostin
description: Tässä ohjeaiheessa kerrotaan, miten raporttiparametrit välitetään raporttiin sisällyttämällä ne sivutetun raportin URL-osoitteeseen.
ms.service: powerbi
ms.subservice: report-builder
ms.custom: ''
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.date: 08/29/2019
ms.openlocfilehash: f7f1b777e7c4e54dbdcfb1757fe4df274624a580
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/17/2019
ms.locfileid: "71075993"
---
# <a name="pass-a-report-parameter-in-a-url-for-a-paginated-report-in-power-bi"></a>Raporttiparametrin välittäminen URL-osoitteessa Power BI:n sivutetuissa raporteissa 

Raporttiparametrit voi välittää raporttiin sisällyttämällä ne sivutetun raportin URL-osoitteeseen. Kaikilla kyselyparametreilla voi olla vastaavat raporttiparametrit. Näin ollen kyselyparametri välitetään raporttiin välittämällä vastaava raporttiparametri. Sinun on lisättävä parametrin nimeen`rp:` -etuliite, jotta Power BI tunnistaa sen URL-osoitteessa. 

Raporttiparametrien kirjainkoko on merkitsevä, ja niissä käytetään seuraavia erikoismerkkejä: 

- URL-osoitteen parametriosan välilyönti korvataan plusmerkillä (+).  Esimerkki: 

    ```rp:Holiday=Christmas+Day```

- Merkkijonon minkä tahansa osan puolipiste korvataan merkeillä `%3A`.

Selaimet suorittavat automaattisesti asianmukaisen URL-koodauksen. Sinun ei tarvitse koodata mitään merkkejä manuaalisesti. 

Jos haluat määrittää raporttiparametrin URL-osoitteeseen, käytä seuraavaa syntaksia: 

```
rp:parameter=value
```

Jos haluat esimerkiksi määrittää kaksi parametria, ”myyjä” ja ”osavaltio”, jotka on määritetty omassa työtilassa olevassa raportissa, käytä seuraavaa URL-osoitetta: 

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:Salesperson=Tie+Bear&rp:State=Utah 
```

Jos haluat määrittää samat kaksi parametria, jotka on määritetty sovelluksessa olevassa raportissa, käytä seuraavaa URL-osoitetta: 

```
https://app.powerbi.com/groups/me/apps/xxxxxxx-c4c4-4217-afd9-3920a0d1e2b0/rdlreports/b1d5e659-639e-41d0-b733-05d2bca9853c?rp:Salesperson=Tiggee&State=Utah 
```

Jos haluat välittää tyhjäarvon parametrille, käytä seuraavaa syntaksia: 

```
parameter:isnull=true
```

Esimerkki:

```
rp:SalesOrderNumber:isnull=true
```

Jos haluat välittää totuusarvon, määritä epätosi-arvoksi 0 ja tosi-arvoksi 1. Jos haluat välittää liukulukuarvon, lisää palvelimen aluekohtaisten asetusten desimaalierotin.

> [!NOTE]
> Jos raporttisi sisältää raporttiparametrin, jolla on oletusarvo, ja **Kehote**-ominaisuuden arvo on **epätosi** (eli **Kehote käyttäjälle** -ominaisuutta ei ole valittu Report Managerissa), et voi välittää kyseisen raporttiparametrin arvoa URL-osoitteeseen. Tämän ansiosta järjestelmänvalvojat voivat estää loppukäyttäjiä lisäämästä tai muokkaamasta tiettyjen raporttiparametrien arvoja.

## <a name="additional-examples"></a>Muita esimerkkejä 

Seuraava esimerkki-URL-osoite sisältää moniarvoisen parametrin ”myyjä”. Moniarvoinen parametri toistaa parametrin nimen kunkin arvon kohdalla. 

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:Salesperson=Tie+Bear&rp:Salesperson=Mickey 
```

Seuraava esimerkki-URL-osoite välittää yhden SellStartDate-parametrin, jonka arvo on ”7/1/2005”, alkuperäistilassa olevalle raporttipalvelimelle.

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:SellStartDate=7/1/2005
```

## <a name="next-steps"></a>Seuraavat vaiheet

- [URL-parametrit Power BI:n sivutetuissa raporteissa](report-builder-url-parameters.md)
- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
