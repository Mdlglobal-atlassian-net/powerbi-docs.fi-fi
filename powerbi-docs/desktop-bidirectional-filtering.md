---
title: Kaksisuuntainen ristiinsuodatus Power BI Desktopissa
description: Ristiinsuodatuksen ottaminen käyttöön DirectQueryn avulla Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 8aeae0075ed32a832c27f475ef3786b7df76576c
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/09/2020
ms.locfileid: "75761768"
---
# <a name="enable-bidirectional-cross-filtering-for-directquery-in-power-bi-desktop"></a>DirectQueryn kaksisuuntaisen ristiinsuodatuksen käyttöönotto Power BI Desktopissa

Kun taulukoita suodatetaan tiedoille sopivan näkymän luomiseksi, raportin luojat (ja tietojen mallintajat) kohtaavat haasteita määrittäessään, miten suodatusta käytetään raporttiin: taulukon suodatinkonteksti säilyy suhteen toisella puolella, mutta ei toisella, mikä edellyttää usein monimutkaisia DAX-kaavoja halutun tuloksen saamiseksi.

Kaksisuuntaisen ristiinsuodatuksen ansiosta raportin luojat (ja tietojen mallintajat) voivat nyt hallita tarkemmin sitä, miten suodattimia käytetään tällaisia taulukoita käsiteltäessä, koska sen avulla nämä suodattimet voidaan ottaa käyttöön taulukkosuhteen *molemmilla* puolilla. Tämä toteutetaan siten, että suodatinkonteksti välitetään taulukkosuhteen toisella puolella olevaan toiseen, liitettyyn taulukkoon.

## <a name="detailed-whitepaper-for-bidirectional-cross-filtering"></a>Yksityiskohtainen tekninen raportti kaksisuuntaista ristiinsuodatusta varten
Saatavilla on [yksityiskohtainen tekninen raportti](https://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx), jossa selitetään kaksisuuntainen ristisuodatus Power BI Desktopissa (tekninen raportti kattaa myös SQL Server Analysis Services 2016:n, molemmat toimivat samalla tavalla).

* Lataa [Kaksisuuntainen ristiinsuodatus Power BI Desktopille](https://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) -tekninen raportti

## <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>Kaksisuuntaisen ristiinsuodatuksen ottaminen käyttöön DirectQuerylle

Ristisuodatuksen ottamiseksi käyttöön suhteen valintaikkunassa **Suhteen muokkaaminen** seuraavien on oltava valittuna:

* **Ristiinsuodatussuunnaksi** on asetettava **Molemmat**
* **Ota suojaussuodattimet käyttöön molempiin suuntiin** on myös oltava valittuna

  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

> [!NOTE]
> Kun luot ristiinsuodatuksen DAX-kaavoja Power BI Desktopissa, käytä *UserPrincipalNamea* (joka on usein sama kuin käyttäjän kirjautumisnimi, kuten <em>joe@contoso.com</em>) *Käyttäjänimen* sijaan. Siten joudut ehkä luomaan vastaavan taulukon, joka yhdistää *Käyttäjänimen* (tai esimerkiksi työntekijätunnuksen) *UserPrincipalNameen*.

Saat lisätietoja ja esimerkkejä kaksisuuntaisen ristiinsuodatuksen toiminnasta tässä artikkelissa aiemmin mainitusta [teknisestä raportista](https://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx).

