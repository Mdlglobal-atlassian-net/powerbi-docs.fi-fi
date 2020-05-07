---
title: SSL-varmenteen luominen
description: Ohjeita, joiden avulla voit luoda varmenteita kehittäjäpalvelimelle manuaalisesti
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: fab40863d7beae4892a56975aa5e92c4fe5486ac
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380268"
---
# <a name="create-an-ssl-certificate"></a>SSL-varmenteen luominen

Tässä artikkelissa kuvataan, miten SSL-varmenne luodaan.

Jos haluat luoda varmenteen käyttämällä PowerShellin cmdlet-komentoa `New-SelfSignedCertificate` Windows 8: ssa tai uudemmassa versiossa, suorita seuraava komento:

```cmd
pbiviz --install-cert
```

Työkalu edellyttää OpenSSL-asennusta Windows 7:lle. OpenSSL-apuohjelman on oltava käytettävissä komentoriviltä.

Kun haluat asentaa OpenSSL-apuohjelman, siirry [OpenSSL](https://www.openssl.org)- tai [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries) -sivustoon.

## <a name="create-a-certificate-mac-os-x"></a>Varmenteen luominen (Mac OS X)

Yleensä OpenSSL-apuohjelma on saatavilla Linux-tai Mac OS X-käyttö järjestelmässä.

Voit asentaa apuohjelman myös suorittamalla jommankumman seuraavista komennoista:

* *Brew*-paketinhallinnasta:

    ```cmd
    brew install openssl
    brew link openssl --force
    ```

* *MacPortsin* avulla:

    ```cmd
    sudo port install openssl
    ```

Kun olet asentanut OpenSSL-apuohjelman uuden varmenteen luomista varten, suorita seuraava komento:

```cmd
pbiviz --install-cert
```

## <a name="create-a-certificate-linux"></a>Varmenteen luominen (Linux)

Jos OpenSSL-apuohjelma ei ole käytettävissä Linux-käyttöjärjestelmässäsi, voit asentaa sen jollakin seuraavista komennoista:

* *APT*-paketinhallinta:

    ```cmd
    sudo apt-get install openssl
    ```

* *Yellowdog Updater*:

    ```cmd
    yum install openssl
    ```

* *Redhat Package Manager*:

    ```cmd
    rpm install openssl
    ```

Jos OpenSSL-apuohjelma on jo käytettävissä käyttöjärjestelmässäsi, luo uusi varmenne suorittamalla seuraava komento:

```cmd
pbiviz --install-cert
```

Voit hankkia OpenSSL-apuohjelman myös siirtymällä [OpenSSL](https://www.openssl.org)- tai [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries) -sivustoon.

## <a name="generate-the-certificate-manually"></a>Varmenteen luominen manuaalisesti

Voit määrittää, että mitkä tahansa työkalut voivat luoda varmenteita.

Jos OpenSSL-apuohjelma on jo asennettu järjestelmääsi, luo uusi varmenne suorittamalla seuraavat komennot:

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

Löydät PowerBI-visuals-tools-verkkopalvelinvarmenteet yleensä suorittamalla jonkin seuraavista:

* Työkalujen yleiselle esiintymälle:

    ```cmd
    %appdata%\npm\node_modules\PowerBI-visuals-tools\certs
    ```

* Työkalujen paikalliselle esiintymälle:

    ```cmd
    <custom visual project root>\node_modules\PowerBI-visuals-tools\certs
    ```

Jos käytät PEM-muotoa, tallenna varmennetiedosto nimellä *PowerBICustomVisualTest_public.crt* ja tallenna yksityinen avain nimellä *PowerBICustomVisualTest_public.key*.

Jos käytät PFX-muotoa, tallenna varmennetiedosto nimellä *PowerBICustomVisualTest_public.pfx*.

Jos PFX-varmennetiedostosi edellyttää tunnuslausetta, toimi seuraavasti:
1. Määritä määritystiedostossa seuraava:

    ```cmd
    \PowerBI-visuals-tools\config.json
    ```

1. Määritä `server`-osassa tunnuslause korvaamalla *TUNNUSLAUSEESI*-paikkamerkki:

    ```cmd
    "server":{
        "root":"webRoot",
        "assetsRoute":"/assets",
        "privateKey":"certs/PowerBICustomVisualTest_private.key",
        "certificate":"certs/PowerBICustomVisualTest_public.crt",
        "pfx":"certs/PowerBICustomVisualTest_public.pfx",
        "port":"8080",
        "passphrase":"YOUR PASSPHRASE"
    }
    ```