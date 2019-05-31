---
title: Q&A:n käyttäminen reaaliaikaisten yhteyksien kautta Power BI:ssä
description: 'Dokumentaatio Power BI Q & A: n kyselyjä luonnollisella kielellä reaaliaikaisia yhteyksiä Analysis Services-tietoihin ja paikallisen tietoyhdyskäytävän avulla.'
author: maggiesMSFT
manager: kfile
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 9836cd88bef5066f61a8ae44eabe7685196e2bed
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65624935"
---
# <a name="enable-qa-for-live-connections-in-power-bi"></a>Q&A:n ottaminen käyttöön reaaliaikaisia yhteyksiä varten Power BI:ssä
## <a name="what-is-the-on-premises-data-gateway--what-is-a-live-connection"></a>Mikä on paikallinen tietoyhdyskäytävä?  Mikä on reaaliaikainen yhteys?
Power BI ‑tietojoukkoja voi joko tuoda Power BI:hin tai niihin voi luoda reaaliaikaisen yhteyden. Reaaliaikainen yhteys tietojoukkoja viitataan usein nimellä ”paikalliseen”. Reaaliaikaisia yhteyksiä hallitaan käyttämällä [yhdyskäytävää](service-gateway-onprem.md), ja tietoja ja kyselyitä lähetetään edestakaisin käyttämällä reaaliaikaisia kyselyjä.

## <a name="qa-for-on-premises-data-gateway-datasets"></a>Q & A paikallisen tietoyhdyskäytävän tietojoukot
Jos haluat käyttää Q&A:ta sellaisten tietojoukkojen kanssa, joita käytät yhdyskäytävän kautta, sinun on ensin otettava ne käyttöön.

Kun ne on otettu käyttöön, Power BI luo tietolähteestäsi indeksin ja lataa tiedoista alijoukon Power BI:hin, jotta voit esittää kysymyksiä. Ensimmäisen indeksin luomiseen voi kulua useita minuutteja. Power BI ylläpitää indeksiä ja päivittää sen automaattisesti tietojen muuttuessa. Q&A:n käyttö tällaisten tietojoukkojen kanssa toimii samalla tavalla kuin Power BI:hin julkaistujen tietojen kanssa. Molemmat tavat tukevat täyttä Q&A-kokemusta, myös tietolähteen käyttöä yhdessä Cortanan välityksellä.

Kun esität kysymyksiä Power BI:ssä, Q&A määrittää tietojoukkosi indeksiä käyttämällä parhaan visualisoinnin tai raportintaulukon, joka vastaisi kysymykseesi. Määritettyään parhaan mahdollisen vastauksen Q&A noutaa DirectQueryn avulla yhdyskäytävän kautta reaaliaikaiset tiedot tietolähteestä ja täyttää kaaviot tiedoilla. Se tarkoittaa, että Power BI:n Q&A-tuloksissa esitetään aina ajantasaiset tiedot suoraan pohjana olevasta tietolähteestä.

Koska Power BI:n Q&A käyttää tietolähteestä peräisin olevia teksti- ja rakennearvoja määrittämään, miten pohjana olevaan malliin tehdään kysely, tiettyjä uusia tai poistettuja tekstiarvoja koskevat haut (esimerkiksi pyyntö hiljattain lisättyyn tekstitietueeseen liittyvästä asiakkaan nimestä) ovat riippuvaisia siitä, että indeksin arvot ovat ajan tasalla. Power BI pitää automaattisesti teksti- ja rakenneindeksin ajan tasalla 60 minuutin muutosikkunalla.

Lisätietoja:

* Mikä [paikallisen tietoyhdyskäytävän](service-gateway-onprem.md)?
* [Power BI Q & A: n kuluttajille](consumer/end-user-q-and-a.md)

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
Ominaisuudella on joitakin rajoituksia:

* Aluksi ominaisuus on käytettävissä vain taulukkomuotoisille SQL Server 2016 Analysis Services  ‑tietolähteille. Ominaisuus on optimoitu toimimaan taulukkomuotoisten tietojen kanssa. Q & A-käyttökokemus ei vielä tueta monidimensioisena. Muita tietolähteitä paikallisen tietoyhdyskäytävän tukemia tarjolle ajan kuluessa.
* Täysi tuki rivitason suojaukselle SQL Server Analysis Services ei ole käytettävissä alun perin. Kun esittää kysymyksiä Q & A ”automaattinen täydennys” aikana kirjoittamalla näyttää merkkijonoarvoja käyttäjä, joihin ei voi käyttää. Mallissa määritettyä rivitason suojausta kuitenkin kunnioitetaan raporttien ja kaaviovisualisointien osalta, eli taustalla olevia numeerisia tietoja ei paljastu. Tulevissa päivityksissä julkaistaan asetukset, joilla tätä käytöstä voi hallita.
* Objektin rivitason suojaus (OLS) ei tueta. Q & A ei noudattaa objektin rivitason suojaus ja voi paljastaa taulukko tai sarakkeiden nimiä käyttäjille, joilla ei ole niihin käyttöoikeutta. Sinun on otettava käyttöön rivitason suojaus (RSL) sen varmistamiseksi, että myös data-arvot suojataan asianmukaisesti. 
* Reaaliaikaisia yhteyksiä tuetaan vain paikallisen tietoyhdyskäytävän kanssa. Tämän vuoksi tämä ei voi käyttää henkilökohtaisen yhdyskäytävän kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet

- [On-premises data gateway (Paikallinen tietoyhdyskäytävä)](service-gateway-onprem.md)  
- [Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
- [Power BI: Peruskäsitteet](consumer/end-user-basic-concepts.md)  
- [Yleiskatsaus Power BI Q&A:sta](consumer/end-user-q-and-a.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

