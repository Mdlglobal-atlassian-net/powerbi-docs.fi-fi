---
title: Linkin luominen tiettyyn sijaintiin Power BI ‑mobiilisovelluksissa
description: Opettele luomaan Power BI ‑mobiilisovelluksessa tarkka linkki tiettyyn koontinäkymään, ruutuun tai raporttiin käyttämällä URI-tunnusta.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: mshenhav
ms.openlocfilehash: 4e09b10e38b018f8e5572343b343a243ace3bf81
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906525"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Linkin luominen tiettyyn sijaintiin Power BI ‑mobiilisovelluksissa
Linkkien avulla voit käyttää suoraan Power BI-osat: Raportin, koontinäytön ja ruudun.

On pääasiassa kahta linkkien käyttäminen Power BI Mobile: 

* Avaa Power BI- **sovelluksen ulkopuolella**, ja askelvälit tekevät tietty sisältö (raportin tai koontinäytön tai sovelluksen). Tämä on tavallisesti integrointiskenaario, kun haluat avata Power BI Mobile muiden sovelluksen. 
* Jos haluat **siirtyä** Power BI sisällä. Tämä on yleensä, kun haluat luoda mukautettu siirtyminen Power BI.


## <a name="use-links-from-outside-of-power-bi"></a>Käytä ulkopuolella Power BI-linkit
Kun käytät linkin Power BI-sovelluksen ulkopuolella, haluat varmistaa, että se avautuu sovelluksen, ja jos sovellus ei ole asennettu laitteen ja tarjota käyttäjän asentaa sitä. Olemme luoneet erityiset muotoa voidaan tukea, jota. Tätä muotoa varmistetaan, että laitteen avulla avata linkin sovellukseen, että jos sovellus ei ole asennettu laitteeseen, se tarjoaa käyttäjän Siirry kauppaan, jotta saat sen.

Linkki tulee alkaa merkkijonolla seuraavat  
```html
https://app.powerbi.com/Redirect?[**QUERYPARAMS**]
```

> [!IMPORTANT]
> Jos sisällön isännöidään erityinen datacenter, kuten Goverment, kiina ja niin edelleen. Linkki tulee alkaa merkkijonolla Power BI-osoitteen, kuten `app.powerbigov.us` tai `app.powerbi.cn`.   
>


**KYSELYN parametrit** ovat:
* **toiminto** (pakollinen) = OpenApp / OpenDashboard / OpenTile / AvaaRaportti
* **appId** =, jos haluat avata raportin tai koontinäytön, jotka ovat osa sovellus 
* **groupObjectId** =, jos haluat avata raportin tai koontinäytön, jotka ovat osa työtilan (mutta ei oma työtila)
* **dashboardObjectId** = koontinäytön Objektitunnus (Jos toiminto on OpenDashboard tai OpenTile)
* **reportObjectId** = raportin Objektitunnus (Jos toiminto on AvaaRaportti)
* **tileObjectId** = ruudun Objektitunnus (Jos toiminto on OpenTile)
* **reportPage** =, jos haluat avata tietyn raporttiosan (Jos toiminto on AvaaRaportti)
* **ctId** = kohde Organisaatiotunnus (B2B-skenaario kannalta. Tämä voidaan jättää pois Jos käyttäjän organisaatiolla kuuluu kohteen).

**Esimerkkejä:**

* Avaa Sovelluslinkki 
  ```html
  https://app.powerbi.com/Redirect?action=OpenApp&appId=appidguid&ctid=organizationid
  ```

* Avaa koontinäyttö, joka on osa sovellus 
  ```html
  https://app.powerbi.com/Redirect?action=OpenDashboard&appId=**appidguid**&dashboardObjectId=**dashboardidguid**&ctid=**organizationid**
  ```

* Avaa raportti, joka on osa työtila
  ```html
  https://app.powerbi.com/Redirect?Action=OpenReport&reportObjectId=**reportidguid**&groupObjectId=**groupidguid**&reportPage=**ReportSectionName**
  ```

### <a name="how-to-get-the-right-link-format"></a>Oikea muotoa hankkiminen

#### <a name="links-of-apps-and-items-in-app"></a>Sovellukset ja sovelluksen kohteiden linkit

- **Sovellusten ja -raportteja ja koontinäyttö, jotka ovat osa sovelluksen**, on helpoin tapa saada linkki on sovelluksen työtilasta ja valitse ”Päivitä sovellus”. Tämä avaa ”Julkaise sovellus”-kokemus ja ratkaisutiedosto Access-välilehti **linkit** osiossa. Laajennetaan, että osion ja tulee luettelo sovellus ja kaikki sen sisältö, joka linkittää voidaan käyttää suoraan.

![Power BI julkaista sovelluksen linkkejä ](./media/mobile-apps-links/mobile-link-copy-app-links.png)

#### <a name="links-of-items-not-in-app"></a>Linkit kohteiden ei sovelluksessa 

Raportteja ja koontinäyttöjä, jotka eivät ole osa sovelluksen tarvitset tunnukset poimia kohteen URL-osoite.

Esimerkiksi löytää 36-merkkisen **koontinäytön** objektitunnus, siirry tiettyyn koontinäyttöön Power BI-palvelussa 

```html
https://app.powerbi.com/groups/me/dashboards/**dashboard guid comes here**?ctid=**organization id comes here**`
```

Etsi 36-merkkisen **raportin** objektitunnus, siirry tietyn raportin Power BI-palvelussa.
Tässä on esimerkki raportin ”oman työtilan”

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**`
```
Yllä oleva URL-osoite sisältää myös tietyn raporttisivun **”ReportSection3”** .

Tässä on esimerkki raportin työtilasta (ei oma työtila)

```html
https://app.powerbi.com/groups/**groupid comes here**/reports/**reportid comes here**/ReportSection1?ctid=**organizationid comes here**
```

## <a name="use-links-inside-power-bi"></a>Linkkien sisällä Power BI

Power BI sisällä linkit toimivat mobiilisovelluksissa tarkalleen kuten Power BI-palvelussa.

Jos haluat Lisää linkin raporttiin, joka viittaa toisen Power BI-kohteen, voit kopioida vain kyseisen kohteen URL-Osoitteen selaimen osoiteriviltä. Lue lisää [hyperlinkin lisääminen tekstiruutuun raportissa](https://docs.microsoft.com/power-bi/service-add-hyperlink-to-text-box).

## <a name="use-report-url-with-filter"></a>Käytä raportin URL-osoite, suodatin
Sama kuin Power BI-palvelussa, Power BI Mobile-sovellusten tukevat myös raportin URL-osoite, joka sisältää filter-kysely-parametri. Voit avata raportin Power BI-mobiilisovellus ja suodattaa se tiettyyn tilaan. Esimerkiksi tämän URL-Osoitteen Avaa myynti-raportin ja suodattaa alueen mukaan

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**&filter=Store/Territory eq 'NC'
```

Lue lisää [luoda kyselyn param suodattaa raporttien](https://docs.microsoft.com/power-bi/service-url-filters).

## <a name="next-steps"></a>Seuraavat vaiheet
Palaute auttaa meitä päättämään, mitä toimintoja otamme käyttöön tulevaisuudessa, joten muista äänestää muita ominaisuuksia, jotka haluaisit nähdä Power BI ‑mobiilisovelluksissa. 

* [Power BI -sovellukset mobiililaitteille](mobile-apps-for-mobile-devices.md)
* Seuraa käyttäjää @MSPowerBI Twitterissä
* Liity keskusteluun [Power BI -yhteisössä](http://community.powerbi.com/)
* [Mikä on Power BI?](../../power-bi-overview.md)

