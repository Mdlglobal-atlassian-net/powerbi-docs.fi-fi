## <a name="general"></a>Yleistä
**Kysymys:** Mikä on varsinaisen Windows-palvelun nimi?  
**Vastaus:** Yhdyskäytävää kutsutaan paikalliseksi tietojen yhdyskäytäväpalveluksi

**Kysymys:** Mitä yhdyskäytävän vaatimukset ovat?  
**Vastaus:** Katso päänäytöltä vaatimuksia koskevaa [yhdyskäytäväartikkelia](../service-gateway-onprem.md).

**Kysymys:** Mitä tietolähteitä yhdyskäytävä tukee?  
**Vastaus:** Katso tietolähdetaulukko [yhdyskäytäväartikkelista](../service-gateway-onprem.md).

**Kysymys:** Tarvitsenko yhdyskäytävää pilvitietolähteisiin, kuten Azure SQL-tietokantaan?  
**Vastaus**: Et. Palvelu voi muodostaa yhteyden tähän tietolähteeseen ilman yhdyskäytävää.

**Kysymys:** Saapuuko pilvipalvelusta yhteyksiä yhdyskäytävään?  
**Vastaus**: Ei. Yhdyskäytävä käyttää lähteviä yhteyksiä Azuren palveluväylään.

**Kysymys:** Entä jos estän lähtevät yhteydet? Mitä minun tulee avata?  
**Vastaus:** Katso [luettelo yhdyskäytävän käyttämistä porteista](../service-gateway-onprem.md#ports) ja isännistä.

**Vastaus:** Onko yhdyskäytävä asennettava samalle koneelle kuin tietolähde?  
**Vastaus**: Ei. Yhdyskäytävä yhdistää tietolähteeseen käyttämällä annettuja yhteystietoja. Yhdyskäytävä on tässä mielessä eräänlainen asiakassovellus. Sen on vain pystyttävä muodostamaan yhteys annettuun palvelimen nimeen.

**Kysymys:** Mikä on viive suoritettaessa kyselyjä yhdyskäytävästä tietolähteeseen? Mikä on paras arkkitehtuuri?  
**Vastaus:** on suositeltavaa sijoittaa yhdyskäytävä mahdollisimman lähelle tietolähdettä verkkoviiveen välttämiseksi. Jos voit asentaa yhdyskäytävän varsinaiseen tietolähteeseen, viive minimoituu. Muista myös palvelinkeskukset. Jos palvelusi käyttää esimerkiksi West US -palvelinkeskusta ja sinulla on SQL Server isännöitynä Azure VM:ssä, haluat että Azure VM on myös West US:ssä. Tämä minimoi viiveen ja auttaa välttämään lähtevän liikenteen maksut Azure VM:ssä.

**Kysymys:** Onko verkon kaistanleveydelle vaatimuksia?  
**Vastaus:** On suositeltavaa, että verkkoyhteyden siirtomäärä on hyvä. Jokainen ympäristö on erilainen, ja lähetettävien tietojen määrä vaikuttaa tuloksiin. ExpressRouten käyttäminen voi auttaa varmistamaan siirtomäärätason paikallisten palvelinkeskusten ja Azuren palvelinkeskusten välillä.

Voit käyttää kolmannen osapuolen [Azure Speed Test -sovellusta](http://azurespeedtest.azurewebsites.net/) siirtomäärän mittaamiseen.

**Kysymys:** Voiko yhdyskäytävän Windows-palvelu toimia Azure Active Directory -tilin kanssa?  
**Vastaus**: Ei. Windows-palvelulla on oltava kelvollinen Windows-tili. Oletusarvoisesti se toimii Service SID:llä, *NT SERVICE\PBIEgwService*.

**Kysymys:** Miten tulokset lähetetään takaisin pilvipalveluun?  
**Vastaus:** Tämä tehdään Azuren palveluväylän kautta. Saat lisätietoja [Miten se toimii](../service-gateway-onprem.md#how-the-gateway-works) -kohdasta.

**Kysymys:** Mihin tunnistetietoni tallennetaan?  
**Vastaus:** Tietolähteelle antamasi tunnistetiedot tallennetaan salattuina yhdyskäytävän pilvipalveluun. Tunnistetietojen salaus puretaan paikallisessa yhdyskäytävässä.

**Kysymys:** Voinko sijoittaa yhdyskäytävän edustaverkkoon (toiselta nimeltään DMZ tai suojattu aliverkko)?  
**Vastaus:** Yhdyskäytävä vaatii liitettävyyden tietolähteeseen. Jos tietolähde ei ole käytettävissä edustaverkossasi, yhdyskäytävä ei välttämättä voi muodostaa yhteyttä siihen. Esimerkiksi SQL Server ei voi olla edustaverkkosi. Et myöskään pysty muodostamaan yhteyttä SQL Serveriin -edustaverkosta. Jos asettaisit yhdyskäytävän edustaverkkoosi, se ei voisi muodostaa yhteyttä SQL Serveriin.

**Kysymys:** Onko mahdollista pakottaa yhdyskäytävä käyttämään HTTPS-liikennettä Azuren palveluväylän kanssa TCP:n sijaan?  
**Vastaus:** Kyllä. Vaikka tämä vähentääkin merkittävästi suorituskykyä. Tämä edellyttää tiedoston *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* muokkaamista. Haluat muuttaa arvon `AutoDetect` arvoksi `Https`. Tämä tiedosto löytyy oletusarvoisesti sijainnista *C:\Program Files\On-premises data gateway*.

**Kysymys:** Pitääkö Azure palvelinkeskuksen IP-luettelo lisätä sallittujen luetteloon? Mistä saan luettelon?  
**Vastaus:** Jos estät lähtevän IP-liikenteen, saatat joutua lisäämään Azure palvelinkeskuksen IP-luettelon sallittujen luetteloon. Tällä hetkellä yhdyskäytävä vaihtaa tietoja Azuren palveluväylän kanssa käyttämällä IP-osoitetta ja täydellistä toimialuenimeä. Azure-palvelinkeskuksen IP-luettelo päivittyy viikoittain. Voit ladata [Microsoft Azuren palvelinkeskusten IP-osoiteluettelon](https://www.microsoft.com/download/details.aspx?id=41653).

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="high-availabilitydisaster-recovery"></a>Korkea käytettävyys / järjestelmäpalautus
**Kysymys:** Onko suunnitteilla korkean käytettävyyden skenaarioiden ottamista käyttöön yhdyskäytävän kanssa?  
**Vastaus:** Kyllä, tämä on Power BI-tiimin aktiivinen painopistealue. Pysy kuulolla ja lue [Power BI-blogia](https://powerbi.microsoft.com/blog/) saadaksesi lisätietoja tästä ominaisuudesta.

**Kysymys:** Mitä vaihtoehtoja järjestelmäpalautukseen on saatavilla?  
**Vastaus:** Voit käyttää palautusavainta yhdyskäytävän palauttamiseen tai siirtämiseen. Anna palautusavain, kun asennat yhdyskäytävän.

**Kysymys:** Mitä etua palautusavaimesta on?  
**Vastaus:** Se tarjoaa tavan siirtää tai palauttaa yhdyskäytävän asetukset. Tätä käytetään myös järjestelmäpalautuksessa.

## <a name="troubleshooting"></a>Vianmääritys
**Kysymys:** Missä yhdyskäytävän lokit sijaitsevat?  
**Vastaus:** Katso kohtaa Työkalut [vianmääritysartikkelista](../service-gateway-onprem-tshoot.md#tools-for-troubleshooting).

**Kysymys:** Miten näen, mitkä kyselyt lähetetään paikalliseen tietolähteeseen?  
**Vastaus:** Kyselyn jäljityksen voi ottaa käyttöön.  Tähän sisältyvät lähetettävät kyselyt. Muista vaihtaa oletusarvo takaisin, kun olet suorittanut vianmäärityksen. Jos kyselyjen seuranta jätetään käyttöön, lokit muuttuvat suuremmiksi.

Voit myös tutustua työkaluihin, jotka tietolähteesi sisältää kyselyjen seuraamista varten. Voit käyttää esimerkiksi Extended Events- tai SQL Profiler for SQL Server- ja Analysis Services -työkaluja.

