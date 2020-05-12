---
title: Power BI:n työtilaroolit
description: Power BI:n työtilaroolitaulukko
services: powerbi
author: maggiesMSFT
ms.service: powerbi
ms.topic: include
ms.date: 04/23/2020
ms.author: maggies
ms.custom: include file
ms.openlocfilehash: 5ed3a65f1ef65640c76ada765931a85714aad3af
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82781342"
---
Tässä ovat ominaisuudet neljästä roolista: järjestelmänvalvojat, jäsenet, osallistujat ja katselijat. Kaikki nämä ominaisuudet tarkastelua ja käyttämistä lukuun ottamatta edellyttävät Power BI Pro -käyttöoikeutta.

|Ominaisuus   | Järjestelmänvalvoja  | Jäsen  | Osallistuja  | Katselija |
|---|---|---|---|---|
| Päivittää työtilaa ja poistaa sen.  | X  |   |   |   | 
| Lisätä tai poistaa ihmisiä, myös muita järjestelmänvalvojia.  | X  |   |   |   |
| Lisätä jäseniä tai muita, joilla on vähäisemmät oikeudet.  |  X | X  |   |   |
| Julkaista ja päivittää sovelluksen. |  X | X  |   |   |
| Jakaa kohteen tai sovelluksen.<sup>1</sup> |  X | X  |   |   |
| Sallia muille kohteiden jakaminen uudelleen.<sup>1</sup> |  X | X  |   |   |
| Ominaisuussovelluksia työtovereiden kotisivuilla |  X | X  |   |   |
| Ominaisuuskoontinäyttöjä ja raportteja työtovereiden kotisivuilla |  X | X  | X |   |
| Luoda, muokata ja poistaa työtilan sisältöä.  |  X | X  | X  |   |
| Julkaista raportteja työtilaan ja poistaa sisältöä.  |  X | X  | X  |   |
| Luo raportti toisessa työtilassa tämän työtilan tietojoukon perusteella.<sup>1</sup> |  X | X  | X  |   |
| Kopioi raportti.<sup>2</sup> | X | X | X |  |
| Ajoita tietojen päivitykset paikallisen yhdyskäytävän kautta.<sup>3</sup> | X | X | X |  |
| Muokkaa yhdyskäytävän yhteysasetuksia.<sup>3</sup> | X | X | X |  |
| Tarkastele ja käytä kohdetta.<sup>4</sup> |  X | X  | X  | X  |
| Työtilan tietovoihin tallennettujen tietojen lukeminen | X | X | X | X |

1. Osallistujat ja katselijat voivat käyttää työtilan kohteita, jos heillä on oikeudet jakaa kohteita uudelleen.
2. Jos haluat kopioida raportin tai luoda raportin toisessa työtilassa tämän työtilan tietojoukon perusteella, tarvitset tietojoukon muodostamisen käyttöoikeuden. Tämän työtilan tietojoukoissa käyttäjillä, joilla on järjestelmänvalvojan, jäsenen tai osallistujan rooli, on muodostamisen käyttöoikeus työtilaroolin kautta.
3. Muista, että tarvitset myös yhdyskäytävän käyttöoikeudet. Näitä käyttöoikeuksia hallitaan muualla riippumatta työtilan rooleista ja käyttöoikeuksista. Lisätietoja on ohjeaiheessa [Paikallisen yhdyskäytävän hallinta](https://docs.microsoft.com/data-integration/gateway/service-gateway-manage).
4. Vaikka sinulla ei olisikaan Power BI Pro -käyttöoikeutta, voit tarkastella ja käyttää Power BI -palvelun kohteita, jos kohteet ovat Premium-kapasiteetin työtilassa.

