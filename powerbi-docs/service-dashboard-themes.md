---
title: Raporttinäkymän teemojen käyttäminen Power BI -palvelussa
description: Opi käyttämään mukautettua värivalikoimaa ja ota se käyttöön kokonaisessa raporttinäkymässä Power BI -palvelussa
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/22/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 8e444c78c1f6f9f3f0be1375f96f7381489cc069
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61143222"
---
# <a name="use-dashboard-themes-in-power-bi-service"></a>Raporttinäkymän teemojen käyttö Power BI-palvelussa
**Raporttinäkymän teemojen** avulla voit käyttää väriteemaa koko raporttinäkymässä, kuten yrityksen värejä, kausivärejä tai mitä tahansa muuta haluamaasi väriteemaa. Kun otat **raporttinäkymän teeman** käyttöön, kaikki raporttinäkymän visualisoinnit käyttävät valitun teeman värejä (lukuun ottamatta muutamia poikkeuksia, jotka kuvataan myöhemmin tässä artikkelissa).

![Esimerkki raporttinäkymän teemasta](media/service-dashboard-themes/power-bi-full-dashboard-theme.png)

Raportin visualisointien värien muuttaminen raporttinäkymässä, ei vaikuta raportin visualisointeihin. Lisäksi kun kiinnität ruutuja raportista, joka käyttää [raporttiteemaa](desktop-report-themes.md), voit vaihtoehtoisesti säilyttää raportin nykyisen teeman tai käyttää raporttinäkymän teemaa.


## <a name="prerequisites"></a>Edellytykset
* Avaa ensin [Myynti ja markkinointi -malliraporttinäkymä](sample-datasets.md).


## <a name="how-dashboard-themes-work"></a>Raporttinäkymän teemojen toiminta
Aloita avaamalla raporttinäkymä, jonka olet luonut (tai jota sinulla on oikeus muokata) ja jota haluat mukauttaa. Valitse kolme pistettä (...) ja valitse sitten **Raporttinäkymän teema**. 

![Raporttinäkymän teema -vaihtoehto](media/service-dashboard-themes/power-bi-dashboard-theme.png)

Valitse jokin valmiiksi luoduista teemoista ilmestyvässä raporttinäkymäruudussa.  Alla olevassa esimerkissä olemme valinneet **Tumman**.

![Vaalea-asetus valittuna](media/service-dashboard-themes/power-bi-theme-menu.png)

![Tumma-asetus käytössä](media/service-dashboard-themes/power-bi-theme-dark.png)

## <a name="create-a-custom-theme"></a>Luo mukautettu teema

Power BI:n raporttinäkymän oletusteema on **Vaalea**. Jos haluat mukauttaa teeman värejä tai luoda oman teeman, valitse avautuvasta valikosta **Mukautettu**. 

![Valitse mukautettu avautuvasta valikosta](media/service-dashboard-themes/power-bi-theme-custom.png)

Luo oma raporttinäkymän teemasi käyttämällä mukautettuja asetuksia. Jos lisäät taustakuvan, suosittelemme kuvalle vähintään 1920 x 1080 tarkkuutta. Jos haluat käyttää kuvaa taustana, lataa kuva julkiseen sivustoon, kopioi URL-osoite ja liitä se **Kuvan URL-osoite** -kenttään. 

### <a name="using-json-themes"></a>JSON-teemojen käyttäminen
Toinen tapa luoda mukautettu teema, on ladata JSON-tiedosto, joka sisältää kaikki asetukset väreille, joita haluat raporttinäkymässä käytettävän. Power BI Desktopissa raportin tekijät käyttävät JSON-tiedostoja [luodessaan raporttiteemoja](desktop-report-themes.md). Näitä samoja JSON-tiedostoja voidaan ladata raporttinäkymiin tai niitä voi etsiä ja ladata Power BI -yhteisön[Teemavalikoima-sivulta](https://community.powerbi.com/t5/Themes-Gallery/bd-p/ThemesGallery) 

![Teemavalikoima-sivusto](media/service-dashboard-themes/power-bi-theme-gallery.png)

Voit myös tallentaa mukautetun teeman JSON-tiedostona ja jakaa sen muiden raporttinäkymien tekijöiden kanssa. 

### <a name="use-a-theme-from-the-theme-gallery"></a>Teeman käyttäminen teemavalikoimasta

Valmiit ja mukautetut asetukset, kuten myös teeman värit, otetaan automaattisesti käyttöön kaikissa raporttinäkymän ruuduissa kun teema ladataan. 

1. Pidä hiiren osoitin teeman päällä ja valitse **Näytä raportti**.

    ![Näytä raportti](media/service-dashboard-themes/power-bi-choose-theme.png)

2. Vieritä alaspäin ja etsi linkki JSON-tiedostoon.  Valitse lataa-kuvake ja tallenna tiedosto.

    ![Kevätpäivä JSON](media/service-dashboard-themes/power-bi-theme-json.png)

3. Power BI -palvelussa, valitse mukautetun raporttinäkymän teema -ikkunassa **Lataa JSON-teema**.

    ![Lataa JSON](media/service-dashboard-themes/power-bi-upload-theme.png)

4. Siirry sijaintiin, johon tallensit JSON-teematiedoston ja valitse **Avaa** .

5. Valitse raporttinäkymän teema -sivulta **Tallenna**. Uusi teema otetaan käyttöön raporttinäkymässä.

    ![uusi teema käytössä](media/service-dashboard-themes/power-bi-json.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

* Jos raporttisi teema eroaa raporttinäkymän teemasta, voit hallita, säilytetäänkö visualisoinnissa nykyinen teema vai käytetäänkö raporttinäkymän teemaa, jotta eri lähteistä peräisin olevat visualisoinnit ovat yhdenmukaisia. Kun kiinnität ruutua raporttinäkymään, voit säilyttää raporttiteeman valitsemalla **Säilytä nykyinen teema**. Raporttinäkymän visualisointi säilyttää raporttiteeman, mukaan lukien läpinäkyvyys asetukset. 

    Ainoa kerta kun näet **Ruudun teemoitus** -asetukset on, jos olet luonut raportin Power BI Desktopissa, [lisännyt raporttiteeman](desktop-report-themes.md) ja julkaissut raportin Power BI -palvelussa. 

    ![Säilytä nykyinen valittu teema](media/service-dashboard-themes/power-bi-keep-current.png)

    Yritä ruudun kiinnittämistä uudelleen ja valitse **Käytä raporttinäkymän teemaa**.

    ![Käytä kohdeteemaa](media/service-dashboard-themes/power-bi-use-destination.png)

* Raporttinäkymän teemoja ei voida käyttää kiinnitetyissä reaaliaikaisissa raporttisivuissa, iframe-ruuduissa, SSRS-ruuduissa, työkirjan ruuduissa tai kuvissa.
* Raporttinäkymän teemoja voi tarkastella mobiililaitteilla, mutta raporttinäkymän teemoja voidaan luoda vain Power BI -palvelussa. 
* Raporttinäkymän mukautetut teemat toimivat vain raporteista kiinnitetyissä ruuduissa. 

