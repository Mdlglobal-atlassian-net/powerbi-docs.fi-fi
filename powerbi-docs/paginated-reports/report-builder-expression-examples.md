---
title: Power BI:n raportin muodostimen lauseke-esimerkit
description: Lausekkeita käytetään usein Power BI:n raporttien muodostimella luoduissa raporteissa sisällön ja raportin ulkoasun hallintaan.
ms.date: 10/21/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 87ddb651-a1d0-4a42-8ea9-04dea3f6afa4
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 48e81c91a4555b4c8ea847ddffb1413058bbb152
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "78921144"
---
# <a name="expression-examples-in-power-bi-report-builder"></a>Power BI:n raportin muodostimen lauseke-esimerkit
Lausekkeita käytetään usein Power BI:n raporttien muodostimella luoduissa raporteissa sisällön ja raportin ulkoasun hallintaan. Lausekkeet kirjoitetaan Microsoft Visual Basicilla, ja niissä voidaan käyttää sisäisiä funktioita, mukautettua koodia, raportti- ja ryhmämuuttujia sekä käyttäjän määrittämiä muuttujia. Lausekkeet alkavat yhtäläisyysmerkillä (=).   

Tässä aiheessa on esimerkkejä lausekkeista, joita voidaan käyttää raporttien yleisissä toiminnoissa.  
  
-   [Visual Basic -funktiot](#VisualBasicFunctions) Päivämäärä-, merkkijono-, muunto- ja ehdollisten Visual Basic -funktioiden esimerkkejä.  
  
-   [Raporttifunktiot](#ReportFunctions) Koosteiden ja muiden sisäisten raporttifunktioiden esimerkkejä.  
  
-   [Raporttitietojen ulkoasu](#AppearanceofReportData) Esimerkkejä raportin ulkoasun muuttamisesta.  
  
-   [Ominaisuudet](#Properties) Esimerkkejä raporttikohteen muoto- tai näkyvyysominaisuuksien määrittämisestä.  
  
-   [Parametrit](#Parameters) Esimerkkejä parametrien käytöstä lausekkeessa.  
  
-   [Mukautettu koodi](#CustomCode) Esimerkkejä upotetusta mukautetusta koodista.  
  
Katso kohdasta [lausekkeet Power BI:n raportin muodostimessa](report-builder-expressions.md) yksinkertaisten ja monimutkaisten lausekkeiden lisätiedot, missä lausekkeita voidaan käyttää ja minkä tyyppisiä viittauksia voit sisällyttää lausekkeeseen. 
  
## <a name="functions"></a>Funktiot  
 Monet raporttien lausekkeet sisältävät funktioita. Voit muotoilla tietoja, soveltaa logiikkaa ja käyttää raportin metatietoja näiden funktioiden avulla. Voit kirjoittaa lausekkeita, joissa käytetään Microsoft Visual Basic -suorituskirjaston `xref:System.Convert` ja `xref:System.Math` -nimitilojen funktioita. Voit lisätä viittauksia funktioihin mukautettuna koodina. Voit käyttää myös Microsoft.NET Frameworkin luokkia, kuten `xref:System.Text.RegularExpressions`.  
  
##  <a name="visual-basic-functions"></a><a name="VisualBasicFunctions"></a> Visual Basic -funktiot  
 Visual Basic -funktioilla voit käsitellä tietoja, jotka näytetään tekstiruuduissa tai joita käytetään parametreissa, ominaisuuksissa tai raportin muissa alueissa. Tämä osio sisältää esimerkkejä joistain tällaisista funktioista. Katso lisätiedot kohdasta [Visual Basic Runtime -kirjaston jäsenet](https://go.microsoft.com/fwlink/?LinkId=198941) MSDN:ssä.  
  
 .NET Framework tarjoaa monia mukautettuja muotoiluasetuksia, kuten tarkat päivämäärämuodot. Katso lisätiedot [Muotoilutyypit](/dotnet/standard/base-types/formatting-types)-kohdasta.  
  
### <a name="math-functions"></a>Matemaattiset funktiot  
  
-   **Round**-funktion avulla voit pyöristää luvut lähimpään kokonaislukuun. Seuraava lauseke pyöristää 1,3:n 1:ksi:  
  
    ```  
    = Round(1.3)  
    ```  
  
     Voit myös kirjoittaa lausekkeen, joka pyöristää arvon määrittämäksesi kertoimeksi Excelin **MRound**-funktion tapaan. Kerro arvo kertoimella, joka tuottaa kokonaisluvun, pyöristä luku ja jaa sitten samalla kertoimella. Esimerkiksi 1,3 pyöristetään lähimpään 0,2-kertoimeen (1,4) seuraavalla lausekkeella:  
  
    ```  
    = Round(1.3*5)/5  
    ```  
  
###  <a name="date-functions"></a><a name="DateFunctions"></a> Päivämääräfunktiot  
  
-   **Today**-funktio antaa senhetkisen päivämäärän. Tätä lauseketta voidaan käyttää tekstiruudussa näyttämään raportin päivämäärä tai parametrissa suodattamaan tiedot senhetkisen päivämäärän perusteella.  
  
    ```  
    =Today()  
    ```  
  
-   **DateInterval**-funktion avulla voit eristää haluamasi päivämäärän osan. Seuraavassa on joitain kelvollisia **DateInterval** -parametreja:

    -   DateInterval.Second
    -   DateInterval.Minute
    -   DateInterval.Hour
    -   DateInterval.Weekday
    -   DateInterval.Day
    -   DateInterval.DayOfYear
    -   DateInterval.WeekOfYear
    -   DateInterval.Month
    -   DateInterval.Quarter
    -   DateInterval.Year

    Esimerkiksi tämä lauseke näyttää senhetkisen päivämäärän viikonnumeron kuluvana vuonna:
  
    ```  
    =DatePart(DateInterval.WeekOfYear, today()) 
    ```  
  
-   **DateAdd**-funktio mahdollistaa useiden, yksittäiseen parametriin perustuvien päivämäärävälien syöttämisen. Seuraava lauseke antaa päivämäärän, joka on kuuden kuukauden päässä *StartDate*-parametrin päivämäärästä.  
  
    ```  
    =DateAdd(DateInterval.Month, 6, Parameters!StartDate.Value)  
    ```  
  
-   **Year**-funktio näyttää tietyn päivämäärän vuoden. Voit käyttää tätä päivämäärien ryhmittelyyn tai vuoden näyttämiseen päivämääräjoukon otsikkona. Tämä lauseke antaa tiettyjä myyntitilausryhmän päivämääriä vastaavan vuoden. **Month**-funktiota ja muita funktioita voidaan käyttää myös päivämäärien muokkaamiseen. Katso lisätiedot Visual Basic -dokumentaatiosta.  
  
    ```  
    =Year(Fields!OrderDate.Value)  
    ```  
  
-   Voit mukauttaa muotoa yhdistämällä lausekkeen funktioita. Seuraava lauseke muuttaa kuukausi-päivä-vuosi-päivämäärämuodon kuukauden viikko-viikon numero -muotoon. Esimerkiksi 12/23/2009 muunnetaan muotoon Joulukuun viikko 3:  
  
    ```  
    =Format(Fields!MyDate.Value, "MMMM") & " Week " &   
    (Int(DateDiff("d", DateSerial(Year(Fields!MyDate.Value),   
    Month(Fields!MyDate.Value),1), Fields!FullDateAlternateKey.Value)/7)+1).ToString  
    ```  
  
     Kun tätä lauseketta käytetään tietojoukossa laskettuna kenttänä, voit koostaa tämän lausekkeen avulla arvot kunkin kuukauden viikon mukaan.  
  
-   Seuraava lauseke muotoilee SellStartDate-arvon muotoon KKK-VV. SellStartDate-kenttä on päivämäärä/aika-tietotyyppi.  
  
    ```  
    =FORMAT(Fields!SellStartDate.Value, "MMM-yy")  
    ```  
  
-   Seuraava lauseke muotoilee SellStartDate-arvon muotoon pp/KK/VVVV. SellStartDate-kenttä on päivämäärä/aika-tietotyyppi.  
  
    ```  
    =FORMAT(Fields!SellStartDate.Value, "dd/MM/yyyy")  
    ```  
  
-   **CDate**-funktio muuntaa arvon päivämääräksi. **Now**-funktio palauttaa päivämääräarvon, joka sisältää järjestelmän senhetkisen päivämäärän ja kellonajan. **DateDiff** palauttaa Long-arvon, joka määrittää kahden päivämääräarvon välisten aikavälien määrän.  
  
     Seuraava esimerkki näyttää senhetkisen vuoden alkamispäivämäärän  
  
    ```  
    =DateAdd(DateInterval.Year,DateDiff(DateInterval.Year,CDate("01/01/1900"),Now()),CDate("01/01/1900"))  
    ```  
  
-   Seuraava esimerkki näyttää edellisen kuukauden alkamispäivämäärän kuluvan kuukauden mukaan.  
  
    ```  
    =DateAdd(DateInterval.Month,DateDiff(DateInterval.Month,CDate("01/01/1900"),Now())-1,CDate("01/01/1900"))  
    ```  
  
-   Seuraava lauseke palauttaa funktioiden SellStartDate–LastReceiptDate väliset vuodet. Nämä kentät ovat kahdessa eri tietojoukossa: DataSet1 ja DataSet2.  
  
    ```  
    =DATEDIFF("yyyy", First(Fields!SellStartDate.Value, "DataSet1"), First(Fields!LastReceiptDate.Value, "DataSet2"))  
    ```  
  
-   **DatePart** -funktio palauttaa kokonaislukuarvon, joka sisältää valitun päivämääräarvon määritetyn osan. Seuraava lauseke palauttaa DataSet1-tietojoukon SellStartDate-funktion ensimmäisen arvon vuoden. Tietojoukon vaikutusalue on määritetty, koska raportissa on useita tietojoukkoja.  
  
    ```  
    =Datepart("yyyy", First(Fields!SellStartDate.Value, "DataSet1"))  
  
    ```  
  
-   **DateSerial**-funktio palauttaa päivämääräarvon, joka vastaa määritettyä vuotta, kuukautta ja päivää. Kellonajaksi määritetään keskiyö. Seuraava esimerkki näyttää edellisen kuukauden päättymispäivämäärän kuluvan kuukauden mukaan.  
  
    ```  
    =DateSerial(Year(Now()), Month(Now()), "1").AddDays(-1)  
    ```  
  
-   Seuraavat lausekkeet näyttävät eri päivämääriä käyttäjän määrittämän parametriarvon mukaan.  
  
|Esimerkkikuvaus|Esimerkki|  
|-------------------------|-------------|  
|Eilen|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-1)`|  
|Kaksi päivää sitten|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-2)`|  
|Kuukausi sitten|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-1,Day(Parameters!TodaysDate.Value))`|  
|Kaksi kuukautta sitten|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-2,Day(Parameters!TodaysDate.Value))`|  
|Vuosi sitten|`=DateSerial(Year(Parameters!TodaysDate.Value)-1,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
|Kaksi vuotta sitten|`=DateSerial(Year(Parameters!TodaysDate.Value)-2,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
  
###  <a name="string-functions"></a><a name="StringFunctions"></a> Merkkijonofunktiot  
  
-   Yhdistä useita kenttiä ketjutusoperaattoreilla ja Visual Basic -vakioilla. Seuraava lauseke palauttaa kaksi kenttää, jotka ovat samassa tekstiruudussa omilla riveillään:  
  
    ```  
    =Fields!FirstName.Value & vbCrLf & Fields!LastName.Value   
    ```  
  
-   Muotoile merkkijonon päivämääriä ja numeroita **Format**-funktiolla. Seuraava lauseke näyttää *StartDate*- ja *EndDate*-parametrien arvot pitkässä päivämäärämuodossa:  
  
    ```  
    =Format(Parameters!StartDate.Value, "D") & " through " &  Format(Parameters!EndDate.Value, "D")    
    ```  
  
     Jos tekstiruutu sisältää vain päivämäärän tai luvun, aseta muotoilu tekstiruudun Muotoilu-ominaisuuden avulla tekstiruudun sisäisen **Format**-funktion sijaan.  
  
-   **Right**, **Len** ja **InStr** ovat hyödyllisiä funktioita alimerkkijonon palauttamiseen. Esimerkiksi *DOMAIN*\\*username* rajataan ainoastaan käyttäjänimeen. Seuraava lauseke palauttaa *User*-parametrista kenoviivan oikealla puolella sijaitsevan merkkijonon osan (\\):  
  
    ```  
    =Right(Parameters!User.Value, Len(Parameters!User.Value) - InStr(Parameters!User.Value, "\"))  
    ```  
  
     Seuraava lauseke tuottaa saman arvon kuin edellinenkin lauseke .NET Framework -jäsenten `xref:System.String`-luokan avulla (Visual Basic -funktioiden asemesta):  
  
    ```  
    =Parameters!User.Value.Substring(Parameters!User.Value.IndexOf("\")+1, Parameters!User.Value.Length-Parameters!User.Value.IndexOf("\")-1)  
    ```  
  
-   Näytä valitut moniarvoisen parametrin arvot. Seuraavassa esimerkissä **Join**-funktiota on käytetty parametrin *MySelection* valittujen arvojen ketjuttamisessa yksittäiseksi merkkijonoksi, joka voidaan määrittää lausekkeeksi raporttikohteen tekstiruudussa:  
  
    ```  
    = Join(Parameters!MySelection.Value)  
    ```  
  
     Seuraava esimerkki tekee saman kuin yllä oleva esimerkki, ja lisäksi se näyttää tekstimerkkijonon ennen valittujen arvojen luetteloa.  
  
    ```  
    ="Report for " & JOIN(Parameters!MySelection.Value, " & ")  
  
    ```  
  
-   .NET Framework `xref:System.Text.RegularExpressions`:n **Regex**-funktiot ovat tehokas tapa muuttaa olemassa olevien merkkijonojen muotoa. Tällaisia merkkijonoja ovat esimerkiksi puhelinnumerot. Seuraavassa lausekkeessa **Replace**-funktion avulla kentässä oleva kymmennumeroinen puhelinnumero muutetaan muodosta "*nnn*-*nnn*-*nnnn*" muotoon "(*nnn*) *nnn*-*nnnn*":  
  
    ```  
    =System.Text.RegularExpressions.Regex.Replace(Fields!Phone.Value, "(\d{3})[ -.]*(\d{3})[ -.]*(\d{4})", "($1) $2-$3")  
    ```  
  
    > [!NOTE]  
    >  Varmista, että Fields!Phone-arvo ei sisällä välilyöntejä ja että sen tyyppi on `xref:System.String`.  
  
### <a name="lookup"></a>Haku  
  
-   Kun olet määrittänyt avainkentän, voit noutaa **Lookup**-funktiolla tietojoukosta yksi-yhteen-suhteen arvon, esimerkiksi avain-arvoparin. Seuraava lauseke näyttää tietojoukon (”Tuote”) tuotenimen, jos tuotetunnus vastaa seuraavaa:  
  
    ```  
    =Lookup(Fields!PID.Value, Fields!ProductID.Value, Fields.ProductName.Value, "Product")  
    ```  
  
### <a name="lookupset"></a>LookupSet  
  
-   Kun olet määrittänyt avainkentän, voit noutaa **LookupSet**-funktiolla tietojoukosta yksi-moneen-suhteen arvon. Jollakulla voi olla esimerkiksi useita puhelinnumeroita. Seuraavassa esimerkissä oletetaan, että PhoneList-tietojoukon kukin rivi sisältää henkilön tunnuksen ja puhelinnumeron. **LookupSet** palauttaa useita arvoja. Seuraava lauseke yhdistää palautettavat arvot yksittäiseksi merkkijonoksi ja näyttää ContactID-funktion määrittämän henkilön puhelinnumeroiden luettelon:  
  
    ```  
    =Join(LookupSet(Fields!ContactID.Value, Fields!PersonID.Value, Fields!PhoneNumber.Value, "PhoneList"),",")  
    ```  
  
###  <a name="conversion-functions"></a><a name="ConversionFunctions"></a> Muuntofunktiot  
 Visual Basic -funktioiden avulla voit muuntaa kentän tietotyypistä toiseen. Muuntofunktioiden avulla kentän oletustietotyyppi voidaan muuntaa laskutoimituksiin tai tekstin yhdistämiseen vaadituksi tietotyypiksi.  
  
-   Seuraava lauseke muuntaa vakion 500 Decimal-tyyppiseksi, jotta sitä voidaan verrata Transact-SQL -rahatietotyyppiin suodatinlausekkeen Arvo-kentässä.  
  
    ```  
    =CDec(500)  
    ```  
  
-   Seuraava lauseke näyttää moniarvoisen *MySelection*-parametrin valittujen arvojen määrän.  
  
    ```  
    =CStr(Parameters!MySelection.Count)  
    ```  
  
###  <a name="decision-functions"></a><a name="DecisionFunctions"></a> Päätösfunktiot  
  
-   **Iif**-funktio palauttaa kaksi arvoa sen mukaan, onko lauseke tosi vai epätosi. Seuraavassa lausekkeessa **Iif**-funktio palauttaa totuusarvon **Tosi**, jos arvon (`LineTotal`) on yli 100. Muussa tapauksessa se palauttaa arvon **Epätosi**:  
  
    ```  
    =IIF(Fields!LineTotal.Value > 100, True, False)  
    ```  
  
-   Voit käyttää useita **IIF**-funktioita (sisäkkäisiä IIF-funktioita) palauttaaksesi yhden kolmesta arvosta `PctComplete`:n arvon mukaan. Seuraava lauseke voidaan sijoittaa tekstiruudun täyttöväriin, jolloin taustaväri muuttuu tekstiruudussa annetun arvon mukaan.  
  
    ```  
    =IIF(Fields!PctComplete.Value >= 10, "Green", IIF(Fields!PctComplete.Value >= 1, "Blue", "Red"))  
    ```  
  
     10 ja sen ylittävät arvot tekevät taustasta vihreän, 1–9 sinisen ja alle 1:n arvot punaisen.  
  
-   **Switch**-funktio on toinen tapa tuottaa sama toiminnallisuus. **Switch**-funktio on kätevä, kun haluat testata kolmea tai useampaa ehtoa. **Switch**-funktio palauttaa ensimmäiseen lausekkeeseen liittyvän arvon sarjassa, joka antaa tulokseksi Tosi:  
  
    ```  
    =Switch(Fields!PctComplete.Value >= 10, "Green", Fields!PctComplete.Value >= 1, "Blue", Fields!PctComplete.Value = 1, "Yellow", Fields!PctComplete.Value <= 0, "Red")  
    ```  
  
     10 ja sen ylittävät arvot tekevät taustasta vihreän, 1–9 sinisen ja alle 1:n arvot keltaisen. 0 ja sen alittavat arvot tekevät taustasta punaisen.  
  
-   Testaa `ImportantDate`-kentän arvo ja palauta Punainen, jos se on yli viikon vanha, ja muissa tapauksissa Sininen. Tällä lausekkeella voidaan hallita raporttikohteen tekstiruudun Väri-ominaisuutta:  
  
    ```  
    =IIF(DateDiff("d",Fields!ImportantDate.Value, Now())>7,"Red","Blue")  
    ```  
  
-   Testaa `PhoneNumber`-kentän arvoa ja palauta "Ei arvoa" jos se on **tyhjäarvo** (**Ei mitään** Visual Basicissa); muussa tapauksessa palauta puhelinnumeroarvo. Tällä lausekkeella voidaan hallita raporttikohteen tekstiruudun arvoa.  
  
    ```  
    =IIF(Fields!PhoneNumber.Value Is Nothing,"No Value",Fields!PhoneNumber.Value)  
    ```  
  
-   Testaa `Department`-kentän arvo ja palauta joko aliraportin nimi tai **tyhjäarvo** (**Ei mitään** Visual Basicissa). Tätä lauseketta voi käyttää aliraporttien ehdolliseen poraamiseen.  
  
    ```  
    =IIF(Fields!Department.Value = "Development", "EmployeeReport", Nothing)  
    ```  
  
-   Testaa, onko kentän arvo nolla. Tällä lausekkeella voidaan hallita raporttikohteen kuvan **Piilotettu**-ominaisuutta. Seuraavassa esimerkissä [LargePhoto]-kentän määrittämä kuva näkyy vain, jos kentän arvo ei ole tyhjäarvo.  
  
    ```  
    =IIF(IsNothing(Fields!LargePhoto.Value),True,False)  
    ```  
  
-   **MonthName**-funktio palauttaa merkkijonoarvon, joka sisältää määritetyn kuukauden nimen. Seuraavassa esimerkissä kuukausikentässä näkyy NA, kun kentän sisältämä arvo on 0.  
  
    ```  
    IIF(Fields!Month.Value=0,"NA",MonthName(IIF(Fields!Month.Value=0,1,Fields!Month.Value)))  
  
    ```  
  
##  <a name="report-functions"></a><a name="ReportFunctions"></a> Raporttifunktiot  
 Voit lisätä lausekkeessa viitteen raportin lisäfunktioihin, jotka käsittelevät raportin tietoja. Tässä osiossa annetaan esimerkkejä kahdesta tällaisesta funktiosta. 
  
###  <a name="sum"></a><a name="Sum"></a> Summa  
  
-   **Sum**-funktio laskee yhteen ryhmän tai tietoalueen arvot. Tämä funktio on kätevä ryhmän otsikossa tai alatunnisteessa. Seuraava lauseke näyttää Tilaus-ryhmän tai -tietoalueen tietojen summan:  
  
    ```  
    =Sum(Fields!LineTotal.Value, "Order")  
    ```  
  
-   Voit myös käyttää **Sum**-funktiota ehdollisiin koostelaskutoimituksiin. Jos tietojoukko sisältää esimerkiksi kentän, jonka nimi on Tila ja jonka mahdolliset arvot ovat Ei aloitettu, Aloitettu, Valmis, ryhmän otsikkoon asetettuna seuraava lauseke laskee vain Valmis-arvon koostetun summan:  
  
    ```  
    =Sum(IIF(Fields!State.Value = "Finished", 1, 0))  
    ```  
  
###  <a name="rownumber"></a><a name="RowNumber"></a> RowNumber  
  
-   Tietoalueessa käytettynä **RowNumber**-funktio näyttää kunkin lausekkeen sisältämän tekstiruutuesiintymän rivin numeron. Tämä toiminto voi auttaa taulukon rivien numeroimisessa. Siitä voi olla hyötyä myös monimutkaisemmissa tehtävissä, kuten rivien määrään perustuvien sivunvaihtojen antamisessa. Katso lisätiedot tämän aiheen kohdasta [Sivunvaihdot](#PageBreaks).  
  
     Voit määrittää **RowNumber**-hallinnan laajuuden, kun numerointi alkaa uudelleen. **Ei mitään** -avainsana ilmaisee, että funktio alkaa laskea uloimman tietoalueen ensimmäisestä tietorivistä. Voit aloittaa sisäkkäisten tietoalueiden sisäisen laskemisen tietoalueen nimen avulla. Voit aloittaa ryhmän sisäisen laskemisen käyttämällä ryhmän nimeä.  
  
    ```  
    =RowNumber(Nothing)  
    ```  
  
##  <a name="appearance-of-report-data"></a><a name="AppearanceofReportData"></a> Raporttitietojen ulkoasu  
 Lausekkeiden avulla voit muuttaa sitä, miten tiedot näkyvät raportissa. Voit esimerkiksi näyttää kahden kentän arvot yhdessä tekstiruudussa, näyttää raporttia koskevia tietoja tai hallita sitä, miten sivunvaihdot lisätään raporttiin.  
  
###  <a name="page-headers-and-footers"></a><a name="PageHeadersandFooters"></a> Sivun otsikot ja alatunnisteet  
 Kun suunnittelet raporttia, haluat ehkä näyttää raportin nimen ja sivunumeron raportin alatunnisteessa. Voit tehdä tämän seuraavien lausekkeiden avulla:  
  
-   Seuraava lauseke antaa raportin nimen ja sen suorittamisen kellonajan. Se voidaan sijoittaa raportin alatunnisteeseen tekstiruutuun tai raportin leipätekstiin. Ajan muoto määrätään .NET Frameworkin lyhyen päivämäärän muotoilumerkkijonolla:  
  
    ```  
    =Globals.ReportName & ", dated " & Format(Globals.ExecutionTime, "d")  
    ```  
  
-   Raportin alatunnisteeseen tekstiruutuun asetettuna seuraava lauseke antaa sivunumeron ja raportin kokonaissivumäärän:  
  
    ```  
    =Globals.PageNumber & " of " & Globals.TotalPages  
    ```  
  
 Seuraavissa esimerkeissä kuvataan, miten sivun ensimmäinen ja viimeinen arvo näytetään sivun otsikossa. Rakenne muistuttaa hakemistoluetteloa. Esimerkissä oletetaan, että käytössä on muokkausruudun `LastName` sisältävä tietoalue.  
  
-   Sivun otsikon vasemmalle puolelle tekstiruutuun sijoitettuna seuraava lauseke antaa `LastName`-tekstiruudun ensimmäisen arvon sivulla:  
  
    ```  
    =First(ReportItems("LastName").Value)  
    ```  
  
-   Sivun otsikon oikealle puolelle tekstiruutuun sijoitettuna seuraava lauseke antaa `LastName`-tekstiruudun ensimmäisen arvon sivulla:  
  
    ```  
    =Last(ReportItems("LastName").Value)  
    ```  
  
 Seuraavassa esimerkissä kuvataan sivujen kokonaismäärän näyttäminen. Esimerkissä oletetaan, että käytössä on muokkausruudun `Cost` sisältävä tietoalue.  
  
-   Sivun otsikkoon tai alatunnisteeseen sijoitettuna seuraava lauseke antaa `Cost`-tekstiruudun arvojen summan sivulla:  
  
    ```  
    =Sum(ReportItems("Cost").Value)  
    ```  
  
> [!NOTE]  
>  Voit viitata vain yhteen sivun otsikon tai alatunnisteen raporttikohteeseen lauseketta kohti. Voit myös viitata tekstiruudun nimeen, mutta et todellisiin tekstiruudun, sivun otsikon ja alatunnisteen lausekkeiden sisäiseen tietolausekkeeseen.  
  
###  <a name="page-breaks"></a><a name="PageBreaks"></a> Sivunvaihdot  
 Joissain raporteissa haluat ehkä sijoittaa sivunvaihdon määritetyn rivimäärän loppuun ryhmien tai raporttikohteiden lopussa olevien sivunvaihtojen sijaan tai niiden lisäksi. Voit tehdä tämän luomalla ryhmän, joka sisältää haluamiasi ryhmiä tai tietueita, lisäämällä sivunvaihdon ryhmään ja lisäämällä sitten ryhmälausekkeen ryhmään määritetyn rivimäärän mukaan.  
  
-   Ryhmälausekkeeseen sijoitettuna seuraava lauseke määrittää numeron joka 25. riville. Kun ryhmälle on määritetty sivunvaihto, tämä lauseke tuottaa sivunvaihdon 25 rivin välein.  
  
    ```  
    =Ceiling(RowNumber(Nothing)/25)  
    ```  
  
     Jotta käyttäjä voi asettaa sivulla näytettävien rivien määrän, luo parametri `RowsPerPage` ja perusta parametrille ryhmälauseke seuraavan lausekkeen mukaisesti:  
  
    ```  
    =Ceiling(RowNumber(Nothing)/Parameters!RowsPerPage.Value)  
    ```  
  
##  <a name="properties"></a><a name="Properties"></a> Ominaisuudet  
 Lausekkeita ei käytetä vain tietojen näyttämiseen tekstiruuduissa. Niiden avulla voidaan myös muuttaa sitä, miten ominaisuuksia käytetään raporttikohteissa. Voit muuttaa raporttikohteen tyylin tietoja tai muuttaa sen näkyvyyttä.  
  
###  <a name="formatting"></a><a name="Formatting"></a> Muotoilu  
  
-   Tekstiruudun Väri-ominaisuudessa käytettynä seuraava lauseke muuttaa tekstin väriä `Profit`-kentän arvon mukaan:  
  
    ```  
    =Iif(Fields!Profit.Value < 0, "Red", "Black")  
    ```  
  
     Voit käyttää myös Visual Basic -objektimuuttujaa `Me`. Muuttuja on vaihtoehtoinen tapa viitata tekstiruudun arvoon.  
  
     `=Iif(Me.Value < 0, "Red", "Black")`  
  
-   Tietoalueeseen sisältyvän raporttikohteen BackgroundColor-ominaisuudessa käytettynä seuraava lauseke vaihtelee rivien taustaväriä vaaleanvihreän ja valkoisen välillä:  
  
    ```  
    =Iif(RowNumber(Nothing) Mod 2, "PaleGreen", "White")  
    ```  
  
     Jos käytät lauseketta tiettyyn laajuuteen, sinun on ehkä ilmaistava koostefunktion tietojoukko:  
  
    ```  
    =Iif(RowNumber("Employees") Mod 2, "PaleGreen", "White")  
    ```  
  
> [!NOTE]  
>  Käytettävissä olevat värit ovat peräisin .NET Frameworkin KnownColor-luetteloinnista.  
  
### <a name="chart-colors"></a>Kaaviovärit  
 Voit määrittää Muoto-kaavion värit mukautetulla koodilla, jonka avulla voit hallita värien ja tietopistearvojen liitosta. Näin voit käyttää yhtenäisiä värejä useissa kaavioissa, joissa on samat luokkaryhmät. 
  
###  <a name="visibility"></a><a name="Visibility"></a> Näkyvyys  
 Voit näyttää tai piilottaa raportin kohteita raporttikohteen näkyvyysominaisuuksien avulla. Voit piilottaa taulukon tai muun tietoalueen tietorivit aluksi lausekkeen arvon perusteella.  
  
-   Ryhmän tietorivien alkunäkyvyyteen käytettynä seuraava lauseke näyttää kaikki 90 prosenttia ylittävät tietorivit `PctQuota`-kentässä:  
  
    ```  
    =Iif(Fields!PctQuota.Value>.9, False, True)  
    ```  
  
-   Taulukon Piilotettu-ominaisuuteen asetettuna seuraava lauseke näyttää taulukon vain, jos siinä on yli 12 riviä:  
  
    ```  
    =IIF(CountRows()>12,false,true)  
    ```  
  
-   Sarakkeen **Piilotettu**-ominaisuuteen asetettuna seuraava lauseke näyttää sarakkeen vain, jos kenttä on olemassa raportin tietojoukossa sen jälkeen, kun tiedot on noudettu tietolähteestä:  
  
    ```  
    =IIF(Fields!Column_1.IsMissing, true, false)  
    ```  
  
###  <a name="urls"></a><a name="Hyperlinks"></a> URL-osoitteet  
 Voit mukauttaa URL-osoitteita raporttitietojen avulla. Voit myös hallita ehdollisesti, lisätäänkö URL-osoitteet tekstiruudun toiminnoiksi.  
  
-   Tekstiruudun toimintona käytettynä seuraava lauseke luo mukautetun URL-osoitteen, joka määrittää tietojoukon kentän `EmployeeID` URL-parametriksi.  
  
    ```  
    ="https://adventure-works/MyInfo?ID=" & Fields!EmployeeID.Value  
    ```  
  
-   Seuraava lauseke määrittää ehdollisesti, lisätäänkö URL-osoite tekstiruutuun. Tämä lauseke on riippuvainen parametrista `IncludeURLs`, jonka avulla käyttäjä voi päättää, lisätäänkö aktiiviset URL-osoitteet raporttiin. Tämä lauseke on määritetty tekstiruudun toiminnoksi. Voit viedä raportin Microsoft Excel -muodossa ilman hyperlinkkejä määrittämällä parametrin arvoksi Epätosi ja sitten tarkastelemalla raporttia.  
  
    ```  
    =IIF(Parameters!IncludeURLs.Value,"https://adventure-works.com/productcatalog",Nothing)  
    ```  
  
##  <a name="report-data"></a><a name="ReportData"></a> Raporttitiedot  
 Lausekkeita voidaan käyttää raportissa käytettyjen tietojen käsittelyyn. Voit viitata parametreihin ja muihin raporttitietoihin. Voit myös muuttaa kyselyä, jota käytetään raportin tietojen noutamiseen.  
  
###  <a name="parameters"></a><a name="Parameters"></a> Parametrit  
 Voit muuttaa parametrin oletusarvoa käyttämällä lausekkeita parametrissa. Voit esimerkiksi käyttää parametria tietojen suodattamiseen tietyn, raportin suorittamiseen käytetyn käyttäjätunnuksen mukaan.  
  
-   Parametrin oletusarvona käytettynä seuraava lauseke kerää raportin suorittavan käyttäjän käyttäjätunnuksen:  
  
    ```  
    =User!UserID  
    ```  
  
-   Voit viitata kyselyparametrin, suodatinlausekkeen, tekstiruudun tai raportin muun alueen parametriin, yleisellä **Parametrit**-kokoelmalla. Tässä esimerkissä oletetaan, että parametrin nimi on *Osasto*:  
  
    ```  
    =Parameters!Department.Value  
    ```  
  
-   Parametrit voidaan luoda raportissa ja asettaa piilotetuksi. Kun raportti suoritetaan raporttipalvelimessa, parametri ei näy työkalurivillä ja raportin lukija ei voi muuttaa oletusarvoa. Voit käyttää piilotettuja parametreja mukautetun vakion oletusarvon asettamiseen. Voit käyttää tätä arvoa missä tahansa lausekkeessa, mukaan lukien kenttälausekkeissa. Seuraava lauseke tunnistaa *ParameterField*-parametrin oletusparametriarvon osoittaman kentän:  
  
    ```  
    =Fields(Parameters!ParameterField.Value).Value  
    ```  
  
##  <a name="custom-code"></a><a name="CustomCode"></a> Mukautettu koodi  
 Voit käyttää mukautettua koodia upotettuna raporttiin. 
  
### <a name="using-group-variables-for-custom-aggregation"></a>Ryhmän muuttujien käyttäminen mukautettuun koostamiseen  
 Voit valmistella tiettyyn ryhmän laajuuteen liittyvän ryhmämuuttujan arvon ja sisällyttää lausekkeisiin viittauksen kyseiseen muuttujaan. Voit käyttää mukautettua koodia sisältävän ryhmän muuttujaa esimerkiksi mukautetun koosteen toteuttamiseen. 
  
## <a name="suppressing-null-or-zero-values-at-run-time"></a>Tyhjäarvojen ja nolla-arvojen poissulkeminen suorituksen aikana  
 Jotkut lausekkeen arvot saattavat tuottaa tyhjäarvon tai määrittämättömän arvon raporttia käsiteltäessä. Tämä saattaa johtaa suorituksenaikaisiin virheisiin ja **#Error**-virhesanoman näyttämiseen tekstiruudussa arvioitujen lausekkeiden sijaan. **IIF**-funktio on erityisen herkkä, koska If-Then-Else-lausekkeesta poiketen **IIF**-lausekkeen jokainen osa (mukaan lukien funktiokutsut) arvioidaan ennen kuin ne siirretään **Tosi**- ja **Epätosi**-testausrutiiniin. Lauseke `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` luo **#Error**-virhesanoman hahmonnettuun raporttiin, jos `Fields!Sales.Value`:n arvo on EI MITÄÄN.  
  
 Voit välttää tämän seuraavilla keinoilla:  
  
-   Aseta osoittajaksi 0 ja nimittäjäksi 1, jos kentän B arvo on 0 tai määrittämätön. Muussa tapauksessa aseta osoittajaksi kentän A arvo ja nimittäjäksi kentän B arvo.  
  
    ```  
    =IIF(Field!B.Value=0, 0, Field!A.Value / IIF(Field!B.Value =0, 1, Field!B.Value))  
    ```  
  
-   Mukautettu koodi -funktion avulla voit palauttaa lausekkeen arvon. Seuraava esimerkki palauttaa nykyisen arvon ja edellisen arvon välisen prosentuaalisen erotuksen. Tämän avulla voit laskea kahden peräkkäisen arvon välisen eron ja käsitellä ensimmäisen vertailun reunatapauksen (kun edellistä arvoa ei ole) sekä tapaukset, joissa edellinen tai nykyinen arvo on **tyhjäarvo** (**Ei mitään** Visual Basicissa).  
  
    ```  
    Public Function GetDeltaPercentage(ByVal PreviousValue, ByVal CurrentValue) As Object  
        If IsNothing(PreviousValue) OR IsNothing(CurrentValue) Then  
            Return Nothing  
        Else if PreviousValue = 0 OR CurrentValue = 0 Then  
            Return Nothing  
        Else   
            Return (CurrentValue - PreviousValue) / CurrentValue  
        End If  
    End Function  
    ```  
  
     Seuraavasta lausekkeesta ilmenee, miten voit kutsua tämän mukautetun koodin ColumnGroupByYear-säilön tekstiruudusta (ryhmä tai tietoalue).  
  
    ```  
    =Code.GetDeltaPercentage(Previous(Sum(Fields!Sales.Value),"ColumnGroupByYear"), Sum(Fields!Sales.Value))  
    ```  
  
     Tämä auttaa välttämään poikkeuksia suorituksen aikana. Voit nyt käyttää lauseketta, kuten `=IIF(Me.Value < 0, "red", "black")`, tekstiruudun **Väri**-ominaisuuteen. Näin voit näyttää tekstiä ehdollisesti sen mukaan, ovatko arvot suurempia tai pienempiä kuin 0.  
  
## <a name="next-steps"></a>Seuraavat vaiheet

- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
  
