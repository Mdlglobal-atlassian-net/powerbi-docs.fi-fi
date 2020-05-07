---
ms.openlocfilehash: cd0696b44e285119193059304c89cfa04c755771
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "71409359"
---
## <a name="faq"></a>Usein kysytyt kysymykset
**Kysymys:** Entä jos olen aiemmin luonut rooleja ja sääntöjä tietojoukolle Power BI -palvelussa? Toimivatko ne edelleen, jos en tee mitään?  
**Vastaus**: Visualisointeja ei hahmonneta oikein. Sinun on luotava roolit ja säännöt uudelleen Power BI Desktopissa ja sen jälkeen julkaistava ne Power BI -palveluun.

**Kysymys:** Voinko luoda nämä roolit Analysis Services -tietolähteille?  
**Vastaus**: Voit, jos tiedot on tuotu Power BI Desktopiin. Jos käytössäsi on reaaliaikainen yhteys, et pysty määrittämään rivitason suojausta Power BI -palvelun sisällä. Se määritetään Analysis Services -mallissa paikallisesti.

**Kysymys:** Voinko käyttää rivitason suojausta rajoittamaan käyttäjien käytössä olevia sarakkeita tai mittareita?  
**Vastaus**: Et voi. Jos käyttäjällä on tietyn tietorivin käyttöoikeus, hän voi nähdä kaikki kyseisen rivin tietosarakkeet.

**Kysymys:** Salliiko rivitason suojaus tarkkojen tietojen piilottamisen ja samalla visualisoinneissa olevien yhteenvetotietojen käytön?  
**Vastaus**: Ei, voit suojata yksittäisiä tietorivejä, mutta käyttäjät voivat aina nähdä tarkat tiedot tai yhteenvetotiedot.

**Kysymys:** Tietolähteeseeni on jo määritetty käyttöoikeusrooleja (esimerkiksi SQL -rooleja tai SAP BW -rooleja). Mikä niiden ja RLS:n suhde on?  
**Vastaus**: Vastaus riippuu siitä, tuotko tietoja, vai käytätkö DirectQuerya. Jos tuot tietoja Power BI -tietojoukkoosi, tietolähteesi käyttöoikeusrooleja ei käytetä. Määritä tällöin RLS, jos haluat pakottaa suojaussäännöt käyttäjille, jotka muodostavat yhteyden Power BI:ssä. Jos käytät DirectQuerya, käytetään tietolähteesi käyttöoikeusrooleja. Kun käyttäjä avaa raportin, Power BI lähettää pohjana olevaan tietolähteeseen kyselyn, joka soveltaa tietoihin käyttöoikeussääntöjä käyttäjän tunnistetietojen perusteella.
