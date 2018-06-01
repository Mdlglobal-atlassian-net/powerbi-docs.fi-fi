---
title: Raporttinäkymä Power BI Desktopissa
description: Raporttinäkymä Power BI Desktopissa
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: af10699ea30b9d8e8dd8e3495860c43387a7e0be
ms.sourcegitcommit: 93e7362fc47319959b6992dfd037effdf831d010
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/21/2018
ms.locfileid: "30975662"
---
# <a name="report-view-in-power-bi-desktop"></a>Raporttinäkymä Power BI Desktopissa
Jos olet työskennellyt Power BI:lla tiedät, miten helppoa on luoda raportteja, jotka sisältävät dynaamisia perspektiivejä ja merkityksellisiä tietoja tietoihisi. Power BI on sisältää myös kehittyneempiä ominaisuuksia Power BI Desktopissa. Power BI Desktopin avulla voit luoda kehittyneitä kyselyitä, koota tietoja useista lähteistä, luoda taulukoiden välisiä yhteyksiä ja paljon muuta.

Power BI Desktop sisältää **raporttinäkymän**, jossa voit luoda minkä tahansa määrän raporttisivuja visualisointien avulla. Raportti-näkymä on rakenteeltaan pääpiirteittäin sama kuin raportin muokkausnäkymä Power BI -palvelussa. Voit esimerkiksi siirtää, kopioida ja liittää sekä yhdistää visualisointeja jne.

Ero näkymien välillä on, että käyttäessäsi Power BI Desktop -versiota voit työstää kyselyitäsi ja mallintaa tietosi, jotta ne varmasti tukevat raporttiesi parhaita merkityksellisiä tietoja. Voit sen jälkeen tallentaa Power BI Desktop -tiedoston minne tahansa, esimerkiksi paikalliselle asemalle tai pilvipalveluun.

## <a name="lets-take-a-look"></a>Katsotaanpa!
Kun lataat tietoja Power BI Desktopiin ensimmäisen kerran, näkyviin tulee **Raporttinäkymä** ja tyhjä pohja.

![](media/desktop-report-view/pbi_reportviewinpbidesigner_reportview.png)

Voit vaihdella **Raporttinäkymää**, **Tietonäkymää** ja **Suhde-näkymää** valitsemalla vasemmanpuoleisessa siirtymispalkissa olevan kuvakkeen:

![](media/desktop-report-view/pbi_reportviewinpbidesigner_changeview.png)

Kun olet lisännyt tietoja, voit lisätä kenttiä uuteen visualisointiin pohjalle.

![](media/desktop-report-view/pbid_reportview_addvis.gif)

Voit muuttaa visualisoinnin tyyppiä, voit valita sen **Visualisoinnit**-ryhmästä valintanauhasta tai voit valita hiiren kakkospainikkeella eri tyyppejä **Muuta visualisoinnin tyyppiä** -kuvakkeesta.

![](media/desktop-report-view/pbid_reportview_changevis.gif)

> [!TIP]
> Muista kokeilla eri visualisointityyppejä. On tärkeää, että visualisointisi välittävät tietoja selvästi.
> 
> 

Raportissa on ainakin yksi tyhjä sivu, josta aloittaa. Sivut näkyvät navigointiruudussa alustan vasemmalla puolella. Voit lisätä sivulle kaikenlaisia visualisointeja, mutta on tärkeää, ettet tee niitä liikaa. Liian monta visualisointia yhdellä sivulla näyttää levottomalta, ja oikeiden tietojen löytäminen voi olla vaikeaa. Voit lisätä uusia sivuja raporttiin. Napsauta **Uusi sivu** valintanauhasta.

![](media/desktop-report-view/pbidesignerreportviewnewpage.png)

Voit poistaa sivun napsauttamalla **X** sivun välilehdellä raporttinäkymän alareunassa.

![](media/desktop-report-view/pbi_reportviewinpbidesigner_deletepage.png)

> [!NOTE]
> Raportteja tai visualisointeja ei voi kiinnittää koontinäyttöön Power BI Desktopista. Sitä varten sinun on suoritettava [Julkaise Power BI Desktopista](desktop-upload-desktop-files.md) Power BI-sivustolle.

## <a name="hide-report-pages"></a>Raporttisivujen piilottaminen

Kun luot raportin, voit myös piilottaa sivuja raportista. Tämä voi olla hyödyllistä, jos haluat luoda raporttiin piilossa olevia tietoja tai visualisointeja, etkä halua, että kyseiset sivut näkyvät muille käyttäjille, esimerkiksi kun luot taulukoita tai tukevia visualisointeja, joita käytetään raportin muilla sivuilla. On olemassa monia muitakin syitä, joiden takia haluat ehkä luoda raporttisivun ja sitten piilottaa tietoja raportista, jonka haluat julkaista. 

Raporttisivun piilottaminen on helppoa. Napsautat vain hiiren kakkospainikkeella Raportin sivu -välilehteä ja valitset **Piilota** valikosta, joka tulee näkyviin.

![](media/desktop-report-view/report-view_05.png)

Ota muutamia seikkoja huomioon, kun piilotat raporttisivua:

* Näet edelleen piilotetun raporttinäkymän **Power BI Desktopissa**, vaikka sivun otsikko näkyy harmaana. Seuraavassa kuvassa sivu 4 on piilotettu.

    ![](media/desktop-report-view/report-view_06.png)

* *Et voi* nähdä piilotettua raporttisivua, kun tarkastelet raporttia **Power BI -palvelussa**.

* Raporttisivun piilottaminen *ei* ole turvatoimi. Käyttäjät pääsevät edelleen sivulle ja sen sisältöön alirakenneraporttien muiden menetelmien avulla.

* Kun sivu on piilotettu, Näytä tilassa ei enää näy siirtymisnuolia.

