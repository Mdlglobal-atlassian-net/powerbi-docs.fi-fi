---
title: SSL-varmenteen luominen
description: Ohjeita, joiden avulla voit luoda varmenteita kehittäjäpalvelimelle manuaalisesti
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 3287e8a7eb1c36c3f0d8a1fc24faa0442de2dddf
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425432"
---
# <a name="creating-ssl-certificate"></a>SSL-varmenteen luominen

Suorita seuraava komento, jos haluat luoda varmenteen käyttämällä powershell New-SelfSignedCertificate cmdlet -komentoa Windows 8: ssa tai uudemmassa versiossa.

Työkalu edellyttää OpenSSL-asennusta **Windows** **7**:lle. Apuohjelman `openssll` on oltava käytettävissä komentoriviltä.

Asenna OpenSSL vierailemalla osoitteessa [https://www.openssl.org](https://www.openssl.org) tai [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries)

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-mac-os-x"></a>Luo varmenne (Mac OS X)

Yleensä OpenSSL-apuohjelmat ovat käytettävissä Linux- tai Mac OS X -käyttöjärjestelmissä.

Muussa tapauksessa voit suorittaa asennuksen

*Brew*-paketinhallinnasta

```cmd
brew install openssl
brew link openssl --force
```

tai käyttämällä *MacPortsia*

```cmd
sudo port install openssl
```

Kun olet asentanut OpenSSL:n, luo uusi varmennekutsu:

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-linux"></a>Luo varmenne (Linux)

OpenSSL-apuohjelmat eivät ole käytettävissä Linux-käyttöjärjestelmässäsi. Voit suorittaa asennuksen seuraavilla komennoilla.

*APT*-paketinhallinta:

```cmd
sudo apt-get install openssl
```

*Yellowdog Updater*:

```cmd
yum install openssl
```

*Redhat Package Manager*:

```cmd
rpm install openssl
```

Jos OpenSSl on jo käytettävissä käyttöjärjestelmässäsi, tee kutsu

```cmd
pbiviz --create-cert
```

luodaksesi uusi varmenne.

Tai hae kohteesta [https://www.openssl.org](https://www.openssl.org)tai [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries)

## <a name="generate-certificate-manually"></a>Luo varmenne manuaalisesti

Voit määrittää minkä tahansa työkalun luomat varmenteet.

Jos järjestelmääsi on asennettu OpenSSL, voit luoda uuden varmenteen suorittamalla seuraavan komennon

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

Yleensä PowerBI:n visualisointityökalujen verkkopalvelinvarmenteet sijaitsevat osoitteessa

```cmd
%appdata%\npm\node_modules\PowerBI-visuals-tools\certs
```

työkalujen yleiselle esiintymälle

tai

```cmd
<custom visual project root>\node_modules\PowerBI-visuals-tools\certs
```

työkalujen paikalliselle esiintymälle.

Sinun tulee tallentaa varmennetiedosto muodossa `PowerBICustomVisualTest_public.cer` ja yksityinen avain muodossa `PowerBICustomVisualTest_public.key`, jos käytät PEM-muotoa.
Tallenna varmennetiedosto muodossa `PowerBICustomVisualTest_public.pfx`, jos käytät PFX-muotoa.

Jos PFX-varmennetiedostosi edellyttää tunnuslausetta, sinun tulee määrittää se

```cmd
\PowerBI-visuals-tools\config.json
```

palvelinosiossa:

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
