---
title: Q&A:n käyttäminen reaaliaikaisten yhteyksien kautta
description: Dokumentaatio Power BI:n Q&A-toiminnon käyttämiseen luonnollisella kielellä ilmaistujen kyselyiden esittämistä varten, kun käytössä on reaaliaikainen yhteys Analysis Services ‑tietoihin sekä paikalliseen tietoyhdyskäytävään.
author: mihart
manager: kfile
ms.reviewer: mihart
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 7402bc638f27175e1c8e1f733fefd508850d9943
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34245578"
---
# <a name="enable-qa-for-live-connections"></a>Q&A:n ottaminen käyttöön reaaliaikaisia yhteyksiä varten
## <a name="what-is-on-premises-data-gateway--what-is-a-live-connection"></a>Mikä on paikallinen tietoyhdyskäytävä?  Mikä on reaaliaikainen yhteys?
Power BI ‑tietojoukkoja voi joko tuoda Power BI:hin tai niihin voi luoda reaaliaikaisen yhteyden. Tietojoukkoja, joihin on reaaliaikainen yhteys, kutsutaan usein ”paikallisiksi”. Reaaliaikaisia yhteyksiä hallitaan käyttämällä [yhdyskäytävää](service-gateway-onprem.md), ja tietoja ja kyselyitä lähetetään edestakaisin käyttämällä reaaliaikaisia kyselyjä.

## <a name="qa-for-on-premises-data-gateway-datasets"></a>Q&A ja paikallisen tietoyhdyskäytävän tietojoukot
Jos haluat käyttää Q&A:ta sellaisten tietojoukkojen kanssa, joita käytät yhdyskäytävän kautta, sinun on ensin otettava ne käyttöön.

Kun ne on otettu käyttöön, Power BI luo tietolähteestäsi indeksin ja lataa tiedoista alijoukon Power BI:hin, jotta voit esittää kysymyksiä. Ensimmäisen indeksin luomiseen voi kulua useita minuutteja. Power BI ylläpitää indeksiä ja päivittää sen automaattisesti tietojen muuttuessa. Q&A:n käyttö tällaisten tietojoukkojen kanssa toimii samalla tavalla kuin Power BI:hin julkaistujen tietojen kanssa. Molemmat tavat tukevat täyttä Q&A-kokemusta, myös tietolähteen käyttöä yhdessä Cortanan välityksellä.

Kun esität kysymyksiä Power BI:ssä, Q&A määrittää tietojoukkosi indeksiä käyttämällä parhaan visualisoinnin tai raportintaulukon, joka vastaisi kysymykseesi. Määritettyään parhaan mahdollisen vastauksen Q&A noutaa DirectQueryn avulla yhdyskäytävän kautta reaaliaikaiset tiedot tietolähteestä ja täyttää kaaviot tiedoilla. Se tarkoittaa, että Power BI:n Q&A-tuloksissa esitetään aina ajantasaiset tiedot suoraan pohjana olevasta tietolähteestä.

Koska Power BI:n Q&A käyttää tietolähteestä peräisin olevia teksti- ja rakennearvoja määrittämään, miten pohjana olevaan malliin tehdään kysely, tiettyjä uusia tai poistettuja tekstiarvoja koskevat haut (esimerkiksi pyyntö hiljattain lisättyyn tekstitietueeseen liittyvästä asiakkaan nimestä) ovat riippuvaisia siitä, että indeksin arvot ovat ajan tasalla. Power BI pitää automaattisesti teksti- ja rakenneindeksin ajan tasalla 60 minuutin muutosikkunalla.

Lisätietoja:

* Mikä on [paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)?
* [Johdatus Power BI:n Q&A-toimintoon](power-bi-q-and-a.md)

## <a name="enable-qa"></a>Q&A:n ottaminen käyttöön
Kun olet määrittänyt tietoyhdyskäytävän, muodosta sen kautta yhteys tietoihisi Power BI:ssä.  Voit joko luoda koontinäytön käyttämällä paikallisia tietoja tai ladata .pbix-tiedoston, joka käyttää paikallisia tietoja.  Sinulla voi olla myös valmiiksi paikallisia tietoja koontinäytöissä, raporteissa ja tietojoukoissa, jotka on jaettu sinulle.

1. Valitse Power BI:n oikeasta yläkulmasta hammasrataskuvake ![hammasrataskuvake](media/service-q-and-a-direct-query/power-bi-cog.png) ja valitse **Asetukset**.
   
   ![Asetukset-valikko](media/service-q-and-a-direct-query/powerbi-settings.png)
2. Valitse **Tietojoukot** ja valitse sitten tietojoukko, jota haluat hyödyntää Q&A-toiminnossa.
   
   ![Asetukset-valikon tietojoukkonäkymä](media/service-q-and-a-direct-query/power-bi-q-and-a-settings.png)
3. Laajenna kohta **Q&A ja Cortana**, valitse valintaruutu **Ota Q&A käyttöön tässä tietojoukossa** ja valitse **Käytä**.
   
    ![Q&A-alue laajennettuna](media/service-q-and-a-direct-query/power-bi-q-and-a-directquery.png)

## <a name="what-data-is-cached-and-how-is-privacy-protected"></a>Tietojen tallentaminen välimuistiin ja yksityisyydensuoja
Kun otat Q&A:n käyttöön paikallisissa tiedoissa, osa tiedoista tallennetaan palvelun välimuistiin. Se varmistaa Q&A:n kohtuullisen suorituskyvyn. Power BI jättää välimuistista pois arvot, jotka ovat yli 24 merkkiä pitkiä. Välimuisti poistetaan muutaman tunnin kuluessa siitä, kun poistat Q&A :n käytöstä poistamalla valintamerkin kohdasta **Ota Q&A käyttöön tässä tietojoukossa** tai kun poistat tietojoukon.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Tämän ominaisuuden esikatseluvaiheessa on useita rajoituksia:

* Aluksi ominaisuus on käytettävissä vain taulukkomuotoisille SQL Server 2016 Analysis Services  ‑tietolähteille. Ominaisuus on optimoitu toimimaan taulukkomuotoisten tietojen kanssa. Jotkin toiminnot ovat käytettävissä monidimensioisille tietolähteille, mutta täyttä Q&A-käyttökokemusta ei vielä tueta monidimensioisena. Paikallisen tietoyhdyskäytävän tukemia tietolähteitä tuodaan lisää tarjolle ajan kuluessa.
* SQL Server Analysis Services ‑palvelussa määritetylle rivitason suojaukselle ei ole aluksi saatavilla täyttä tukea julkisessa esikatselussa. Kun Q&A:ssa esitetään kysymyksiä, tekstin automaattinen täydennys saattaa kirjoittamisen aikana näyttää merkkijonoarvoja, joihin käyttäjällä ei ole käyttöoikeutta. Mallissa määritettyä rivitason suojausta kuitenkin kunnioitetaan raporttien ja kaaviovisualisointien osalta, eli taustalla olevia numeerisia tietoja ei paljastu. Tulevissa päivityksissä julkaistaan asetukset, joilla tätä käytöstä voi hallita.
* Reaaliaikaisia yhteyksiä tuetaan vain paikallisen tietoyhdyskäytävän kanssa. Niitä ei voi käyttää henkilökohtaisen yhdyskäytävän kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet
[Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)  
[Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Power BI:n peruskäsitteet](service-basic-concepts.md)  
[Yleiskatsaus Power BI Q&A:sta](power-bi-q-and-a.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

