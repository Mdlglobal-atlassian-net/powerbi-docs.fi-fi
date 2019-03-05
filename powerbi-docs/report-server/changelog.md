---
title: Power BI -raporttipalvelimen muutosloki
description: Power BI -raporttipalvelimen muutoslokissa on listattu jokaisen koontiversion uudet ominaisuudet ja ohjelmavirhekorjaukset.
ms.author: jtarquino
author: jtarquino
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 03/31/2018
ms.openlocfilehash: 9589c2cf5277995459a9f43f573b6e19c4c8f748
ms.sourcegitcommit: e9c45d6d983e8cd4cb5af938f838968db35be0ee
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/05/2019
ms.locfileid: "57327960"
---
# <a name="changelog-for-power-bi-report-server"></a>Power BI -raporttipalvelimen muutosloki

Power BI -raporttipalvelimen muutoslokissa on listattu jokaisen koontiversion uudet ominaisuudet ja ohjelmavirhekorjaukset.

Lisätietoja uusista ominaisuuksista on artikkelissa [Power BI -raporttipalvelinten uudet ominaisuudet](whats-new.md). 

## <a name="january-2019"></a>Tammikuu 2019

- **Power BI -raporttipalvelin**            
    - *Versio 1.4.6969.7395 (koontiversio 15.0.1102.235), julkaistu: 30. tammikuuta 2019*
        - Ohjelmavirhekorjauksia
            - Power BI -raportit
                - Korjattu suoran kyselyn yhteydessä ilmennyt perustunnistetietoihin liittyvä ongelma
                - Korjattu rivitason suojauksen suodattimien käytössä ilmennyt kaksisuuntaisiin suhteisiin liittyvä ongelma
                - Korjattu tietojen vanhenemisongelma, joka ilmeni skaalausympäristössä suoritetun mallin päivityksen jälkeen
                - Korjattu taulukon tai matriisin kaksinkertainen vierityspalkki Firefox 63+:ssa
                - Internet Explorerin +/- -kuvakkeen koko korjattu
            - Sivutetut raportit
                - Korjattu raportin jaetun tietolähteen käytön päivittämiseen liittynyt ongelma

    - *Versio 1.4.6960.38798 (koontiversio 15.0.1102.222), julkaistu: 22. tammikuuta 2019*
        - Ominaisuudet
            - Power BI -raportit 
                - Rivitason suojauksen tuki
                - Matriisin riviotsikoiden laajennus ja kutistus
                - Kopioiminen ja liittäminen .pbix-tiedostojen välillä
                - Älykkäät tasauksen apuviivat
                - SAP BW 2.0 -yhdistimen tuki
            - Järjestelmänvalvojat
                - Mahdollisuus rajoittaa resurssien tiedostopäätteitä, joita raporttipalvelimeen voi ladata
                - Mahdollisuus rajoittaa tuettuja hyperlinkkimalleja
            - Ohjelmoitavuus
                - Uusi verkko-ohjelmointirajapinta: /PowerBIReports({Id})/DataModelRoles (GET)
                - Uusi verkko-ohjelmointirajapinta: /PowerBIReports({Id})/DataModelRoles (GET ja PUT)
                - Katso lisätietoja artikkelista [Power BI -raporttipalvelimen REST API](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0)
        - Ohjelmavirhekorjauksia
            - HTML:n lisäyksen heikkous
            - Euron merkki ei näy PDF-tiedostoksi vietäessä
            - Jos useiden tietolähteiden salasana tallennetaan Power BI -raporteissa, muuttamattomat salasanat lakkaavat toimimasta
            - Visualisointien näyttämiseen liittyvät ongelmat Power BI -mobiilisovelluksessa käyttämättömyysajan jälkeen

- **Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)**
    - *Versio: 2.65.5313.1562 (tammikuu 2019), julkaistu: 30. tammikuuta 2019*
        - Pikakuvake ja kiinnitetyt kuvakkeet pysyvät Power BI -raporttipalvelimen asennuksen poistamisen jälkeen
        - Korjattu ongelma, jossa Power BI -raporttipalvelimen kiinnittäminen aloitusvalikkoon johti mustaan tekstiin mustalla kuvakkeella

    - *Versio: 2.65.5313.1421 (tammikuu 2019), julkaistu: 22. tammikuuta 2019*
        - Sisältää Power BI -raporttipalvelinyhteyden edellyttämiä muutoksia (tammikuu 2019)  

## <a name="august-2018"></a>Elokuu 2018

- **Power BI -raporttipalvelin**
    - *Versio 1.3.6816.37243 (koontiversio 15.0.2.557), julkaistu: 30. elokuuta 2018*
        - Ohjelmavirhekorjauksia
            - Korjattiin ongelma, joka liittyi siihen, että kun palvelin päivitettiin PBI-raporttipalvelimen aiemmista versioista, joissa sitovaa uudelleenohjausta ei ollut päivitetty, asiakas näki seuraavan ilmoituksen:      
            *`
            Failed to load expression host assembly. Details: Could not load file or assembly 'Microsoft.ReportingServices.ProcessingObjectModel, Version=2018.7.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040) (rsErrorLoadingExprHostAssembly)
             `*
             
            - Arvopisteen otsikon läpinäkyvyyttä koskeva ohjelmavirhe on nyt korjattu.
            
    - *Versio 1.3.6801.38816 (koontiversio 15.0.2.540), julkaistu: 15. elokuuta 2018*
        - Ominaisuudet
            - Suoran SAP HANA SSO -kyselyn Kerberos-tuki nyt käytettävissä Power BI -raporteissa
            - Mukautettujen visualisointien ohjelmointirajapinta sisältyy julkaisuun – versio 1.13.0
            - Mukautetuissa visualisoinneissa palataan edelliseen palvelimen nykyisen ohjelmointirajapintaversion kanssa yhteensopivaan versioon (jos sellainen on käytettävissä)

- **Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)**
    - *Versio: 2.61.5192.641 (elokuu 2018), julkaistu: 15. elokuuta 2018*
        - Sisältää Power BI -raporttipalvelinyhteyden edellyttämiä muutoksia (elokuu 2018).         
        
## <a name="march-2018"></a>Maaliskuu 2018

- **Power BI -raporttipalvelin**
    - *Versio 1.2.6690.34729 (koontiversio 15.0.2.402), julkaistu: 27. huhtikuuta 2018*
        - Ohjelmavirhekorjauksia
            - SQL Server Reporting Services 2017 -luetteloiden siirtämisen käyttöönotto
            - Power BI -raportit (PBIX)
                - Raportit voidaan päivittää, kun palvelin on määritetty käyttämään mukautettua tarkistusta
                - Raportin ominaisuuksien muokkaaminen ei palauta tietolähteen tunnistetietoja
            - Sivutetut raportit (RDL)
                - `Lookup()`-toiminnon tai johdannaistoimintojen, kuten `LookupSet()` ja `MultiLookup()`, käyttö RDL-lausekkeissa ei enää anna tulokseksi `#Error`
                - Linkitetyt raportit noudattavat kohderaportin sivukokoa tulostuksen yhteydessä
                - Tilauksia voidaan luoda linkitetyille raporteille, jotka käyttävät johdannaisia parametrejä
                - Moniarvoisten parametrien oletusarvoja voi muokata IE11:ssä
                - Aineistoperäisen tilauksen toimitusasetukset ovat muokattavissa
                - Tilauksia voi tarkastella ja muokata, kun tilausta suoritetaan
                - Asetuksen tietolähteen tunnistetietojen määrittäminen ei poista lausekepohjaisia yhteysmerkkijonoja
            - Suorituskyvyn mittarit
                - Trendirivit päivitetään, kun tiedot päivitetään
            - Yleiset parannukset vakauteen

    - *Versio 1.2.6660.39920 (koontiversio 15.0.2.389), julkaistu: 28. maaliskuuta 2018*
        - Ohjelmavirhekorjauksia
            - Korjattu Power BI -raporttien (PBIX) ongelma, joka esti tietojen viemisen Power BI:n visualisoinneista.
            - Korjattu Power BI -raporttien (PBIX) ongelma, joka esti URL-suodattimien toiminnan.
            - Korjattu sivutettujen raporttien (RDL) ongelma, joka esti kuvien näkymisen oikein IE11:ssä Power BI -raporttipalvelimen maaliskuun päivityksen jälkeen.

    - *Versio 1.2.6648.38132 (koontiversio 15.0.2.378), julkaistu: 19. maaliskuuta 2018*
        - Suojauspäivitykset
        - Helppokäyttötoimintojen parannuksia
        - Ohjelmavirhekorjauksia
            - Korjattu sivutettujen raporttien (RDL) ongelma, joka esti parametrien näkyvyyden linkitetyssä raportissa, kun se palautettiin ominaisuuksien muokkaamisen jälkeen.
            - Korjattu verkkoportaalin mukautettujen lomakkeiden todennuksen ongelma, joka jätti huomioimatta siirtyvän vanhenemisen evästeen.
            - Korjattu Wordiin liittyvä ongelma, joka aiheutti epätasaisen rivikorkeuden, jos rivin sisältö on tyhjä.
            - Korjattu sivutettujen raporttien (RDL) ongelma, joka poisti lausekepohjaisen yhteysmerkkijonon, kun tietolähteen tunnistetietoja muutettiin.
            - Korjattu ongelma, joka liittyi mahdollisuuteen käyttää suorituskykyilmaisinta tekstiarvojen kanssa.
            - Korjattu sivutettujen raporttien (RDL) ongelma, joka esti mahdollisuuden määrittää uusi tietojoukko olemassa olevalle sivutetulle raportille.
            - Muita vakauteen ja käytettävyyteen liittyviä korjauksia.

- **Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)**
    - Versio: 2.56.5023.1043 (maaliskuu 2018), julkaistu: 19. maaliskuuta 2018
        - Sisältää Power BI -raporttipalvelinyhteyden edellyttämiä muutoksia (maaliskuu 2018).

## <a name="october-2017"></a>Lokakuu 2017

- **Power BI -raporttipalvelin**
    - *Versio 1.1.6582.41691 (koontiversio 14.0.600.442), julkaistu: 10. tammikuuta 2018*
        - Suojauspäivitykset
        - Ohjelmavirhekorjauksia
            - Korjattu Model.GetParameters-kutsu, joka palautti tilakoodin 400.
            - Korjattu virhe, joka liittyi jaetun tietojoukon asettamiseen olemassa oleviin sivutettuihin raportteihin (RDL).
            - Korjattu ilmoitukseen ExecutionNotFoundException liittyvä virhe, joka ilmeni vietäessä eri parametriarvoilla määritettyä raporttia PDF:ksi.

    - *Versio 1.1.6551.5155 (koontiversio 14.0.600.438), julkaistu: 11. joulukuuta 2017*
        - Ohjelmavirhekorjauksia
            - Korjattu virhe, joka esti tietojen tallentamisen tiettyjen Power BI Desktop -raporttien päivittämisen jälkeen.

    - *Versio 1.1.6530.30789 (koontiversio 14.0.600.437), julkaistu: 17. marraskuuta 2017*
        - Ohjelmavirhekorjauksia
            - Korjattu perustodennuksen skenaarioiden virhe. 
            - Korjattu ongelma, joka esti arkipäivien valitsemisen tilauksiin, välimuistin päivityssuunnitelmiin ja historiatilannevedoksiin portaalin aikataulusivulla.
            - Korjattu sivutettujen raporttien (RDL) ongelma, joka tuotti värien ja fonttien osalta väärin näkyviä arvoja sellaisille tekstiruudun ilmauksille, joiden CanGrow-ominaisuusjoukon arvoksi on asetettu epätosi.
            - Korjattu Power BI -raporttien (PBIX) ongelma, joka tuotti tyhjän visualisoinnin, kun viivakaavioon lisättiin selitteitä.

    - *Versio 1.1.6514.9163 (koontiversio 14.0.600.434), julkaistu: 1. marraskuuta 2017*
        - Ohjelmavirhekorjauksia
            - Korjattu yli 500 megatavun kokoisten PBIX-raporttien lataamisen epävakausongelma.
            - Korjattu yli gigatavun kokoisten PBIX-raporttien lataamisen ongelma.

    - *Versio 1.1.6513.3500 (koontiversio 14.0.600.433), julkaistu: 31. lokakuuta 2017*
        - Ominaisuudet
            - Upotettujen tietomallien tuki
            - Excel-työkirjan tarkasteleminen (Office Online Server -integrointi käytössä)
            - Ajoitettu tietojen päivittäminen (PBIX)
            - Suorien kyselyjen tuki
            - Suurten tiedostojen tuki (jopa 2 Gt)
            - Julkinen REST-ohjelmointirajapinta
            - Jaettujen tietojoukkojen tuki Power BI Desktopissa (oDatan kautta)
            - URL-parametrin tuki PBIX-tiedostoille
            - Helppokäyttötoimintojen parannuksia

- **Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)**
    - *Versio: 2.51.4885.3981 (lokakuu 2017), julkaistu: 10. huhtikuuta 2018*
        - Suojauspäivitykset

    - *Versio: 2.51.4885.2501 (lokakuu 2017), julkaistu: 10. tammikuuta 2018*
        - Suojauspäivitykset

    - *Versio: 2.51.4885.1423 (lokakuu 2017), julkaistu: 17. marraskuuta 2017*
        - Ohjelmavirhekorjauksia
            - Korjattu ongelma, joka esti 32-bittisen Power BI Desktopin toiminnan x86-käyttöjärjestelmässä.
            - Korjattu Power BI -raportteihin (PBIX) liittyvä ongelma, joka esti x-akselin ruudukon näkymisen.
            - Muita pieniä ohjelmavirhekorjauksia

    - *Versio: 2.51.4885.1041 (lokakuu 2017), julkaistu: 31. lokakuuta 2017*
        - Ominaisuudet
            - Sisältää Power BI -raporttipalvelinyhteyden edellyttämiä muutoksia (maaliskuu 2017).

## <a name="june-2017"></a>Kesäkuu 2017

- **Power BI -raporttipalvelin**
    - *Koontiversio 14.0.600.309, julkaistu: 10. tammikuuta 2018*
        - Suojauspäivitykset

    - *Koontiversio 14.0.600.305, julkaistu: 19. syyskuuta 2017*  
        - Ohjelmavirhekorjauksia
            - Päivitys uusimpaan [Bing-karttojen verkko-ohjausobjektiin](https://msdn.microsoft.com/library/mt712542.aspx)

    - *Koontiversio 14.0.600.301, julkaistu: 11. heinäkuuta 2017*
        - Ohjelmavirhekorjauksia
            - Korjattu ongelma, joka aiheutti `{{UserId}}`-tunnisteen ratkaisemisen tallennettuihin tunnistetietoihin sen sijaan, että raportti suoritettaisiin Power BI -raporteissa.
            - Korjattu ongelma, joka esti tiettyjen kuvien piirtymisen Power BI -raporttipalvelimen raportteihin.
            - Korjattu ongelma, joka esti Power BI -raportin nimen muuttamisen Power BI -raporttipalvelimessa.
            - Korjattu ongelma, joka esti mukautettujen visualisointien lataamisen Power BI -mobiilisovellukseen ilman paikallisen välimuistin tyhjentämistä asentamalla mobiilisovellus uudelleen.

    - *Koontiversio 14.0.600.271, julkaistu: 12. kesäkuuta 2017*
        - Power BI -raporttipalvelimen ensimmäinen julkaisu

- **Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)**
    - *Versio: 2.47.4766.4901 (kesäkuu 2017), julkaistu: 10. tammikuuta 2018*
        - Suojauspäivitykset

## <a name="next-steps"></a>Seuraavat vaiheet

[Mikä on Power BI -raporttipalvelin?](get-started.md)
[Järjestelmänvalvojien yleiskatsaus](admin-handbook-overview.md)  
[Power BI -raporttipalvelimen asentaminen](install-report-server.md)  
[Raportin muodostimen lataaminen](https://www.microsoft.com/download/details.aspx?id=53613)  
[SQL Server Data Tools (SSDT) -työkalujen lataaminen](http://go.microsoft.com/fwlink/?LinkID=616714)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
