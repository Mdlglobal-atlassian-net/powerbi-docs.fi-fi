---
title: Omien salausavainten tuominen Power BI:hin (esikatselu)
description: Lue, miten voit käyttää omia salausavaimia Power BI Premiumissa.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 06/10/2019
LocalizationGroup: Premium
ms.openlocfilehash: 7adcfeec771796aa9fe322512f8ca8584559cea0
ms.sourcegitcommit: c122c1a8c9f502a78ccecd32d2708ab2342409f0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/11/2019
ms.locfileid: "66829384"
---
# <a name="bring-your-own-encryption-keys-for-power-bi-preview"></a>Omien salausavainten tuominen Power BI:hin (esikatselu)

Power BI salaa tiedot _levossa_ ja _käytössä_ olevat tiedot. Oletusarvoisesti Power BI käyttää Microsoftin hallitsemia avaimia tietojen salaamiseen. Power BI Premiumissa voit käyttää omia avaimia tietojoukkoon tuotuihin, levossa oleviin tietoihin (katso lisätiedot artikkelista [Huomioitavaa tietolähteissä ja tallennusvälineissä](#data-source-and-storage-considerations)). Tähän menetelmään viitataan usein termillä _Bring Your Own Key_ (BYOK).

## <a name="why-use-byok"></a>Mitä etuja BYOK tarjoaa?

BYOK:n avulla on helppo noudattaa vaatimuksia, jotka määrittävät avainjärjestelyt pilvipalveluntarjoajan kanssa (tässä tapauksessa Microsoft). BYOK:ta käytettäessä annat Power BI:n levossa olevien tietojen salausavaimet ja hallitset niitä sovellustasolla. Tämän ansiosta voit valvoa organisaatiosi avaimia ja perua ne, jos päätät lopettaa palvelun käytön. Avainten kumoamisen jälkeen palvelu ei voi lukea tietoja.

## <a name="data-source-and-storage-considerations"></a>Huomioitavaa tietolähteissä ja tallennusvälineissä

BYOK:n käyttö edellyttää, että lataat tietoja Power BI -palveluun Power BI Desktop (PBIX) -tiedostosta. Kun muodostat yhteyden tietolähteisiin Power BI Desktopissa, sinun on määritettävä tuonnin tallennuksen tila. Et voi käyttää BYOK:ta seuraavissa tilanteissa:

- DirectQuery
- Reaaliaikainen Analysis Services -yhteys
- Excel-työkirjat (ellei tietoja tuoda ensin Power BI Desktopiin)
- Push-tietojoukot

Seuraavassa osiossa opit määrittämään Azure Key Vaultin, jonne salausavaimet tallennetaan BYOK:ta varten.

## <a name="configure-azure-key-vault"></a>Azure Key Vaultin määrittäminen

Azure Key Vault on työkalu salausavainten ja muiden salaisuuksien tallentamiseen ja käyttöön. Voit säilyttää salausavaimia aiemmin luodussa avainholvissa tai voit luoda uuden nimenomaan Power BI -käyttöä varten.

Tämän osion ohjeissa oletetaan, että sinulla on perustiedot Azure Key Vaultin käytöstä. Jos haluat lisätietoja, katso [Mikä on Azure Key Vault?](/azure/key-vault/key-vault-whatis). Avainsäilön määrittäminen:

1. Lisää Power BI -palvelu avainsäilön palvelun päänimeksi ja anna sille paketointi- ja avaamisoikeudet.

1. Luo RSA-avain, jonka bittipituus on 4096 (tai käytä aiempaa tämäntyyppistä avainta) ja jolla on paketointi- ja avaamisoikeudet.

1. Suositus: Tarkista, että avainsäilössä on käytössä _pehmeä poisto_ -asetus.

### <a name="add-the-service-principal"></a>Palvelun päänimen lisääminen

1. Valitse Azure-portaalissa avainsäilön kohdalta **Käyttöoikeuskäytännöt** ja valitse **Lisää uusi**.

1. Hae ja valitse **Valitse palvelun päänimi** -kohdasta Microsoft.Azure.AnalysisServices.

1. Valitse **Avaimen käyttöoikeudet** -kohdasta **Avaa avain** ja **Paketoi avain**.

    ![PBIX-tiedoston osat](media/service-encryption-byok/service-principal.png)

1. Valitse ensin **OK** ja sitten **Tallenna**.

### <a name="create-an-rsa-key"></a>RSA-avaimen luominen

1. Valitse avainsäilöstä **Avain**-kohdasta **Luo/Tuo**.

1. Valitse RSA:n **Avaimen tyyppi** ja **RSA-avaimen kooksi** 4096.

    ![PBIX-tiedoston osat](media/service-encryption-byok/create-rsa-key.png)

1. Valitse **Luo**.

1. Valitse **Avaimet**-kohdasta luomasi avain.

1. Valitse avaimen **nykyisen version** GUID-tunnus.

1. Tarkista, että sekä **Paketoi avain** että **Avaa avain** on valittu. Kopio **Avaimen tunniste**, jota käytetään, kun BYOK on käytössä Power BI:ssä.

    ![PBIX-tiedoston osat](media/service-encryption-byok/key-properties.png)

### <a name="soft-delete-option"></a>Pehmeä poisto -asetus

Suosittelemme, että otat [Pehmeä poisto](/azure/key-vault/key-vault-ovw-soft-delete) -asetuksen käyttöön avainsäilössä. Tämä suojaa tietojen tahattomalta menetykseltä, jos avaimia tai avainsäilö poistetaan vahingossa. Sinun on käytettävä [PowerShellia ottaaksesi pehmeä poisto -asetuksen käyttöön](/azure/key-vault/key-vault-soft-delete-powershell) avainsäilössä, koska tämä asetus ei ole vielä käytettävissä Azure-portaalissa.

Kun Azure Key Vault on määritetty oikein, voit alkaa käyttää BYOK:ta vuokraajassasi.

## <a name="enable-byok-on-your-tenant"></a>BYOK:n käyttöönotto vuokraajassa

Jotta voit ottaa BYOK:n käyttöön vuokraajatasolla PowerShellin avulla, sinun on ensin lisättävä Power BI -vuokraajallesi Azure Key Vaultissa luodut ja siihen tallennetut salausavaimet. Voit sen jälkeen määrittää nämä salausavaimet Premium-kapasiteettikohtaisesti kyseisen kapasiteetin sisällön salaamista varten.

### <a name="important-considerations"></a>Huomioitavaa

Huomioi seuraavat asiat ennen kuin otat BYOK:n käyttöön:

- Tällä hetkellä et voi poistaa BYOK:ta käytöstä, kun olet ottanut sen käyttöön. `Add-PowerBIEncryptionKey`-parametrien määrityksistä riippuen voit valita, miten BYOK:ta käytetään yhdessä tai useassa kapasiteetissa. Et voi kuitenkaan perua avainten lisäämistä vuokraajille. Katso lisätietoja artikkelista [BYOK:n käyttöönotto](#enable-byok).

- Et voi _suoraan_ siirtää BYOK:ta käyttävää työtilaa erillisestä Power BI Premium -kapasiteetista jaettuun kapasiteettiin. Sinun on ensin siirrettävä työtila varattuun kapasiteettiin, jossa ei käytetä BYOK:ta.

### <a name="enable-byok"></a>BYOK:n käyttöönotto

BYOK:n käyttöönotto edellyttää, että olet Power BI -palvelun vuokraajan järjestelmänvalvoja ja että kirjaudut sisään `Connect-PowerBIServiceAccount` cmdlet-komennon kautta. Sen jälkeen voit ottaa BYOK:n käyttöön `Add-PowerBIEncryptionKey`:n avulla seuraavassa esimerkissä kuvatulla tavalla:

```powershell
Add-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
```

Cmdlet-komento hyväksyy kolme kytkinparametria, jotka vaikuttavat nykyisten ja tulevien kapasiteettien salaukseen. Kaikki kytkimet ovat oletuksena pois käytöstä:

- `-Activate`: Ilmaisee, että tätä avainta käytetään kaikissa vuokraajan olemassa olevissa kapasiteeteissa.

- `-Default`: Ilmaisee, että tämä avain on nyt koko vuokraajan oletusarvo. Kun luot uuden kapasiteetin, uusi kapasiteetti perii tämän avaimen.

- `-DefaultAndActivate`: Ilmaisee, että tätä avainta käytetään kaikissa olemassa olevissa sekä uusissa kapasiteeteissa.

Jos määrität `-Default`- tai `-DefaultAndActivate`-arvon, kaikki tälle vuokraajalle jatkossa luodut kapasiteetit salataan määrittämäsi avaimen (tai päivitetyn oletusavaimen) avulla. Et voi perua oletustoimintoa, joten et voi jatkossa luoda vuokraajaasi premium-kapasiteettia, jossa ei käytetä BYO:ta.

Voit määrittää, miten BYOK:ta käytetään vuokraajassa. Jos haluat esimerkiksi salata yksittäisen kapasiteetin, kutsu `Add-PowerBIEncryptionKey` ja sulje `-Activate`, `-Default` ja `-DefaultAndActivate` kutsun ulkopuolelle. Kutsu sitten `Set-PowerBICapacityEncryptionKey` siinä kapasiteetissa, jossa haluat ottaa BYOK:n käyttöön.

## <a name="manage-byok"></a>BYOK:n hallinta

Power BI sisältää cmdlet-lisäkomentoja, joiden avulla voit hallintaan vuokraajasi BYOK:ta:

- `Get-PowerBIEncryptionKey` mahdollistaa vuokraajassa sillä hetkellä käytössä olevan avaimen noutamisen:

    ```powershell
    Get-PowerBIEncryptionKey
    ```

- `Get-PowerBIWorkspaceEncryptionStatus` näyttää, ovatko työtilan tietojoukot salattuja ja onko niiden salauksen tila synkronoitu työtilan kanssa:

    ```powershell
    Get-PowerBIWorkspaceEncryptionStatus -Name'Contoso Sales'
    ```

    Huomaa, että salaus on käytössä kapasiteettitasolla, mutta saat salauksen tilan määritetyn työtilan tietojoukon tasolla.

- `Set-PowerBICapacityEncryptionKey` päivittää Power BI -kapasiteetin salausavaimen:

    ```powershell
    Set-PowerBICapacityEncryptionKey-CapacityId 08d57fce-9e79-49ac-afac-d61765f97f6f -KeyName 'Contoso Sales'
    ```

- `Use Switch-PowerBIEncryptionKey` vaihtaa (tai _kierrättää_) salaukseen sillä hetkellä käytetyn avaimen. Cmdlet-komento on päivittää avaimen `-KeyVaultKeyUri`-arvon `-Name`:

    ```powershell
    Switch-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
    ```