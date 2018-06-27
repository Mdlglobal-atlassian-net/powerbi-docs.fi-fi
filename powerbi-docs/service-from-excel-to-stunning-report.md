---
title: Excel-työkirjasta upeaksi raportiksi nopeasti
description: Excel-työkirjasta upeaksi raportiksi nopeasti
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/28/2018
ms.author: mihart
LocalizationGroup: Data from files
ms.openlocfilehash: f24d4055bd5fcf5fdee058112c268a1a0e197012
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34247168"
---
# <a name="from-excel-workbook-to-stunning-report-in-no-time"></a>Excel-työkirjasta upeaksi raportiksi nopeasti
Esimiehesi haluaa raportin viimeisimmistä myyntiluvuista yhdistettynä viimeisimmän kampanjan näyttökertoihin vielä tämän päivän aikana. Uusimmat tiedot sijaitsevat kuitenkin erilaisissa kolmannen osapuolen järjestelmissä ja kannettavan tietokoneesi tiedostoissa. Aiemmin visualisointien luominen ja raportin muotoilu on vienyt tunteja. Tunnet, kuinka ahdistus alkaa vallata alaa.

Ei huolta. Power BI:llä voit luoda näyttävän raportin hetkessä.

Tässä esimerkissä lataamme Excel-tiedoston paikallisesta järjestelmästä, luomme uuden raportin ja jaamme sen työtovereille – ja teemme kaiken tämän Power BI -ohjelmassa.

## <a name="prepare-your-data"></a>Tietojen valmistelu
Otetaan esimerkiksi yksinkertainen Excel-tiedosto. Ennen kuin voit ladata Excel-tiedostosi Power BI:hin, tiedot on järjestettävä taulukoksi, jonka ulkoasu on litteä. Tämä tarkoittaa, että kukin sarake sisältää samaa tietotyyppiä, esimerkiksi tekstiä, päivämääriä, lukuja tai valuuttoja. Taulukossa on oltava otsikkorivi, mutta siinä ei saa olla summasarakkeita tai -rivejä.

![tiedot järjestettynä Excelissä](media/service-from-excel-to-stunning-report/pbi_excel_file.png)

Seuraavaksi tiedot muotoillaan taulukoksi. Valitse Excelin Aloitus-välilehden Tyylit-ryhmässä **Muotoile taulukoksi**. Valitse laskentataulukossa käytettävä taulukkotyyli. Excel-laskentataulukko on nyt valmis ladattavaksi Power BI:hin.

![tiedot muotoiltuna taulukoksi](media/service-from-excel-to-stunning-report/pbi_excel_table.png)

## <a name="upload-your-excel-file-into-power-bi"></a>Excel-tiedoston lataaminen Power BI:hin
Power BI muodostaa yhteyden useisiin tietolähteisiin, kuten tietokoneessasi oleviin Excel-tiedostoihin. Aloita kirjautumalla sisään Power BI:hin. Jos et ole vielä rekisteröinyt, [voit tehdä sen maksutta](https://powerbi.com).

Haluat luoda uuden koontinäytön. Avaa **Oma työtila** ja valitse **+ Luo** -kuvake.

![Luo-kuvake](media/service-from-excel-to-stunning-report/power-bi-new-dash.png)

Valitse **Koontinäyttö**, kirjoita nimi ja valitse **Luo**. Uusi koontinäyttö tulee näkyviin – ilman tietoja.

![Avattava Luo-valikko](media/service-from-excel-to-stunning-report/power-bi-create-dash.png)

Valitse vasemman siirtymisruudun alareunasta **Nouda tiedot**. Valitse Nouda tiedot -sivun Tuo tietoja tai yhdistä niihin -kohdan Tiedostot-ruudussa **Nouda**.

![Tietojen hakeminen tiedostoista](media/service-from-excel-to-stunning-report/pbi_get_files.png)

Valitse Tiedostot-sivulla **Paikallinen tiedosto**. Siirry tietokoneella olevan Excel-työkirjatiedoston kohdalle ja valitse se ladattavaksi Power BI:hin. Valitse **Tuo**.

> **HUOMAUTUS**: Käytä tämän opetusohjelman loppuun suorittamisessa [Talousmalli-työkirjaa](sample-financial-download.md).
> 
> 

![Nouda tiedot > Tiedostot-ikkuna](media/service-from-excel-to-stunning-report/pbi_local_file.png)

## <a name="build-your-report"></a>Raportin luominen
Kun Power BI on tuonut Excel-tiedoston, voit aloittaa raportin luomisen. Kun näyttöön tulee **Tietojoukkosi on valmiina** -ilmoitus, valitse **Näytä tietojoukko**.  Power BI avautuu muokkausnäkymässä ja näyttää raporttipohjan. Oikealla puolella sijaitsevat Visualisoinnit-, Suodattimet- ja Kentät-ruudut.

Huomaa, että Excel-työkirjan taulukkotiedot näkyvät Kentät-ruudussa. Power BI näyttää sarakeotsikot taulukon nimen alla yksittäisten kenttien luettelona.

![Excel-tietojen näkymä Kentät-ruudussa](media/service-from-excel-to-stunning-report/pbi_report_fields.png)

Nyt voit aloittaa visualisointien luomisen. Esimiehesi haluaa tarkastella tuottoa ajan mukaan. Etsi Kentät-ruudussa **Tuotto** ja vedä se raporttipohjaan. Power BI näyttää oletusarvoisesti palkkikaavion. Jatka vetämällä **Päivämäärä** raporttipohjaan. Power BI päivittää palkkikaavion näyttämään tuoton päivämäärän mukaan.

![pylväskaavio raporttieditorissa](media/service-from-excel-to-stunning-report/pbi_report_pin-new.png)

> **VIHJE**: Jos kaavio ei vastaa odotuksiasi, tarkista koosteet. Voit esimerkiksi napsauttaa **Arvo**-kohdassa hiiren kakkospainikkeella juuri lisäämääsi kenttää ja varmistaa, että tiedot on koostettu haluamallasi tavalla.  Tässä esimerkissä käytetään **Summaa**.
> 
> 

Esimiehesi haluaa tietää, mitkä maat tuottavat eniten voittoa. Tee häneen vaikutus karttavisualisoinnilla. Valitse raporttipohjalta tyhjä alue ja vedä siihen Kentät-ruudusta ensin **Maa**- ja sitten **Tuotto**-kentät. Power BI luo karttavisualisoinnin, jonka kuplat edustavat kunkin sijainnin suhteellista tuottoa.

![karttavisualisointi raporttieditorissa](media/service-from-excel-to-stunning-report/pbi_report_map-new.png)

Entäpä visualisointi, joka kuvaa myyntiä tuotteittain ja markkinasegmenteittäin? Helppoa. Valitse Kentät-ruudussa Myynti-, Tuote- ja Segmentti-kenttien vieressä olevat valintaruudut. Power BI luo palkkikaavion välittömästi. Voit muuttaa kaaviotyyppiä valitsemalla haluamasi kuvakkeen Visualisoinnit-valikosta. Voit esimerkiksi muuttaa kaavion pinotuksi palkkikaavioksi.  Jos haluat lajitella kaavion, valitse kolme pistettä (...) > **Lajitteluperuste**.

![pinottu pylväskaavio raporttieditorissa](media/service-from-excel-to-stunning-report/pbi_barchart-new.png)

Kiinnitä kaikki visualisoinnit koontinäyttöön. Nyt voit jakaa sen työtovereillesi.

![koontinäyttö, johon on kiinnitetty 3 visualisointia](media/service-from-excel-to-stunning-report/pbi_report.png)

## <a name="share-your-dashboard"></a>Koontinäytön jakaminen
Haluat jakaa koontinäytön esimiehellesi Tainalle. Voit jakaa koontinäytön ja siihen liittyvän raportin kenelle tahansa työtoverillesi, jolla on Power BI -tili. Työtoverisi voivat käsitellä raporttia, mutta muutoksia ei voi tallentaa.

Voit jakaa raportin valitsemalla koontinäytön yläreunassa **Jaa**.

![Jaa-kuvake](media/service-from-excel-to-stunning-report/power-bi-share.png)

Power BI:hin avautuu Jaa koontinäyttö -sivu. Kirjoita vastaanottajien sähköpostiosoitteet sivun yläosaan. Lisää viesti alla olevaan kenttään. Jos sallit vastaanottajien jakaa koontinäyttösi muille, valitse **Salli vastaanottajien jakaa koontinäyttösi**. Valitse **Jaa**.

![Jaa koontinäyttö -ikkuna](media/service-from-excel-to-stunning-report/power-bi-share-dash-new.png)

Seuraavat vaiheet

* [Power BI -palvelun käytön aloittaminen](service-get-started.md)
* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)
* [Power BI:n peruskäsitteet](service-basic-concepts.md)
* Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

