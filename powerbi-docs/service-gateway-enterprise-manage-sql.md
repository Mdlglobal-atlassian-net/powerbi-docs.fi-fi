---
title: Tietolähteen hallinta – SQL
description: Paikallisen tietoyhdyskäytävän ja kyseiseen yhdyskäytävään kuuluvien tietolähteiden hallinta.
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 66e9b53761fa154fe76cefea99cb5c88345b97aa
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73881630"
---
# <a name="manage-your-data-source---sql-server"></a>Tietolähteen hallinta – SQL Server

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Kun [paikallinen tietoyhdyskäytävä on asennettu](/data-integration/gateway/service-gateway-install), voit [lisätä tietolähteitä](service-gateway-data-sources.md#add-a-data-source), joita voidaan käyttää kyseisen yhdyskäytävän kanssa. Tässä artikkelissa perehdytään siihen, miten käsitellään yhdyskäytäviä ja SQL Server -tietolähteitä, joita käytetään joko ajoitetussa päivityksessä tai DirectQueryssa.

## <a name="add-a-data-source"></a>Tietolähteen lisääminen

Lisätietoja tietolähteen lisäämisestä on artikkelissa [Tietolähteen lisääminen](service-gateway-data-sources.md#add-a-data-source). Valitse **SQL Server** **tietolähteen tyyppi** -kohdasta.

![Valitse SQL Serverin tietolähde](media/service-gateway-enterprise-manage-sql/datasourcesettings2.png)

> [!NOTE]
> DirectQuery käytettäessä yhdyskäytävä tukee vain versiota **SQL Server 2012 SP1** ja sitä uudempia.

Täytä sitten tietolähteen tiedot, jotka sisältävät **palvelimen** ja **tietokannan**. 

Valitse **Todennusmenetelmä**-kohdassa joko **Windows** tai **Perus**. Valitse vaihtoehto **Perus**, jos aiot käyttää SQL-todennusta Windows-todennuksen sijaan. Anna tunnistetiedot, joita käytetään tälle tietolähteelle.

> [!NOTE]
> Kaikki kyselyt tietolähteelle suoritetaan käyttämällä näitä tunnistetietoja, ellei Kerberos-kertakirjautumista (SSO) ole määritetty ja käytössä tietolähteelle. SSO:n avulla tietojoukkojen tuonnissa käytetään tallennettuja tunnistetietoja, mutta DirectQuery-tietojoukkoja käytetään nykyisen Power BI -käyttäjän kyselyihin SSO:n avulla. Lisätietoja tunnistetietojen tallentamisesta on artikkelissa [Salattu tunnistetietojen tallentaminen pilvipalveluun](service-gateway-data-sources.md#store-encrypted-credentials-in-the-cloud). Tai lue artikkeli, jossa kuvataan [Kerberoksen käyttämisestä kertakirjautumista (SSO) varten Power BI:stä paikallisiin tietolähteisiin](service-gateway-sso-kerberos.md).

![Tietolähdeasetusten täyttäminen](media/service-gateway-enterprise-manage-sql/datasourcesettings3.png)

Kun kaikki kohdat on täytetty, valitse **Lisää.** Voit nyt käyttää tätä tietolähdettä ajoitettuihin päivityksiin tai DirectQueryyn paikallista SQL Serveriä vastaan. *Yhteyden muodostaminen onnistui* -teksti tulee näkyviin, jos yhteys muodostettiin onnistuneesti.

![Yhteyden tilan näyttäminen](media/service-gateway-enterprise-manage-sql/datasourcesettings4.png)

### <a name="advanced-settings"></a>Lisäasetukset

Vaihtoehtoisesti voit määrittää tietolähteellesi yksityisyystason. Tällä asetuksella hallinnoidaan sitä, miten tietoja voidaan yhdistää. Sitä käytetään vain ajoitetussa päivityksessä. Tietosuojatason asetus ei koske DirectQuerya. Lisätietoja tietolähteen yksityisyystasoista on artikkelissa [Yksityisyystasot (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Yksityisyystason määrittäminen](media/service-gateway-enterprise-manage-sql/datasourcesettings9.png)

## <a name="use-the-data-source"></a>Tietolähteen käyttäminen

Kun tietolähde on luotu, se on käyttäjien saatavilla joko DirectQuery-yhteyksien tai ajoitetun päivityksen välityksellä.

> [!NOTE]
> Palvelimen ja tietokannan nimien pitää täsmätä paikallisen tietoyhdyskäytävän Power BI Desktopin ja tietolähteen kanssa.

Yhdyskäytävän tietojoukon ja tietolähteen välinen linkki perustuu palvelimen ja tietokannan nimiin. Näiden nimien on vastattava toisiaan. Jos esimerkiksi Power BI Desktopissa palvelimen nimelle annetaan IP-osoite, samaa IP-osoitetta tulee käyttää myös yhdyskäytävän kokoonpanon tietolähteessä. Jos käytät Power BI Desktopissa nimeä *PALVELIN\ESIINTYMÄ*, sitä on käytettävä yhdyskäytävälle määritetyn tietolähteen sisällä.

Tämä vaatimus koskee sekä DirectQuerya että ajoitettuja päivityksiä.

### <a name="use-the-data-source-with-directquery-connections"></a>Käytä tietolähdettä DirectQueryssa

Palvelimen ja tietokannan nimien on täsmättävä Power BI Desktopissa ja yhdyskäytävälle määritetyssä tietolähteessä. Varmista myös, että käyttäjä on mainittu tietolähteen **Käyttäjät**-välilehdellä, jotta voit julkaista DirectQuery-tietojoukkoja. DirectQuery-valinta tapahtuu Power BI Desktopissa, kun tuot tietoja ensimmäisen kerran. Lisätietoja DirectQueryn käyttämisestä on artikkelissa [DirectQueryn käyttö Power BI Desktopissa](desktop-use-directquery.md).

Raporttisi alkaa toimia, kun olet julkaissut tietojoukot Power BI Desktopissa tai **Nouda tiedot** -ominaisuudella. Yhdyskäytävässä luodun tietolähteen luomisen jälkeen voi kestää useita minuutteja, ennen kuin yhteyttä voidaan käyttää.

### <a name="use-the-data-source-with-scheduled-refresh"></a>Tietolähteen käyttö ajoitetun päivityksen kanssa

Jos sinut on lisätty yhdyskäytävän sisällä määritellyn tietolähteen **Käyttäjät**-välilehdelle ja jos palvelimen ja tietokannan nimet täsmäävät, näet yhdyskäytävän yhtenä, ajoitetun päivityksen kanssa käytettävänä vaihtoehtona.

![Käyttäjien näyttäminen](media/service-gateway-enterprise-manage-sql/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Seuraavat vaiheet

* [Yhteyden muodostaminen paikallisiin tietoihin SQL Serverissä](service-gateway-sql-tutorial.md)
* [Paikallisen tietoyhdyskäytävän vianmääritys](/data-integration/gateway/service-gateway-tshoot)
* [Yhdyskäytävien vianmääritys – Power BI](service-gateway-onprem-tshoot.md)
* [Kerberoksen käyttäminen kertakirjautumista (SSO) varten Power BI:stä paikallisiin tietolähteisiin](service-gateway-sso-kerberos.md)

Onko sinulla kysyttävää? Voit esittää kysymyksiä [Power BI -yhteisössä](https://community.powerbi.com/).

