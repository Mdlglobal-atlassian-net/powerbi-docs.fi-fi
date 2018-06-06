---
title: 'Virhe: Excel-työkirjasta ei löydy mitään tietoja'
description: 'Virhe: Excel-työkirjasta ei löydy mitään tietoja'
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: a58af88d23c04c0afd2fa71cab7824b657451b33
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973872"
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>Virhe: Excel-työkirjasta ei löydy mitään tietoja

>[!NOTE]
>Tämä artikkeli koskee Excel 2007:ää ja uudempia versioita.

Kun tuot Excel-työkirjan Power BI:hin, saatat nähdä seuraavan virheilmoituksen:

*Virhe: Excel-työkirjasta ei löydy mitään tietoja. Tietoja ei ehkä ole muotoiltu oikein. Sinun on muokattava työkirjaa Excelissä ja tuotava se uudelleen.*

![](media/service-admin-troubleshoot-excel-workbook-data/pbi_wecouldntfindanydata.png)

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
    
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht1.png)
2. Valitse tiedot sisältävä solualue. Ensimmäisen rivin tulee sisältää sarakeotsikot (sarakkeiden nimet):
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht2.png)
3. Valitse valintanauhan **LISÄÄ**-välilehdessä **Taulukko**. (Tai paina näppäinyhdistelmää **Ctrl + T**.)
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht3.png)
4. Näet seuraavan valintaikkunan. Varmista, että **Taulukossa on otsikot** on valittuna ja valitse sitten **OK**:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlcreatetbl.png)
5. Tietosi on nyt muotoiltu taulukoksi:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xltbl.png)
6. Tallenna työkirja.
7. Palaa Power BI:hin. Valitse vasemman siirtymisruudun alareunassa Nouda tiedot.
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_getdata.png)
8. Valitse **Tiedostot**-ruudussa **Nouda**.
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_getfiles.png)
9. Tuo Excel-työkirjasi uudelleen. Tällä kertaa tuonnin pitäisi löytää taulukko ja onnistua.
   
    Jos tuonti ei edelleenkään onnistu, ilmoita asiasta valitsemalla **Yhteisö **Ohje-valikossa:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_questionmenucommunity.png)
