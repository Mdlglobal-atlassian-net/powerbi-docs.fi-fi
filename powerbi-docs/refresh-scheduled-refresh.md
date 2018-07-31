---
title: Ajoitetun päivityksen määrittäminen
description: Tämä kattaa vaiheet yhdyskäytävän valintaan ja ajoitetun päivityksen määrittämiseen.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: 5c614c00c0354e79c73023bdc0b81313a19a78a3
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2018
ms.locfileid: "39327311"
---
# <a name="configuring-scheduled-refresh"></a>Ajoitetun päivityksen määrittäminen

>[!NOTE]
>Tietojoukon ajoitettu päivitys keskeytetään kahden kuukauden käyttämättömyyden jälkeen. Katso kohta [*Ajoitettua päivitys*](#schedule-refresh) tuonnempana tässä artikkelissa saadaksesi lisätietoja.
> 
> 

Jos tietojoukkosi tukee ajoitettua päivitystä, käyttämällä toimintoja ”Päivitä nyt” ja ”Ajoita päivitys” on huomioitava muutama vaatimus ja asetus onnistunutta päivitystä varten. Näitä ovat **Yhdyskäytävän yhteys**, **Tietolähteen tunnistetiedot** ja **Ajoita päivitys**. Alla on kunkin käsitteen kuvailu:

Tässä kuvataan vaihtoehtoja, jotka ovat käytössä vaihtoehdoissa [Power BI Gateway – Personal](service-gateway-personal-mode.md) ja [Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md).

Pääset aikataulun päivitysnäyttöön toimimalla seuraavasti.

1. Valitse **kolme pistettä (...)**  tietojoukon vierestä kohdasta **Tietojoukot**.
2. Valitse **Ajoita päivitys**.
   
    ![](media/refresh-scheduled-refresh/dataset-menu.png)

## <a name="gateway-connection"></a>Yhdyskäytäväyhteys
Näet eri vaihtoehtoja sen mukaan, onko kyseessä henkilökohtainen tai yrityksen yhdyskäytävä verkossa ja käytettävissä.

Jos yhdyskäytävää ei ole käytettävissä, näet **Yhdyskäytävän asetukset** poistettuna käytöstä. Näkyviin tulee myös sanoma henkilökohtaisen yhdyskäytävän asentamisesta.

![](media/refresh-scheduled-refresh/gateway-not-configured.png)

Jos sinulla on henkilökohtainen yhdyskäytävä määritettynä, se on valittavissa, jos se on online-tilassa. Se näkyy offline-tilassa, jos se ei ole käytettävissä.

![](media/refresh-scheduled-refresh/gateway-connection.png)

Voit myös valita yritysyhdyskäytävän, jos sellainen on käytettävissäsi. Näkyviin tulee vain yritysyhdyskäytävä, joka on käytettävissä, jos tilisi on luettelossa tietolähteen Käyttäjät-välilehdellä kyseisen yhdyskäytävän kohdalla.

## <a name="data-source-credentials"></a>Tietolähteen tunnistetiedot
### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
Jos käytössäsi on henkilökohtainen yhdyskäytävä tietojen päivittämiseksi, sinun on annettava tunnistetiedot, joita käytit yhteyden muodostamisessa taustan tietolähteeseen. Jos olet muodostanut yhteyden sisältöpakettiin online-palvelusta, antamasi tunnistetiedot yhteyden muodostamiseksi suoritetaan ajoitettua päivitystä varten.

![](media/refresh-scheduled-refresh/data-source-credentials-pgw.png)

Sinua pyydetään kirjautumaan tietolähteeseen vain kun päivität kyseisen tietojoukon ensimmäistä kertaa. Kun tunnistetiedot on syötetty, kyseiset tunnistetiedot säilyvät tietojoukossa.

> [!NOTE]
> Jotkin todennusmenetelmät, jos käytät kirjautuessasi tietolähteeseen vanhentunutta salasanaa tai ne on muutettu, edellyttävät sen muuttamista tietolähteeseen Tietolähteen tunnistetiedoissa.
> 
> 

Jos ilmenee ongelmia, ongelmalla on yleensä jotain tekemistä sen kanssa, että yhdyskäytävä on offline-tilassa, koska sitä ei voitu kirjata sisään Windowsiin ja palvelua käynnistää tai Power BI ei voinut kirjautua tietolähteisiin tietojen päivittämistä koskevaa kyselyä varten. Jos päivitys epäonnistuu, tarkista tietojoukon asetukset. Jos yhdyskäytäväpalvelu on offline-tilassa, yhdyskäytävän tilasta näet virheen. Jos Power BI ei voi kirjautua sisään tietolähteeseen, näet virheen Tietolähteen tunnistetiedot -kohdassa.

### <a name="on-premises-data-gateway"></a>Paikallinen tietoyhdyskäytävä
Jos käytössäsi on paikallinen tietoyhdyskäytävä tietojen päivittämiseen, sinun ei tarvitse antaa tunnistetietoja sellaisina kuin ne on määritelty tietolähdettä varten yhdyskäytävän järjestelmänvalvojan toimesta.

![](media/refresh-scheduled-refresh/data-source-credentials-egw.png)

> [!NOTE]
> Muodostettaessa yhteyttä paikalliseen SharePointiin tietojen päivittämiseksi, Power BI tukee vain *Anonyymi-*, *Perus-*, ja *Windows (NTLM/Kerberos)* -todennusmekanismeja. Power BI ei tue *ADFS:a* tai mitään *lomakepohjaisen todentamisen* mekanismia  tietojen päivittämiseksi paikallisessa SharePoint-tietolähteessä.
> 
> 

## <a name="schedule-refresh"></a>Ajoita päivitys
Ajoitettu päivitys -osassa määritetään aikavälit tietojoukon päivittämiseksi. Jotkin tietolähteet eivät edellytä yhdyskäytävää pystyäkseen määritykseen. Jotkin taas edellyttävät yhdyskäytävää.

Sinun on asetettava **Pidä tietosi ajan tasalla** -liukusäätimestä **Kyllä**, jotta voit määrittää asetukset.

> [!NOTE]
> Power BI -palvelu pyrkii aloittamaan tietojen päivittämisen **15 minuutin kuluessa** ajoitetusta päivitysajasta.
> 
> 

![](media/refresh-scheduled-refresh/scheduled-refresh.png)

> [!NOTE]
> Tietojoukon ajoitettu päivitys keskeytetään kahden kuukauden käyttämättömyyden jälkeen. Tietojoukkoa pidetään epäaktiivisena, kun kukaan käyttäjä ei ole käynyt koontinäytössä tai sille rakennetussa raportissa. Samaan aikaan tietojoukon omistajalle lähetetään sähköpostiviesti, joka kertoo ajoitetun päivityksen olevan keskeytetty, ja tietojoukon päivitysaikataulu näytetään muodossa **pois käytöstä**. Jatka ajoitettua päivitystä käymällä millä tahansa koontinäytöllä tai raportissa, joka on rakennettu tietojoukkoon.
> 
> 

## <a name="whats-supported"></a>Tuetut toiminnot:
Tiettyjä tietojoukkoja tuetaan ajoitettua päivitystä varten eri yhdyskäytäviä vastaan. Seuraavassa kerrotaan, mitä on saatavana.

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
**Power BI Desktop**

* Kaikki online-tietolähteet, jotka näkyvät Power BI Desktopin kohdassa Nouda tiedot ja Kyselyeditorissa.
* Kaikki paikalliset tietolähteet, jotka näkyvät Power BI Desktopin kohdassa Nouda tiedot ja Kyselyeditorissa lukuun ottamatta Hadoop-tiedostoa (HDFS) ja Microsoft Exchangea.

**Excel**

> [!NOTE]
> Excel 2016:ssa ja uudemmissa versioissa Power Query näkyy nyt valintanauhan Tiedot-osiossa kohdassa Hae ja muunna tiedot.
> 
> 

* Kaikki Power Queryssä näkyvät online tietolähteet.
* Kaikki paikalliset tietolähteet, jotka näkyvät Power Queryssä, lukuun ottamatta Hadoop-tiedostoa (HDFS) ja Microsoft Exchangea.
* Kaikki Power Pivotissa näkyvät online-tietolähteet.\*
* Kaikki paikalliset tietolähteet, jotka näkyvät Power Pivotissa, lukuun ottamatta Hadoop-tiedostoa (HDFS) ja Microsoft Exchangea.

<!-- Refresh Data sources-->
[!INCLUDE [refresh-datasources](./includes/refresh-datasources.md)]

## <a name="troubleshooting"></a>Vianmääritys
Joskus tietojen päivittäminen ei mene odotetulla tavalla. Yleensä tämä on yhdyskäytävään liittyvä ongelma. Tutustu yhdyskäytävän vianmääritystä koskeviin artikkeleihin, joissa on esitetty työkaluja ja tunnettuja ongelmia.

[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)

[Power BI -yhdyskäytävän vianmääritys – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietojen päivittäminen Power BI:ssä](refresh-data.md)  
[Power BI -yhdyskäytävä – Personal](service-gateway-personal-mode.md)  
[Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
[Power BI -yhdyskäytävän vianmääritys – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

