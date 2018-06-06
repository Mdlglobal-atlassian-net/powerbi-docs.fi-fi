## <a name="sign-in-account"></a>Kirjautumistili
Käyttäjät kirjautuvat sisään joko työpaikan tai oppilaitoksen tilillä. Se on käyttäjän organisaatiotili. Jos olet tilannut Office 365 -tarjooman etkä ole antanut todellista työsähköpostiasi, tilisi voi näyttää tältä: nancy@contoso.onmicrosoft.com. Pilvipalvelun sisällä oleva tilisi on tallennettu-vuokraajaan Azure Active Directoryssa (AAD). Useimmissa tapauksissa Azure Active Directory -tilin täydellinen käyttäjätunnus vastaa sähköpostiosoitetta.

## <a name="windows-service-account"></a>Windows-palvelutili
Paikallinen tietoyhdyskäytävä on määritetty käyttämään *NT SERVICE\PBIEgwService* -palvelua Windows-palvelun sisäänkirjautumisen tunnistetiedoille. Sillä on oletusarvoisesti sisäänkirjautumisoikeus palveluna. Tämä on sen koneen kontekstissa, jolle asennat yhdyskäytävän.

> [!NOTE]
> Jos olet valinnut henkilökohtaisen tilan, voit määrittää Windows-palvelutilin erikseen.
> 
> 

Tämä ei ole tili, jota käytetään yhteyden muodostamiseen paikalliseen tietolähteisiin.  Tämä ei myöskään ole työpaikan tai oppilaitoksen tili, jolla kirjaudut pilvipalveluihin.

Jos kohtaat todentamisen vuoksi ongelmia välityspalvelimen kanssa, sinun kannattaa vaihtaa Windows-palvelutili toimialuekäyttäjäksi tai hallituksi palvelutiliksi. Saat tietää, kuinka muutetaan [välityspalvelimen määrityksiä](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

## <a name="ports"></a>Portit
Yhdyskäytävä luo lähtevän yhteyden Azuren palveluväylään. Se viestii lähtevien porttien kautta: TCP 443 (oletusarvoinen), 5671, 5672, 9350–9354.  Yhdyskäytävä ei vaadi saapuvia portteja. [Lue lisää](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/)

On suositeltavaa, että lisäät tietoalueesi IP-osoitteet sallittujen luetteloon palomuurin asetuksissa. Voit ladata [Microsoft Azuren palvelinkeskusten IP-osoiteluettelon](https://www.microsoft.com/download/details.aspx?id=41653). Luettelo päivitetään viikoittain. Yhdyskäytävä vaihtaa tietoja Azuren palveluväylän kanssa käyttämällä IP-osoitetta ja täydellistä toimialuenimeä (FQDN). Jos pakotat yhdyskäytävän vaihtamaan tietoja HTTPS-yhteyden kautta, se käyttää ainoastaan FQDN:ää ja tietojen vaihtoa IP-osoitteita käyttämällä ei tapahdu lainkaan.

> [!NOTE]
> Azuren palvelinkeskusten IP-osoiteluettelossa käytetään CIDR-merkintätapaa. Esimerkiksi 10.0.0.0/24 ei tarkoita 10.0.0.0 /10.0.0.24. Lue lisätietoja [CIDR-merkintätavasta](http://whatismyipaddress.com/cidr).
> 
> 

Tässä on luettelo yhdyskäytävän käyttämistä täysin valtuutetuista toimialuenimistä.

| Toimialuenimet | Lähtevien pyyntöjen portit | Kuvaus |
| --- | --- | --- |
| *. download.microsoft.com |80 |Asennusohjelman lataamisessa käytettävä HTTP. |
| *.powerbi.com |443 |HTTPS |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671–5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350–9354 |Kuuntelutoiminnot Microsoft Azuren palveluväylässä käyttäen TCP-protokollaa (edellyttää 443:n käyttöoikeuksien hallinnan tunnuksen hankintaa varten) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| *.msftncsi.com |443 |Käytetään Internet-yhteyden testaamiseen, jos Power BI -palvelu ei saa yhteyttä yhdyskäytävään. |
| *.microsoftonline-p.com |443 |Käytetään todentamiseen määritysten mukaan. |

> [!NOTE]
> Liikenne visualstudio.comiin tai visualstudioonline.comiin ovat sovelluksen merkityksellisiä tietoja, eivätkä ne ole pakollisia yhdyskäytävän funktiolle.
> 
> 

## <a name="forcing-https-communication-with-azure-service-bus"></a>HTTPS-tiedonsiirron pakottaminen Azuren palveluväylän kanssa
Voit pakottaa yhdyskäytävän vaihtamaan tietoja Azuren palveluväylän kanssa HTTPS-yhteydellä suoran TCP-yhteyden sijaan. Tällä voi olla vaikutusta suorituskykyyn. Voit tehdä tämän muokkaamalla *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* -tiedostoa muuttamalla arvon `AutoDetect` arvoksi `Https`suoraan tämän kappaleen jälkeen esitetyn koodikatkelma mukaisesti. Tiedosto löytyy (oletusarvoisesti) sijainnista *C:\Program Files\On-premises data gateway*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

*ServiceBusSystemConnectivityModeString* -parametrin arvossa kirjainkoko on merkitsevä. Kelvolliset arvot ovat *Automaattinen tunnistus* ja *Https*.

Vaihtoehtoisesti voit pakottaa yhdyskäytävän valitsemaan tämän tavan käyttämällä yhdyskäytävän käyttöliittymää alkaen [maaliskuun 2017](https://powerbi.microsoft.com/blog/power-bi-gateways-march-update/) julkaisusta. Valitse yhdyskäytävän käyttöliittymässä **Verkko** ja ota **Azuren palveluväylän yhteystila** **käyttöön**.

![](./media/gateway-onprem-accounts-ports-more/gw-onprem_01.png)

Kun se on vaihdettu ja kun valitset **Käytä** (painike, joka tulee näkyviin vain, kun teet muutoksen), *yhdyskäytävän Windows-palvelu* käynnistyy automaattisesti uudelleen, jotta muutokset tulevat voimaan.

Vastaisuudessa voit käynnistää *yhdyskäytävän Windows-palvelun* uudelleen valitsemalla käyttöliittymä-valintaikkunasta **Palveluasetukset** ja sitten *Käynnistä uudelleen nyt*.

![](./media/gateway-onprem-accounts-ports-more/gw-onprem_02.png)

## <a name="support-for-tls-1112"></a>TLS 1.1:n ja TLS 1.2:n tuki
Elokuun 2017 päivityksestä lähtien paikallinen yhdyskäytävä on oletusarvoisesti yhteydessä **Power BI -palveluun** Transport Layer Security (TLS) 1.1:llä tai 1.2:lla. Vanhemmat paikallisen tietoyhdyskäytävän versiot käyttävät oletusarvoisesti TLS 1.0:aa. TLS 1.0:n tuki päättyi 15.3.2018, mukaan lukien käytävän kysy toimia **Power BI -palvelun kanssa** käyttämällä TLS 1.0:a, joten sinun täytyy päivittää paikallisen tietoyhdyskäytävän asennukset elokuun 2017 versioon tai tätä uudempaan versioon, jotta yhdyskäytäväsi toimivat jatkossakin.

Paikallinen tietoyhdyskäytävä tukee TLS 1.0:aa 1.11.2017 saakka ja tämän jälkeenkin varamekanismina. Voit varmistaa, että yhdyskäytäväliikenne käyttää TLS 1.1:tä tai 1.2:ta (ja estää TSL 1.0:n käytön yhdyskäytävässäsi) lisäämällä seuraavat rekisteriavaimet koneeseen, joka suorittaa yhdyskäytäväpalvelua, tai muokkaamalla niitä siinä:

        [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
        [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001

> [!NOTE]
> Näiden rekisteriavaimien lisääminen tai muokkaaminen ottaa muutoksen käyttöön kaikissa .NET-sovelluksissa. Jos haluat lisätietoja rekisterimuutoksista, jotka vaikuttavat muiden sovellusten TLS:ään, lue ohjeartikkeli [Transport Layer Securityn (TLS) rekisteriasetukset](https://docs.microsoft.com/windows-server/security/tls/tls-registry-settings).
> 
> 

## <a name="how-to-restart-the-gateway"></a>Yhdyskäytävän uudelleenkäynnistys
Yhdyskäytävä toimii Windows-palveluna. Voit käynnistää ja pysäyttää sen kuten minkä tahansa Windows-palvelun. Voit tehdä tämän useilla tavoilla. Tässä kerrotaan, miten voit tehdä sen komentokehotteesta.

1. Tietokoneessa, jossa yhdyskäytävä on käynnissä, käynnistetään järjestelmänvalvojan komentokehote.
2. Käytä seuraavaa komentoa palvelun pysäyttämiseen.
   
   net stop PBIEgwService
3. Käytä seuraavaa komentoa palvelun käynnistämiseen.
   
   net start PBIEgwService

