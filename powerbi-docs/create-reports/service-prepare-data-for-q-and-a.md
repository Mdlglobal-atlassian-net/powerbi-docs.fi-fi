---
title: Excel-tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa
description: Tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 102145e8c5b2fd3ad19b6703710405d06da5a93a
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83323225"
---
# <a name="make-excel-data-work-well-with-qa-in-power-bi"></a>Excel-tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa
Jos luot tietomalleja tai Excel-työkirjoja, joita käytetään Power BI:ssä, jatka lukemista.

Power BI:ssä Q&A-toiminto voi hakea strukturoitua tietoa ja valita oikean visualisoinnin kysymystä varten, mikä tekee siitä houkuttelevan työkalun.   

Q&A osaa käyttää mitä tahansa ladattua Excel-tiedostoa, joka sisältää taulukoita, alueita tai PowerPivot-mallin. Mitä enemmän optimointia ja tietojen siistimistä teet, sitä tehokkaammin Q&A toimii.  Jos aiot jakaa tietojoukkoihin perustuvia raportteja ja koontinäyttöjä, voit helpottaa niiden käyttämistä työtovereillesi, kun he voivat esittää kysymyksiä ja saada laadukkaita vastauksia.

## <a name="how-qa-works-with-excel"></a>Q&A:n toiminta Excelin kanssa
Q&A sisältää luonnollisen kielen perusymmärrysominaisuuksia, jotka toimivat tietojen kanssa. Toiminnossa on kontekstiriippuvainen avainsanahaku Excelin taulukoiden, sarakkeiden ja laskettujen kenttien nimille. Siinä on myös sisäisiä tietoja siitä, miten tiedot suodatetaan, lajitellaan, koostetaan, ryhmitellään ja näytetään. 

Esimerkiksi Excel-taulukossa nimeltä ”Myynti”, joka sisältää sarakkeet ”Tuote”, ”Kuukausi”, ”Myyty määrä”, ”Bruttomyynti” ja ”Tuotto” voi esittää kysymyksiä mistä tahansa näistä kohteista.  Voit sanoa esimerkiksi ”näytä myynti”, ”tuotto yhteensä kuukauden mukaan”, ”lajittele tuotteet myytyjen yksiköiden mukaan” ja paljon muuta. Lue lisätietoja siitä, [millaisia kysymyksiä voit esittää](power-bi-tutorial-q-and-a.md) ja [mitä visualisointityyppejä voit määrittää Q&A:n kyselyssä](../visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).

## <a name="prepare-an-excel-dataset-for-qa"></a>Excel-tietojoukon valmisteleminen Q&A:ta varten
Q&A on riippuvainen taulukoiden, sarakkeiden ja laskettujen kenttien nimistä, jotta toiminto osaa vastata tietoihin liittyviin kysymyksiin. Työkirjassa olevien kohteiden nimillä on siis merkitystä!

Seuraavassa on joitakin vinkkejä, joiden avulla voit hyödyntää Q&A:ta tehokkaasti työkirjassa.

* Varmista, että tiedot ovat Excel-taulukossa. Lue [Excel-taulukon luontiohjeet](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664).
* Varmista, että taulukoiden, sarakkeiden ja laskettujen kenttien nimet toimivat loogisesti luonnollisessa puheessa.
  
  Jos sinulla on esimerkiksi taulukko, joka sisältää myyntitiedot, anna taulukon nimeksi ”Myynti”. Sarakenimet, kuten ”Vuosi”, ”Tuote”, ”Myyntiedustaja” ja ”Summa”, toimivat hyvin Q&A:ssa.

* Jos työkirjassa on PowerPivot-tietomalli, voit tehdä muitakin optimointeja. Lue Microsoftin luonnollisen kielen tiimin asiantuntijoiden kirjoittama artikkeli, jossa [kerrotaan tarkemmin Power BI Q&A:sta (osa 2)](https://powerbi.microsoft.com/blog/demystifying-power-bi-q-amp-a-part-2/).

* Avaa tietojoukko Power BI Desktopissa ja luo esimerkiksi uusia sarakkeita, luo laskettuja mittareita, luo yksilöllisiä arvoja yhdistämällä kenttiä sekä luokittele tietoja tyypin mukaan (esimerkiksi päivämäärät, merkkijonot, maantieteelliset alueet, kuvat, URL-osoitteet).

## <a name="next-steps"></a>Seuraavat vaiheet

- [Q&A kuluttajille](../consumer/end-user-q-and-a.md)  
- [Q&A:n käyttäminen koontinäyttöissä ja raporteissa](power-bi-tutorial-q-and-a.md)
- [Paikallisten tietojoukkojen valmisteleminen Q&A:ta varten](service-q-and-a-direct-query.md)   
- [Tietojen noutaminen (Power BI:hin)](../connect-data/service-get-data.md)  

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
