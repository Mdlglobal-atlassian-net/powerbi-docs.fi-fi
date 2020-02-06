---
title: DirectQueryn käyttö Power BI Desktopissa
description: DirectQueryn, jota kutsutaan myös reaaliaikaiseksi yhteydeksi, käyttö Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 90721b059958e59cfd74f9ba1d0d25617a7438e6
ms.sourcegitcommit: 8b300151b5c59bc66bfef1ca2ad08593d4d05d6a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2020
ms.locfileid: "76889278"
---
# <a name="use-directquery-in-power-bi-desktop"></a>DirectQueryn käyttö Power BI Desktopissa
Kun muodostat yhteyden tietolähteeseen, voit *Power BI Desktopin* avulla aina tuoda kopion tiedoista Power BI Desktopiin. Joillekin tietolähteille on saatavilla vaihtoehtoinen menetelmä: yhteyden muodostaminen suoraan tietolähteeseen DirectQueryn avulla.

## <a name="supported-data-sources"></a>Tuetut tietolähteet
Löydät DirectQueryä tukevien tietolähteiden täydellisen luettelon artikkelista [DirectQueryn tukemat tietolähteet](power-bi-data-sources.md).

## <a name="how-to-connect-using-directquery"></a>Yhteyden muodostaminen DirectQueryn avulla
Kun käytät **Nouda tiedot** -komentoa yhteyden muodostamiseen DirectQueryn tukemaan tietolähteeseen, voit yhteysikkunan avulla valita yhteystavan. Valitse esimerkiksi Power BI Desktopin **Aloitus**-valintanauhassa valita **Nouda tiedot** > **SQL Server**. **SQL Server -tietokanta**-valintaikkunassa **tietojen yhdistämistilassa** näytetään **Tuonti** -ja **DirectQuery**-asetukset:

![Tuonti- ja DirectQuery-asetukset, SQL Server Database -valintaikkuna, Power BI Desktop](media/desktop-use-directquery/directquery_sqlserverdb.png)

**Tuonti**- ja **DirectQuery**-komentojen valinnan erot ovat:

- **Tuonti**: Valitut taulukot ja sarakkeet tuodaan Power BI Desktopiin. Kun luot tai käsittelet visualisointeja, Power BI Desktop käyttää tuotuja tietoja. Jos haluat nähdä taustalla olevat tietomuutokset alkuperäisen tuonnin tai viimeisimmän päivityksen jälkeen, sinun on päivitettävä tiedot, jotka tuovat koko tietojoukon uudelleen.

- **DirectQuery**: Mitään tietoja ei tuoda tai kopioida Power BI Desktopiin. Valitut taulukot ja sarakkeet näkyvät relaatiolähteissä **Kentät**-luettelossa. Moniulotteisissa lähteissä, kuten SAP Business Warehouse, valitun kuution dimensiot ja mittarit näkyvät **Kentät**-luettelossa. Kun luot tai käsittelet visualisointeja, Power BI Desktop lähettää kyselyjä pohjana olevaan tietolähteeseen eli näet aina ajantasaiset tiedot.

Saatavilla on useita tietojen mallinnuksia ja muunnoksia DirectQueryn käytön aikana, vaikka siihen liittyykin joitakin rajoituksia. Kun luot tai käsittelet visualisointia, sinun on tehtävä kysely pohjana olevalle lähteelle. Visualisoinnin päivittämiseen kuluva aika määräytyy taustalla olevan tietolähteen tehokkuuden perusteella. Kun palvelupyynnön täyttämiseen tarvittavia tietoja on pyydetty äskettäin, Power BI Desktop käyttää viimeisimpiä tietoja visualisoinnin näyttämiseen vaaditun ajan lyhentämiseksi. Valitsemalla **Päivitä** **Aloitus**-valintanauhasta päivität kaikkiin visualisointeihin uusimmat tiedot.

Artikkelissa [Power BI ja DirectQuery](desktop-directquery-about.md) kuvataan DirectQueryä tarkemmin. Lisätietoja eduista, rajoituksista ja tärkeistä huomioon otettavista seikoista, kun käytät DirectQueryä, näet seuraavista kohdista.

## <a name="benefits-of-using-directquery"></a>DirectQueryn käytön edut
DirectQueryn käytöstä on joitakin etuja:

- Voit DirectQueryn avulla luoda visualisointeja hyvin laajoista tietojoukoista, kun se muuten olisi mahdotonta, tuomalla ensin kaikki tiedot esikoostettuina.
- Pohjana olevien tietojen muutokset voivat edellyttää tietojen päivittämistä. Joidenkin raporttien tapauksessa nykyisten tietojen näyttäminen voi vaatia suuria tiedonsiirtoja, eikä tietoja voida siten tuoda uudestaan. Sitä vastoin DirectQuery-raportit käyttävät aina ajantasaisia tietoja.
- 1 Gt:n tietojoukkorajoitusta *ei* sovelleta DirectQueryyn.

## <a name="limitations-of-directquery"></a>DirectQueryn rajoitukset
DirectQueryn käyttöön liittyy nykyisin joitakin rajoituksia:

- Kaikkien taulukoiden on oltava peräisin yksittäisestä tietokannasta, ellei käytetä [yhdistelmämalleja](desktop-composite-models.md).

- Jos **kyselyeditorin** kysely on liian monimutkainen, tapahtuu virhe. Virheen korjaamiseksi on joko poistettava ongelmallinen vaihe **kyselyeditorissa** tai *tuotava* tiedot DirectQueryn käytön sijasta. Moniulotteisten tietolähteiden, kuten SAP Business Warehousen, tapauksessa ei voi käyttää **kyselyeditoria**.

- Aikatieto-ominaisuudet eivät ole käytettävissä DirectQueryssä. Esimerkiksi päivämääräsarakkeiden (kuten vuosi, vuosineljännes, kuukausi tai päivä) erityiskohtelua ei tueta DirectQuery-tilassa.

- Mittareille määritetään oletusarvoisesti rajoituksia sen varmistamiseksi, että pohjana olevaan tietolähteeseen lähetettyjen kyselyjen suorituskyky on riittävä.

- Tietojen palautuksen tapauksessa on miljoonan rivin rajoitus käytettäessä DirectQueryä, jollei käytetä Premium-ominaisuuksia. Rajoitus ei vaikuta koosteisiin tai laskelmiin, joita on käytetty DirectQueryn avulla palautetun tietojoukon luontiin. Se vaikuttaa vain palautettuihin riveihin. Premium-ominaisuudet voivat asettaa rivien enimmäisrajat, kuten on kuvattu [tässä julkaisussa](https://powerbi.microsoft.com/blog/five-new-power-bi-premium-capacity-settings-is-available-on-the-portal-preloaded-with-default-values-admin-can-review-and-override-the-defaults-with-their-preference-to-better-fence-their-capacity/). 

    Voit esimerkiksi koostaa 10 miljoonaa riviä käyttäen kyselyä, joka suoritetaan tietolähteessä. Kysely palauttaa tämän koosteen tulokset Power BI DirectQueryn avulla, jos palautettuja Power BI -tietoja on alle miljoona riviä. Jos DirectQuery palauttaa yli miljoona riviä, Power BI palauttaa virheen (jollei käytetä Premium-ominaisuuksia, jolloin rivimäärä on järjestelmänvalvojan määrittämä).

## <a name="important-considerations-when-using-directquery"></a>DirectQueryn käytössä huomioitavia tärkeitä seikkoja
Kun käytät DirectQueryä, ota huomioon seuraavat kolme seikkaa:

- **Suorituskyky ja kuormitus**: Kaikki DirectQuery-pyynnöt lähetetään lähdetietokantaan, joten visualisoinnin päivitykseen vaadittava aika riippuu siitä, miten kauan taustalähteeltä menee vastaamiseen kyselyn (tai kyselyjen) tulosten avulla. Suositeltu vastausaika (kun pyydetyt tiedot palautetaan) käyttämällä DirectQueryä visualisoinneille on korkeintaan viisi sekuntia. Suositeltu enimmäisaika on 30 sekuntia. Jos aika on tätä pidempi, raportin käyttökokemus heikkenee selvästi. Kun raportti on julkaistu Power BI -palvelussa, yli pari minuuttia kestävä kysely aikakatkaistaan, ja käyttäjä saa virheen.
  
    Tässä yhteydessä olisi myös otettava huomioon lähdetietokannan kuormitus julkaistua raporttia hyödyntävien Power BI -käyttäjien määrän mukaan. **Rivitason suojauksen** (RLS) käyttäminen voi vaikuttaa myös merkittävästi. Useiden käyttäjien jakama muu kuin RLS-koontinäytön ruutu johtaa yksittäiseen tietokantakyselyyn. RLS-kohteen käyttäminen koontinäytön ruudulla tarkoittaa yleensä sitä, että ruudun päivittäminen edellyttää yhtä kyselyä *käyttäjää kohden*, mikä lisää merkittävästi lähdetietokannan kuormitusta ja saattaa vaikuttaa suorituskykyyn.
  
    Power BI luo kyselyjä, jotka ovat mahdollisimman tehokkaita. Luotu kysely ei ehkä kuitenkaan tietyissä tilanteissa ole riittävän tehokas mahdollisesti epäonnistuneen päivityksen välttämiseksi. Yksi esimerkki tästä tilanteesta on se, kun luotu kysely noutaa liikaa rivejä taustatietolähteestä. Tällöin tapahtuu seuraavia virheitä:

    ```output
    The resultset of a query to external data source has exceeded
    ```
  
    Tällainen tilanne voi ilmetä yksinkertaisen kaavion tapauksessa, kun se sisältää hyvin suuren kardinaliteettisarakkeen, jonka koostevaihtoehdoksi on määritetty **Älä tee yhteenvetoa**. Visualisoinnissa on oltava vain sarakkeita, joiden kardinaliteetti on alle miljoona, tai siihen on sovellettava asianmukaisia suodattimia.

- **Suojaus**: Oletusarvoisesti kaikki julkaistua raporttia hyödyntävät käyttäjät muodostavat yhteyden taustatietolähteeseen tunnistetiedoilla, jotka annetaan kirjautumisen jälkeen Power BI -palveluun. Tämä on sama prosessi kuin tuotujen tietojen tapauksessa: kaikki käyttäjät näkevät samat tiedot riippumatta taustalähteessä määritetyistä suojaussäännöistä.

    Asiakkaiden, jotka haluavat käyttää käyttäjäkohtaista suojausta DirectQuery-lähteissä, tulee käyttää joko RLS-protokollaa tai määrittää lähteelle rajoitettu Kerberos-todentaminen. Kerberos ei ole käytettävissä kaikille lähteille. [Lue lisää RLS-tasosta](service-admin-rls.md). [Lisätietoja Kerberosista DirectQueryssa](service-gateway-sso-kerberos.md).

- **Tuetut ominaisuudet**: Power BI Desktopin kaikkia ominaisuuksia ei tueta DirectQuery-tilassa tai niihin liittyy joitakin rajoituksia. Lisäksi Power BI -palvelussa on joitakin ominaisuuksia (kuten *Nopeat merkitykselliset tiedot*), joita eivät ole saatavilla DirectQueryä käyttäville tietojoukoille. Kun määrität, käytetäänkö DirectQueryä, harkitse näitä ominaisuuksien rajoituksia.

## <a name="publish-to-the-power-bi-service"></a>Power BI -palveluun kirjautuminen
DirectQueryn avulla luodut raportit voidaan kirjata Power BI -palveluun.

Jos käytetty tietolähde ei tarvitse **paikallista tietoyhdyskäytävää** (**Azure SQL -tietokanta**, **Azure SQL Data Warehouse** tai **Redshift**), tunnistetiedot on annettava ennen kuin kirjattu raportti näytetään Power BI -palvelussa. Anna tunnistetiedot noudattamalla näitä ohjeita:

1. Kirjautuminen [Power BI](https://www.powerbi.com/):iin.
2. Valitse Power BI -palvelu, valitse **Asetukset**-kuvake ja valitse **Asetukset** -valikkokohde.

    ![Asetukset, Power BI -palvelu](media/desktop-use-directquery/directquery_pbiservicesettings.png)

3. Power BI -palvelun **Asetukset**-sivulta valitaan **Tietojoukot**-välilehti ja sitten tietojoukko, joka käyttää DirectQueryä, minkä jälkeen valitaan **Muokkaa tunnistetietoja**.

4. Lisää tunnistetiedot. Muussa tapauksessa ilmenee virhe, kun avaat julkaistun raportin tai tutustut tietojoukkoon, joka on luotu DirectQuery-yhteydellä.

Muille tietolähteille kuin **Azure SQL -tietokanta**, **Azure SQL Data Warehouse** ja **Redshift**, jotka käyttävät DirectQueryä **, on asennettava paikallinen tietoyhdyskäytävä**, ja tietolähde on rekisteröitävä tietoyhteyden muodostamiseksi. Lisätietoja on ohjeaiheessa [Mikä on paikallinen tietoyhdyskäytävä?](service-gateway-onprem.md)

## <a name="next-steps"></a>Seuraavat vaiheet
Saat lisätietoja DirectQuerystä seuraavista resursseista:

- [DirectQueryn käyttäminen Power BI:ssä](desktop-directquery-about.md)
- [DirectQueryn tukemat tietolähteet](power-bi-data-sources.md)
- [DirectQuery ja SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)
- [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
- [Mikä paikallinen tietoyhdyskäytävä on?](service-gateway-onprem.md)
