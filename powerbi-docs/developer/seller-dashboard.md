---
title: Power BI -visualisoinnin lähettäminen AppSourceen myyjän koontinäytön kautta
description: Power BI -visualisoinnin lähettäminen AppSourceen myyjän koontinäytön kautta
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 12/03/2019
ms.openlocfilehash: 73a6a3d16ae2515af41a3232a37579e18876f38b
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/04/2020
ms.locfileid: "75223677"
---
# <a name="submit-a-power-bi-visual-to-appsource-using-seller-dashboard"></a>Power BI -visualisoinnin lähettäminen AppSourceen myyjän koontinäytön kautta

Sinun täytyy lähettää **pbiviz**- ja **pbix**-tiedoston sisältävä sähköposti Power BI -tiimille ennen AppSourceen lähettämistä. Tällä tavoin Power BI -tiimi voi ladata tiedostot julkiseen jakopalvelimeen. Muussa tapauksessa kauppa ei voi hakea tiedostoja. Sinun täytyy lähettää tiedostot, kun lähetät uuden Power BI -visualisoinnin, päivität aiemmin julkaistua Power BI -visualisointia tai teet korjauksia hylätyn lähetyksen johdosta.

>[!NOTE]
>[Myyjän koontinäytöstä](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store) ollaan luopumassa. Se korvataan [kumppanikeskuksella](https://docs.microsoft.com/partner-center/). Käytä myyjän koontinäyttöä vain, jos olet jo osittain lähettänyt Power BI -visualisoinnin. Jos olet lähettämässä uutta Power BI -visualisointia AppSourceen, käytä [kumppanikeskusmenetelmää](office-store.md#submitting-to-appsource).

### <a name="seller-dashboard-submission-process"></a>Myyjän koontinäytön lähettämisprosessi

[Office-kehittäjäkeskukseen](https://dev.office.com/) kirjautumiseen vaaditaan kelvollinen Office-kehittäjätili. Office-kehittäjätilin on oltava Microsoft-tili Live ID, esimerkiksi hotmail.com tai outlook.com.

1. Siirry [kehittäjäkeskukseen](https://sellerdashboard.microsoft.com/Application/Summary).

2. Valitse **Lisää uusi sovellus**.

    ![Lisää sovellus](media/office-store/powerbi-custom-visual-add-an-app.png)

3. Valitse **Power BI:n mukautettu visualisointi** > **Seuraava**.

4. Valitse **Sovelluspaketti** -kohdan alta **+** ja valitse sitten Avaa tiedosto -valintaikkunassa XML-sovelluspakettitiedosto, jonka sait Power BI -tiimiltä.

    ![Sovelluspaketti](media/office-store/powerbi-custom-visual-apppackage.png)

5. Sinun pitäisi saada hyväksyntä siitä, että kyseessä on kelvollinen Power BI -sovelluspaketti.

    ![Kokoonpanotiedot hyväksyttiin](media/office-store/powerbi-custom-visual-manifest-approved.png)

6. Täytä **yleiset tiedot**.

   * *Lähetyksen otsikko:* Lähetyksesi nimi kehittäjäkeskuksessa.
   * *Versio:* Versionumero määritetään automaattisesti apuohjelmasi sovelluspaketin perusteella.
   * *Julkaisupäivämäärä (UTC):* Valitse päivämäärä, jolloin sovelluksesi julkaistaan kaupassa. Jos valitset tulevaisuudessa olevan päivämäärän, sovelluksesi on saatavilla kaupasta vasta valittuna päivänä.
   * *Luokka:* Ensimmäiseksi luokaksi määritetään ”Tietojen visualisointi ja liiketoimintatiedot”. Tämä merkintä lisätään kaikille Power BI -visualisoinneille. Voit määrittää kaksi muutakin luokkaa, joiden avulla käyttäjät voivat helposti etsiä visualisointiasi.
   * *Testaushuomautukset:* voit halutessasi antaa tässä ohjeita Microsoftin testaajille.
   * *Sovelluksesi kutsuu, tukee, sisältää tai käyttää salausta*: jätä tämä kohta valitsematta.
   * *Tarjoa tämä apuohjelma käytettäväksi iPadin Office-apuohjelmaluettelossa*: jätä tämä kohta valitsematta.
7. Lataa visualisointisi logo valitsemalla **sovelluksen logon** kohdasta **+** . Valitse sitten kuvatiedosto Avaa tiedosto -valintaikkunassa. Kuvaketiedoston täytyy olla .png-, .jpg-, .jpeg- tai .gif-tiedosto. Sen on oltava tarkalleen 300 × 300 kuvapistettä (leveys × korkeus). Suurin sallittu tiedostokoko on 512 kt.

    ![Sovelluksen logo](media/office-store/powerbi-custom-visual-app-logo.png)

8. Täytä **tukiasiakirjojen** tiedot.

   * Tukiasiakirjan linkki
   * Tietosuoja-asiakirjan linkki
   * Videolinkki
   * Käyttöoikeussopimus (EULA)

       Sinun täytyy ladata palveluun käyttöoikeussopimus. Se voi olla oma käyttöoikeussopimuksesi tai Office-kaupan oletuskäyttöoikeussopimus Power BI -visualisoinneille. Jos haluat käyttää oletuskäyttöoikeussopimusta, liitä seuraava URL-osoite myyjän koontinäytön ”Käyttöoikeussopimus”-tiedoston latauksen valintaikkunaan: [https://visuals.azureedge.net/app-store/Power BI - Default Custom Visual EULA.pdf](https://visuals.azureedge.net/app-store/Power%20BI%20-%20Default%20Custom%20Visual%20EULA.pdf).

9. Jatka **Tiedot**-sivulle valitsemalla **Seuraava**.

10. Valitse **Kieli** ja valitse sitten kieli luettelosta.

    ![Kieli](media/office-store/powerbi-custom-visual-language.png)

11. Täytä Kuvaus-kohdan tiedot.

    * *Sovelluksen nimi (tällä kielellä):* Kirjoita sovelluksen nimi, joka näytetään kaupassa.
    * *Lyhyt kuvaus:* Kirjoita sovelluksen lyhyt kuvaus, joka näytetään kaupassa (enintään 100 merkkiä). Tämä kuvaus näytetään ylimmän tason sivuilla logon kanssa. Voit käyttää pbiviz-paketin kuvausta.
    * *Pitkä kuvaus:* Kirjoita sovelluksen tarkempi kuvaus, jonka asiakkaat näkevät sovelluksen tietosivulla. Jos haluat antaa yhteisön parantaa visualisointiasi tekemällä siitä avoimen lähdekoodin visualisoinnin, anna tässä linkki julkiseen säilöön (esimerkiksi GitHubiin).

12. Lataa ainakin yksi näyttökuva. Se voi olla .png-, .jpg-, .jpeg- tai .gif-muodossa. Sen on oltava tarkalleen 1 366 × 768 kuvapistettä (leveys × korkeus). Suurin sallittu tiedostokoko on 1 024 kt. *Käyttäjämäärien kasvattamiseksi suosittelemme, että lisäät näyttökuviin tekstikuplia, jotka tuovat esiin tärkeimpien toimintojen etuja.*

12. Jos haluat lisätä muita kieliä, valitse **Lisää kieli** ja toista vaiheet 10 sekä 11. Kun lisäät muitakin kieliä, käyttäjät voivat tarkastella visualisoinnin tietoja omalla kielellään. Kielet, joita ei luetella, vaihdetaan oletusarvoisesti ensimmäiseksi valituksi kieleksi.

13. Kun olet lisännyt haluamasi kielet, jatka **käytön estämisen** sivulla valitsemalla **Seuraava**.

14. Jos haluat estää tiettyjen maiden tai alueiden käyttäjiä käyttämästä tai estämästä sovellustasi, valitse ruutu ja valitse haluamasi maat tai alueet luettelosta.

15. Jatka **hinnoittelusivulle** valitsemalla **Seuraava**.

16. Tällä hetkellä tuemme vain *maksuttomia* visualisointeja. Myöskään lisäostoja visualisoinneissa (sovelluskohtaiset ostot) ei sallita. Valitse **Tämä sovellus on maksuton**.

    > [!NOTE]
    > Jos valitset minkä tahansa muun vaihtoehdon kuin maksuttomuuden tai jos lähetetyssä visualisoinnissa on sovelluskohtaisia ostoja, lähetyksesi hylätään.

17. Voit nyt valita **Tallenna luonnoksena** ja lähettää myöhemmin tai lähettää oman visualisointisi Office-kauppaan valitsemalla **Lähetä hyväksyttäväksi**.

## <a name="seller-dashboard-certification-submission-process"></a>Myyjän koontinäytön sertifioinnin lähettämisprosessi

Noudata tämän osion ohjeita, kun lähetät Power BI -visualisoinnin sertifioitavaksi myyjän koontinäyttöön. Käytä tätä menetelmää, jos lähetit aiemmin Power BI -visualisoinnin AppSourceen myyjän koontinäytön kautta.

1. Lähetä sähköpostia Power BI -visualisointien tukitiimille (pbicvsupport@microsoft.com). Sisällytä viestiin seuraavat tiedot:
    * Otsikko: Visualisoinnin sertifiointipyyntö
    * Linkki GitHub-säilöön, joka isännöi ihmisen luettavaa lähdekoodia
    * [Vaatimuksien noudattaminen](power-bi-custom-visuals-certified.md#certification-requirements)
    * Kooditarkastuksen läpäiseminen

2. Microsoftin Power BI ‑visualisointien tiimi ilmoittaa, kun Power BI ‑visualisointi on joko sertifioitu ja lisätty [sertifioitujen Power BI ‑visualisointien luetteloon](power-bi-custom-visuals-certified.md#certified-power-bi-visuals) tai hylätty, jolloin mukana toimitetaan raportti korjattavista ongelmista. On kehittäjän vastuulla pitää yllä avointa viestiyhteyttä Microsoftin kanssa ja päivittää tarvittaessa omat sertifioidut visualisointinsa.

## <a name="tracking-submission-status-and-usage"></a>Lähetyksen tilan ja käytön seuraaminen

Voit tarkistaa [vahvistuskäytännöt](https://dev.office.com/officestore/docs/validation-policies#13-power-bi-custom-visuals).

Kun olet lähettänyt visualisoinnin, voit seurata sen tilaa [sovelluskoontinäytössä](https://sellerdashboard.microsoft.com/Application/Summary/).

## <a name="certify-your-visual"></a>Visualisoinnin sertifioiminen

Kun visualisointisi on luotu, voit halutessasi hankkia sille [sertifioinnin](../developer/power-bi-custom-visuals-certified.md).

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI:n mukautetun visualisoinnin kehittäminen](visuals/custom-visual-develop-tutorial.md)  
[Visualisoinnit Power BI:ssä](../visuals/power-bi-report-visualizations.md)  
[Mukautetut visualisoinnit Power BI:ssä](../developer/power-bi-custom-visuals.md)  
[Sertifioinnin hankkiminen Power BI -visualisoinnille](../developer/power-bi-custom-visuals-certified.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
