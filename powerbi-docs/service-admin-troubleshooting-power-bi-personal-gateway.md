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
ms.openlocfilehash: bc6eaccc2976266102dcca0d20df73df810fa5f3
ms.sourcegitcommit: bf535771c9ef495f9bb658569403fa5e3dd82e6a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2019
ms.locfileid: "65853565"
---
# <a name="troubleshooting-power-bi-gateway---personal"></a>Power BI Gateway - Personal -yhdyskäytävän vianmääritys
Seuraavassa käydään läpi joitakin yleisiä ongelmia, jotka saattavat olla eri, kun käytät Power BI Gateway-Personal.

> [!NOTE]
> Henkilökohtaiseen käyttöön tarkoitetun yhdyskäytävän nykyinen versio on **paikallinen tietoyhdyskäytävä (henkilökohtainen)**. Päivitä asennuksesi käyttämään kyseistä versiota.
> 
> 

## <a name="update-to-the-latest-version"></a>Päivitä uusimpaan versioon
Monet ongelmat ilmenevät yhdyskäytävän versio on vanhentunut.  Se on hyvä yleinen käytäntö on varmistaa, että olet aina uusinta versiota. Jos ole päivittänyt yhdyskäytävää, kuukausi tai pidempi, harkitse yhdyskäytävän uusin versio. Katso sitten, jos toistuuko ongelma.

## <a name="installation"></a>Asennus
**Henkilökohtainen yhdyskäytävä on 64-bittinen** – Jos tietokoneesi on 32-bittinen, et voi asentaa henkilökohtaisen yhdyskäytävän. Käyttöjärjestelmän on oltava 64-bittinen versio. Asenna Windows 64-bittinen versio tai asenna henkilökohtaisen yhdyskäytävän 64-bittiseen tietokoneeseen.

**Henkilökohtaisen yhdyskäytävän asentaminen palveluna, vaikka olet tietokoneen paikallinen järjestelmänvalvoja epäonnistuu** – asennus voi epäonnistua, jos käyttäjä kuuluu tietokoneen paikallisten järjestelmänvalvojien ryhmään, mutta Ryhmäkäytäntö ei salli kyseisen käyttäjätunnuksen Kirjaudu sisään palvelu. Tällä hetkellä Varmista, että Ryhmäkäytäntö sallii käyttäjän, kirjaudu sisään palveluna. Pyrimme korjaamaan tämän ongelman. [Lue lisää](https://technet.microsoft.com/library/cc739424.aspx)

**Toiminto aikakatkaistiin** – tämä viesti on yleinen, jos tietokoneessa (fyysinen kone tai Näennäiskone), johon olet asentamassa henkilökohtaista yhdyskäytävää on yksiytiminen suoritin. Sulje kaikki sovellukset, poista tarpeettomat prosessit käytöstä ja yritä asentaa uudelleen.

**Tietoyhdyskäytävää tai Analysis Services Connector ei voi asentaa samaan tietokoneeseen henkilökohtaisen yhdyskäytävän** – Jos sinulla on jo Analysis Services Connector-tai tietoyhdyskäytävä asennettuna, poista ensin liittimen tai yhdyskäytävä. Yritä sitten asentaa henkilökohtainen yhdyskäytävä.

> [!NOTE]
> Jos kohtaat ongelman asennuksen aikana asennuslokit antaa tietoja, jotka auttavat sinua ratkaisemaan ongelman. Jos haluat lisätietoja, katso [asennuslokit](#SetupLogs).
> 
> 

 **Välityspalvelimen määritys** näyttöön saattaa tulla ongelmia henkilökohtaisen yhdyskäytävän määrityksessä, jos ympäristösi tarvitsee välityspalvelimen käyttöä. Lisätietoja välityspalvelimen tietojen määrityksestä saat artikkelista [Power BI -yhdyskäytävien välityspalvelinasetusten määrittäminen](service-gateway-proxy.md).

## <a name="schedule-refresh"></a>Ajoita päivitys
**Virhe: pilveen tallennettu tunnistetieto puuttuu.**

Voit saada tämän virheen asetuksissa \<tietojoukon\> Jos olet ajoittanut päivityksen asennus ja henkilökohtaisen yhdyskäytävän uudelleen. Kun henkilökohtaisen yhdyskäytävän asennuksen, joka on päivitettäväksi määritetyn tietojoukon tietolähteen tunnistetiedot poistetaan Power BI-palvelusta.

**Ratkaisu:** Siirry Power BI:ssä tietojoukon päivitysasetuksiin. Tietolähteiden hallinta-virheen tietolähteen Valitse **Muokkaa tunnistetietoja** ja kirjaudu sisään tietolähteeseen uudelleen.

**Virhe: tietojoukolle annetut tunnistetiedot ovat virheelliset. Jatka päivittämällä tunnistetiedot päivityksen kautta tai Tietolähdeasetukset-valintaikkunassa.**

**Ratkaisu**: Jos näyttöön tulee tunnistetietosanoma, se voi tarkoittaa seuraavia asioita:

* Varmista, että käyttäjänimet ja salasanat kirjautua sisään tietolähteisiin ovat ajan tasalla. Siirry Power BI:ssä tietojoukon päivitysasetuksiin. Valitse tietolähteiden hallinta **Muokkaa tunnistetietoja** tietolähteen tunnistetietojen päivittäminen.
* Koosteet pilvipalvelulähteen ja paikallisen lähteen välillä, yksittäisessä kyselyssä, eivät päivity henkilökohtaisessa yhdyskäytävässä, jos jompikumpi lähteistä käyttää OAuth-todennusta. Esimerkiksi Tämä ongelma on kooste CRM Onlinen ja paikallisen SQL Server-välillä. Kooste ei onnistu, koska CRM Online edellyttää OAuth-todennusta.
  
  Tämä virhe on tunnettu ongelma ja se on parhaillaan tarkastellut. Voit kiertää ongelman ole erillisiä kyselyitä pilvipalvelulähteelle ja paikalliselle lähteelle. Sitten käyttämällä Yhdistä tai liittämiskysely yhdistää ne.

**Virhe: ei-tuettu tietolähde.**

**Ratkaisu:** Jos saat ei-tuetusta tietolähteestä ilmoittavan virhesanoman Ajoita päivitys -asetuksissa, se voi tarkoittaa seuraavia asioita: 

* Tietolähde ei tällä hetkellä tueta Power BI-päivitys. 
* Excel-työkirja ei sisällä tietomallia, vain laskentataulukkotietoja. Power BI tukee tällä hetkellä päivitystä vain, jos ladattu Excel-työkirja sisältää tietomallin. Kun tuot tietoja Power Queryn avulla Excelissä, muista valita Lataa tiedot tietomalliin -vaihtoehto. Tämä asetus varmistaa, että tiedot tuodaan tietomallin. 

**Virhe: [Tietojen yhdistäminen ei onnistu] &lt;kyselyosa&gt;/&lt;... &gt; / &lt;... &gt; käyttää tietolähteitä, joiden yksityisyystasoja ei voi käyttää yhdessä. Muodosta tämä tietoyhdistelmä uudelleen.**

**Ratkaisu**: Tämä virhe johtuu tietosuojatason rajoituksista ja erilaisiin tietolähteisiin, jota käytät.

**Virhe: Tietolähdevirhe: Arvoa ”\[Table\]” ei voi muuntaa tyypiksi Table.**

**Ratkaisu**: Tämä virhe johtuu tietosuojatason rajoituksista ja erilaisiin tietolähteisiin, jota käytät.

**Virhe: Tälle riville ei ole tarpeeksi tilaa.**

Tämä virhe ilmenee, jos sinulla on yli 4 Mt. yksittäisen rivin kokoa. Etsi rivi, tietolähteestä ja yrittää suodattaa se pois tai pienentää kyseisen rivin kokoa.

## <a name="data-sources"></a>Tietolähteet
**Puuttuva tietopalvelu** – henkilökohtainen yhdyskäytävä on vain 64-bittinen versio. Se edellyttää, että tietopalveluiden 64-bittinen versio on asennettuna samaan tietokoneeseen, jossa henkilökohtainen yhdyskäytävä on asennettuna. Jos esimerkiksi tietojoukon tietolähde on Microsoft Access, sinun on asennettava 64-bittinen ACE-palvelu samaan tietokoneeseen, johon asensit henkilökohtaisen yhdyskäytävän.  

>[!NOTE]
>Jos sinulla on 32-bittinen Excel, et voi asentaa 64-bittinen ACE-palvelua samaan tietokoneeseen.

**Windows-todentamista ei tueta Access-tietokannan osalta** – Power BI tukee tällä hetkellä vain anonyymiä todentamista Access-tietokannassa. Pyrimme ottamaan Windows-todennuksen käyttöön Access-tietokannassa.

**Kirjautumisvirhe tunnistetietojen antamisen yhteydessä tietolähteeseen** – Jos saat virheilmoituksen katsomalla antaessasi Windows-tunnistetietoja tietolähteelle, käytössäsi saattaa edelleen olla henkilökohtaisen yhdyskäytävän vanhempi versio. [Asenna Power BI Gateway - Personal -yhdyskäytävän uusin versio](https://powerbi.microsoft.com/gateway/).

  ![](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

**Virhe: Kirjautumisvirhe valittaessa Windows-todennusta tietolähteelle käyttämällä ACE OLEDB -palvelua** – Jos saat seuraavan virheilmoituksen antaessasi tietolähteen tunnistetietoja käyttämällä ACE OLEDB -palvelua:

![](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

Power BI ei tällä hetkellä tue Windows-todennusta tietolähteelle käyttämällä ACE OLEDB-palvelua.

**Ratkaisu:** Voit kiertää tämän virheen valitsemalla **anonyymi todennus**. Vanhoissa ACE OLEDB-anonyymit tunnistetiedot vastaavat Windows-tunnistetietoja.

## <a name="tile-refresh"></a>Ruudun päivitys
Jos saat virhe koontinäyttöruudut päivittyvät, katso seuraavasta artikkelista.

[Ruutuvirheiden vianmääritys](refresh-troubleshooting-tile-errors.md)

## <a name="tools-for-troubleshooting"></a>Työkalut vianmääritykseen
### <a name="refresh-history"></a>Päivityshistoria
**Päivityshistoria** avulla näet ilmenneet virheet ja tarjoaa hyödyllisiä tietoja, jos haluat luoda tukipyyntö. Voit tarkastella ajoitettu sekä pyydettäessä päivitykset. Miten saat **päivityshistoria**.

1. Valitse Power BI:n siirtymisruudun **Tietojoukot**-kohdasta tietojoukko ja sitten &gt; Avaa valikko&gt; **Ajoita päivitys**.
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
1. - **Asetukset...** , valitse **päivityshistoria**.  
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>Tapahtumalokit
Useita tapahtumalokeja voi antaa tietoja. Kaksi ensimmäistä, **Data Management Gateway** ja **PowerBIGateway**, ei ole, jos olet tietokoneen järjestelmänvalvoja.  Jos et ole järjestelmänvalvoja ja käytät henkilökohtaista yhdyskäytävää, näet lokimerkinnät **sovelluksen** log.

**Tietoyhdyskäytävän** ja **PowerBIGatewayn** lokit ovat kohdassa **Sovellus- ja palvelulokit**.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Fiddler-jäljitys
[Fiddler](http://www.telerik.com/fiddler) on Telerikin ilmainen työkalu, joka valvoo HTTP-liikennettä. Näet Power BI-palvelun tiedonsiirtoa tietoliikenteen. Tämä tiedote saattaa näyttää virheitä ja muita olennaisia tietoja.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>Asennuslokit
Jos **henkilökohtaisen yhdyskäytävän**, ei voi asentaa, näkyviin tulee linkki asennuslokiin. Asennuksen lokin näyttää voit saada lisätietoja virheestä. Nämä lokit ovat Windowsin, myös nimitystä MSI-lokit. Ne voivat olla melko monimutkaisia ja vaikealukuisia. Yleensä alareunassa on saatava virhe, mutta määritettäessä virheen syy ei ole yksinkertaisen. Se voi olla tulos eri lokissa olevista virheistä tai tulos lokissa ylempänä olevasta virheestä.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

Tai voit siirtyä- **Temp-kansioosi** (% temp %) ja etsiä tiedostoja, jotka alkavat **Power\_BI\_**.

> [!NOTE]
> Hakemiston %temp% avaaminen voi viedä temp-alikansioon. **Power\_BI\_**  tiedostot ovat tilapäishakemiston juuressa.  Joudut ehkä siirtymään ylöspäin tason tai kahden verran.
> 
> 

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI -yhdyskäytävien välityspalvelinasetusten määrittäminen](service-gateway-proxy.md)  
[Tietojen uudelleenlataus](refresh-data.md)  
[Power BI Gateway - Personal](service-gateway-personal-mode.md)  
[Ruutuvirheiden vianmääritys](refresh-troubleshooting-tile-errors.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

