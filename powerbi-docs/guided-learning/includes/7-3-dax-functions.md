DAX sisältää runsaan joukon funktioita, joilla voit jäsentää, muotoilla ja analysoida tietojasi. Nämä funktiot voidaan jakaa muutamaan luokkaan:

* **koostamisfunktiot**
* **laskemisfunktiot**
* **loogiset funktiot**
* **tietofunktiot**
* **tekstifunktiot**
* **päivämääräfunktiot**.

Kun aloitat kaavan kirjoittamisen Power BI Desktopin **kaavariville**, näyttöön avautuu luettelo käytettävissä olevista funktioista, joista voit sitten valita haluamasi (kuten Excelissä). Näppäimistön **ylä-** ja **alanuolen** avulla voit korostaa käytettävissä olevia funktioita. Näin näet korostetun funktion kuvauksen.

Power BI näyttää funktiot, joiden nimet vastaavat tähän mennessä kirjoittamiasi kirjaimia. Jos siis kirjoitat *S*, näet luettelossa vain funktiot, joiden nimi alkaa *S*-kirjaimella. Jos kirjoitat *Su*, näet luettelossa vain funktiot, joiden nimi *sisältää* kirjainyhdistelmän *Su* (funktion ei tarvitse alkaa kirjaimilla *Su*, mutta nimen täytyy sisältää peräkkäiset kirjaimet s ja u).

![](media/7-3-dax-functions/dax-functions_1.png)

Tällä tavalla voit helposti etsiä Power BI:ssä käytettävissä olevia DAX-funktioita ja tutustua niihin. Kun aloitat funktion nimen kirjoittamisen, Power BI auttaa sinua löytämään funktion.

Nyt kun tiedämme, miten voimme aloittaa DAX-kaavan, voimme jatkaa tutustumaan eri funktioluokkiin.

## <a name="aggregation-functions"></a>Koostamisfunktiot
DAX sisältää lukuisia **koostamisfunktioita**, muun muassa seuraavat yleisesti käytetyt funktiot:

* SUM
* AVERAGE
* MIN
* MAX
* SUMX (ja muut *X*-funktiot).

Nämä funktiot toimivat vain numeerisissa sarakkeissa. Yleensä niillä voidaan koostaa kerrallaan vain yhtä saraketta.

**X**-kirjaimeen päättyviä erikoiskoostamisfunktioita (esimerkiksi **SUMX**), voi kuitenkin käyttää useissa sarakkeissa. Nämä funktiot toistetaan koko taulukossa, ja lauseke käsitellään jokaisella rivillä.

## <a name="counting-functions"></a>Laskemisfunktiot
DAX sisältää esimerkiksi seuraavat usein käytetyt **laskemisfunktiot**:

* COUNT
* COUNTA
* COUNTBLANK
* COUNTROWS
* DISTINCTCOUNT.

Ne laskevat eri asioita, esimerkiksi erillisiä arvoja, ei-tyhjiä arvoja ja taulukon rivejä.

## <a name="logical-functions"></a>Loogiset funktiot
DAX sisältää esimerkiksi seuraavat **loogiset** funktiot:

* AND
* OR
* NOT
* IF
* IFERROR.

Näitä erikoisfunktioita voi ilmaista myös *operaattoreilla*. Esimerkiksi **AND** voidaan kirjoittaa (ja korvata) DAX-kaavoissa muodossa **&&**.

Voit käyttää operaattoreita (esimerkiksi **&&**), kun tarvitset kaavaasi enemmän kuin kaksi ehtoa. Muissa tapauksissa suosittelemme itse funktion nimen (esimerkiksi **AND**) käyttöä DAX-koodin luettavuuden parantamiseksi.

## <a name="information-functions"></a>Tietofunktiot
DAX sisältää esimerkiksi seuraavat **tietofunktiot**:

* ISBLANK
* ISNUMBER
* ISTEXT
* ISNONTEXT
* ISERROR.

Vaikka näistä funktioista voikin olla silloin tällöin hyötyä, sinun kannattaa tietää sarakkeidesi tietotyypit jo etukäteen (sen sijaan, että tarkistat tietotyypin näiden funktioiden avulla).

DAX käyttää **MAX**- ja **MIN**-funktioita sekä arvojen *koostamiseen* että *vertailuun*.

## <a name="text-functions"></a>Tekstifunktiot
DAX sisältää esimerkiksi seuraavat **tekstifunktiot**:

* CONCATENTATE
* REPLACE
* SEARCH
* UPPER
* FIXED.

Nämä **tekstifunktiot** toimivat hyvin pitkälti samalla tavalla kuin samannimiset Excel-funktiot. Jos siis tunnet, miten Excel käsittelee tekstifunktioita, olet jo askeleen edellä. Jos et, kokeile rohkeasti näitä funktioita Power BI:ssä ja tutustu niiden toimintaan.

## <a name="date-functions"></a>Päivämääräfunktiot
DAX sisältää seuraavat **päivämääräfunktiot**:

* DATE
* HOUR
* NOW
* EOMONTH
* WEEKDAY.

Näillä funktioilla voit laskea ja hakea tietoja *päivämääräarvoista*, mutta ne eivät koske aikatieto, joissa käytetään päivämäärätaulukkoa.

> Videon sisällön on luonut [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit).
> 
> 

