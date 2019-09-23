---
title: Tietojen hakeminen Power BI Desktop -tiedostoista
description: Opi noutamaan tietoja ja raportteja Power BI Desktopista Power BI:hin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 5e0ad4ed93fac06ace7c8e0569ebb0c2aeac9a87
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513102"
---
# <a name="get-data-from-power-bi-desktop-files"></a>Tietojen hakeminen Power BI Desktop -tiedostoista
![](media/service-desktop-files/pbid_file_icon.png)

**Power BI Desktop** tekee liiketoimintatiedon hallinnasta ja raportoinnista helppoa. Oletpa sitten olet muodostamassa yhteyttä moniin eri tietolähteisiin, tekemässä kyselyitä ja muokkaamassa tietoja, mallintamassa tietoja tai luomassa tehokkaita ja dynaamisia raportteja, **Power BI Desktopin** avulla liiketoimintatiedon hallintatehtävät sujuvat intuitiivisesti ja nopeasti. Jos et ole aiemmin käyttänyt **Power BI Desktopia**, tutustu [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md) -artikkeliin.

Kun olet tuonut tiedot **Power BI Desktopiin** ja luonut muutamia raportteja, on aika noutaa tallennettu tiedosto **Power BI -palveluun**.

## <a name="where-your-file-is-saved-makes-a-difference"></a>Tiedoston tallennussijainnilla on merkitystä
**Paikallinen** – Jos tallennat tiedoston tietokoneesi paikalliseen asemaan tai toiseen sijaintiin organisaatiossasi, voit *tuoda* tiedoston tai *julkaista* sen Power BI Desktopista siirtääksesi sen tiedot ja raportit Power BI:hin. Todellisuudessa tiedosto säilyy paikallisessa asemassa, joten koko tiedostoa ei ole varsinaisesti siirretty Power BI:hin. Käytännössä Power BI:hin luodaan uusi tietojoukko, johon Power BI Desktop -tiedoston tiedot ja tietomalli ladataan. Jos tiedostossa on raportteja, ne näkyvät Power BI -sivuston Raportit-kohdassa.

**OneDrive – yritys** – Ehdottomasti tehokkain tapa, jolla voit pitää Power Bi Desktop -työsi ja Power BI:n tietojoukon, raportit ja koontinäytöt synkronoituina, on käyttää OneDrive for Businessia ja kirjautua siihen sisään samalla tilillä kuin Power BI:hinkin. Koska sekä Power BI että OneDrive toimivat pilvipalvelussa, Power BI *muodostaa yhteyden* OneDrivessa sijaitsevaan tiedostoon noin tunnin välein. Jos muutoksia löytyy, Power BI:n tietojoukko, raportit ja raporttinäkymät päivitetään automaattisesti.

**OneDrive – henkilökohtainen** – Jos tallennat tiedostot henkilökohtaiseen OneDrive-tiliisi, saat monia samoja etuja kuin käyttäessäsi OneDrive for Businessia. Suurin ero on, että sinun on kirjauduttava sisään OneDriveen käyttämällä Microsoft-tiliäsi, kun muodostat ensimmäisen kerran yhteyden tiedostoon (Nouda tiedot > Tiedostot > OneDrive - henkilökohtainen). Yleensä Microsoft-tili on eri kuin tili, jota käytetään Power BI:hin kirjautumiseen. Kun kirjaudut sisään OneDriveen käyttämällä Microsoft-tiliäsi, muista valita asetus Pidä minut sisäänkirjautuneena. Näin Power BI voi muodostaa yhteyden tiedostoon noin tunnin välein ja varmistaa, että Power BI:n tietojoukko on synkronoitu.

**SharePoint-työryhmäsivustot** – Power BI Desktop -tiedostojen tallentaminen SharePoint-työryhmäsivustoihin tapahtuu lähes samoin kuin tallentaminen OneDrive for Businessiin. Suurin ero on siinä, miten yhteys Power BI:stä tiedostoon muodostetaan. Voit määrittää URL-osoitteen tai muodostaa yhteyden pääkansioon.

## <a name="import-or-connect-to-a-power-bi-desktop-file-from-power-bi"></a>Tiedoston tuominen tai yhteyden muodostaminen Power BI:stä Power BI Desktop -tiedostoon
>[!IMPORTANT]
>Power BI:hin tuotavan tiedoston enimmäiskoko on 1 gigatavu.

1. Valitse Power BI:n siirtymisruudussa ** Nouda tiedot **.
   
   ![](media/service-desktop-files/pbid_get_data_button.png)
2. Valitse **Tiedostot**-kohdassa **Nouda**.
   
   ![](media/service-desktop-files/pbid_files_get.png)
3. Etsi tiedosto. Power BI Desktop -tiedostojen tunniste on .PBIX.
   
   ![](media/service-desktop-files/pbid_find_your_file.png)

## <a name="publish-a-file-from-power-bi-desktop-to-your-power-bi-site"></a>Tiedoston julkaiseminen Power BI Desktopista Power BI -sivustoon
Julkaiseminen Power BI Desktopista toimii käytännössä samoin kuin Power BI:n Nouda tiedot -toiminnon avulla tapahtuva tiedoston tuominen paikallisesta asemasta tai yhteyden muodostaminen siihen OneDrivessa.  Seuraavassa on lyhyt ohje. Tarkempia tietoja on [Power BI Desktopista julkaiseminen](desktop-upload-desktop-files.md) -artikkelissa.

1. Valitse Power BI Desktopissa **Tiedosto** > **Julkaise** > **Julkaise Power BI:hin**, tai napsauta valintanauhan **Julkaise**-painiketta.
   
   ![](media/service-desktop-files/pbid_publish.png)
2. Kirjaudu sisään Power BI:hin. Sinun on tehtävä tämä vain ensimmäisellä kerralla.
   
   Tämän jälkeen näkyviin tulee linkki, joka avaa raportin Power BI -sivustossa.
   
   ![](media/service-desktop-files/pbid_publishing.png)

## <a name="next-steps"></a>Seuraavat vaiheet
**Tutki tietoja** – Kun olet noutanut tiedot ja raportit tiedostosta Power BI:hin, on aika tutkia niitä. Jos tiedostossa on jo raportteja, ne näkyvät siirtymisruudun **Raportit**-kohdassa. Jos tiedostossa on vain tietoja, voit luoda uusia raportteja. Napsauta hiiren kakkospainikkeella uutta tietojoukkoa ja valitse sitten **Tutki**.

**Päivitä ulkoiset tietolähteet** – Jos Power BI Desktop -tiedosto on yhteydessä ulkoisiin tietolähteisiin, voit määrittää ajoitetut päivitykset ja varmistaa näin, että tietojoukkosi on aina ajan tasalla. Useimmiten ajoitetun päivityksen määrittäminen on varsin helppoa, mutta sen tarkat ohjeet eivät kuulu tämän artikkelin piiriin. Lisätietoja asiasta on [Tietojen päivittäminen Power BI:ssä](refresh-data.md) -artikkelissa.

