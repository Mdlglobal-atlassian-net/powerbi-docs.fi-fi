---
title: Koontinäytön, raportin, työkirjan, tietojoukon tai työtilan poistaminen
description: Opi poistamaan melkein mitä tahansa Power BI:stä
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/11/2018
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: 5701176e362649d992fb6f9cd79e003abcf87bf5
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249386"
---
# <a name="delete-almost-anything-in-power-bi-service"></a>Poista melkein mitä tahansa Power BI -palvelussa
Tässä artikkelissa opetetaan, miten Power BI -palvelussa poistetaan koontinäyttö, raportti, työkirja, tietojoukko, sovellus, visualisointi ja työtila.

## <a name="delete-a-dashboard"></a>Koontinäytön poistaminen
Koontinäyttöjä voidaan poistaa. Koontinäytön poistaminen ei poista sen pohjana olevaa tietojoukkoa tai tähän koontinäyttöön liittyviä raportteja.

* Jos olet koontinäytön omistaja, voit poistaa sen. Jos olet jakanut koontinäytön työtovereiden kanssa, koontinäytön poistaminen Power BI -työtilastasi poistaa koontinäytön heidän Power BI -työtiloistaan.
* Jos koontinäyttö on jaettu kanssasi etkä enää halua nähdä sitä, voit poistaa sen.  Koontinäytön poistaminen ei poista sitä kenenkään muun käyttäjän Power BI -työtilasta.
* Jos koontinäyttö on osa [organisaation sisältöpakettia](service-organizational-content-pack-disconnect.md), ainoa tapa poistaa se on poistaa siihen liittyvä tietojoukko.

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
   > Jos raportti on osa [sisältöpakettia](service-organizational-content-pack-introduction.md), et voi poistaa sitä tällä menetelmällä.  Katso [Organisaation sisältöpaketin yhteyden poistaminen](service-organizational-content-pack-disconnect.md).
   >
   >

## <a name="delete-a-workbook"></a>Työkirjan poistaminen
Työkirjoja voidaan poistaa. Työkirjan poistaminen poistaa kuitenkin myös kaikki raportit ja koontinäyttöruudut, jotka sisältävät tietoja tästä työkirjasta.

Jos työkirja on tallennettu OneDrive for Businessissa, sen poistaminen Power BI:stä ei poista sitä OneDrivesta.

### <a name="to-delete-a-workbook"></a>Työkirjan poistaminen
1. Valitse työtilassa **Työkirjat**-välilehti.
2. Etsi poistettava työkirja ja valitse Poista- ![Poista-kuvake](media/service-delete/power-bi-delete-report2.png) kuvake.

    ![Työkirjat-välilehti](media/service-delete/power-bi-delete-workbooknew.png)
3. Vahvista poistaminen.

   ![Poista työkirja -valintaikkuna](media/service-delete/power-bi-delete-confirm.png)

## <a name="delete-a-dataset"></a>Tietojoukon poistaminen
Tietojoukkoja voi poistaa. Tietojoukon poistaminen poistaa kuitenkin myös kaikki raportit ja koontinäyttöruudut, jotka sisältävät tietojoukon tietoja.

Jos tietojoukko on osa vähintään yhtä [organisaation sisältöpakettia](service-organizational-content-pack-disconnect.md), ainoa tapa poistaa se on poistaa se sisältöpaketeista, joissa se on käytössä, odottaa sen käsittelemistä ja yrittää sitten poistaa se uudelleen.

### <a name="to-delete-a-dataset"></a>Tietojoukon poistaminen
1. Valitse työtilassa **Tietojoukot**-välilehti.
2. Etsi poistettava tietojoukko ja valitse kolme pistettä (...).  

    ![Tietojoukot-välilehti](media/service-delete/power-bi-delete-datasetnew.png)
3. Valitse avattavasta valikosta **Poista**.

   ![kolmen pisteen valikko](media/service-delete/power-bi-delete-datasetnew2.png)
4. Vahvista poistaminen.

   ![Poista koontinäyttö -valintaikkuna](media/service-delete/power-bi-delete-dataset-confirm.png)

## <a name="delete-an-app-workspace"></a>Sovelluksen työtilan poistaminen
> [!WARNING]
> Kun luot sovelluksen työtilan, luot Office 365 -ryhmän. Ja kun poistat sovelluksen työtilan, poistat kyseisen Office 365 -ryhmän. Tämä tarkoittaa sitä, että ryhmä poistetaan myös muista O365-tuotteista, kuten SharePointista ja Microsoft Teamsista.
>
>

Sovelluksen työtilan tekijänä voit poistaa sen. Kun poistat sen, myös siihen liittyvä sovellus poistetaan kaikilta ryhmän jäseniltä ja omasta AppSourcesta, jos sovellus oli julkaistu koko organisaatiolle. Sovelluksen työtilan poistaminen on erilainen kuin sovelluksen työtilasta poistuminen.

### <a name="to-delete-an-app-workspace---if-you-are-an-admin"></a>Sovelluksen työtilan poistaminen - jos olet järjestelmänvalvoja
1. Valitse vasemmassa siirtymispalkissa **Työtilat**

    ![Sovelluksen työtilat](media/service-delete/power-bi-delete-workspace.png)
2. Valitse poistettavan työtilan oikealta puolelta kolme pistettä (...) ja valitse **Muokkaa työtilaa**.

   ![kolme pistettä-valikko > Muokkaa työtilaa](media/service-delete/power-bi-edit-workspace.png)
3. Valitse **Muokkaa työtilaa** -ikkunasta **Poista työtila** > **Poista**.

    ![poista työtila](media/service-delete/power-bi-delete-workspace2.png)

### <a name="to-remove-an-app-workspace-from-your-list"></a>Sovelluksen työtilan poistaminen luettelosta
Jos et enää halua olla sovelluksen työtilan jäsen, voit ***poistua*** siitä, jolloin se poistetaan luettelostasi. Työtilasta poistuminen jättää sen paikalleen kaikille muille työtilan jäsenille.  

> [!IMPORTANT]
> Jos olet sovelluksen työtilan ainoa järjestelmänvalvoja, Power BI ei salli poistumista.
>
>

1. Aloita poistettavasta sovelluksen työtilasta.
2. Valitse oikeasta yläkulmasta kolme pistettä (...) ja valitse **Poistu työtilasta** > **Poistu**.

      ![poistu työtilasta](media/service-delete/power-bi-leave-workspace.png)

   > [!NOTE]
   > Avattavan valikon vaihtoehdot määräytyvät sen mukaan, oletko sovelluksen työtilan järjestelmänvalvoja vai jäsen.
   >
   >

## <a name="delete-or-remove-an-app"></a>Sovelluksen poistaminen
Sovellukset voidaan helposti poistaa sovellusten luettelosivulta. Mutta vain sovelluksen järjestelmänvalvoja voi poistaa sovelluksen pysyvästi.

### <a name="remove-an-app-from-your-app-list-page"></a>Sovelluksen poistaminen sovelluksen luettelosivulta
Sovelluksen poistaminen sovelluksen luettelosivulta ei poista sovellusta muilta jäseniltä.

1. Avaa sovellusten luettelosivu valitsemalla vasemmassa siirtymispalkissa **Sovellukset**.
2. Pidä osoitinta poistettavan sovelluksen päällä ja valitse Poista ![](media/service-delete/power-bi-delete-report2.png) -kuvake.

   ![valitse Sovellukset](media/service-delete/power-bi-delete-app.png)

   Jos poistat sovelluksen vahingossa, voit palauttaa sen usealla eri tavalla.  Voit pyytää sovelluksen tekijää lähettämään sen uudelleen, voit etsiä alkuperäisen sähköpostiviestin, joka sisältää linkin sovellukseen, voit tarkistaa [ilmoituskeskuksesta](service-notification-center.md), onko sovelluksen ilmoitus yhä luettelossa, tai voit tarkistaa organisaation [ AppSourcen](service-install-use-apps.md).

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Tässä artikkelissa kuvattiin Power BI -palvelun pääosien poistaminen. Mutta on paljon muutakin, mitä voit poistaa Power BI:ssä.  

* [Suositellun koontinäytön poistaminen](service-dashboard-featured.md#change-the-featured-dashboard)
* [Koontinäytön poistaminen (suosikeista)](service-dashboard-favorite.md)
* [Raporttisivun poistaminen](service-delete.md)
* [Koontinäyttöruudun poistaminen](service-dashboard-edit-tile.md)
* [Raportin visualisoinnin poistaminen](service-delete.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
