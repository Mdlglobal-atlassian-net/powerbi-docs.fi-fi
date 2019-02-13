---
title: Raportin upottaminen iFramea käyttäen
description: Power BI -raporttipalvelimen raportin upottaminen iFrameen SharePoint-palvelimessa
author: markingmyname
ms.author: maghan
ms.date: 05/04/2018
ms.topic: quickstart
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 4730bef0e7f1fc47a4a59a0129640760714fe2e0
ms.sourcegitcommit: 80961ace38ff9dac6699f81fcee0f7d88a51edf4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/13/2019
ms.locfileid: "56223325"
---
# <a name="quickstart-embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>Pikaopas: Power BI -raporttipalvelimen raportin upottaminen iFramella SharePoint-palvelimessa

Tässä pikaoppaassa opit upottamaan Power BI -raporttipalvelimen raportin iFramella SharePoint-sivuun. Jos käytät SharePoint Onlinea, Power BI -raporttipalvelimen on oltava julkisesti käytettävissä. SharePoint Onlinessa Power BI:n verkko-osa, joka toimii Power BI -palvelun kanssa, ei toimi Power BI -raporttipalvelimen kanssa. 

![iFrame-malli](media/quickstart-embed/quickstart_embed_01.png)
## <a name="prerequisites"></a>Edellytykset
* Sinulla on oltava [Power BI -raporttipalvelin](https://powerbi.microsoft.com/report-server/) asennettuna ja määritettynä.
* Sinulla on oltava asennettuna [Power BI -raporttipalvelimelle optimoitu Power BI Desktop](install-powerbi-desktop.md).
* Sinulla on oltava [SharePoint](https://docs.microsoft.com/sharepoint/install/install)-ympäristö asennettuna ja määritettynä.

## <a name="creating-the-power-bi-report-server-report-url"></a>Power BI -raporttipalvelimen raportin URL-osoitteen luominen

1. Lataa malli GitHubista – [blogiesittely](https://github.com/Microsoft/powerbi-desktop-samples).

    ![Lataa PBIX-mallitiedosto](media/quickstart-embed/quickstart_embed_14.png)

2. Avaa PBIX-mallitiedosto GitHubista **Power BI -raporttipalvelimelle optimoidussa Power BI Desktopissa**.

    ![PBI RS Desktop -työkalu](media/quickstart-embed/quickstart_embed_02.png)

3. Tallenna raportti **Power BI -raporttipalvelimeen**. 

    ![PBI RS Save](media/quickstart-embed/quickstart_embed_03.png)

4. Tarkastele raporttia **verkkoportaalissa**.

    ![Verkkoportaali](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capturing-the-url-parameter"></a>URL-parametrin sieppaaminen

Kun sinulla on URL-osoite, voit luoda SharePoint-sivulla iFramen, jonka sisällä raportti isännöidään. Voit lisätä mitä tahansa Power BI -raporttipalvelimen raportin URL-osoitetta varten querystring-parametrin `?rs:embed=true` upottaaksesi raportin iFrameen. 

   Esimerkki:
    ``` 
    http://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embedding-a-power-bi-report-server-report-in-a-sharepoint-iframe"></a>Power BI -raporttipalvelimen raportin upottaminen iFrameen SharePointissa

1. Siirry SharePointin **Sivuston sisältö** -sivulle.

    ![Sivuston sisältö -sivu](media/quickstart-embed/quickstart_embed_05.png)

2. Valitse sivu, johon haluat lisätä raporttiin.

    ![Sivuston sisältö -sivun sovellus](media/quickstart-embed/quickstart_embed_06.png)

3. Valitse hammasrataskuvake ylimpänä oikealla ja valitse **Muokkaa sivua**.

    ![Muokkaa sivua -vaihtoehto](media/quickstart-embed/quickstart_embed_07.png)

4. Valitse **Lisää verkko-osa**.

    ![Lisää verkko-osa](media/quickstart-embed/quickstart_embed_08.png)

5. Valitse **Luokat**-kohdasta **Media ja sisältö**, valitse **Osat**-kohdasta **Sisällön muokkaus**, ja valitse sitten **Lisää** .

    ![Valitse Verkko-osan sisällön muokkaus](media/quickstart-embed/quickstart_embed_09.png) ![Valitse Lisää](media/quickstart-embed/quickstart_embed_091.png)

6. Valitse **Lisää uutta sisältöä napsauttamalla tästä**.

    ![Lisää uutta sisältöä](media/quickstart-embed/quickstart_embed_10.png)

7. Valitse valintanauhasta **Muotoile tekstiä** -välilehti ja valitse sitten **Muokkaa lähdettä**.

     ![Muokkaa lähdettä](media/quickstart-embed/quickstart_embed_11.png)

8. Liitä iFrame-koodi Muokkaa lähdettä -ikkunaan ja valitse OK.

    ![iFrame-koodi](media/quickstart-embed/quickstart_embed_12.png)

     Esimerkki:
     ```html
     <iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. Valitse valintanauhasta **Sivu**-välilehti ja valitse **Lopeta muokkaaminen**.

    ![Lopeta muokkaaminen](media/quickstart-embed/quickstart_embed_13.png)

10. Raportin pitäisi nyt näkyä sivulla.

    ![iFrame-malli](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Pika-aloitus: Power BI -raportin luominen Power BI -raporttipalvelimeen](quickstart-create-powerbi-report.md)  
[Pika-aloitus: Sivutetun raportin luominen Power BI -raporttipalvelimeen](quickstart-create-paginated-report.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/) 