---
title: Koontinäytön, raportin, työkirjan, tietojoukon tai työtilan poistaminen
description: Opi poistamaan melkein mitä tahansa Power BI:stä
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/11/2018
ms.author: maggies
LocalizationGroup: Common tasks
ms.openlocfilehash: 3fdb969888d023ca9683c2460086f2fb8157c3c3
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83304549"
---
# <a name="delete-almost-anything-in-power-bi-service"></a>Poista melkein mitä tahansa Power BI -palvelussa
Tässä artikkelissa opetetaan, miten Power BI -palvelussa poistetaan koontinäyttö, raportti, työkirja, tietojoukko, sovellus, visualisointi ja työtila.

## <a name="delete-a-dashboard"></a>Koontinäytön poistaminen
Koontinäyttöjä voidaan poistaa. Koontinäytön poistaminen ei poista sen pohjana olevaa tietojoukkoa tai tähän koontinäyttöön liittyviä raportteja.

* Jos olet koontinäytön omistaja, voit poistaa sen. Jos olet jakanut koontinäytön työtovereiden kanssa, koontinäytön poistaminen Power BI -työtilastasi poistaa koontinäytön heidän Power BI -työtiloistaan.
* Jos koontinäyttö on jaettu kanssasi etkä enää halua nähdä sitä, voit poistaa sen.  Koontinäytön poistaminen ei poista sitä kenenkään muun käyttäjän Power BI -työtilasta.
* Jos koontinäyttö on osa [organisaation sisältöpakettia](../collaborate-share/service-organizational-content-pack-disconnect.md), ainoa tapa poistaa se on poistaa siihen liittyvä tietojoukko.

### <a name="to-delete-a-dashboard"></a>Koontinäytön poistaminen
1. Valitse työtilassa **Koontinäytöt**-välilehti.
2. Etsi poistettava koontinäyttö ja valitse Poista-kuvake ![Poista-kuvake](media/service-delete/power-bi-delete-icon.png).

    ![video](media/service-delete/power-bi-delete-dash.gif)

## <a name="delete-a-report"></a>Raportin poistaminen
Älä huolestu, raportin poistaminen ei poista tietojoukkoa, johon raportti perustuu.  Myös visualisoinnit, jotka olet kiinnittänyt raporttiin, ovat turvassa -- ne pysyvät koontinäytössä, kunnes poistat ne yksitellen.

### <a name="to-delete-a-report"></a>Raportin poistaminen
1. Valitse työtilassa **Raportit**-välilehti.
2. Etsi poistettava raportti ja valitse Poista-kuvake   ![Poista-kuvake](media/service-delete/power-bi-delete-icon.png).   

    ![työtilan raportit-välilehti](media/service-delete/power-bi-delete-reportnew.png)
3. Vahvista poistaminen.

   ![Poista raportti -valintaikkuna](media/service-delete/power-bi-delete-report.png)

   > [!NOTE]
   > Jos raportti on osa [sisältöpakettia](../collaborate-share/service-organizational-content-pack-introduction.md), et voi poistaa sitä tällä menetelmällä.  Katso [Organisaation sisältöpaketin yhteyden poistaminen](../collaborate-share/service-organizational-content-pack-disconnect.md).
   >
   >

## <a name="delete-a-workbook"></a>Työkirjan poistaminen
Työkirjat voidaan poistaa. Työkirjan poistaminen poistaa kuitenkin myös kaikki raportit ja koontinäyttöruudut, jotka sisältävät tietoja tästä työkirjasta.

Jos työkirja on tallennettu OneDrive for Businessissa, sen poistaminen Power BI:stä ei poista sitä OneDrivesta.

### <a name="to-delete-a-workbook"></a>Työkirjan poistaminen
1. Valitse työtilassa **Työkirjat**-välilehti.
2. Etsi poistettava työkirja ja valitse Poista- ![Poista-kuvake](media/service-delete/power-bi-delete-report2.png) kuvake.

    ![Työkirjat-välilehti](media/service-delete/power-bi-delete-workbooknew.png)
3. Vahvista poistaminen.

   ![Poista työkirja -valintaikkuna](media/service-delete/power-bi-delete-confirm.png)

## <a name="delete-a-dataset"></a>Tietojoukon poistaminen
Tietojoukkoja voi poistaa. Tietojoukon poistaminen poistaa kuitenkin myös kaikki raportit ja koontinäyttöruudut, jotka sisältävät tietojoukon tietoja.

Jos tietojoukko on osa vähintään yhtä [organisaation sisältöpakettia](../collaborate-share/service-organizational-content-pack-disconnect.md), ainoa tapa poistaa se on poistaa se sisältöpaketeista, joissa se on käytössä, odottaa sen käsittelemistä ja yrittää sitten poistaa se uudelleen.

### <a name="to-delete-a-dataset"></a>Tietojoukon poistaminen
1. Valitse työtilassa **Tietojoukot**-välilehti.
2. Etsi poistettava tietojoukko ja valitse **Lisää vaihtoehtoja** (...).  

    ![Tietojoukot-välilehti](media/service-delete/power-bi-delete-datasetnew.png)
3. Valitse avattavasta valikosta **Poista**.

   ![kolmen pisteen valikko](media/service-delete/power-bi-delete-datasetnew2.png)
4. Vahvista poistaminen.

   ![Poista koontinäyttö -valintaikkuna](media/service-delete/power-bi-delete-dataset-confirm.png)

## <a name="delete-a-workspace"></a>Poista työtila
> [!WARNING]
> Kun luot työtilan, luot Office 365 -ryhmän. Ja kun poistat työtilan, poistat kyseisen Office 365 -ryhmän. Tämä tarkoittaa sitä, että ryhmä poistetaan myös muista O365-tuotteista, kuten SharePointista ja Microsoft Teamsista.
>
>

Työtilan tekijänä voit poistaa sen. Kun poistat sen, myös siihen liittyvä sovellus poistetaan kaikilta ryhmän jäseniltä ja omasta AppSourcesta, jos sovellus oli julkaistu koko organisaatiolle. Työtilan poistaminen on eri asia kuin työtilasta poistuminen.

### <a name="to-delete-a-workspace---if-you-are-an-admin"></a>Työtilan poistaminen – jos olet järjestelmänvalvoja
1. Valitse siirtymisruudusta **Työtilat**

2. Valitse poistettavan työtilan oikealta puolelta **Lisää vaihtoehtoja** (...) ja valitse **Muokkaa työtilaa**.

    ![työtilat](media/service-delete/power-bi-delete-workspace.png)

3. Valitse **Muokkaa työtilaa** -ikkunasta **Poista työtila** > **Poista**.

    ![poista työtila](media/service-delete/power-bi-delete-workspace2.png)

### <a name="to-remove-a-workspace-from-your-list"></a>Työtilan poistaminen luettelosta
Jos et enää halua olla työtilan jäsen, voit ***poistua*** siitä, jolloin se poistetaan luettelostasi. Työtilasta poistuminen jättää sen paikalleen kaikille muille työtilan jäsenille.  

> [!IMPORTANT]
> Jos olet työtilan ainoa järjestelmänvalvoja, Power BI ei salli poistumista.
>
>

1. Aloita siitä työtilasta, jonka haluat poistaa.

2. Valitse oikeasta yläkulmasta **Lisää vaihtoehtoja** (...) ja valitse **Poistu työtilasta** > **Poistu**.

      ![poistu työtilasta](media/service-delete/power-bi-leave-workspace.png)

   > [!NOTE]
   > Avattavan valikon vaihtoehdot määräytyvät sen mukaan, oletko työtilan järjestelmänvalvoja vai jäsen.
   >
   >

## <a name="delete-or-remove-an-app"></a>Sovelluksen poistaminen
Sovellukset voidaan helposti poistaa sovellusten luettelosivulta. Mutta vain sovelluksen järjestelmänvalvoja voi poistaa sovelluksen pysyvästi.

### <a name="remove-an-app-from-your-app-list-page"></a>Sovelluksen poistaminen sovelluksen luettelosivulta
Sovelluksen poistaminen sovelluksen luettelosivulta ei poista sovellusta muilta jäseniltä.

1. Avaa sovellusten luettelosivu valitsemalla siirtymisruudussa **Sovellukset**.
2. Pidä osoitinta poistettavan sovelluksen päällä ja valitse Poista ![](media/service-delete/power-bi-delete-report2.png) -kuvake.

   ![valitse Sovellukset](media/service-delete/power-bi-delete-app.png)

   Jos poistat sovelluksen vahingossa, voit palauttaa sen usealla eri tavalla.  Voit pyytää sovelluksen tekijää lähettämään sen uudelleen, voit etsiä alkuperäisen sähköpostiviestin, joka sisältää linkin sovellukseen, voit tarkistaa [ilmoituskeskuksesta](../consumer/end-user-notification-center.md), onko sovelluksen ilmoitus yhä luettelossa, tai voit tarkistaa [organisaatiosi AppSourcen](../consumer/end-user-apps.md).

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Tässä artikkelissa kuvattiin Power BI -palvelun pääosien poistaminen. Mutta on paljon muutakin, mitä voit poistaa Power BI:ssä.  

* [Suositellun koontinäytön poistaminen](../consumer/end-user-featured.md)
* [Koontinäytön poistaminen (suosikeista)](../consumer/end-user-favorite.md)
* [Raporttisivun poistaminen](service-delete.md)
* [Koontinäyttöruudun poistaminen](service-dashboard-edit-tile.md)
* [Raportin visualisoinnin poistaminen](service-delete.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
