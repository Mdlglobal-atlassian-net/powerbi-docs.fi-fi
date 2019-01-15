---
title: Raportin upottaminen turvalliseen portaaliin tai sivustoon
description: Power BI:n turvallisen upotusominaisuuden avulla voit antaa käyttäjille mahdollisuuden upottaa raportteja sisäisiin verkkoportaaleihin helposti ja turvallisesti.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/08/2019
LocalizationGroup: Share your work
ms.openlocfilehash: b816b504d3eed3aa91eb25c0bb3c6189d3075d1f
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54285825"
---
# <a name="embed-a-report-in-a-secure-portal-or-website"></a>Raportin upottaminen turvalliseen portaaliin tai sivustoon

Power BI:n uusi raporttien turvallinen **Upota**-asetus mahdollistaa sen, että käyttäjät voivat helposti ja turvallisesti upottaa raportteja sisäisiin verkkoportaaleihin (niin **pilvipohjaisiin** kuin **isännöityihin ja paikallisiinkin**), esimerkiksi SharePoint 2019:een. Uudella menetelmällä upotettuihin raportteihin sovelletaan kaikkia kohteille asetettuja käyttöoikeuksia ja tietosuojamenetelmiä RLS:n (row-level security, rivitason suojaus) avulla. Ominaisuus on suunniteltu mahdollistamaan upottaminen ilman koodausta kaikkiin portaaleihin, jotka hyväksyvät upottamisen URL-osoitteen tai iFramen avulla.

**Upota**-asetus tukee myös [URL-suodattimia](service-url-filters.md) ja URL-asetuksia. **Upota**-asetuksen avulla voit integroida sisältöä portaaleihin ilman työlästä koodausta: perustiedot HTML:stä ja JavaScriptista riittävät.

## <a name="how-to-embed-power-bi-reports-into-portals"></a>Power BI -raporttien **upottaminen** portaaleihin

1. Uusi **Upota**-vaihtoehto näkyy kaikkien Power BI -palvelussa olevien raporttien **Tiedosto**-valikossa.

    ![Avattavan luettelon Turvallinen upotus -vaihtoehto](media/service-embed-secure/secure-embed-drop-down-menu.png)

2. Valitse Upota-vaihtoehto. Näkyviin tulee valintaikkuna, jossa on linkki sekä iFrame, jota käytetään raportin turvalliseen upottamiseen.

    ![Upota-vaihtoehdon valintaikkuna](media/service-embed-secure/secure-embed-code-dialog.png)

3. Kun olet upottanut URL-osoitteen verkkoportaaliin tai jos avaat URL-osoitteen suoraan, käyttäjä todennetaan, ennen kuin hänelle annetaan raportin käyttöoikeus. Alla olevassa kuvassa käyttäjä ei ole selainistunnossa kirjautuneena Power BI:hin. Kun käyttäjä napsauttaa **Kirjaudu sisään** -vaihtoehtoa, järjestelmä saattaa avata uuden selainikkunan tai -välilehden. Jos et saa sisäänkirjautumiskehotetta, tarkista, onko ponnahdusikkunat estetty.

    ![Kirjaudu sisään tarkastellaksesi tätä raporttia](media/service-embed-secure/secure-embed-sign-in.png)

4. Kun käyttäjä on kirjautunut sisään, raportti aukeaa ja sen tiedot tulevat näkyviin. Käyttäjät voivat nyt siirtyä sivujen välillä ja määrittää suodattimia. Raportti näytetään vain niille käyttäjille, joilla on raportin tarkasteluoikeus Power BI:ssä. Myös kaikkia RLS-sääntöjä sovelletaan. Lisäksi käyttäjällä täytyy olla riittävät tuotekäyttöoikeudet: raportin tarkasteluun tarvitaan Power BI Pro -käyttöoikeus, tai raportin on vaihtoehtoisesti oltava sellaisessa työtilassa, joka kuuluu Power BI Premium -kapasiteettiin. Käyttäjän on kirjauduttava uudelleen sisään aina, kun hän avaa uuden selainikkunan. Kirjautumisen jälkeen muut raportit ladataan automaattisesti.

    ![Raportin upottaminen](media/service-embed-secure/secure-embed-report.png)

5. Jos käytät iFrame-vaihtoehtoa, portaalin verkkosivulle sopiva korkeus ja leveys kannattaa määrittää muokkaamalla annettua HTML-koodia.

    ![Korkeuden ja leveyden määrittäminen](media/service-embed-secure/secure-embed-size.png)

## <a name="granting-access-to-reports"></a>Raporttien käyttöoikeuksien myöntäminen

Upota-asetus ei automaattisesti salli käyttäjien tarkastella raporttia. Raportin katseluoikeudet määritetään Power BI -palvelussa.

Jos haluat tarjota raportin tarkasteltavaksi Power BI -palvelussa, voit jakaa raportin käyttäjille, jotka tarvitsevat upotetun raportin käyttöoikeuden. Jos käytät Office 365 -ryhmää, voit lisätä käyttäjän Power BI -palvelun sovellustyötilan jäseneksi. Jos haluat lisätietoja, katso, miten voit [hallita sovelluksen työtilaa](service-manage-app-workspace-in-power-bi-and-office-365.md).

## <a name="licensing"></a>Käyttöoikeudet

Käyttäjät tarvitsevat upotetun raportin tarkasteluun Power BI Pro -käyttöoikeuden, tai sisällön on vaihtoehtoisesti oltava työtilassa, joka kuuluu [Power BI Premium -kapasiteettiin (EM- tai P-varastointiyksikkö)](service-admin-premium-purchase.md).

## <a name="customize-your-embed-experience-using-url-settings"></a>Upotustoiminnon mukauttaminen URL-asetusten avulla

Upotuksen URL-osoite tukee erilaisia syöteasetuksia, jotka auttavat käyttäjäkokemuksen mukauttamisessa. Jos käytät annettua iFramea, varmista, että päivität URL-osoitteen iFramen src-asetuksissa.

| Ominaisuus  | Kuvaus  |  |  |  |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|---|
| pageName  | **pageName**-kyselymerkkijonoparametrin avulla voit määrittää, minkä raportin sivuista haluat avata. **pageName**-arvo vastaa raportin URL-osoitteen loppua, kun raporttia tarkastellaan Power BI -palvelussa, kuten alla. |  |  |  |
| URL-suodattimet  | Voit käyttää Power BI:n käyttöliittymästä saamassasi upotus-URL-osoitteessa [URL-suodattimia](service-url-filters.md) upotetun sisällön suodattamiseen. Näin voit luoda integraatioita HTML- ja JavaScript-perusosaamisella ilman työlästä koodaamista.  |  |  |  |

## <a name="set-which-page-opens-when-the-report-is-embedded"></a>Upotetun raportin aloitussivun määrittäminen

*pageName*-asetuksessa annettu arvo vastaa raportin URL-osoitteen loppua, kun raporttia tarkastellaan Power BI -palvelussa.

1. Avaa raportti Power BI -palvelusta selaimeen ja kopioi URL-osoite osoitepalkista.

    ![Raporttiosa](media/service-embed-secure/secure-embed-report-section.png)

2. Liitä *pageName*-asetus URL-osoitteeseen.

    ![pageNamen liittäminen](media/service-embed-secure/secure-embed-append-page-name.png)

## <a name="filter-report-content-using-url-filters"></a>Raportin sisällön suodattaminen URL-suodattimien avulla

Jos haluat lisäominaisuuksia, voit luoda raportille lisää käyttötilanteita [URL-suodattimien](service-url-filters.md) avulla. Esimerkiksi alla oleva URL-osoite suodattaa raportin näyttämään energiateollisuutta koskevat tiedot.

**pageName**-asetuksen ja [URL-suodattimien](service-url-filters.md) yhteiskäyttö voi olla tehokasta. Voit luoda käyttötilanteita HTML- ja JavaScript-perustaidoilla.

Voit esimerkiksi lisätä HTML-sivuun painikkeen näin:

```html
<button class="textLarge" onclick='show("ReportSection", "Energy");' style="display: inline-block;">Show Energy</button>
```

Painettaessa painike kutsuu funktion, joka päivittää iFramen päivitetyllä URL-osoitteella, joka sisältää suodattimen energiateollisuuden tiedoille.

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

* Käyttäjän on kirjauduttava sisään raportin tarkastelua varten aina, kun hän avaa uuden selainikkunan.

* Osa selaimista edellyttää sivun päivittämistä kirjautumisen jälkeen, erityisesti käytettäessä InPrivate- tai Incognito-tilaa.

* Voit luoda kertakirjautumisella toimivan käyttökokemuksen Upota SharePoint Onlineen -vaihtoehdon avulla tai luomalla mukautetun integraation [käyttäjä omistaa tiedot](developer/embed-sample-for-your-organization.md) -menetelmällä. Lue lisää [käyttäjän omistamista tiedoista](developer/embed-sample-for-your-organization.md).

* **Upota**-vaihtoehdon tarjoama automaattisen todentamisen mahdollisuus ei toimi Power BI:n JavaScript-ohjelmointirajapinnan kanssa. Jos käytät Power BI:n JavaScript-ohjelmointirajapintaa, käytä upotuksessa [käyttäjä omistaa tiedot](developer/embed-sample-for-your-organization.md) -menetelmää. Lue lisää [käyttäjän omistamista tiedoista](developer/embed-sample-for-your-organization.md).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Töiden jakamistavat](service-how-to-collaborate-distribute-dashboards-reports.md)

* [URL-suodattimet](service-url-filters.md)

* [SharePoint Online -raportin verkko-osa](service-embed-report-spo.md)

* [Verkkoon julkaiseminen](service-publish-to-web.md)