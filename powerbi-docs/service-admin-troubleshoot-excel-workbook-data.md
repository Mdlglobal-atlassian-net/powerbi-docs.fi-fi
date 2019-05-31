---
title: 'Virhe: Excel-työkirjasta ei löydy mitään tietoja'
description: 'Virhe: Excel-työkirjasta ei löydy mitään tietoja'
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/30/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 6fb02e6cbaca30859aa00f58ae07c9a3fd7f6fe0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65101393"
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>Virhe: Excel-työkirjasta ei löydy mitään tietoja

>[!NOTE]  
>Tämä artikkeli koskee Excel 2007:ää ja uudempia versioita.

Kun tuot Excel-työkirjan Power BI:hin, saatat nähdä seuraavan virheilmoituksen:

*Virhe: Taulukoksi muotoiltuja tietoja ei löytynyt. Jos haluat tuoda Excelistä Power BI-palveluun, Muotoile tiedot taulukoksi. Valitse kaikki taulukkoon haluamasi ja painamalla Ctrl + T tiedot.*

![Tietoja ei löydy työkirjasta](media/service-admin-troubleshoot-excel-workbook-data/power-bi-we-couldnt-find-any-data.png)

## <a name="quick-solution"></a>Nopea ratkaisu
1. Muokkaa työkirjaa Excelissä.
2. Valitse tiedot sisältävä solualue. Ensimmäisen rivin tulee sisältää sarakeotsikot (sarakkeiden nimet).
3. Luo taulukko painamalla näppäinyhdistelmää **Ctrl + T**.
4. Tallenna työkirja.
5. Palaa Power BI:hin ja tuo työkirja uudelleen. Jos käytössäsi on Excel 2016 ja olet tallentanut työkirjan OneDrive for Businessiin, valitse Excelissä Tiedosto > Julkaise.

## <a name="details"></a>Tiedot
### <a name="cause"></a>Syy
Voit luoda Excelissä solualueesta **taulukon**, mikä helpottaa tietojen lajittelemista, suodattamista ja muotoilemista.

Kun tuot Excel-työkirjan, Power BI etsii taulukot ja tuo ne tietojoukkona. Jos se ei löydä taulukoita, näkyviin tulee tämä virhesanoma.

### <a name="solution"></a>Ratkaisu
1. Avaa työkirja Excelissä. 
    >[!NOTE]
    >Tässä olevat kuvat ovat Excel 2013:sta. Jos käytössäsi on jokin muu versio, asiat saattaa näyttää hieman erilaisilta, mutta vaiheet ovat samat.
    
    ![Avaa työkirja](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-worksheet-1.png)
2. Valitse tiedot sisältävä solualue. Ensimmäisen rivin tulee sisältää sarakeotsikot (sarakkeiden nimet):
   
    ![Valitse solualue](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-worksheet-2.png)
3. Valitse valintanauhan **LISÄÄ**-välilehdessä **Taulukko**. (Tai paina näppäinyhdistelmää **Ctrl + T**.)
   
    ![Lisää taulukko](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-worksheet-3.png)
4. Näet seuraavan valintaikkunan. Varmista, että **Taulukossa on otsikot** on valittuna ja valitse sitten **OK**:
   
    ![Luo taulukko](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-create-table.png)
5. Tietosi on nyt muotoiltu taulukoksi:
   
    ![tiedot muotoiltuna taulukoksi](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-table.png)
6. Tallenna työkirja.
7. Palaa Power BI:hin. Valitse vasemman siirtymisruudun alareunassa Nouda tiedot.
   
    ![Nouda tiedot](media/service-admin-troubleshoot-excel-workbook-data/power-bi-get-data.png)
8. Valitse **Tiedostot**-ruudusta **Nouda**.
   
    ![Hae tiedostot](media/service-admin-troubleshoot-excel-workbook-data/power-bi-get-files.png)
9. Tuo Excel-työkirjasi uudelleen. Tällä kertaa tuonnin pitäisi löytää taulukko ja onnistua.
   
    Jos tuonti ei edelleenkään onnistu, ilmoita asiasta valitsemalla **Yhteisö **Ohje-valikossa:
   
    ![Yhteisölinkki](media/service-admin-troubleshoot-excel-workbook-data/power-bi-question-menu-community.png)
