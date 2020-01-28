---
title: Power BI Desktopin käynnistysongelmien korjaaminen
description: Power BI Desktopin käynnistysongelmien korjaaminen
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/14/2020
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 67c83f2cc0eb81e90f447961ed178a04e97e050e
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/17/2020
ms.locfileid: "76160899"
---
# <a name="troubleshoot-opening-power-bi-desktop"></a>Power BI Desktopin avaamisen vianmääritys

Power BI Desktopissa on mahdollista, että jos käyttäjällä on asennettuna ja käytössä aiempia versioita *Power BI:n paikallisesta tietoyhdyskäytävästä*, häneltä estetään Power BI Desktopin käynnistäminen, koska Power BI:n paikallisella yhdyskäytävällä on hallinnollisia käytäntöjä, joiden mukaan se rajoittaa nimettyjä putkia paikallisella koneella.

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Paikallisen tietoyhdyskäytävän ja Power BI Desktopin ongelmien ratkaiseminen

Sinulla on kolme keinoa, joilla voit ratkaista paikalliseen tietoyhdyskäytävään liittyvät ongelmat ja mahdollistaa Power BI Desktopin avautumisen:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Ratkaisu 1: Asenna uusin versio Power BI:n paikallisesta tietoyhdyskäytävästä

Power BI:n paikallisen tietoyhdyskäytävän uusin versio ei tee nimettyä putkea koskevia rajoituksia paikalliselle koneelle ja mahdollistaa siten Power BI Desktopin asianmukaisen avautumisen. Jos sinun on jatkettava Power BI:n paikallisen tietoyhdyskäytävän käyttöä, suositeltu ratkaisu on päivittää se. Voit ladata [Power BI:n paikallisen tietoyhdyskäytävän uusimman version](https://go.microsoft.com/fwlink/?LinkId=698863). Tämä on suora latauslinkki suoritettavaan asennustiedostoon.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-microsoft-service"></a>Ratkaisu 2: Poista Power BI:n paikallisen tietoyhdyskäytävän asennus tai pysäytä sen käyttö Microsoft-palvelussa

Voit poistaa Power BI:n paikallisen tietoyhdyskäytävän asennuksen, jos et enää tarvitse sitä. Tai voit pysäyttää Power BI:n paikallisen tietoyhdyskäytävän käytön Microsoft-palvelussa, jolloin käytännön rajoitus poistuu ja Power BI Desktop avautuu jälleen.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Ratkaisu 3: Suorita Power BI Desktop järjestelmänvalvojan oikeuksilla

Voit myös käynnistää Power BI Desktopin järjestelmänvalvojana, mikä mahdollistaa myös Power BI Desktopin onnistuneen avautumisen. On silti yhä suositeltavaa, että asennat uusimman version Power BI:n paikallisesta tietoyhdyskäytävästä, kuten edellä on kuvattu.

Power BI Desktop on suunniteltu moniajoarkkitehtuuriksi ja useat prosessit käyttävät kommunikoidessaan Windowsin nimettyjen putkia. Muut prosessit saattavat häiritä näiden nimettyjen putkien toimintaa. Yleisin syy tällaisille häiriöille on suojaus, kuten tilanteet, joissa virustentorjuntaohjelmisto tai palomuurit voivat estää putkien toimintaa tai niiden liikennettä ohjataan tiettyyn porttiin. Power BI Desktopin avaaminen järjestelmänvalvojan oikeuksilla saattaa ratkaista ongelman. Jos et voi avata sitä järjestelmänvalvojan oikeuksilla, pyydä järjestelmänvalvojaa selvittämään, mitkä suojaussäännöt estävät nimettyjä putkia luomasta asianmukaisia yhteyksiä. Poista sitten Power BI Desktop ja siihen liittyvät aliprosessit kiellettyjen luettelosta.

## <a name="resolve-issues-when-connecting-to-sql-server"></a>Ratkaise ongelmat yhdistettäessä SQL-palvelimeen

Kun yrität muodostaa yhteyden SQL-palvelimen tietokantaan, saatat saada seuraavanlaisen virheilmoituksen:

`"An error happened while reading data from the provider:`\
`'Could not load file or assembly 'System.EnterpriseServices, Version=4.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxx' or one of its dependencies.`\
`Either a required impersonation level was not provided, or the provided impersonation level is invalid. (Exception from HRESULT: 0x80070542)'"`

Voit usein korjata ongelman avaamalla Power BI Desktopin järjestelmänvalvojana, ennen kuin luot SQL-palvelinyhteyden.

Kun olet avannut Power BI Desktopin järjestelmänvalvojana ja muodostanut yhteyden, vaaditut DLL-tiedostot rekisteröityvät oikein. Sen jälkeen ei enää ole välttämätöntä avata Power BI Desktopia järjestelmänvalvojana.

## <a name="get-help-with-other-launch-issues"></a>Hanki apua muihin käynnistysongelmiin

Pyrimme kattamaan mahdollisimman monet Power BI Desktopissa esiintyvät ongelmat. Tutkimme säännöllisesti ongelmia, joita useilla asiakkailla saattaa ilmetä, ja lisäämme artikkeleihin niitä koskevat ohjeet.

Jos Power BI Desktopin avautumisongelmat eivät liity paikalliseen tietoyhdyskäytävään tai jos edellä mainitut ratkaisutavat eivät auta, voit lähettää tukipyynnön *Power BI -tukeen* (<https://support.powerbi.com>) ongelmasi tunnistamiseksi ja ratkaisemiseksi.

Jos sinulla ilmenee vastaisuudessa muita Power BI Desktop -ongelmia, on hyödyllistä ottaa käyttöön jäljitys ja kerätä talteen lokitiedostoja. Lokitiedostot voivat auttaa eristämään ja tunnistamaan ongelman. Kytke jäljitys käyttöön valitsemalla **Tiedosto** > **Vaihtoehdot ja asetukset** > **Vaihtoehdot**, valitse **Diagnostiikka** ja valitse siitä **Ota jäljitys käyttöön**. Tämän asetuksen valitseminen edellyttää Power BI Desktopin käynnissä oloa, mutta siitä on hyötyä tulevissa Power BI Desktopin avaamisongelmissa.
