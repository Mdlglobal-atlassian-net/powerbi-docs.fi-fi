---
title: Power BI Premium -kapasiteettien valvominen hallintaportaalissa
description: Power BI -hallintaportaalissa voit valvoa Premium-kapasiteettejasi.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2019
LocalizationGroup: Premium
ms.openlocfilehash: 59097c07719e4bb8db188e8a86db377076aea7a9
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794111"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Kapasiteettien valvonta hallintaportaalissa

Tässä artikkelissa kerrotaan, miten voit tarkistaa kapasiteettisi suorituskyvyn nopeasti hallintaportaalin kapasiteettiasetuksissa.  Jos haluat tarkempia tietoja kapasiteetistasi, sinun kannattaa käyttää [Power BI Premium -kapasiteettiarvo](service-admin-premium-monitor-capacity.md) -sovellusta.

## <a name="capacity-metrics"></a>Kapasiteettiarvot

Hallintaportaalin **Kapasiteettiasetukset**-alueella on neljä mittaria, jotka ilmoittavat kapasiteetin asettamat kuormitukset ja käyttämät resurssit viimeisten seitsemän päivän ajalta. Nämä neljä ruutua toimivat tuntikohtaisessa aikaikkunassa, joka ilmaisee, kuinka monta tuntia vastaava mittausarvo oli yli 80 prosenttia viimeisten seitsemän päivän aikana. Tämä mittausarvo ilmaisee mahdollisen käyttäjäkokemuksen heikkenemisen.

![Käyttö 7 päivän aikana](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Suoritin |Kuinka monta kertaa suoritin ylitti 80 prosentin käyttöasteen. |
| Muistin tietojen poistaminen |Kuvastaa taustatoimintojen ydinten muistin vähyyttä. Tarkemmin sanottuna tämä ilmaisee, kuinka monta kertaa tietojoukkoja poistetaan muistista useiden tietojoukkojen aiheuttaman muistin vähäisyyden vuoksi. |
| Muistin käyttö |Keskimääräinen muistin käyttö gigatavuina (Gt). |
| DQ-kyselyjä/s | Kuinka monta kertaa DirectQueryn ja reaaliaikaisten yhteyksien määrä ylitti 80 prosenttia rajoituksesta. <br>  DirectQuery-yhteyden ja reaaliaikaisen yhteyden kyselyiden sekuntikohtainen kokonaismäärä on rajoitettu. Rajoitukset ovat 30/s P1:llä, 60/s P2:lla ja 120/s P3:lla.  DirectQuery-kyselyiden ja reaaliaikaisen yhteyden kyselyiden määrä lasketaan kiintiöön. Jos sinulla on käynnissä esimerkiksi 15 DirectQuery-kyselyä ja 15 reaaliaikaista yhteyttä samalla sekunnilla, nopeutta rajoitetaan.<br> Tämä koskee niin paikallisia kuin pilviyhteyksiäkin. |
|  |  |

Mittarit kuvaavat käyttöä viime viikon aikana.  Jos haluat tarkastella mittareita tarkemmin, voit tehdä niin napsauttamalla jotakin yhteenvetoruutua.  Sen jälkeen näet yksityiskohtaiset kaaviot Premium-kapasiteetin mittareista. Seuraavassa kaaviossa näkyvät suorittimen mittausarvon tiedot.

![Suorittimen yksityiskohtainen käyttökaavio](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

Näissä kaavioissa on tuntikohtainen yhteenveto viime viikolta ja ne voivat auttaa selvittämään, jos Premium-kapasiteetissasi on ollut jokin suorituskykyyn liittyvä tapahtuma.

Voit myös viedä minkä tahansa mittarin pohjana olevat tiedot csv-tiedostoon.  Tämän viennin ansiosta saat yksityiskohtaista tietoa kolmen minuutin välein viime viikon kultakin päivältä.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun tiedät, miten voit valvoa Power BI Premium -kapasiteetteja, lue lisätietoja kapasiteettien optimoinnista.

> [!div class="nextstepaction"]
> [Power BI Premium -kapasiteetin resurssien hallinta ja optimointi](service-premium-understand-how-it-works.md)
