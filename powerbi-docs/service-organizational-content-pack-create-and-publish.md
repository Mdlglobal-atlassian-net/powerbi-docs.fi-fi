---
title: Organisaation sisältöpaketin luominen ja julkaiseminen - Power BI
description: Tässä opetusohjelmassa luodaan organisaation sisältöpaketti, rajoitetaan käyttö tiettyyn ryhmään ja julkaistaan se organisaatiosi sisältöpakettikirjastossa Power BI:ssä.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/06/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: eb1940f7d5a4e809590b5b425b8005776040a5cc
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "72020660"
---
# <a name="tutorial-create-and-publish-a-power-bi-organizational-content-pack"></a>Opetusohjelma: Organisaation sisältöpaketin luominen ja julkaiseminen Power BI:ssä

Tässä opetusohjelmassa luodaan organisaation sisältöpaketti, annetaan käyttö tiettyyn ryhmään ja julkaistaan se organisaatiosi sisältöpakettikirjastossa Power BI:ssä.

Sisältöpakettien luominen eroaa koontinäyttöjen jakamisesta tai niiden työstämisestä ryhmässä. Lue [Töiden jakamistavat Power BI:ssä](service-how-to-collaborate-distribute-dashboards-reports.md) ja valitse omaan tilanteesi parhaiten sopiva vaihtoehto.

Organisaation sisältöpaketin luominen edellyttää [Power BI Pro -tiliä](https://powerbi.microsoft.com/pricing) sinulle ja työtovereillesi.

> [!NOTE]
> Et voi luoda tai asentaa organisaation sisältöpaketteja uusissa työtilakokemuksissa. Nyt on hyvä aika päivittää sisältöpaketit sovelluksiin, jos et ole vielä aloittanut päivittämistä. Lue [lisätietoja uudesta työtilakokemuksesta](service-create-the-new-workspaces.md).

## <a name="create-and-publish-a-content-pack"></a>Sisältöpaketin luominen ja julkaiseminen

Kuvittele olevasi Release Manager Contosossa ja valmistaudut uuden tuotteen julkaisun varten.  Olet luonut koontinäytön ja raportit, jotka haluat jakaa. Muut käynnistämistä hallitsevat työntekijät voivat havaita ne hyödyllisiksi. Haluat saada tavan pakata raporttinäkymän ja raportit ratkaisuna työtovereidesi käyttöön.

Haluatko seurata mukana? Siirry [Power BI -palvelussa](https://powerbi.com) **omaan työtilaan**. Siirry sitten kohtaan **Nouda tiedot** > **Näytteet** > **Mahdollisuusanalyysimalli**  > **Yhteydet** ja hanki oma kopio.

1. Valitse vasemmassa siirtymisruudussa **Työtilat** > **Oma työtila**.

1. Valitse ylälaidan siirtymispalkissa hammasrataskuvake ![Näyttökuva hammasrataskuvakkeesta.](media/service-organizational-content-pack-create-and-publish/cog.png) > **Luo sisältöpaketti**.

   ![Näyttökuva käyttöliittymästä, jossa painopisteenä ovat hammasrataskuvake ja Luo sisältöpaketti -asetus.](media/service-organizational-content-pack-create-and-publish/pbi_create_contpk.png)

1. Anna **Luo sisältöpaketti** -ikkunassa seuraavat tiedot.  

   Muista, että organisaatiosi sisältöpakettikirjasto saattaa täyttyä nopeasti. Kirjastoon voi päättyä satoja sisältöpaketteja, jotka on julkaistu organisaatiolle tai ryhmille. Paneudu hetkeksi sisältöpaketin nimeämiseen, jotta se on kuvaava, lisää sopiva kuvaus ja valitse oikea kohderyhmä.  Käytä sanoja, jotka helpottavat sisältöpaketin löytämistä haun avulla. Se helpottaa etsimistä jatkossa.

      ![Näyttökuva valmiista Luo sisältöpaketti -lomakkeesta.](media/service-organizational-content-pack-create-and-publish/cpwindow.png)

    1. Valitse **Tietyt ryhmät**.

    1. Kirjoita henkilöiden, [Office 365 -ryhmien](https://support.office.com/article/Create-a-group-in-Office-365-7124dc4c-1de9-40d4-b096-e8add19209e9), jakeluryhmien tai käyttöoikeusryhmien koko sähköpostiosoitteet. Esimerkki: salesmgrs@contoso.com; sales@contoso.com

        Tässä opetusohjelmassa voit kokeilla ryhmän sähköpostiosoitteen käyttämistä.

    1. Nimeä sisältöpaketti *Myyntimahdollisuudet*.

        > [!TIP]
        > Harkitse, voiko sisältöpakein nimeen liittää raporttinäkymän nimen. Tällä tavoin työtoverisi löytää raporttinäkymän helpommin sen jälkeen, kun on muodostanut yhteyden sisältöpakettiisi.

    1. Suositus: Lisää kuvaus. Sen avulla työtoverin on helppo löytää sisältöpaketteja, joita he tarvitsevat. Kuvauksen lisäksi lisää avainsanoja, joilla työtoverisi saattavat hakea tätä sisältöpakettia. Sisällytä myös yhteystiedot siltä varalta, että työtoverillasi on kysyttävää tai hän tarvitsee apua.

    1. Lataa kuva tai logo, jotta ryhmän jäsenet löytävät sisältöpaketin helposti.

        Kuvan silmäileminen on nopeampaa kuin tekstin silmäileminen. Näyttökuvassa on kuva **Mahdollisuuksien lukumäärä** -pylväskaavion ruudusta.

    1. Valitse **Mahdollisuusanalyysimalli** -raporttinäkymä lisätäksesi sen sisältöpakettiin.

        Power BI lisää automaattisesti liittyvän raportin ja tietojoukon. Voit lisätä myös muita, jos haluat.

       > [!NOTE]
       > Power BI luettelee vain raporttinäkymät, raportit, tietojoukot ja työkirjat, joita voit muokata. Näin ollen sovellus ei näytä sinulle jaettuja kohteita.

   1. Jos sinulla on Excel-työkirjoja, näet ne kohdassa **Raportit** Excel-kuvakkeella varustettuina. Voit lisätä ne myös sisältöpakettiin.

      ![Näyttökuva Raportit-osasta ja valittavissa olevista raporteista.](media/service-organizational-content-pack-create-and-publish/pbi_orgcontpkexcel.png)

      > [!NOTE]
      > Jos ryhmän jäsenet eivät voi tarkastella Excel-työkirjaa, voit joutua [jakamaan työkirjan heidän kanssaan OneDrive for Business -palvelussa](https://support.office.com/article/Share-documents-or-folders-in-Office-365-1fe37332-0f9a-4719-970e-d2578da4941c).

1. Valitse **Julkaise** lisätäksesi sisältöpaketin ryhmän Organisaation sisältöpaketit -kirjastoon.  

   Kun julkaisu onnistuu, esiin tulee onnistumisesta ilmoittava viesti.

1. Kun ryhmäsi jäsenet siirtyvät kohtaan **Nouda tiedot** > **Organisaation sisältöpaketit**, he näkevät sisältöpakettisi.

   ![Näyttökuva Myyntimahdollisuudet-sisältöpaketista AppSource-valintaikkunassa.](media/service-organizational-content-pack-create-and-publish/powerbi-find-content-pack-organization.png)

   > [!TIP]
   > Selaimessa näkyvä URL-osoite on tämän sisältöpaketin yksilöllinen osoite.  Haluatko kertoa työtovereillesi tästä uudesta sisältöpaketista?  Liitä URL-osoite sähköpostiviestiin.

1. Kun ryhmäsi jäsenet valitsevat **Yhdistä**, he voivat [tarkastella ja käsitellä sisältöpakettiasi](service-organizational-content-pack-copy-refresh-access.md).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Power BI:n organisaation sisältöpakettien esittely](service-organizational-content-pack-introduction.md)

* [Organisaation sisältöpakettien hallinta, päivitys ja poistaminen](service-organizational-content-pack-manage-update-delete.md)

* [Julkaise sovellus Power BI:ssä](service-create-distribute-apps.md).

* [Mikä on OneDrive for Business?](https://support.office.com/article/What-is-OneDrive-for-Business-187f90af-056f-47c0-9656-cc0ddca7fdc2)

* Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
