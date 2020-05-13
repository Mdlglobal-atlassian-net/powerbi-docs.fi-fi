---
title: Painikkeiden käyttäminen Power BI:ssä
description: Voit lisätä Power BI -raportteihin painikkeita, joiden avulla raportit toimivat sovellusten tavoin ja jotka auttavat syventämään käyttäjien kiinnostusta.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/12/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: c703a4b67b642af5199413e80ff1e140905a2338
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83298546"
---
# <a name="use-buttons-in-power-bi"></a>Painikkeiden käyttäminen Power BI:ssä
Power BI:n **painikkeiden** avulla voit luoda raportteja, jotka toimivat sovellusten tavoin ja jotka luovat siten kiinnostavan ympäristön. Siinä käyttäjät voivat osoittaa ja valita Power BI -sisältöä hiirellä ja olla vuorovaikutuksessa sen kanssa muilla tavoilla. Voit lisätä painikkeita raportteihin **Power BI Desktopissa** ja **Power BI -palvelussa**. Kun jaat raporttisi Power BI -palvelussa, ne tarjoavat käyttäjillesi sovelluksen kaltaisen käyttökokemuksen.

![Painikkeet Power BI:ssä](media/desktop-buttons/power-bi-buttons.png)

## <a name="create-buttons-in-reports"></a>Painikkeiden luominen raporteissa

### <a name="create-a-button-in-power-bi-desktop"></a>Painikkeen luominen Power BI Desktopissa

Voit luoda painikkeen **Power BI Desktopissa** valitsemalla **Lisää**-valintanauhassa **Painikkeet**. Näyttöön tulee avattava valikko, josta voit valita haluamasi painikkeen seuraavassa kuvassa esitetyistä eri vaihtoehdoista. 

![Painike-ohjausobjektin lisääminen Power BI Desktopissa](media/desktop-buttons/power-bi-button-dropdown.png)

### <a name="create-a-button-in-the-power-bi-service"></a>Painikkeen luominen Power BI -palvelussa

Luo painike **Power BI -palvelussa** avaamalla raportti muokkausnäkymässä. Valitse yläreunan valikkorivillä **Painikkeet**. Näyttöön tulee avattava valikko, josta voit valita haluamasi painikkeen seuraavassa kuvassa esitetyistä eri vaihtoehdoista. 

![Painike-ohjausobjektin lisääminen Power BI -palvelussa](media/desktop-buttons/power-bi-button-service-dropdown.png)

## <a name="customize-a-button"></a>Painikkeen mukauttaminen

Prosessin loppuosa on sama riippumatta siitä, luotko painikkeen Power BI Desktopissa vai Power BI -palvelussa. Kun valitset painikkeen raporttialustalla, **Visualisoinnit**-ruudussa näytetään useita tapoja, joilla voit mukauttaa painikkeen tarpeidesi mukaiseksi. Voit esimerkiksi ottaa käyttöön **Painikkeen tekstin** tai poistaa sen käytöstä **Visualisoinnit**-ruudun liukusäätimellä. Voit myös muuttaa mm. painikkeen kuvaketta, painikkeen täyttöä, otsikkoa ja sitä, minkä toiminnon painikkeen valitseminen raportissa käynnistää.

![Painikkeen muotoilu Power BI -raportissa](media/desktop-buttons/power-bi-button-properties.png)

## <a name="set-button-properties-when-idle-hovered-over-or-selected"></a>Voit määrittää painikkeen ominaisuudet, kun sillä ei tehdä mitään, kun osoitin on sen päällä tai kun painike on valittu

Power BI:n painikkeilla on kolme tilaa: oletus (miltä painike näyttää, kun sitä ei osoiteta ja kun se ei ole valittuna), osoitettuna ja valittuna (kun painiketta on *napsautettu*). Monia **Visualisoinnit**-ruudun kortteja voidaan muokata yksitellen mukaan näiden kolmen tilan mukaan, minkä ansiosta painikkeita voidaan mukauttaa joustavasti.

**Visualisoinnit**-ruudun seuraavien korttien avulla voit säätää painikkeen muotoilua tai toimintaa sen kolmen tilan perusteella:

* Painikkeen teksti
* Kuvake
* Ääriviiva
* Täyttö

Jos haluat valita, miltä painikkeen pitäisi näkyä kussakin tilassa, laajenna jokin korteista ja valitse kortin yläosassa näkyvä avautuva luettelo. Seuraavassa kuvassa **Kuvake**-kortti on laajennettu ja avattava luettelo valittu niin, että kaikki kolme tilaa näkyvät:

![Painikkeen kolme tilaa Power BI -raportissa](media/desktop-buttons/power-bi-button-format.png)


## <a name="select-the-action-for-a-button"></a>Painikkeen toiminnon valitseminen

Voit valita, mikä toiminto käynnistetään, kun käyttäjä valitsee painikkeen Power BI:ssä. Voit käyttää painikkeiden toimintojen asetuksia **Visualisoinnit**-ruudun **Toiminto**-kortista.

![Power BI -painikkeen toiminto](media/desktop-buttons/power-bi-button-action.png)

Painikkeen toiminnon asetukset ovat seuraavat:

- **Takaisin** palauttaa käyttäjän raportin edelliselle sivulle. Tämä on hyödyllinen ominaisuus sivuilla, joissa poraudutaan.
- **Kirjanmerkki** näyttää raporttisivun, joka on liitetty senhetkisen raportin kirjanmerkkiin. Katso lisätietoja [kirjanmerkeistä Power BI:ssä](desktop-bookmarks.md). 
- **Porautuminen (esikatselu)** siirtää käyttäjän porautumissivulle hänen valinnoillaan suodatettuna ilman kirjanmerkkien käyttämistä. Katso lisätietoja [raporttien porautumispainikkeista](desktop-drill-through-buttons.md).
- **Sivussa siirtyminen** siirtää käyttäjän raportin eri sivulle myös ilman kirjanmerkkien käyttämistä. Katso lisätietoja tämän artikkelin kohdasta [Sivussa siirtymisen luominen](#create-page-navigation).
- **Q&A** avaa **Q&A Explorer** -ikkunan. 

Tietyillä painikkeilla on automaattisesti valittu oletustoiminto. Esimerkiksi **Q&A**-painiketyypin oletustoiminnoksi valitaan automaattisesti **Q&A**. Katso lisätietoja **Q&A Explorerista**[tästä blogikirjoituksesta](https://powerbi.microsoft.com/blog/power-bi-desktop-april-2018-feature-summary/#Q&AExplorer).

Voit kokeilla tai testata raportin painikkeita käyttämällä *CTRL + NAPSAUTUS* -yhdistelmää haluamaasi painikkeeseen. 

### <a name="create-page-navigation"></a>Sivussa siirtymisen luominen

**Toiminto**-tyypin **sivussa siirtymisellä** voit luoda nopeasti kaikki siirtymistoiminnot ilman, että sinun tarvitsee tallentaa tai hallita yhtään kirjanmerkkiä.

Jos haluat määrittää sivussa siirtymisen painikkeen, luo painike **Sivussa siirtyminen** -kohdassa toimintotyyppinä ja valitse **Kohde**-sivu.

![Sivussa siirtyminen -toiminto](media/desktop-buttons/power-bi-page-navigation.png)

Voit luoda mukautetun siirtymisruudun nopeasti. Sinun ei tarvitse muokata ja hallita kirjanmerkkejä, jos haluat muuttaa siirtymisruudussa näytettäviä sivuja.

![Siirtymissivun luominen](media/desktop-buttons/power-bi-build-navigation-pane.png)

Lisäksi voit muotoilla työkaluvihjeen ehdollisesti samalla tavalla kuin muutkin painiketyypit.

## <a name="next-steps"></a>Seuraavat vaiheet
Seuraavissa artikkeleissa on lisätietoja ominaisuuksista, jotka muistuttavat painikkeita tai toimivat niiden kanssa:

* [Porautumisen käyttäminen Power BI -raporteissa](desktop-drillthrough.md)
* [Kirjanmerkkien käyttäminen merkityksellisten tietojen jakamiseen ja tarinoiden koostamiseen Power BI:ssä](desktop-bookmarks.md)

