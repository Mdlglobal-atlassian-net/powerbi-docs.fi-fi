---
title: Entiteettien linkittäminen tietovoiden välillä Power BI:ssä
description: Lue, miten voit linkittää entiteetit tietovoissa Power BI:ssä
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/06/2018
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 4331878aee591f9e3939c0bb1c239eca160ee61d
ms.sourcegitcommit: 80961ace38ff9dac6699f81fcee0f7d88a51edf4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/13/2019
ms.locfileid: "56223647"
---
# <a name="link-entities-between-dataflows-in-power-bi-preview"></a>Entiteettien linkittäminen tietovoiden välillä Power BI:ssä (esikatselu)

Power BI:n tietovoiden ansiosta voit saada yhden organisatoristen tietojen säilön lähteen, jossa yritysanalyytikot voivat valmistella ja hallita tietoja kertaheitolla ja sitten käyttää niitä uudelleen eri analyysisovellusten välillä organisaatiossa. 

Kun linkität entiteettejä tietovoiden välillä, voit käyttää uudelleen entiteettejä, joita muiden omistamat muut tietovuot ovat jo käsitelleet, puhdistaneet ja muuntaneet, ilman näiden tietojen ylläpitämistä. Linkitetyt entiteetit vain osoittavat entiteetteihin muissa tietovoissa, *eivätkä* ne kopioi tai monista tietoja.

![Linkitetyt entiteetit Power BI:ssä](media/service-dataflows-linked-entities/linked-entities_00.png)

Linkitetyt entiteetit ovat **vain luku** -tilassa. Jos haluat luoda linkitetyn entiteetin muunnoksia, sinun on luotava uusi laskettu entiteetti, joka viittaa linkitettyyn entiteettiin.

## <a name="linked-entity-availability"></a>Linkitetyn entiteetin saatavuus

Linkitettyjen entiteettien päivitys edellyttää [Power BI Premium](service-premium.md) -tilausta. Linkitetyt entiteetit ovat saatavilla missä tahansa tietovuossa työtilassa, jota isännöidään Power BI Premium -kapasiteetissa. Lähteen tietovuohon ei liity rajoituksia.

Linkitetyt entiteetit toimivat kunnolla vain uusissa Power BI -työtiloissa. Lue lisää [uusista Power BI -työtiloista](service-create-the-new-workspaces.md). Kaikkien linkitettyjen tietovoiden on sijaittava uusissa työtiloissa, jotta ne toimivat kunnolla.

> [!NOTE]
> Entiteetit eroavat sen mukaan, ovatko ne vakioentiteettejä vai laskettuja entiteettejä. Vakioentiteetit (joita nimitetään usein vain entiteeteiksi) kyselevät ulkoisesta tietolähteestä, kuten SQL-tietokannasta. Lasketut entiteetit edellyttävät Power BI:n Premium-kapasiteettia ja soveltavat muunnoksia Power BI -säilössä jo oleviin tietoihin. 
>
>Jos tietovuo ei ole Premium-kapasiteetin työtilassa, voit edelleen viitata yksittäiseen kyselyyn tai yhdistää kaksi kyselyä tai useamman kyselyn, kunhan muunnoksia ei määritetä säilön sisäisiksi muunnoksiksi. Tällaisia viittaukset pidetään vakioentiteetteinä. Poista tässä tapauksessa käytöstä **Ota lataus käyttöön** -vaihtoehto viitatuille kyselyille, jotta tietoja ei muodosteta eikä niitä sisällytetä säilöön. Voit täältä viitata näihin **Ota lataus käyttöön = epätosi** -kyselyihin ja määrittää **Ota lataus käyttöön** -vaihtoehdon arvoksi **Käytössä** vain niille tuloksena saaduille kyselyille, jotka haluat muodostaa.


## <a name="how-to-link-entities-between-dataflows"></a>Entiteettien linkittäminen tietovoiden välillä

Entiteettejä voi linkittää parilla tavalla tietovoiden välillä Power BI:ssä. Voit valita **Lisää linkitetyt entiteetit** tietovoiden luontityökalusta seuraavan kuvan mukaisesti. 

![Linkitetyt entiteetit Power BI:ssä](media/service-dataflows-linked-entities/linked-entities_00.png)

Voit myös valita **Lisää linkitetyt entiteetit** **Lisää entiteetit** -valikkovaihtoehdosta Power BI -palvelussa.

![Linkitetyt entiteetit Power BI:ssä](media/service-dataflows-linked-entities/linked-entities_01.png)

Jotta voit linkittää entiteetit, sinun on kirjauduttava sisään Power BI:n tunnistetiedoilla.

Esiin avautuu **Siirtymistoiminto**-ikkuna, jossa voit valita entiteetit, joihin muodostat yhteyden. Näytetyt entiteetit ovat entiteettejä, joihin sinulla on käyttöoikeudet Power BI -vuokraajasi kaikissa työtiloissa. 

Kun olet valinnut linkitetyt entiteetit, ne näkyvät tietovuon entiteettiluettelossa luontityökalussa ja ne on merkitty erityisellä kuvakkeella linkitetyiksi entiteeteiksi.

Voit myös tarkastella lähteen tietovuota linkitetyn entiteetin tietovuon asetuksista.

## <a name="refresh-logic-of-linked-entities"></a>Linkitettyjen entiteettien päivityslogiikka
Linkitettyjen entiteettien oletuspäivityslogiikka muuttuu sen mukaan, sijaitseeko lähteen tietovuo samassa työtilassa kohteen tietovuossa. Seuraavissa osioissa kuvataan kunkin logiikan toimintaa.

### <a name="links-between-workspaces"></a>Työtilojen väliset linkit

Linkkien päivitys eri työtilojen entiteeteistä toimii kuten ulkoinen tietolähde. Kun tietovuo päivitetään, se poimii entiteetin uusimmat tiedot lähteen tietovuosta. Jos lähteen tietovuo päivitetään, se ei automaattisesti vaikuta kohteen tietovuon tietoihin.

### <a name="links-in-the-same-workspace"></a>Linkit samassa työtilassa

Kun lähteen tietovuon tietoja päivitetään, tapahtuma käynnistää automaattisesti riippuvaisten entiteettien päivitysprosessin kaikissa kohteen tietovoissa samassa työtilassa, mukaan lukien niihin perustuvat mahdolliset lasketut entiteetit. Kohteen tietovuon kaikki muut entiteetit päivitetään tietovuon aikataulun mukaisesti. Entiteetit, jotka riippuvat useammasta kuin yhdestä lähteestä, päivittävät tietonsa aina, kun jokin niiden lähteistä päivitetään onnistuneesti.

On hyödyllistä panna merkille, että koko päivitysprosessi suoritetaan kerralla. Sen vuoksi, jos kohteen tietovuon päivitys ei onnistu, lähteen tietovuota ei voida myöskään päivittää.

## <a name="permissions-when-viewing-reports-from-dataflows"></a>Käyttöoikeudet tarkasteltaessa raportteja tietovoista

Kun luot Power BI -raportin, joka sisältää tietovuohon perustuvia tietoja, käyttäjät voivat nähdä linkitetyt entiteetit vain, kun käyttäjällä on lähteen tietovuon käyttöoikeudet.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Linkitettyjen entiteettien käsittelyn aikana on hyvä pitää mielessä pari rajoitusta:

* Viitehyppyjä voi olla korkeintaan viisi
* Linkitettyjen entiteettien syklisiä riippuvuuksia ei sallita
* Tietovuon on sijaittava [uudessa Power BI -työtilassa](service-create-the-new-workspaces.md)


## <a name="next-steps"></a>Seuraavat vaiheet

Seuraavista artikkeleista voi olla hyötyä, kun luot tai käsittelet tietovoita. 

* [Omatoiminen tietojen valmisteleminen Power BI:ssä (esikatselu)](service-dataflows-overview.md)
* [Tietovoiden luominen ja käyttäminen Power BI:ssä](service-dataflows-create-use.md)
* [Laskettujen entiteettien käyttäminen Power BI Premiumissa (esikatselu)](service-dataflows-computed-entities-premium.md)
* [Tietovoiden käyttäminen paikallisten tietolähteiden kanssa (esikatselu)](service-dataflows-on-premises-gateways.md)
* [Kehittäjien resurssit Power BI -tietovoille (esikatselu)](service-dataflows-developer-resources.md)

Lisätietoja Power Querysta ja ajoitetusta päivityksestä on seuraavissa artikkeleissa:
* [Kyselyn yleiskatsaus Power BI Desktopissa](desktop-query-overview.md)
* [Ajoitetun päivityksen määrittäminen](refresh-scheduled-refresh.md)

Lisätietoja Common Data Modelista on sen yleiskatsauksen sisältävässä artikkelissa:
* [Common Data Model – yleiskatsaus](https://docs.microsoft.com/powerapps/common-data-model/overview)

