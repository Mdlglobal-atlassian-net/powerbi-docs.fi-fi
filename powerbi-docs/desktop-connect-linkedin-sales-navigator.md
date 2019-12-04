---
title: Yhdistäminen LinkedIn Sales Navigatoriin Power BI Desktopissa
description: LinkedIn-tietoihin yhdistäminen ja tietojen käyttäminen helposti Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/11/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: cd952dfa690d079d662f09e1e01c34dadf129b7b
ms.sourcegitcommit: a21f7f9de32203e3a4057292a24ef9b5ac6ce94b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/27/2019
ms.locfileid: "74565635"
---
# <a name="connect-to-linkedin-sales-navigator-in-power-bi-desktop"></a>Yhdistäminen LinkedIn Sales Navigatoriin Power BI Desktopissa

**Power BI Desktopissa** voit muodostaa yhteyden **LinkedIn Sales Navigatoriin** sekä etsiä ja kehittää sen avulla suhteita aivan samalla tavalla kuin muiden tietolähteiden kanssa Power BI Desktopissa, minkä lisäksi voit luoda valmiita raportteja kehityksestä.

![LinkedIn Sales Navigatorin Käyttö-välilehti](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-01.png)


Jos haluat muodostaa yhteyden LinkedIn-tietoihin käyttämällä **LinkedIn Sales Navigatoria**, tarvitset LinkedIn Sales Navigator Enterprise -tilauksen, minkä lisäksi sinun on oltava Sales Navigator -sopimuksen järjestelmänvalvoja tai raportoiva käyttäjä.

Seuraava video on lyhyt esittely ja opetusohjelma **LinkedIn Sales Navigator** -mallisovelluksen käytöstä; mallisovellus kuvataan tarkemmin [edempänä tässä artikkelissa](#using-the-linkedin-sales-navigator-template-app). 

> [!VIDEO https://www.youtube.com/embed/ZqhmaiORLw0]

## <a name="connect-to-linkedin-sales-navigator"></a>Yhdistäminen LinkedIn Sales Navigatoriin

Voit yhdistää **LinkedIn Sales Navigatorin** tietoihin valitsemalla Power BI Desktopin **Aloitus**-valintanauhasta **Nouda tiedot**. Valitse vasemmalla olevista luokista **Online-palvelut** ja vieritä sitten, kunnes näkyviin tulee **LinkedIn Sales Navigator (Beta)** .

![Nouda tiedot Power BI Desktopissa](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-02.png)

Saat ilmoituksen, että muodostat yhteyden kolmannen osapuolen liittimeen, joka on vielä kehitteillä. 

![Kolmatta osapuolta koskeva varoitus](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-03.png)

Kun valitset **Jatka**, sinua pyydetään määrittämään, mitä tietoja haluat.

![Kehote annettavista tiedoista](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-04.png)


Valitse näkyviin tulevan **LinkedIn Sales Navigator** -ikkunan ensimmäisestä avattavasta valitsimesta, mitä tietoja haluat palautettavan, joko *Kaikki yhteystiedot* tai *Valitut yhteystiedot*. Voit sitten rajoittaa palautettavat tiedot tietylle aikavälille määrittämällä alkamis- ja päättymispäivämäärän.

Kun olet antanut tiedot, Power BI Desktop muodostaa yhteyden LinkedIn Sales Navigator -sopimukseesi liittyviin tietoihin. Käytä samaa sähköpostiosoitetta, jolla kirjaudut sisään LinkedIn Sales Navigatoriin verkkosivuston kautta. 

![Kirjautuminen LinkedIniin](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-05.png)

Kun olet muodostanut yhteyden, näyttöön tulee kehote valita LinkedIn Sales Navigator -sopimuksen tietoja **Navigator**-ikkunasta.

![Tietojen valitseminen Navigatorilla](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-09.png)

Voit luoda LinkedIn Sales Navigator -tiedoilla millaisia raportteja tahansa. Asioiden helpottamiseksi tarjolla on myös LinkedIn Sales Navigatorin .PBIX-tiedosto, jonka voit ladata ja jossa on valmiina mallitietoja, niin ettei sinun tarvitse aloittaa tyhjästä vaan voit tutustua tietoihin ja raportteihin.

Voit ladata PBIX-tiedoston seuraavasta sijainnista:
* [LinkedIn Sales Navigatorin PBIX](service-template-apps-samples.md)

PBIX-tiedoston lisäksi LinkedIn Sales Navigatorissa on myös mallisovellus, jonka voit ladata ja jota voit käyttää. Seuraavassa osiossa mallisovellus kuvataan tarkasti.


## <a name="using-the-linkedin-sales-navigator-template-app"></a>LinkedIn Sales Navigator -mallisovelluksen käyttäminen

Voit helpottaa **LinkedIn Sales Navigatorin** käyttöä hyödyntämällä [mallisovellusta](service-template-apps-overview.md), joka luo LinkedIn Sales Navigator -tiedoistasi automaattisesti valmiin raportin.

![LinkedIn Sales Navigatorin mallisovellus](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-10.png)

Kun lataat sovelluksen, voit valita, muodostetaanko yhteys tietoihisi vai haluatko tutustua sovellukseen käyttämällä mallitietoja. Voit aina palata taaksepäin ja muodostaa yhteyden omiin LinkedIn Sales Navigatorin tietoihisi, kun olet ensin tutkinut mallitietoja. 

![Yhteyden muodostaminen LinkedIn Sales Navigatorin tietoihin](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-11.png)



Saat **LinkedIn Sales Navigatorin** mallisovelluksen seuraavasta linkistä:
* [LinkedIn Sales Navigator -mallisovellus](https://appsource.microsoft.com/product/power-bi/pbi-contentpacks.linkedin_navigator-preview?flightCodes=17ad4c68-fbc5-4925-a351-139fd384ec33)

Mallisovelluksessa on neljä välilehteä, jotka auttavat analysoimaan ja jakamaan tietoja:

* Käyttö
* Hae
* InMail
* SSI

**Käyttö**-välilehdellä näkyvät yleiset LinkedIn Sales Navigatorin tietosi.

![LinkedIn Sales Navigatorin Käyttö-välilehti](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-12.png)

**Hae**-välilehdellä voit porautua syvemmälle hakutuloksiin:

![LinkedIn Sales Navigatorin Hae-välilehti](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-13.png)

**InMail**-välilehdellä on tietoja InMailin käytöstäsi, kuten lähetettyjen InMail-viestien määrä, hyväksymisprosentti ja muita hyödyllisiä tietoja:

![LinkedIn Sales Navigatorin InMail-välilehti](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-14.png)

**SSI**-välilehdellä on lisätietoja SSI (Social Selling Index) -arvostasi:

![LinkedIn Sales Navigatorin SSI-välilehti](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-15.png)

Jos haluat siirtyä mallitiedoista omiin tietoihisi, valitse oikeasta yläkulmasta **muokkaa sovellusta** (kynäkuvake) ja valitse sitten näkyviin tulevasta ruudusta **Yhdistä tietosi**.

![Omien tietojen yhdistäminen](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-16.png)

Voit sitten muodostaa yhteyden omiin tietoihisi ja valita, monenko päivän tiedot ladataan. Voit ladata enintään 365 päivän tiedot. Sinun tulee kirjautua sisään käyttämällä samaa sähköpostiosoitetta, jolla kirjaudut sisään LinkedIn Sales Navigatoriin verkkosivuston kautta. 

![Kirjaudu sisään](media/desktop-connect-linkedin-sales-navigator/linkedin-sales-navigator-17.png)

Mallisovellus päivittää sitten sovelluksen tiedot omilla tiedoillasi. Voit myös määrittää ajoitetun tietojen päivityksen, niin että sovelluksesi tiedot ovat niin ajan tasalla kuin päivitystiheytesi määrittää. 

Kun tiedot ovat päivittyneet, näet sovelluksen täyttyneen omilla tiedoillasi.

## <a name="getting-help"></a>Ohjeiden hakeminen

Jos yhteyden muodostaminen tietoihisi aiheuttaa ongelmia, voit ottaa yhteyttä LinkedIn Sales Navigator -tukeen osoitteessa https://www.linkedin.com/help/sales-navigator. 

## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   

