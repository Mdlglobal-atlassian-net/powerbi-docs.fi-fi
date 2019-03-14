---
title: Mallisovellusten luominen Power BI:ssä (esikatselu)
description: Sellaisten mallisovellusten luominen Power BI:ssä, joita voi jakaa kaikille Power BI -asiakkaille.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: maggies
ms.openlocfilehash: c08b7e60777b720aa4fc2489b02c212bdd3e7169
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/14/2019
ms.locfileid: "56249659"
---
# <a name="create-a-template-app-in-power-bi-preview"></a>Mallisovelluksen luominen Power BI:ssä (esikatselu)

Power BI:n uusien *mallisovellusten* avulla Power BI -kumppanit voivat kehittää Power BI -sovelluksia käyttäen vain vähän tai ei lainkaan koodausta, minkä lisäksi sovellukset voidaan ottaa käyttöön kenelle tahansa Power BI -asiakkaalle.  Tässä artikkelissa on vaiheittaiset ohjeet Power BI -mallisovelluksen luomiseen. 

Jos luot Power BI -raportteja ja koontinäyttöjä, voit ryhtyä *mallisovelluksen kehittäjäksi*, joka laatii ja paketoi analyysisisältöä *sovellukseksi*. Voit sitten ottaa sovelluksesi muiden Power BI -vuokraajien käyttöön hyödyntämällä jotakin käytettävissä olevaa ympäristöä, kuten AppSourcea, tai käyttämällä sovellusta omassa verkkopalvelussasi. Kehittäjänä voit luoda suojatun analytiikkapaketin jakelua varten. 

Power BI -vuokraajan järjestelmänvalvojat hallinnoivat ja ohjaavat sitä, ketkä organisaation käyttäjät voivat luoda mallisovelluksia ja ketkä voivat asentaa niitä. Valtuutetut käyttäjät voivat asentaa mallisovelluksesi, muokata sitä ja jakaa sen organisaation Power BI -käyttäjille.

## <a name="prerequisites"></a>Edellytykset 

Mallisovelluksen kehittämistä varten tarvitaan:  

- [Power BI Pro -käyttöoikeus](service-self-service-signup-for-power-bi.md)
- [Power BI Desktop -asennus](desktop-get-the-desktop.md) (valinnainen)
- [Power BI-peruskäsitteiden](service-basic-concepts.md) tuntemus
- oikeudet luoda mallisovelluksia. Lisätietoja on Power BI:n [hallintaportaalin kohdassa Mallisovelluksen asetukset](service-admin-portal.md#template-apps-settings-preview).

## <a name="enable-app-developer-mode"></a>Ota käyttöön sovelluskehittäjän tila

Jotta voisit luoda mallisovelluksen, jonka voi jakaa muille Power BI -vuokraajille, sinun tulee olla sovelluskehittäjän tilassa. Muussa tapauksessa luot sovelluksen vain oman organisaatiosi Power BI -kuluttajille.
 
1. Avaa Power BI -palvelu selaimessa.
2. Valitse **Asetukset** > **Yleiset** > **Kehittäjä** > **Ota käyttöön mallisovelluksen kehitystila**.

    ![Ota käyttöön mallisovellukset](media/service-template-apps-create/power-bi-dev-template-app.png)

    Jos et näe tätä asetusta, ota yhteyttä Power BI-järjestelmänvalvojaasi ja pyydä häntä myöntämään [mallisovellusten kehitysoikeudet](service-admin-portal.md#template-apps-settings-preview) hallintaportaalissa.

3. Valitse **Käytä**.

## <a name="create-the-template-app-workspace"></a>Mallisovelluksen luonnin työtila

Jotta voisit luoda mallisovelluksen, jonka voi jakaa muille Power BI -vuokraajille, mallisovellus tulee luoda jossakin uusista sovellustyötiloista. 
 
1. Valitse Power BI -palvelussa **Työtilat** > **Luo sovellustyötila**. 
 
    ![Luo sovellustyötila](media/service-template-apps-create/power-bi-new-workspace.png)

3. Valitse **Luo sovellustyötila** -kohdan **Esikatsele paranneltuja työtiloja** -asetuksessa **Kokeile nyt**.

    ![Uusien työtilojen kokeileminen](media/service-template-apps-create/power-bi-try-now-new-workspace.png)

5. Kirjoita sovellustyötilan nimi, kuvaus (valinnainen) ja logokuva (valinnainen).

4. Valitse **Kehitä mallisovellus**.

    ![Kehitä mallisovellus](media/service-template-apps-create/power-bi-template-app-develop.png)

5. Valitse **Tallenna**.

## <a name="create-the-content-in-your-template-app"></a>Luo mallisovelluksesi sisältö

Kuten tavallisessakin Power BI -sovellustyötilassa, seuraava tehtäväsi on luoda työtilan sisältö.  Tässä mallisovellusten esikatseluversiossa tuetaan enintään yhtä kustakin lajista: yhtä tietojoukkoa, yhtä raporttia ja yhtä koontinäyttöä.

- [Luo oma Power BI -sisältösi](power-bi-creator-landing.md) sovellustyötilassa.

Jos käytät Power Query -parametreja, varmista, että niiden tietolaji on määritelty hyvin (esimerkiksi teksti). Tietolajeja Mikä tahansa ja Binaarinen ei tueta. 

[Vihjeitä mallisovellusten luomiseen Power BI:ssä (esikatselu)](service-template-apps-tips.md) -artikkelissa on ehdotuksia, jotka kannattaa ottaa huomioon, kun luodaan raportteja ja koontinäyttöjä mallisovellusta varten.

## <a name="create-the-test-template-app"></a>Luo testimallisovellus

Nyt kun työtilassasi on sisältöä, voit pakata sen mallisovellukseksi. Ensimmäiseksi luodaan koemallisovellus, jota voi käyttää vain organisaatiostasi käsin omalla vuokraajallasi.

1. Valitse mallisovellus-työtilassa **Luo sovellus**. 

    ![Luo sovellus](media/service-template-apps-create/power-bi-create-app.png)
 
    Täällä voit lisätä mallisovellukseen neljän luokan parametreja. 

    **Tuotemukautus**

    - Sovelluksen nimi 
    - Kuvaus
    - Sovelluksen logo (valinnainen)
    - Sovelluksen väri 

    **Sisältö** 

    - Sovelluksen aloitussivu (valinnainen): Määritä sovelluksesi aloitussivuksi jokin raportti tai koontinäyttö.  
    
    **Hallinta** 

    Voit hallinnoida rajoituksia, jotka säätelevät sitä, miten sovelluksen käyttäjät voivat käyttää sovelluksesi sisältöä. Näin voit suojata tiettyjä immateriaalioikeuksia, joita sovelluksesi saattaa sisältää.

    **Käyttöoikeudet**

    - Päätä testivaiheessa, ketkä muut organisaatiosi käyttäjät voivat asentaa sovelluksesi ja testata sitä.

    Voit aina palata takaisin ja muuttaa näitä asetuksia myöhemmin.  

2. Valitse **Luo sovellus**. 

    Näyttöön tulee sanoma, joka ilmoittaa koesovelluksen olevan valmis. Mukana on linkki, jonka voit kopioida ja jakaa sovelluksen testaajille.

    ![Testisovellus on valmis](media/service-template-apps-create/power-bi-template-app-test-ready.png)

    Olet samalla suorittanut ensimmäisen vaiheen julkaisuhallinnan prosessista, joka käsitellään seuraavaksi.

    

## <a name="manage-the-template-app-release"></a>Mallisovelluksen julkaisemisen hallinta

Ennen kuin julkaiset mallisovellusta, kannattaa varmistaa, että kaikki on kunnossa. Power BI on luonut julkaisuhallinnan ruudun, jossa voit seurata ja tarkastella sovelluksen koko julkaisupolkua. Voit myös käynnistää siirtymän vaiheesta toiseen. Perusvaiheita ovat seuraavat: 

- Testisovelluksen luonti: Vain organisaation sisäistä testausta varten. 
- Testipaketin ylennys esituotantovaiheeseen: Testaus organisaatiosi ulkopuolella.
- Esituotantopaketin ylennys tuotannoksi: Tuotantoversio. 
- Poista paketti tai aloita uudelleen edellisestä vaiheesta. 

Käydään seuraavaksi vaiheet läpi.

1. Valitse mallisovellus-työtilassa **Julkaisun hallinta**.

    ![Julkaisun hallinta -kuvake](media/service-template-apps-create/power-bi-release-management-icon.png)

2. Valitse **Luo sovellus**. 

    Jos olet luonut testisovelluksen yllä kuvatussa **Luo testimallisovellus** -vaiheessa, **Testataan**-kohdan vieressä oleva keltainen pallo on jo täyttynyt eikä tässä vaiheessa tarvitse valita **Luo sovellus** -vaihtoehtoa. Jos kuitenkin valitset sen, palaat mallisovelluksen luontiin.
 
3. Valitse **Hanki linkki**.

    ![Luo sovellus, hanki linkki](media/service-template-apps-create/power-bi-dev-template-create-app-get-link.png)
 
9. Voit testata sovelluksen asennusta kopioimalla ilmoitusikkunassa olevan linkin ja liittämällä sen uuteen selainikkunaan. 

    Tästä eteenpäin teet samat toiminnot kuin mitä asiakkaasi tulevat tekemään. Asiakkaiden versio on kohdassa [Mallisovellusten asentaminen ja jakaminen organisaatiossa](service-template-apps-install-distribute.md).
 
10. Valitse valintaikkunassa **Asenna**.

    Kun asennus on valmis, näkyviin tulee ilmoitus, että uusi sovellus on valmis. 
 
11. Valitse **Siirry sovellukseen**.
 
12. **Aloita uuden sovelluksesi käyttö** -kohdassa näet sovelluksen samanlaisena kuin asiakkaasi näkevät sen. 

    ![Aloita sovelluksesi käyttö](media/service-template-apps-create/power-bi-template-app-get-started.png)

13. Valitse **Tarkastele sovellusta** ja vahvista testisovelluksen toiminta mallitietojen kanssa.

1. Jos haluat tehdä muutoksia, palaa sovellukseen alkuperäisessä työtilassa. Päivitä testisovellusta, kunnes olet tyytyväinen.

9. Kun olet valmis ylentämään sovelluksesi esituotantoon, niin että sen testausta voidaan jatkaa oman vuokraajasi ulkopuolella, palaa **Julkaisun hallinta** -ruutuun ja valitse **Testataan**-kohdan vierestä **Ylennä sovellus**.
 
    ![Ylennä sovellus esituotantoon](media/service-template-apps-create/power-bi-template-app-promote.png)

11. Vahvista valintasi valitsemalla **Ylennä**. 

12. Kopioi tämä uusi URL-osoite, niin voit jakaa sen oman vuokraajasi ulkopuolelle testausta varten. Tämän linkin lähettämällä voit myös aloittaa sovelluksesi jakamisen AppSourcessa.

12. Kun sovelluksesi on valmis tuotantoon tai jaettavaksi AppSourcen kautta, palaa takaisin **Julkaisuhallinta**-ruutuun ja valitse **Esituotanto**-kohdan vierestä **Ylennä sovellus**.
 
11. Vahvista valintasi valitsemalla **Ylennä**. 

    Sovelluksesi on nyt tuotannossa ja valmis jaettavaksi.

    ![Sovellus tuotannossa](media/service-template-apps-create/power-bi-template-app-production.png)

Jos haluat saada sovelluksesi tuhansien Power BI -käyttäjien saataville maailmanlaajuisesti, kannustamme sinua lähettämään sen AppSourceen. Lisätietoja on kohdassa [Power BI -sovellustarjous](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer). 

## <a name="update-your-app"></a>Päivitä sovelluksesi

Kun sovelluksesi on nyt tuotantoympäristössä, voit aloittaa alusta testausvaiheessa häiritsemättä tuotantoympäristössä olevaa sovellusta. 

1. Valitse **Julkaisun hallinta** -ruudussa **Luo sovellus**.

1. Suorita sovelluksen luontiprosessi uudelleen. 
2. Kun olet määrittänyt **tuotemerkkiohjeet**, **sisällön**, **hallinnan** ja **käyttöoikeudet**, voit uudelleen valita **Luo sovellus** -vaihtoehdon.
3. Valitse **Sulje** ja palaa **Julkaisun hallintaan**. 

    Näkyvillä on nyt kaksi versiota: tuotantoympäristössä oleva versio sekä testausvaiheessa oleva uusi versio. 

    ![Mallisovelluksen kaksi versiota](media/service-template-apps-create/power-bi-template-app-2-versions.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Ohjeaiheessa [Mallisovellusten asentaminen, mukauttaminen ja jakaminen organisaatiossa](service-template-apps-install-distribute.md) voit selvittää, miten asiakkaasi käsittelevät mallisovellusta.

Lisätietoja sovelluksen jakamisesta on kohdassa [Power BI -sovellustarjous](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).




