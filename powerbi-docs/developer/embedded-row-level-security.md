---
title: Rivitason suojaus Power BI:n upotetussa sisällössä
description: Lue ohjeet, miten voit upottaa Power BI -sisältöä sovellukseesi.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/22/2018
ms.author: maghan
ms.openlocfilehash: 218f4cd0aaaa5ffc8cab3a06b06af9544b02143d
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2018
---
# <a name="use-row-level-security-with-power-bi-embedded-content"></a>Rivitason suojaus Power BI:n upotetussa sisällössä
Rivitason suojauksen (row level security, RLS) avulla käyttäjien käyttöoikeuksia koontinäyttöjen, ruutujen, raporttien ja tietojoukkojen tietoihin voidaan rajoittaa. Eri käyttäjät voivat nähdä eri tiedot käyttäessään kyseisiä kohteita. Upottaminen tukee rivitason suojausta.

Jos olet upottamassa sisältöä muille kuin Power BI:n käyttäjille (sovellus omistaa tiedot), tavallisesti ISV-skenaariossa, tämä artikkeli koskee sinua. Sinun on määritettävä upotuksen tunnus käyttäjälle ja roolille. Ohjeet ovat alla.

Jos olet upottamassa sisältöä Power BI -käyttäjille (käyttäjä omistaa tiedot) organisaatiosi sisällä, rivitason suojaus toimii samalla tavalla kuin suoraan Power BI -palvelussa. Sinun ei tarvitse tehdä sovelluksessasi mitään muuta. Lisätietoja on artikkelissa [Rivitason suojaus (RLS) Power BI:ssä](../service-admin-rls.md).

![Rivitason suojaukseen liittyvät kohteet.](media/embedded-row-level-security/powerbi-embedded-rls-components.png)

Jotta voit hyödyntää rivitason suojausta, sinun on tärkeää ymmärtää kolme pääkäsitettä; käyttäjät, roolit ja säännöt. Alla on kunkin käsitteen kuvailu:

**Käyttäjät** – Kohdetta (koontinäyttöä, ruutua, raporttia tai tietojoukkoa) tarkasteleva loppukäyttäjä. Power BI Embeddedissä käyttäjät tunnistetaan upotuksen tunnuksen käyttäjänimi-ominaisuudella.

**Roolit** – Käyttäjät kuuluvat rooleihin. Rooli on sääntöjen säilö. Roolin nimi voi olla esim. *myyntipäällikkö* tai *myyntiedustaja*. Voit luoda rooleja Power BI Desktopissa. Lisätietoja on artikkelissa [Rivitason suojaus (RLS) Power BI Desktopissa](../desktop-rls.md).

**Säännöt** – Rooleilla on sääntöjä, jotka ovat tietoihin sovellettavia todellisia suodattimia. Sääntö voi olla yksinkertainen, esim. ”maa = USA”, tai paljon dynaamisempi.
Tässä artikkelissa annamme esimerkin rivitason suojauksen luomisesta ja sen käyttämisestä upotetussa sovelluksessa. Esimerkissämme käytetään [Jälleenmyynnin analyysiesimerkki](http://go.microsoft.com/fwlink/?LinkID=780547) -PBIX-tiedostoa.

![Esimerkkiraportti](media/embedded-row-level-security/powerbi-embedded-report-example.png)

## <a name="adding-roles-with-power-bi-desktop"></a>Roolien lisääminen Power BI Desktopilla
Microsoftin jälleenmyynnin analyysiesimerkissä näkyy kaikkien jälleenmyyntiketjuun kuuluvien myymälöiden myynti. Jos rivitason suojaus ei ole käytössä, kaikkien alueiden johtohenkilöt näkevät samat tiedot kirjautuessaan ja tarkastellessaan raporttia. Ylin johto on päättänyt, että kunkin alueen johtajan pitäisi nähdä hallitsemiensa myymälöiden myynti. Rivitason suojaus auttaa tämän saavuttamisessa.

RLS on luotu Power BI Desktopissa. Kun tietojoukko ja raportti on avattu, voimme siirtyä kaavionäkymään ja tarkastella rakennetta:

![Kaavionäkymä Power BI Desktopissa](media/embedded-row-level-security/powerbi-embedded-schema.png)

Huomioi seuraavat asiat tässä rakenteessa:

* Kaikki mitattavat arvot, kuten **Kokonaismyynti**, on tallennettu **Myynti**-faktataulukkoon.
* Muita aiheeseen liittyviä dimensiotaulukoita on neljä: **Kohde**, **Aika**, **Myymälä** ja **Alue**.
* Yhteysviivojen nuolet osoittavat, mihin suuntaan suodattimet voivat jatkua taulukosta toiseen. Jos suodatin on sijoitettu esimerkiksi **Aika[Päivämäärä]**-kohtaan, nykyisessä rakenteessa se suodattaa arvot vain **Myynti**-taulukosta eteenpäin. Tämä suodatin ei vaikuta muihin taulukoihin, sillä kaikki yhteysviivojen nuolet osoittavat myyntitaulukkoon eivätkä siitä pois.
* **Alue**-taulukko ilmaisee kunkin alueen johtajan:
  
    ![Aluetaulukon rivit](media/embedded-row-level-security/powerbi-embedded-district-table.png)

Jos tämän rakenteen perusteella käytämme suodatinta **Alueen johtaja** -sarakkeeseen **Alue**-taulukossa ja jos kyseinen suodatin vastaa raporttia tarkastelevaa käyttäjää, suodatin suodattaa myös **Myymälä-** ja **Myynti**-taulukon tiedot, jolloin vain kyseisen alueen johtaja näkee tiedot.

Ohjeet:

1. Valitse **Mallinnus**-välilehdeltä **Roolien hallinta**.
   
    ![Mallinnusnäkymä Power BI Desktopissa](media/embedded-row-level-security/powerbi-embedded-manage-roles.png)
2. Luo uusi rooli, jonka nimi on **Johtaja**.
   
    ![Luo uusi rooli](media/embedded-row-level-security/powerbi-embedded-new-role.png)
3. Kirjoita **Alue**-taulukkoon seuraava DAX-lauseke: **[alueen johtaja] = USERNAME()**.
   
    ![Rivitason suojauksen säännön DAX-lauseke](media/embedded-row-level-security/powerbi-embedded-new-role-dax.png)
4. Varmista, että säännöt toimivat, valitsemalla **Mallinnus**-välilehdeltä **Näytä rooleina** ja valitse sitten sekä juuri luomasi **Johtaja** että **Muu käyttäjä**. Valitse **Antero Ma** käyttäjäksi.
   
    ![Näytä rooleina -valintaikkuna](media/embedded-row-level-security/powerbi-embedded-new-role-view.png)
   
    Raportit näkyvät tiedot nyt ikään kuin olisit kirjautuneena **Antero Ma** -tilillä.

Kun suodatinta käytetään näin, kaikki **Alue-**, **Myymälä-** ja **Myynti**-taulukkojen tietueet suodatetaan. **Myynti-** ja **Aika**-taulukkojen, **Myynti-** ja **Kohde**-taulukkojen ja **Kohde-** ja **Aika**-taulukkojen yhteyksiin käytettyjen suodattimien suunnan vuoksi taulukoita ei suodateta alaspäin. Saat lisätietoja kaksisuuntaisesta ristiinsuodatuksesta lataamalla [Kaksisuuntainen ristiinsuodatus SQL Server Analysis Services 2016:ssa ja Power BI Desktopissa](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) -raportin.

## <a name="applying-user-and-role-to-an-embed-token"></a>Käyttäjän ja roolin käyttäminen upotustunnukseen
Nyt kun Power BI Desktop -roolit on määritetty, sovelluksesi on määritettävä, jotta voit hyödyntää rooleja.

Sovelluksesi todentaa ja valtuuttaa käyttäjäsi, ja upotettavien tunnusten avulla heille voidaan myöntää käyttöoikeudet valittuun Power BI Embedded -raporttiin. Power BI Embedded ei sisällä tietoja siitä, kuka käyttäjä on. Jotta rivitason suojaus toimii, sinun on välitettävä käyttäjätietoja upotuksen tunnuksen osana. Voit tehdä tämän [GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx)-ohjelmointirajapinnalla.

[GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx)-ohjelmointirajapinta tukee käyttäjätietojen luetteloa, joka sisältää viittauksen oleellisiin tietojoukkoihin. Jotta rivitason suojaus toimii, sinun on välitettävä seuraavat tiedot osana käyttäjätietoja.

* **käyttäjänimi (pakollinen)** – Tämä on merkkijono, jonka avulla käyttäjä voidaan rivitason suojauksen sääntöjä käytettäessä. Luettelossa voi olla vain yksi käyttäjä.
* **roolit (pakollinen)** – Merkkijono, joka sisältää rivitason suojausta käytettäessä valittavat säännöt. Jos välitettäviä rooleja on useampi kuin yksi, ne tulisi välittää merkkijonotaulukkona.
* **tietojoukko (pakollinen)** – Tietojoukko, joka koskee upotettavaa kohdetta. 

Voit luoda upotuksen tunnuksen **GenerateTokenInGroup**-menetelmällä **PowerBIClient.Reports**-kohdassa. 

Voit esimerkiksi muuttaa [PowerBIEmbedded_AppOwnsData](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) -mallia. *Home\HomeController.cs rivin 76 ja 77* voidaan päivittää arvosta:

```
// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync(GroupId, report.Id, generateTokenRequestParameters);
```

arvoon

```
var generateTokenRequestParameters = new GenerateTokenRequest("View", null, identities: new List<EffectiveIdentity> { new EffectiveIdentity(username: "username", roles: new List<string> { "roleA", "roleB" }, datasets: new List<string> { "datasetId" }) });

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync("groupId", "reportId", generateTokenRequestParameters);
```

Jos muodostat yhteyden REST-ohjelmointirajapintaan, päivitetty ohjelmointirajapinta hyväksyy nyt JSON-lisätaulukon nimeltä **käyttäjätiedot**, joka sisältää käyttäjänimen, roolien merkkijonoluettelon ja luettelon merkkijonotietojoukoista, esim.:

```
{
    "accessLevel": "View",
    "identities": [
        {
            "username": "EffectiveIdentity",
            "roles": [ "Role1", "Role2" ],
            "datasets": [ "fe0a1aeb-f6a4-4b27-a2d3-b5df3bb28bdc" ]
        }
    ]
}
```

Nyt kun kaikki osat on koottu yhteen, kun henkilö kirjautuu sovellukseesi tarkastelemaan tätä kohdetta, hän näkee vain sellaiset tiedot, jotka rivitason suojaus sallii hänen näkevän.

## <a name="working-with-analysis-services-live-connections"></a>Reaaliaikaisten Analysis Services -yhteyksien käyttäminen
Rivitason suojausta voi käyttää paikallisilla palvelimilla reaaliaikaisten Analysis Services -yhteyksien avulla. Kun käytät tämäntyyppistä yhteyttä, sinun tulee tuntea muutama käsite.

Käyttäjänimi-ominaisuuden on vastattava Windows-käyttäjää, jolla on käyttöoikeudet Analysis Services -palvelimella.

**Paikallinen tietoyhdyskäytävä -määritys**

[Paikallista tietoyhdyskäytävää](../service-gateway-onprem.md) käytetään, kun käsittelet reaaliaikaisia Analysis Services -yhteyksiä. Upotuksen tunnusta luotaessa, kun käyttäjätieto on luetteloitu, päätili on lueteltava yhdyskäytävän järjestelmänvalvojana. Jos päätili ei ole luettelossa, rivitason suojausta ei käytetä tietojen ominaisuuksiin. Yhdyskäytävän muu käyttäjä kuin järjestelmänvalvojien voi lisätä rooleja, mutta hänen on annettava käyttäjätiedoksi oma käyttäjänimensä.

**Roolien käyttö**

Roolit voidaan toimittaa upotustunnuksen käyttäjätiedoissa. Jos roolia ei ole annettu, annettua käyttäjänimeä käytetään asianmukaisia rooleja ratkaistaessa.

**CustomData-toiminnon käyttö**

CustomData-toiminto mahdollistaa vapaan tekstin (merkkijonon) välittämisen CustomDatan yhteysmerkkijono-ominaisuuden avulla. Se on arvo, jota AS käyttää (CUSTOMDATA()-funktion kautta).
Voit käyttää tätä vaihtoehtoisena tapana tietojen käytön mukauttamiseen.
Voit käyttää sitä DAX-kyselyn roolissa. Voit käyttää sitä ilman roolia mittayksikön DAX-kyselyssä.
CustomData-ominaisuus on osa tunnuksen luontitoimintoja, joita voi käyttää koontinäyttöjen, raporttien ja ruutujen kanssa. Koontinäytöillä voi olla useita CustomData-käyttäjätietoja (yksi ruutu mallia kohden).

> [!NOTE]
> CustomData-ominaisuus toimii vain malleilla, jotka sijaitsevat Azure Analysis Services -palveluissa, ja se toimii vain live-tilassa. Toisin kuin käyttäjät ja roolit, CustomData-ominaisuutta ei voi asettaa .pbix-tiedoston sisälle. Sinulla on oltava käyttäjänimi CustomData-ominaisuuden sisältävää tunnusta luotaessa.
>
>

**CustomDatan SDK-lisäykset**

CustomDatan yhteysmerkkijono-ominaisuus lisättiin käytössä olevaan käyttäjätietoon tunnuksen luontitapahtumassa.
        
        [JsonProperty(PropertyName = "customData")]
        public string CustomData { get; set; }

Käyttäjätieto voidaan luoda mukautetuilla tiedoilla käyttämällä seuraavaa kutsua:

        public EffectiveIdentity(string username, IList<string> datasets, IList<string> roles = null, string customData = null);

**CustomDatan SDK:n käyttö**

Jos muodostat yhteyden REST-ohjelmointirajapintaan, voit lisätä mukautettuja tietoja kaikkiin käyttäjätietoihin, esim.:

```
{
    "accessLevel": "View",
    "identities": [
        {
            "username": "EffectiveIdentity",
            "roles": [ "Role1", "Role2" ],
            "customData": "MyCustomData",
            "datasets": [ "fe0a1aeb-f6a4-4b27-a2d3-b5df3bb28bdc" ]
        }
    ]
}
```

## <a name="considerations-and-limitations"></a>Huomioon otettavat seikat ja rajoitukset
* Käyttäjien määrittäminen rooleihin Power BI -palvelussa ei vaikuta rivitason suojaukseen upotuksen tunnusta käytettäessä.
* Power BI -palvelu ei sovella rivitason suojauksen asetuksia järjestelmänvalvojiin tai jäseniin, joilla on muokkausoikeudet, mutta niitä sovelletaan tietoihin, kun annat upotustunnuksen sisältävät käyttäjätiedot.
* Reaaliaikaisia Analysis Services -yhteyksiä tuetaan paikallisissa palvelimissa.
* Reaaliaikaiset Azure Analysis Services -yhteydet tukevat suodattamista roolien mukaan, mutta eivät dynaamisesti käyttäjänimen mukaan.
* Jos pohjana oleva tietojoukko ei vaadi rivitason suojausta, GenerateToken-pyyntö **ei** saa sisältää käytössä olevia käyttäjätietoja.
* Jos pohjana oleva tietojoukko on pilvimalli (välimuistissa oleva tai DirectQuery-malli), käytössä olevien käyttäjätietojen on sisällettävä vähintään yksi rooli, tai roolimääritystä ei tehdä.
* Käyttäjätietojen luettelo mahdollistaa useat käyttäjätietojen tunnukset koontinäyttöjen upotusta varten. Luettelo sisältää yksittäisen käyttäjän tiedot kaikille muille kohdetyypeille.

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)