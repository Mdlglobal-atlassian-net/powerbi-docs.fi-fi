---
title: Microsoft Power BI Premium-Kapasiteettien hallinta
description: Tässä artikkelissa kuvataan Power BI Premium-kapasiteetteja hallintatehtäviä.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: e4bb907e12d3c0b07408f069d9b238599756e8e0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565240"
---
# <a name="managing-premium-capacities"></a>Premium-Kapasiteettien hallinta

Power BI Premium hallintaan sisältyy luomista, hallintaan ja valvontaan Premium-kapasiteetteja.

## <a name="creating-and-managing-capacities"></a>Luomisesta ja hallitsemisesta kapasiteetit

**Kapasiteettiasetukset** Power BI-hallintaportaalin sivulla näkyy määrän v-ydintä ostettu ja Premium-kapasiteetteja. Office 365: n Yleiset Järjestelmänvalvojat tai Power BI-palvelun järjestelmänvalvojat avulla voit luoda Premium-kapasiteetteja käytettävissä olevat v-ytimet ja muokata aiemmin Premium-kapasiteetteja sivulla.

Kun luot Premium-kapasiteettiin, järjestelmänvalvojat vaaditaan määrittämään:

- Kapasiteetin nimi (yksilöiviä vuokraajassa).
- Kapasiteetin admin(s).
- Kapasiteetin koko.
- Tietojen tallennusta Saksassa vaatimukset alue.

Vähintään yksi kapasiteetin järjestelmänvalvojan on määritettävä. Kapasiteetin järjestelmänvalvojat määrittää käyttäjät voivat:

- Määritä työtilat kapasiteettiin.
- Hallitse käyttöoikeuksia, voit lisätä muita kapasiteetin Järjestelmänvalvojat tai käyttäjät, joilla on määrityskäyttöoikeudet (jotta ne voivat määrittää työtiloja kapasiteettiin).
- Hallintaan, määrittämään muistinkäyttö sivutetut raportit ja dataflows kuormituksille.
- Käynnistä kapasiteetin, kaikki toiminnot vaihtaa järjestelmän ylikuormitusta vuoksi.

Kapasiteetin järjestelmänvalvojat voi käyttää työtilan sisältöä, ellet ole erikseen määritetty työtilan käyttöoikeudet. He myös ei ole käyttöoikeuksia Power BI-järjestelmänvalvojien kaikkiin alueisiin (paitsi eksplisiittisesti varattu) kuten käyttötilastoihin, Valvontalokeihin tai vuokraaja-asetukset. Ennen kaikkea kapasiteetin järjestelmänvalvojilla ei ole oikeuksia luoda uusien kapasiteettien tai Skaalaa aiemmin kapasiteettien. Järjestelmänvalvojat määritetään kohden kapasiteetin säännöllisesti, varmistaa, että he voivat vain tarkastella ja hallita kapasiteetit, joihin ne on varattu.

Kapasiteetin koko valitaan on käytettävissä SKU vaihtoehtojen luettelo, joka on rajoitettu käytettävissä olevat v-ytimet varannossa määrän mukaan. On mahdollista luoda useita kapasiteettien varannosta, joka saattaa vakioentiteeteille yhdestä tai Lisää ostanut Varastointiyksiköt. Esimerkiksi P3-Varastointiyksikkö (32 v-ydintä) avulla voi luoda kolmen kapasiteettien: yksi P2 (16 v-ydintä) ja kaksi P1 (2 x 8 v-ydintä). Parannettu suorituskyvyn ja mittakaavan voidaan saavuttaa luomalla pienempi suuriin kapasiteettien kuvatulla tavalla [optimointi Premium-kapasiteetteja](service-premium-capacity-optimize.md) artikkelissa. Seuraavassa kuvassa on esimerkki-asennusohjelma kuvitteellisia Contoso organisaation viisi Premium-kapasiteetteja muodostuu (3 x P1 ja 2 x P3) sisältävän kunkin sovelluksen työtilat ja useita työtiloja jaettuun kapasiteettiin.

![Esimerkki-asetukset-kuvitteellisia Contoso-organisaatio](media/service-premium-capacity-manage/contoso-organization-example.png)

Premium-kapasiteettiin määrittää, että alue kuin Power BI-vuokraaja, kutsutaan useiden geo kotialueella. Useiden geo avulla voit hallita järjestelmänvalvojan mitä palvelinkeskuksiin sisällä määritettyä Power BI-sisältösi sijaitsee maantieteellisellä alueella. Useiden geo-käyttöönoton perusteet on yleensä yrityksen tai valtionhallinnon yhteensopivuuden sijaan suorituskyvyn ja mittakaavan. Raportin ja koontinäytön lataamisen liittyy yhä metatietojen kotialue pyyntöjä. Lisätietoja on artikkelissa [useiden Geo tuki Power BI Premium](service-admin-premium-multi-geo.md).

Power BI-palvelun Järjestelmänvalvojat ja Office 365: n Yleiset järjestelmänvalvojat voivat muokata Premium-kapasiteetteja. Tarkemmin sanottuna he voivat:

- Muuta kapasiteetin kokoa, Skaalaa suuremmaksi tai asteikon alaspäin resursseja.
- Lisää tai poista kapasiteetin järjestelmänvalvojia.
- Lisää tai poista käyttäjät, joilla on määrityskäyttöoikeudet.
- Lisää tai poista muita kuormituksille.
- Muuta alueilla.

Määrittämisen käyttöoikeudet vaaditaan työtila tietyn Premium-kapasiteettiin. Käyttöoikeuksia voidaan myöntää koko organisaatiolle, tietyille käyttäjille tai ryhmille.

Oletusarvon mukaan Premium-kapasiteetteja tue kuormituksia liittyvät suoritettaessa Power BI-kyselyjä. Premium-kapasiteetteja tukevat myös muita kuormituksia: **AI (kognitiiviset palvelut)** , **sivutetut raportit**, ja **Dataflows**. Jokainen kuormitus edellyttää määrittäminen muistin enimmäismäärän (yhteensä muistia prosenttilukuna), jonka avulla voidaan kuormituksen mukaan. On tärkeää ymmärtää, että päivitykset siirtomäärän ja active malleja, joita voidaan isännöidä määrä voi vaikuttaa kasvattamista enimmäismuisti estetään. 

Muistin kohdistetaan dynaamisesti dataflows, mutta kohdistetaan staattisesti sivutettuja raportteja. Lisämuistin staattisesti muistin enimmäismäärän johtuu sivutetut raportit toimivat kapasiteetin suojatun contained välilyönti. Huolehdittava Kun asetus Sivutettujen raporttien muistin, kun muistia lataamiseen malleja. Lisätietoja on artikkelissa [muistin oletusasetukset](service-admin-premium-workloads.md#default-memory-settings).

Premium-kapasiteettiin poistaminen on mahdollista ja ei johtaa sen työtilat ja sisällön poistaminen. Sen sijaan siirtää määritetyt työtilat jaettuun kapasiteettiin. Luotaessa Premium-kapasiteettiin eri alueella, työtilan siirretään jaettuun kapasiteettiin poikkeavalla alueella.

### <a name="assigning-workspaces-to-capacities"></a>Työtilojen määrittäminen kapasiteetit

Työtilat voidaan määrittää Premium-kapasiteettiin Power BI-hallintaportaalissa tai sovelluksen työtilassa **työtilan** ruudussa.

Kapasiteetin järjestelmänvalvojat sekä Office 365: n Yleiset Järjestelmänvalvojat tai Power BI-palvelun järjestelmänvalvojat voivat joukkomäärittää työtiloja Power BI-hallintaportaalissa. Määritetty Bulk käyttää:

- **Työtilat käyttäjien mukaan** – kaikki kyseisten käyttäjien, mukaan lukien Omat työtilat omistamat työtilat määritetään Premium-kapasiteettiin. Tämä sisältää työtilat uudelleenmääritys, kun ne on jo määritetty eri Premium-kapasiteettiin. Lisäksi käyttäjät määritetään myös työtilan määrittämisen käyttöoikeudet.

- **Määritetyt työtilat**
- **Koko organisaation työtilat** – kaikki työtilat, mukaan lukien Omat työtilat määritetään Premium-kapasiteettiin. Kaikki nykyiset ja tulevat käyttäjät määritetään työtilan määrittämisen käyttöoikeudet. Tämä lähestymistapa ei suositella. Lisää lähestymistapaan suositellaan.

Työtila voidaan lisätä Premium-kapasiteetin avulla **työtilan** tarjoten käyttäjä on sekä työtilan järjestelmänvalvoja ja on määrittämisen käyttöoikeudet.

![Työtila Premium-kapasiteettiin työtila-ruudussa avulla](media/service-premium-capacity-manage/assign-workspace-capacity.png)

Työtilan järjestelmänvalvojat voivat poistaa työtilan-kapasiteetti (Voit jaettuun kapasiteettiin) edellyttämättä määrittämisen käyttöoikeus. Työtilan työtilat poistamista varattua kapasiteettia tehokkaasti uudelleensijoittaa jaettuun kapasiteettiin. Huomaa, että poistaminen työtilan Premium-kapasiteettiin voi olla negatiivisia vaikutuksia tuloksena, esimerkiksi jaettua sisältöä muodostumassa ole käytettävissä Power BI ilmainen käyttöoikeus käyttäjät tai ajoitetun päivityksen peruuttamisesta, kun ne ylittävät tueta korvauksia jaettu kapasiteettien käytössä.

Power BI-palvelussa määritetty Premium-kapasiteettiin työtila tunnistetaan helposti avulla vinoneliökuvakkeen, adorns työtilan nimi.

![Tunnistetaan määritetty Premium-kapasiteettiin työtila](media/service-premium-capacity-manage/premium-diamond-icon.png)

## <a name="monitoring-capacities"></a>Valvonnan kapasiteetit

Premium-kapasiteetteja valvonta tarjoaa Järjestelmänvalvojat, joilla on käsitys siitä, miten kapasiteetit toimivat. Kapasiteettien voidaan valvoa käyttämällä Power BI-hallintaportaalissa tai **Power BI Premium-kapasiteetin Mittaustietoihin** (Power BI)-sovellus.

### <a name="power-bi-admin-portal"></a>Power BI -hallintaportaali

Hallintaportaalissa kunkin kapasiteetin **kunnon** välilehdessä on yhteenveto mittareita kapasiteetti ja jokainen käytössä kuormitus. Mittarit näyttävät keskiarvo viimeisten seitsemän päivän aikana.  

Kapasiteetin tasolla tietoraportti on koottu kaikki käytössä kuormitusten. seuraavat arvot on annettu:

- **Suorittimen KÄYTTÖASTE** -tarjoaa keskimääräinen yhteensä käytettävissä suorittimen prosenttiosuutena suorittimen käytöstä kapasiteetti.  
- **MUISTINKÄYTTÖ** -tarjoaa keskimääräinen muistinkäyttö (gt) kuin kapasiteetin muistia yhteensä. 

Kunkin käytössä kuormituksen suoritinkäytön ja muistinkäyttö on annettu, sekä kuormituksen tietyt mittarit määrä. Esimerkiksi tietovirrassa, kuormituksen **kokonaismäärä** näkyy yhteensä kunkin tietovirrassa päivitykset ja **keskimääräinen kesto** näyttää tietovirrassa päivityksen keskimääräinen kesto.

![Kapasiteetin kunnon välilehti-portaalissa](media/service-premium-capacity-manage/admin-portal-health-dataflows.png)

Saat lisätietoja jokainen kuormitus käytettävissä luomiensa [valvoa kapasiteetin hallintaportaalissa](service-admin-premium-monitor-portal.md).

Power BI-hallintaportaalissa valvontaan on suunniteltu antamaan avaimen kapasiteetin mittaustietoihin nopeasti yhteenveto. Yksityiskohtaisempia valvonta, on suositeltavaa **Power BI Premium-kapasiteetin Mittaustietoihin** sovelluksen.

### <a name="power-bi-premium-capacity-metrics-app"></a>Power BI Premium-kapasiteetin mittareita sovellus

[Power BI Premium-kapasiteetin Mittaustietoihin sovelluksen](https://appsource.microsoft.com/product/power-bi/pbi_pcmm.pbi-premiumcapacitymonitoring?tab=Overview) Power BI-sovellus on käytettävissä kapasiteetin Järjestelmänvalvojat ja kuten Power BI-sovellus on asennettu. Se sisältää koontinäytön ja raportin.

![Power BI Premium-kapasiteetin mittareita sovellus](media/service-premium-capacity-manage/capacity-metrics-app.png)

Sovellus avautuu, kun koontinäyttöä ladataan esittää useita ruutuja ilmoittaminen koostettu näkymä kautta kapasiteetteihin käyttäjä on kapasiteetin järjestelmänvalvoja. Raporttinäkymän asettelu sisältää viisi osaa:

- **Yleiskatsaus** -sovelluksen versio, kapasiteettien ja työtilat
- **Järjestelmäyhteenveto** -muistin ja suorittimen mittarit
- **Tietojoukon yhteenveto** – luku tietojoukkoja, DQ/LC, päivitys ja kyselyn mittarit
- **Tietovirrassa yhteenveto** – luku dataflows ja tietojoukon mittarit
- **Sivutettu raportti yhteenveto** – Päivitä ja tarkastella mittareita

Pohjana olevaan raporttiin, josta koontinäyttöruudut on kiinnitetty, voidaan käyttää napsauttamalla mitä tahansa koontinäytön ruudulle. Se antaa lisätietoja yleiskuvan koontinäytön osioissa ja tukee vuorovaikutteinen suodatusta. 

Suodatus voidaan saavuttaa asettamalla osittajat päivämääräalue, kapasiteetti, työtilan ja kuormituksen (raportin, tietojoukon tietovirrassa) ja valitsemalla raportin sisältämiä elementtejä raporttisivu cross visualisoinnit suodatetaan. Ristisuodatuksen on tehokas tekniikkaa, voit rajata ajanjaksoihin kapasiteetit, työtilat, tietojoukot, jne. voi olla paljon hyötyä, kun root syy analyysiä

Katso lisätietoja koontinäytön ja raportin mittareita sovelluksessa [valvonnan Premium-kapasiteetteja sovelluksessa](service-admin-premium-monitor-capacity.md).

### <a name="interpreting-metrics"></a>Tulkitseminen mittarit

Resurssin käyttö ja kuormituksen toimintaa alkuperäiset käsitys muodostaa olisi seurattava mittareita. Jos kapasiteetin hidas, on tärkeää ymmärtää, mitä mittareita, jotta voit valvoa ja päätelmien voit tehdä.

Ihannetapauksessa kyselyt suoritetaan tarjoavat reagoiva kokemuksia raporttikäyttäjät tai uudempi kyselyn siirtomäärän ottaminen käyttöön sekunnin kuluessa. Se on yleensä vähemmän huolta – mukaan lukien päivitykset - taustan prosessit kestää kauemmin kertaa suorittamiseen.

Yleensä hidas raportit voivat olla osoitus ylikulutusta lämmitys kapasiteetti. Kun raporttien lataaminen epäonnistuu, tämä on perusteettomasti lämmitettävä kapasiteetin osoittaa. Kummassakin tapauksessa sen voitu johtuvat monien tekijöiden mukaan:

- **Epäonnistuneiden kyselyiden** ilmaista erottuu muisti on vähissä, ja että mallia ei voitu ladata muistiin. Power BI-palvelu yrittää ladata mallin 30 sekuntia ennen epäonnistumista.

- **Liiallisen kyselyn Odota kertaa** voi aiheutua useista syistä:
  - Täytyy ensin Power BI-palvelun evict mallit ja lataa sitten to-be-kysely-malli (peruuttaminen että uudempi tietojoukon häätäminen hinnaston mukaisesti yksin eivät ole kapasiteetin ruuhkautuminen osoittaa pitkä kyselyn Odota kertaa, jotka osoittavat muistin tietojen poistaminen ei liity).
  - Mallin lataaminen aikakatkaistaan (erityisesti suurten mallin lataaminen muistiin Odota).
  - Pitkäkestoinen kyselyitä.
  - Liian monta LC\DQ yhteyttä (kapasiteetin ylitysten).
  - Suorittimen kylläisyys.
  - Monimutkainen raportti-suunnitteluista ja visualisointien liikaa sivulla (peruuttaminen, että jokainen visualisointi on kysely).

- **Pitkän kyselyn keston** voivat ilmaista, että mallin rakenteet ovat ei ole optimoitu, erityisesti silloin, kun useita tietojoukkoja ovat aktiivisia kapasiteettia ja vain yksi tietojoukko on tekemiseen kyselyn keston. Tämä ilmaisee, että kapasiteetti on riittävän niille ja kysymys-tietojoukko on optimaalisen tai vain hidas. Pitkään suoritettavat kyselyt voivat olla ongelmallinen, kuin ne estä pääsy resursseihin muut prosessit.
- **Päivitä pitkä Odota kertaa** ilmaista vuoksi useita active mallien muistia ei ole tarpeeksi muistia tai että ongelmallinen päivityksen estää muita päivittää (yli parallel päivityksen rajoitukset).

Tarkempi kuvaus käyttäminen mittarit käsitellään [optimointi Premium-kapasiteetteja](service-premium-capacity-optimize.md) artikkelissa.

## <a name="acknowledgements"></a>Kuittaussanomien

Tämä artikkeli koskee Peter Myers, tietojen Platform MVP ja riippumattoman BI asiantuntijan kanssa [Bitwise ratkaisuja](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Seuraavat vaiheet

> [!div class="nextstepaction"]
> [Premium-kapasiteetteja optimointi](service-premium-capacity-optimize.md)   
> [!div class="nextstepaction"]
> [Määritä kuormituksia Premium-kapasiteetissa](service-admin-premium-workloads.md)   

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

||||||
