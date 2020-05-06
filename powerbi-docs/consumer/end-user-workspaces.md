---
title: Sisällön järjestäminen työtiloissa
description: Tutustuminen työtiloihin ja työtilarooleihin
author: mihart
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/22/2020
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: 801b5cf5400bbe1cc0487eef596ea3d1cdc5fb1e
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82120153"
---
# <a name="collaborate-in-workspaces"></a>Yhteistyö työtiloissa

 *Työtiloissa* voit käyttää tiettyä sisältöä yhdessä työtovereiden kanssa. Power BI -*suunnittelijat* luovat työtiloja koontinäyttö- ja raporttikokoelmia varten. Sen jälkeen suunnittelija voi niputtaa ne yhteen *sovellukseksi* ja jakaa sen koko organisaatiolle tai tietyille henkilöille tai ryhmille. 

 Kaikilla Power BI -palvelun käyttäjillä on myös **oma työtila**.  Oma työtila on henkilökohtainen eristetty tilasi, jossa voit luoda sisältöä itse.

 Voit tarkastella työtilojasi Power BI -**aloitussivulla** tai valitsemalla **Työtila** tai **Oma työtila** vasemmassa siirtymisruudussa.

 ![siirtymisruutu, jossa näkyy kahdentyyppisiä työtiloja](media/end-user-workspaces/power-bi-home.png)

## <a name="types-of-workspaces"></a>Työtilojen tyypit
**Oma työtila** -sijaintiin voit tallentaa kaiken omistamasi ja luomasi sisällön. Ajattele sitä oman sisältösi henkilökohtaisena eristyksenä tai työskentelyalueena. Monilla Power BI *-kuluttajilla* **Oma työtila** pysyy tyhjänä, koska heidän työnsä ei edellytä uuden sisällön luontia. *Kuluttajat* kuluttavat, eli käyttävät, muiden luomia tietoja ja tekevät liiketoimintapäätöksiä näiden tietojen avulla. Jos luotkin sisältöä, lue sen sijaan [suunnittelijoille tarkoitetut Power BI -artikkelit](../create-reports/index.yml).

**Sovelluksen työtila** sisältää kaiken sisällön tiettyä sovellusta varten. Kun *suunnittelija* luo sovelluksen, hän niputtaa yhteen kaiken sisällön, jota tarvitaan kyseisen sovelluksen käytössä. Sisältö voi olla koontinäyttöjä, raportteja ja tietojoukkoja. Kaikki sovellukset eivät sisällä näitä kolmea sisältöä. Sovelluksessa saattaa olla vain yksi koontinäyttö tai kolme kappaletta jokaista sisältötyyppiä tai jopa kaksikymmentä raporttia. Kaikki riippuu siitä, mitä *suunnittelija* sisällyttää sovellukseen. Yleensä *kuluttajien* sovellustyötilat eivät sisällä tietojoukkoja.

Alla kuvatussa viikunoiden myyntisovelluksen työtilassa on kolme raporttia ja yksi koontinäyttö. 

![siirtymisruutu, jossa näkyy kahdentyyppisiä työtiloja](media/end-user-workspaces/power-bi-app-workspace.png)

## <a name="roles-in-the-workspaces"></a>Työtilojen roolit

Roolit määrittävät, mitä työtiloissa voi tehdä, jotta ryhmät voivat tehdä yhteistyötä.  Myöntäessään uuden työtilan käyttöoikeuksia *suunnittelijat* lisäävät yksittäiset henkilöt tai ryhmät johonkin työtilan rooleista: **Katselija**, **Jäsen**, **Osallistuja** tai **Järjestelmänvalvoja**. 


Power BI -*kuluttajana* voit yleensä käyttää työtiloja käyttämällä **Katselija**-roolia. *Suunnittelija* voi kuitenkin määrittää sinulle myös **Jäsen**- tai **Osallistuja**-rooliin. Katselija-roolilla voit tarkastella ja käyttää sisältöjä (koontinäyttöjä, raportteja ja sovelluksia), joita muut ovat luoneet ja jakaneet sinulle. Koska Katselija-rooli ei voi käyttää pohjana olevaa tietojoukkoa, se on turvallinen tapa käsitellä sisältöä, eikä sinun tarvitse huolehtia pohjana olevien tietojen mahdollisesta haitallisuudesta.


Yksityiskohtainen luettelo siitä, mitä voit tehdä *kuluttajana*, jolla on Katselija-rooli, on artikkelissa [Power BI -ominaisuudet kuluttajille](end-user-features.md).


### <a name="workspace-roles"></a>Työtilaroolit
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
| Kopioi raportti. | X | X | X |  |
| Tarkastele ja käytä kohdetta.<sup>2</sup> |  X | X  | X  | X  |
| Työtilan tietovoihin tallennettujen tietojen lukeminen | X | X | X | X |

1. Osallistujat ja Jäsenet voivat käyttää työtilan kohteita, jos heillä on oikeudet jakaa kohteita uudelleen.

2. Vaikka sinulla ei olisi Power BI Pro -käyttöoikeutta, voit tarkastella ja käyttää Power BI -palvelun kohteita, jos kohteet ovat Premium-kapasiteetin työtilassa.

## <a name="licensing-workspaces-and-capacity"></a>Käyttöoikeudet, työtilat ja kapasiteetti
Käyttöoikeudet määrittävät myös osittain, mitä voit tehdä ja mitä et voi tehdä työtilassa. Monet ominaisuudet edellyttävät, että käyttäjillä on Power BI *Pro* -käyttöoikeus. Useimmat *kuluttajat* käyttävät *maksutonta* käyttöoikeutta. 

Jos sinulla on maksuton käyttöoikeus ja työtila on tallennettu *Premium-kapasiteettiin*, voit tarkastella ja käsitellä kyseisen työtilan sisältöä. Premium-kapasiteettiin tallennetut työtilat ja sovellukset on merkitty timanttikuvakkeella.

![Valitut työtilat](media/end-user-workspaces/power-bi-diamond.png) Jos haluat lisätietoja, katso [Mikä käyttöoikeus minulla on?](end-user-license.md).



## <a name="next-steps"></a>Seuraavat vaiheet
* [Sovellukset Power BI:ssä](end-user-apps.md)    

* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

