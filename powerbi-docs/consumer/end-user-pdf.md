---
title: Raporttien vieminen PDF-muotoon
description: Lue ohjeet siihen, miten voit viedä Power BI -raportin PDF-tiedostona.
author: mihart
manager: kvivek
ms.custom: ''
ms.reviewer: cmfinlan
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 02/14/2019
ms.author: mihart
LocalizationGroup: Share your work
ms.openlocfilehash: e15cb6e09ff493512bb1b87939004c851b31fa10
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/16/2019
ms.locfileid: "61047967"
---
# <a name="export-reports-from-power-bi-to-pdf"></a>Raporttien vieminen Power BI:stä PDF-muotoon
Power BI:llä voit julkaista raportin PDF-muodossa ja luoda helposti Power BI -raporttiisi perustuvan PDF-tiedoston. Kun **viet PDF-muotoon**, jokaisesta Power BI -raportin sivusta tulee yksittäinen sivu PDF-tiedostossa.

## <a name="how-to-export-your-power-bi-report-to-pdf"></a>Ohjeet Power BI -raportin viemiseksi PDF-muotoon
Valitse Power BI -palvelussa raportti, joka näytetään kankaalla. Voit myös valita raportin aloitussivulta, sovelluksista tai vasemman siirtymisruudun mistä tahansa osasta.

1. Valitse valikkoriviltä **Tiedosto** > **Vie PDF-muotoon**.

    ![Tiedosto-kohdan valitseminen valikkopalkista, nuoli osoittamassa Vie PDF-muotoon -kohtaa](media/end-user-pdf/power-bi-export-pdf.png)

    Näkyviin tulee ponnahdusikkuna, jossa on vaihtoehtoina **Nykyinen näkymä** ja **Oletusnäkymä**.  **Nykyinen näkymä** vie raportin nykyisessä tilassa, johon sisältyvät ne aktiiviset muutokset, joita olet tehnyt osittajan ja suodattimen arvoihin.  Useimmat käyttäjät valitsevat tämän vaihtoehdon.  Vaihtoehtoisesti voit valita **Oletusnäkymä**-vaihtoehdon, joka vie raportin sen alkuperäisessä tilassa (jossa laatija on jakanut sen) eikä sisällä mitään alkuperäiseen tilaan tekemiäsi muutoksia.
    
    Ponnahdusikkunassa on myös valintaruutu, jossa voit valita, viedäänkö raportin piilotetut välilehdet.  Valitse tämä valintaruutu, jos haluat viedä vain sellaiset raportin välilehdet, joita voit tarkastella selaimessasi.  Jos haluat viedä myös kaikki piilotetut välilehdet, voit jättää tämän valintaruudun valitsematta.  Jos valintaruutu näkyy harmaana, raportissa ei ole piilotettuja välilehtiä.  Kun olet tehnyt valintasi, jatka napsauttamalla Vie-painiketta.
    
    Oikeassa yläkulmassa näytetään edistymispalkki. Vieminen voi kestää muutamia minuutteja, minkä aikana voit jatkaa Power BI:n käyttöä.

    ![Viennin edistymisilmoitus](media/end-user-pdf/power-bi-export-message.png)

    Kun vieminen on valmis, ilmoituspalkissa kerrotaan, että Power BI -palvelu on suorittanut viennin.

2. Tiedostosi on käytettävissä sijainnissa, jossa selain näyttää ladatut tiedostot. Seuraavassa kuvassa se näkyy selainikkunan alareunan lataukset-palkissa.

    ![Ladatun tiedoston sijainti](media/end-user-pdf/power-bi-save-file.png)

Siinä kaikki. Voit ladata tiedoston ja avata sen millä tahansa PDF-lukuohjelmalla, esimerkiksi Microsoft Edgeen sisältyvällä PDF-lukuohjelmalla.


## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat
Huomioi seuraavat seikat ja rajoitukset, kun käytät **Vie PDF-muotoon** -toimintoa.

* **R-visualisointeja** ei tällä hetkellä tueta. Nämä visualisoinnit ovat tyhjiä PDF-tiedostossa. Niiden tilalla näytetään virheilmoitus.  

* **Sertifioituja** **mukautettuja visualisointeja** tuetaan. Saat lisätietoja sertifioiduista mukautetuista visualisoinneista, mukaan lukien sertifioinnin hakemisesta visualisoinnille, artikkelista [Mukautetun visualisoinnin sertifiointi](../power-bi-custom-visuals-certified.md). Mukautettuja visualisointeja, joita ei ole sertifioitu, ei tueta. Niiden tilalla näytetään virheilmoitus PDF-tiedostossa.   

* Yli 30 raporttisivua sisältäviä raportteja ei tällä hetkellä voi viedä.

* Raportin vieminen PDF-muotoon saattaa kestää muutamia minuutteja. Kestoon vaikuttavat mm. raportin rakenne ja Power BI -palvelun senhetkinen kuormitus.

* Jos **Vie PDF-muotoon** -valikkovaihtoehtoa ei ole käytettävissä Power BI -palvelussa, syy on todennäköisesti se, että vuokraajan järjestelmänvalvoja on poistanut toiminnon käytöstä. Saat lisätietoja ottamalla yhteyttä vuokraajan järjestelmänvalvojaan.

* Taustakuvat rajataan kaavion raja-alueen mukaiseksi. Suosittelemme, että poistat taustakuvat ennen PDF-muotoon viemistä.

* PDF-muotoon ei voi julkaista raportteja, jotka ovat vuokraajan Power BI -toimialueen ulkopuolisen käyttäjän omistamia (esimerkiksi organisaation ulkopuolisen henkilön omistama raportti, joka on jaettu kanssasi).

* Jos jaat koontinäytön organisaatiosi ulkopuoliselle henkilölle (joka ei ole Power BI -vuokraajasi toimialueella), kyseinen henkilö ei voi viedä jaettuun koontinäyttöön liittyviä raportteja PDF-muotoon. Jos olet esimerkiksi aaron@contoso.com, voit jakaa sisältöä käyttäjän cassie@cohowinery.com kanssa. cassie@cohowinery.com ei kuitenkaan voi viedä siihen liittyviä raportteja PDF-muotoon.

* Kun PDF-muotoon viedään raportteja, jotka sisältävät taustakuvan, kuva saattaa vääristyä viennissä, jos Sivun tausta -asetuksena käytetään ”Normaali”- tai ”Täyttö”-vaihtoehtoa.  Parhaan tuloksen varmistamiseksi on suositeltavaa käyttää ”Sovita”-asetusta, jolloin vältetään vietyyn tiedostoon liittyvät ongelmat.

* Power BI -palvelu käyttää PDF-viennin kielenä Power BI:n kieliasetuksen kieltä. Jos tarkistaa kieliasetuksesi tai muuttaa sitä, valitse hammasrataskuvake > **Asetukset** > **Yleiset** > **Kieli**.

* URL-suodattimia ei oteta tällä hetkellä huomioon, kun valitset viennin kohdalla ”Nykyiset arvot”.

## <a name="next-steps"></a>Seuraavat vaiheet
[Raportin tulostaminen](end-user-print.md)
