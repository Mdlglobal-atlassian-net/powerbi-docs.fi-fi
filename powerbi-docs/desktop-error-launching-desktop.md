---
title: Power BI Desktopin käynnistysongelmien ratkaiseminen
description: Power BI Desktopin käynnistysongelmien ratkaiseminen
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: eeaf2c48baddaccbaeb80b788e9f8a5bc3263000
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73878252"
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Ratkaise ongelmat, kun Power BI Desktop ei käynnisty
**Power BI Desktopissa** on mahdollista, että jos käyttäjällä on asennettuna ja käytössä aiempia versioita **Power BI:n paikallisesta tietoyhdyskäytävästä**, häneltä estetään Power BI Desktopin käynnistäminen, koska Power BI:n paikallisella yhdyskäytävällä on hallinnollisia käytäntöjä, joiden mukaan se rajoittaa nimettyjä putkia paikallisella koneella. 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Paikallisen tietoyhdyskäytävän ja Power BI Desktopin ongelmien ratkaiseminen
On kolme keinoa, joilla voit ratkaista paikalliseen tietoyhdyskäytävään liittyvät ongelmat ja mahdollistaa ja Power BI Desktopin käynnistämisen:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Ratkaisu 1: Asenna uusin versio Power BI:n paikallisesta tietoyhdyskäytävästä
Power BI:n paikallisen tietoyhdyskäytävän uusin versio ei tee nimettyä putkea koskevia rajoituksia paikalliselle koneelle ja mahdollistaa siten Power BI Desktopin käynnistämisen. Jos sinun on jatkettava Power BI:n paikallisen tietoyhdyskäytävän käyttöä, tämä on suositeltu ratkaisu. Voit ladata Power BI:n paikallisen tietoyhdyskäytävän uusimman version [täältä](https://go.microsoft.com/fwlink/?LinkId=698863). Huomaa, että tämä on suora latauslinkki suoritettavan asennustiedostoon.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>Ratkaisu 2: Poista Power BI:n paikallisen tietoyhdyskäytävän asennus tai pysäytä sen käyttö Windows-palvelussa
Jos et enää tarvitse Power BI:n paikallista tietoyhdyskäytävää, voit poistaa sen asennuksen tai pysäyttää Power BI:n paikallisen tietoyhdyskäytävän Windows-palvelussa, mikä poistaa rajoittavan käytännön ja mahdollistaa siten Power BI Desktopin käynnistämisen.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Ratkaisu 3: Suorita Power BI Desktop järjestelmänvalvojan oikeuksilla
Voit vaihtoehtoisesti käynnistää Power BI Desktopin järjestelmänvalvojana. On silti suositeltavaa, että asennat uusimman version Power BI:n paikallisesta tietoyhdyskäytävästä tässä artikkelissa aiemmin annettujen ohjeiden mukaisesti.

On tärkeää huomata, että Power BI Desktop on suunniteltu moniajoarkkitehtuuriksi ja useat prosessit käyttävät kommunikoidessaan Windowsin nimettyjen putkia. Muut prosessit saattavat häiritä näiden nimettyjen putkien toimintaa. Yleisin syy tällaisille häiriöille on suojaus, mukaan lukien tilanteet, joissa virustentorjuntaohjelmisto tai palomuurit saattavat estää putkien toimintaa tai niiden liikennettä ohjataan tiettyyn porttiin. Power BI Desktopin käynnistäminen järjestelmänvalvojan oikeuksilla saattaa ratkaista ongelman. Jos käynnistäminen ei onnistu järjestelmänvalvojan oikeuksilla, ota yhteyttä järjestelmänvalvojaan sen määrittämiseksi, mitkä suojaussäännöt estävät nimettyjen putkien asianmukaisen viestinnän, ja lisää Power BI Desktop ja sen vastaavat aliprosessit sallittujen luetteloon.

## <a name="resolve-issues-when-connecting-to-sql-server"></a>Ratkaise ongelmat yhdistettäessä SQL-palvelimeen
Jos kohtaat SQL Server-tietokantaan yhdistettäessä seuraavan kaltaisen virhesanoman, voit usein korjata ongelman käynnistämällä **Power BI Desktopin** järjestelmänvalvojana ja yhdistämällä tämän jälkeen SQL-palvelimeen:

    "An error happened while reading data from the provider: 'Could not load file or assembly 'System.EnterpriseServices, Version=4.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxx' or one of its dependencies. Either a required impersonation level was not provided, or the provided impersonation level is invalid. (Exception from HRESULT: 0x80070542)'"

Järjestelmänvalvojana käynnistämisen ja yhteyden muodostamisen jälkeen, tarvittavat DLL-tiedostot on rekisteröity oikein. Tämän jälkeen Power BI Desktopin käynnistämistä järjestelmänvalvojana ei tarvitse suorittaa.

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Apua muihin Power BI Desktopin käynnistysongelmiin
Pyrimme hoitamaan mahdollisimman monet **Power BI Desktopissa** ilmenevät ongelmat. Tutkimme säännöllisesti ongelmia, joita useilla asiakkailla saattaa ilmetä, ja lisäämme artikkeleihin niitä koskevat ohjeet.

Jos **Power BI Desktopin** käynnistysongelma ei liity paikalliseen tietoyhdyskäytävään tai jos edellä mainitut ratkaisut eivät auta, voit lähettää tukipyynnön [Power BI:n tukeen](https://support.powerbi.com) (https://support.powerbi.com), jotta ongelmasi saataisiin tunnistettua ja ratkaistua.

Sen varalta että **Power BI Desktopissa** ilmenee vastaisuudessa muita ongelmia (toivottavasti ei ilmene tai ainakin vain hyvin vähän), voi olla hyödyllistä ottaa käyttöön seuranta ja kerätä lokitiedostot, jotka helpottavat ongelmien eristämisessä ja tunnistamisessa. Jos haluat ottaa seurannan käyttöön, valitse **Tiedosto > Asetukset ja vaihtoehdot > Asetukset**, valitse sitten **Diagnostiikka** ja valitse kohdasta *Diagnostiikka-asetukset* valintaruutu **Ota jäljitys käyttöön**. Olemme tietoisia siitä, että tämän asetuksen valitseminen edellyttää **Power BI Desktopin** käynnistymistä, joten siitä on hyötyä lähinnä tulevissa **Power BI Desktopin** käynnistysongelmissa.

