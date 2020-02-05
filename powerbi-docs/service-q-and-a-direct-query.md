---
title: Q&A:n käyttäminen reaaliaikaisten yhteyksien kautta Power BI:ssä
description: Dokumentaatio Power BI:n Q&A-toiminnon käyttämiseen luonnollisella kielellä ilmaistujen kyselyiden esittämistä varten, kun käytössä on reaaliaikainen yhteys Analysis Services -tietoihin sekä paikalliseen tietoyhdyskäytävään.
author: maggiesMSFT
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: cf1d67318fc86b1044e38e6f4f5f56c9473c39a1
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/04/2020
ms.locfileid: "74265472"
---
# <a name="enable-qa-for-live-connections-in-power-bi"></a>Q&A:n ottaminen käyttöön reaaliaikaisia yhteyksiä varten Power BI:ssä
## <a name="what-is-the-on-premises-data-gateway--what-is-a-live-connection"></a>Mikä on paikallinen tietoyhdyskäytävä?  Mikä on reaaliaikainen yhteys?
Power BI ‑tietojoukkoja voi joko tuoda Power BI:hin tai niihin voi luoda reaaliaikaisen yhteyden. Tietojoukkoja, joihin on reaaliaikainen yhteys, kutsutaan usein ”paikallisiksi”. Reaaliaikaisia yhteyksiä hallitaan käyttämällä [yhdyskäytävää](service-gateway-onprem.md), ja tietoja ja kyselyitä lähetetään edestakaisin käyttämällä reaaliaikaisia kyselyjä.

## <a name="qa-for-on-premises-data-gateway-datasets"></a>Q&A ja paikallisen tietoyhdyskäytävän tietojoukot
Jos haluat käyttää Q&A:ta sellaisten tietojoukkojen kanssa, joita käytät yhdyskäytävän kautta, sinun on ensin otettava ne käyttöön.

Kun ne on otettu käyttöön, Power BI luo tietolähteestäsi indeksin ja lataa tiedoista alijoukon Power BI:hin, jotta voit esittää kysymyksiä. Ensimmäisen indeksin luomiseen voi kulua useita minuutteja. Power BI ylläpitää indeksiä ja päivittää sen automaattisesti tietojen muuttuessa. Q&A:n käyttö tällaisten tietojoukkojen kanssa toimii samalla tavalla kuin Power BI:hin julkaistujen tietojen kanssa. Molemmat tavat tukevat täyttä Q&A-käyttöä.

Kun esität kysymyksiä Power BI:ssä, Q&A määrittää tietojoukkosi indeksiä käyttämällä parhaan visualisoinnin tai raportintaulukon, joka vastaisi kysymykseesi. Määritettyään parhaan mahdollisen vastauksen Q&A noutaa DirectQueryn avulla yhdyskäytävän kautta reaaliaikaiset tiedot tietolähteestä ja täyttää kaaviot tiedoilla. Tämän johdosta Power BI:n Q&A:ssa näytetään aina ajantasaiset tiedot suoraan pohjana olevasta tietolähteestä.

Koska Power BI:n Q&A käyttää tietolähteestä peräisin olevia teksti- ja rakennearvoja määrittämään, miten pohjana olevaan malliin tehdään kysely, tiettyjä uusia tai poistettuja tekstiarvoja koskevat haut (esimerkiksi pyyntö hiljattain lisättyyn tekstitietueeseen liittyvästä asiakkaan nimestä) ovat riippuvaisia siitä, että indeksin arvot ovat ajan tasalla. Power BI pitää automaattisesti teksti- ja rakenneindeksin ajan tasalla 60 minuutin muutosikkunalla.

Lisätietoja:

* Mikä on [paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)?
* [Power BI -Q&A kuluttajille](consumer/end-user-q-and-a.md)

## <a name="enable-qa"></a>Q&A:n ottaminen käyttöön
Kun olet määrittänyt tietoyhdyskäytävän, muodosta sen kautta yhteys tietoihisi Power BI:ssä.  Voit joko luoda koontinäytön käyttämällä paikallisia tietoja tai ladata .pbix-tiedoston, joka käyttää paikallisia tietoja.  Sinulla voi olla myös valmiiksi paikallisia tietoja koontinäytöissä, raporteissa ja tietojoukoissa, jotka on jaettu sinulle.

1. Valitse Power BI:n oikeasta yläkulmasta hammasrataskuvake ![hammasrataskuvake](media/service-q-and-a-direct-query/power-bi-cog.png) ja valitse **Asetukset**.
   
   ![Asetukset-valikko](media/service-q-and-a-direct-query/powerbi-settings.png)
2. Valitse **Tietojoukot** ja valitse sitten tietojoukko, jota haluat hyödyntää Q&A-toiminnossa.
   
   ![Asetukset-valikon tietojoukkonäkymä](media/service-q-and-a-direct-query/power-bi-q-and-a-settings.png)
3. Laajenna **Q&A**-kohta, valitse valintaruutu **Ota Q&A käyttöön tässä tietojoukossa** ja valitse **Käytä**.
   
    ![Q&A-alue laajennettuna](media/service-q-and-a-direct-query/power-bi-qna-dataset-direct-query.png)

## <a name="what-data-is-cached-and-how-is-privacy-protected"></a>Tietojen tallentaminen välimuistiin ja yksityisyydensuoja
Kun otat Q&A:n käyttöön paikallisissa tiedoissa, osa tiedoista tallennetaan palvelun välimuistiin. Tämä välimuistitallennus varmistaa Q&A:n kohtuullisen suorituskyvyn. Power BI jättää välimuistista pois arvot, jotka ovat yli 24 merkkiä pitkiä. Välimuisti poistetaan muutaman tunnin kuluessa siitä, kun poistat Q&A :n käytöstä poistamalla valintamerkin kohdasta **Ota Q&A käyttöön tässä tietojoukossa** tai kun poistat tietojoukon.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Ominaisuudella on joitakin rajoituksia:

* Aluksi ominaisuus on käytettävissä vain taulukkomuotoisille SQL Server 2016 Analysis Services  ‑tietolähteille. Ominaisuus on optimoitu toimimaan taulukkomuotoisten tietojen kanssa. Q&A-käyttökokemusta ei vielä tueta monidimensioisena. Paikallisen tietoyhdyskäytävän tukemia tietolähteitä tuodaan lisää tarjolle ajan kuluessa.
* SQL Server Analysis Services -palvelussa määritetylle rivitason suojaukselle ei ole aluksi saatavilla täyttä tukea. Kun Q&A:ssa esitetään kysymyksiä, tekstin automaattinen täydennys saattaa kirjoittamisen aikana näyttää merkkijonoarvoja, joihin käyttäjällä ei ole käyttöoikeutta. Mallissa määritettyä rivitason suojausta kuitenkin kunnioitetaan raporttien ja kaaviovisualisointien osalta, eli taustalla olevia numeerisia tietoja ei paljastu. Tulevissa päivityksissä julkaistaan asetukset, joilla tätä käytöstä voi hallita.
* Objektitason suojausta (OLS) ei tueta. Q&A ei kunnioita objektitason suojausta ja voi paljastaa taulukon tai sarakkeen nimet käyttäjille, joilla ei ole niihin käyttöoikeutta. Sinun on otettava käyttöön rivitason suojaus (RSL) sen varmistamiseksi, että myös data-arvot suojataan asianmukaisesti. 
* Reaaliaikaisia yhteyksiä tuetaan vain paikallisen tietoyhdyskäytävän kanssa. Tämän johdosta tätä toimintoa ei voi käyttää henkilökohtaisen yhdyskäytävän kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet

- [On-premises data gateway (Paikallinen tietoyhdyskäytävä)](service-gateway-onprem.md)  
- [Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
- [Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)  
- [Yleiskatsaus Power BI Q&A:sta](consumer/end-user-q-and-a.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

