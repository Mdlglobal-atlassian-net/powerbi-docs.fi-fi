---
title: Power BI -visualisointien ohjeet
description: Lue ohjeet siihen, miten voit julkaista omia visualisointejasi Microsoft AppSourcessa muiden löydettäviksi ja käytettäviksi maksua vastaan.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 07/16/2019
ms.openlocfilehash: 6bf7610a010a72248a3d2fdd96718eea513a68da
ms.sourcegitcommit: 5bb62c630e592af561173e449fc113efd7f84808
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/11/2019
ms.locfileid: "75000085"
---
# <a name="guidelines-for-power-bi-visuals"></a>Power BI -visualisointien ohjeet
Ennen kuin [julkaiset](https://docs.microsoft.com/power-bi/developer/office-store) Power BI -visualisoinnin Microsoft AppSourcessa muiden käytettäväksi, varmista, että noudatat ohjeita, jotta käyttäjäsi saavat erinomaisen käyttökokemuksen.

## <a name="power-bi-visuals-with-additional-purchases"></a>Lisäostoja sisältävät Power BI -visualisoinnit

Voit lähettää maksuttomia Power BI -visualisointeja Marketplacelle (Microsoft AppSource). Voit myös lähettää Microsoft AppSourceen Power BI -visualisointeja, joissa on ”lisäosto saattaa olla tarpeen” -hintalappu. ”Lisäosto saattaa olla tarpeen” -Power BI -visualisoinnit ovat samankaltaisia kuin Office-kaupan apuohjelmien sovelluskohtaiset ostokset. 

Ostoja sisältävät Power BI -visualisoinnit voidaan sertifioida maksuttomien Power BI -visualisointien tapaan. Ennen kuin lähetät ostoja sisältävää Power BI -visualisointia sertifioitavaksi, varmista, että se täyttää [sertifioinnin edellytykset](../power-bi-custom-visuals-certified.md). 

### <a name="what-is-a-power-bi-visual-with-iap-features"></a>Mikä on sovelluskohtaisia ostoja sisältävä Power BI -visualisointi?

Ostoja sisältävä Power BI -visualisointi on *ilmainen* visualisointi, jossa on *maksuttomia ominaisuuksia*. Siihen liittyy myös lisäominaisuuksia, jotka saattavat vaatia lisämaksuja. Kehittäjien on ilmoitettava käyttäjille Power BI -visualisoinnin kuvauksessa siitä, minkä ominaisuuksien käyttö edellyttää lisäostoja. Microsoft ei tällä hetkellä tarjoa omia ohjelmointirajapintoja, jotka tukisivat ostoja sovelluksissa ja apuohjelmissa.

Kehittäjät voivat käyttää ostoihin haluamaansa kolmannen osapuolen maksujärjestelmää. Lisätietoja on [Microsoftin myymälä-käytännössä](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads).


>[!IMPORTANT]  
> Jos päivität Power BI -visualisoinnin ilmaisesta ”Lisäosto saattaa olla tarpeen” -tasolle, käyttäjien on saatava sama ilmainen toimintotaso kuin ennen päivitystä. Voit lisätä valinnaisia maksullisia lisäominaisuuksia aiempien maksuttomien ominaisuuksien lisäksi.

### <a name="watermarks"></a>Vesileimat

Voit käyttää vesileimoja, jolloin asiakkaat jatkavat ostettavien lisäominaisuuksien käyttöä ilman maksua. 

Vesileimojen avulla voidaan esitellä Power BI -visualisoinnin täyttä toiminnallisuutta ennen ostotapahtumaa. 

* Vesileimoja voi käyttää ainoastaan maksullisissa ominaisuuksissa, joita käytetään ilman kelvollista käyttöoikeutta.
* Vesileimoja ei sallita Power BI -visualisoinneissa, joiden on *Maksuton*-hintalappu.
* Vesileimoja ei sallita ostoja sisältävissä visualisoinneissa, kun käyttäjä käyttää maksuttomia ominaisuuksia. 

### <a name="pop-up-window"></a>Ponnahdusikkuna

Ponnahdusikkunan avulla voit selittää, miten käyttöoikeus ostetaan, jos ostoja sisältävää Power BI -visualisointia käytetään virheellisellä (tai vanhentuneella) käyttöoikeudella.

### <a name="submission-process"></a>Lähettämisprosessi

Noudata [lähettämisprosessia](office-store.md#submitting-to-appsource) ja siirry *Tuotteen asennus* ‑välilehdelle ja valitse *Tuotteeni edellyttää palvelun ostamista* ‑valintaruutu.

Kun Power BI -visualisointi on vahvistettu ja hyväksytty, Microsoft AppSourcessa ilmoitetaan sovelluskohtaisia ostoja sisältävän Power BI -visualisoinnin hinnoitteluvaihtoehtojen kohdalla, että käyttö saattaa edellyttää lisäostoja.

>[!NOTE]
>Jos Power BI -visualisointisi on jo lähetetty [myyjän koontinäytön](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store) kautta ja haluat lisätä siihen sovelluskohtaisia ostoja edellyttävän ominaisuuden, sinun on kirjoitettava myyjän koontinäytön huomautuksiin ”Visual with in-app purchase” (Sovelluskohtaisia ostoja sisältävä visualisointi). Lisäksi sinun tulee antaa käyttöoikeusavain tai -tunnus, jotta vahvistustiimi voi vahvistaa sovelluskohtaisia ostoja edellyttävät ominaisuudet.

## <a name="context-menu"></a>Pikavalikko
Pikavalikko on hiiren kakkospainikkeella avautuva valikko, joka tulee näkyviin, kun hiiren osoitin on visualisoinnin päällä.
Kaikissa Power BI:n visualisoinneissa tulee ottaa pikavalikko käyttöön, jotta käyttökokemus on yhtenäinen. Lue [tästä artikkelista](https://github.com/Microsoft/PowerBI-visuals/blob/gh-pages/tutorials/building-bar-chart/adding-context-menu-to-the-bar.md) pikavalikon lisäämisohjeet.

## <a name="commercial-logo"></a>Kaupallinen logo
Tässä osiossa annetaan ohjeet Power BI -visualisointien kaupallisten logojen lisäämiseen. Kaupalliset logot eivät ole pakollisia. Jos ne lisätään, niiden on noudatettava seuraavia ohjeita.

> [!NOTE]
> * Tässä artikkelissa ”kaupallinen logo” viittaa mihin tahansa kaupallisen yrityksen logoon alla olevissa kuvissa esitetyllä tavalla.
> * Microsoftin kaupallista logoa käytetään tässä artikkelissa vain esimerkkinä. Käytä oman Power BI -visualisointisi yhteydessä omaa kaupallista logoasi.

> [!IMPORTANT]
> Kaupalliset logot sallitaan *ainoastaan muokkaustilassa*. Kaupallisia logoja *ei voi* näyttää tarkastelutilassa.

### <a name="commercial-logo-type"></a>Kaupallisten logojen tyypit

Kaupallisia logoja on kolmea tyyppiä:
* **Logo** - Logo koostuu kahdesta toisiinsa yhdistetystä elementistä: kuvakkeesta ja nimestä.

    ![Microsoftin logo](media/guidelines-powerbi-visuals/microsoft-logo.png)

* **Symboli** - Kuva ilman tekstiä.

    ![Microsoftin symboli](media/guidelines-powerbi-visuals/microsoft-symbol.png)

* **Logotyyppi** - Logo, jossa ei ole kuvaketta, pelkkä teksti.

    ![Microsoftin symboli](media/guidelines-powerbi-visuals/microsoft-logotype.png)

### <a name="commercial-logo-color"></a>Kaupallisen logon väri

Kaupallista logoa käytettäessä logon värin on oltava harmaa (hex-väri #C8C8C8). Älä lisää kaupalliseen logoon tehosteita, kuten liukuvärejä.

* **Logo**

    ![Microsoftin symboli](media/guidelines-powerbi-visuals/grey-microsoft-logo.png)

* **Symboli** - Kuva ilman tekstiä.

    ![Microsoftin symboli](media/guidelines-powerbi-visuals/grey-microsoft-symbol.png)

* **Logotyyppi** - Logo, jossa ei ole kuvaketta, pelkkä teksti.

    ![Microsoftin symboli](media/guidelines-powerbi-visuals/grey-microsoft-logotype.png)

> [!TIP]
> * Jos Power BI -visualisointiisi kuuluu kuva, kannattaa harkita valkoisen taustan (10 pikselin reunuksella) lisäämistä logoon.
> * Kannattaa harkita varjon (30 % läpinäkyvä musta) lisäämistä logoon.

### <a name="commercial-logo-size"></a>Kaupallisen logon koko

Power BI -visualisointi vaatii kaksi kaupallista logoa, yhden suuria ruutuja varten ja toisen pienille ruuduille. Sijoita logo täsmälliseen kehikkoon, joka on sijoitettu oikeaan ylä- tai alareunaan ja jossa on 4 kuvapisteen reunukset.

Seuraavassa taulukossa kuvataan Power BI -visualisointeihin liittyvät kokorajoitukset.

|  |Pieni Power BI -visualisointi  |Suuri Power BI -visualisointi  |
|---------|---------|---------|
|*Logon leveys*    |Enintään 240 kuvapistettä         |Enemmän kuin 240 kuvapistettä         |
|*Logon korkeus*     |Enintään 160 kuvapistettä         |Enemmän kuin 160 kuvapistettä         |
|*Täsmällisen kehikon koko*     |40 x 15 kuvapistettä         |101 x 30 kuvapistettä         |
|*Kaupallisen logon esimerkki*     |![Microsoftin symboli](media/guidelines-powerbi-visuals/grey-microsoft-symbol.png)         |![Microsoftin logo](media/guidelines-powerbi-visuals/grey-microsoft-logo.png)         |
|*Täsmällisen kehikon esimerkki*    |![pienen logon esimerkki](media/guidelines-powerbi-visuals/small-logo-box.png)         |![suuren logon esimerkki](media/guidelines-powerbi-visuals/big-logo-box.png)         |
|    |         |         |

### <a name="commercial-logo-behavior"></a>Kaupallisen logon toiminta

Kaupalliset logot sallitaan ainoastaan muokkaustilassa. Kun kaupallista logoa napsautetaan, siihen voivat sisältyä vain seuraavat toiminnallisuudet:

* Kaupallisen logon napsauttaminen ohjaa käyttäjän sivustolle.

* Kaupallisen logon napsauttaminen avaa ponnahdusikkunan, jossa on lisätietoja. Ponnahdusikkuna tulee jakaa kahteen osaan:
    * Markkinointialueeseen, joka voi sisältää kaupallisen logon, visualisoinnin ja markkinaluokituksia.
    * Tietoalueeseen, jossa voi olla tietoja ja linkkejä.    


### <a name="things-to-avoid"></a>Mitä kannattaa välttää

* Kaupallisia logoja ei voi näyttää tarkastelutilassa.

* Animoitu kaupallinen logo voi esittää animaatiota enintään viiden sekunnin ajan.

* Jos Power BI -visualisointi sisältää informatiivisia kuvakkeita (i) lukutilassa, niiden tulee vastata kaupallisen logon väriä, kokoa ja sijaintia, jotka on kuvattu yllä.

* Älä käytä värikästä tai mustaa kaupallista logoa. Kaupallisen logon tulee olla harmaa (hex-väri #C8C8C8).

    ![Luvaton värikäs logo](media/guidelines-powerbi-visuals/no-color-logo.png) ![Luvaton musta logo](media/guidelines-powerbi-visuals/black-logo.png)

* Kaupallinen logo, jossa on tehosteita, kuten liukuvärejä tai vahvoja varjoja.

    ![Luvaton logotyyli](media/guidelines-powerbi-visuals/no-style-logo.png)

## <a name="best-practices"></a>Parhaat käytännöt

Kun julkaiset Power BI -visualisoinnin, ota seuraavat suositukset huomioon, jotta käyttäjät saavat erinomaisen käyttökokemuksen.

### <a name="visual-landing-page"></a>Visualisoinnin aloitussivu

Aloitussivulla kerrot käyttäjille, miten Power BI -visualisointia voi käyttää ja mistä sen käyttöoikeuden voi ostaa. Älä lisää automaattisesti toistettavia videoita. Lisää ainoastaan sellaista sisältöä, joka parantaa käyttökokemusta, esimerkiksi käyttöoikeuden ostamiseen liittyviä ohjeita tai linkkejä ja sovelluskohtaisia ostoja edellyttävien ominaisuuksien käyttöohjeita.

### <a name="license-key-and-token"></a>Käyttöoikeusavain ja -tunnus

Lisää käyttömukavuuden parantamiseksi käyttöoikeusavainta tai -tunnusta koskevat kentät muokkausruudun yläreunaan.

## <a name="faq"></a>Usein kysytyt kysymykset

Saat lisätietoja Power BI -visualisoinneista [lisäostoja sisältävien Power BI -visualisointien usein kysytyistä kysymyksistä](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#visuals-with-additional-purchases).

## <a name="next-steps"></a>Seuraavat vaiheet

Lue ohjeet siihen, miten voit julkaista Power BI -visualisointejasi [Microsoft AppSourcessa](office-store.md) muiden löydettäviksi ja käytettäviksi.