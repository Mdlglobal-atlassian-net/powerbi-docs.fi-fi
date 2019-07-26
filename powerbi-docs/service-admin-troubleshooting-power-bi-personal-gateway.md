---
title: Power BI Gateway - Personal -yhdyskäytävän vianmääritys
description: Power BI Gateway - Personal -yhdyskäytävän vianmääritys
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 5/06/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 7827ce359022eccfb75798b08da164b7504c84df
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271841"
---
# <a name="troubleshooting-power-bi-gateway---personal"></a>Power BI Gateway - Personal -yhdyskäytävän vianmääritys

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Seuraavissa osissa käydään läpi joitakin yleisiä ongelmia, joita saatat kohdata käyttäessäsi Power BI Gateway - Personal -yhdyskäytävää.

## <a name="update-to-the-latest-version"></a>Päivitä uusimpaan versioon

Henkilökohtaiseen käyttöön tarkoitetun yhdyskäytävän nykyinen versio on **paikallinen tietoyhdyskäytävä (henkilökohtainen)** . Päivitä asennuksesi käyttämään kyseistä versiota.

Ongelmia voi esiintyä paljon, jos yhdyskäytävän versio on vanhentunut.  Hyvä yleinen käytäntö on varmistaa, että käytät aina uusinta versiota. Jos et ole päivittänyt yhdyskäytävää ainakaan kuukauteen, sinun kannattaa harkita yhdyskäytävän uusimman version asentamista. Tarkista sitten, voitko toistaa ongelman.

## <a name="installation"></a>Asennus
**Henkilökohtainen yhdyskäytävä on 64-bittinen** – Jos koneesi on 32-bittinen, henkilökohtaista yhdyskäytävää ei voi asentaa. Käyttöjärjestelmän on oltava 64-bittinen versio. Asenna Windowsin 64-bittinen versio tai asenna henkilökohtainen yhdyskäytävä 64-bittiseen tietokoneeseen.

**Henkilökohtaisen yhdyskäytävän asentaminen palveluna epäonnistuu, vaikka olet tietokoneen paikallinen järjestelmänvalvoja** – Asennus voi epäonnistua, jos käyttäjä kuuluu tietokoneen paikallisten järjestelmänvalvojien ryhmään, mutta ryhmäkäytäntö ei salli kyseisen käyttäjätunnuksen kirjautumista palveluna. Varmista tässä tilanteessa, että ryhmäkäytäntö sallii käyttäjän kirjautumisen sisään palveluna. Pyrimme korjaamaan tämän ongelman. [Lue lisää](https://technet.microsoft.com/library/cc739424.aspx)

**Toiminto aikakatkaistiin** – Tämä sanoma on yleinen, jos tietokoneessa (fyysinen kone tai näennäiskone), johon olet asentamassa henkilökohtaista yhdyskäytävää, on yksiytiminen suoritin. Sulje kaikki sovellukset, poista tarpeettomat prosessit käytöstä ja yritä asentaa uudelleen.

**Tietoyhdyskäytävää tai Analysis Services Connector -liitintä ei voi asentaa samaan tietokoneeseen henkilökohtaisen yhdyskäytävän kanssa** – Jos sinulla on jo Analysis Services Connector tai tietoyhdyskäytävä asennettuna, poista ensin liittimen tai henkilökohtaisen yhdyskäytävän asennus. Yritä sitten asentaa henkilökohtainen yhdyskäytävä.

> [!NOTE]
> Jos kohtaat ongelman asennuksen aikana, asennuslokeista voit saada tietoja, jotka auttavat sinua ratkaisemaan ongelman. Katso lisätietoja kohdasta [Asennuslokit](#SetupLogs).
> 
> 

 **Välityspalvelinmääritys** – Henkilökohtaisen yhdyskäytävän määrityksessä voi ilmetä ongelmia, jos ympäristössäsi on käytettävä välityspalvelinta. Lisätietoja välityspalvelimen tietojen määrityksestä saat artikkelista [Paikallisen tietoyhdyskäytävän välityspalvelinasetusten määrittäminen](/data-integration/gateway/service-gateway-proxy).

## <a name="schedule-refresh"></a>Ajoita päivitys
**Virhe: pilveen tallennettu tunnistetieto puuttuu.**

Saatat saada tämän virheilmoituksen \<tietojoukon\> asetuksissa, jos olet ajoittanut päivityksen ja sen jälkeen poistanut henkilökohtaisen yhdyskäytävän asennuksen ja asentanut sen uudelleen. Kun poistat henkilökohtaisen yhdyskäytävän asennuksen, päivitettäväksi määritetyn tietojoukon tietolähteen tunnistetiedot poistetaan Power BI -palvelusta.

**Ratkaisu:** Siirry Power BI:ssä tietojoukon päivitysasetuksiin. Valitse Tietolähteiden hallinta -kohdassa kaikkien virheen kohdanneiden tietolähteiden kohdalla **Muokkaa tunnistetietoja** -vaihtoehto ja kirjaudu sitten tietolähteeseen uudelleen.

**Virhe: tietojoukolle annetut tunnistetiedot ovat virheelliset. Jatka päivittämällä tunnistetiedot päivityksen kautta tai Tietolähdeasetukset-valintaikkunassa.**

**Ratkaisu**: Jos näyttöön tulee tunnistetietosanoma, se voi tarkoittaa seuraavia asioita:

* Varmista, että tietolähteisiin kirjautumiseen käytetyt käyttäjänimet ja salasanat ovat ajan tasalla. Siirry Power BI:ssä tietojoukon päivitysasetuksiin. Päivitä tietolähteen tunnistetiedot valitsemalla Tietolähteiden hallinnassa **Muokkaa tunnistetietoja** -vaihtoehto.
* Koosteet pilvipalvelulähteen ja paikallisen lähteen välillä, yksittäisessä kyselyssä, eivät päivity henkilökohtaisessa yhdyskäytävässä, jos jompikumpi lähteistä käyttää OAuth-todennusta. Esimerkki tästä ongelmasta on kooste CRM Onlinen ja paikallisen SQL Serverin välillä. Kooste epäonnistuu, koska CRM Online edellyttää OAuth-todennusta.
  
  Tämä virhe on tunnettu ongelma, joka on tarkastelun alla. Voit kiertää ongelman käyttämällä erillisiä kyselyitä pilvipalvelulähteelle ja paikalliselle lähteelle. Yhdistä ne käyttämällä Yhdistä kysely- tai Liitä kyselyt loppuun -toimintoa.

**Virhe: ei-tuettu tietolähde.**

**Ratkaisu:** Jos saat ei-tuetusta tietolähteestä ilmoittavan virhesanoman Ajoita päivitys -asetuksissa, se voi tarkoittaa seuraavia asioita: 

* Tietolähteen päivitystä ei tällä hetkellä tueta Power BI:ssä. 
* Excel-työkirja ei sisällä tietomallia, vain laskentataulukon tietoja. Power BI tukee tällä hetkellä päivitystä vain, jos ladattu Excel-työkirja sisältää tietomallin. Kun tuot tietoja Power Queryn avulla Excelissä, muista valita Lataa tiedot tietomalliin -vaihtoehto. Tämä vaihtoehto varmistaa, että tiedot tuodaan tietomalliin. 

**Virhe: [Tietojen yhdistäminen ei onnistu] &lt;kyselyosa&gt;/&lt;…&gt;/&lt;…&gt; käyttää tietolähteitä, joiden yksityisyystasoja ei voi käyttää yhdessä. Muodosta tämä tietoyhdistelmä uudelleen.**

**Ratkaisu**: Tämä virhe johtuu yksityisyystason rajoituksista ja käyttämiesi tietolähteiden tyypeistä.

**Virhe: Tietolähdevirhe: Arvoa ”\[Table\]” ei voi muuntaa tyypiksi Table.**

**Ratkaisu**: Tämä virhe johtuu yksityisyystason rajoituksista ja käyttämiesi tietolähteiden tyypeistä.

**Virhe: Tälle riville ei ole tarpeeksi tilaa.**

Tämä virhe ilmenee, jos yksittäisen rivin koko on yli 4 Mt. Selvitä, mikä tietolähteen rivi on kyseessä, ja yritä suodattaa se pois tai pienentää kyseisen rivin kokoa.

## <a name="data-sources"></a>Tietolähteet
**Puuttuva tietopalvelu** – Henkilökohtainen yhdyskäytävä on vain 64-bittinen versio. Se edellyttää, että tietopalveluiden 64-bittinen versio on asennettuna samaan tietokoneeseen, jossa henkilökohtainen yhdyskäytävä on asennettuna. Jos esimerkiksi tietojoukon tietolähde on Microsoft Access, sinun on asennettava 64-bittinen ACE-palvelu samaan tietokoneeseen, johon asensit henkilökohtaisen yhdyskäytävän.  

>[!NOTE]
>Jos sinulla on 32-bittinen Excel-versio, et voi asentaa 64-bittistä ACE-palvelua samaan tietokoneeseen.

**Windows-todentamista ei tueta Access-tietokannan osalta** – Power BI tukee tällä hetkellä vain anonyymiä todentamista Access-tietokannassa. Pyrimme ottamaan Windows-todennuksen käyttöön Access-tietokannassa.

**Kirjautumisvirhe tunnistetietojen antamisen yhteydessä tietolähteeseen** – Jos saat tällaisen virheilmoituksen antaessasi Windows-tunnistetietoja tietolähteelle, käytössäsi saattaa edelleen olla henkilökohtaisen yhdyskäytävän vanhempi versio. [Asenna Power BI Gateway - Personal -yhdyskäytävän uusin versio](https://powerbi.microsoft.com/gateway/).

  ![](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

**Virhe: Kirjautumisvirhe valittaessa Windows-todennusta tietolähteelle käyttämällä ACE OLEDB -palvelua** – Jos saat seuraavan virheilmoituksen antaessasi tietolähteen tunnistetietoja käyttämällä ACE OLEDB -palvelua:

![](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

Power BI tällä hetkellä tue Windows-todentamista tietolähteelle ACE OLEDB -palvelun avulla.

**Ratkaisu:** Voit ohittaa tämän virheen valitsemalla **anonyymin todennuksen**. Vanhoissa ACE OLEDB -palveluissa anonyymit tunnistetiedot vastaavat Windows-tunnistetietoja.

## <a name="tile-refresh"></a>Ruudun päivitys
Jos saat koontinäytön ruutujen päivittämistä koskevan virheilmoituksen, tutustu seuraavaan artikkeliin.

[Ruutuvirheiden vianmääritys](refresh-troubleshooting-tile-errors.md)

## <a name="tools-for-troubleshooting"></a>Työkalut vianmääritykseen
### <a name="refresh-history"></a>Päivityshistoria
**Päivityshistoriasta** näet ilmenneet virheet ja hyödyllisiä tietoja, jos joudut luomaan tukipyynnön. Voit tarkistaa sekä ajoitetut päivitykset että pyynnöstä suoritetut päivitykset. Pääset **päivityshistoriaan** seuraavasti.

1. Valitse Power BI:n siirtymisruudun **Tietojoukot**-kohdasta tietojoukko ja sitten &gt; Avaa valikko&gt; **Ajoita päivitys**.
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
1. Valitse **Asetukset kohteelle...** ja **Päivityshistoria**.  
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>Tapahtumalokit
Saatavilla on useita tapahtumalokeja, jotka voivat antaa tietoja. Kaksi ensimmäistä, **tietoyhdyskäytävä** ja **PowerBIGateway**, ovat käytettävissä, jos olet tietokoneen järjestelmänvalvoja.  Jos et ole järjestelmänvalvoja ja käytössäsi on henkilökohtainen yhdyskäytävä, näet lokimerkinnät **sovelluslokista**.

**Tietoyhdyskäytävän** ja **PowerBIGatewayn** lokit ovat kohdassa **Sovellus- ja palvelulokit**.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Fiddler-jäljitys
[Fiddler](http://www.telerik.com/fiddler) on Telerikin ilmainen työkalu, joka valvoo HTTP-liikennettä. Voit tarkastella Power BI -palvelun tiedonsiirtoa asiakaskoneelta. Tässä tiedonsiirrossa saattaa näkyä virheitä ja muita olennaisia tietoja.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>Asennuslokit
Jos **henkilökohtaisen yhdyskäytävän** asennus epäonnistuu, näkyviin tulee linkki, jonka kautta pääset asennuslokiin. Asennusloki voi sisältää lisätietoja virheestä. Lokit ovat Windowsin asennuslokeja, joista käytetään myös nimitystä MSI-lokit. Ne voivat olla melko monimutkaisia ja vaikealukuisia. Tavallisesti tuloksena oleva virhe on alhaalla, mutta virheen syyn määrittäminen ei ole yksinkertaista. Se voi olla tulos eri lokissa olevista virheistä tai tulos lokissa ylempänä olevasta virheestä.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

Voit myös siirtyä omaan **Temp-kansioosi** (%temp%) ja etsiä tiedostoja, jotka alkavat nimellä **Power\_BI\_** .

> [!NOTE]
> Hakemiston %temp% avaaminen voi viedä temp-alikansioon. **Power\_BI\_** -tiedostot ovat tilapäishakemiston juuressa.  Joudut ehkä siirtymään ylöspäin tason tai kahden verran.
> 
> 

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Paikallisen tietoyhdyskäytävän välityspalvelinasetusten määrittäminen](/data-integration/gateway/service-gateway-proxy)  
[Tietojen päivittäminen](refresh-data.md)  
[Power BI Gateway - Personal](service-gateway-personal-mode.md)  
[Ruutuvirheiden vianmääritys](refresh-troubleshooting-tile-errors.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

