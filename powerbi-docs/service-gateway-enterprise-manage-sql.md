---
title: Tietolähteen hallinta – SQL
description: Paikallisen yhdyskäytävän ja kyseiseen yhdyskäytävään kuuluvien tietolähteiden hallinta.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 7d9e670d2567181a0dc99c23997ac3bc2d35f3c9
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271574"
---
# <a name="manage-your-data-source---sql-server"></a>Tietolähteen hallinta – SQL Server

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Kun [paikallinen tietoyhdyskäytävä on asennettu](/data-integration/gateway/service-gateway-install), sinun on [lisättävä tietolähteitä](service-gateway-data-sources.md#add-a-data-source), joita voidaan käyttää kyseisen yhdyskäytävän kanssa. Tässä artikkelissa perehdytään siihen, miten käsitellään yhdyskäytäviä ja SQL Server -tietolähteitä, joita käytetään joko ajoitetussa päivityksessä tai DirectQueryssa.

## <a name="add-a-data-source"></a>Tietolähteen lisääminen

Lisätietoja tietolähteen lisäämisestä on artikkelissa [Tietolähteen lisääminen](service-gateway-data-sources.md#add-a-data-source).

![Valitse SQL Serverin tietolähde](media/service-gateway-enterprise-manage-sql/datasourcesettings2.png)

> [!NOTE]
> DirectQuery käytettäessä yhdyskäytävä tukee vain versiota **SQL Server 2012 SP1** ja sitä uudempia.

Täytä sitten tietolähteen tiedot, jotka sisältävät **palvelimen** ja **tietokannan**.  

Sinun on myös valittava **todennusmenetelmä**. Tämä voi olla joko **Windows** tai **Basic**. Haluat ehkä valita vaihtoehdon **Perus**, jos aiot käyttää SQL-todennusta Windows-todennuksen sijaan. Anna tunnistetiedot, joita käytetään tälle tietolähteelle.

> [!NOTE]
> Kaikki kyselyt tietolähteelle suoritetaan käyttämällä näitä tunnistetietoja, ellei Kerberos-kertakirjautumista (SSO) ole määritetty ja käytössä tietolähteelle. SSO:n avulla tietojoukkojen tuonnissa käytetään tallennettuja tunnistetietoja, mutta DirectQuery-tietojoukkoja käytetään nykyisen Power BI -käyttäjän kyselyihin SSO:n avulla. Lisätietoja tunnistetietojen tallentamisesta on artikkelissa [Salattu tunnistetietojen tallentaminen pilvipalveluun](service-gateway-data-sources.md#storing-encrypted-credentials-in-the-cloud) tai artikkelissa, jossa kuvataan, miten [käyttää Kerberos for SSO:a (kertakirjautuminen) Power BI:stä paikalliseen tietolähteiden ympäristöön](service-gateway-sso-kerberos.md).

![Tietolähdeasetusten täyttäminen](media/service-gateway-enterprise-manage-sql/datasourcesettings3.png)

Valitse **Lisää**, kun kaikki kohdat on täytetty. Voit nyt käyttää tätä tietolähdettä ajoitettuihin päivityksiin tai DirectQueryyn paikallista SQL Serveriä vastaan. *Yhteyden muodostaminen onnistui* -teksti tulee näkyviin, jos yhteys muodostettiin onnistuneesti.

![Yhteyden tilan näyttäminen](media/service-gateway-enterprise-manage-sql/datasourcesettings4.png)

### <a name="advanced-settings"></a>Lisäasetukset

Vaihtoehtoisesti voit määrittää tietolähteellesi yksityisyystason. Tällä hallinnoidaan sitä, miten tietoja voidaan yhdistää. Tätä käytetään vain ajoitetussa päivityksessä. Tämä ei koske DirectQuerya. Lisätietoja tietolähteen yksityisyystasoista on artikkelissa [Yksityisyystasot (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Yksityisyystason määrittäminen](media/service-gateway-enterprise-manage-sql/datasourcesettings9.png)

## <a name="using-the-data-source"></a>Tietolähteen käyttö

Kun tietolähde on luotu, se on käyttäjien saatavilla joko DirectQuery-yhteyksien tai ajoitetun päivityksen välityksellä.

> [!NOTE]
> Palvelimen ja tietokannan nimien pitää täsmätä paikallisen tietoyhdyskäytävän Power BI Desktopin ja tietolähteen kanssa.

Yhdyskäytävän tietojoukon ja tietolähteen välinen linkki perustuu palvelimen ja tietokannan nimiin. Näiden on täsmättävä. Jos esimerkiksi **Power BI Desktopissa** palvelimen nimelle annetaan IP-osoite, samaa IP-osoitetta tulee käyttää myös yhdyskäytävän kokoonpanon tietolähteessä. Jos käytät Power BI Desktopissa nimenä *PALVELIN\ESIINTYMÄ*, yhdyskäytävälle määritetyn tietolähteen sisällä on käytettävä samaa nimeä.

Tämä koskee sekä DirectQuerya että ajoitettuja päivityksiä.

### <a name="using-the-data-source-with-directquery-connections"></a>Tietolähteen käyttö DirectQueryssa

Palvelimen ja tietokannan nimen on täsmättävä **Power BI Desktopissa** ja yhdyskäytävälle määritetyssä tietolähteessä. Varmista myös, että käyttäjä on mainittu tietolähteen **Käyttäjät**-välilehdellä, jotta voit julkaista DirectQuery-tietojoukkoja. DirectQuery-valinta tapahtuu Power BI Desktopissa, kun tuot tietoja ensimmäisen kerran. Lisätietoja DirectQueryn käyttämisestä on artikkelissa [DirectQueryn käyttö Power BI Desktopissa](desktop-use-directquery.md).

Raporttisi alkaa toimia, kun olet julkaissut tietojoukot Power BI Desktopissa tai **Nouda tiedot** -ominaisuudella. Yhdyskäytävässä luodun tietolähteen luomisen jälkeen voi kestää useita minuutteja, ennen kuin yhteyttä voidaan käyttää.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Tietolähteen käyttö ajoitetun päivityksen kanssa

Jos sinut on lisätty yhdyskäytävän sisällä määritellyn tietolähteen **Käyttäjät**-välilehdelle ja jos palvelimen ja tietokannan nimet täsmäävät, näet yhdyskäytävän yhtenä, ajoitetun päivityksen kanssa käytettävänä vaihtoehtona.

![Käyttäjien näyttäminen](media/service-gateway-enterprise-manage-sql/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Seuraavat vaiheet

* [Yhteyden muodostaminen paikallisiin tietoihin SQL Serverissä](service-gateway-sql-tutorial.md)
* [Paikallisen tietoyhdyskäytävän vianmääritys](/data-integration/gateway/service-gateway-tshoot)
* [Yhdyskäytävien vianmääritys – Power BI](service-gateway-onprem-tshoot.md)
* [Käytä Kerberosta SSO:ta varten (kertakirjautuminen) Power BI:stä paikallisiin tietolähteisiin](service-gateway-sso-kerberos.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

