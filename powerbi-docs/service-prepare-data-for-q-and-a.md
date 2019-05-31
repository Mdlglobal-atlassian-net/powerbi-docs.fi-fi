---
title: Excel-tietojen muokkaaminen toimimaan hyvin Q & A Power BI-
description: Tietojen muokkaaminen toimimaan hyvin Power BI:n Q&A-toiminnon kanssa
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 7ed8eb8e205c05582d2cfd93030ab056be77912a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65624973"
---
# <a name="make-excel-data-work-well-with-qa-in-power-bi"></a>Excel-tietojen muokkaaminen toimimaan hyvin Q & A Power BI-
Jos luot tietomalleja tai Excel-työkirjoja, joita käytetään Power BI:ssä, jatka lukemista.

Power BI:ssä Q&A-toiminto voi hakea strukturoitua tietoa ja valita oikean visualisoinnin kysymystä varten, mikä tekee siitä houkuttelevan työkalun.   

Q&A osaa käyttää mitä tahansa ladattua Excel-tiedostoa, joka sisältää taulukoita, alueita tai PowerPivot-mallin. Mitä enemmän optimointia ja tietojen siistimistä teet, sitä tehokkaammin Q&A toimii.  Jos aiot jakaa tietojoukkoihin perustuvia raportteja ja koontinäyttöjä, voit helpottaa niiden käyttämistä työtovereillesi, kun he voivat esittää kysymyksiä ja saada laadukkaita vastauksia.

## <a name="how-qa-works-with-excel"></a>Q&A:n toiminta Excelin kanssa
Q&A sisältää luonnollisen kielen perusymmärrysominaisuuksia, jotka toimivat tietojen kanssa. Toiminnossa on kontekstiriippuvainen avainsanahaku Excelin taulukoiden, sarakkeiden ja laskettujen kenttien nimille. Siinä on myös sisäisiä tietoja siitä, miten tiedot suodatetaan, lajitellaan, koostetaan, ryhmitellään ja näytetään. 

Esimerkiksi Excel-taulukossa nimeltä ”Myynti”, joka sisältää sarakkeet ”Tuote”, ”Kuukausi”, ”Myyty määrä”, ”Bruttomyynti” ja ”Tuotto” voi esittää kysymyksiä mistä tahansa näistä kohteista.  Voit sanoa esimerkiksi ”näytä myynti”, ”tuotto yhteensä kuukauden mukaan”, ”lajittele tuotteet myytyjen yksiköiden mukaan” ja paljon muuta. Lue lisää [käyttämällä Q & A: n koontinäyttöjen ja raporttien](power-bi-tutorial-q-and-a.md), ja [visualisointityyppejä voit määrittää Q & A: n kyselyssä](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).

## <a name="prepare-an-excel-dataset-for-qa"></a>Excel-tietojoukon valmisteleminen Q&A:ta varten
Q&A on riippuvainen taulukoiden, sarakkeiden ja laskettujen kenttien nimistä, jotta toiminto osaa vastata tietoihin liittyviin kysymyksiin. Työkirjassa olevien kohteiden nimillä on siis merkitystä!

Seuraavassa on joitakin vinkkejä, joiden avulla voit hyödyntää Q&A:ta tehokkaasti työkirjassa.

* Varmista, että tiedot ovat Excel-taulukossa. Lue [Excel-taulukon luontiohjeet](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664).
* Varmista, että taulukoiden, sarakkeiden ja laskettujen kenttien nimet toimivat loogisesti luonnollisessa puheessa.
  
  Jos sinulla on esimerkiksi taulukko, joka sisältää myyntitiedot, anna taulukon nimeksi ”Myynti”. Sarakenimet, kuten ”Vuosi”, ”Tuote”, ”Myyntiedustaja” ja ”Summa”, toimivat hyvin Q&A:ssa.

* Jos työkirjassa on PowerPivot-tietomalli, voit tehdä muitakin optimointeja. Lue Microsoftin luonnollisen kielen tiimin asiantuntijoiden kirjoittama artikkeli, jossa [kerrotaan tarkemmin Power BI Q&A:sta (osa 2)](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx).

* Avaa tietojoukko Power BI Desktopissa ja luo esimerkiksi uusia sarakkeita, luo laskettuja mittareita, luo yksilöllisiä arvoja yhdistämällä kenttiä sekä luokittele tietoja tyypin mukaan (esimerkiksi päivämäärät, merkkijonot, maantieteelliset alueet, kuvat, URL-osoitteet).

## <a name="next-steps"></a>Seuraavat vaiheet

- [Q & A kuluttajat](consumer/end-user-q-and-a.md)  
- [Koontinäyttöjen ja raporttien Q & A: n käyttäminen](power-bi-tutorial-q-and-a.md)
- [Paikallisten tietojoukkojen valmisteleminen Q & A:](service-q-and-a-direct-query.md)   
- [Tietojen noutaminen (Power BI:hin)](service-get-data.md)  

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

