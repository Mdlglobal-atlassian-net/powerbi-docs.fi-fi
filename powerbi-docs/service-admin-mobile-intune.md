---
title: Mobiilisovellusten määrittäminen Microsoft Intunella
description: Lue Power BI -mobiilisovellusten määritysohjeet, kun käytössä on Microsoft Intune. Tämä sisältää ohjeet sovelluksen lisäämiseen ja käyttöönottoon. Lisäksi opit luomaan mobiilisovelluskäytännön suojauksen hallintaa varten.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 8e31d3128e38453212a8a0ecef2a139fa2d0f356
ms.sourcegitcommit: 49570ab8f5b5cd5bab4cd388f4281b1372bcb80b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/09/2018
ms.locfileid: "35250541"
---
# <a name="configure-mobile-apps-with-microsoft-intune"></a>Mobiilisovellusten määrittäminen Microsoft Intunella
Microsoft Intunen avulla organisaatiot voivat hallita laitteita ja sovelluksia. Power BI -mobiilisovellukset iOS:ssa ja Androidissa integroituvat Intuneen, joten sovellusta ja suojausta voidaan hallita laitteissa. Määrityskäytäntöjen avulla organisaatiot voivat hallita tietoyksiköitä kuten pikakäytön kiinnittämisen edellyttämistä, sovelluksen tietojenkäytön valvontaa ja sovellustietojen salaamista myös silloin, kun sovellus ei ole käytössä.

## <a name="general-mobile-device-management-configuration"></a>Yleisen mobiililaitteiden hallinnan määritys
Tätä artikkelia ei ole tarkoitettu Microsoft Intunen täydelliseksi määritysoppaaksi. Jos olet juuri nyt integroimassa Intunea, muutamia määritettyjä asioita kannattaa varmistaa. [Lue lisää](https://technet.microsoft.com/library/jj676587.aspx)

Microsoft Intune voi olla käytössä Mobiililaitteiden hallinnan (MDM) kanssa Office 365:ssä. [Lue lisää](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365/)

Tässä artikkelissa oletetaan, että Intune on määritetty oikein ja että laitteet on rekisteröity Intuneen. Jos käytät samaan aikaan MDM:ää, laite näkyy rekisteröitynä MDM:ssä, mutta se on hallittavissa myös Intunessa.

> [!NOTE]
> Jos käytät Power BI -mobiilisovellusta iOS-laitteessa, kun organisaatio on määrittänyt Microsoft Intunen mobiilisovellusten hallinnan, tietojen päivittäminen taustalla on poistettu käytöstä. Kun avaat sovelluksen seuraavan kerran, Power BI päivittää tiedot verkossa olevasta Power BI -palvelusta.
> 
> 

## <a name="step-1-get-the-url-for-the-application"></a>Vaihe 1: Sovelluksen URL-osoitteen hankkiminen
Tarvitsemme sovellusten URL-osoitteet, jotta voimme luoda sovelluksen Intunessa. Osoitteet saadaan iOS:ssä iTunesista. Androidissa ne saadaan Power BI -mobiilisivulta.

Tallenna URL-osoite, sillä tarvitset sitä, kun luomme sovelluksen.

### <a name="ios"></a>iOS
Jotta saamme sovelluksen URL-osoitteen iOS:ssä, se on noudettava iTunesista.

1. Avaa iTunes.
2. Hae *Power BI*.
3. **Microsoft Power BI** pitäisi näkyä luettelon kohdissa **iPhone-sovellukset** ja **iPad-sovellukset**. Voit käyttää jompaakumpaa niistä, sillä tuloksena on sama URL-osoite.
4. Valitse avattava **Nouda**-luettelo ja valitse **Kopioi linkki**.
   
    ![](media/service-admin-mobile-intune/itunes-url.png)

Näkymän kuuluu näyttää seuraavankaltaiselta.

    https://itunes.apple.com/us/app/microsoft-power-bi/id929738808?mt=8

### <a name="android"></a>Android
Saat URL-osoitteen Google Playhin [Power BI -mobiilisivulta](https://powerbi.microsoft.com/mobile/). Kun napsautat **Lataa Google Playsta** -kuvaketta, pääset sovelluksen sivulla. Voit kopioida URL-osoitteen selaimen osoiteriviltä. Näkymän kuuluu näyttää seuraavankaltaiselta.

    https://play.google.com/store/apps/details?id=com.microsoft.powerbim

## <a name="step-2-create-a-mobile-application-management-policy"></a>Vaihe 2: Mobiilisovellusten hallintakäytännön luominen
Mobiilisovellusten hallintakäytännön avulla voit pakottaa kohteita, kuten käytön PIN-koodin. Voit luoda sellaisen Intune-portaalissa. 

Voit luoda sovelluksen tai käytännön ensin. Lisäysjärjestyksellä ei ole merkitystä. Niiden kummankin on oltava olemassa käyttöönottovaihetta varten.

1. Valitse **Käytäntö** > **Määrityskäytännöt**.
   
    ![](media/service-admin-mobile-intune/intune-policy.png)
2. Valitse **Lisää...**.
3. Voit valita **Ohjelmisto**-kohdasta mobiilisovellusten hallinnan joko Androidille tai iOS:lle. Jos haluat päästä alkuun nopeasti, valitse **Luo käytäntö käyttäen suositeltuja asetuksia**. Voit vaihtoehtoisesti luoda mukautetun käytännön.
4. Muokkaa käytäntöä ja määritä sovelluksessa haluamasi rajoitukset.

## <a name="step-3-create-the-application"></a>Vaihe 3: Sovelluksen luominen
Sovellus on viittaus tai paketti, joka on tallennettu Intuneen käyttöönottoa varten. Meidän on luotava sovellus ja viittaus sovelluksen URL-osoitteeseen, jonka saimme joko Google Playsta tai iTunesista.

Voit luoda sovelluksen tai käytännön ensin. Lisäysjärjestyksellä ei ole merkitystä. Niiden kummankin on oltava olemassa käyttöönottovaihetta varten.

1. Siirry Intune-portaaliin ja valitse **Sovellukset** vasemmanpuoleisesta valikosta.
2. Valitse **Lisää sovellus**. Tämä käynnistää **Lisää ohjelmisto** -sovelluksen.

### <a name="ios"></a>iOS
1. Valitse avattavasta luettelosta **Hallittu iOS-sovellus App Storesta**.
2. Anna sovelluksen URL-osoite, jonka haimme [vaiheessa 1](#step-1-get-the-url-for-the-application), ja valitse **Seuraava**.
   
    ![](media/service-admin-mobile-intune/intune-add-software-ios1.png)
3. Anna **Julkaisija**, **Nimi** ja **Kuvaus**. Voit halutessasi lisätä **kuvakkeen**. **Luokka** on Yritysportaali-sovellus. Kun olet valmis, valitse **Seuraava**.
4. Voit päättää, missä muodossa sovellus julkaistaan (**Mikä tahansa** (oletus), **iPad** tai **iPhone**). Oletusarvon mukaan se näkyy **missä tahansa** ja toimii kummassakin laitetyypissä. Power BI -sovelluksella on sama URL-osoite iPhonessa ja iPadissa. Valitse **Seuraava**.
5. Valitse **Lataa**.

> [!NOTE]
> Se saattaa näkyä sovellusluettelossa vasta sivun päivittämisen jälkeen. Voit valita **Yleiskatsaus** ja palata takaisin **Sovellukset**-kohtaan, jotta sivu latautuu uudelleen.
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-ios2.png)

### <a name="android"></a>Android
1. Valitse avattavasta luettelosta **Ulkoinen linkki**.
2. Anna sovelluksen URL-osoite, jonka haimme [vaiheessa 1](#step-1-get-the-url-for-the-application), ja valitse **Seuraava**.
   
    ![](media/service-admin-mobile-intune/intune-add-software-android1.png)
3. Anna **Julkaisija**, **Nimi** ja **Kuvaus**. Voit halutessasi lisätä **kuvakkeen**. **Luokka** on Yritysportaali-sovellus. Kun olet valmis, valitse **Seuraava**.
4. Valitse **Lataa**.

> [!NOTE]
> Se saattaa näkyä sovellusluettelossa vasta sivun päivittämisen jälkeen. Voit valita **Yleiskatsaus** ja palata takaisin **Sovellukset**-kohtaan, jotta sivu latautuu uudelleen.
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-android2.png)

## <a name="step-4-deploy-the-application"></a>Vaihe 4: Sovelluksen käyttöönotto
Kun sovellus on lisätty, se on otettava käyttöön, jotta se on loppukäyttäjien käytettävissä. Tässä vaiheessa velvoitat käyttäjät noudattamaan sovelluksen kanssa luomaasi käytäntöä.

### <a name="ios"></a>iOS
1. Valitse luomasi sovellus sovellusten näytössä. Valitse sitten **Hallitse käyttöönottoa...** -linkki.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios1.png)
2. Voit valita **Valitse ryhmät** -ruudussa, mille ryhmille tämä sovellus otetaan käyttöön. Valitse **Seuraava**.
3. Voit valita **Käyttöönottotoiminto**-ruudussa, miten tämä sovellus otetaan käyttöön. Jos valitset **Käytettävissä oleva asennus** tai **Pakollinen asennus**, sovellus on yritysportaalissa käyttäjien asennettavissa tarvittaessa. Kun olet tehnyt valintasi, valitse **Seuraava**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios2.png)
4. Voit valita **Mobiilisovellusten hallinta** -ruudussa mobiilisovellusten hallintakäytännön, joka luotiin [vaiheessa 2](#step-2-create-a-mobile-application-management-policy). Oletuksena on luomasi käytäntö, mikäli se on ainoa käytettävissä oleva iOS-käytäntö. Valitse **Seuraava**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios3.png)
5. Voit valita **VPN-profiili**-ruudussa käytännön, jos sinulla on sellainen organisaatiollesi. Oletusarvo on **Ei mitään**. Valitse **Seuraava**.
6. Valitse **Mobiilisovelluksen määritys** -ruudussa **Sovellusten määrityskäytäntö**, jos olet luonut sellaisen. Oletusarvo on **Ei mitään**. Tämä ei ole pakollista. Valitse **Valmis**.

Kun olet ottanut sovelluksen käyttöön, sen käyttöönoton kohdalla pitäisi näkyä **Kyllä** sovellusten sivulla.

### <a name="android"></a>Android
1. Valitse luomasi sovellus sovellusten näytössä. Valitse sitten **Hallitse käyttöönottoa...** -linkki.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android1.png)
2. Voit valita **Valitse ryhmät** -ruudussa, mille ryhmille tämä sovellus otetaan käyttöön. Valitse **Seuraava**.
3. Voit valita **Käyttöönottotoiminto**-ruudussa, miten tämä sovellus otetaan käyttöön. Jos valitset **Käytettävissä oleva asennus** tai **Pakollinen asennus**, sovellus on yritysportaalissa käyttäjien asennettavissa tarvittaessa. Kun olet tehnyt valintasi, valitse **Seuraava**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android2.png)
4. Voit valita **Mobiilisovellusten hallinta** -ruudussa mobiilisovellusten hallintakäytännön, joka luotiin [vaiheessa 2](#step-2-create-a-mobile-application-management-policy). Oletuksena on luomasi käytäntö, mikäli se on ainoa käytettävissä oleva Android-käytäntö. Valitse **Valmis**.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android3.png)

Kun olet ottanut sovelluksen käyttöön, sen käyttöönoton kohdalla pitäisi näkyä **Kyllä** sovellusten sivulla.

## <a name="step-5-install-the-application-on-a-device"></a>Vaihe 5: Sovelluksen asentaminen laitteeseen
Sovellus asennetaan Yritysportaali-sovelluksen kautta. Jos et ole vielä asentanut Yritysportaalia, saat sen sovelluskaupasta iOS- tai Android-ympäristössä. Kirjaudu yritysportaaliin organisaation kirjautumistunnuksella.

1. Avaa Yritysportaali-sovellus.
2. Jos et näe Power BI -sovellusta esiteltyjen sovellusten luettelossa, valitse **Yrityksen sovellukset**.
   
    ![](media/service-admin-mobile-intune/intune-companyportal1.png)
3. Valitse Power BI -sovellus, jonka olet ottanut käyttöön.
   
    ![](media/service-admin-mobile-intune/intune-companyportal2.png)
4. Valitse **Asenna**.
   
    ![](media/service-admin-mobile-intune/intune-companyportal3.png)
5. Jos käytössäsi on iOS, sovellus työnnetään sinulle. Valitse **Asenna** työntövalintaikkunassa.
   
    ![](media/service-admin-mobile-intune/intune-companyportal5.png)

Kun sovellus on asennettu, näet, että se on **yrityksesi hallitsema**. Jos olet ottanut PIN-koodin käyttöön käytännössä, näet sen seuraavaksi.

![](media/service-admin-mobile-intune/intune-powerbi-pin.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Mobiilisovellusten hallintakäytäntöjen määrittäminen ja ottaminen käyttöön Microsoft Intune -konsolissa](https://technet.microsoft.com/library/dn878026.aspx)  
[Power BI -sovellukset mobiililaitteille](mobile-apps-for-mobile-devices.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

