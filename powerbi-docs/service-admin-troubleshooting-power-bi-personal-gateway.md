---
title: Power BI Gateway - Personal -yhdyskäytävän vianmääritys
description: Power BI Gateway - Personal -yhdyskäytävän vianmääritys
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 58e6dc99198eb4f031dd28b5c80cc8babb03dbfb
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34247260"
---
# <a name="troubleshooting-power-bi-gateway---personal"></a>Power BI Gateway - Personal -yhdyskäytävän vianmääritys
Seuraavassa käydään läpi joitakin yleisiä ongelmia, joita saatat kohdata käyttäessäsi Power BI Gateway - Personal -yhdyskäytävää.

> [!NOTE]
> Henkilökohtaiseen käyttöön tarkoitetun yhdyskäytävän nykyinen versio on **paikallinen tietoyhdyskäytävä (henkilökohtainen)**. Päivitä asennuksesi käyttämään kyseistä versiota.
> 
> 

## <a name="update-to-the-latest-version"></a>Päivitä uusimpaan versioon
Ongelmia voi esiintyä paljon, jos yhdyskäytävän versio on vanhentunut.  Hyvä yleinen käytäntö on varmistaa, että käytät aina uusinta versiota.  Jos et ole päivittänyt yhdyskäytävää ainakaan kuukauteen, sinun kannattaa harkita yhdyskäytävän uusimman version asentamista ja kokeilla ongelman toistamista.

## <a name="installation"></a>Asennus
**Henkilökohtainen yhdyskäytävä on 64-bittinen** – jos tietokoneesi on 32-bittinen, henkilökohtaista yhdyskäytävää ei voi asentaa siihen. Käyttöjärjestelmän on oltava 64-bittinen. Sinun on asennettava Windowsin 64-bittinen versio, tai voit asentaa henkilökohtaisen yhdyskäytävän 64-bittiseen tietokoneeseen.

**Henkilökohtaisen yhdyskäytävän asentaminen palveluna epäonnistuu, vaikka olet tietokoneen paikallinen järjestelmänvalvoja** – Asennus voi epäonnistua, jos käyttäjä kuuluu tietokoneen paikallisten järjestelmänvalvojien ryhmään, mutta ryhmäkäytäntö ei salli kyseisen käyttäjätunnuksen kirjautumista palveluna.  Varmista tässä tilanteessa, että ryhmäkäytäntö sallii käyttäjän kirjautua sisään palveluna. Pyrimme korjaamaan tämän ongelman. [Lue lisää](https://technet.microsoft.com/library/cc739424.aspx)

**Toiminto aikakatkaistiin** – Tämä on yleinen, jos tietokoneessa (fyysinen kone tai näennäiskone), johon olet asentamassa henkilökohtaista yhdyskäytävää, on yksiytiminen suoritin. Sulje kaikki sovellukset, poista tarpeettomat prosessit käytöstä ja yritä asentaa uudelleen.

**Tietoyhdyskäytävää tai Analysis Services Connector -liitintä ei voi asentaa samaan tietokoneeseen henkilökohtaisen yhdyskäytävän kanssa** – Jos sinulla on jo Analysis Services Connector tai tietoyhdyskäytävä asennettuna, poista ensin liittimen tai yhdyskäytävän asennus ja yritä sen jälkeen asentaa henkilökohtainen yhdyskäytävä.

> [!NOTE]
> Jos kohtaat ongelman asennuksen aikana, asennuslokeista voit saada tietoja, jotka auttavat sinua ratkaisemaan ongelman. Katso lisätietoja kohdasta [Asennuslokit](#SetupLogs).
> 
> 

 **Välityspalvelinmääritys** – Henkilökohtaisen yhdyskäytävän määrityksessä voi ilmetä ongelmia, jos ympäristösi tarvitsee välityspalvelimen käyttöä. Lisätietoja välityspalvelimen tietojen määrityksestä saat artikkelista [Power BI -yhdyskäytävien välityspalvelinasetusten määrittäminen](service-gateway-proxy.md).

## <a name="schedule-refresh"></a>Ajoita päivitys
**Virhe: pilveen tallennettu tunnistetieto puuttuu.**

Saatat saada tämän virheilmoituksen \<tietojoukon\> asetuksissa, jos olet ajoittanut päivityksen ja sen jälkeen poistanut henkilökohtaisen yhdyskäytävän asennuksen ja asentanut sen uudelleen. Kun poistat henkilökohtaisen yhdyskäytävän asennuksen, päivitettäväksi määritetyn tietojoukon tietolähteen tunnistetiedot poistetaan Power BI -palvelusta.

**Ratkaisu:** siirry Power BI:ssä tietojoukon päivitysasetuksiin. Valitse Tietolähteiden hallinta -kohdassa kaikkien virheen kohdanneiden tietolähteiden kohdalla Muokkaa tunnistetietoja -vaihtoehto ja kirjaudu sitten tietolähteeseen uudelleen.

**Virhe: tietojoukolle annetut tunnistetiedot ovat virheelliset. Jatka päivittämällä tunnistetiedot päivityksen kautta tai Tietolähdeasetukset-valintaikkunassa.**

**Ratkaisu**: jos näyttöön tulee tunnistetietosanoma, se voi tarkoittaa seuraavia:

* Varmista, että tietolähteisiin kirjautumiseen käytetyt käyttäjänimet ja salasanat ovat ajan tasalla. Siirry Power BI:ssä tietojoukon päivitysasetuksiin. Päivitä tietolähteen tunnistetiedot valitsemalla Tietolähteiden hallinnassa Muokkaa tunnistetietoja -vaihtoehto.
* Koosteet pilvipalvelulähteen ja paikallisen lähteen välillä, yksittäisessä kyselyssä, eivät päivity henkilökohtaisessa yhdyskäytävässä, jos jompikumpi lähteistä käyttää OAuth-todennusta. Esimerkki tästä on kooste CRM Onlinen ja paikallisen SQL Serverin välillä. Tämä epäonnistuu, koska CRM Online edellyttää OAuth-todennusta.
  
  Tämä on tunnettu ongelma, joka on tarkastelun alla. Voit kiertää ongelman käyttämällä erillisiä kyselyitä pilvipalvelulähteelle ja paikalliselle lähteelle ja yhdistämällä ne käyttämällä Yhdistä kysely- tai Liitä kyselyt loppuun -toimintoa.

**Virhe: Ei-tuettu tietolähde.**

**Ratkaisu:** jos saat ei-tuetusta tietolähteestä ilmoittavan virhesanoman Ajoita päivitys -asetuksissa, se voi tarkoittaa seuraavia: 

* Tietolähteen päivitystä ei tällä hetkellä tueta Power BI:ssä. 
* Excel-työkirja ei sisällä tietomallia, vain laskentataulukon tietoja. Power BI tukee tällä hetkellä päivitystä vain, jos ladattu Excel-työkirja sisältää tietomallin. Kun tuot tietoja Power Queryn avulla Excelissä, muista valita Lataa tiedot tietomalliin -vaihtoehto. Tämä varmistaa, että tiedot tuodaan tietomallin. 

**Virhe: [Tietojen yhdistäminen ei onnistu] &lt;kyselyosa&gt;/&lt;…&gt;/&lt;…&gt; {0} käyttää tietolähteitä, joiden yksityisyystasoja ei voi käyttää yhdessä. Muodosta tämä tietoyhdistelmä uudelleen.**

**Ratkaisu**: tämä virhe johtuu tietosuojatason rajoituksista ja käyttämiesi tietolähteiden tyypeistä.

**Virhe: Tietolähdevirhe: arvoa ”\[Table\]” ei voi muuntaa tyypiksi Table.**

**Ratkaisu**: tämä virhe johtuu tietosuojatason rajoituksista ja käyttämiesi tietolähteiden tyypeistä.

**Virhe: tälle riville ei ole tarpeeksi tilaa.**

Tämä virhe ilmenee, jos yksittäisen rivin koko on yli 4 Mt. Sinun täytyy määrittää, mikä tietolähteen rivi on kyseessä, ja yrittää suodattaa se pois tai pienentää tämän rivin kokoa.

## <a name="data-sources"></a>Tietolähteet
**Puuttuva tietopalvelu** – Henkilökohtainen yhdyskäytävä on vain 64-bittinen. Se edellyttää, että tietopalveluiden 64-bittinen versio on asennettuna samaan tietokoneeseen, jossa henkilökohtainen yhdyskäytävä on asennettuna. Jos esimerkiksi tietojoukon tietolähde on Microsoft Access, sinun on asennettava 64-bittinen ACE-palvelu samaan tietokoneeseen, johon asensit henkilökohtaisen yhdyskäytävän.  

>[!NOTE]
>Jos sinulla on 32-bittinen Excel, et voi asentaa 64-bittistä ACE-palvelua samaan tietokoneeseen.

**Windows-todentamista ei tueta Access-tietokannan osalta** – Power BI tukee tällä hetkellä vain anonyymiä todentamista Access-tietokannassa. Pyrimme ottamaan Windows-todennuksen käyttöön Access-tietokannassa.

**Kirjautumisvirhe tunnistetietojen antamisen yhteydessä tietolähteeseen** – Jos saat tätä vastaavan virheilmoituksen antaessasi Windows-tunnistetietoja tietolähteelle, käytössäsi saattaa edelleen olla henkilökohtaisen yhdyskäytävän vanhempi versio. [Asenna Power BI Gateway - Personal -yhdyskäytävän uusin versio](https://powerbi.microsoft.com/gateway/).

  ![](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

**Virhe: Kirjautumisvirhe valittaessa Windows-todennusta tietolähteelle käyttämällä ACE OLEDB -palvelua** – Jos saat seuraavan virheilmoituksen antaessasi tietolähteen tunnistetietoja käyttämällä ACE OLEDB -palvelua:

![](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

Power BI tällä hetkellä tue Windows-todentamista tietolähteelle ACE OLEDB -palvelun avulla.

**Ratkaisu:** voit kiertää tämän virheen valitsemalla anonyymin todennuksen. Vanhoissa ACE OLEDB -palveluissa anonyymit tunnistetiedot vastaavat Windows-tunnistetietoja.

## <a name="tile-refresh"></a>Ruudun päivitys
Jos saat koontinäytön ruutujen päivittämistä koskevan virheilmoituksen, tutustu seuraavaan artikkeliin.

[Ruutuvirheiden vianmääritys](refresh-troubleshooting-tile-errors.md)

## <a name="tools-for-troubleshooting"></a>Työkalut vianmääritykseen
### <a name="refresh-history"></a>Päivityshistoria
**Päivityshistoriasta** näet ilmenneet virheet sekä hyödyllisiä tietoja, jos sinun täytyy luoda tukipyyntö. Voit tarkistaa sekä ajoitetut päivitykset että pyynnöstä suoritetut päivitykset. Pääset **päivityshistoriaan seuraavasti**.

1. Valitse Power BI:n siirtymisruudun **Tietojoukot**-kohdasta tietojoukko ja sitten &gt; Avaa valikko&gt; **Ajoita päivitys**.
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
2. Valitse **Asetukset kohteelle...** &gt; **Ajoita päivitys** > **Päivityshistoria**.  
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>Tapahtumalokit
Saatavilla on useita tapahtumalokeja, jotka voivat antaa tietoja. Kaksi ensimmäistä, **tietoyhdyskäytävä** ja **PowerBIGateway**, ovat käytettävissä, jos olet tietokoneen järjestelmänvalvoja.  Jos et ole järjestelmänvalvoja ja käytössäsi on henkilökohtainen yhdyskäytävä, näet lokimerkinnät **sovelluslokista**.

**Tietoyhdyskäytävän** ja **PowerBIGatewayn** lokit ovat kohdassa **Sovellus- ja palvelulokit**.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Fiddler-jäljitys
[Fiddler](http://www.telerik.com/fiddler) on Telerikin ilmainen työkalu, joka valvoo HTTP-liikennettä.  Voit tarkastella Power BI -palvelun tiedonsiirtoa asiakaskoneelta. Tämä saattaa näyttää virheitä ja muita olennaisia tietoja.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>Asennuslokit
Jos **henkilökohtaisen yhdyskäytävän** asennus epäonnistuu, näkyviin tulee linkki, jonka kautta pääset asennuslokiin. Lokista voit saada lisätietoja virheestä. Nämä ovat Windowsin asennuslokeja, joista käytetään myös nimitystä MSI-lokit. Ne voivat olla melko monimutkaisia ja vaikealukuisia. Tavallisesti tuloksena oleva virhe on alhaalla, mutta virheen syyn määrittäminen ei ole yksinkertaista. Se voi olla tulos eri lokissa olevista virheistä tai tulos lokissa ylempänä olevasta virheestä.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

Vaihtoehtoisesti voit siirtyä omaan **Temp-kansioosi** (% temp %) ja etsiä tiedostoja, jotka alkavat nimellä **Power\_BI\_**.

> [!NOTE]
> Hakemiston %temp% avaaminen voi viedä temp-alikansioon.  **Power\_BI\_**  -tiedostot ovat tilapäishakemiston juuressa.  Joudut ehkä siirtymään ylöspäin tason tai kahden verran.
> 
> 

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI -yhdyskäytävien välityspalvelinasetusten määrittäminen](service-gateway-proxy.md)  
[Tietojen uudelleenlataus](refresh-data.md)  
[Power BI Gateway - Personal](personal-gateway.md)  
[Ruutuvirheiden vianmääritys](refresh-troubleshooting-tile-errors.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

