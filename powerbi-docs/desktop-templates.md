---
title: Mallien käyttäminen Power BI Desktopissa
description: Mallien luominen ja jakaminen Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/16/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e28306532714369830df46304aa4a1ebff67bd8f
ms.sourcegitcommit: e62889690073626d92cc73ff5ae26c71011e012e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/23/2019
ms.locfileid: "69985646"
---
# <a name="using-templates-in-power-bi-desktop"></a>Mallien käyttäminen Power BI Desktopissa

**Power BI Desktopin** avulla voit luoda vaikuttavia raportteja, joiden kautta voit jakaa merkityksellisiä tietoja koko organisaatiolle. Power BI Desktopin **mallien** avulla voit tehostaa työtä luomalla olemassa olevaan malliin perustuvan raporttimallin, jota sinä ja organisaatiosi muut käyttäjät voivat käyttää lähtökohtana uuden raportin asettelussa, tietomallissa ja kyselyissä. **Power BI Desktopin** mallit nopeuttavat raportin luomista ja vakioivat sen.

![Raportin vieminen mallina](media/desktop-templates/desktop-templates-01.png)

## <a name="creating-templates"></a>Mallien luominen

Power BI:n raporttimallit sisältävät seuraavat tiedot raportista, josta ne luotiin:

* Raportin **sivut**, visualisoinnit ja muut visuaaliset elementit
* **Tietomallin määritykset**, mukaan lukien rakenne, yhteydet, mittarit ja muut mallin määritelmän artefaktit
* Kaikki **kyselymääritykset**, kuten kyselyt, kyselyparametrit ja muut kyselyiden elementit

Mallit *eivät* sisällä raportin tietoja. 

Raporttimalleissa käytetään tiedostotunnistetta .PBIT (Power BI Desktop -raporteissa tunniste on .PBIX). 

Jos haluat luoda raporttimallin, valitse valikosta **Tiedosto > Vie > Power BI -malli**. Saat näkyviin seuraavan ikkunan, jossa pyydetään antamaan mallin kuvaus. Tässä esimerkissä mallin kuvaus on *Kuukausittaisen myynnin raporttimalli.*

![Vie malli -kuvausvalintaikkuna](media/desktop-templates/desktop-templates-02.png)

Valitse **OK**. Sinua pyydetään valitsemaan tiedostosijainti, johon .PBIT-mallitiedosto tallennetaan.

![Mallin sijainti](media/desktop-templates/desktop-templates-03.png)

Siinä kaikki. Power BI -raporttimallisi luodaan määritettyyn tiedostosijaintiin .PBIT-tunnisteella.

> [!NOTE]
> Power BI -raporttimallitiedostot ovat yleensä paljon pienempiä kuin Power BI Desktopin raportit, koska mallit eivät sisällä mitään tietoja, vaan ainoastaan raporttimääritykset. 

## <a name="using-templates"></a>Mallien käyttäminen

Jos haluat käyttää Power BI -raporttimallia, avaa se Power BI Desktopissa ja aloita sen käyttö. Voit avata Power BI -raporttimallin kahdella tavalla:

* Kaksoisnapsauta mitä tahansa .PBIT-tiedostoa, jotta Power BI Desktop käynnistyy ja lataa mallin automaattisesti
* Valitse **Tiedosto > Tuo > Power BI -malli** Power BI Desktopissa

![Mallin vieminen](media/desktop-templates/desktop-templates-04.png)

Kun avaat raporttimallin, näkyviin tulee valintaikkuna, joka näyttää arvot mallin perustana olevassa raportissa määritetyille parametreille. Jos raportissa esimerkiksi analysoidaan asiakkaita maan tai alueen perusteella ja siinä on *Maa*-parametri asiakaskunnan määrittämiseksi, näkyviin tulee kehotus valita *Maa*-arvo parametrin määrittämisessä yksilöidystä arvoluettelosta. 

![Mallin parametrien määrittäminen](media/desktop-templates/desktop-templates-05a.png)

Kun tarvittavat parametrit on annettu, sinua pyydetään antamaan raporttiin liittyvien pohjana olevien tietojen sijainti. Nykyinen raportin tekijä voi muodostaa yhteyden tietoihin tunnistetietojensa perusteella.

![Mallin tietojen sijainnin määrittäminen](media/desktop-templates/desktop-templates-05.png)

Kun parametrit ja tiedot on määritetty, luodaan raportti, joka sisältää kaikki sivut, visualisoinnit, tietomallin artefaktit ja kyselyt, jotka olivat osa mallin perustana olevaa raporttia. 

Siinä kaikki! Raporttimallien luominen ja käyttäminen Power BI Desktopissa on helppoa. Voit helposti toistaa vaikuttavia asetteluja ja muita raportin ominaisuuksia ja jakaa ne muille.

## <a name="next-steps"></a>Seuraavat vaiheet
Voit olla myös kiinnostunut **kyselyparametreista**:
* [Käytätkö kyselyparametreja Power BI Desktopissa?](https://docs.microsoft.com/power-query/power-query-query-parameters)

Voit lisäksi tehdä kaikenlaista Power BI Desktopilla. Saat lisätietoja sen toiminnoista seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin kyselyiden yleiskatsaus](desktop-query-overview.md)
* [Tietotyypit Power BI Desktopissa](desktop-data-types.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](desktop-common-query-tasks.md)    
