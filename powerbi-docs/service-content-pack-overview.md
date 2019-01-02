---
title: Power BI -palvelun sisältöpakettiohjelman yleiskatsaus
description: Sisältöpakettisertifiointiohjelma
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/20/2018
ms.author: maggies
ms.openlocfilehash: f97393a8a7fe8dc9c413a0cb0cda8be0e965da5b
ms.sourcegitcommit: 6c6aa214dc36c26a01b29e823598d217a3e2b8a1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/17/2018
ms.locfileid: "53451348"
---
# <a name="overview-of-the-power-bi-service-content-pack-program"></a>Power BI -palvelun sisältöpakettiohjelman yleiskatsaus
Sisältöpaketti on joukko valmista sisältöä, jonka avulla käyttäjät saavat välittömästi merkityksellistä tietoa lähteestä. Sisältöpaketti keskittyy yleensä tiettyyn liiketoimintaskenaarioon ja tarjoaa rooli-, toimialue- tai työnkulkukohtaista merkityksellistä tietoa.

Riippumattomat ohjelmistokehittäjät voivat luoda mallisisältöpaketteja, joiden avulla asiakkaat voivat yhdistää ja alustaa tiedot omiin tileihinsä. Toimialueen asiantuntijoina he voivat avata tietojen lukituksen siten, että ne ovat helposti yrityskäyttäjien käytettävissä. Sisältöpaketit tarjoavat asiakkaille räätälöityjä seuranta- ja analyysitoimintoja ilman raskaita investointeja raportointi-infrastruktuuriin.

Nämä riippumattomien ohjelmistokehittäjien luomat mallisisältöpaketit voidaan lähettää Power BI -tiimille, jotta ne olisivat julkisesti käytettävissä Power BI -sisältöpakettivalikoimassa (app.powerbi.com/getdata/services) ja Microsoft AppSourcessa (appsource.microsoft.com). Esimerkki julkisen sisältöpaketin käyttökokemuksesta on nähtävissä [täällä](template-content-pack-experience.md).

## <a name="overview"></a>Yleiskatsaus
Yleinen prosessi mallisisältöpaketin kehittämiseksi ja lähettämiseksi sisältää useita vaiheita.

 ![Prosessi](media/service-content-pack-overview/developer-content-pack-overview.png)

1. [Tarkista edellytykset](#requirements) ja varmista, että täytät ne
2. [Luo sisältö](template-content-pack-authoring.md#queries) Power BI Desktopissa
3. [Luo koontinäyttö](template-content-pack-authoring.md#dashboard) Power BI.comissa
4. [Testaa sisältöpaketti](template-content-pack-testing.md) itse organisaatiossa
5. [Lähetä](template-content-pack-testing.md#submission) sisältö Power BI:hin julkaisua varten

<a name="requirements"></a>

## <a name="requirements"></a>Vaatimukset
Jotta voit luoda sisältöpaketin ja lähettää sen julkaistavaksi Power BI -palveluun ja AppSourceen, sinun on täytettävä seuraavat vaatimukset:

* Sinulla on yrityskäyttöön tarkoitettu SaaS-sovellus.
* SaaS-sovelluksessasi on käyttäjätietoja, jotka voidaan visualisoida Power BI:ssä.
* SaaS-sovelluksellasi on ohjelmointirajapinta, jota voidaan käyttää julkisen internetin kautta. Ohjelmointirajapinta on ihannetapauksessa REST-pohjainen ohjelmointirajapinta tai OData-syöte. Power BI -sisältöpaketit tukevat useita todennustyyppejä, kuten perustodentamista, OAuth 2.0 -todentamista ja ohjelmointirajapinnan avainta. 
* SaaS-sovelluksesi on hyväksytty sisältöpaketin julkaisemiseen. Lähetä pyyntösi osoitteeseen pbiservicesapps@microsoft.com. Tarkistamme jokaisen lähetetyn pyynnön merkityksellisyyden ja oletetun käyttötavan. 
* Allekirjoitettu kumppanisopimus. Teet tämän [lähetysvaiheessa](template-content-pack-testing.md#submission).

Katso [sisällön tuottamista](template-content-pack-authoring.md) koskevasta osiosta lisätietoja teknisistä vaatimuksista.

## <a name="business-scenario"></a>Liiketoimintaskenaario
Sisältöpaketit tarjoavat käyttöön merkityksellisiä tietoja ja mittareita, jotka keskittyvät tiettyyn liiketoimintaskenaarioon. Tuntemalla yleisösi ja ymmärtämällä, miten he hyötyvät sisältöpaketista, varmistat, että käyttäjät voivat käyttää sisältöä menestyksekkäästi.

### <a name="tips"></a>Vinkkejä
* Identifioi yleisösi ja tehtävä, jonka he haluavat suorittaa.  
* Keskity tiettyyn ajanjaksoon (edelliset 90 päivää) tai tiettyyn määrään viimeisimpiä tuloksia.  
* Tuo vain skenaarioosi liittyvät taulukot tai sarakkeet.  
* Harkitse useamman kuin yhden sisältöpaketin tarjoamista erillisiä ainutkertaisia skenaarioita varten.  

## <a name="frequently-asked-questions"></a>Usein kysyttyjä kysymyksiä
**Voinko kolmannen osapuolen ominaisuudessa luoda Power BI -palvelun sisältöpaketin SaaS-sovellukselle, jota en omista?**

Edellytämme kumppanisopimuksen allekirjoittamista SaaS-sovelluksen omistajan kanssa ennen sisältöpaketin julkaisemista palvelussa. Kolmantena osapuolena sinun on huolehdittava kumppanisopimuksen allekirjoittamisesta SaaS-sovelluksen omistajan kanssa.

**Minulla ei ole julkista kehittäjän ohjelmointirajapintaa palvelulleni. Voinko edelleen luoda Power BI -palvelun sisältöpaketin, joka hakee tiedot suoraan tallennusvälineestä?**

Ei, Power BI -palvelun sisältöpaketit vaativat kehittäjän ohjelmointirajapinnan, joka on käytettävissä kautta julkisen internetin välityksellä.

**Millaisia ohjelmointirajapintoja palvelun sisältöpaketit tukevat ja millaisten todennustyyppien kanssa ne voivat toimia?**

Power BI -palvelun sisältöpaketit tukevat mitä tahansa REST-ohjelmointirajapintaa tai OData-syötettä. Power BI:n kanssa voidaan käyttää useita eri todennustyyppejä, kuten perustodentamista, OAuth2.0 -todennusta ja verkkopalvelujen ohjelmointirajapinnan avainta. Artikkelissa [Sisällön tuottaminen](template-content-pack-authoring.md#dashboard) on lisätietoja teknisistä vaatimuksista.

**Minulla on Power BI:ssä julkaistu sisältöpaketti. Miten voin päivittää sen?**

Julkaistut sisältöpaketit voidaan päivittää kerran kuukaudessa. Päivityspyynnöt, jotka lähetetään osoitteeseen [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com) ennen kuluvan kuukauden viimeistä päivää, julkaistaan seuraavan kuukauden ensimmäisellä viikolla.

**Minulla on enemmän kysymyksiä palvelun sisältöpaketeista. Miten voin ottaa teihin yhteyttä?**

Voit lähettää kysymyksesi meille sähköpostilla osoitteeseen [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com)

## <a name="support"></a>Tuki
Saat tukea kehityksen aikana osoitteesta [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support). Asiakastapaukset ohjataan nopeasti oikealle tiimille.

## <a name="next-step"></a>Seuraava vaihe
[Sisällön tuottaminen](template-content-pack-authoring.md)