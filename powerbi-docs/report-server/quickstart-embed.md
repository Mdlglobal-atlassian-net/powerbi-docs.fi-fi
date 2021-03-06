---
title: Power BI -raporttipalvelimen raportin upottaminen iFramella SharePoint-palvelimessa
description: Tässä artikkelissa kerrotaan, miten Power BI -raporttipalvelimen raportti upotetaan iFramella SharePoint-palvelimessa
author: maggiesMSFT
ms.author: maggies
ms.date: 08/12/2019
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
ms.openlocfilehash: 4e7616ec3ce6552130848bc0508bf8b9ac8ac965
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "75762596"
---
# <a name="embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>Power BI -raporttipalvelimen raportin upottaminen iFramella SharePoint-palvelimessa

Tässä artikkelissa opit upottamaan Power BI -raporttipalvelimen raportin iFramella SharePoint-sivuun. Jos käytät SharePoint Onlinea, Power BI -raporttipalvelimen on oltava julkisesti käytettävissä. SharePoint Onlinessa Power BI:n verkko-osa, joka toimii Power BI -palvelun kanssa, ei toimi Power BI -raporttipalvelimen kanssa.  

![iFrame-malli](media/quickstart-embed/quickstart_embed_01.png)

## <a name="prerequisites"></a>Edellytykset
* [Power BI -raporttipalvelin](https://powerbi.microsoft.com/report-server/) asennettuna ja määritettynä.
* [Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)](install-powerbi-desktop.md) asennettuna.
* [SharePoint](https://docs.microsoft.com/sharepoint/install/install)-ympäristö asennettuna ja määritettynä.
* Internet Explorer 11:tä tuetaan vain, jos tiedostotilaksi on määritetty IE11 (Edge) -tila tai käytettäessä SharePoint Onlinea. Voit käyttää muita tuettuja selaimia paikallisessa SharePointissa ja SharePoint Onlinessa.

## <a name="create-the-power-bi-report-url"></a>Luo Power BI -raportin URL-osoite

1. Lataa malli GitHubista: [Blogiesittely](https://github.com/Microsoft/powerbi-desktop-samples). Valitse **Kloonaa tai lataa** ja valitse sitten **Lataa ZIP**.

    ![Lataa PBIX-mallitiedosto](media/quickstart-embed/quickstart_embed_14.png)

2. Pura ZIP-tiedosto ja avaa .pbix-mallitiedosto Power BI -raporttipalvelimelle optimoidussa Power BI Desktopissa.

    ![PBI RS Desktop -työkalu](media/quickstart-embed/quickstart_embed_02.png)

3. Tallenna raportti **Power BI -raporttipalvelimeen**. 

    ![PBI RS Save](media/quickstart-embed/quickstart_embed_03.png)

4. Tarkastele raporttia Power BI -raporttipalvelimen verkkoportaalissa.

    ![Verkkoportaali](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capture-the-url-parameter"></a>Sieppaa URL-parametri

Kun sinulla on URL-osoite, voit luoda SharePoint-sivulla iFramen, jonka sisällä raportti isännöidään. Lisää mitä tahansa Power BI -raporttipalvelimen raportin URL-osoitetta varten seuraava kyselymerkkijonoparametri, joka upottaa raporttisi SharePointin iFrameen: `?rs:embed=true`.

   Esimerkki:
    ``` 
    https://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embed-the-report-in-a-sharepoint-iframe"></a>Upota raportti SharePointin iFrameen

1. Siirry SharePointin **Sivuston sisältö** -sivulle.

    ![Sivuston sisältö -sivu](media/quickstart-embed/quickstart_embed_05.png)

2. Valitse sivu, johon haluat lisätä raporttiin.

    ![Sivuston sisältö -sivun sovellus](media/quickstart-embed/quickstart_embed_06.png)

3. Valitse hammasrataskuvake oikeasta yläkulmasta ja valitse **Muokkaa sivua**.

    ![Muokkaa sivua -vaihtoehto](media/quickstart-embed/quickstart_embed_07.png)

4. Valitse **Lisää verkko-osa**.

5. Valitse **Luokat**-kohdasta **Media ja sisältö**. Valitse **Osat**-kohdasta **Sisältöeditori** ja valitse sitten **Lisää**.

    ![Valitse Verkko-osan sisällön muokkaus](media/quickstart-embed/quickstart_embed_09.png)

6. Valitse **Lisää uutta sisältöä napsauttamalla tästä**.

7. Valitse yläreunan valikosta **Muotoile tekstiä** ja valitse sitten **Muokkaa lähdettä**.

     ![Muokkaa lähdettä](media/quickstart-embed/quickstart_embed_11.png)

8. Liitä **Muokkaa lähdettä** -ikkunassa iFrame-koodi **HTML-lähde**-kohtaan ja valitse **OK**.

    ![iFrame-koodi](media/quickstart-embed/quickstart_embed_12.png)

     Esimerkki:
     ```html
     <iframe width="800" height="600" src="https://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. Valitse yläreunan valikosta **Sivu** ja valitse sitten **Lopeta muokkaaminen**.

    ![Lopeta muokkaaminen](media/quickstart-embed/quickstart_embed_13.png)

    Raportti tulee näkyviin sivulla.

    ![iFrame-malli](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>Seuraavat vaiheet

- [Power BI -raportin luominen Power BI -raporttipalvelimeen](quickstart-create-powerbi-report.md)  
- [Sivutetun raportin luominen Power BI -raporttipalvelimeen](quickstart-create-paginated-report.md)  

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/). 
