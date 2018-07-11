---
title: Power BI Desktop -tiedostosta luodun tietojoukon päivittäminen – paikallinen
description: Power BI Desktop -tiedostosta luodun tietojoukon päivittäminen – tiedosto paikallisessa asemassa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: 1d9d4b13c6453f32a470b90980b03490d46ee424
ms.sourcegitcommit: 001ea0ef95fdd4382602bfdae74c686de7dc3bd8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/11/2018
ms.locfileid: "38937128"
---
# <a name="refresh-a-dataset-created-from-a-power-bi-desktop-file-on-a-local-drive"></a>Power BI Desktop -tiedostosta luodun tietojoukon päivittäminen – tiedosto paikallisessa asemassa
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

Voit suorittaa vain kerran manuaalisen päivityksen suoraan Power BI Desktopissa valitsemalla Aloitus-valintanauhasta Päivitä. Kun valitset tässä kohdassa Päivitä, tiedot *tiedoston* mallissa päivitetään alkuperäisen tietolähteen päivitetyillä tiedoilla. Tällainen päivitys kokonaan Power BI Desktop-sovelluksen sisällä eroaa manuaalisesta tai ajoitetusta päivityksestä Power BI:ssä, ja on tärkeää ymmärtää tämä ero.

![](media/refresh-desktop-file-local-drive/pbix-refresh.png)

Kun tuot Power BI Desktop-tiedostoa paikalliselta asemalta, data sekä muita tietoja mallista ladataan tietojoukkoon Power BI -palvelussa. Power BI -palvelussa, ei Power BI Desktopissa, haluat päivittää tietojoukon tietoja, koska siihen raporttisi Power BI -palvelussa perustuvat. Koska tietolähteet ovat ulkoisia, voit päivittää tietojoukon manuaalisesti valitsemalla **Päivitä nyt** tai voit asettaa päivityksen ajoituksen valitsemalla **Ajoita päivitys**.

Kun päivität tietojoukon, Power BI ei muodosta yhteyttä paikallisen aseman tiedostoon kyselemään päivitettyjä tietoja. Se käyttää tietojoukon tietoja ja muodostaa suoraan yhteyden tietolähteisiin päivitettyjen tietojen kyselyä varten, minkä jälkeen se lataa tiedot tietojoukkoon.

> [!NOTE]
> Tietojoukon päivitettyjä tietoja ei synkronoida takaisin tiedoston paikalliselle asemalle.
> 
> 

## <a name="how-do-i-schedule-refresh"></a>Kuinka päivitys ajoitetaan?
Kun asetat päivitysaikataulun, Power BI muodostaa suoraan yhteyden tietolähteisiin käyttämällä tietojoukon yhteystietoja ja tunnistetietoja päivitettyjen tietojen kyselyyn ja lataa sitten päivitetyt tiedot tietojoukkoon. Kaikki visualisoinnit raportteihin ja koontinäyttöihin, jotka perustuvat Power BI-palvelussa oleviin tietojoukkoihin, päivitetään myös.

Lisätietoja ajoitetun päivityksen määrityksestä on kohdassa [Ajoitetun päivityksen määrittäminen](refresh-scheduled-refresh.md).

## <a name="when-things-go-wrong"></a>Jos ilmenee ongelmia
Ongelmat johtuvat yleensä siitä, että Power BI ei voi kirjautua sisään tietolähteisiin tai jos tietojoukko muodostaa yhteyden paikalliseen tietolähteeseen, mutta yhdyskäytävä on offline-tilassa. Varmista, että Power BI voi kirjautua sisään tietolähteisiin. Jos tietolähteeseen kirjautumisen salasana muuttuu tai jos Power BI kirjataan ulos tietolähteestä, yritä kirjautua uudelleen sisään tietolähteisiin Tietolähteen tunnistetiedot -kohdassa.

Varmista, että jätät kohtaan **Lähetä päivitysvirheen ilmoitusviesti sähköpostiini** valintamerkin. Haluat tietää heti, jos ajoitettu päivitys epäonnistuu.

## <a name="troubleshooting"></a>Vianmääritys
Joskus tietojen päivittäminen ei mene odotetulla tavalla. Yleensä tämä on yhdyskäytävään liittyvä ongelma. Tutustu yhdyskäytävän vianmääritystä koskeviin artikkeleihin, joissa on esitetty työkaluja ja tunnettuja ongelmia.

[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)

[Power BI -yhdyskäytävän vianmääritys – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

