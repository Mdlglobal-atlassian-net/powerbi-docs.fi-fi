---
title: Tietojoukon päivittäminen OneDrivesta tai SharePoint Onlinesta
description: Power BI Desktop -tiedostosta luodun tietojoukon päivittäminen – OneDrive tai SharePoint Online
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mblythe
LocalizationGroup: Data refresh
ms.openlocfilehash: 2acdada1a0b6955fb7d85f445bdbf5895b795bb4
ms.sourcegitcommit: 81ba3572531cbe95ea0b887b94e91f94050f3129
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/06/2019
ms.locfileid: "66751181"
---
# <a name="refresh-a-dataset-stored-on-onedrive-or-sharepoint-online"></a>Päivitä Onedriveen tai SharePoint Onlineen tallennettuja tietojoukkoja
Tiedostojen tuominen Onedrivesta tai SharePoint Onlinesta Power BI -palveluun on hyvä tapa varmistaa, että työ, jota olet tekemässä **Power BI Desktopissa** pysyy synkronoituna Power BI -palveluun.

## <a name="advantages-of-storing-a-power-bi-desktop-file-on-onedrive-or-sharepoint-online"></a>Power BI Desktop -tiedoston tallennuksesta OneDriveen tai SharePoint Onlineen saatavat edut
Kun tallennat **Power BI Desktop** -tiedoston OneDriveen tai SharePoint Onlineen, tiedoston malliin lataamasi tiedot tuodaan tietojoukkoon, ja tiedostoon luomasi raportit ladataan kohtaan **Raportit** Power BI -palvelussa. Kun teet muutoksia tiedostoon OneDrivessa tai SharePoint Onlinessa, esimerkiksi lisäämällä uusia mittareita, muuttamalla sarakenimiä tai muokkaamalla visualisointeja ja kun tallennat tiedoston, muutokset päivitetään myös Power BI-palveluun yleensä noin tunnin kuluessa.

Voit suorittaa vain kerran manuaalisen päivityksen suoraan Power BI Desktopissa valitsemalla Aloitus-valintanauhasta Päivitä. Kun valitset tässä kohdassa Päivitä, tiedot *tiedoston* mallissa päivitetään alkuperäisen tietolähteen päivitetyillä tiedoilla. Tällainen päivitys kokonaan Power BI Desktop-sovelluksen sisällä eroaa manuaalisesta tai ajoitetusta päivityksestä Power BI:ssä, ja on tärkeää ymmärtää tämä ero.

![](media/refresh-desktop-file-onedrive/pbix-refresh.png)

Kun tuot Power BI Desktop-tiedostoa OneDriveen tai SharePoint Onlineen, data sekä muita tietoja mallista ladataan tietojoukkoon Power BI -palvelussa. Power BI -palvelussa, ei Power BI Desktopissa, haluat päivittää tietojoukon tietoja, koska siihen raporttisi Power BI -palvelussa perustuvat. Koska tietolähteet ovat ulkoisia, voit päivittää tietojoukon manuaalisesti valitsemalla **Päivitä nyt** tai voit asettaa päivityksen ajoituksen valitsemalla **Ajoita päivitys**.

Kun päivität tietojoukon, Power BI ei muodosta yhteyttä OneDriveen tai SharePoint Onlineen kyselemään päivitettyjä tietoja. Se käyttää tietojoukon tietoja ja muodostaa suoraan yhteyden tietolähteisiin päivitettyjen tietojen kyselyä varten, minkä jälkeen se lataa tiedot tietojoukkoon. Näitä tietojoukon päivitettyjä tietoja ei synkronoida takaisin tiedoston OneDrivessa tai SharePoint Onlinessa.

## <a name="whats-supported"></a>Tuetut toiminnot:
Power BI, Päivitä nyt ja Ajoita päivitys ovat tuettuja tietojoukkoja, jotka on luotu Power BI Desktop -tiedostoista, jotka on tuotu paikallisesta asemasta, jossa Nouda tiedot/Kyselyeditoria käytetään yhteyden muodostamiseen ja tietojen lataamiseen missä tahansa seuraavista tietolähteistä:

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
* Kaikki online-tietolähteet, jotka näkyvät Power BI Desktopin kohdassa Nouda tiedot ja Kyselyeditorissa.
* Kaikki paikalliset tietolähteet, jotka näkyvät Power BI Desktopin kohdassa Nouda tiedot ja Kyselyeditorissa lukuun ottamatta Hadoop-tiedostoa (HDFS) ja Microsoft Exchangea.

<!-- Refresh Data sources-->
[!INCLUDE [refresh-datasources](./includes/refresh-datasources.md)]

> [!NOTE]
> Yhdyskäytävä on oltava asennettuna ja käynnissä, jotta Power BI voi muodostaa yhteyden paikallisiin tietolähteisiin ja päivittää tietojoukon.
> 
> 

## <a name="onedrive-or-onedrive-for-business-whats-the-difference"></a>OneDrive vai OneDrive for Business? Mikä niiden ero on?
Jos sinulla on sekä henkilökohtainen OneDrive että OneDrive for Business, on suositeltavaa säilyttää tiedostot, jotka haluat tuoda Power BI:ssa OneDrive for Business -palveluun. Syynä on se, että käytät todennäköisesti kahta eri tiliä niille kirjautumista varten.

Yhteyden muodostaminen OneDrive for Business -palveluun Power BI:ssa on yleensä saumaton, koska tili, jota käytit Power BI -kirjautumiseen on usein sama tili, jota käytetään kirjauduttaessa OneDrive for Business -palveluun. Henkilökohtaisen OneDrive olet todennäköisesti kuitenkin kirjautunut sisään toisella [Microsoft-tilillä](https://account.microsoft.com).

Kun olet kirjautunut sisään Microsoft-tilillesi, muista valita Pysy kirjautuneena -vaihtoehto. Power BI voi tämän jälkeen synkronoida mitä tahansa tekemiäsi päivityksiä Power BI Desktop -tiedostoon ja Power BI -tietojoukkoihin  
    ![](media/refresh-desktop-file-onedrive/refresh_signin_keepmesignedin.png)

Jos teet muutoksia OneDrive-tiedostoon, joita ei voi synkronoida tietojoukkoon tai raporttiin Power BI:ssa, koska Microsoft-tilisi tunnistetiedot ovat ehkä muuttuneet, sinun pitää muodostaa yhteys ja tuoda tiedostosi takaisin omasta OneDrivesta.

## <a name="how-do-i-schedule-refresh"></a>Kuinka päivitys ajoitetaan?
Kun asetat päivitysaikataulun, Power BI muodostaa suoraan yhteyden tietolähteisiin käyttämällä tietojoukon yhteystietoja ja tunnistetietoja päivitettyjen tietojen kyselyyn ja lataa sitten päivitetyt tiedot tietojoukkoon. Kaikki visualisoinnit raportteihin ja koontinäyttöihin, jotka perustuvat Power BI-palvelussa oleviin tietojoukkoihin, päivitetään myös.

Lisätietoja ajoitetun päivityksen määrityksestä on kohdassa [Ajoitetun päivityksen määrittäminen](refresh-scheduled-refresh.md).

## <a name="when-things-go-wrong"></a>Jos ilmenee ongelmia
Ongelmat johtuvat yleensä siitä, että Power BI ei voi kirjautua sisään tietolähteisiin tai jos tietojoukko muodostaa yhteyden paikalliseen tietolähteeseen, mutta yhdyskäytävä on offline-tilassa. Varmista, että Power BI voi kirjautua sisään tietolähteisiin. Jos tietolähteeseen kirjautumisen salasana muuttuu tai jos Power BI kirjataan ulos tietolähteestä, yritä kirjautua uudelleen sisään tietolähteisiin Tietolähteen tunnistetiedot -kohdassa.

Jos olet tekemässä muutoksia Power BI Desktop -tiedostoon OneDrivessa ja tallennat, eivätkä kyseiset muutokset näy Power BI:ssa noin tunnin kuluessa, se voi johtua siitä, että Power BI ei pysty muodostamaan yhteyttä OneDriveen. Yritä muodostaa yhteys uudelleen tiedostoon OneDrivessa. Jos sinua pyydetään kirjautumaan sisään, varmista, että valitset vaihtoehdon Pysy kirjautuneena. Koska Power BI ei pystynyt muodostamaan yhteyttä OneDriveen tiedoston synkronoimiseksi, sinun on tuotava tiedosto uudelleen.

Varmista, että jätät kohtaan **Lähetä päivitysvirheen ilmoitusviesti sähköpostiini** valintamerkin. Haluat tietää heti, jos ajoitettu päivitys epäonnistuu.

## <a name="troubleshooting"></a>Vianmääritys
Joskus tietojen päivittäminen ei mene odotetulla tavalla. Yleensä tämä on yhdyskäytävään liittyvä ongelma. Tutustu yhdyskäytävän vianmääritystä koskeviin artikkeleihin, joissa on esitetty työkaluja ja tunnettuja ongelmia.

[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)

[Power BI -yhdyskäytävän vianmääritys – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

