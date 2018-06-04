---
title: Power BI -raporttipalvelimen julkaisutiedot
description: REST-ohjelmointirajapinta tarjoaa ohjelmallinen pääsyn Power BI -raporttipalvelimen hakemiston objekteihin.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: a1cbcc6d265504bc93ef6447a6be381ca6399063
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721750"
---
# <a name="develop-with-the-rest-apis-for-power-bi-report-server"></a>Power BI -raporttipalvelimen REST-ohjelmointirajapintojen käyttö ohjelmankehityksessä
Power BI-raporttipalvelin tukee Representational State Transfer (REST) -rajapintoja. REST-ohjelmointirajapinnat ovat palvelun päätepisteitä, jotka tukevat tiettyjä HTTP-toimintoja (menetelmät), jotka tarjoavat pääsyn raporttipalvelimen sisältämien resurssien luomiseen, hakemiseen, päivittämiseen tai poistamiseen.

REST-ohjelmointirajapinta tarjoaa ohjelmallinen pääsyn Power BI -raporttipalvelimen hakemiston objekteihin. Objekteja ovat esimerkiksi kansiot, raportit, suorituskykyilmaisimet, tietolähteet, tietojoukot, päivityssuunnitelmat, tilaukset ynnä muut. REST-ohjelmointirajapinnan avulla voit esimerkiksi siirtyä kansiohierarkiassa, tutustua kansion sisältöön tai ladata raporttimäärityksen. Voit myös luoda, päivittää ja poistaa objekteja. Esimerkkejä objektien kanssa työskentelemisestä ovat raportin lataaminen, päivityssuunnitelman toteuttaminen ja niin edelleen.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-hybrid-note.md)]

## <a name="components-of-a-rest-api-requestresponse"></a>REST-ohjelmointirajapinnan pyynnön/vastauksen osat
REST-ohjelmointirajapinnan pyyntö/vastaus-pari voidaan jakaa viiteen osaan:

* **Pyynnön URI**, joka koostuu: `{URI-scheme} :// {URI-host} / {resource-path} ? {query-string}`. Vaikka pyynnön URI-tunnus on mukana pyynnön otsikossa, esitämme sen erikseen tässä, koska useimmat kielet tai kehitysmenetelmät edellyttävät sen välittämistä pyyntöviestistä erillään.
  
  * URI-protokolla: ilmaisee pyynnön välittämiseen käytetyn protokollan. Esimerkiksi `http` tai `https`.
  * URI-isäntä: määrittää toimialuenimen tai palvelimen IP-osoitteen, jossa REST-palvelupäätepiste sijaitsee, kuten `myserver.contoso.com`.
  * Resurssipolku: määrittää resurssin tai resurssikokoelman ja saattaa sisältää useita segmenttejä, joita palvelu käyttää kyseisten resurssien valinnassa. Esimerkiksi: `CatalogItems(01234567-89ab-cdef-0123-456789abcdef)/Properties` soveltuu CatalogItemin määriteltyjen ominaisuuksien hakemiseen.
  * Kyselyn merkkijono (valinnainen): tarjoaa yksinkertaisia parametreja, kuten ohjelmointirajapinnan versio- tai resurssinvalintaehdot.
* HTTP-pyyntöviestin otsikkokentät:
  
  * Pakollinen [HTTP-menetelmä](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) (tunnetaan myös nimellä toiminto tai verbitoiminto), joka kertoo palvelulle minkä tyyppinen pyytämäsi toiminnon on. Reporting Services REST-ohjelmointirajapinnat tukevat menetelmiä DELETE, GET, HEAD, PUT, POST ja PATCH.
  * Valinnaisia muita otsikkokenttiä, joita tietty URI- ja HTTP-menetelmä vaatii.
* Valinnaiset HTTP-**pyyntöviestin tekstikentät**, jotka tukevat URI- ja HTTP-toimintoja. Esimerkiksi POST-toiminnot sisältävät MIME-koodattuja objekteja, jotka monimutkaisina parametreina ohitetaan. POST- tai PUT-toiminnoissa tulee tekstiosan MIME-koodaustyyppi määritellä myös `Content-type`pyyntöotsikossa. Jotkin palvelut edellyttävät, että käytät tiettyä MIME-tyyppiä, kuten `application/json`.
* HTTP-**-vastausviestiotsikon** kentät:
  
  * [HTTP-tilakoodi](http://www.w3.org/Protocols/HTTP/HTRESP.html), joka voi olla aina 2xx-onnistumiskoodeista 4xx- tai 5xx-virhekoodeihin. Vaihtoehtoisesti saatetaan palauttaa palvelun määrittämä tilakoodi, kuten esitetty rajapinnan dokumentaatiossa.
  * Valinnaisia muita otsikkokenttiä sen mukaan, mitä tarvitaan tukemaan pyynnön vastausta, kuten `Content-type`vastausotsikko.
* Valinnainen HTTP**vastausviestin tekstiosan** kentät:
  
  * MIME-koodatut vastausobjektit palautetaan HTTP-vastauksen tekstiosassa, kuten tiedot palauttava GET-menetelmän vastaus. Yleensä nämä objektit palautetaan jäsennellyssä muodossa, kuten JSON tai XML, jota on merkitty `Content-type` vastauksen otsikkoon.

## <a name="api-documentation"></a>Rajapintadokumentaatio
Nykyaikainen REST-rajapinta vaatii nykyaikaisen rajapintadokumentaation. REST-rajapinta perustuu OpenAPI-määritykseen (tunnetaan swagger-määrityksenä) ja ohjeita on käytettävissä [SwaggerHubissa](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0). Rajapinnan dokumentoinnin lisäksi SwaggerHub auttaa luomaan asiakaskirjaston valitulla ohjelmointikielellä – JavaScript, TypeScript, C#, Java, Python, Ruby ja monia muita.

## <a name="testing-api-calls"></a>API-kutsujen testaaminen
[Fiddler](http://www.telerik.com/fiddler) on työkalu, jolla voidaan testata HTTP-pyyntö/vastausviestejä. Fiddler on maksuton virheenkorjausvälityspalvelin verkossa, joka voi siepata REST-pyynnöt, mikä tekee HTTP-pyyntö/vastausviestien vianmäärityksestä helppoa.

## <a name="next-steps"></a>Seuraavat vaiheet
Selaa [SwaggerHubissa](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0) käytettävissä olevia rajapintoja.

Esimerkkejä ovat käytettävissä [GitHubissa](https://github.com/Microsoft/Reporting-Services). Malleihin lukeutuu TypeScriptillä, Reactillä ja verkkopaketilla rakennettu HTML5-sovellus sekä PowerShell-esimerkki.

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

