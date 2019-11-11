---
title: Tietojoukon päivittäminen OneDrivesta tai SharePoint Onlinesta
description: Power BI Desktop -tiedostosta luodun tietojoukon päivittäminen – OneDrive tai SharePoint Online
author: mgblythe
ms.reviewer: kayu
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/04/2019
ms.author: mblythe
LocalizationGroup: Data refresh
ms.openlocfilehash: 1d9e38b94cf3c345df12cb22a0ab3309dff263c2
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73877553"
---
# <a name="refresh-a-dataset-stored-on-onedrive-or-sharepoint-online"></a>Päivitä Onedriveen tai SharePoint Onlineen tallennettuja tietojoukkoja
Tiedostojen tuominen OneDrivesta tai SharePoint Onlinesta Power BI -palveluun on mainio tapa varmistaa, että Power BI Desktop -työsi synkronoidaan Power BI -palvelun kanssa.

## <a name="advantages-of-storing-a-power-bi-desktop-file-on-onedrive-or-sharepoint-online"></a>Power BI Desktop -tiedoston tallennuksesta OneDriveen tai SharePoint Onlineen saatavat edut
Kun tallennat Power BI Desktop -tiedoston OneDriveen tai SharePoint Onlineen, tiedoston malliin lataamasi kaikki tiedot tuodaan tietojoukkoon. Tiedostoon luomasi kaikki raportit ladataan **Raportit**-kohtaan Power BI -palvelussa. Oletetaan, että teet muutoksia tiedostoosi OneDrivessa tai SharePoint Onlinessa. Nämä muutokset voivat sisältää uusien mittayksiköiden lisäämisen, sarakkeiden nimien muuttamisen tai visualisointien muokkaamisen. Kun tiedosto on tallennettu, Power BI -palvelu synkronoi myös nämä muutokset yleensä noin tunnin kuluessa.

Voit suorittaa manuaalisen kertapäivityksen suoraan Power BI Desktopissa valitsemalla **Aloitus**-valintanauhasta **Päivitä**. Kun valitset **Päivitä**, päivität tiedoston malliin päivitetyt tiedot alkuperäisestä tietolähteestä. Tällainen päivitys tapahtuu kokonaan itse Power BI Desktop -sovelluksesta. Se poikkeaa Power BI:n manuaalisesta tai ajoitetusta päivityksestä, ja on tärkeää ymmärtää niiden ero.

![](media/refresh-desktop-file-onedrive/pbix-refresh.png)

Kun tuot Power BI Desktop -tiedoston OneDrivesta tai SharePoint Onlinesta, lataat tiedot ja mallin tiedot Power BI:n tietojoukkoon. Haluat varmasti päivittää tietojoukon Power BI -palveluun, koska raporttisi perustuvat siihen. Koska tietolähteet ovat ulkoisia, voit päivittää tietojoukon manuaalisesti valitsemalla **Päivitä nyt**. Vaihtoehtoisesti voit asettaa päivityksen ajoituksen valitsemalla **Ajoita päivitys**. 

![](media/refresh-desktop-file-onedrive/powerbi-service-refresh.png)

Kun päivität tietojoukon, Power BI ei muodosta yhteyttä OneDriven tai SharePoint Onlinen tiedostoon kyselemään päivitettyjä tietoja. Se käyttää tietojoukon tietoja ja muodostaa suoraan yhteyden tietolähteisiin päivitettyjen tietojen kyselyä varten. Sen jälkeen se lataa tiedot tietojoukkoon. Näitä tietojoukon päivitettyjä tietoja ei synkronoida takaisin OneDriven tai SharePoint Onlinen tiedostoon.

## <a name="whats-supported"></a>Tuetut toiminnot:
Power BI tukee **Päivitä**- ja **Ajoita päivitys** -komentoja tietojoukoille, jotka on luotu sellaisista Power BI Desktop -tiedostoista, jotka tuotu paikallisesta asemasta, jossa **Nouda tiedot**- tai **Kyselyeditori**-kohtaa käytetään yhteyden muodostamiseen ja tietojen lataamiseen seuraavista tietolähteistä.

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
* Kaikki online-tietolähteet, jotka näkyvät Power BI Desktopin **Nouda tiedot**- ja **Kyselyeditori**-kohdassa.
* Kaikki paikalliset tietolähteet, jotka näkyvät Power BI Desktopin **Nouda tiedot**- ja **Kyselyeditori**-kohdassa lukuun ottamatta Hadoop-tiedostoa (HDFS) ja Microsoft Exchangea.

<!-- Refresh Data sources-->
[!INCLUDE [refresh-datasources](./includes/refresh-datasources.md)]

> [!NOTE]
> Yhdyskäytävä on oltava asennettuna ja käynnissä, jotta Power BI voi muodostaa yhteyden paikallisiin tietolähteisiin ja päivittää tietojoukon.
> 
> 

## <a name="onedrive-or-onedrive-for-business-whats-the-difference"></a>OneDrive vai OneDrive for Business? Mikä niiden ero on?
Jos sinulla on sekä henkilökohtainen OneDrive että OneDrive for Business, sinun kannattaa säilyttää tiedostot, jotka haluat tuoda Power BI:hin OneDrive for Businessissa. Syynä on se, että käytät todennäköisesti kahta eri tiliä niille kirjautumista varten.

Kun muodostat yhteyden OneDrive for Businessiin Power BI:ssä, yhteyden muodostaminen on helppoa, koska Power BI -tili on usein sama tili kuin OneDrive for Business -tili. Voit henkilökohtaisen OneDriven avulla yleensä kirjautua sisään eri [Microsoft-tilillä](https://account.microsoft.com).

Kun olet kirjautunut sisään Microsoft-tilillesi, muista valita **Pysy kirjautuneena** . Power BI voi tämän jälkeen synkronoida mitä tahansa tekemiäsi päivityksiä Power BI Desktop -tiedostoon ja Power BI -tietojoukkoihin.

![](media/refresh-desktop-file-onedrive/refresh_signin_keepmesignedin.png)

Jos olet muuttanut Microsoft-tunnistetietosi, muutoksia ei voi synkronoida OneDrive-tiedostosi ja Power BI -tietojoukkosi välillä. Sinun on muodostettava yhteys tiedostoon ja tuotava se uudelleen OneDrivesta.

## <a name="how-do-i-schedule-refresh"></a>Kuinka päivitys ajoitetaan?
Kun asetat päivitysaikataulun, Power BI muodostaa yhteyden suoraan tietolähteisiin. Power BI käyttää tietojoukon yhteystietoja ja tunnistetietoja kyselemään päivitettyjä tietoja. Power BI lataa sitten päivitetyt tiedot tietojoukkoon. Se päivittää sen jälkeen kaikki raporttivisualisoinnit ja koontinäytöt tämän tietojoukon perusteella Power BI -palvelussa.

Lisätietoja ajoitetun päivityksen määrityksestä on artikkelissa [Ajoitetun päivityksen määrittäminen](refresh-scheduled-refresh.md).

## <a name="when-things-go-wrong"></a>Jos ilmenee ongelmia
Jos ilmenee ongelmia, se johtuu yleensä siitä, että Power BI ei voi kirjautua sisään tietolähteisiin. Asiat voivat myös mennä pieleen, jos tietojoukko yrittää muodostaa yhteyden paikalliseen tietolähteeseen, mutta yhdyskäytävä on offline-tilassa. Varmista näiden ongelmien välttämiseksi, että Power BI voi kirjautua sisään tietolähteisiin. Yritä kirjautua sisään tietolähteisiin **tietolähteen tunnistetiedoissa**. Joskus salasana, jota käytät kirjautuessasi sisään tietolähteeseen, muuttuu, tai Power BI kirjataan ulos tietolähteestä.

Kun tallennat muutoksesi Power BI Desktop -tiedostoon OneDrivessa, eivätkä kyseiset muutokset näy Power BI:ssa noin tunnin kuluessa, se voi johtua siitä, että Power BI ei pysty muodostamaan yhteyttä OneDriveen. Yritä muodostaa yhteys uudelleen tiedostoon OneDrivessa. Jos sinua pyydetään kirjautumaan sisään, varmista, että valitset vaihtoehdon **Pysy kirjautuneena**. Koska Power BI ei pystynyt muodostamaan yhteyttä OneDriveen tiedoston synkronoimiseksi, sinun on tuotava tiedosto uudelleen.

Varmista, että jätät kohtaan **Lähetä päivitysvirheen ilmoitusviesti sähköpostiini** valintamerkin. Haluat tietää heti, jos ajoitettu päivitys epäonnistuu.

## <a name="troubleshooting"></a>Vianmääritys
Joskus tietojen päivittäminen ei mene odotetulla tavalla. Kohtaat yleensä tietojen päivitysongelmia, kun olet muodostanut yhteyden yhdyskäytävään. Tutustu yhdyskäytävän vianmääritystä koskeviin artikkeleihin, joissa on esitetty työkaluja ja tunnettuja ongelmia.

[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)

[Power BI -yhdyskäytävän vianmääritys – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)

Onko sinulla kysyttävää? Voit esittää kysymyksiä [Power BI -yhteisössä](https://community.powerbi.com/).

