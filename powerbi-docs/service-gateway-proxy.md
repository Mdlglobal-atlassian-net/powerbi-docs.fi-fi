---
title: Paikallisen tietoyhdyskäytävän välityspalvelinasetusten määrittäminen
description: Tietoja välityspalvelimen asetusten määrittämisestä paikallista tietoyhdyskäytävää varten
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 11/21/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 2122ce9bd6eb850a51a06188ca1c10faf78f4bb1
ms.sourcegitcommit: ac63b08a4085de35e1968fa90f2f49ea001b50c5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/18/2019
ms.locfileid: "57964659"
---
# <a name="configuring-proxy-settings-for-the-on-premises-data-gateway"></a>Paikallisen tietoyhdyskäytävän välityspalvelinasetusten määrittäminen
Työympäristö saattaa edellyttää, että käytät Internetiä välityspalvelimen kautta. Se voi estää paikalliselta tietoyhdyskäytävältä yhteyden palveluun.

## <a name="does-your-network-use-a-proxy"></a>Käytetäänkö verkossasi välityspalvelinta?
Seuraava kirjoitus Superuser.comissa käsittelee sitä, miten voit määrittää, onko välityspalvelin käytössä verkossasi.

[Mistä tiedän, mikä välityspalvelin on käytössä? (SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## <a name="configuration-file-location-and-default-configuration"></a>Määritystiedoston sijainti ja oletusmääritys
Välityspalvelimen tiedot määritetään .NET-määritystiedostossa. Sijainti ja tiedostonimet riippuvat käytetystä yhdyskäytävästä.

### <a name="on-premises-data-gateway"></a>Paikallinen tietoyhdyskäytävä
Paikalliseen tietoyhdyskäytävään liittyy kaksi tärkeää määritystiedostoa.

**Määrittäminen**

Ensimmäinen on tarkoitettu määritysnäytöille, joilla yhdyskäytävä määritetään. Jos sinulla on ongelmia yhdyskäytävän määrittämisessä, perehdy tähän tiedostoon.

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Windows-palvelu**

Toinen on tarkoitettu Windows-palvelulle, joka on vuorovaikutuksessa Power BI -palvelun kanssa, ja joka käsittelee pyynnöt.

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

## <a name="configuring-proxy-settings"></a>Välityspalvelinasetusten määrittäminen
Välityspalvelimen oletusmääritys on seuraava.

```
<system.net>
    <defaultProxy useDefaultCredentials="true" />
</system.net>
```


Oletusmääritys toimii Windows-todennuksen kanssa. Jos välityspalvelin käyttää toista todennusmuotoa, asetuksia on muutettava. Jos et ole varma, ota yhteyttä verkonvalvojaasi. Välityspalvelimen perustodentamista ei suositella, sillä sen käyttö saattaa aiheuttaa välityspalvelimen todennusvirheitä, jotka johtavat siihen, ettei yhdyskäytävää ole määritetty oikein. Käytä välityspalvelimessa vahvempaa todentamista ratkaistaksesi ongelman.

Oletustunnistetietojen käyttämisen lisäksi voit lisätä <proxy> elementin määrittämään välityspalvelimen asetuksia tarkemmin. Voit esimerkiksi määrittää, että paikallisen tietoyhdyskäytävän tulee aina käyttää välityspalvelinta, myös paikallisia resursseja käytettäessä, määrittämällä bypassonlocal-parametrin arvoksi epätosi. Tämä auttaa vianmääritystilanteissa, jos haluat seurata kaikkia välityspalvelimen lokitiedostojen https-pyyntöjä, jotka ovat peräisin paikallisesta tietoyhdyskäytävästä. Seuraavat malliasetukset määrittävät, että kaikki pyynnöt tulee siirtää tietylle välityspalvelimelle, jonka IP-osoite on 192.168.1.10.

```
<system.net>
    <defaultProxy useDefaultCredentials="true">
        <proxy  
            autoDetect="false"  
            proxyaddress="http://192.168.1.10:3128"  
            bypassonlocal="false"  
            usesystemdefault="true"
        />  
    </defaultProxy>
</system.net>
```

Päivitä lisäksi seuraava tiedosto, jotta yhdyskäytävä voi muodostaa yhteyden pilvipalvelutietolähteisiin välityspalvelimen kautta: *C:\Program Files\On-premises data gateway\Microsoft.Mashup.Container.NetFX45.exe*. Laajenna tiedoston `<configurations>`-osiota niin, että se sisältää alla olevan sisällön, ja päivitä `proxyaddress`-määrite välityspalvelimen tiedoilla. Seuraava esimerkki reitittää kaikki pilvipalvelun pyynnöt tietyn välityspalvelimen kautta, jonka IP-osoite on 192.168.1.10 kautta.

```
<configuration>
<system.net>
    <defaultProxy useDefaultCredentials="true" enabled="true">
    <proxy proxyaddress=""http://192.168.1.10:3128" bypassonlocal="true" />
    </defaultProxy>
</system.net>
</configuration>
```

Lisätietoja välityspalvelinelementtien määrittämisestä .NET-määritystiedostoja varten on artikkelissa [Oletusarvoinen välityspalvelinelementti (Verkkoasetukset)](https://msdn.microsoft.com/library/kd3cf2ex.aspx).

## <a name="changing-the-gateway-service-account-to-a-domain-user"></a>Yhdyskäytävän palvelutilin muuttaminen toimialueen käyttäjäksi
Kun määrität välityspalvelinasetukset käyttämään oletustunnistetietoja, kuten edellä on selitetty, välityspalvelimessa saattaa ilmetä todennusongelmia. Tämä johtuu siitä, että oletuspalvelutili on palvelun SID-tunnus todennetun toimialuekäyttäjän sijaan. Voit muuttaa yhdyskäytävän palvelutiliä, jotta se sallii oikean todennuksen välityspalvelimen kanssa.

> [!NOTE]
> Suosituksena on, että käytät hallittua palvelutiliä, jotta salasanojen vaihtaminen voidaan välttää. Katso ohjeet [hallitun palvelutilin](https://technet.microsoft.com/library/dd548356.aspx) luomiseen Active Directoryssä.
> 
> 

### <a name="change-the-on-premises-data-gateway-service-account"></a>Paikallisen tietoyhdyskäytävän palvelutilin muuttaminen
1. Vaihda **paikallisen tietoyhdyskäytävän** Windows-palvelutili.

    Tämän palvelun oletustili on *NT SERVICE\PBIEgwService*. Sen tilalle kannattaa ehkä vaihtaa Active Directory -toimialueen sisällä oleva toimialueen käyttäjätili. Vaihtoehtoisesti voit käyttää hallittua palvelutiliä, jotta salasanoja ei tarvitse vaihtaa.

    Haluat todennäköisesti vaihtaa **Kirjaudu**-välilehden tilin Windows-palvelun ominaisuuksissa.
2. Käynnistä **Paikallinen tietoyhdyskäytävä -palvelu** uudelleen.

    Syötä seuraavat komennot järjestelmänvalvojan komentoriville.

        net stop PBIEgwService

        net start PBIEgwService
3. Käynnistä **paikallisen tietoyhdyskäytävän määritystoiminto**. Voit valita Windowsin Käynnistä-painikkeen ja tehdä haun *paikallinen tietoyhdyskäytävä*.
4. Kirjaudu sisään Power BI:hin.
5. Palauta yhdyskäytävä palautusavaimen avulla.

    Tämän avulla uusi palvelutili voi purkaa tietolähteiden tallennetut tunnistetiedot.

> [!NOTE]
> Käyttöoikeusluettelo ei päivity automaattisesti kun muutat palvelutiliä suoraan palvelun hallintapaneelista. Varmista, että uudella palvelutilillä on käyttöoikeudet asennustiedostoihin ja -kansioon. Yhdyskäytävän asennuskansio löytyy polusta C:\Ohjelmatiedostot\Paikallinen tietoyhdyskäytävä. 
> 

## <a name="next-steps"></a>Seuraavat vaiheet
[Paikallinen tietoyhdyskäytävä (henkilökohtainen tila)](service-gateway-personal-mode.md)
[Palomuurin tiedot](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

