---
title: Power BI -tietovoiden parhaat käytännöt
description: Power BI -tietovoiden parhaat käytännöt
author: mohaali
manager: mohaali
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/19/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: c499a83b87eb15031d75974084468f418a17804a
ms.sourcegitcommit: 200291eac5769549ba5c47ef3951e2f3d094426e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/19/2019
ms.locfileid: "71142301"
---
# <a name="dataflows-best-practice"></a>Tietovoiden parhaat käytännöt

Tämä artikkeli sisältää tietovoiden parhaat suunnittelukäytännöt Power BI:ssä. Näiden ohjeiden avulla opit luomaan tietovoita sekä soveltamaan näitä käytäntöjä omiin tietovoihisi.

> [!NOTE]
> Tämän artikkelin suositukset ovat suuntaa antavia. Saatat eri syistä joutua poikkeamaan tässä artikkelissa kuvatuista parhaista käytännöistä. 
> 
> 

### <a name="split-ingestion-and-transformation-to-use-the-enhanced-compute-engine"></a>Parannetun käsittelymoduulin käyttämin osiin jaettujen tietojen käsittelyyn ja muuntamiseen

Kun luot tietovoita, saatat haluta luoda yhden tietovuon, joka sisältää kaikki entiteetit, muunnokset, liitokset ja parannukset. Yksittäinen tietovuo voi olla hyvä ratkaisu pienten tietojoukkojen tapauksessa. Kun käsittelet suurempia tietomääriä, liitosten tai joidenkin muunnosten suorittaminen voi joskus estyä kuormitussäätimen tai muistin rajoitusten vuoksi. Näiden ongelmien vuoksi Power BI Premium -käyttäjille on julkaistu parannettu käsittelymoduuli, joka skaalautuu paljon suurempien tietomäärien mukaisesti. Parannettu käsittelymoduuli toimii vain linkitettyjen tai käsiteltyjen entiteettien kanssa, joten siitä on hyötyä erillisen käsiteltävän tietovuon sekä monimutkaisia yhdistämis- ja muuntamistehtäviä suorittavien linkitettyjen tietovoiden luomisessa.

Tietovoiden jakaminen osiin on kätevä myös päivitysongelmien vianmäärityksessä ja virheenkorjauksessa, erityisesti jos lähdettä koskevat kuormitussäätimien rajoitukset.

### <a name="perform-actions-that-can-use-the-enhanced-compute-engine"></a>Parannettua käsittelymoduulia käyttävien toimintojen suorittaminen

Voit varmistaa, että hyödynnät parannettua käsittelymoduulia, suorittamalla liitokset ja suodatinten muunnokset käsitellyssä entiteetissä ennen muunlaisten muunnosten suorittamista.

### <a name="split-dataflows-when-connecting-to-sharepoint"></a>Tietovoiden jakaminen osiin SharePointiin yhdistettäessä

Kun työskentelet SharePointin kanssa ja muodostat yhteyden useisiin tiedostoihin, saatat havaita satunnaisia virheitä. SharePointin luotettavuus ja reagoivuus on varmistettu rajoittamalla pyyntöjä. Tämän seurauksena saatat haluta ladata kaikki tiedostot yhdestä tietovuosta yhdistäessäsi Excel-tiedostoihin SharePointista. Jos lataat useita tiedostoja (yli 20), voit ohittaa SharePointin rajoituksen luomalla vähintään kaksi tietovuota.

### <a name="avoid-scheduling-refresh-for-linked-entities-inside-the-same-workspace"></a>Samaan työtilaan sisältyvien entiteettien ajoitetun päivittämisen välttäminen

Jos et usein pysty käyttämään tietovoita, jotka sisältävät linkitettyjä entiteettejä, se saattaa johtua samassa työtilassa olevasta vastaavasta, riippuvaisesta tietovuosta, joka on lukittu tietovuon päivittämisen ajaksi. Tällainen lukitus mahdollistaa tapahtumien tarkkuuden ja varmistaa, että molemmat tietovuot päivitetään, mutta se voi myös estää sinua muokkaamasta niitä. 

Jos määrität linkitetylle tietovuolle erillisen ajoituksen, tietovuo saatetaan päivittää tarpeettomasti, mikä estää sinua muokkaamasta tietovuota. Tämän ongelman välttämiseksi on kaksi suositusta: 

* Älä määritä lähdetietovuon kanssa samaan työtilaan kuuluvalle linkitetylle tietovuolle päivitysaikataulua
* Jos haluat määrittää päivitysaikataulun erikseen ja jos haluat välttää lukituksen, aseta tietovuo erilliseen työtilaan.

### <a name="create-a-separate-workspace-for-ingestion-transformation"></a>Erillisten työtilojen luominen käsittelylle ja muuntamiselle

Jos haluat antaa käyttää pohjana olevien tietovoiden tietojen käyttöoikeudet useille käyttäjille antamatta käyttöoikeutta pohjana olevan lähdejärjestelmän raakatietoihin, luo erillinen työtila, joka sisältää kaikki jaettavat tiedot, ja määritä sitten sen käyttöoikeudet. Yksittäisten tietovoiden käyttöoikeuksia ei tällä hetkellä tueta.

### <a name="ensure-capacity-is-in-the-same-region"></a>Kapasiteetin ja vuokraajan alueen vastaavuuden tarkistaminen

Tietovuot eivät tällä hetkellä tue useita maantieteellisiä alueita. Premium-kapasiteetin on oltava samalla alueella kuin Power BI -vuokraajasi.

### <a name="separate-on-premises-sources-from-cloud-sources"></a>Erilliset paikalliset lähteet pilvilähteistä

Aiemmin kuvattujen parhaiden käytäntöjen lisäksi voit luoda erillisen tietovuon kullekin lähdetyypille, kuten paikallinen, pilvipalvelu, SQL Server, Spark, Dynamics ja niin edelleen. Suosittelemme jakamaan tietovuon osiin tietolähteen tyypin mukaan. Lähdetyypin mukaan erottaminen helpottaa nopeaa vianmääritystä ja ohittaa sisäiset rajoitukset tietovoita päivittäessäsi.

### <a name="separate-dataflows-into-a-separate-capacity"></a>Tietovoiden erottaminen erilliseen kapasiteettiin

Jos törmäät rajoituksiin tai jos tietovoissasi on usein virheitä kapasiteettisi muistirajoitusten vuoksi, sinun kannattaa ehkä erottaa tietovuosi tai skaalata Premium-kapasiteettiisi lisämuistia.

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä artikkelissa annettiin tietoja tietovoihin liittyvistä parhaista käytännöistä. Jos haluat lisätietoja tietovoista, seuraavista artikkeleista voi olla hyötyä:

* [Omatoiminen tietojen valmistelu tietovoiden avulla](service-dataflows-overview.md)
* [Tietovoiden luominen ja käyttäminen Power BI:ssä](service-dataflows-create-use.md)
* [Laskettujen entiteettien käyttäminen Power BI Premiumissa](service-dataflows-computed-entities-premium.md)
* [Tietovoiden käyttö paikallisiin tietolähteisiin](service-dataflows-on-premises-gateways.md)

Katso lisätietoja Common Data Modelin (CDM) kehittämisestä ja opetusohjelmaresursseista seuraavista ohjeaiheista:
* [Common Data Model – yleiskatsaus](https://docs.microsoft.com/powerapps/common-data-model/overview)
* [CDM-kansiot](https://go.microsoft.com/fwlink/?linkid=2045304)
* [CDM-mallitiedoston määritys](https://go.microsoft.com/fwlink/?linkid=2045521)


Lisätietoja Power Querysta ja ajoitetusta päivityksestä on seuraavissa artikkeleissa:
* [Kyselyn yleiskatsaus Power BI Desktopissa](desktop-query-overview.md)
* [Ajoitetun päivityksen määrittäminen](refresh-scheduled-refresh.md)
