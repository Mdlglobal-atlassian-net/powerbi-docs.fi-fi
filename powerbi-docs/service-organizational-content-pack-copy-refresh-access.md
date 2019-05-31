---
title: 'Organisaation sisältöpaketit: käyttö ja kopiointi'
description: Lisätietoja kopioiden luomisesta organisaation sisältöpaketeista ja käytön vianmäärityksestä Power BI:ssä
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp, kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/02/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: c369d8f0d342aebcb3625b289472089412ef7cee
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61227713"
---
# <a name="organizational-content-packs-copy-refresh-and-get-access"></a>Organisaation sisältöpaketit: kopioiminen, päivittäminen ja käyttöoikeuden hankkiminen

Kun organisaation sisältöpaketti julkaistaan, kaikki vastaanottajat näkevät saman sisällön (koontinäytön, raportit, Excel-työkirjat, tietojoukot ja tiedot, ellei kyseessä ole SQL Server Analysis Services (SSAS) -tietolähde).  [Vain sisältöpaketin tekijä voi muokata sisältöpakettia ja julkaista sen uudelleen](service-organizational-content-pack-manage-update-delete.md).  Kaikki vastaanottajat voivat kuitenkin tallentaa kopion sisältöpaketista, joka toimii alkuperäisen kappaleen rinnalla.

Sisältöpakettien luominen eroaa koontinäyttöjen jakamisesta tai niiden työstämisestä ryhmässä. Valitse itsellesi sopivin vaihtoehto lukemalla artikkeli [Miten voin työstää koontinäyttöjä ja raportteja yhdessä muiden kanssa sekä jakaa niitä?](service-how-to-collaborate-distribute-dashboards-reports.md).

> [!NOTE]
> Et voi luoda tai asentaa organisaation sisältöpaketteja uuden työtilakokemuksen esiversiossa. Nyt on hyvä aika päivittää sisältöpaketit sovelluksiin, jos et ole vielä aloittanut päivittämistä. Lue [lisätietoja uudesta työtilakokemuksesta](service-create-the-new-workspaces.md).
>

## <a name="create-a-copy-of-an-organizational-content-pack"></a>Kopion luominen organisaation sisältöpaketista
Luo sisältöpaketista oma kopiosi, joka ei näy muille.

1. Valitse kolme pistettä (...) sisältöpaketin koontinäytön vieressä ja valitse Tee kopio.

    ![](media/service-organizational-content-pack-copy-refresh-access/power-bi-create-copy-organizational-content-pack.png)
2. Valitse **Tallenna**.  

Nyt sinulla on kopio, jota voit muokata. Kukaan muu ei näe tekemiäsi muutoksia.

> [!NOTE]
> Aiemmin sisältöpaketin asentaminen tai kopioiminen aiheutti sen, että työtilan sisältöluetteloon ilmestyi uusi tietojoukko. Viimeisin päivitys yksinkertaisti käyttökokemusta niin, että näet vain yhden kohteen, jossa käytetään uutta, viittauksen sisältävää tietojoukkokuvaketta:
>
> ![tietokanta, jossa linkkikuvake](media/service-organizational-content-pack-copy-refresh-access/power-bi-dataset-reference-icon.png)
>

## <a name="help--i-can-no-longer-access-the-content-pack"></a>Apua!  Sisältöpaketti ei ole enää käytettävissä
Tämä voi johtua useista syistä:

* **Jäsenyys muuttuu**:  Sisältöpaketit julkaistaan sähköpostin jakeluryhmille, käyttöoikeusryhmille ja [Office 365:een perustuville Power BI -ryhmille](https://support.office.com/article/Create-a-group-in-Office-365-7124dc4c-1de9-40d4-b096-e8add19209e9).  Jos sinut poistetaan ryhmästä, et enää pääse käyttämään sisältöpakettia.
* **Jakelun muutokset**: Sisältöpaketin tekijä muuttaa jakelua. Esimerkiksi jos sisältöpaketti on alun perin julkaistu koko organisaatiolle, mutta tekijä julkaisee sen uudelleen pienemmälle yleisölle, et välttämättä enää sisälly paketin kohdeyleisöön.
* **Suojausasetukset muuttuvat**: Jos koontinäyttö ja raportit on yhdistetty paikallisiin SSAS-tietolähteisiin ja suojausasetuksia muutetaan, käyttöoikeutesi kyseiseen palvelimeen on ehkä kumottu.

## <a name="how-are-organizational-content-packs-refreshed"></a>Miten organisaation sisältöpaketit päivitetään?
Kun sisältöpaketti luodaan, päivitysasetukset periytyvät tietojoukon kanssa.  Kun luot sisältöpaketista kopion, uusi versio säilyttää yhteyden alkuperäiseen tietojoukkoon ja sen päivitysaikatauluun.

Katso [Organisaation sisältöpakettien hallinta, päivitys ja poistaminen](service-organizational-content-pack-manage-update-delete.md).

## <a name="next-steps"></a>Seuraavat vaiheet
* [Johdanto organisaation sisältöpaketteihin](service-organizational-content-pack-introduction.md)
* [Ryhmän luominen Power BI:ssä](service-create-distribute-apps.md)
* Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
