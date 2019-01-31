---
title: Power BI:n mallisisältöpakettien testaaminen
description: Mallisisältöpaketin testaaminen
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maggies
ms.openlocfilehash: 8a5382a5e435f916599b05310f89d9b1f0327023
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/31/2019
ms.locfileid: "55430667"
---
# <a name="testing-template-content-packs-for-power-bi"></a>Power BI:n mallisisältöpakettien testaaminen
On useita tapoja testata sisältöpakettia ennen sen lähettämistä julkaisemista varten.  

> [!NOTE]
> Jos sisältöpaketti käyttää mukautettua [Tietoyhdistintä](https://aka.ms/DataConnectors), jonka olet itse kehittänyt, et voi testata tietojen päivittämistä tai mallinsisältöpakettia alla olevien ohjeiden mukaisesti. Jos näin on, siirry kohtaan [Lähetä](#submission) sisältöpaketin lähettämiseksi, niin Power BI -tiimi toimii apunasi sisältöpakettisi testaamisessa.
> 
> 

## <a name="testing-scheduled-data-refresh"></a>Ajoitetun tietojen päivittämisen testaaminen
Mallisisältöpaketit hyödyntävät Päivittämistä PowerBI.comissa sisältöpaketin alustamiseksi asiakkaan tiedoilla yhteyttä muodostettaessa. Voit testata tämän työnkulun työpöytätiedostolla, jonka olet luonut, ennen kuin sisältöpaketti tulee julkisesti saataville.

Kun tiedosto on ladattu palvelimelle, valitse ”...” tietojoukon vierestä ja valitse Ajoita päivitys. Määritä lähteen tunnistetiedot. Varmista, että tietojoukkosi päivittyy onnistuneesti kokeilemalla sekä toimintoa ”Päivitä nyt” että ”Ajoitettu päivitys”. Jos päivityksessä ilmenee virheitä, tarkista virheilmoitukset ja vahvista kyselyt sekä kohdejärjestelmä.

### <a name="additional-refresh-tips"></a>Muita päivitysvihjeitä
* Ohjelman pitäisi havaita vain yksi tietolähde, kun yrität ajoittaa päivitystä  
* Testiyhteyden tulisi ilmaista, että käyttäjä pystyy lataamaan sisältöpaketin. Jos näin ei ole, varmista, että kyselysi käsittelevät muut virhetilanteet.  
* Päivityksen pitäisi valmistua kohtuullisessa ajassa, noin 5 minuuttia on ohjeellinen aika  

![asetukset](media/template-content-pack-testing/scheduledrefresh.png)

<a name="templates"></a>

## <a name="testing-templates"></a>Mallien testaaminen
Mallisisältöpaketti muistuttaa olemassa olevia ratkaisuja, paitsi että sen tietojoukoissa ei ole todellisia tietoja. Sen sijaan, kun käyttäjä käyttää tai alustaa mallin, häntä kehotetaan antamaan parametrit ja tunnistetiedot, jotta yhteys voidaan muodostaa. Kun yhteys on muodostettu, hän näkee omat tietonsa koontinäytössä, raportissa ja tietojoukoissa. 

Kun käyttäjä alustaa sisältöpaketin, hän pääsee käyttämään tietojoukkoasetuksia, mukaan lukien ajoitettua päivitystä. Mitään tietojoukon RLS-asetuksia **ei** julkaista sisältöpaketissa.  

> [!NOTE]
> Mallisisältöpaketit voivat sisältää vain 1 koontinäytön, 1 raportin ja 1 tietojoukon. Katso rajoitusten luettelo [sisällön tuottamisen](template-content-pack-authoring.md#restrictions) sivulta. 
> 
> 

Jos haluat ottaa käyttöön mallin luomisen vuokraajalle, työskentele yhdessä Power BI -järjestelmänvalvojasi kanssa alla olevan ominaisuusvalitsimen ottamiseksi käyttöön. 

![ominaisuusvalitsin](media/template-content-pack-testing/featureswitch.png)

Kun se on otettu käyttöön, näkyviin tulee valintaruutu [”Luo sisältöpaketti”](https://app.powerbi.com/groups/me/publish-content/) -kohdan alareunassa, jonka avulla voit julkaista mallisisältöpaketin organisaatiollesi. 

![valintaruutu](media/template-content-pack-testing/checkbox.png)

### <a name="naming"></a>Nimeäminen
Suosittelemme koontinäytön, raportin ja tietojoukon nimeämistä yhdenmukaisesti kaikkialla sisältöpaketissa. Nämä nimet ovat kiinteästi koodattuja ja ne ovat samoja kaikille käyttäjille, joten käyttämällä tuotteen tai skenaarion nimeä asiakkaittesi on helpompaa löytää ne.

### <a name="additional-template-tips"></a>Muita mallia koskevia vihjeitä
* Varmista, että kyselyihin määritetyt parametrit ovat merkityksellisiä loppukäyttäjille
* Mieti, kuinka kauan loppukäyttäjä odottaa ajoitetun päivityksen päättymistä

![luo](media/template-content-pack-testing/createtemplate.png)

<a name="submission"></a>

## <a name="submission"></a>Lähettäminen
[Microsoft AppSourcen](https://appsource.microsoft.com/partners/list-an-app) kautta tehtävän lähetysprosessin avulla voit julkaista mallisisältöpakettisi palvelusisältöpakettien valikoimaan PowerBI.comissa sekä lisätä sisältöpakettisi [Microsoft AppSourcen](http://appsource.microsoft.com) luetteloon.

### <a name="before-submission"></a>Ennen lähettämistä
* Tarkista sisällöntuottamisen vihjeet kullekin artefaktille sisältöpaketissa
* Testaa ja muodosta yhteys useilla eri tileillä ja tietoehdoilla. (Ohita tämä vaihe, jos olet kehittänyt oman, mukautetun [Tietoyhdistimen](https://aka.ms/DataConnectors))
* Tarkastele kaikkia visualisointeja ja tarkasta kohteiden oikeinkirjoitus huolellisesti
* Varmista, että sisältöpaketti reagoi hyvin Kysymyksiin ja vastauksiin. Suosittelemme testaamaan vähintään 30 erilaista kysymystä kaikkialla tietomallissa. (Ohita tämä vaihe, jos olet kehittänyt oman, mukautetun [Tietoyhdistimen](https://aka.ms/DataConnectors))

### <a name="submission"></a>Lähettäminen
Kun olet valmis lähettämään, käy [Sovellusten lähetyssivulla](https://appsource.microsoft.com/partners/list-an-app) AppSourcessa ja lähetä tietosi. Varmista, että valitset Power BI:n käytettävissä olevien tuotteiden luettelosta

Power BI -tiimi tarkastaa lähettämäsi tiedot ja ottavat sinuun yhteyttä varmistaakseen, että kaikki artefaktit ovat lähetyksen vaatimusten mukaisia. Valmistumisen jälkeen teemme lisäksi toimitettujen koontinäytön ja raporttien laadunvarmistuksen, jotta voimme varmistaa, että ne ovat sovelluksessa kuvaillun liiketoimintaskenaarion mukaisia.

### <a name="updates"></a>Päivitykset
Sisältöpaketin päivittäminen tapahtuu samanlaisella työnkululla kuin alkuperäinenkin lähetys. 

