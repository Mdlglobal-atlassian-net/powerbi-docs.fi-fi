---
title: Raporttinäkymä Power BI Desktopissa
description: Raporttinäkymä Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/19/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: c76dfc45437fdc2406c89e41a4a076d9ef4e7a44
ms.sourcegitcommit: 200291eac5769549ba5c47ef3951e2f3d094426e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/19/2019
ms.locfileid: "71142199"
---
# <a name="report-view-in-power-bi-desktop"></a>Raporttinäkymä Power BI Desktopissa
Jos olet työskennellyt Power BI:lla tiedät, miten helppoa on luoda raportteja, jotka sisältävät dynaamisia perspektiivejä ja merkityksellisiä tietoja tietoihisi. Power BI on sisältää myös kehittyneempiä ominaisuuksia Power BI Desktopissa. Power BI Desktopin avulla voit luoda kehittyneitä kyselyitä, koota tietoja useista lähteistä, luoda taulukoiden välisiä yhteyksiä ja paljon muuta.

Power BI Desktop sisältää **raporttinäkymän**, jossa voit luoda minkä tahansa määrän raporttisivuja visualisointien avulla. Raportti-näkymä on rakenteeltaan pääpiirteittäin sama kuin raportin muokkausnäkymä Power BI -palvelussa. Voit esimerkiksi siirtää, kopioida ja liittää sekä yhdistää visualisointeja jne.

Ero näkymien välillä on, että käyttäessäsi Power BI Desktop -versiota voit työstää kyselyitäsi ja mallintaa tietosi, jotta ne varmasti tukevat raporttiesi parhaita merkityksellisiä tietoja. Voit sen jälkeen tallentaa Power BI Desktop -tiedoston minne tahansa, esimerkiksi paikalliselle asemalle tai pilvipalveluun.

## <a name="lets-take-a-look"></a>Katsotaanpa!
Kun lataat tietoja Power BI Desktopiin ensimmäisen kerran, näkyviin tulee **Raporttinäkymä** ja tyhjä pohja.

![Power BI Desktop](media/desktop-report-view/pbi_reportviewinpbidesigner_reportview.png)

Voit vaihdella **Raporttinäkymää**, **Tietonäkymää** ja **Suhde-näkymää** valitsemalla vasemmanpuoleisessa siirtymispalkissa olevan kuvakkeen:

![Raporttinäkymäkuvake](media/desktop-report-view/pbi_reportviewinpbidesigner_changeview.png)

Kun olet lisännyt tietoja, voit lisätä kenttiä uuteen visualisointiin pohjalle.

![Lisää visualisointi vetämällä Kentät-ruudusta](media/desktop-report-view/pbid_reportview_addvis.gif)

Voit muuttaa visualisoinnin tyyppiä, voit valita sen **Visualisoinnit**-ryhmästä valintanauhasta tai voit valita hiiren kakkospainikkeella eri tyyppejä **Muuta visualisoinnin tyyppiä** -kuvakkeesta.

![Muuta visualisointia valitsemalla uusi](media/desktop-report-view/pbid_reportview_changevis.gif)

> [!TIP]
> Muista kokeilla eri visualisointityyppejä. On tärkeää, että visualisointisi välittävät tietoja selvästi.

Raportissa on ainakin yksi tyhjä sivu, josta aloittaa. Sivut näkyvät navigointiruudussa alustan vasemmalla puolella. Voit lisätä sivulle kaikenlaisia visualisointeja, mutta on tärkeää, ettet tee niitä liikaa. Liian monta visualisointia yhdellä sivulla näyttää levottomalta, ja oikeiden tietojen löytäminen voi olla vaikeaa. Voit lisätä uusia sivuja raporttiin. Napsauta **Uusi sivu** valintanauhasta.

![Uusi sivu -kuvake](media/desktop-report-view/pbidesignerreportviewnewpage.png)

Voit poistaa sivun napsauttamalla **X** sivun välilehdellä raporttinäkymän alareunassa.

![Sivun lisääminen raporttiin](media/desktop-report-view/pbi_reportviewinpbidesigner_deletepage.png)

> [!NOTE]
> Raportteja tai visualisointeja ei voi kiinnittää koontinäyttöön Power BI Desktopista. Sitä varten sinun on suoritettava [Julkaise Power BI Desktopista](desktop-upload-desktop-files.md) Power BI-sivustolle.

## <a name="copy-and-paste-between-reports"></a>Kopioiminen ja liittäminen raporttien välillä

Voit helposti ottaa visualisoinnin yhdestä Power BI Desktop -raportista ja liittää sen toiseen raporttiin. Kopioi raportin visualisointi **CTRL+C**-näppäinyhdistelmällä ja liitä sitten visualisointi toiseen Power BI Desktop -raporttiin käyttämällä **CTRL+V**-näppäinyhdistelmää. Voit valita yhden visualisoinnin kerrallaan tai voit valita sivun kaikki visualisoinnit kopioitaviksi ja sitten liittää ne Power BI Desktop -kohderaporttiin. 

Visualisointien kopiointi- ja liittämismahdollisuudesta on hyötyä henkilöille, jotka luovat ja päivittävät useita raportteja usein. Tiedostojen välillä kopioitaessa asetukset ja muotoilu, jotka on nimenomaan määritetty muotoiluruudussa, kopioituvat eteenpäin, kun taas teemaan tai oletusasetuksiin pohjautuvat visuaaliset elementit päivitetään automaattisesti vastaamaan kohderaportin teemaa. Kun siis saat muotoiltua visualisoinnin juuri haluamallasi tavalla, voit kopioida ja liittää kyseisen visualisoinnin uusiin raportteihin ja näin säilyttää muotoilun eteen tehdyn työn.

Jos mallin kentät ovat erilaisia, visualisoinnissa tulee näkyviin virhe sekä varoitus siitä, mitä kenttiä ei ole olemassa. Virhe on samanlainen kuin silloin, kun poistat kentän mallista, jota visualisointi käyttää. 

![Virhe visualisoinnin kopioinnissa tai liittämisessä – ei tietokenttä](media/desktop-report-view/report-view_07.png)

Virheen korjaamiseksi korvaa rikkinäiset kentät haluamillasi kentillä raportissa olevasta mallista, johon liitit visualisoinnin. Jos käytät mukautettua visualisointia, sinun on tuotava myös kyseinen mukautettu visualisointi kohderaporttiin.




## <a name="hide-report-pages"></a>Raporttisivujen piilottaminen

Kun luot raportin, voit myös piilottaa sivuja raportista. Tämä voi olla hyödyllistä, jos haluat luoda raporttiin piilossa olevia tietoja tai visualisointeja, etkä halua, että kyseiset sivut näkyvät muille käyttäjille, esimerkiksi kun luot taulukoita tai tukevia visualisointeja, joita käytetään raportin muilla sivuilla. On olemassa monia muitakin syitä, joiden takia haluat ehkä luoda raporttisivun ja sitten piilottaa tietoja raportista, jonka haluat julkaista. 

Raporttisivun piilottaminen on helppoa. Napsautat vain hiiren kakkospainikkeella Raportin sivu -välilehteä ja valitset **Piilota** valikosta, joka tulee näkyviin.

![Piilota sivu -vaihtoehto](media/desktop-report-view/report-view_05.png)

Ota muutamia seikkoja huomioon, kun piilotat raporttisivua:

* Näet edelleen piilotetun raporttinäkymän **Power BI Desktopissa**, vaikka sivun otsikko näkyy harmaana. Seuraavassa kuvassa sivu 4 on piilotettu.

    ![harmaana näkyvä piilotettu sivu](media/desktop-report-view/report-view_06.png)

* *Et voi* nähdä piilotettua raporttisivua, kun tarkastelet raporttia **Power BI -palvelussa**.

* Raporttisivun piilottaminen *ei* ole turvatoimi. Käyttäjät pääsevät edelleen sivulle ja sen sisältöön alirakenneraporttien muiden menetelmien avulla.

* Kun sivu on piilotettu, Näytä tilassa ei enää näy siirtymisnuolia.

