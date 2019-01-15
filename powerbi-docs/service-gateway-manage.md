---
title: Power BI:n paikallisen yhdyskäytävän hallinta
description: Lue, miten voit hallita yhdyskäytävää niin, että voit muodostaa yhteyden paikallisiin tietoihin Power BI:ssä.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 04/18/2018
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Gateways
ms.openlocfilehash: ff9f75b216ba64dfdb0b8244bb99016d0edd4ede
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54276993"
---
# <a name="manage-a-power-bi-on-premises-gateway"></a>Power BI:n paikallisen yhdyskäytävän hallinta

Kun olet [asentanut Power BI -tietoyhdyskäytävän](service-gateway-install.md), voit hallita sitä tarpeidesi mukaan. Tässä aiheessa kerrotaan, miten voit lisätä ja poistaa tietolähteitä ja käyttäjiä; käynnistää yhdyskäytävän uudelleen; siirtää, palauttaa, ottaa haltuun ja poistaa yhdyskäytävän. 

Voit hallita yhdyskäytävää Power BI -palvelun **Yhdyskäytävien hallinta** -alueen, paikallisen tietokoneen yhdyskäytäväsovelluksen ja PowerShell-komentosarjojen avulla. Tässä artikkelissa keskitytään Power BI -palveluun. 

Jos olet juuri asentanut yhdyskäytävän, suosittelemme seuraavaksi [lisäämään tietolähteen](#add-a-data-source) ja sitten [lisäämään käyttäjiä](#add-users-to-a-data-source), jotta he voivat käyttää tietolähdettä.


## <a name="manage-data-sources"></a>Tietolähteiden hallinta

Power BI tukee monia paikallisia tietolähteitä, joista jokaisella on omat vaatimuksensa. Yhdyskäytävää voidaan käyttää yksittäisen tai useiden tietolähteiden kanssa. Tässä esimerkissä näytetään, miten voit lisätä SQL Serverin tietolähteeksi. Vaiheita voidaan soveltaa muihinkin tietolähteisiin.


### <a name="add-a-data-source"></a>Tietolähteen lisääminen

1. Valitse ![Asetukset-rataskuvake](media/service-gateway-manage/icon-gear.png) >  Power BI -palvelun oikeasta yläkulmasta ja valitse sitten **Hallitse yhdyskäytäviä**.

    ![Hallitse yhdyskäytäviä](media/service-gateway-manage/manage-gateways.png)

2. Valitse yhdyskäytävä > **tietolähde** tai siirry kohtaan Yhdyskäytävät > **Lisää tietolähde**.

    ![Lisää tietolähde](media/service-gateway-manage/add-data-source.png)

3. Valitse **tietolähteen tyyppi**.

    ![Valitse SQL Server](media/service-gateway-manage/select-sql-server.png)


4. Anna tietolähteen tiedot. Tässä esimerkissä annetut tiedot ovat **Palvelin**, **Tietokanta** ja muuta.  

    ![Tietolähdeasetukset](media/service-gateway-manage/data-source-settings.png)

5. SQL Serverin tapauksessa valitaan **Todennusmenetelmäksi** **Windows** tai **Perus** (SQL-todennus).  Jos valitset **Perus**, anna tietolähteen tunnistetiedot.

6. **Lisäasetukset**-kohdassa voit halutessasi määrittää tietolähteen [yksityisyystason](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540) (ei koske [DirectQuerya](desktop-directquery-about.md)).

    ![Lisäasetukset](media/service-gateway-manage/advanced-settings.png)

7. Valitse **Lisää**. *Yhteyden muodostaminen onnistui* -teksti tulee näkyviin, jos yhteys muodostettiin.

    ![Yhteyden muodostaminen onnistui](media/service-gateway-manage/connection-successful.png)

Nyt voit sisällyttää SQL Server -tietoja Power BI -raporttinäkymiin ja -raportteihin tämän tietolähteen avulla.

### <a name="remove-a-data-source"></a>Tietolähteen poistaminen

Voit poistaa tietolähteen, jos et käytä sitä enää. Huomaa, että tietolähteen poistaminen rikkoo kyseisestä tietolähteestä riippuvaiset raporttinäkymät tai raportit.

Jos haluat poistaa tietolähteen, valitse tietolähde ja sitten **Poista**.

![Tietolähteen poistaminen](media/service-gateway-manage/remove-data-source.png)


## <a name="manage-users-and-administrators"></a>Käyttäjien ja järjestelmänvalvojien hallinta

Kun olet lisännyt tietolähteen yhdyskäytävään, anna käyttäjille ja käyttöoikeusryhmille käyttöoikeudet kyseiseen tietolähteeseen (ei koko yhdyskäytävään). Tietolähteen käyttäjäluettelolla hallitaan vain sitä, ketkä voivat julkaista raportteja, jotka sisältävät tietoja kyseisestä tietolähteestä. Raporttien omistajat voivat luoda raporttinäkymiä, sisältöpaketteja ja sovelluksia ja jakaa niitä muiden käyttäjien kanssa.

Voit myös antaa käyttäjille ja käyttöoikeusryhmille järjestelmänvalvojan oikeudet yhdyskäytävään.


### <a name="add-users-to-a-data-source"></a>Lisää käyttäjiä tietolähteeseen

1. Valitse ![Asetukset-rataskuvake](media/service-gateway-manage/icon-gear.png) >  Power BI -palvelun oikeasta yläkulmasta ja valitse sitten **Hallitse yhdyskäytäviä**.

2. Valitse tietolähde, johon haluat lisätä käyttäjiä.

3. Valitse **Käyttäjät** ja kirjoita organisaatiosi käyttäjän nimi, jolle haluat myöntää käyttöoikeudet kyseiseen tietolähteeseen. Seuraavassa kuvassa näkyy, että olen lisännyt Maggien ja Adamin.

    ![Käyttäjät-välilehti](media/service-gateway-manage/users-tab.png)

4. Valitse **Lisää**, minkä jälkeen lisätty jäsen näkyy ruudussa.

    ![Lisää käyttäjä](media/service-gateway-manage/add-user.png)

Siinä kaikki. Muista, että sinun on lisättävä käyttäjiä jokaiseen tietolähteeseen, johon haluat myöntää käyttöoikeuden. Jokaisessa tietolähteessä on erillinen luettelo käyttäjistä, ja sinun on lisättävä käyttäjiä kuhunkin tietolähteeseen erikseen.


### <a name="remove-users-from-a-data-source"></a>Poista käyttäjiä tietolähteestä

Tietolähteen **Käyttäjät**-välilehdeltä voit poistaa käyttäjiä tai käyttöoikeusryhmiä, jotka voivat käyttää tätä tietolähdettä.

![Poista käyttäjä](media/service-gateway-manage/remove-user.png)


### <a name="add-and-remove-administrators"></a>Lisää ja poista järjestelmänvalvojia

Yhdyskäytävän **Järjestelmänvalvojat**-välilehdeltä voit lisätä ja poistaa käyttäjiä (tai käyttöoikeusryhmiä), jotka voivat hallita yhdyskäytävää.

![Järjestelmänvalvojat-välilehti](media/service-gateway-manage/administrators-tab.png)


## <a name="manage-a-gateway-cluster"></a>Yhdyskäytävän klusterin hallinta

Kun luot kahdesta tai useammasta yhdyskäytävästä koostuvan klusterin, kaikki yhdyskäytävän hallintatoiminnot, kuten tietolähteen lisääminen tai järjestelmänvalvojan oikeuksien myöntäminen yhdyskäytävään, koskevat kaikkia klusterin yhdyskäytäviä. 

Kun järjestelmänvalvojat käyttävät **Hallitse yhdyskäytäviä** -valikkokohdetta, joka sijaitsee **Power BI -palvelun** hammaspyöräkuvakkeen alapuolella, he näkevät rekisteröityjen klustereiden tai yksittäisten yhdyskäytävien luettelon, mutta he eivät näe yksittäisiä yhdyskäytäväesiintymiä, jotka ovat klusterin jäseniä.

Kaikki uudet **Ajoitettu päivitys** -pyynnöt ja DirectQuery-toiminnot reititetään automaattisesti tietyn yhdyskäytäväklusterin ensisijaiseen esiintymään. Jos ensisijainen yhdyskäytäväesiintymä ei ole verkossa, pyyntö reititetään klusterin toiseen yhdyskäytäväesiintymään.


## <a name="share-a-gateway"></a>Jaa yhdyskäytävä

Et voi varsinaisesti *jakaa* yhdyskäytävää, mutta voit lisätä järjestelmänvalvojia yhdyskäytävään ja käyttäjiä yhdyskäytävän tietolähteisiin. 

Kun asennat yhdyskäytävän, olet oletusarvoisesti kyseisen yhdyskäytävän järjestelmänvalvoja. Kuten aiemmin näytettiin, voit lisätä muita käyttäjiä järjestelmänvalvojiksi. Nämä järjestelmänvalvojat voivat lisätä tietolähteitä, määrittää ja poistaa yhdyskäytävän.

Voit myös määrittää käyttäjiä tietolähteisiin, jota luot kuhunkin yhdyskäytävään. Käyttäjät voivat tämän jälkeen käyttää kyseisiä tietolähteitä Power BI -raporttien päivittämiseen. He eivät voi kuitenkaan muuttaa tietolähteitä tai yhdyskäytävän asetuksia.

## <a name="migrate-restore-or-take-over-a-gateway"></a>Yhdyskäytävän siirtäminen, palauttaminen tai ottaminen hallintaan

Suorita yhdyskäytävän asennusohjelma tietokoneella, jolla haluat siirtää tai palauttaa yhdyskäytävän tai ottaa sen haltuusi.

1. Lataa yhdyskäytävä ja asenna se.

2. Rekisteröi yhdyskäytävä, kun olet kirjautunut Power BI -tilillesi. Valitse **Siirrä, palauta tai ota olemassa oleva yhdyskäytävä hallintaan** > **Seuraava**.

    ![Rekisteröi yhdyskäytävä](media/service-gateway-manage/register-gateway.png)

3. Valitse käytettävissä olevista klustereista ja yhdyskäytävistä ja anna valitun yhdyskäytävän palautusavain. Valitse **Määritä**.

    ![Siirtäminen, palauttaminen tai ottaminen hallintaan](media/service-gateway-manage/migrate-restore-takeover.png)


## <a name="restart-a-gateway"></a>Yhdyskäytävän käynnistäminen uudelleen

Yhdyskäytävä toimii Windows-palveluna. Kuten muutkin Windows-palvelut, voit käynnistää ja pysäyttää sen usealla tavalla. Tässä kerrotaan, miten voit tehdä sen komentokehotteesta.

1. Käynnistä komentokehote järjestelmänvalvojan oikeuksilla tietokoneessa, jossa yhdyskäytävä on käynnissä.

2. Pysäytä palvelu kirjoittamalla `net stop PBIEgwService`.

3. Käynnistä palvelu uudelleen kirjoittamalla `net start PBIEgwService`.


## <a name="remove-a-gateway"></a>Yhdyskäytävän poistaminen

Voit poistaa yhdyskäytävän, jos et käytä sitä enää. Huomaa, että yhdyskäytävän poistaminen poistaa myös kaikki sen tietolähteet. Tämä vuorostaan rikkoo kaikki raporttinäkymät ja raportit, jotka ovat riippuvaisia kyseisistä tietolähteistä.

1. Valitse ![Asetukset-rataskuvake](media/service-gateway-manage/icon-gear.png) >  Power BI -palvelun oikeasta yläkulmasta ja valitse sitten **Hallitse yhdyskäytäviä**.

2. Valitse yhdyskäytävä > **Poista**
   
   ![Poista yhdyskäytävä](media/service-gateway-manage/remove-gateway.png)


## <a name="next-steps"></a>Seuraavat vaiheet

[Tietoyhdyskäytävän käyttöönotto-ohjeet](service-gateway-deployment-guidance.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
