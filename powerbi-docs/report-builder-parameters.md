---
title: Raporttiparametrit Power BI:n raportin muodostimessa
description: Tässä aiheessa kuvataan Power BI:n sivutetun raportin muodostimen raporttiparametrien yleisiä käyttötarkoituksia, määritettäviä ominaisuuksia ja paljon muuta.
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.custom: ''
ms.date: 06/06/2019
ms.openlocfilehash: d31036676a5960f7f6eb0f346c2c02ab979ff9bc
ms.sourcegitcommit: 01de0b01f66f28ca45b8d309d7864f261d6c9a85
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/16/2019
ms.locfileid: "74128432"
---
# <a name="report-parameters-in-power-bi-report-builder"></a>Raporttiparametrit Power BI:n raportin muodostimessa

Tässä aiheessa kuvataan Power BI:n sivutetun raportin muodostimen raporttiparametrien yleisiä käyttötarkoituksia, määritettäviä ominaisuuksia ja paljon muuta. Raporttiparametrien avulla voit hallita raportin tietoja, yhdistää toisiinsa liittyviä raportteja ja muuttaa raportin esitystapaa. Voit käyttää raporttiparametreja Raportin muodostimessa luoduissa sivutetuissa raporteissa.

## <a name="bkmk_Common_Uses_for_Parameters"></a> Raporttiparametrien yleiset käyttötarkoitukset

 Alla on joitakin yleisiä parametrien käyttötapoja.  
  
**Sivutettujen raporttien tietojen hallinta**
  
- Suodata sivutettujen raporttien tietoja tietolähteessä kirjoittamalla muuttujia sisältäviä tietojoukkokyselyjä.  
  
- Salli käyttäjien muokata sivutetun raportin tietoja määrittämällä arvoja. Voit esimerkiksi määrittää myyntitietojen alkamis- ja päättymispäivän kahden parametrin avulla.  
  
**Raportin esitystavan muuttaminen**
  
- Salli käyttäjien osallistua raportin ulkoasun muokkaamiseen määrittämällä arvoja. Esimerkiksi totuusarvoparametrin avulla voit määrittää, laajennetaanko tai kutistetaanko kaikki taulukon sisäkkäiset riviryhmät.  
  
- Salli käyttäjien muokata raportin tietoja ja ulkoasua lisäämällä parametreja lausekkeisiin.  
  
## <a name="UserInterface"></a> Parametreja sisältävän raportin tarkastelu

Kun tarkastelet raporttia, jossa on parametreja, raporttien katseluohjelman työkalurivi näyttää jokaisen parametrin, joten voit määrittää arvot vuorovaikutteisesti. Seuraavassa kuvassa on raportin parametrialue, jossa on parametrit @ReportMonth, @ReportYear, @EmployeeID, @ShowAll, @ExpandTableRows, @CategoryQuota ja @SalesDate.  

![Parametreja sisältävän raportin tarkastelu](media/report-builder-parameters/report-builder-parameters-power-bi-service.png "Parametreja sisältävän raportin tarkastelu")
  
1. **Parametrit-ruutu** Raporttien katseluohjelman työkalurivi näyttää kehotteen ja kunkin parametrin oletusarvon. Voit mukauttaa parametrien asettelua parametriruudussa.  
  
2. **@SalesDate parametri** Parametrin@SalesDate tietotyyppi on **päivämäärä/aika**. Päivämäärän/ajan valintakehote näkyy tekstiruudun vieressä. Jos haluat muokata päivämäärää, kirjoita uusi päivämäärä tekstiruutuun tai käytä kalenterin ohjausobjektia.  
  
3. **@ShowAll parametri** Parametrin@ShowAll tietotyyppi on **totuusarvo**. Valintapainikkeiden avulla voit määrittää arvoksi **Tosi** tai **Epätosi**.  
  
4. **Parametrialueen kahvan näyttäminen/piilottaminen** Napsauta raportin katseluohjelman työkalurivin nuolta, jos haluat näyttää tai piilottaa parametrit-ruudun.  
  
5. **@CategoryQuota parametri** Parametrin@CategoryQuota tietotyyppi on **liukuluku**, joten sille annetaan numeerinen arvo.  @CategoryQuota sallii useita arvoja.  
  
6. **Näytä raportti** Kun lisäät parametriarvoja, suorita raportti valitsemalla **Näytä raportti**. Jos kaikilla parametreilla on oletusarvot, raportti suoritetaan automaattisesti ensimmäisellä näyttökerralla.  
  
## <a name="bkmk_Create_Parameters"></a> Parametrien luominen

Voit luoda raporttiparametreja muutamalla eri tavalla.
  
> [!NOTE]
>  Kaikki tietolähteet eivät tue parametreja.
  
**Parametreja sisältävä tietojoukon kysely tai tallennettu toimintosarja**
  
 Lisää muuttujia sisältävä tietojoukkokysely tai syöteparametreja sisältävä tietojoukon tallennettu toimintosarja. Kullekin muuttujalle sekä syöteparametrille luodaan tietojoukkoparametri ja kullekin tietojoukkoparametrille raporttiparametri.  
  
![Report Builder -parametritietojoukon ominaisuudet](media/report-builder-parameters/report-builder-parameter-dataset.png "Report Builder -parametritietojoukon ominaisuudet")

  
 Raportin muodostimen kuvassa näytetään:  
  
1.  Raporttiparametrit Raporttitietoruudussa.  
  
2.  Parametreja sisältävä tietojoukko.  
  
3.  Parametriruutu.  
  
4.  Tietojoukon ominaisuudet -valintaikkunassa luetteloidut parametrit.  
  
**Parametrin luominen manuaalisesti**
  
Luo parametri manuaalisesti raporttitietoruudusta. Voit määrittää raporttiparametrit siten, että käyttäjä voi syöttää vuorovaikutteisesti arvoja, joiden avulla raportin sisältöä tai ulkoasua voidaan muokata. Voit myös määrittää raporttiparametrit niin, että käyttäjä ei voi muuttaa esimääritettyjä tietoja.  
  
> [!NOTE]  
>  Koska parametreja hallitaan erikseen palvelimessa, päivitettyjä parametriasetuksia sisältävän pääraportin julkaiseminen ei korvaa kyseisen raportin parametriasetuksia.  

### <a name="parameter-values"></a>Parametriarvot

 Raportin parametriarvojen valinta-asetukset on esitetty alla.  
  
- Valitse yksittäinen parametriarvo avattavasta luettelosta.  
  
- Valitse useita parametriarvoja avattavasta luettelosta.  
  
- Valitse avattavasta luettelosta yksittäisen parametrin arvo, joka määrittää arvot, jotka ovat käytettävissä toisen parametrin avattavassa luettelossa. Nämä ovat johdannaisparametreja. Johdannaisparametrien avulla voit suodattaa tuhansista parametriarvoista sopivan määrän asteittain.  
  
- Suorita raportti valitsematta ensin parametriarvoa, koska parametrille on luotu oletusarvo.  
  
## <a name="bkmk_Report_Parameters"></a> Raporttiparametrin ominaisuudet

 Voit muuttaa raporttiparametrin ominaisuuksia raportin ominaisuudet -valintaikkunan kautta. Seuraavassa taulukossa on yhteenveto parametreille määritettävissä olevista ominaisuuksista:  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Nimi|Kirjoita parametrille kirjainkoon huomioon ottava nimi. Nimen on alettava kirjaimella, ja siinä voi olla kirjaimia, numeroita ja alaviivoja (_). Nimessä ei voi olla välilyöntejä. Automaattisesti luotavien parametrien nimet vastaavat tietojoukkokyselyn parametreja. Manuaalisesti luodut raporttiparametrit ovat oletusarvoisesti samankaltaisia kuin Raporttiparametri1.|  
|Kehote|Raportin katseluohjelman työkalurivissä parametrin vieressä näytettävä teksti.|  
|Tietotyyppi|Raporttiparametrin on oltava jotain seuraavista tietotyypeistä:<br /><br /> **Totuusarvo**. Käyttäjä valitsee valintapainikkeella Tosi tai Epätosi.<br /><br /> **Päivämäärä/aika**. Käyttäjä valitsee päivämäärän kalenterin ohjausobjektista.<br /><br /> **Kokonaisluku**. Käyttäjä kirjoittaa arvot tekstiruutuun.<br /><br /> **Liukuluku**. Käyttäjä kirjoittaa arvot tekstiruutuun.<br /><br /> **Teksti**. Käyttäjä kirjoittaa arvot tekstiruutuun.<br /><br /> Kun käytettävissä olevat arvot on määritetty parametrille, käyttäjä valitsee arvot avattavasta luettelosta, vaikka tietotyyppi olisi **päivämäärä/aika**.|  
|Salli tyhjä arvo|Valitse tämä vaihtoehto, jos parametrin arvo voi olla tyhjä.<br /><br /> Jos määrität parametrin kelvolliset arvot ja haluat sallia tyhjät arvot, lisää se yhdeksi määrittämäksesi arvoksi. Tämän vaihtoehdon valitseminen ei automaattisesti lisää tyhjiä arvoja.|  
|Salli nolla-arvo|Valitse tämä vaihtoehto, jos parametrin arvo voi olla nolla.<br /><br /> Jos määrität parametrin kelvolliset arvot ja haluat sallia nolla-arvot, lisää ne yhdeksi määrittämäksesi arvoksi. Tämän vaihtoehdon valitseminen ei automaattisesti lisää nolla-arvoja.|  
|Salli useita arvoja|Luomasi, käyttäjien valittavissa olevat arvot, ovat saatavana avattavasta luettelosta. Tämä on hyvä tapa varmistaa, että tietojoukkokyselyssä lähetetään vain kelvollisia arvoja.<br /><br /> Valitse tämä vaihtoehto, jos parametrin arvo voi olla useita, avattavassa luettelossa näytettäviä arvoja. Nolla-arvoja ei sallita. Kun tämä asetus on valittuna, parametrin käytettävissä olevien arvojen luetteloon lisätään valintaruutuja. Luettelon alussa on **Valitse kaikki** -valintaruutu. Käyttäjät voivat valita haluamansa arvot.<br /><br /> Jos tietoja antavat arvot muuttuvat nopeasti, käyttäjän näkemä luettelo ei ehkä ole ajan tasalla.|  
|Näkyvissä|Valitsemalla tämän voit näyttää raporttiparametrin raportin alussa, kun raportti suoritetaan. Tämän asetuksen avulla käyttäjät voivat valita suorittamisen aikana näytettävät parametriarvot.|  
|Piilotettu|Valitsemalla tämän voit piilottaa julkaistun raportin raporttiparametrit. Raportin parametriarvot voidaan edelleen määrittää raportin URL-osoitteessa, tilausmäärityksessä tai raporttipalvelimessa.|  
|Sisäinen|Valitsemalla tämän voit piilottaa raporttiparametrin. Raporttiparametria voidaan tämän jälkeen tarkastella julkaistussa raportissa vain raportin määrityksissä.|  
|Käytettävissä olevat arvot|Jos olet määrittänyt käytettävissä olevat parametrin arvot, kelvolliset arvot näkyvät aina avattavassa luettelossa. Jos annat **päivämäärä/aika**-parametrille käytettävissä olevia arvoja, päivämäärät näkyvät parametriruudussa avattavassa luettelossa kalenteriohjausobjektin sijaan.<br /><br /> Voit määrittää tietolähteen käyttämään yksittäistä tapahtumaa kaikissa tietolähteeseen liittyvissä tietojoukkokyselyissä. Näin voit varmistaa, että arvojen luettelo vastaa raporttia ja aliraporttia.<br /><br /> **Tietoturvahuomautus** **Teksti**-tietotyypin parametreja sisältävissä raporteissa on käytettävä käytettävissä olevien arvojen luetteloa (kelvollisten arvojen luetteloa). Varmista, että raporttia suorittavilla käyttäjillä on vain raportin tietojen tarkasteluoikeudet.|  
|Oletusarvot|Määritä oletusarvot kyselystä tai staattisesta luettelosta.<br /><br /> Kun kaikilla parametreilla on oletusarvot, raportti suoritetaan automaattisesti ensimmäisellä näyttökerralla.|  
|Laajennettu|Määritä raportin määrityksen ominaisuudeksi **UsedInQuery**. Se on arvo, joka ilmaisee, vaikuttaako parametri raportin tietoihin suoraan tai epäsuorasti.<br /><br /> **Päivitysajankohdan automaattinen määrittäminen**<br /> Valitse tämä vaihtoehto, kun haluat raportin käsittelytoiminnon määrittävän arvon asetuksen. Arvo on **Tosi**, jos raportin käsittelytoiminto havaitsee parametriin suoraan tai epäsuorasti viittaavan tietojoukkokyselyn tai jos raportissa on aliraportteja.<br /><br /> **Päivitä aina**<br /> Valitse tämä vaihtoehto, kun raporttiparametria käytetään tietojoukkokyselyssä tai parametrilausekkeissa suoraan tai epäsuorasti. Tämä asetus määrittää **UsedInQuery**-arvoksi Tosi.<br /><br /> **Älä koskaan päivitä**<br /> Valitse tämä vaihtoehto, kun raporttiparametria ei käytetä tietojoukkokyselyssä tai parametrilausekkeissa suoraan tai epäsuorasti. Tämä asetus määrittää **UsedInQuery**-arvoksi Epätosi.<br /><br /> **Varoitus** Käytä **Älä koskaan päivitä** -vaihtoehtoa harkiten. Raporttipalvelimella **UsedInQuery**-parametria käytetään raporttitietojen ja hahmonnettujen raporttien välimuistiasetusten sekä tilannevedosraporttien asetusten hallintaan. Jos määrität **Älä koskaan päivitä** -parametrin virheellisesti, raporttitiedot tai raportit saatetaan siirtää välimuistiin virheellisesti tai tilannevedosraportin tiedot saattavat siirtyä epäyhtenäisesti. |  
  
##  <a name="bkmk_Dataset_Parameters"></a> Tietojoukkokysely  
 Voit suodattaa tietojoukkokyselyn tietoja sisällyttämällä rajoituslauseen, joka rajoittaa noudettuja tietoja määrittämällä tulosjoukkoon sisällytettävät ja siitä pois jätettävät arvot.  
  
 Voit koostaa parametrisoidun kyselyn tietolähteessä suunnittelutyökalun avulla.  
  
-   Transact-SQL-kyselyissä eri tietolähteet tukevat parametrien eri syntakseja. Tuki kattaa kyselyssä sijainnin tai nimen mukaan tunnistettavat parametrit. Relaatiokyselyjen suunnittelutyökalussa valitset suodattimelle parametriasetuksen, joka luo parametrisoidun kyselyn.   
  
-   Microsoft SQL Server Analysis Servicesiin tai muihin moniulotteisiin tietolähteisiin perustuvien kyselyiden tapauksessa voit valita, luodaanko kyselyjen suunnittelutyökalussa määritettyyn suodattimeen perustuva parametri. 
  
##  <a name="bkmk_Manage_Parameters"></a> Julkaistun raportin parametrien hallinta  
 Kun suunnittelet raporttia, raporttiparametrit tallennetaan raportin määritykseen. Kun julkaiset raportin, raporttiparametrit tallennetaan ja niitä hallitaan erillään raportin määrityksestä.  
  
 Julkaistuissa raporteissa voit käyttää seuraavia parametreja:  
  
-   **Raporttiparametrien ominaisuudet.** Muuta raporttiparametrien arvoja suoraan raporttipalvelimessa raportin määrityksestä riippumatta.  
  
-   **Raporttitilaukset** Voit määrittää tietojen suodattamisen parametriarvot ja toimittaa raportteja tilausten kautta. 
  
 Julkaistun raportin parametriominaisuudet säilytetään, jos julkaiset raportin määrityksen uudelleen. Ominaisuusasetukset säilytetään, jos raporttimääritys julkaistaan uudelleen ja parametrin nimet sekä tietotyypit pysyvät muuttumattomina. Jos lisäät tai poistat raporttimäärityksen parametreja tai muutat tietotyyppiä tai aiemman parametrin nimeä, sinun on ehkä muutettava julkaistun raportin parametriominaisuuksia.  
  
 Joissain tapauksissa et voi muokata kaikkia parametreja. Jos raporttiparametri saa tietojoukkokyselystä oletusarvon, kyseistä arvoa ei voi muokata julkaistuissa raporteissa eikä raporttipalvelimessa. Suorittamisen aikana käytettävä arvo määritetään kyselyn suoritushetkellä. Jos parametrit ovat perustuvat lausekkeisiin, suorittamisen aikana käytettävä arvo määritetään, kun lauseke arvioidaan.  
  
 Raportin suoritusasetukset voivat vaikuttaa siihen, miten parametreja käsitellään. Raportti, joka suoritetaan tilannevedoksena, ei voi käyttää kyselystä johdettuja parametreja, paitsi jos kysely sisältää parametrien oletusarvot.  
  
##  <a name="bkmk_Parameters_Subscription"></a> Tilauksen parametrit  
 Voit määrittää pyydettäessä suoritettavan tai tilannevedosraportin tilauksen ja määrittää tilauksen käsittelyssä käytettävät parametriarvot.  
  
-   **Pyydettäessä suoritettava raportti**  Voit määrittää pyydettäessä suoritettavalle raportille eri parametriarvon kuin raportissa luetteloiduille julkaistuille arvoille. Oletetaan, että sinulla on palvelun kutsuraportti, jossa asiakkaiden palvelupyynnöt palautetaan päivän, viikon tai kuukauden mukaan *ajanjakso*parametrin avulla. Jos raportin oletusparametriarvoksi määritetään **tänään**, tilauksessa voidaan käyttää eri parametriarvoja (kuten **viikko** tai **kuukausi**) viikoittaisia tai kuukausittaisia lukuja palauttavan raportin tuottamiseen.  
  
## <a name="next-steps"></a>Seuraavat vaiheet

- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)  
 
 
