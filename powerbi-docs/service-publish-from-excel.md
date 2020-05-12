---
title: Julkaiseminen Power BI:hin Microsoft Excelistä
description: Opi julkaisemaan Excel-työkirja Power BI -sivustoon.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/05/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: ca3e954f64665798c439fba47c3135e93fe51ac0
ms.sourcegitcommit: a199dda2ab50184ce25f7c9a01e7ada382a88d2c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/06/2020
ms.locfileid: "82866790"
---
# <a name="publish-to-power-bi-from-microsoft-excel"></a>Julkaiseminen Power BI:hin Microsoft Excelistä
Microsoft Excel 2016:n tai uudemman version avulla voit julkaista Excel-työkirjat suoraan [Power BI](https://powerbi.microsoft.com) -työtilaan, jossa voit luoda erittäin vuorovaikutteisia raportteja ja koontinäyttöjä työkirjan tietojen perusteella. Voit sitten jakaa merkityksellisiä tietoja muiden kanssa organisaatiossasi.

![Julkaise työkirja Power BI:hin](media/service-publish-from-excel/pbi_uploadexport2.png)

Kun julkaiset työkirjan Power BI:hin, ota huomioon muutama asia:

* Tilin, jota käytät kirjautuessasi Officeen, OneDrive for Businessiin (jos käytät siihen tallennettuja työkirjoja) ja Power BI:hin, on oltava sama tili.
* Et voi julkaista tyhjää työkirjaa tai työkirjaa, joka ei sisällä Power BI:n tukemaa sisältöä.
* Et voi julkaista salattuja tai salasanalla suojattuja työkirjoja tai työkirjoja Information Protection -hallinnalla.
* Power BI:hin julkaiseminen edellyttää, että moderni todentaminen on käytössä (oletus). Jos se ei ole käytössä, Julkaise-vaihtoehto ei ole käytettävissä Tiedosto-valikon kautta.

## <a name="publish-your-excel-workbook"></a>Excel-työkirjan julkaiseminen
Kun haluat julkaista Excel-työkirjasi, valitse Excelissä **Tiedosto** > **Julkaise** ja valitse joko **Lataa** tai **Vie**.

Jos **lataat** työkirjasi Power BI:hin, voit käsitellä työkirjaa samalla tavalla kuin käyttäessäsi Excel Onlinea. Voit myös kiinnittää työkirjan valintoja Power BI:n koontinäyttöihin ja jakaa työkirjasi tai sen valitut osat muille Power BI:n kautta.

Jos valitset **Vie**, voit viedä taulukon tiedot ja sen tietomallin Power BI:n tietojoukkoon, jonka avulla voit sitten luoda Power BI -raportteja ja -koontinäyttöjä.

### <a name="local-file-publishing"></a>Paikallisen tiedoston julkaiseminen
Excel tukee paikallisten Excel-tiedostojen julkaisemista. Niitä ei tarvitse tallentaa OneDrive for Businessiin tai SharePoint Onlineen.

> [!IMPORTANT]
> Voit julkaista paikallisia tiedostoja vain, jos käytössäsi on Excel 2016 (tai uudempi versio) ja Office 365 -tilaus. Erilliset Excel 2016 -asennukset voivat julkaista Power BI:hin, mutta vain silloin, kun työkirja on tallennettu OneDrive for Businessiin tai SharePoint Onlineen.
> 

Kun valitset **Julkaise**, voit valita työtilan, johon haluat julkaista. Jos Excel-tiedostosi on OneDrive for Businessissa, voit julkaista sen *omassa työtilassa*. Jos Excel-tiedosto sijaitsee paikallisessa asemassa, voit julkaista *omassa työtilassa* tai jaetussa työtilassa, johon sinulla on käyttöoikeus.

![Julkaise Power BI:hin](media/service-publish-from-excel/pbi_choose_workspace.png)

Kaksi vaihtoehtoa, miten saat työkirjasi Power BI:hin.

![Julkaise Power BI:hin](media/service-publish-from-excel/pbi_uploadexport3.png)

Julkaisemisen jälkeen julkaistava työkirjan sisältö tuodaan Power BI:hin erilleen paikallisesta tiedostosta. Jos haluat päivittää tiedoston Power BI:ssä, sinun on julkaistava päivitetty versio uudelleen, tai voit myös päivittää tiedot määrittämällä ajoitetun päivityksen työkirjalle tai Power BI -tietojoukolle.

### <a name="publishing-from-a-standalone-excel-installation"></a>Julkaiseminen erillisestä Excel-asennuksesta
Kun julkaiset erillisestä Excel-asennuksesta, työkirja on tallennettava OneDrive for Businessiin. Valitse **Tallenna pilvipalveluun** ja valitse sijainti OneDrive for Businessissa.

![Tallenna OneDrive for Businessiin](media/service-publish-from-excel/pbi_savetoonedrive2.png)

Kun työkirja on tallennettu OneDrive for Businessiin ja valitset **Julkaise**, näkyviin tulee kaksi vaihtoehtoa, joilla saat työkirjasi Power BI:hin, eli **Lataa** ja **Vie**:

![Power BI -vaihtoehdot](media/service-publish-from-excel/pbi_uploadexport2.png)

#### <a name="upload-your-workbook-to-power-bi"></a>Työkirjan lataaminen Power BI:hin
Kun valitset **Lataa**-vaihtoehdon, työkirjasi näkyy Power BI:ssä aivan samalla tavalla kuin se näkyisi Excel Onlinessa. Excel Onlinesta poiketen käytettävissäsi on kuitenkin käteviä ominaisuuksia, joilla voit kiinnittää laskentataulukoiden elementtejä koontinäyttöihin.

Työkirjaa ei voi muokata Power BI:ssä. Jos haluat muuttaa tietoja, voit valita **Muokkaa**-vaihtoehdon ja sitten työkirjan muokkaamisen joko Excel Onlinessa tai tietokoneesi Excelissä. Tekemäsi muutokset tallennetaan työkirjaan OneDrive for Businessiin.

kun valitset **Lataa**-vaihtoehdon, Power BI:ssä ei luoda mitään tietojoukkoja. Työkirja näkyy työtilan siirtymisruudussa Raportit-kohdassa. Power BI:hin ladatuilla työkirjoilla on erityinen Excel-kuvake, jotka merkitsevät ne ladatuiksi Excel-työkirjoiksi.

Valitse **Lataa**-vaihtoehto, jos sinulla on vain tietoja laskentataulukoissa tai sinulla Pivot-taulukoita ja kaavioita, jotka haluat nähdä Power BI:ssä.

Lataus-toiminnon käyttäminen Julkaise Power BI:hin -kohdasta Excelissä on samantapaista kuin jos valitsisit selaimen Power BI:ssä **Nouda tiedot > Tiedosto > OneDrive for Business > Yhdistä, hallitse ja näytä Excel Power BI:ssä**.

#### <a name="export-workbook-data-to-power-bi"></a>Työkirjan tietojen vieminen Power BI:hin
Kun valitset **Vie**-vaihtoehdon, taulukoissa ja/tai tietomallissa tuetut tiedot viedään uuteen tietojoukkoon Power BI:ssä. Työkirjassa olevat Power View -taulukot luodaan uudelleen Power BI:ssä raportteina.

Voit jatkaa työkirjan muokkaamista. Kun tekemäsi muutokset tallennetaan, ne synkronoidaan Power BI:n tietojoukon kanssa yleensä noin tunnin kuluessa. Jos tarvitset enemmän välittömiä päivityksiä, voit valita **Julkaise** uudelleen Excelistä, jolloin tekemäsi muutokset viedään heti. Raporttien ja koontinäyttöjen visualisoinnit päivitetään myös.

Valitse **Julkaise**-vaihtoehto, jos olet ladannut tiedot tietomalliin Hae ja muunna -toiminnolla tai Power Pivotin toiminnoilla tai jos työkirjassa on visualisointeja sisältäviä Power View -taulukoita, jotka haluat nähdä Power BI:ssä.

**Vie**-toiminnon käyttäminen on hyvin samantapaista kuin jos valitsisit selaimen Power BI:ssä **Nouda tiedot > Tiedosto > OneDrive for Business > Vie Excel-tiedon Power BI:hin**.

## <a name="publishing"></a>Julkaiseminen
Kun valitset jommankumman vaihtoehdon, Excel kirjautuu Power BI:hin nykyiseltä tililtäsi ja sitten julkaisee työkirjan Power BI -työtilaan. Voit seurata julkaisuprosessin etenemistä Excelin tilariviltä.

![tilarivi Power BI:hin julkaisemista varten](media/service-publish-from-excel/pbi_publishingstatus.png)

Kun toiminto on valmis, voit siirtyä Power BI:hin suoraan Excelistä.

![siirry Power BI:hin](media/service-publish-from-excel/pbi_gotopbi.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Excel-tiedot Power BI:ssä](service-excel-workbook-files.md)  
Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

