---
title: Kapasiteetti ja SKU Power BI:n upotetussa analytiikassa
description: Tutustu kapasiteettiin ja SKU:hun Power BI:n upotetussa analytiikassa.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/11/2020
ms.openlocfilehash: f8c3bdf3e3f92d570205551a97389def2921fe98
ms.sourcegitcommit: 17aad73762579d6822383b27b96b1b63f87f2d6f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/14/2020
ms.locfileid: "77260453"
---
# <a name="capacity-and-skus-in-power-bi-embedded-analytics"></a>Kapasiteetti ja SKU Power BI:n upotetussa analytiikassa

Siirryttäessä tuotantoon Power BI:n upotettu analytiikka edellyttää varattua kapasiteettia(*A*, *EM* tai *P* SKU) upotetun Power BI -sisällön julkaisemista varten.

Kapasiteetti on yksinomaiseen käyttöön varattujen resurssien joukko. Sen avulla voit julkaista koontinäyttöjä, raportteja ja tietojoukkoja käyttäjille ilman, että sinun tarvitsee ostaa käyttäjäkohtaisia käyttöoikeuksia. Se tarjoaa myös sisällön luotettavan, tasalaatuisen suorituskyvyn.

>[!NOTE]
>Julkaisua varten tarvitset yhden Power BI Pro -tilin.

## <a name="what-is-embedded-analytics"></a>Mitä on upotettu analytiikka?

Power BI:n upotettu analytiikka sisältää kaksi ratkaisua:
* *Power BI Embedded* – Azure-tarjous
* Power BI:n upottaminen osana *Power BI Premiumia* – Office-tarjous

### <a name="power-bi-embedded"></a>Power BI Embedded

Power BI Embedded on tarkoitettu ISV-kumppaneille ja kehittäjille, jotka haluavat upottaa visualisointeja sovelluksiinsa.

Power BI Embeddediä käyttävien sovellusten avulla käyttäjät voivat käyttää Power BI Embedded -kapasiteettiin tallennettua sisältöä.

### <a name="power-bi-premium"></a>Power BI Premium

[Power BI Premium](../service-premium-what-is.md) on optimoitu yrityksille, jotka haluavat täydellisen BI-ratkaisun, joka mahdollistaa organisaation, kumppanien, asiakkaiden ja toimittajien tietojen tarkastelun yhdessä näkymässä.

Power BI Premium on SaaS-tuote, jonka käyttäjät voivat käyttää sisältöä mobiilisovellusten, sisäisesti kehitettyjen sovellusten tai Power BI -portaalin kautta (Power BI -palvelu). Tämän avulla Power BI Premium voi tarjota ratkaisun sekä sisäisille että ulkoisille asiakkaille tarkoitettuihin sovelluksiin.

## <a name="capacity-and-skus"></a>Kapasiteetti ja SKU

Jokainen kapasiteetti tarjoaa SKU-valikoiman ja kukin SKU tarjoaa eri resurssitasoja muistia ja laskentatehoa varten. Tarvitsemasi SKU-tyyppi riippuu siitä, minkä ratkaisun haluat ottaa käyttöön.

Ennen kuin päätät, minkä SKU:n haluat ostaa, tutustu tämän osion tietoihin.
* Jos haluat tietää, mitä kuormituksia kullekin tasolle tuetaan, katso artikkelia [Premium-kapasiteetin kuormitusten määrittäminen](../service-admin-premium-workloads.md)
* [Suunnittele ja testaa kapasiteettisi](../service-premium-capacity-optimize.md#testing-approaches) tämän linkin avulla

### <a name="power-bi-embedded-skus"></a>Power BI Embeddedin SKU

Power BI Embedded toimitetaan *A* SKU:n kanssa.
* [Tiedä, mitä Power BI Embedded -kapasiteetti voi käsitellä](https://powerbi.microsoft.com/blog/power-bi-developer-community-june-july-update/#Capacity-Plan)
* [Osta *A* SKU](../service-admin-premium-purchase.md#purchase-a-skus-for-testing-and-other-scenarios)

### <a name="power-bi-premium-skus"></a>Power BI Premiumin SKU

Power BI Premium tarjoaa kaksi SKU:ta, *P* ja *EM*.
* [Ymmärrä *P* ja *EM* SKU:n](../service-premium-what-is.md#subscriptions-and-licensing) väliset erot
* [Osta Premium SKU](../service-admin-premium-purchase.md)

### <a name="which-sku-should-i-use"></a>Mitä SKU:ta minun pitäisi käyttää?

Tämä taulukko sisältää yhteenvedon ominaisuuksista, niiden tarvitsemasta kapasiteetista ja erityisestä SKU:sta, jota kukin tarvitsee. 

</br>
<table>
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<tbody>
<tr>
<td style="text-align: center"; colspan="2"><p><b>Ominaisuus</b></p></td>
<td style="text-align: center">
<p><b>Power BI Embedded</b></p>
</td>
<td style="text-align: center"; colspan="2">
<p><b>Power BI Premium</b></p>
</td>
</tr>
<tr>
<td><p><em>Mitä käytetään?</em><p></td>
<td><p><em>Mitä käytetään?</em><p></td>
<td style="text-align: center"><p><em>SKU</br>(Azure)</em></p></td>
<td style="text-align: center"><p><em>EM SKU</br>(Office)</em></p></td>
<td style="text-align: center"><p><em>P SKU</br>(Office)</em></p></td>
</tr>
<tr>
<td>Upotusartefaktit Power BI -työtilasta</td>
<td>
</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="2">Power BI -raportit</td>
<td>Upotettu sovellus organisaatiollesi</br>(käyttäjä omistaa tiedot)</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Upotettu sovellus asiakkaillesi</br>(sovellus omistaa tiedot)</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="3">Power BI -sisältö<br>(ilmaisella Power BI -käyttöoikeudella)</td>
<td>Power BI -palvelu</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Power BI Mobile</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>MS Office -sovellukset</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
</tbody>
</table>

### <a name="capacity-considerations"></a>Kapasiteettinäkökohdat

Alla olevassa taulukossa luetellaan maksu- ja käyttönäkökohdat kapasiteettia kohden.

</br>
<table>
<tbody>
<tr>
<td></td>
<td style="text-align: center;"><p><strong>Power BI Embedded</strong></p></td>
<td style="text-align: center;" colspan="2"><p><strong>Power BI Premium</strong></p></td>
</tr>
<tr>
<td><p><strong>Tarjous</strong></p></td>
<td style="text-align: center;"><p>Azure</p></td>
<td style="text-align: center;" colspan="2"><p>Office</p></td>
</tr>
<tr>
<td><p><strong>SKU</strong></p></td>
<td style="text-align: center;"><p>A</p></td>
<td style="text-align: center;"><p>EM</p></td>
<td style="text-align: center;"><p>P</p></td>
</tr>
<tr>
<td><p><strong>Laskutus</strong></td>
<td style="text-align: center;">Tunneittain</td>
<td style="text-align: center;">Kuukausittain</td>
<td style="text-align: center;">Kuukausittain</td>
</tr>
<tr>
<td><p><strong>Sitoutuminen</strong></td>
<td style="text-align: center;">Ei mitään</td>
<td style="text-align: center;">Kuukausittain tai vuosittain</td>
<td style="text-align: center;">Kuukausittain tai vuosittain</td>
</tr>
<tr>
<td valign="top"><p><strong>Käyttö</strong></td>
<td style="text-align: center;">Azure-resurssit voi olla:</br>- <a href="azure-pbie-scale-capacity.md">skaalattu ylös tai alas</a></br>- <a href="azure-pbie-pause-start.md">keskeytetty ja jatkettu</a>
</td>
<td style="text-align: center;">Upotettu sovelluksiin ja</br> Microsoft-sovelluksiin</td>
<td style="text-align: center;">Upotettu sovelluksiin ja</br> Power BI -palveluun</td>
</tr>
</tbody>
</table>

### <a name="sku-memory-and-computing-power"></a>SKU-muisti ja laskentateho

Seuraavassa taulukossa kuvataan jokaisen SKU:n resurssit ja rajoitukset.

| Kapasiteetin solmut | V-ytimiä yhteensä | Taustan v-ytimet | RAM (GB) | Edustan v-ytimet | DirectQuery/live-yhteys (sekunnissa) | Mallin uudelleen latauksen parallelisointi |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0,5 | 2.5 | 0,5 | 3.75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7.5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| P4 | 64 | 32 | 200 | 32 | 240 | 48 |
| P5 | 128 | 64 | 400 | 64 | 480 | 96 |
| | | | | | | |

## <a name="next-steps"></a>Seuraavat vaiheet

> [!div class="nextstepaction"]
>[Upottaminen asiakkaillesi](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Upottaminen organisaatiollesi](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Upottaminen sovelluksista](embed-from-apps.md)