---
title: Spark + HDInsight ja DirectQuery
description: Spark + HDInsight ja DirectQuery
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2018
LocalizationGroup: Data from databases
ms.openlocfilehash: 398737276e55e15273a2245a4b7a72fdca938438
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54287711"
---
# <a name="spark-on-hdinsight-with-directquery"></a>Spark + HDInsight ja DirectQuery

Azure HDInsightin Sparkin ja DirectQueryn avulla voit luoda dynaamisia raportteja niiden tietojen ja arvojen perusteella, joita sinulla jo on Spark-klusterissasi. DirectQueryn avulla kyselyt lähetetään takaisin Azure HDInsight Spark -klusteriin reaaliaikaisesti tutkiessasi tietoja raporttinäkymässä. Tätä kokemusta ehdotetaan käyttäjille, jotka ovat perehtyneet entiteetteihin, joihin he ovat muodostamassa yhteyttä.

> [!WARNING]
> Automaattinen ruutujen päivitys on poistettu käytöstä koontinäytön ruuduissa, jotka on luotu Spark-pohjautuvista tietojoukoista. Voit päivittää manuaalisesti valitsemalla **Päivitä koontinäytön ruudut**. Tämä ei vaikuta raportteihin ja niiden pitäisi pysyä ajan tasalla. 

Seuraavien vaiheiden avulla voit muodostaa yhteyden Azure HDInsightin Spark-tietolähteeseen käyttäen Power BI -palveluun sisältyvää DirectQueryä.

> [!Important]
> Olemme parantaneet liitettävyyttämme Sparkiin.  Pystyt parhaiten muodostamaan yhteyden Spark-tietolähteeseen Power BI Desktopin avulla.  Kun olet luonut mallin ja raportin, voit julkaista sen Power BI -palvelussa.  Suora yhdistin Sparkille Power BI-palvelussa on nyt vanhentunut.

1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.

     ![](media/spark-on-hdinsight-with-direct-connect/spark-getdata.png)
2. Valitse **Tietokannat ja muut**.

     ![](media/spark-on-hdinsight-with-direct-connect/spark-getdata-databases.png)
3. Valitse **Spark HDInsight** -liitin ja valitse **Yhdistä**.

     ![](media/spark-on-hdinsight-with-direct-connect/spark-getdata-databases-connect.png)
4. Kirjoita sen **palvelimen** nimi, johon haluat muodostaa yhteyden, sekä **käyttäjänimi** ja **salasana**. Palvelin on aina muodossa \<klusterinimi\>.azurehdinsight.net. Alla on lisätietoja näiden arvojen löytämisestä.

     ![](media/spark-on-hdinsight-with-direct-connect/spark-server-name.png)

     ![](media/spark-on-hdinsight-with-direct-connect/spark-username.png)
5. Kun yhteys on muodostettu, näet uuden tietojoukon nimeltä SparkDataset. Voit myös käyttää tietojoukkoa luodun paikkamerkkiruudun kautta.

     ![](media/spark-on-hdinsight-with-direct-connect/spark-dataset.png)
6. Porautumalla tietojoukkoon voit tarkastella kaikkia tietokannassa olevia taulukoita ja sarakkeita. Sarakkeen valitseminen lähettää kyselyn takaisin lähteeseen luoden visualisoinnin dynaamisesti. Nämä visualisoinnit voidaan tallentaa uudessa raportissa ja kiinnittää takaisin koontinäyttöön.

## <a name="finding-your-spark-on-hdinsight-parameters"></a>Omien Spark HDInsight -parametrien löytäminen

Palvelin on aina muodossa \<klusterinimi\>.azurehdinsight.net, ja se löytyy Azure-portaalista.

![](media/spark-on-hdinsight-with-direct-connect/spark-server-name-parameter.png)

Käyttäjänimi ja salasana löytyvät myös Azure-portaalista.

## <a name="limitations"></a>Rajoitukset

Nämä rajoitukset ja muistiinpanot saattavat muuttua jatkaessamme käyttökokemusten kehittämistä. Lisäohjeita on artikkelissa [BI-työkalujen käyttäminen Azure HDInsightin Apache Sparkin avulla](/azure/hdinsight/spark/apache-spark-use-bi-tools/).

* Power BI -palvelu tukee vain Spark 2.0:n ja HDInsight 3.5:n kokoonpanoa.
* Jokainen toiminto, esimerkiksi sarakkeen valitseminen tai suodattimen lisääminen, lähettää kyselyn takaisin tietokantaan. Valitse sopiva visualisointityyppi ennen erittäin suurten kenttien valitsemista.
* Q&A ei ole käytettävissä DirectQuery-tietojoukoissa.
* Rakenteen muutoksia ei poimita automaattisesti.
* Power BI tukee tietojoukossa 16 000 saraketta **kaikissa taulukoissa**. Power BI sisältää myös sisäisen rivinumerosarakkeen taulukkoa kohden. Tämä tarkoittaa sitä, että jos tietojoukossa on 100 taulukkoa, käytettävissä olevien sarakkeiden määrä on 15 900. Spark-tietolähteestä käsiteltävien tietojen määrästä riippuen tämä rajoitus saattaa tulla vastaan.

## <a name="troubleshooting"></a>Vianmääritys

Jos kohtaat ongelmia suorittaessasi kyselyitä klusterista, varmista, sovellus on yhä käynnissä ja käynnistä se uudelleen tarvittaessa.

Voit myös varata lisäresursseja Azure-portaalin kohdassa **Kokoonpano** > **Klusterin skaalaus**:

![](media/spark-on-hdinsight-with-direct-connect/spark-scale.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Aloittaminen: Luo Apache Spark -klusteri HDInsight Linuxissa ja suorita vuorovaikutteisia kyselyjä Spark SQL:llä](/azure/hdinsight/spark/apache-spark-jupyter-spark-sql/)  
[Mikä on Power BI?](power-bi-overview.md)  
[Tietojen noutaminen Power BI:lle](service-get-data.md)
[Kerberosin käyttäminen kertakirjautumiseen paikallisessa yhdyskäytävässä](service-gateway-sso-kerberos.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)