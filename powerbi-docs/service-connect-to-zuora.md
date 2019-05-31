---
title: Yhteyden muodostaminen Zuoraan Power BI:llä
description: Zuora for Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/24/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 605cd2f135ff6d8626586abbd503bcb44687931d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61156924"
---
# <a name="connect-to-zuora-with-power-bi"></a>Yhteyden muodostaminen Zuoraan Power BI:llä
Zuora for Power BI:n avulla voit visualisoida tärkeät tuotto-, laskutus- ja tilaustiedot. Käytä oletusraporttinäkymiä ja -raportteja käyttötrendien analysointiin, laskutuksen ja maksujen seurantaan sekä toistuvan tuoton valvontaan, tai mukauta niitä omien raporttinäkymä- ja raportointitarpeidesi mukaan.

Yhteyden muodostaminen [Zuora](https://app.powerbi.com/getdata/services/Zuora) for Power BI:hin.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.

   ![](media/service-connect-to-zuora/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.

   ![](media/service-connect-to-zuora/services.png)
3. Valitse **Zuora** \>  **Nouda**.

   ![](media/service-connect-to-zuora/zuora.png)
4. Määritä Zuoran URL-osoite. URL on tavallisesti <https://www.zuora.com>. Katso lisätiedot [näiden parametrien etsimisestä](#FindingParams) alta.

   ![](media/service-connect-to-zuora/params.png)
5. Valitse **Todennusmenetelmä**-kohdassa **Perus** ja anna käyttäjänimesi ja salasanasi (kirjainkoolla on merkitystä), ja valitse sitten **Kirjaudu sisään**.

    ![](media/service-connect-to-zuora/creds.png)
6. Hyväksymisen jälkeen tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.

     ![](media/service-connect-to-zuora/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Sisältöpaketti käyttää Zuora AQUA -ohjelmointirajapintaa seuraavien taulukoiden noutamiseksi:

| Taulukot |  |  |
| --- | --- | --- |
| Tili |InvoiceItemAdjustment |Hyvitys |
| AccountingCode |Maksu |RevenueSchedule |
| AccountingPeriod |PaymentMethod |RevenueScheduleItem |
| BillTo |Tuote |Tilaus |
| DateDim |ProductRatePlan |TaxationItem |
| Lasku |ProductRatePlanCharge |Käyttö |
| InvoiceAdjustment |RatePlan | |
| InvoiceItem |RatePlanCharge | |

Se sisältää myös nämä lasketut mittarit:

| Mittari | Kuvaus | Pseudo-laskenta |
| --- | --- | --- |
| Tili: maksut |Kokonaismaksusummat tietyllä ajanjaksolla maksun voimaantulopäivän mukaan. |SUM (Payment.Amount) <br>WHERE<br>Payment.EffectiveDate =< TimePeriod.EndDate<br>AND    Payment.EffectiveDate >= TimePeriod.StartDate |
| Tili: Hyvitykset |Kokonaishyvityssummat tietyllä ajanjaksolla hyvityksen päivämäärän mukaan. Summa ilmoitetaan negatiivisena lukuna. |-1*SUM(Refund.Amount)<br>WHERE<br>Refund.RefundDate = < TimePeriod.EndDate<br>AND    Refund.RefundDate >= TimePeriod.StartDate |
| Tili: nettomaksut |Tilin maksut ja tilin hyvitykset ajanjaksolla. |Account.Payments + Account.Refunds |
| Tili: aktiiviset tilit |Niiden tilien määrä, jotka olivat aktiivisia ajanjaksolla. Tilaukset on oltava aloitettu viimeistään ajanjakson aloituspäivämääränä. |COUNT (Account.AccountNumber)<br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    (Subscription.SubscriptionEndDate > TimePeriod.StartDate<br>TAI<br>Subscription.SubscriptionEndDate = null) –evergreen subscription |
| Tili: keskimääräinen toistuva tuotto |Brutto-MRR aktiivista tiliä kohden ajanjaksolla. |Brutto-MRR / Account.ActiveAccounts |
| Tili: peruutetut tilaukset |Niiden tilien määrä, jotka ovat peruuttaneet tilauksen ajanjaksolla. |COUNT (Account.AccountNumber)<br>WHERE<br>Subscription.Status = "Cancelled"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    Subscription.CancelledDate >= TimePeriod.StartDate |
| Tili: maksuvirheet |Maksuvirheiden kokonaisarvo. |SUM (Payment.Amount)<br>WHERE<br>Payment.Status = "Error" |
| Tuoton ajoituskohde: tunnistettu tuotto |Tunnistettu kokonaistuotto laskentakaudella. |SUM (RevenueScheduleItem.Amount)<br>WHERE<br>AccountingPeriod.StartDate = TimePeriod.StartDate |
| Tilaus: uudet tilaukset |Uusien tilausten määrä ajanjaksolla. |COUNT (Subscription.ID)<br>WHERE<br>Subscription.Version = ”1”<br>AND    Subscription.CreatedDate <= TimePeriod.EndDate<br>AND    Subscription.CreatedDate >= TimePeriod.StartDate |
| Lasku: Laskun nimikkeet |Laskun kokonaisveloitussummat ajanjaksolla. |SUM (InvoiceItem.ChargeAmount)<br>WHERE<br>    Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Lasku: Verotusnimikkeet |Verotuskohteiden kokonaissummat ajanjaksolla. |SUM (TaxationItem.TaxAmount)<br>WHERE<br>Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Lasku: Laskun nimikkeiden muutokset |Laskun kohteiden kokonaismuutossummat ajanjaksolla. |SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceItemAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceItemAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Lasku: Laskun muutokset |Laskun kokonaismuutossummat ajanjaksolla. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Lasku: Nettolaskutus |Laskun kohteiden, verotuskohteiden, laskun kohteiden muutosten ja laskun muutosten summa ajanjaksolla. |Invoice.InvoiceItems + Invoice.TaxationItems + Invoice.InvoiceItemAdjustments + Invoice.InvoiceAdjustments |
| Lasku: laskun vanhentumissaldo |Kirjattujen laskun saldojen summa. |SUM (Invoice.Balance) <br>WHERE<br>    Invoice.Status = "Posted" |
| Lasku: bruttolaskutukset |Kirjattujen laskujen kohteiden veloitusten summa ajanjaksolla. |SUM (InvoiceItem.ChargeAmount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Lasku: kokonaismuutokset |Kirjattuihin laskuihin liittyvien käsiteltyjen laskumuutosten ja laskukohteiden muutosten summa. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceAdjustment.Status = "Processed"<br>+<br>SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    invoiceItemAdjustment.Status = "Processed" |
| Maksusuunnitelman veloitus: brutto-MRR |Tilausten kuukausittain toistuvan tuoton summa ajanjaksolla. |SUM (RatePlanCharge.MRR) <br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    RatePlanCharge.EffectiveStartDate <= TimePeriod.StartDate<br>AND        RatePlanCharge.EffectiveEndDate > TimePeriod.StartDate<br>    OR    RatePlanCharge.EffectiveEndDate = null --evergreen subscription |

## <a name="system-requirements"></a>Järjestelmävaatimukset
Yhteys Zuora-ohjelmointirajapintaan vaaditaan.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Anna URL-osoite, jota käytät yleensä Zuora-tietojen noutamiseen. Kelvolliset vaihtoehdot ovat:  

* https://www.zuora.com  
* Palveluesiintymääsi vastaava URL-osoite  

## <a name="troubleshooting"></a>Vianmääritys
Zuora-sisältöpaketti hakee tietoja Zuora-tilisi monilta eri osa-alueilta. Jos et käytä tiettyjä ominaisuuksia, jotkin ruudut/raportit voivat olla tyhjiä. Jos sinulla on ongelmia lataamisessa, ota yhteyttä Power BI -tukeen.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)
