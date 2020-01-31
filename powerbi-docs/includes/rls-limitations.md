---
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 09/13/2019
ms.author: davidi
ms.openlocfilehash: 6d1a239954a64da1c92cc68b56912e6f4ab67228
ms.sourcegitcommit: 9a265d8117cc202f5f700286b5ff42a631aacdb4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/06/2019
ms.locfileid: "74882775"
---
## <a name="limitations"></a>Rajoitukset

Tässä on luettelo tämänhetkisistä rajoituksista pilvimallien rivitason suojaukselle.

* Jos määritit aiemmin roolit ja säännöt Power BI -palvelussa, sinun on luotava ne uudelleen Power BI Desktopissa.

* Voit määrittää rivitason suojauksen vain tietojoukoille, jotka on luotu Power BI Desktopin avulla. Jos haluat ottaa rivitason suojauksen käyttöön tietojoukoille, jotka on luotu Excelin avulla, sinun on ensin muunnettava tiedostosi Power BI Desktop (PBIX) -tiedostoiksi. [Lue lisää](../desktop-import-excel-workbooks.md)

* Vain tuonti- ja DirectQuery-yhteyksiä tuetaan. Reaaliaikaisista yhteyksistä Analysis Servicesiin huolehditaan paikallisessa mallissa.

## <a name="known-issues"></a>Tunnetut ongelmat

Tunnemme ongelman, jossa näyttöön tulee virheviesti, kun käyttäjä yrittää julkaista Power BI Desktopista raportin, joka on julkaistu jo aiemmin. Tilanne on seuraavanlainen.

1. Annalla on tietojoukko, joka on julkaistu Power BI -palveluun ja jolle on määritetty rivitason suojaus.

1. Anna päivittää raportin Power BI Desktopissa ja julkaisee sen uudelleen.

1. Anna kohtaa virheen.

**Vaihtoehtoinen menetelmä:** Julkaise Power BI Desktop -tiedosto uudelleen Power BI -palvelusta, kunnes tämä ongelma on ratkaistu. Voit toimia näin valitsemalla **Nouda tiedot** > **Tiedostot**.
