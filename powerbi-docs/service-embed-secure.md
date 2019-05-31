---
title: Raportin upottaminen turvalliseen portaaliin tai sivustoon
description: Power BI-ominaisuuden avulla käyttäjät voivat upottaa helposti ja turvallisesti upottaa raporttien sisäinen WWW-portaalit.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2019
LocalizationGroup: Share your work
ms.openlocfilehash: bf9d7bcdf6ddaf7d0063843a5314233989b2dadd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222250"
---
# <a name="embed-a-report-in-a-secure-portal-or-website"></a>Raportin upottaminen turvalliseen portaaliin tai sivustoon

Uuden **Upota** asetus Power BI-raportit, voit helposti ja turvallisesti upottaa raporttien sisäinen WWW-portaalit. Nämä portaalit voidaan **pilvipohjainen** tai **paikallisesti Isännöidyt**, kuten SharePoint 2019: lle. Upotetut raportit noudattavat kaikki käyttöoikeudet ja tietojen suojauksen kautta [rivitason suojaus (RLS)](service-admin-rls.md). Ne tarjoavat koodia kirjoittamatta upottamiseen, joka hyväksyy URL-osoite tai IFRAME-kehyksen portaalissa. 

**Upota** vaihtoehto tukee [URL-suodattimien](service-url-filters.md) ja URL-osoite asetukset. Sen avulla voit integroida portaalien low-code-tavalla, että vain HTML- ja JavaScript perustiedot.

## <a name="how-to-embed-power-bi-reports-into-portals"></a>Power BI -raporttien **upottaminen** portaaleihin

1. Uusi **Upota**-vaihtoehto näkyy kaikkien Power BI -palvelussa olevien raporttien **Tiedosto**-valikossa.

    ![Avattavan luettelon Turvallinen upotus -vaihtoehto](media/service-embed-secure/secure-embed-drop-down-menu.png)

2. Valitse **Upota** voi avata valintaikkuna, joka sisältää linkin ja iFrame-kehyksen avulla voit upottaa raportin turvallisesti.

    ![Upota-vaihtoehdon valintaikkuna](media/service-embed-secure/secure-embed-code-dialog.png)

3. Käyttäjä avaa raportin URL-osoite suoraan tai yhden upotetun verkkoportaalissa, raportin käyttöoikeudet edellyttää todennusta. Seuraavassa näytössä näkyy, jos käyttäjä on ole kirjautuneena Power BI-istunnot selaimessa. Kun he valitsevat **sisäänkirjautumisen**, uudessa selainikkunassa tai välilehteä voitu avata. Pyydä häntä tarkistetaan ponnahdusikkunoiden esto, jos ne eivät saa kehottaa kirjautumaan.

    ![Kirjaudu sisään tarkastellaksesi tätä raporttia](media/service-embed-secure/secure-embed-sign-in.png)

4. Kun käyttäjä on kirjautunut sisään, raportti avautuu, näkyy tietoja ja sallii sivulla siirtymisen ja Suodata asetus. Vain käyttäjät, joilla on tarkasteluoikeudet näet Power BI-raportissa. Kaikki [rivitason suojaus (RLS)](service-admin-rls.md) sääntöjä sovelletaan myös. Lisäksi käyttäjällä täytyy olla riittävät tuotekäyttöoikeudet: raportin tarkasteluun tarvitaan Power BI Pro -käyttöoikeus, tai raportin on vaihtoehtoisesti oltava sellaisessa työtilassa, joka kuuluu Power BI Premium -kapasiteettiin. Käyttäjän on kirjauduttava sisään aina, kun he avaavat uudessa selainikkunassa. Kuitenkin kun kirjautunut sisään, muut raportit ladata automaattisesti.

    ![Raportin upottaminen](media/service-embed-secure/secure-embed-report.png)

5. Kun iframella, saatat joutua Muokkaa **korkeus** ja **leveys** sen-portaalissa verkkosivun mahtumaan.

    ![Korkeuden ja leveyden määrittäminen](media/service-embed-secure/secure-embed-size.png)

## <a name="granting-report-access"></a>Raportin käyttöoikeuksien myöntäminen

**Upota** vaihtoehto ei salli käyttäjien tarkastella raportin automaattisesti. Näytä käyttöoikeudet määritetään Power BI-palvelussa.

Power BI-palvelussa voit jakaa upotetut raportit käyttäjien, jotka tarvitsevat kanssa. Jos käytät Office 365-ryhmä, voit näyttää käyttäjän sovelluksen työtilan jäsenenä. Jos haluat lisätietoja, katso miten [sovelluksen työtilan Power BI-ja Office 365: n hallinta](service-manage-app-workspace-in-power-bi-and-office-365.md).

## <a name="licensing"></a>Käyttöoikeudet

Voit tarkastella upotettua raporttia käyttäjät tarvitsevat joko Power BI Pro-käyttöoikeuden tai sisällön on oltava on-työtila [Power BI Premium-kapasiteetti (EM tai P-Varastointiyksikköä)](service-admin-premium-purchase.md).

## <a name="customize-your-embed-experience-using-url-settings"></a>Upotustoiminnon mukauttaminen URL-asetusten avulla

Voit mukauttaa käyttämällä liitetty URL-osoite syöttöasetukset käyttökokemuksen. Annettu iFrame, voit päivittää URL-osoitteen **src** asetukset.

| Ominaisuus  | Kuvaus  |  |  |  |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|---|
| pageName  | Voit määrittää **pageName** kyselyn avata raporttisivu määrittää parametrin. Löydät tämän arvon raportin URL-osoitteen lopussa kun tarkastelet raporttia Power BI-palvelussa kuten alla. |  |  |  |
| URL-suodattimet  | Voit käyttää [URL-suodattimien](service-url-filters.md) liitetty URL-osoite saamasi suodattaa Upota sisältöä Power BI-Käyttöliittymän. Näin voit luoda integraatioita HTML- ja JavaScript-perusosaamisella ilman työlästä koodaamista.  |  |  |  |

## <a name="set-which-page-opens-for-an-embedded-report"></a>Määritä, mitä sivu avautuu upotetun raportin 

Voit etsiä **pageName** arvo raportin URL-osoitteen lopussa, kun tarkastelet raporttia Power BI-palvelussa.

1. Avaa raportti Power BI-palvelun selaimessasi ja kopioi osoite palkki URL-osoite.

    ![Raporttiosa](media/service-embed-secure/secure-embed-report-section.png)

2. Liitä **pageName**-asetus URL-osoitteeseen.

    ![pageNamen liittäminen](media/service-embed-secure/secure-embed-append-page-name.png)

## <a name="filter-report-content-using-url-filters"></a>Raportin sisällön suodattaminen URL-suodattimien avulla 

Voit käyttää [URL-suodattimien](service-url-filters.md) antamaan eri raporttinäkymiä. Esimerkiksi alla oleva URL-osoite suodattaa raportin näyttämään energiateollisuutta koskevat tiedot.

**pageName**-asetuksen ja [URL-suodattimien](service-url-filters.md) yhteiskäyttö voi olla tehokasta. Voit luoda käyttötilanteita HTML- ja JavaScript-perustaidoilla.

Tässä on esimerkiksi lisäät HTML-sivulle painiketta:

```html
<button class="textLarge" onclick='show("ReportSection", "Energy");' style="display: inline-block;">Show Energy</button>
```

Kun valittuna, painikkeen kutsuu funktion IFRAME-kehyksen päivitetään päivitetty URL-Osoitteen, joka sisältää energia-alan suodatin.

```javascript
function show(pageName, filterValue)

{

var newUrl = baseUrl + "&pageName=" + pageName;

if(null != filterValue && "" != filterValue)

{

newUrl += "&$filter=Industries/Industry eq '" + filterValue + "'";

}

//Assumes there’s an iFrame on the page with id=”iFrame”

var report = document.getElementById("iFrame")

report.src = newUrl;

}
```

![Suodatin](media/service-embed-secure/secure-embed-filter.png)

Voit luoda mukautetun ja helposti koodattavan käyttökokemuksen lisäämällä erilaisia painikkeita. 

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

* Ulkoisia käyttäjiä ei tueta yritystenvälisen yhteistyön (B2B) Azure-ratkaisuissa.

* Turvallinen upotus toimii Power BI -palvelussa julkaistuissa raporteissa.

* Käyttäjän on kirjauduttava sisään, voit tarkastella raporttia, kun he avaavat uudessa selainikkunassa.

* Jotkin selaimet edellyttää Päivitä sivu, sisäänkirjautumisen jälkeen erityisesti InPrivate- tai Incognito-tilaa käytettäessä.

* Saavuttaa yksittäisen Sign-käyttökokemusta, upotuksen käyttäminen SharePoint Online-asetusta tai luoda mukautettuja integroinnin avulla [käyttäjä omistaa tiedot](developer/embed-sample-for-your-organization.md) upottaminen menetelmää. 

* **Upota**-vaihtoehdon tarjoama automaattisen todentamisen mahdollisuus ei toimi Power BI:n JavaScript-ohjelmointirajapinnan kanssa. Käytä Power BI JavaScript-Ohjelmointirajapinta [käyttäjä omistaa tiedot](developer/embed-sample-for-your-organization.md) upottaminen menetelmää. 

## <a name="next-steps"></a>Seuraavat vaiheet

* [Jakaminen Power BI-työt](service-how-to-collaborate-distribute-dashboards-reports.md)

* [Voit suodattaa raportin käyttämällä kyselymerkkijonon parametreja URL-osoite](service-url-filters.md)

* [Upota raportin verkko-osa SharePoint Onlinessa](service-embed-report-spo.md)

* [Julkaise verkkoon-toiminto Power BI](service-publish-to-web.md)