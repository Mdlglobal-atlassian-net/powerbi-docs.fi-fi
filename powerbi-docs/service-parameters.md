---
title: Tietojoukon parametriasetusten tarkasteleminen ja muokkaaminen Power BI -palvelussa
description: Kyselyparametrit luodaan Power BI Desktopissa, mutta niitä voidaan tarkastella ja päivittää Power BI -palvelussa
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/26/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: ac271e8013bce5824931153351a651644a716a2f
ms.sourcegitcommit: 5eb8632f653b9ea4f33a780fd360e75bbdf53b13
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965155"
---
# <a name="what-is-a-query-parameter"></a>Mikä on kyselyparametri?
Raportin luojat lisäävät kyselyparametreja Power BI Desktopiin. Parametrien avulle he voivat osittaa raportteja yhden tai useamman parametrin *arvon* mukaan. Raportin luoja voi esimerkiksi luoda parametrin, joka rajoittaa tiedot yhden maan alueelle tai parametrin, joka määrittää hyväksyttävät muodot esimerkiksi päivämäärä-, kellonaika- ja tekstikenttiin.

![Aloitus-välilehti, joka näyttää Hallitse parametreja -vaihtoehdon Desktopissa](media/service-parameters/power-bi-manage-parameters.png)


## <a name="review-and-edit-parameters-in-power-bi-service"></a>Parametrien tarkasteleminen ja muokkaaminen Power BI -palvelussa

Kun parametrit on määritetty Desktopissa ja tämä [raportti julkaistaan Power BI -palvelussa](desktop-upload-desktop-files.md), parametrin asetukset ja valinnat kulkevat tämän raportin mukana. Joitakin parametriasetuksia voidaan tarkastella ja muokata Power BI -palvelussa -- tämä ei koske parametreja, jotka rajoittavat saatavilla olevia tietoja, vaan parametreja, jotka määrittävät ja kuvaavat hyväksyttäviä arvoja.

1. Valitse Power BI -palvelussa ![cog-kuvake](media/service-parameters/power-bi-cog.png), jotta voit avata **Asetukset**-kohdan.

2. Valitse välilehti **Tietojoukot**-kohdalle ja korosta tietojoukko luettelossa. 
    
    ![Asetukset-ikkuna, jossa Tietojoukko-välilehti on valittuna](media/service-parameters/power-bi-select-dataset2.png)

3. Laajenna **Parametrit**-kohtaa.  Jos valitulla tietojoukolla ei ole parametreja, näkyviin tulee viesti, jossa on linkki artikkeliin Lisätietoja kyselyparametreista. Jos tietojoukolla ei ole parametreja, saat ne näkyviin laajentamalla **Parametrit**-ylätunnistetta. 

    ![Asetukset-ikkuna, jossa Parametrit-ylätunniste on laajennettu](media/service-parameters/power-bi-settings.png)

    Tarkastele parametriasetuksia ja muuta niitä tarvittaessa. Harmaita kenttiä ei voi muokata. 


## <a name="next-steps"></a>Seuraavat vaiheet
Yksinkertaisia parametreja voi tilapäisesti lisätä [muokkaamalla URL-osoitetta](service-url-filters.md).