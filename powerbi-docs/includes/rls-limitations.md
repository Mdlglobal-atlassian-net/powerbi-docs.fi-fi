---
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 01/31/2020
ms.author: davidi
ms.openlocfilehash: b67025de5e2a70876a31fd42e22c9572403288fa
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "77464369"
---
## <a name="limitations"></a>Rajoitukset

Tämänhetkiset rajoitukset pilvimallien rivitason suojaukselle:

* Jos määritit aiemmin roolit ja säännöt Power BI -palvelussa, sinun on luotava ne uudelleen Power BI Desktopissa.

* Voit määrittää rivitason suojauksen vain tietojoukoille, jotka on luotu Power BI Desktopin avulla. Jos haluat ottaa rivitason suojauksen käyttöön tietojoukoille, jotka on luotu Excelin avulla, sinun on ensin muunnettava tiedostosi Power BI Desktop (PBIX) -tiedostoiksi. [Lue lisää](../desktop-import-excel-workbooks.md).

* Vain tuonti- ja DirectQuery-yhteyksiä tuetaan. Reaaliaikaisista yhteyksistä Analysis Servicesiin huolehditaan paikallisessa mallissa.

## <a name="known-issues"></a>Tunnetut ongelmat

Tunnemme ongelman, jossa näyttöön tulee virheviesti, kun käyttäjä yrittää julkaista Power BI Desktopista raportin, joka on julkaistu jo aiemmin. Skenaario on seuraava:

1. Annalla on tietojoukko, joka on julkaistu Power BI -palveluun ja jolle on määritetty rivitason suojaus.

1. Anna päivittää raportin Power BI Desktopissa ja julkaisee sen uudelleen.

1. Anna kohtaa virheen.

**Vaihtoehtoinen menetelmä:** Julkaise Power BI Desktop -tiedosto uudelleen Power BI -palvelusta, kunnes tämä ongelma on ratkaistu. Voit toimia näin valitsemalla **Nouda tiedot** > **Tiedostot**.
