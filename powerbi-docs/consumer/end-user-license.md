---
title: Power BI -kuluttajien käyttöoikeustyypit
description: Lue erilaisista käyttöoikeustyypeistä ja siitä, miten voit selvittää, minkä tyyppinen käyttöoikeus sinulla on.
author: mihart
ms.reviewer: lukasz
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 04/18/2020
ms.author: mihart
LocalizationGroup: consumers
ms.openlocfilehash: 8610f5c0efbc3da394e4de7c263a88aad813eae2
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82066012"
---
# <a name="using-the-power-bi-service-as-a-consumer"></a>Power BI -palvelun käyttäminen *kuluttajana*

[!INCLUDE[consumer-appliesto-ynnn](../includes/consumer-appliesto-ynnn.md)]

[*Kuluttajana*](end-user-consumer.md) käytät Power BI -palvelua raporttien ja koontinäyttöjen tarkastelemiseen, jotta voit tehdä tietoihin perustuvia liiketoimintapäätöksiä. Jos olet käyttänyt Power BI:tä jonkin aikaa tai olet jutellut *design-osaston* työntekijöiden kanssa, olet luultavasti huomannut, että jotkin ominaisuudet toimivat vain, jos sinulla on tietyntyyppinen käyttöoikeus tai tilaus tai tietyntyyppiset oikeudet. 

Power BI -palvelun käytettävissä olevat ominaisuudet riippuvat kolmesta asiasta:
-    käyttämäsi käyttöoikeuden ja tilauksen tyypistä
-    sisällön tallennuspaikasta
-    määritetyistä rooleista ja käyttöoikeuksista.


![kuva pro-käyttäjistä](media/end-user-license/power-bi-questions-small.png)

Tässä artikkelissa kerrotaan kunkin käyttöoikeustyypin ominaisuuksista ja siitä, miten *sisällön tallennuspaikka* voi vaikuttaa siihen, *mitä voit sillä tehdä*. Opit myös etsimään käyttöoikeuden ja tilauksen sekä selvittämään, minne sisältösi tallennetaan. Lisätietoja rooleista ja käyttöoikeuksista on [työtilan rooleissa](end-user-workspaces.md).

## <a name="licenses"></a>Käyttöoikeudet

Jokaisella Power BI -palvelun käyttäjällä on joko *maksuton* käyttöoikeus tai *Pro*-käyttöoikeus. Jos olet Power BI -*kuluttaja*, käytössäsi on todennäköisesti maksuton käyttöoikeus, jota järjestelmänvalvojasi hallitsee. 

Käyttöoikeuksia voi olla samanaikaisesti useita.  Palvelu tarjoaa aina parasta käyttöoikeuttasi vastaavan käyttökokemuksen. 

## <a name="power-bi-premium-capacity"></a>Power BI Premium -kapasiteetti

Premium on organisaation tilaus, joka tarjoaa erilaisen tavan tallentaa sisältöä – varatussa kapasiteetissa. Premiumia käyttämällä niin organisaatiosi sisällä kuin ulkopuolella olevat käyttäjät voivat tarkastella Power BI -sisältöäsi ilman yksittäisten Power BI Pro -käyttöoikeuksien ostoa. 

Premium mahdollistaa Pro-version käyttäjien luoman sisällön laaja-alaisen jakamisen ilman, että sisältöä katselevilla vastaanottajilla on oltava Pro-käyttöoikeus. Sisällön suunnittelijoille vaaditaan Pro-käyttöoikeudet. Suunnittelijat muodostavat yhteyden tietolähteisiin, mallintavat tietoja ja luovat raportteja sekä koontinäyttöjä, jotka on pakattu työtilasovelluksiksi. Käyttäjä voi käyttää Power BI Premium -työtilaa myös ilman Pro-käyttöoikeutta, jos hänelle on määritetty katselijarooli.

Näissä työtiloissa suunnittelijat määrittävät rooleja, kuten **Katselija**, **Osallistuja**, **Jäsen** ja **Järjestelmänvalvoja**, jotka määrittävät, missä määrin työtoverit voivat käsitellä sisältöä. Lisätietoja on [työtilan käyttöoikeuksia ja rooleja](end-user-workspaces.md) käsittelevässä kohdassa. 

Lisätietoja Premium-kapasiteetista on kohdassa [Mikä on Microsoft Power BI Premium?](../service-premium-what-is.md)


## <a name="find-out-which-licenses-you-have"></a>Selvitä, mitkä käyttöoikeudet sinulla on

Vieraile [Microsoftin **Oma tili** -sivullasi](https://portal.office.com/account), jotta näet, mitä käyttöoikeuksia sinulle on määritetty.  Valitse **Tilaukset**-välilehti.


Tällä ensimmäisellä käyttäjällä Pradtannalla on Office 365 E5, joka sisältää Power BI Pro -käyttöoikeuden.

![Office-portaalin Tilaukset-välilehti](media/end-user-license/power-bi-license-office.png)

Tällä toisella käyttäjällä Zalanilla on maksuton Power BI -käyttöoikeus. 

![Office-portaalin Tilaukset-välilehti](media/end-user-license/power-bi-license-free.png)

## <a name="find-out-if-you-have-access-to-premium-capacity"></a>Selvitä, onko sinulla Premium-kapasiteetin käyttöoikeus.

Tarkista seuraavaksi, oletko osa organisaatiota, jolla on Premium-kapasiteetti. Kumpi tahansa edellä mainituista käyttäjistä, Pro tai maksuton, voi kuulua organisaatioon, jolla on Premium-kapasiteetti.  Tarkistetaan tilanne toiselta käyttäjältä, Zalanilta.  

Voimme määrittää, onko Zalanin organisaatiolla Premium-kapasiteetti, tarkistamalla käytettävissä olevan tallennustilan. 

- Valitse Power BI -palvelussa **Oma työtila** ja valitse sitten oikeassa yläkulmassa oleva hammasrataskuvake. Valitse **Hallitse henkilökohtaista tallennustilaa**.

    ![Hammasrattaan Asetukset-valikko näytetään](media/end-user-license/power-bi-license-personal.png)

    Jos näet yli 10 Gt, olet sellaisen organisaation jäsen, jolla on Premium-tilaus. Alla olevassa kuvassa näkyy, että Zalanin organisaatiolla on enintään 100 Gt tallennustilaa.  

    ![Tallennustilan hallinta näyttää 100 Gt](media/end-user-license/power-bi-free-capacity.png)

Ota huomioon, että Pro-käyttäjä on jo jakanut työtilan Zalanin kanssa. Vinoneliökuvake ilmaisee, että työtila on tallennettu Premium-kapasiteettiin. 

## <a name="identify-content-hosted-in-premium-capacity"></a>Premium-kapasiteetissa isännöidyn sisällön tunnistaminen

Toinen tapa selvittää, onko organisaatiollasi Premium-kapasiteetti, on etsiä sovelluksia ja sovellustyötiloja, joissa on vinoneliökuvake. Vinoneliö ilmaisee, että sisältö on tallennettu Premium-kapasiteettiin. 

Alla olevassa kuvassa kolme sovellusta on tallennettu Premium-kapasiteettiin.

![Sovellukset-näyttö](media/end-user-license/power-bi-premium.png)

    
*Kuluttajana* organisaatiossa voit tarkastella **kyseisessä työtilassa** jaettua sisältöä, tehdä yhteistyötä työtovereiden kanssa, käyttää sovelluksia ja tehdä paljon muutakin, kunhan *suunnittelija* asettaa työtilan Premiumille varattuun kapasiteettiin. Power BI -järjestelmänvalvoja ja sisällön suunnittelija määrittävät käyttöoikeuksiesi laajuuden. 

   

## <a name="putting-it-all-together"></a>Tietojen kokoaminen yhteen

Kun organisaatio ostaa Premium-tilauksen, järjestelmänvalvoja tavallisesti määrittää Pro-käyttöoikeudet niille työntekijöille, jotka luovat ja jakavat sisältöä Premium-kapasiteetissa. Järjestelmänvalvoja myös määrittää maksuttomat käyttöoikeudet kaikille, jotka kuluttavat luotua sisältöä. Pro-käyttäjät luovat [sovellustyötiloja](end-user-workspaces.md) ja lisäävät sisältöä (koontinäyttöjä, raportteja ja sovelluksia) kyseisiin työtiloihin. Jos haluat sallia maksuttoman version käyttäjien tehdä yhteistyötä näissä työtiloissa, järjestelmänvalvoja tai Pro-käyttäjä määrittää työtilat *varattuun kapasiteettiin*.    
<br>

|Käyttöoikeustyyppi  |jaettu kapasiteetti  |varattu kapasiteetti  |
|---------|---------|---------|
|**Maksuton**     |  Käytettäväksi henkilökohtaisena eristyksenä, jossa voit luoda sisältöä itsellesi ja käsitellä kyseistä sisältöä. Tämä on erinomainen tapa kokeilla Power BI -palvelua. Et voi käyttää muiden käyttäjien sisältöä tai jakaa sisältöäsi muiden kanssa. <sup>1</sup>     |   Voit käsitellä varattuun kapasiteettiin määritettyä sisältöä, joka on jaettu kanssasi. Maksuttoman version käyttäjät ja Pro-käyttäjät voivat tehdä yhteistyötä ilman, että maksuttoman version käyttäjillä on Pro-tili.      |
|**Pro**     |  Voit tehdä yhteistyötä muiden Pro-käyttäjien kanssa luomalla ja jakamalla sisältöä.        |  Voit tehdä yhteistyötä maksuttoman version ja Pro-käyttäjien kanssa luomalla ja jakamalla sisältöä.       |


<sup>1</sup> Katso kohta [Huomioon otettavat seikat ja vianmääritys](#considerations-and-troubleshooting). 

Alla olevan kaavion vasen puoli kuvaa Pro-käyttäjiä, jotka luovat ja jakavat sisältöä sovellustyötiloissa. 

- **Työtila A** luotiin organisaatiossa, jolla ei ole Premium-kapasiteettia. 

- **Työtila B** luotiin organisaatiossa, jolla on Premium-tilaus, ja työtila tallennettiin varattuun kapasiteettiin. Tällä työtilalla on vinoneliökuvake.  

    ![kuva kolmesta työtilasta](media/end-user-license/power-bi-dedicated.jpg)

Power BI Pron *suunnittelija* voi jakaa ja tehdä yhteistyötä muiden Pro-käyttäjien kanssa missä tahansa näistä kolmesta työtilasta. Power BI Pron käyttäjä voi kuitenkin jakaa ja tehdä yhteistyötä maksuttoman version käyttäjien kanssa vain työtilassa B, joka on varatussa Premium-kapasiteetissa.  Työtilassa suunnittelija määrittää roolit työtovereille. Rooli määrittää, mitä toimintoja käyttäjä voi tehdä työtilassa. Power BI *-kuluttajille* määritetään yleensä *Katselija*-rooli. Saat lisätietoja rooleista ohjeartikkelista [Työtilat Power BI -kuluttajille](end-user-workspaces.md).




## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
- Power BI -käyttöoikeuksia voi olla useita. Power BI -palvelu tarjoaa aina parasta käyttöoikeuttasi vastaavan käyttökokemuksen. Jos sinulla on esimerkiksi sekä Pro-käyttöoikeus että maksuton käyttöoikeus, Power BI -palvelu käyttää Pro-käyttöoikeutta.

- Jos haluat jakaa ja luoda sisältöä (koontinäyttöjä, raportteja, sovelluksia), sinun kannattaa ehkä olla Power BI -*kuluttajan* sijaan *suunnittelija*. Harkitse vaihtamista Pro-käyttöoikeuteen. Voit rekisteröityä maksuttomaan 60 päivän yksityishenkilöiden Power BI Pro -kokeiluun valitsemalla päivitysvalintaikkunan, joka näkyy Power BI -palvelussa aina, kun yrität käyttää Pro-ominaisuutta.

    ![valintaikkuna, jossa on linkki Pro-kokeiluun](media/end-user-license/power-bi-trial.png)

  Kun 60-päivän kokeilujakso päättyy, käyttöoikeutesi muuttuu takaisin maksuttomaksi Power BI -käyttöoikeudeksi. Tämän jälkeen sinulla ei ole enää käyttöoikeutta ominaisuuksiin, joihin tarvitaan Power BI Pro -käyttöoikeus. Jos haluat jatkaa Pro-käyttöoikeuden käyttöä, kysy lisätietoja järjestelmänvalvojaltasi Power BI Pro -käyttöoikeuden ostamisesta. Jos sinulla ei ole järjestelmänvalvojaa, vieraile [Power BI -hinnoittelusivulla](https://powerbi.microsoft.com/pricing/).     


- Jos olet rekisteröinyt maksuttoman käyttöoikeuden, se ei vanhene koskaan. Jos siis päivität Pro-kokeiluversioon tai organisaatiosi antaa sinulle Pro-käyttöoikeuden ja sitten kokeilujaksosi päättyy tai organisaatiosi poistaa Pro-käyttöoikeutesi, käytettävissäsi on edelleen maksuton käyttöoikeus – ellet sinä tai järjestelmänvalvojasi peruuta käyttöoikeutta. 

- <sup>1</sup> Power BI -palvelun maksuton käyttöoikeus on täydellinen käyttäjälle, joka tutustuu siihen tai käyttää sitä henkilökohtaisten tietojen analysointiin ja visualisointeihin **omassa työtilassa**. Maksuton käyttäjä ei käytä Power BI:tä yhteistyöhön työtovereiden kanssa. Käyttäjät, joilla on maksuton käyttöoikeus, eivät voi tarkastella toisten jakamaa sisältöä tai jakaa omaa sisältöään muiden Power BI -käyttäjien kanssa. 

    ![kuva erillisistä käyttäjistä](media/end-user-license/power-bi-free-license.jpg)


## <a name="next-steps"></a>Seuraavat vaiheet
- [Olenko Power BI *-kuluttaja*?](end-user-consumer.md)    
- [Lisätietoja työtiloista](end-user-workspaces.md)    
- [Tutustu Power BI:n ominaisuuksiin käyttöoikeustyypin mukaan](end-user-features.md)
