---
title: SSL-varmenteen luominen Power BI -visualisoinneille
description: Lue, miten voit luoda SSL-varmenteita käyttämällä Power BI -visualisointityökaluja Windowsissa, Macissa tai Linuxissa tai manuaalisesti.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 05/08/2020
ms.openlocfilehash: 37bd8f15dcf17cd0f967e819338a719edf2a3054
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83276371"
---
# <a name="create-an-ssl-certificate"></a>SSL-varmenteen luominen

Tässä artikkelissa kerrotaan, miten voit luoda ja asentaa Secure Sockets Layer (SSL) -varmenteita Power BI -visualisointeihin.

Windows-, macOS X- ja Linux-toimintosarjoissa sinulla on oltava Power BI Visual Tools **pbiviz** -paketti asennettuna. Lisätietoja on kohdassa [Kehittäjä ympäristön määrittäminen](https://docs.microsoft.com/power-bi/developer/visuals/custom-visual-develop-tutorial#setting-up-the-developer-environment). 

## <a name="create-a-certificate-on-windows"></a>Varmenteen luominen Windowsissa

Jos haluat luoda varmenteen käyttämällä PowerShellin cmdlet-komentoa `New-SelfSignedCertificate` Windows 8:ssa tai uudemmassa versiossa, suorita seuraava komento:

```powershell
pbiviz --install-cert
```

Windows 7:ssä `pbiviz` työkalu edellyttää OpenSSL-apuohjelman olevan käytettävissä komentorivillä. Kun haluat asentaa OpenSSL-apuohjelman, avaa [OpenSSL](https://www.openssl.org) tai [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries).

Lisätietoja ja ohjeita varmenteen asentamiseen on ohjeaiheessa [Windows-varmenteen luominen ja asentaminen](https://docs.microsoft.com/power-bi/developer/visuals/custom-visual-develop-tutorial#windows).

## <a name="create-a-certificate-on-macos-x"></a>Varmenteen luominen macOS X:ssa

OpenSSL-apuohjelma on yleensä saatavilla Linux- tai Mac OS X -käyttöjärjestelmässä.

Voit asentaa OpenSSL-apuohjelman myös suorittamalla jommankumman seuraavista komennoista:

- *Brew*-paketinhallinnasta:
  
  ```cmd
  brew install openssl
  brew link openssl --force
  ```

- *MacPortsin* avulla:
  
  ```cmd
  sudo port install openssl
  ```

Kun olet asentanut OpenSSL-apuohjelman, suorita seuraava komento uuden varmenteen luomiseksi:

```cmd
pbiviz --install-cert
```

Lisätietoja ja ohjeita on ohjeaiheessa [OS X -varmenteen luominen ja asentaminen](https://docs.microsoft.com/power-bi/developer/visuals/custom-visual-develop-tutorial#osx).

## <a name="create-a-certificate-on-linux"></a>Varmenteen luominen Linuxissa

OpenSSL-apuohjelma on yleensä saatavilla Linux-käyttöjärjestelmässä.

Ennen kuin aloitat, suorita seuraavat komennot varmistaaksesi, että `openssl` ja `certutil` on asennettu:

```sh
which openssl
which certutil
```

Jos `openssl` ja `certutil` eivät ole asennettuina, asenna `openssl`- ja `libnss3`-apuohjelmat.

### <a name="create-the-ssl-configuration-file"></a>SSL-määritystiedoston luominen

Luo tiedosto nimeltä */tmp/openssl.cnf*, joka sisältää seuraavan tekstin:

```
authorityKeyIdentifier=keyid,issuer
basicConstraints=CA:FALSE
keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
subjectAltName = @alt_names

[ alt_names ]
DNS.1=localhost
```

### <a name="generate-root-certificate-authority"></a>Päävarmenteen myöntäjän luominen

Jos haluat luoda päävarmenteiden myöntäjän (CA), jotta voit allekirjoittaa paikallisia varmenteita, suorita seuraavat komennot:

```sh
touch $HOME/.rnd
openssl req -x509 -nodes -new -sha256 -days 1024 -newkey rsa:2048 -keyout /tmp/local-root-ca.key -out /tmp/local-root-ca.pem -subj "/C=US/CN=Local Root CA/O=Local Root CA"
openssl x509 -outform pem -in /tmp/local-root-ca.pem -out /tmp/local-root-ca.crt
```

### <a name="generate-a-certificate-for-localhost"></a>Localhost-varmenteen luominen 

Jos haluat luoda varmenteen `localhost` käyttämällä luotua varmenteiden myöntäjää ja *openssl. cnf*, suorita seuraavat komennot:

```sh
PBIVIZ=`which pbiviz`
PBIVIZ=`dirname $PBIVIZ`
PBIVIZ="$PBIVIZ/../lib/node_modules/powerbi-visuals-tools/certs"
# Make sure that $PBIVIZ contains the correct certificate directory path. ls $PBIVIZ should list 'blank' file.
openssl req -new -nodes -newkey rsa:2048 -keyout $PBIVIZ/PowerBIVisualTest_private.key -out $PBIVIZ/PowerBIVisualTest.csr -subj "/C=US/O=PowerBI Visuals/CN=localhost"
openssl x509 -req -sha256 -days 1024 -in $PBIVIZ/PowerBIVisualTest.csr -CA /tmp/local-root-ca.pem -CAkey /tmp/local-root-ca.key -CAcreateserial -extfile /tmp/openssl.cnf -out $PBIVIZ/PowerBIVisualTest_public.crt
```

### <a name="add-root-certificates"></a>Päävarmenteiden lisääminen

Jos haluat lisätä päävarmenteen Chrome-selaimen tietokantaan, suorita:

```sh
certutil -A -n "Local Root CA" -t "CT,C,C" -i /tmp/local-root-ca.pem -d sql:$HOME/.pki/nssdb
```

Jos haluat lisätä päävarmenteen Mozilla Firefox-selaimen tietokantaan, suorita:

```sh
for certDB in $(find $HOME/.mozilla* -name "cert*.db")
do
certDir=$(dirname ${certDB});
certutil -A -n "Local Root CA" -t "CT,C,C" -i /tmp/local-root-ca.pem -d sql:${certDir}
done
```

Jos haluat lisätä koko järjestelmää koskevan päävarmenteen, suorita:

```sh
sudo cp /tmp/local-root-ca.pem /usr/local/share/ca-certificates/
sudo update-ca-certificates
```

### <a name="remove-root-certificates"></a>Päävarmenteiden poistaminen

Jos haluat poistaa päävarmenteen, suorita:

```sh
sudo rm /usr/local/share/ca-certificates/local-root-ca.pem
sudo update-ca-certificates --fresh
```

## <a name="generate-a-certificate-manually"></a>Varmenteen luominen manuaalisesti

Voit myös luoda SSL-varmenteen manuaalisesti OpenSSL:n avulla. Voit määrittää minkä tahansa työkalun luomat varmenteesi.

Jos OpenSSL-apuohjelma on jo asennettu, luo uusi varmenne suorittamalla:

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBIVisualTest_private.key -out PowerBIVisualTest_public.crt -days 365
```

Löydät `PowerBI-visuals-tools`-verkkopalvelinvarmenteet yleensä suorittamalla jonkin seuraavista:

- Työkalujen yleiselle esiintymälle:
  
  ```cmd
  %appdata%\npm\node_modules\PowerBI-visuals-tools\certs
  ```

- Työkalujen paikalliselle esiintymälle:
  
  ```cmd
  <Power BI visual project root>\node_modules\PowerBI-visuals-tools\certs
  ```

### <a name="pem-format"></a>PEM-muoto

Jos käytät Privacy Enhanced Mail (PEM) -varmennemuotoa, tallenna varmennetiedosto nimellä *PowerBIVisualTest_public.crt* ja tallenna yksityinen avain muodossa *PowerBIVisualTest_private.key*.

### <a name="pfx-format"></a>PFX-muoto

Jos käytät Personal Information Exchange (PFX) -varmennemuotoa, tallenna varmennetiedosto nimellä *PowerBIVisualTest_public.pfx*.

Jos PFX-varmennetiedostosi edellyttää tunnuslausetta:

1. Määritä määritystiedostossa seuraava:
   
   ```cmd
   \PowerBI-visuals-tools\config.json
   ```
   
1. Määritä `server`-osassa tunnuslause korvaamalla \<TUNNUSLAUSEESI> paikkamerkki:

    ```cmd
    "server":{
        "root":"webRoot",
        "assetsRoute":"/assets",
        "privateKey":"certs/PowerBIVisualTest_private.key",
        "certificate":"certs/PowerBIVisualTest_public.crt",
        "pfx":"certs/PowerBIVisualTest_public.pfx",
        "port":"8080",
        "passphrase":"<YOUR PASSPHRASE>"
    }
    ```

## <a name="next-steps"></a>Seuraavat vaiheet
- [Power BI -visualisoinnin kehittäminen](custom-visual-develop-tutorial.md)
- [Power BI -visualisointiesimerkkejä](samples.md)
- [Power BI -visualisointien julkaiseminen AppSourceen](office-store.md)
