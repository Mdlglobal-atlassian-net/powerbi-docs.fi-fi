## <a name="firewall-or-proxy"></a>Palomuuri tai välityspalvelin
Jos tarvitset tietoa siitä, miten välityspalvelintiedot annetaan yhdyskäytävää varten, katso [Välityspalvelinasetusten määrittäminen Power BI ‑yhdyskäytäviä varten](../service-gateway-proxy.md).

Voit testata, estääkö palomuurisi tai välityspalvelimesi yhteyksiä, suorittamalla PowerShell-komentoriviltä [Test-NetConnection](https://docs.microsoft.com/powershell/module/nettcpip/test-netconnection)-komennon. Se testaa yhdistettävyyden Azuren palveluväylään. Komento testaa vain verkon yhdistettävyyttä, eikä sillä ole mitään tekemistä pilvipalvelinpalvelun tai yhdyskäytävän kanssa. Se auttaa määrittämään, voiko koneesi muodostaa Internet-yhteyden.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Test-NetConnection-komento on käytettävissä vain Windows Server 2012 R2 ‑versiossa tai sitä uudemmissa versioissa. Se on myös käytettävissä Windows 8.1 ‑versiossa ja uudemmissa versioissa. Vanhemmissa käyttöjärjestelmäversiossa voit testata porttien yhdistettävyyden käyttämällä Telnetiä.
> 
> 

Tulosten pitäisi vastata seuraavaa esimerkkiä. TcpTestSucceeded-kohta saattaa poiketa esimerkistä. Jos **TcpTestSucceeded** ei ole *tosi*, palomuuri saattaa estää yhteyden.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Jos haluat olla perusteellinen, korvaa **ComputerName**- ja **Port**-arvot [porttien](../service-gateway-onprem.md#ports) luettelossa annetuilla arvoilla.

Palomuuri voi estää myös yhteydet, jotka Azuren palveluväylä muodostaa Azuren palvelinkeskuksiin. Tällaisessa tapauksessa lisää alueesi kyseisten palvelinkeskusten IP-osoitteet sallittujen luetteloon (poista esto). Näet luettelon Azuren IP-osoitteista [täältä](https://www.microsoft.com/download/details.aspx?id=41653).

