---
title: Tietolähteiden hallinta
description: Opi hallitsemaan tietolähteitä Power BI:ssä.
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: arthii
ms.custom: seodec18
LocalizationGroup: Gateways
ms.openlocfilehash: 2665e33d5f268bf8037634406aca819c23f3513c
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74698183"
---
# <a name="manage-data-sources"></a>Tietolähteiden hallinta

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Power BI tukee monia [paikallisia tietolähteitä](power-bi-data-sources.md), joista jokaisella on omat vaatimuksensa. Yhdyskäytävää voidaan käyttää yksittäisen tietolähteen tai useiden tietolähteiden kanssa. Tässä esimerkissä näytämme, miten voit lisätä SQL Serverin tietolähteeksi. Vaiheet ovat samanlaiset muille tietolähteille.

Useimmat tietolähteiden hallintatoiminnot voidaan suorittaa myös ohjelmointirajapintojen avulla. Lisätietoja on kohdassa [REST-ohjelmointirajapinnat (yhdyskäytävät)](/rest/api/power-bi/gateways).

## <a name="add-a-data-source"></a>Tietolähteen lisääminen

1. Valitse ![Asetukset-rataskuvake](media/service-gateway-data-sources/icon-gear.png) >  Power BI -palvelun oikeasta yläkulmasta ja valitse sitten **Hallitse yhdyskäytäviä**.

    ![Hallitse yhdyskäytäviä](media/service-gateway-data-sources/manage-gateways.png)

2. Valitse yhdyskäytävä ja valitse sitten **Lisää tietolähde**. Tai valitse **Yhdyskäytävät** > **Lisää tietolähde**.

    ![Lisää tietolähde](media/service-gateway-data-sources/add-data-source.png)

3. Valitse **tietolähteen tyyppi**.

    ![Valitse SQL Server](media/service-gateway-data-sources/select-sql-server.png)

4. Anna tietolähteen tiedot. Tässä esimerkissä annetut tiedot ovat **Palvelin**, **Tietokanta** ja muuta. 

    ![Tietolähdeasetukset](media/service-gateway-data-sources/data-source-settings.png)

5. SQL Serverin tapauksessa valitaan **Todennusmenetelmäksi** **Windows** tai **Perus** (SQL-todennus). Jos valitset **Perus**, anna tietolähteen tunnistetiedot.

6. **Lisäasetukset**-kohdassa voit halutessasi määrittää tietolähteen [yksityisyystason](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540) (ei koske [DirectQuerya](desktop-directquery-about.md)).

    ![Lisäasetukset](media/service-gateway-data-sources/advanced-settings.png)

7. Valitse **Lisää**. *Yhteyden muodostaminen onnistui* -teksti tulee näkyviin, jos yhteys muodostettiin.

    ![Yhteyden muodostaminen onnistui](media/service-gateway-data-sources/connection-successful.png)

Nyt voit sisällyttää SQL Server -tietoja Power BI -raporttinäkymiin ja -raportteihin tämän tietolähteen avulla.

## <a name="remove-a-data-source"></a>Tietolähteen poistaminen

Voit poistaa tietolähteen, jos et käytä sitä enää. Tietolähteen poistaminen rikkoo kyseisestä tietolähteestä riippuvaiset raporttinäkymät tai raportit.

Jos haluat poistaa tietolähteen, valitse tietolähde ja valitse sitten **Poista**.

![Tietolähteen poistaminen](media/service-gateway-data-sources/remove-data-source.png)

## <a name="use-the-data-source-for-scheduled-refresh-or-directquery"></a>Tietolähteen käyttö ajoitetussa päivityksessä tai DirectQueryssa

Kun tietolähde on luotu, se on käyttäjien saatavilla joko DirectQuery-yhteyksien tai ajoitetun päivityksen välityksellä.

> [!NOTE]
>Palvelimen ja tietokannan nimien pitää täsmätä paikallisen tietoyhdyskäytävän Power BI Desktopin ja tietolähteen kanssa.

Yhdyskäytävän tietojoukon ja tietolähteen välinen linkki perustuu palvelimen ja tietokannan nimiin. Näiden nimien on vastattava toisiaan. Jos esimerkiksi Power BI Desktopissa palvelimen nimelle annetaan IP-osoite, IP-osoitetta tulee käyttää myös tietolähteelle yhdyskäytävän määrityksessä. Jos käytät Power BI Desktopissa nimeä *PALVELIN\ESIINTYMÄ*, yhdyskäytävälle määritetyn tietolähteen sisällä on käytettävä samaa nimeä.

Jos sinut on lisätty yhdyskäytävän sisällä määritellyn tietolähteen **Käyttäjät**-välilehdelle ja jos palvelimen ja tietokannan nimet täsmäävät, näet yhdyskäytävän yhtenä, ajoitetun päivityksen kanssa käytettävänä vaihtoehtona.

![Yhdyskäytäväyhteys](media/service-gateway-data-sources/gateway-connection.png)

> [!WARNING]
> Jos tietojoukkosi sisältää useita tietolähteitä, jokaisen tietolähteen on oltava lisättynä yhdyskäytävään. Jos yksi tai useampi tietolähde ei ole lisättynä yhdyskäytävään, yhdyskäytävää ei näytetä ajoitetun päivityksen yhteydessä.

### <a name="limitations"></a>Rajoitukset

OAuth-todentamista tuetaan paikallisessa tietoyhdyskäytävässä vain mukautetuilla liittimillä. Muita OAuth-todentamista vaativia tietolähteitä ei voi lisätä. Jos tietojoukon tietolähde edellyttää OAuth-todentamista ja tämä tietolähde ei ole mukautettu liitin, yhdyskäytävää ei voi käyttää ajoitetussa päivityksessä.

## <a name="manage-users"></a>Käyttäjien hallinta

Kun olet lisännyt tietolähteen yhdyskäytävään, anna käyttäjille ja sähköpostia käyttäville käyttöoikeusryhmille käyttöoikeudet kyseiseen tietolähteeseen (ei koko yhdyskäytävään). Tietolähteen käyttäjäluettelolla hallitaan vain sitä, ketkä voivat julkaista raportteja, jotka sisältävät tietoja kyseisestä tietolähteestä. Raporttien omistajat voivat luoda raporttinäkymiä, sisältöpaketteja ja sovelluksia ja jakaa niitä muiden käyttäjien kanssa.

Voit myös antaa käyttäjille ja käyttöoikeusryhmille järjestelmänvalvojan oikeudet yhdyskäytävään.

### <a name="add-users-to-a-data-source"></a>Lisää käyttäjiä tietolähteeseen

1. Valitse ![Asetukset-rataskuvake](media/service-gateway-data-sources/icon-gear.png) >  Power BI -palvelun oikeasta yläkulmasta ja valitse sitten **Hallitse yhdyskäytäviä**.

2. Valitse tietolähde, johon haluat lisätä käyttäjiä.

3. Valitse **Käyttäjät** ja kirjoita organisaatiosi käyttäjän nimi, jolle haluat myöntää käyttöoikeudet kyseiseen tietolähteeseen. Esimerkiksi seuraavassa kuvassa lisätään Maggie ja Adam.

    ![Käyttäjät-välilehti](media/service-gateway-data-sources/users-tab.png)

4. Valitse **Lisää**, minkä jälkeen lisätyn jäsenen nimi näkyy ruudussa.

    ![Lisää käyttäjä](media/service-gateway-data-sources/add-user.png)

Muista, että sinun on lisättävä käyttäjiä jokaiseen tietolähteeseen, johon haluat myöntää käyttöoikeuden. Kullakin tietolähteellä on erillinen käyttäjien luettelo. Lisää käyttäjiä kuhunkin tietolähteeseen erikseen.

### <a name="remove-users-from-a-data-source"></a>Poista käyttäjiä tietolähteestä

Tietolähteen **Käyttäjät**-välilehdeltä voit poistaa käyttäjiä tai käyttöoikeusryhmiä, jotka voivat käyttää tätä tietolähdettä.

![Poista käyttäjä](media/service-gateway-data-sources/remove-user.png)

## <a name="store-encrypted-credentials-in-the-cloud"></a>Salattujen tunnistetietojen tallentaminen pilvipalveluun

Kun lisäät tietolähteen yhdyskäytävään, sinun on annettava tunnistetiedot kyseiselle tietolähteelle. Kaikki tietolähteeseen kohdennetut kyselyt suoritetaan näitä tunnistetietoja käyttämällä. Tunnistetiedot salataan turvallisesti. Tämä tehdään epäsymmetrisellä salauksella siten, että niiden salausta ei voi purkaa pilvipalvelussa ennen kuin ne on tallennettu pilvipalveluun. Tunnistetiedot lähetetään tietokoneelle, jossa yhdyskäytävä on käynnissä paikallisesti ja jossa tietojen salaus puretaan käytettäessä tietolähteitä.

## <a name="list-of-available-data-source-types"></a>Luettelo käytettävissä olevista tietolähdetyypeistä

Saat lisätietoja paikallisen tietoyhdyskäytävän tukemista tietolähteistä [Power BI:n tietolähteiden artikkelista](power-bi-data-sources.md).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md)
* [Tietolähteen hallinta – SAP HANA](service-gateway-enterprise-manage-sap.md)
* [Tietolähteen hallinta – SQL Server](service-gateway-enterprise-manage-sql.md)
* [Tietolähteen hallinta – Oracle](service-gateway-onprem-manage-oracle.md)
* [Tietolähteen hallinta – tuonti ja ajoitettu päivitys](service-gateway-enterprise-manage-scheduled-refresh.md)
* [Tietoyhdyskäytävän käyttöönotto-ohjeet](service-gateway-deployment-guidance.md)

Onko sinulla kysyttävää? Kokeile [Power BI -yhteisöä](https://community.powerbi.com/).
