---
title: Raporttien erottaminen malleista Power BI Desktopissa
description: Ohjeet raporttien erottamiseen malleista Power BI Desktopissa.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/11/2020
ms.author: v-pemyer
ms.openlocfilehash: dad451da460abed65a69990394522f268d7f21cd
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "81525247"
---
# <a name="separate-reports-from-models-in-power-bi-desktop"></a>Raporttien erottaminen malleista Power BI Desktopissa

Uutta Power BI Desktop -ratkaisua luodessasi yksi ensimmäisistä tehtävistä on "noutaa tiedot". Tietojen noutaminen voi johtaa kahteen selvästi erilaiseen tulokseen. Se voi

- luoda [reaaliaikaisen yhteyden](../desktop-report-lifecycle-datasets.md) jo julkaistuun malliin, joka voi olla Power BI -tietojoukko tai etäisännöity Analysis Services -malli.
- aloittaa uuden mallin kehittämisen, joka voi olla joko tuonti-, DirectQuery- tai yhdistelmämalli.

Tämä artikkeli koskee toista skenaariota. Se antaa ohjeita siitä, pitäisikö raportti ja malli yhdistää yhdeksi Power BI Desktop -tiedostoksi.

## <a name="single-file-solution"></a>Yhden tiedoston ratkaisu

_Yhden tiedoston ratkaisu_ toimii hyvin, kun malliin perustuvia raportteja on vain yksi. Tässä tapauksessa on todennäköistä, että malli ja raportti ovat saman henkilön luomia. Määritämme sen _henkilökohtaiseksi BI-ratkaisuksi_, vaikka raportti saatetaankin jakaa muiden kanssa. Tällaiset ratkaisut voivat edustaa roolipohjaisia raportteja tai liiketoimintahaasteen kertaluontoisia arviointeja, joita kuvataan usein _ad hoc_ -raporteiksi.

:::image type="content" source="media/report-separate-from-model/single-file-solution.png" alt-text="Yksi tiedosto sisältää saman henkilön kehittämän mallin ja raportin." border="true":::

## <a name="separate-report-files"></a>Raporttitiedostojen erottaminen

On järkevää erottaa mallin ja raportin kehitys erillisiksi Power BI Desktop -tiedostoiksi, kun

- tietojen mallintajat ja raporttien tekijät ovat eri henkilöitä.
- on selvää, että malli toimii lähteenä useille raporteille nyt tai tulevaisuudessa.

:::image type="content" source="media/report-separate-from-model/separate-report-files.png" alt-text="PBIX-tiedostoja on kolme. Ensimmäinen sisältää vain mallin. Kaksi muuta sisältävät vain raportteja, ja ne ovat reaaliaikaisessa yhteydessä Power BI -palvelussa olevaan malliin. Eri käyttäjät ovat kehittäneet raportteja." border="true":::

Tietojen mallintajat voivat edelleen testata ja vahvistaa mallejaan Power BI Desktopin raportin luontikokemuksen avulla. Kuitenkin heti tiedoston julkaisemisen jälkeen Power BI -palveluun heidän tulee poistaa raportti työtilasta. Heidän on muistettava poistaa raportti aina tietojoukon uudelleenjulkaisemisen ja korvaamisen jälkeen.

### <a name="preserve-the-model-interface"></a>Mallin käyttöliittymän säilyttäminen

Malliin on joskus pakko tehdä muutoksia. Tietojen mallintajien on silloin huolehdittava, että ne eivät aiheuta häiriötä mallin käyttöliittymään. Häiriöt saattavat vaikuttaa raportin visualisointeihin tai koontinäytön kuvakkeisiin. Rikkinäiset visualisoinnit näkyvät virheinä, ja ne voivat turhauttaa raportin tekijöitä ja käyttäjiä. Ja mikä vielä pahempaa – ne voivat vähentää luottamusta tietoihin.

Hallitse siis malliin tehtäviä muutoksia huolellisesti. Vältä seuraavia muutoksia, jos mahdollista:

- taulukoiden, sarakkeiden, hierarkioiden, hierarkiatasojen tai mittayksiköiden nimeäminen uudelleen
- sarakkeen tietotyyppien muokkaaminen
- mittayksikkölausekkeiden muuttaminen niin, että ne palauttavat eri tietotyypin
- mittayksiköiden siirtäminen eri aloitustaulukkoon. Tämä johtuu siitä, että mittayksikön siirtäminen voi aiheuttaa häiriötä raportin laajuisiin mittayksiköihin, jotka täyttävät täydellisesti mittayksiköt aloitustaulukon nimellä. Emme suosittele kirjoittamaan DAX-lausekkeita käyttäen täydellisiä mittayksiköiden nimiä. Katso lisätietoja kohdasta [DAX: Sarake- ja mittaviittaukset](dax-column-measure-references.md).

Uusien taulukoiden, sarakkeiden, hierarkioiden, hierarkiatasojen tai mittayksiköiden lisääminen on turvallista, yhtä poikkeusta lukuun ottamatta: on mahdollista, että uuden mittayksikön nimi voi olla ristiriidassa raportin laajuisen mittayksikön nimen kanssa. Ristiriitojen välttämiseksi on suositeltavaa, että raportin tekijät käyttävät tiettyä nimeämiskäytäntöä määrittäessään mittayksiköitä raporteissaan. Raporttien laajuisten mittayksiköiden nimiin voi laittaa etuliitteen, kuten alaviivan tai jonkin muun merkin.

Jos sinun on tehtävä häiriötä aiheuttavia muutoksia malleihin, suosittelemme jompaakumpaa seuraavista:

- [Tarkastele tietojoukon aiheeseen liittyvää sisältöä Power BI -palvelussa.](../consumer/end-user-related.md#view-related-content-for-a-dataset)
- Tutustu [Tietojen historiatiedot](../collaborate-share/service-data-lineage.md) -näkymään Power BI -palvelussa.

Molempien vaihtoehtojen avulla voit nopeasti tunnistaa liittyvät raportit ja koontinäytöt. Tietojen historiatiedot -näkymä on luultavasti parempi vaihtoehto, koska yhteyshenkilö on helppo nähdä kunkin liittyvän artefaktin kohdalla. Kyseessä on hyperlinkki, joka avaa yhteyshenkilölle osoitetun sähköpostiviestin.

Suosittelemme ottamaan yhteyttä kunkin liittyvän artefaktin omistajaan ja kertomaan hänelle suunnitelluista, häiriötä aiheuttavista muutoksista. Näin hän voi olla valmiina korjaamaan ja julkaisemaan raporttejaan uudelleen, ja se auttaa myös minimoimaan käyttökatkoja ja turhautumista.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Tietojoukkoihin yhdistäminen Power BI -palvelussa Power BI Desktopista](../desktop-report-lifecycle-datasets.md)
- [Tarkastele aiheeseen liittyvää sisältöä Power BI -palvelussa](../consumer/end-user-related.md)
- [Tietojen siirtymä](../collaborate-share/service-data-lineage.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
