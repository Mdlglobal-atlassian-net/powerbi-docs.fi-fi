---
title: Omien salausavainten tuominen Power BI:hin
description: Lue, miten voit käyttää omia salausavaimia Power BI Premiumissa.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/20/2020
LocalizationGroup: Premium
ms.openlocfilehash: 133d807d26ba6571eeb614852f3f651a749a369f
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "77527767"
---
# <a name="bring-your-own-encryption-keys-for-power-bi"></a>Omien salausavainten tuominen Power BI:hin

Power BI salaa tiedot _levossa_ ja _käytössä_ olevat tiedot. Oletusarvoisesti Power BI käyttää Microsoftin hallitsemia avaimia tietojen salaamiseen. Power BI Premiumissa voit käyttää omia avaimia tietojoukkoon tuotuihin, levossa oleviin tietoihin (katso lisätiedot artikkelista [Huomioitavaa tietolähteissä ja tallennusvälineissä](#data-source-and-storage-considerations)). Tähän menetelmään viitataan usein termillä _Bring Your Own Key_ (BYOK).

## <a name="why-use-byok"></a>Mitä etuja BYOK tarjoaa?

BYOK:n avulla on helppo noudattaa vaatimuksia, jotka määrittävät avainjärjestelyt pilvipalveluntarjoajan kanssa (tässä tapauksessa Microsoft). BYOK:ta käytettäessä annat Power BI:n levossa olevien tietojen salausavaimet ja hallitset niitä sovellustasolla. Tämän ansiosta voit valvoa organisaatiosi avaimia ja perua ne, jos päätät lopettaa palvelun käytön. Avainten kumoamisen jälkeen palvelu ei voi lukea tietoja 30 minuuttiin.

## <a name="data-source-and-storage-considerations"></a>Huomioitavaa tietolähteissä ja tallennusvälineissä

BYOK:n käyttö edellyttää, että lataat tietoja Power BI -palveluun Power BI Desktop (PBIX) -tiedostosta. Et voi käyttää BYOK:ta seuraavissa tilanteissa:

- Reaaliaikainen Analysis Services -yhteys
- Excel-työkirjat (ellei tietoja tuoda ensin Power BI Desktopiin)
- [Push-tietojoukot](/rest/api/power-bi/pushdatasets)
- [Virtautettavat tietojoukot](service-real-time-streaming.md#set-up-your-real-time-streaming-dataset-in-power-bi)
- [Suuret mallit](service-premium-large-models.md)

BYOK koskee vain tietojoukkoja. Push-tietojoukkoja, Excel-tiedostoja ja CSV-tiedostoja, joita käyttäjät voivat ladata palveluun, ei salata käyttämällä omaa avaintasi. Jos haluat selvittää, mitkä artefakteja tallennetaan työtiloihisi, käytä seuraavaa PowerShell-komentoa:

```PS C:\> Get-PowerBIWorkspace -Scope Organization -Include All```

> [!NOTE]
> Tämä cmdlet-komento edellyttää Power BI -hallintamoduulin versiota 1.0.840. Voit tarkistaa versiosi suorittamalla komennon Get-InstalledModule-Name MicrosoftPowerBIMgmt. Asenna uusin versio suorittamalla komento Install-Module -Name MicrosoftPowerBIMgmt. Saat lisätietoja Power BI:n cmdlet-komennosta ja sen parametreista kohdasta [Power BI:n PowerShell-cmdlet-komentomoduuli](https://docs.microsoft.com/powershell/power-bi/overview).

## <a name="configure-azure-key-vault"></a>Azure Key Vaultin määrittäminen

Tässä osiossa opit määrittämään Azure Key Vaultin, joka on salausavainten ja muiden salaisuuksien tallentamiseen ja käyttöön tarkoitettu työkalu. Voit säilyttää salausavaimia aiemmin luodussa avainholvissa tai voit luoda uuden nimenomaan Power BI -käyttöä varten.

Tämän osion ohjeissa oletetaan, että sinulla on perustiedot Azure Key Vaultin käytöstä. Jos haluat lisätietoja, katso [Mikä on Azure Key Vault?](/azure/key-vault/key-vault-whatis). Avainsäilön määrittäminen:

1. Lisää Power BI -palvelu avainsäilön palvelun päänimeksi ja anna sille paketointi- ja avaamisoikeudet.

1. Luo RSA-avain, jonka bittipituus on 4096 (tai käytä aiempaa tämäntyyppistä avainta) ja jolla on paketointi- ja avaamisoikeudet.

    > [!IMPORTANT]
    > Power BI BYOK tukee vain RSA-avaimia, joiden pituus on 4096 bittiä.

1. Suositus: Tarkista, että avainsäilössä on käytössä _pehmeä poisto_ -asetus.

### <a name="add-the-service-principal"></a>Palvelun päänimen lisääminen

1. Valitse Azure-portaalissa avainsäilön kohdalta **Käyttöoikeuskäytännöt** ja valitse **Lisää uusi**.

1. Hae ja valitse **Valitse palvelun päänimi** -kohdasta Microsoft.Azure.AnalysisServices.

    > [!NOTE]
    > Jos et löydä kohdetta "Microsoft.Azure.AnalysisServices", on todennäköistä, että Azure Key Vaultiin liittyvään Azure-tilaukseen ei ole liitetty Power BI -resurssia. Kokeile hakea sen sijaan seuraavaa merkkijonoa: 00000009-0000-0000-c000-000000000000.

1. Valitse **Avaimen käyttöoikeudet** -kohdasta **Avaa avain** ja **Paketoi avain**.

    ![PBIX-tiedoston osat](media/service-encryption-byok/service-principal.png)

1. Valitse ensin **OK** ja sitten **Tallenna**.

> [!NOTE]
> Jos haluat kumota Power BI -käyttöoikeuden tietoihisi jatkossa, poista tämän palvelun päänimen käyttöoikeudet Azure Key Vaultissa.

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

Jotta voit ottaa BYOK:n käyttöön vuokraajatasolla [PowerShellin](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt.Admin) avulla, sinun on ensin lisättävä Power BI -vuokraajallesi Azure Key Vaultissa luodut ja siihen tallennetut salausavaimet. Voit sen jälkeen määrittää nämä salausavaimet Premium-kapasiteettikohtaisesti kyseisen kapasiteetin sisällön salaamista varten.

### <a name="important-considerations"></a>Huomioitavaa

Huomioi seuraavat asiat ennen kuin otat BYOK:n käyttöön:

- Tällä hetkellä et voi poistaa BYOK:ta käytöstä, kun olet ottanut sen käyttöön. `Add-PowerBIEncryptionKey`-parametrien määrityksistä riippuen voit valita, miten BYOK:ta käytetään yhdessä tai useassa kapasiteetissa. Et voi kuitenkaan perua avainten lisäämistä vuokraajille. Katso lisätietoja artikkelista [BYOK:n käyttöönotto](#enable-byok).

- Et voi _suoraan_ siirtää BYOK:ta käyttävää työtilaa erillisestä Power BI Premium -kapasiteetista jaettuun kapasiteettiin. Sinun on ensin siirrettävä työtila varattuun kapasiteettiin, jossa ei käytetä BYOK:ta.

- Jos siirrät työtilaa, joka käyttää BYOKia varatusta kapasiteetista Power BI Premiumissa jaettuna, raportteja ja tietojoukkoja ei voi käyttää, koska ne salataan avaimella. Tämän välttämiseksi on ensin siirrettävä työtila varattuun kapasiteettiin, jossa ei käytetä BYOK:ia.

### <a name="enable-byok"></a>BYOK:n käyttöönotto

BYOK:n käyttöönotto edellyttää, että olet Power BI -palvelun vuokraajan järjestelmänvalvoja ja että kirjaudut sisään `Connect-PowerBIServiceAccount` cmdlet-komennon kautta. Sen jälkeen voit ottaa BYOK:n käyttöön [`Add-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/Add-PowerBIEncryptionKey):n avulla seuraavassa esimerkissä kuvatulla tavalla:

```powershell
Add-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
```

Jos haluat lisätä useita avaimia, suorita `Add-PowerBIEncryptionKey` eri arvoilla parametreille -`-Name` ja `-KeyVaultKeyUri`. 

Cmdlet-komento hyväksyy kaksi kytkinparametria, jotka vaikuttavat nykyisten ja tulevien kapasiteettien salaukseen. Kumpaakaan kytkintä ei ole oletusarvoisesti määritetty:

- `-Activate`: tämä ilmaisee sitä, että tätä avainta käytetään kaikissa vuokraajan olemassa olevissa kapasiteeteissa, joita ei ole jo salattu.

- `-Default`: Ilmaisee, että tämä avain on nyt koko vuokraajan oletusarvo. Kun luot uuden kapasiteetin, uusi kapasiteetti perii tämän avaimen.

> [!IMPORTANT]
> Jos määrität arvon parametrille `-Default`, kaikki vuokraajallesi jatkossa luodut kapasiteetit salataan määrittämäsi avaimen (tai päivitetyn oletusavaimen) avulla. Et voi perua oletustoimintoa, joten et voi jatkossa luoda Premium-kapasiteettia vuokraajaasi, jossa ei käytetä BYOK:ta.

Kun otat BYOK:n käyttöön vuokraajassasi, määritä yhden tai useamman Power BI -kapasiteetin salausavain:

1. Parametrilla [`Get-PowerBICapacity`](/powershell/module/microsoftpowerbimgmt.capacities/get-powerbicapacity) voit noutaa kapasiteetin tunnuksen, jota tarvitaan seuraavassa vaiheessa.

    ```powershell
    Get-PowerBICapacity -Scope Individual
    ```

    Cmdlet-komento palauttaa seuraavankaltaiset tulokset:

    ```
    Id              : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    DisplayName     : Test Capacity
    Admins          : adam@sometestdomain.com
    Sku             : P1
    State           : Active
    UserAccessRight : Admin
    Region          : North Central US
    ```

1. Parametrilla [`Set-PowerBICapacityEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/set-powerbicapacityencryptionkey) voit asettaa salausavaimen:

    ```powershell
    Set-PowerBICapacityEncryptionKey-CapacityId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -KeyName 'Contoso Sales'
    ```

Voit määrittää, miten BYOK:ta käytetään vuokraajassa. Jos haluat esimerkiksi salata yksittäisen kapasiteetin, kutsu `Add-PowerBIEncryptionKey` ja sulje `-Activate` tai `-Default` kutsun ulkopuolelle. Kutsu sitten `Set-PowerBICapacityEncryptionKey` siinä kapasiteetissa, jossa haluat ottaa BYOK:n käyttöön.

## <a name="manage-byok"></a>BYOK:n hallinta

Power BI sisältää cmdlet-lisäkomentoja, joiden avulla voit hallintaan vuokraajasi BYOK:ta:

- [`Get-PowerBICapacity`](/powershell/module/microsoftpowerbimgmt.capacities/get-powerbicapacity) mahdollistaa kapasiteetissa sillä hetkellä käytössä olevan avaimen noutamisen:

    ```powershell
    Get-PowerBICapacity -Scope Organization -ShowEncryptionKey
    ```

- [`Get-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/get-powerbiencryptionkey) mahdollistaa vuokraajassa sillä hetkellä käytössä olevan avaimen noutamisen:

    ```powershell
    Get-PowerBIEncryptionKey
    ```

- [`Get-PowerBIWorkspaceEncryptionStatus`](/powershell/module/microsoftpowerbimgmt.admin/get-powerbiworkspaceencryptionstatus) näyttää, ovatko työtilan tietojoukot salattuja ja onko niiden salauksen tila synkronoitu työtilan kanssa:

    ```powershell
    Get-PowerBIWorkspaceEncryptionStatus -Name'Contoso Sales'
    ```

    Huomaa, että salaus on käytössä kapasiteettitasolla, mutta saat salauksen tilan määritetyn työtilan tietojoukon tasolla.

- [`Switch-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/switch-powerbiencryptionkey) vaihtaa (tai _kierrättää_) salaukseen käytetyn avainversion. Cmdlet-komento on päivittää avaimen `-KeyVaultKeyUri`-arvon `-Name`:

    ```powershell
    Switch-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
    ```



## <a name="next-steps"></a>Seuraavat vaiheet

* [Power BI:n PowerShell-cmdlet-komentomoduuli](https://docs.microsoft.com/powershell/power-bi/overview) 

* [Töiden jakamistavat Power BI:ssä](service-how-to-collaborate-distribute-dashboards-reports.md)

* [Raportin suodattaminen URL-osoitteen kyselymerkkijonoparametrien avulla](service-url-filters.md)

* [Upota raportin verkko-osa SharePoint Onlinessa](service-embed-report-spo.md)

* [Power BI:n Julkaise verkkoon -toiminto](service-publish-to-web.md)
