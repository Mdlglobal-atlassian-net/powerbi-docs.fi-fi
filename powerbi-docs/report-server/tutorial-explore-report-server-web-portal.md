---
title: 'Opetusohjelma: Tutustu Power BI -raporttipalvelimeen VM:ssä'
description: Tässä opetusohjelmassa opit luomaan näennäiskoneen Power BI -raporttipalvelimen ollessa jo asennettu sekä tutkimaan verkkoportaalia.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: tutorial
ms.date: 05/06/2019
ms.author: maggies
ms.openlocfilehash: 312b86f9e0c0dda0c9c943520c74286e0458acef
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73859242"
---
# <a name="tutorial-explore-the-power-bi-report-server-web-portal-in-a-vm"></a>Opetusohjelma: Power BI -raporttipalvelimen verkkoportaaliin tutustuminen näennäiskoneella
Tässä opetusohjelmassa luot Azure-virtuaalikoneen Power BI -raporttipalvelimen ollessa jo asennettu, jotta voit tutustua Power BI- ja sivutettujen näyteraporttien ja suorituskykyilmaisimien tarkasteluun, muokkaamiseen ja hallintaan.

![Raporttipalvelimen verkkoportaali](media/tutorial-explore-report-server-web-portal/power-bi-report-server-browser-in-vm-no-numbers.png)

Tässä opetusohjelmassa suoritettavat tehtävät:

> [!div class="checklist"]
> * Näennäiskoneen luominen ja siihen yhdistäminen
> * Power BI -raporttipalvelimen verkkoportaaliin tutustuminen
> * Suosikkikohteen merkitseminen tunnisteella
> * Power BI -raportin tarkastelu ja muokkaaminen
> * Sivutetun raportin tarkastelu, hallinta ja muokkaaminen
> * Excel-työkirjan tarkastelu Excel Onlinessa

Tämä opetusohjelma edellyttää, että sinulla on Azure-tilaus. Jos sinulla ei ole tilausta, [luo ilmainen tili](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) ennen aloittamista.

## <a name="create-a-power-bi-report-server-vm"></a>Power BI -raporttipalvelimen näennäiskoneen luominen

Power BI -tiimi on onneksi luonut näennäiskoneen, johon Power BI -raporttipalvelin on jo asennettu.

1. Valitse Power BI -raporttipalvelin Azure Marketplacessa. Tämä linkki avaa sen suoraan: [Power BI -raporttipalvelin](https://azuremarketplace.microsoft.com/marketplace/apps/reportingservices.technical-preview?tab=Overview).  

2. Valitse **Hanki se nyt**.
3. Hyväksy tarjoajan käyttöehdot ja tietosuojakäytäntö valitsemalla **Jatka**.

4. Valitse **Luo**.

    ![Power BI -raporttipalvelimen näennäiskoneen luominen](media/tutorial-explore-report-server-web-portal/power-bi-report-server-create.png)

5. Kirjoita **Vaihe 1 Perusteet** -kohdassa **Näennäiskoneen nimi** -kentän arvoksi **reportservervm**.

    Power BI -raporttipalvelimen näennäiskoneen nimi ei voi sisältää yhdysviivoja.

5. Luo käyttäjänimi ja salasana.

6. Valitse **Resurssiryhmä**-kohdassa **Luo uusi** ja anna sen nimeksi **reportserverresourcegroup** > **OK**.

    Jos seuraat opetusohjelmaa useamman kuin yhden kerran, sinun on annettava resurssiryhmälle eri nimi ensimmäisen kerran jälkeen. Et voi käyttää resurssiryhmän nimeä kahdesti samassa tilauksessa. 

    ![Nimeä näennäiskone ja resurssiryhmä](media/tutorial-explore-report-server-web-portal/power-bi-report-server-create-resource-group.png)

7. Säilytä muut oletusarvot > **OK**.

8. Säilytä **Vaihe 2 Asetukset** -kohdan oletusasetukset > **OK**.
 
    **SQL-tallennustilin** ja **diagnostiikan tallennustilin** arvojen on myös oltava yksilöllisiä. Jos seuraat opetusohjelmaa useamman kuin yhden kerran, sinun on annettava niille eri nimi.

9. Tarkista valintasi **Vaihe 3 Yhteenveto** -kohdassa > **OK**.

10. Tarkista **Vaihe 4 Osta** -kohdassa käyttöehdot ja tietosuojakäytäntö > **Luo**.

    **Käyttöönottoa lähetetään Power BI -raporttipalvelimeen** -käsittely saattaa kestää muutamia minuutteja.

## <a name="connect-to-your-virtual-machine"></a>Muodosta yhteys näennäiskoneeseen

1. Valitse Azuren siirtymisruudussa **Näennäiskoneet**. 

2. Kirjoita **Suodata nimen mukaan** -ruutuun ”raportti”. 

3. Valitse näennäiskone, jonka nimi on **REPORTSERVERVM**.

    ![Näytä näennäiskone](media/tutorial-explore-report-server-web-portal/power-bi-report-server-view-virtual-machine.png)

4. Valitse REPORTSERVERVM-näennäiskoneen kohdalta **Yhdistä**.

    ![Yhdistä näennäiskoneeseen](media/tutorial-explore-report-server-web-portal/power-bi-report-server-connect-to-virtual-machine.png)

5. Säilytä oletusarvot **Yhdistä näennäiskoneeseen** -ruudussa ja valitse **Lataa RDP-tiedosto**.

1. Valitse **Etätyöpöytäyhteys**-valintaikkunasta **Yhdistä**.

6. Anna näennäiskonetta varten luomasi käyttäjänimi ja salasana > **OK**.

7. Seuraavassa valintaikkunassa ilmoitetaan, että **etätietokonetta ei tunnisteta**. Valitse **Kyllä**.

   Uusi näennäiskone avautuu.

## <a name="power-bi-report-server-on-the-vm"></a>Power BI -raporttipalvelin näennäiskoneella

Kun näennäiskone avautuu, näet työpöydällä seuraavat kohteet.

![Power BI -raporttipalvelimen näennäiskone käynnistyy](media/tutorial-explore-report-server-web-portal/power-bi-report-server-vm-5-numbers.png)

|Luku  |Merkitys  |
|---------|---------|
|![Numero 1](media/tutorial-explore-report-server-web-portal/number-1.png) | Power BI -malliraportit (.PBIX) |
|![Numero 2](media/tutorial-explore-report-server-web-portal/number-2.png) | Linkki Power BI -raporttipalvelimen ohjeisiin |
|![Numero 3](media/tutorial-explore-report-server-web-portal/number-3.png) | Käynnistää Power BI -raporttipalvelimelle optimoidun Power BI Desktopin (tammikuu 2019) |
|![Numero 4](media/tutorial-explore-report-server-web-portal/number-4.png) | Avaa Power BI -raporttipalvelimen verkkoportaalin selaimessa |
|![Numero 5](media/tutorial-explore-report-server-web-portal/number-5.png) | Käynnistää SQL Server Data Tools -työkalun sivutettujen (. RDL) raporttien luomista varten |

Kaksoisnapsauta **Raporttipalvelimen verkkoportaali** -kuvaketta. `https://localhost/reports/browse` avataan selaimella. Verkkoportaalista näet tyypin mukaan ryhmitellyt tiedostot. 

![Power BI -raporttipalvelimen verkkoportaali](media/tutorial-explore-report-server-web-portal/power-bi-report-server-browser-in-vm.png)

|Luku  |Merkitys  |
|---------|---------|
|![Numero 1](media/tutorial-explore-report-server-web-portal/number-1.png) | Verkkoportaalissa luodut suorituskykyilmaisimet |
|![Numero 2](media/tutorial-explore-report-server-web-portal/number-2.png) |  Power BI -malliraportit (.PBIX)  |
|![Numero 3](media/tutorial-explore-report-server-web-portal/number-3.png) | SQL Serverin mobiiliraportin julkaisijassa luodut mobiiliraportit  |
|![Numero 4](media/tutorial-explore-report-server-web-portal/number-4.png) |  Raportin muodostimessa tai SQL Server Data Tools -työkalussa luodut sivutetut raportit  |
|![Numero 5](media/tutorial-explore-report-server-web-portal/number-5.png) | Excel-työkirjat   | 
|![Numero 6](media/tutorial-explore-report-server-web-portal/number-6.png) | Sivutettujen raporttien tietolähteet | 


## <a name="tag-your-favorites"></a>Merkitse suosikkisi tunnisteella
Voit lisätä tunnisteen niihin raportteihin ja suorituskykyilmaisimiin, joiden haluat olevan suosikkeja. Ne on helpompi löytää, sillä ne on kaikki kerätty yhteen Suosikit-kansioon sekä verkkoportaalissa että Power BI -mobiilisovelluksissa. 

1. Valitse kolme pistettä ( **…** ) **Kate**-suorituskykyilmaisimen oikeasta yläkulmasta > **Lisää suosikkeihin**.
   
    ![Lisää suosikkeihin](media/tutorial-explore-report-server-web-portal/power-bi-report-server-add-to-favorites.png)
2. Valitse **Suosikit** verkkoportaalin valintanauhasta, niin näet sen verkkoportaalin Suosikit-sivulla olevien muiden suosikkien ohella.
   
    ![Näytä suosikit](media/tutorial-explore-report-server-web-portal/power-bi-report-server-favorites.png)

3. Palaa verkkoportaaliin valitsemalla **Selaa**.
   
## <a name="view-items-in-list-view"></a>Näytä kohteet luettelonäkymässä
Verkkoportaalin sisältö näkyy oletusarvoisesti ruutunäkymässä.

Voit siirtyä luettelonäkymään, jossa voit helposti siirtää tai poistaa useita kohteita samalla kertaa. 

1. Valitse **Ruudut** >  **-luettelo**.
   
    ![Vaihda näkymää](media/tutorial-explore-report-server-web-portal/report-server-web-portal-list-view.png)

2. Siirry takaisin ruutunäkymään: Valitse **Luettelo** > **Ruudut**.

## <a name="power-bi-reports"></a>Power BI -raportit

Verkkoportaalin kautta voit käynnistää Power BI Desktopin ja tarkastella ja käsitellä Power BI -raportteja.

### <a name="view-power-bi-reports"></a>Power BI -raporttien tarkastelu

1. Valitse verkkoportaalissa **Power BI -raportit** kohdasta **Asiakkaan yleiskatsausraportin malli**. Raportti avautuu selaimessa.

1. Valitse puukartasta Yhdysvallat, niin näet, miten toisiinsa liittyvät arvot korostetaan muissa visualisoinneissa.

    ![Power BI -raportti korostettuna](media/tutorial-explore-report-server-web-portal/power-bi-report-server-power-bi.png)

### <a name="edit-in-power-bi-desktop"></a>Muokkaa Power BI Desktopissa

1. Valitse **Muokkaa Power BI Desktopissa**.

1. Valitse **Salli**, jotta verkkosivusto voidaan avata tietokoneelle asennetulla ohjelmalla. 

     Raportti avataan Power BI Desktopissa. Huomaa yläpalkissa oleva nimi ”Power BI Desktop (tammikuu 2019)”. Kyseessä on Power BI -raporttipalvelimelle optimoitu versio.

    Käytä näennäiskoneelle asennettua Power BI Desktop -versiota. Et voi siirtyä toimialueiden välillä ladataksesi raportin palvelimelle.

3. Laajenna Asiakkaat-taulukko Kentät-ruudussa ja vedä Ammatti-kenttä Raporttitason suodattimiin.

    ![Vedä kenttä Suodattimet-ruutuun](media/tutorial-explore-report-server-web-portal/power-bi-report-server-desktop-filter.png)

1. Tallenna raportti.

1. Palaa raporttiin selaimella ja valitse selaimen **Päivittä**-kuvake.

    ![Selaimen Päivitä-kuvake](media/tutorial-explore-report-server-web-portal/power-bi-report-server-browser-refresh.png)

8. Laajenna oikealla oleva **Suodattimet**-ruutu, jotta voit nähdä lisäämäsi **Ammatti**-suodattimen. Valitse **Ammattilainen**.

    ![Suodatettu Power BI -raportti](media/tutorial-explore-report-server-web-portal/power-bi-report-server-power-bi-filtered.png)

3. Palaa verkkoportaaliin valitsemalla **Selaa**.

## <a name="paginated-rdl-reports"></a>Sivutetut raportit (.RDL)

Voit tarkastella ja hallita sivutettuja raportteja ja käynnistää Raportin muodostimen verkkoportaalista.

### <a name="manage-a-paginated-report"></a>Sivutetun raportin hallinta

1. Valitse verkkoportaalissa **Myyntitilaus** > **Hallinta** -kohdan viereisestä **Sivutetut raportit** -kohdasta **Enemmän vaihtoehtoja** (...).

1. Valitse **Parametrit**, muuta **SalesOrderNumber**-arvon oletukseksi **SO50689** > **Käytä**.

   ![Raportin parametrien asettaminen](media/tutorial-explore-report-server-web-portal/power-bi-report-server-set-parameters.png)

3. Palaa verkkoportaaliin valitsemalla **Selaa**.

### <a name="view-a-paginated-report"></a>Tarkastele sivutettua raporttia

1. Valitse **Myyntitilaus** verkkoportaalissa.
 
3.  Se avaa asettamasi **Tilaus**-parametrin **SO50689**. 

    ![Sivutetun raportin parametri](media/tutorial-explore-report-server-web-portal/power-bi-report-server-paginated.png)

    Voit muuttaa kyseisen parametrin ja muut parametrit tästä muuttamatta oletusasetuksia.

1. Valitse **Tilaus** **SO48339** > **Näytä raportti**.

4. Huomaa, että tämä on sivu 1/2. Voit siirtyä toiselle sivulle valitsemalla oikean nuolen. Taulukko jatkuu toisella sivulla.

    ![Sivutetun raportin sivu 2/2](media/tutorial-explore-report-server-web-portal/power-bi-report-server-paginated-2-of-2.png)

5. Palaa verkkoportaaliin valitsemalla **Selaa**.

### <a name="edit-a-paginated-report"></a>Sivutetun raportin muokkaaminen

Voit muokata sivutettuja raportteja Raportin muodostimessa, jonka voit käynnistää suoraan selaimesta.

1. Valitse verkkoportaalissa **Myyntitilaus** > **Muokkaa raportin muodostimessa** -kohdan vierestä **Enemmän vaihtoehtoja** (...).

1. Valitse **Salli**, jotta verkkosivusto voidaan avata tietokoneelle asennetulla ohjelmalla.

1. Myyntitilausraportti avautuu raportin muodostimen suunnittelunäkymässä.

    ![Suunnittelunäkymä, sivutettu raportti](media/tutorial-explore-report-server-web-portal/power-bi-report-server-paginated-design-view.png)

1. Esikatsele raporttia valitsemalla **Suorita**.

    ![Sivutetun raportin esikatselu](media/tutorial-explore-report-server-web-portal/power-bi-report-server-paginated-preview.png)

5. Sulje Raportin muodostin ja palaa selaimeen.

## <a name="view-excel-workbooks"></a>Excel-työkirjojen tarkastelu

Voit tarkastella ja käsitellä Excel-työkirjoja Excel Onlinessa Power BI -raporttipalvelimella. 

1. Valitse Excel-työkirja **Office Liquidation Sale.xlsx**. Työkirja saattaa pyytää tunnistetietoja. Valitse **Peruuta**. 
    Työkirja avautuu verkkoportaalissa.
1. Valitse osittajasta **Laite**.

    ![Excel Online verkkoportaalissa](media/tutorial-explore-report-server-web-portal/power-bi-report-server-excel-online.png)

1. Palaa verkkoportaaliin valitsemalla **Selaa**.

## <a name="clean-up-resources"></a>Resurssien tyhjentäminen

Opetusohjelma on nyt valmis. Poista vielä resurssiryhmä, näennäiskone ja kaikki niihin liittyvät resurssit. 

- Voit tehdä tämän valitsemalla näennäiskoneen resurssiryhmän ja valitsemalla sitten **Poista**.

## <a name="next-steps"></a>Seuraavat vaiheet

Loit tässä opetusohjelmassa näennäiskoneen Power BI -raporttipalvelimella. Kokeilit joitain verkkoportaalin toiminnoista ja avasit Power BI -raportin ja sivutetun raportin asianmukaisissa muokkaustyökaluissa. Tälle näennäiskoneelle on asennettu SQL Server Analysis Services -tietolähteitä, joten voit yrittää luoda omia Power BI- ja sivutettuja raportteja samoista tietolähteistä. 

Jatkamalla saat lisätietoja raporttien luomisesta Power BI -raporttipalvelimeen.

> [!div class="nextstepaction"]
> [Power BI -raportin luominen Power BI -raporttipalvelimeen](./quickstart-create-powerbi-report.md)



