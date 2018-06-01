## <a name="update-to-the-latest-version"></a>Päivitä uusimpaan versioon
Ongelmia voi esiintyä paljon, jos yhdyskäytävän versio on vanhentunut.  Hyvä yleinen käytäntö on varmistaa, että käytät aina uusinta versiota.  Jos et ole päivittänyt yhdyskäytävää ainakaan kuukauteen, sinun kannattaa harkita yhdyskäytävän uusimman version asentamista ja kokeilla ongelman toistamista.

## <a name="common-issues"></a>Yleisiä ongelmia
Seuraavassa on joitakin yleisiä ongelmia ja ratkaisuja, joista on ollut apua useille asiakkaille ympäristöissä, jotka rajoittavat internetin käyttöä.

<iframe width="560" height="315" src="https://www.youtube.com/embed/-t7RO6mHATI?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="authentication-to-proxy-server"></a>Välityspalvelimen todennus
Välityspalvelin voi vaatia todennuksen toimialueen käyttäjätililtä. Oletusarvoisesti yhdyskäytävä käyttää palvelun SID-tunnusta Windows-palveluun kirjautuvalle käyttäjälle. Kirjautuvan käyttäjän muuttamisesta toimialueen käyttäjäksi voi olla tässä apua. Katso lisätietoja ohjeaiheesta [Yhdyskäytävän palvelutilin muuttaminen toimialueen käyttäjäksi](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

### <a name="your-proxy-only-allows-ports-80-and-443-traffic"></a>Välityspalvelimesi sallii liikenteen vain porteille 80 ja 443
Jotkin välityspalvelimet rajaavat liikenteen vain porteille 80 ja 443. Oletusarvoisesti viestintä Azuren palveluväylään tapahtuu muiden porttien kautta kuin portin 443.

Voit pakottaa yhdyskäytävän vaihtamaan tietoja Azuren palveluväylän kanssa HTTPS-yhteydellä suoran TCP-yhteyden sijaan. Tämä edellyttää tiedoston *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* muokkaamista. Muuta arvo `AutoDetect` arvoksi `Https`. Tämä tiedosto löytyy oletusarvoisesti sijainnista *C:\Program Files\On-premises data gateway*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="installation"></a>Asennus
### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Virhe: Käyttäjän lisääminen ryhmään epäonnistui.  (-2147463168   PBIEgwService   Performance Log Users   )
Voit saada tämän virheviestin, jos yrität asentaa yhdyskäytävää toimialueen ohjauskoneeseen. Toimialueen ohjauskoneen käyttöönottoa ei tueta. Sinun on otettava yhdyskäytävä käyttöön koneella, joka ei ole toimialueen ohjauskone.

