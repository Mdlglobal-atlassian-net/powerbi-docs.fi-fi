---
title: Excel-tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa
description: Tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 76027ff6e75071fde178ae05a8656c1596d36598
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54291690"
---
# <a name="how-to-make-your-excel-data-work-well-with-qa-in-power-bi"></a>Excel-tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa
Jos luot tietomalleja tai Excel-työkirjoja, joita käytetään Power BI:ssä, jatka lukemista.

Power BI:ssä Q&A-toiminto voi hakea strukturoitua tietoa ja valita oikean visualisoinnin kysymystä varten, mikä tekee siitä houkuttelevan työkalun.   

Q&A osaa käyttää mitä tahansa ladattua Excel-tiedostoa, joka sisältää taulukoita, alueita tai PowerPivot-mallin. Mitä enemmän optimointia ja tietojen siistimistä teet, sitä tehokkaammin Q&A toimii.  Jos aiot jakaa tietojoukkoihin perustuvia raportteja ja koontinäyttöjä, voit helpottaa niiden käyttämistä työtovereillesi, kun he voivat esittää kysymyksiä ja saada laadukkaita vastauksia.

### <a name="how-qa-works-with-excel"></a>Q&A:n toiminta Excelin kanssa
Q&A sisältää luonnollisen kielen perusymmärrysominaisuuksia, jotka toimivat tietojen kanssa. Toiminnossa on kontekstiriippuvainen avainsanahaku Excelin taulukoiden, sarakkeiden ja laskettujen kenttien nimille. Siinä on myös sisäisiä tietoja siitä, miten tiedot suodatetaan, lajitellaan, koostetaan, ryhmitellään ja näytetään. 

Esimerkiksi Excel-taulukossa nimeltä ”Myynti”, joka sisältää sarakkeet ”Tuote”, ”Kuukausi”, ”Myyty määrä”, ”Bruttomyynti” ja ”Tuotto” voi esittää kysymyksiä mistä tahansa näistä kohteista.  Voit sanoa esimerkiksi ”näytä myynti”, ”tuotto yhteensä kuukauden mukaan”, ”lajittele tuotteet myytyjen yksiköiden mukaan” ja paljon muuta. Lue lisätietoja siitä, [millaisia kysymyksiä voit esittää](consumer/end-user-q-and-a.md) ja [mitä visualisointityyppejä voit määrittää Q&A:n kyselyssä](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).

### <a name="prepare-an-excel-dataset-for-qa"></a>Excel-tietojoukon valmisteleminen Q&A:ta varten
Q&A on riippuvainen taulukoiden, sarakkeiden ja laskettujen kenttien nimistä, jotta toiminto osaa vastata tietoihin liittyviin kysymyksiin. Työkirjassa olevien kohteiden nimillä on siis merkitystä!

Seuraavassa on joitakin vinkkejä, joiden avulla voit hyödyntää Q&A:ta tehokkaasti työkirjassa.

* Varmista, että tiedot ovat Excel-taulukossa. Lue [Excel-taulukon luontiohjeet](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US).
* Varmista, että taulukoiden, sarakkeiden ja laskettujen kenttien nimet toimivat loogisesti luonnollisessa puheessa.
  
  Jos sinulla on esimerkiksi taulukko, joka sisältää myyntitiedot, anna taulukon nimeksi ”Myynti”. Sarakenimet, kuten ”Vuosi”, ”Tuote”, ”Myyntiedustaja” ja ”Summa”, toimivat hyvin Q&A:ssa.

* Jos työkirjassa on PowerPivot-tietomalli, voit tehdä muitakin optimointeja. Lue Microsoftin luonnollisen kielen tiimin asiantuntijoiden kirjoittama artikkeli, jossa [kerrotaan tarkemmin Power BI Q&A:sta (osa 2)](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx).

* Avaa tietojoukko Power BI Desktopissa ja luo esimerkiksi uusia sarakkeita, luo laskettuja mittoja, luo yksilöllisiä arvoja yhdistämällä kenttiä sekä luokittele tietoja tyypin mukaan (esimerkiksi päivämäärät, merkkijonot, maantieteelliset alueet, kuvat, URL-osoitteet).

## <a name="next-steps"></a>Seuraavat vaiheet
Takaisin artikkeliin [Q&A Power BI:ssä](consumer/end-user-q-and-a.md)  
[Paikallisten tietojoukkojen valmisteleminen Q&A:ta varten](service-q-and-a-direct-query.md)   
[Q&A:n pika-aloitus](power-bi-visualization-introduction-to-q-and-a.md)  
[Tietojen noutaminen (Power BI:hin)](service-get-data.md)  

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

