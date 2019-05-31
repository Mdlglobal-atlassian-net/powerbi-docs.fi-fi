---
title: Raportin tarkasteleminen Power BI:ssä
description: Raportit Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 5/10/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 02652bd027d7dab8a40d77fb92c5aae8f09d8820
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607872"
---
# <a name="reports-in-power-bi"></a>Raportit Power BI:ssä
## <a name="what-is-a-power-bi-report"></a>Mikä on Power BI -raportti?
Power BI- ***raportin*** on usean perspektiivin tietojoukkonäkymä, visualisointeja, jotka edustavat eri havaintoja ja merkityksellisiä tietoja tietojoukosta.  Raportissa voi olla yksittäinen visualisointi tai sivukaupalla visualisointeja. Työn roolistasi riippuen voit olla joku, joka *suunnitteluista* raportteja ja/tai voit olla joku, joka *kuluttaa* eli käyttää raportteja.

![raporttisivu](./media/end-user-reports/power-bi-report.png)

Tässä raportissa on kuusi sivua (tai välilehteä), ja tarkastelemme olet tällä hetkellä asenne-sivun. Tällä sivulla on 6 eri visualisointeja ja sivun otsikko.  

Jos olet uusi Power BI:n käyttäjä, saat hyvän pohjan sen käyttöön lukemalla [Power BI:n peruskäsitteet](end-user-basic-concepts.md).

Raportit ovat saatavilla tarkastella, jakaminen ja lisäämiseksi mobiililaitteissa. Jos haluat lisätietoja, katso [Power BI-mobiiliraportteja](mobile/mobile-reports-in-the-mobile-apps.md).

## <a name="advantages-of-reports"></a>Raporttien edut
Raportti perustuu yhteen tietojoukkoon. Raportin visualisointeja luodaan raportin *suunnittelijat* ja nugget tietoja. Visualisoinnit eivät ole staattisia; Voit käsitellä visualisointeja ja suodattimia, kun pureudut tietoihin ja merkityksellisiä tietoja ja vastauksia. Kuten koontinäyttö mutta lisätietoja-niin, raportti on vuorovaikutteinen ja mukautettava, ja visualisoinnit päivittyvät sitä mukaa kun pohjana olevat tiedot muuttuvat.

### <a name="safely-interact-with-content"></a>Sisällön turvallinen käyttö
Koska voit tarkastella ja käsitellä-sisältöä, suodattamista, mittayksikkösovellukseen, tilaat, ja vieminen, rest varmistaa; työsi ei vaikuta pohjana olevaa tietojoukkoa tai alkuperäisen jaettu sisältö (koontinäytöt, raportit ja sovellukset).
 
> [!NOTE]
> Muista, että tietoja ei voi osu. Power BI on hyvä paikka voit tutkia ja kokeile huolehtimatta, sinun ”rikkoa” mitään.

### <a name="save-your-changes-or-revert-to-the-default-settings"></a>Tallenna muutokset tai palauta oletusasetukset
Ei tarkoita ei voi tallentaa muutokset. Voit kuitenkin muutokset vaikuttavat vain sisällön näkymä. Palautumisen alkuperäiseen oletusnäkymää on yhtä helppoa kuin valitsemalla Palauta oletusasetukseen-painike.

## <a name="dashboards-versus-reports"></a>Koontinäytöt vs. raportit
[Koontinäyttöjen](end-user-dashboards.md) sekoitetaan usein raportteihin, koska nekin ovat pohjia visualisoinnit ovat. Niiden välillä on kuitenkin merkittäviä eroja.  

| **Ominaisuus** | **Koontinäytöt** | **Raportit** |
| --- | --- | --- |
| Sivut |Yksi sivu |Yksi tai useampi sivu |
| Tietolähteet |Yksi tai useampi raportti ja yksi tai useampi tietojoukko koontinäyttöä kohden |Yksi tietojoukko raporttia kohden |
| Suodatus |Ei voi suodattaa tai jakaa sektoreihin |Monta eri tapaa suodattaa, korostaa ja jakaa sektoreihin |
| Hälytysten asettaminen |Voit luoda hälytyksiä lähetettäväksi sähköpostina, kun tietyt ehdot täyttyvät |Ei |
| Ominaisuus |Voit määrittää jonkin koontinäytön ”esittelyssä” olevaksi koontinäytöksi |Esittelyssä olevaa raporttia ei voida luoda |
| Pohjana olevat tietojoukkojen taulukot ja kentät ovat näkyvissä |Ei. Voit viedä tietoja, mutta etänäe tietojoukon taulukoita ja kenttiä itse koontinäytössä. |Kyllä. Näet tietojoukon taulukot ja kentät ja arvot, jotka sinulla on oikeudet nähdä. |
| Mukauttaminen |Ei  |Voit suodattaa, viedä, tarkastele aiheeseen liittyvää sisältöä, Lisää kirjanmerkkejä, luoda QR-koodeja, analysoida Excelissä ja paljon muuta.   |

<!--| Available in Power BI Desktop |No |Yes, can create and view reports in Desktop |
| Pinning |Can pin existing visuals (tiles) only from current dashboard to your other dashboards |Can pin visuals (as tiles) to any of your dashboards. Can pin entire report pages to any of your dashboards. | -->

## <a name="report-creators-and-report-consumers"></a>Raportin ***laatijat*** ja raportin ***kuluttajat***
Roolistasi riippuen saatat olla *suunnittelutyökalu*, henkilö, joka luo raportteja omaan käyttöönsä tai jakaa niitä työtovereidensa kanssa. Haluat oppia, miten raportteja luodaan ja jaetaan. Tai voit olla henkilö, joka saa raportteja muilta. Haluat oppia ymmärtämään ja käyttämään raportteja. Jos olet raportin **kuluttajan**, nämä linkit ovat puolestasi. 

* Aloita [Power BI -palvelun esittelyllä](end-user-basic-concepts.md) niin tiedät, mistä raportit ja raporttityökalut löytyvät.
* Opi [avaamaan raportti](end-user-report-open.md) ja tutustu kaikkeen [lukunäkymässä](end-user-reading-view.md) käytettävissä olevaan vuorovaikutukseen.
* Tutustu raportteihin paremmin tutustumalla johonkin [malleistamme](../sample-tutorial-connect-to-the-samples.md).  
<!--* Don't need the report any more? You can [remove it](../service-delete.md).-->
* Katso, mitä tietojoukkoa raportissa käytetään ja missä koontinäytöissä on raportista kiinnitettyjä ruutuja, [tarkastelemalla asiaan liittyvää sisältöä](end-user-related.md).

> [!TIP]
> Jos et löytänyt etsimääsi täältä, selaa kaikkia *raportteihin* liittyviä aiheita vasemmalla olevan sisällysluettelon avulla.
> 
> 

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](../power-bi-overview.md) 

[Power BI:n peruskäsitteet](end-user-basic-concepts.md)

