---
title: SSL-varmenteen luominen
description: Ohjeita, joiden avulla voit luoda varmenteita kehittäjäpalvelimelle manuaalisesti
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: d24135cc55ebc8cdfd2a1279cb2a2a46f8f0bc3e
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880194"
---
# <a name="create-an-ssl-certificate"></a>SSL-varmenteen luominen

Tässä artikkelissa kuvataan, miten SSL-varmenne luodaan.

Jos haluat luoda varmenteen käyttämällä PowerShellin cmdlet-komentoa `New-SelfSignedCertificate` Windows 8: ssa tai uudemmassa versiossa, suorita seuraava komento:

```cmd
pbiviz --create-cert
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
pbiviz --create-cert
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
pbiviz --create-cert
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
