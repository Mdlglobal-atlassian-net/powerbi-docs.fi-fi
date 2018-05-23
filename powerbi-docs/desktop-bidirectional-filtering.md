---
title: Kaksisuuntainen ristiinsuodatus Power BI Desktopissa
description: Ristiinsuodatuksen ottaminen käyttöön DirectQueryn avulla Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a584d61e1f2f55c244b453e6c086f3222217ee9a
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2018
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop"></a>Kaksisuuntainen ristiinsuodatus DirectQueryn avulla Power BI Desktopissa

Kun taulukoita suodatetaan tiedoille sopivan näkymän luomiseksi, raportin luojat (ja tietojen mallintajat) kohtaavat haasteita määrittäessään, miten suodatusta käytetään raporttiin: taulukon suodatinkonteksti säilyy suhteen toisella puolella, mutta ei toisella, mikä edellyttää usein monimutkaisia DAX-kaavoja halutun tuloksen saamiseksi.

Kaksisuuntaisen ristiinsuodatuksen ansiosta raportin luojat (ja tietojen mallintajat) voivat nyt hallita tarkemmin sitä, miten suodattimia käytetään tällaisia taulukoita käsiteltäessä, koska sen avulla nämä suodattimet voidaan ottaa käyttöön taulukkosuhteen *molemmilla* puolilla. Tämä toteutetaan siten, että suodatinkonteksti välitetään taulukkosuhteen toisella puolella olevaan toiseen, liitettyyn taulukkoon.

Saatavilla on [yksityiskohtainen tekninen raportti](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx), jossa selitetään kaksisuuntainen ristisuodatus Power BI Desktopissa (tekninen raportti kattaa myös SQL Server Analysis Services 2016:n, molemmat toimivat samalla tavalla).

* Lataa [Kaksisuuntainen ristiinsuodatus Power BI Desktopille](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) -tekninen raportti

### <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>Kaksisuuntaisen ristiinsuodatuksen ottaminen käyttöön DirectQuerylle

Ristisuodatuksen ottamiseksi käyttöön suhteen valintaikkunassa **Suhteen muokkaaminen** seuraavien on oltava valittuna:

* **Ristiinsuodatussuunnaksi** on asetettava **Molemmat**
* **Ota suojaussuodattimet käyttöön molempiin suuntiin** on myös oltava valittuna
  
  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

> [!NOTE]
> Kun luot ristiinsuodatuksen DAX-kaavoja Power BI Desktopissa, käytä *UserPrincipalNamea* (joka on usein sama kuin käyttäjän kirjautumisnimi, kuten *joe@contoso.com*) *Käyttäjänimen* sijaan. Niinpä joudut ehkä luomaan vastaavan taulukon, joka yhdistää *Käyttäjänimen* (tai esimerkiksi työntekijätunnuksen) *UserPrincipleNameen*.
> 
> 

Saat lisätietoja ja esimerkkejä kaksisuuntaisen ristiinsuodatuksen toiminnasta tässä artikkelissa aiemmin mainitusta [teknisestä raportista](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx).

