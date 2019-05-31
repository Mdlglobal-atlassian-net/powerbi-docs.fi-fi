---
title: Power BI -käyttöoikeudet
description: Power BI -käyttöoikeudet
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 10/01/2018
ms.openlocfilehash: 8a48ec007f2d8c9c07de5cc0d51049e3dbf19662
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61269335"
---
# <a name="power-bi-permissions"></a>Power BI -käyttöoikeudet

## <a name="permission-scopes"></a>Käyttöoikeuden vaikutusalueet

Power BI -käyttöoikeudet antavat sovellukselle mahdollisuuden suorittaa tiettyjä toimenpiteitä käyttäjän puolesta. Käyttäjän on hyväksyttävä kaikki käyttöoikeudet, jotta ne ovat voimassa.

| Näyttönimi | Kuvaus | Vaikutusalueen arvo |
| --- | --- | --- |
| Kaikkien tietojoukkojen lukuoikeus |Sovelluksella on lukuoikeus kaikkiin kirjautuneen käyttäjän tietojoukkoihin sekä tietojoukkoihin, joihin käyttäjällä on käyttöoikeus. |Dataset.Read.All |
| Kaikkien tietojoukkojen luku- ja kirjoitusoikeus |Sovelluksella on luku- ja kirjoitusoikeus kaikkiin kirjautuneen käyttäjän tietojoukkoihin sekä tietojoukkoihin, joihin käyttäjällä on käyttöoikeus. |Dataset.ReadWrite.All |
| Tietojen lisäämisoikeus käyttäjän tietojoukkoon |Antaa sovellukselle oikeuden lisätä tai poistaa käyttäjän tietojoukon rivejä. Tämä käyttöoikeus ei anna sovellukselle pääsyä käyttäjän tietoihin. |Data.Alter_Any |
| Sisällön luontioikeus |Sovellus voi luoda automaattisesti sisältöä ja tietojoukkoja käyttäjälle. |Content.Create |
| Käyttäjän ryhmien lukuoikeus |Sovelluksella on lukuoikeus kaikkiin ryhmiin, joihin kirjautunut käyttäjä kuuluu. |Group.Read |
| Kaikkien ryhmien lukuoikeus |Sovelluksella on lukuoikeus kaikkiin ryhmiin, joihin kirjautunut käyttäjä kuuluu. |Group.Read.All |
| Kaikkien ryhmien luku- ja kirjoitusoikeus |Sovelluksella on luku- ja kirjoitusoikeus kaikkiin kirjautuneen käyttäjän ryhmiin sekä ryhmiin, joihin käyttäjällä on käyttöoikeus. |Group.ReadWrite.All |
| Kaikkien raporttinäkymien lukuoikeus |Sovelluksella on lukuoikeus kaikkiin kirjautuneen käyttäjän raporttinäkymin sekä raporttinäkymiin, joihin käyttäjällä on käyttöoikeus. |Dashboard.Read.All |
| Kaikkien raporttien lukuoikeus |Sovelluksella on lukuoikeus kaikkiin kirjautuneen käyttäjän raportteihin sekä raportteihin, joihin käyttäjällä on käyttöoikeus. Sovellus voi myös nähdä raporttien sisältämät tiedot sekä niiden rakenteen. |Report.Read.All |
| Kaikkien raporttien luku- ja kirjoitusoikeus |Sovelluksella on luku- ja kirjoitusoikeus kaikkiin kirjautuneen käyttäjän raportteihin sekä raportteihin, joihin käyttäjällä on käyttöoikeus. Tämä ei tarjoa oikeuksia luoda uutta raporttia. |Report.ReadWrite.All |
| Kaikkien kapasiteettien luku- ja kirjoitusoikeus |Sovelluksella on luku- ja kirjoitusoikeus kaikkiin kirjautuneen käyttäjän kapasiteetteihin sekä kapasiteetteihin, joihin käyttäjällä on käyttöoikeus. Tämä ei anna oikeuksia luoda uutta kapasiteettia. |Capacities.ReadWrite.All |
| Kaikkien kapasiteettien lukuoikeus |Sovelluksella on luku- ja kirjoitusoikeus kaikkiin kirjautuneen käyttäjän kapasiteetteihin sekä kapasiteetteihin, joihin käyttäjällä on käyttöoikeus. Tämä ei anna oikeuksia luoda uutta kapasiteettia. |Capacities.Read.All |
| Kaiken vuokraajan sisällön luku- ja kirjoitusoikeus |Sovelluksella on luku- ja kirjoitusoikeus kaikkiin Power BI:n artefakteihin, kuten ryhmiin, raportteihin, raporttinäkymiin ja tietojoukkoihin. Edellyttää, että kirjautunut käyttäjä on Power BI -palvelun järjestelmänvalvoja. |Tenant.ReadWrite.All |
| Kaiken vuokraajan sisällön lukuoikeus |Sovellus voi tarkastella kaikkia artefakteja, kuten ryhmiä, raportteja, koontinäyttöjä ja tietojoukkoja Power BI:ssä. Edellyttää, että kirjautunut käyttäjä on Power BI -palvelun järjestelmänvalvoja. |Tenant.Read.All |

Sovellus voi pyytää käyttöoikeuksia, kun se yrittää ensimmäistä kertaa kirjautua sisään käyttäjän sivulle, välittämällä pyydetyt käyttöoikeudet kutsun vaikutusalueparametrissa. Jos käyttöoikeudet myönnetään, sovellukselle palautetaan käyttöoikeustietue, jota voidaan käyttää tulevissa ohjelmointirajapintojen kutsuissa. Käyttöoikeus on vain tietyn sovelluksen käytössä.

> [!NOTE]
> Power BI -ohjelmointirajapinnat viittaavat sovelluksen työtiloihin edelleen ryhminä. Mitkä tahansa viittaukset ryhmiin tarkoittavat sitä, että työskentelet sovelluksen työtilojen parissa.

## <a name="requesting-permissions"></a>Käyttöoikeuksien pyytäminen

Voit kutsua API:a suorittamaan todennuksen käyttäjätunnuksella ja salasanalla, mutta toimenpiteiden suorittaminen toisen käyttäjän puolesta edellyttää käyttöoikeuksien pyytämistä ja sitä, että käyttäjä hyväksyy ja sen jälkeen lähettää käyttöoikeustietueen kaikkien tulevien kutsujen yhteydessä. Tässä noudatamme [OAuth 2.0](http://oauth.net/2/) -vakioprotokollaa. Toteutus voi vaihdella, mutta Power BI:n OAuth-työnkulku sisältää seuraavat osat:

* **Kirjautumiskäyttöliittymä** – tämä on käyttöliittymä, jonka kehittäjä voi kutsua käyttöoikeuksien pyytämistä varten. Se edellyttää käyttäjältä sisäänkirjautumista, mikäli hän ei vielä ole tehnyt niin. Käyttäjän on myös hyväksyttävä käyttöoikeudet, joita sovellus pyytää. Kirjautumisikkuna antaa takaisin joko käyttökoodin tai virhesanoman koskien annettua uudelleenohjauksen URL-osoitetta.
  * Power BI:n pitäisi toimittaa uudelleenohjauksen vakio-URL-osoite käytettäväksi alkuperäisissä sovelluksissa.
* **Varmennuskoodi** – varmennuskoodit palautetaan verkkosovelluksille kirjautumisen jälkeen uudelleenohjauksen URL-osoitteen URL-parametrien kautta. Koska ne ovat parametreja, niihin liittyy joitakin tietoturvariskejä. Verkkosovellusten on vaihdettava varmennuskoodi valtuutustunnukseen
* **Valtuutustunnus** – käytetään API-kutsujen varmentamiseen toisen käyttäjän puolesta. Ne on rajoitettu tiettyyn sovellukseen. Tunnuksilla on elinkaari, ja kun ne vanhenevat, ne on päivitettävä.
* **Päivitä tunnus** – kun tunnukset vanhenevat, ne päivitetään.

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)