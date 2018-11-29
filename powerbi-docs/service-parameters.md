---
title: Parametriasetusten muokkaaminen Power BI -palvelussa
description: Kyselyparametrit luodaan Power BI Desktopissa, mutta niitä voidaan tarkastella ja päivittää Power BI -palvelussa
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: b379812a16bbdbbc16517b86d9ce4e941ac45f01
ms.sourcegitcommit: 35d763dfc75c229204d36fd8b35c1e860786b707
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/27/2018
ms.locfileid: "52331869"
---
# <a name="edit-parameter-settings-in-the-power-bi-service"></a>Parametriasetusten muokkaaminen Power BI -palvelussa
Raporttien luojat lisäävät kyselyparametreja raportteihin Power BI Desktopissa. Parametrien avulle he voivat osittaa raportteja yhden tai useamman parametrin *arvon* mukaan. Raportin luoja voi esimerkiksi luoda parametrin, joka rajoittaa tiedot yhteen maahan tai yhdelle alueelle, tai parametrin, joka määrittää hyväksyttävät muodot esimerkiksi päivämäärä-, kellonaika- ja tekstikenttiin.

![Aloitus-välilehti, joka näyttää Hallitse parametreja -vaihtoehdon Desktopissa](media/service-parameters/power-bi-manage-parameters.png)

## <a name="review-and-edit-parameters-in-power-bi-service"></a>Parametrien tarkasteleminen ja muokkaaminen Power BI -palvelussa

Raportin luojana määrität parametrit Desktop-versiossa. Kun [julkaiset raportin Power BI -palveluun](desktop-upload-desktop-files.md), parametriasetukset ja -valinnat siirtyvät sen mukana. Voit tarkastella ja muokata joitakin parametriasetuksia Power BI -palvelussa – tämä ei koske parametreja, jotka rajoittavat saatavilla olevia tietoja, vaan parametreja, jotka määrittävät ja kuvaavat hyväksyttäviä arvoja.

1. Valitse Power BI -palvelussa ![cog-kuvake](media/service-parameters/power-bi-cog.png), jotta voit avata **Asetukset**-kohdan.

2. Valitse välilehti **Tietojoukot**-kohdalle ja korosta tietojoukko luettelossa. 
    
    ![Asetukset-ikkuna, jossa Tietojoukko-välilehti on valittuna](media/service-parameters/power-bi-select-dataset2.png)

3. Laajenna **Parametrit**-kohtaa.  Jos valitulla tietojoukolla ei ole parametreja, näkyviin tulee viesti, jossa on linkki artikkeliin Lisätietoja kyselyparametreista. Jos tietojoukolla ei ole parametreja, saat ne näkyviin laajentamalla **Parametrit**-ylätunnistetta. 

    ![Asetukset-ikkuna, jossa Parametrit-ylätunniste on laajennettu](media/service-parameters/power-bi-settings.png)

    Tarkastele parametriasetuksia ja muuta niitä tarvittaessa. Harmaita kenttiä ei voi muokata. 


## <a name="next-steps"></a>Seuraavat vaiheet
Yksinkertaisia parametreja voi tilapäisesti lisätä [muokkaamalla URL-osoitetta](service-url-filters.md).