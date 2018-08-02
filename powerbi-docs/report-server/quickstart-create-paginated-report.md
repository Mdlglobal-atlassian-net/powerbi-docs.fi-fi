---
title: Sivutetun raportin luominen Microsoft Power BI -raporttipalvelimeen
description: Ohjeet sivutetun raportin luomiseen Power BI -raporttipalvelimelle helposti ja nopeasti.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: maggies
ms.openlocfilehash: e996b1399ff4dde96d122e747cf1f07db3a44876
ms.sourcegitcommit: fbb7924603f8915d07b5e6fc8f4d0c7f70c1a1e1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/02/2018
ms.locfileid: "34721819"
---
# <a name="create-a-paginated-report-for-power-bi-report-server"></a>Sivutetun raportin luominen Microsoft Power BI -raporttipalvelimeen
Nimensä mukaisesti sivutetuissa raporteissa voi olla useita sivuja. Niiden asettelu on kiinteässä muodossa ja ne tarjoavat tarkan mukautuksen. Sivutetut raportit ovat .rdl-tiedostoja.

Voit tallentaa ja käsitellä sivutettuja raportteja Power BI -raporttipalvelimen verkkoportaalissa, samalla tavalla kuin SQL Server Reporting Services (SSRS) -verkkoportaalissa. Voit luoda ja muokata niitä Raportin muodostimessa tai Raportin suunnitteluohjelmassa SQL Server Data Toolsissa (SSDT). Sen jälkeen voit julkaista ne jommankumman verkkoportaalin kautta. Raportin lukijat organisaatiossasi voivat tarkastella niitä selaimessa tai Power BI -mobiilisovelluksessa mobiililaitteillaan.

![Power BI -raporttipalvelimen sivutettu raportti](media/quickstart-create-paginated-report/reportserver-paginated-report.png)

Jos olet jo luonut sivutettuja raportteja Raportin muodostimessa tai Raportin suunnitteluohjelmassa, niin osaat myös luoda sivutettuja raportteja Power BI -raporttipalvelimelle. Jos et ole, niin seuraavassa on muutamia nopea ohjeita, joiden avulla pääset alkuun.

## <a name="step-1-install-and-start-report-builder"></a>Vaihe 1: Asenna ja käynnistä Raportin muodostin
Olet ehkä jo asentanut Raportin muodostimen raporttien luomiseksi SSRS-palvelimelle. Voit käyttää samaa versiota tai Raportin muodostinta Power BI -raporttipalvelimen raporttien luomiseen. Jos et ole vielä asentanut sitä, prosessi on helppo.

1. Valitse Power BI -raporttipalvelimen verkkoportaalissa **Uusi** > **Sivutettu raportti**.
   
    ![Uusi sivutettu raportti -valikko](media/quickstart-create-paginated-report/reportserver-new-paginated-report-menu.png)
   
    Jos sinulla ei ole raportin muodostinta asennettuna, se opastaa sinut asennusprosessin läpi nyt.
2. Asennuksen jälkeen Raportin muodostin aukeaa **Uusi raportti tai tietojoukko** -näyttöön.
   
    ![Uusi raportti tai tietojoukko -näyttö](media/quickstart-create-paginated-report/reportserver-paginated-new-report-screen.png)
3. Valitse ohjattu toiminto sille raporttityypille, jonka haluat luoda:
   
   * Taulukko tai matriisi
   * Kaavio
   * Kartta
   * Tyhjä
4. Aloitetaan ohjatulla kaavion luomisella.
   
    Ohjattu kaavion luominen johdattaa sinut raportin peruskaavion luomisen läpi. Sen jälkeen voit mukauttaa raporttia lähes rajattomasti.

## <a name="step-2-go-through-the-chart-wizard"></a>Vaihe 2: Käy läpi ohjattu kaavion luominen
Ohjattu kaavion luominen johdattaa sinut raportin visualisoinnin luomisen perusvaiheiden läpi.

Sivutetut raportit voidaan yhdistää moniin eri tietolähteisiin, Microsoft SQL Serveristä ja Microsoft Azure SQL -tietokannasta Oracleen, Hyperioniin ja moneen muuhun. Lisätietoja [sivutettujen raporttien tukemista tietolähteistä](connect-data-sources.md).

Ollessasi ohjatun kaavion luomisen ensimmäisellä sivulla **Valitse tietojoukko**, jolloin voit luoda tietojoukon tai valita jaetun tietojoukon palvelimelta. *Tietojoukot* palauttavat raporttitiedot ulkoiselle tietolähteelle tehdystä kyselystä.

1. Valitse **Selaa** > valitse jaettu tietojoukko palvelimelta > **Avaa** > **Seuraava**.
   
    ![Ohjattu kaavion luominen: Valitse tietojoukko](media/quickstart-create-paginated-report/reportserver-paginated-choose-dataset.png)
   
     Tietojoukon luominen Katso [Jaetun tai upotetun tietojoukon luominen](https://docs.microsoft.com/sql/reporting-services/report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs).
2. Valitse kaaviotyyppi – tässä tapauksessa palkkikaavio.
   
    ![Ohjattu kaavion luominen: Kaaviotyyppi](media/quickstart-create-paginated-report/reportserver-paginated-choose-chart-type.png)
3. Järjestä kenttiä vetämällä ne **Luokat**-, **Sarjat**- ja **Arvot**-ruutuihin.
   
    ![Ohjattu kaavion luominen: Järjestä kentät](media/quickstart-create-paginated-report/reportserver-paginated-arrange-fields.png)
4. Valitse **Seuraava** > **Valmis**.

## <a name="step-3-design-your-report"></a>Vaihe 3: Suunnittele raportti
Nyt olet Raportin suunnittelunäkymässä. Huomaa, että tiedot ovat paikkamerkkitietoja, eivät sinun tietojasi.

![Raportin suunnittelunäkymä](media/quickstart-create-paginated-report/reportserver-paginated-preview-report.png)

* Jos haluat tarkastella tietojasi, valitse **Suorita**.
  
     ![Suorita raportti](media/quickstart-create-paginated-report/reportserver-paginated-run-report.png)
* Siirry takaisin Suunnittelunäkymään valitsemalla **Rakenne**.

Voit muokata juuri luomaasi kaaviota, muuttaa asettelua, arvoja, selitettä... eli lähes mitä tahansa.

Voit lisätä kaikenlaisia muita visualisointeja: mm. mittareita, taulukoita, matriiseja ja karttoja. Voit lisätä ylä- ja alatunnisteita useille sivuille. Katso [Raportin muodostimen opetusohjelmat](https://docs.microsoft.com/sql/reporting-services/report-builder-tutorials), jotta voit kokeilla niitä itse.

![Raportin muodostimen suunnittelunäkymä](media/quickstart-create-paginated-report/reportserver-paginated-finished-design-report.png)

## <a name="step-4-save-your-report-to-the-report-server"></a>Vaihe 4: Tallenna raportti raporttipalvelimelle
Kun raportti on valmis, tallenna se Power BI -raporttipalvelimelle.

1. Valitse **Tiedosto**-valikosta **Tallenna nimellä** ja tallenna se raporttipalvelimelle. 
2. Nyt voit tarkastella sitä selaimessa.
   
    ![Sivutettu raportti selaimessa](media/quickstart-create-paginated-report/reportserver-paginated-report.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Käytettävissä on useita hyviä resursseja raporttien suunnitteluun Raportin muodostimessa ja Raporttien suunnitteluohjelmassa SQL Server Data Toolsissa. Raportin muodostimen opetusohjelmat ovat hyvä paikka aloittaa.

* [Raportin muodostimen opetusohjelmat](https://docs.microsoft.com/sql/reporting-services/report-builder-tutorials)
* [Mikä on Power BI -raporttipalvelin?](get-started.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

