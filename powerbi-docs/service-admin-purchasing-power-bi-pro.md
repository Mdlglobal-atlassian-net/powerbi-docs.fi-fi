---
title: Power BI Pro -käyttöoikeuksien hankinta ja määritys
description: Lue, miten voit ostaa ja määrittää Power BI Pro -käyttöoikeuksia käyttäjille, jotta he voivat käyttää sisältöä ja tehdä yhteistyötä muiden kanssa Power BI -palvelussa.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/16/2020
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 138173d30b9c37c04047c61dbd04cbd3101696aa
ms.sourcegitcommit: 08f65ea314b547b41b51afef6876e56182190266
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/25/2020
ms.locfileid: "76753187"
---
# <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Power BI Pro -käyttöoikeuksien hankinta ja määritys

>[!IMPORTANT]
>Ovatko käyttäjäsi valmiita päivittämään Power BI Pro -käyttöoikeuteen? Voit määrittää tilisi siirtymällä suoraan [Power BI Pro:n käytön aloittaminen](https://go.microsoft.com/fwlink/?LinkId=2106428&clcid=0x409&cmpid=pbidocs-purchasing-power-bi-pro) -kohtaan.

Power BI Pro on yksilöllinen käyttöoikeus, jonka avulla käyttäjät voivat lukea ja käsitellä raportteja ja koontinäyttöjä, joita muut käyttäjät ovat julkaisseet Power BI -palvelussa. Käyttäjät, joilla on tämä käyttöoikeustyyppi, voivat jakaa sisältöä ja tehdä yhteistyötä muiden Power BI Pro -käyttäjien kanssa. Vain Power BI Pro -käyttäjät voivat julkaista tai jakaa sisältöä muiden käyttäjien kanssa tai käyttää muiden luomaa sisältöä, ellei Power BI Premium -kapasiteetissa isännöidä tätä sisältöä. Lisätietoja on [Power BI:n hinnoittelusivulla](https://powerbi.microsoft.com/pricing/) kohdassa _Power BI:n ominaisuuksien vertailu_.

## <a name="purchase-power-bi-pro-user-licenses"></a>Power BI Pro- käyttöoikeuksien ostaminen

Tässä artikkelissa kerrotaan, miten voit ostaa Power BI Pro -käyttöoikeuksia Microsoft 365 -hallintakeskuksessa. Kun olet ostanut käyttöoikeudet, voit määrittää ne käyttäjille joko Microsoft 365 -hallintakeskuksessa tai Azure-portaalissa.

> [!NOTE]
> 14. tammikuuta 2020 alkaen Power Platform -tuotteiden (Power BI, Power Apps ja Power Automate) itsepalveluostot, tilaukset ja käyttöoikeuksien hallintatoiminnot ovat käytettävissä kaupallisille pilvipalveluasiakkaille Yhdysvalloissa. Lisätietoja siitä, miten voit ottaa itsepalveluostot käyttöön tai poistaa ne käytöstä organisaatiossasi, on artikkelissa [Itsepalveluostojen usein kysytyt kysymykset](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq).

### <a name="prerequisites"></a>Edellytykset

Jotta voit ostaa ja määrittää käyttöoikeuksia Microsoft 365 -hallintakeskuksessa, sinun on oltava **[yleisen järjestelmänvalvojan tai laskutuksen järjestelmänvalvojan](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)** roolissa Microsoft 365:ssä.

Jos haluat määrittää käyttöoikeudet Azure-portaalissa, sinulla on oltava Azure-tilaus, jota Power BI käyttää Azure Active Directory -hauissa.

### <a name="purchase-licenses-in-microsoft-365"></a>Käyttöoikeuksien ostaminen Microsoft 365:ssä

Näiden ohjeiden avulla voit ostaa Power BI Pro -käyttöoikeuksia Microsoft 365 -hallintakeskuksessa:

1. Kirjaudu [Microsoft 365 -hallintakeskukseen](https://admin.microsoft.com).

2. Valitse siirtymisvalikosta **Laskutus** > **Ostopalvelut**.

3. Hae tai vieritä, jotta löydät tilauksen, jonka haluat ostaa. Löydät **Power BI:n** kohdasta **Muut luokat, jotka saattavat kiinnostaa sinua** läheltä sivun alareunaa. Valitse linkki, jos haluat tarkastella organisaatiosi käytettävissä olevia Power BI -tilauksia.

4. Valitse **Power BI Pro**.

5. Valitse **Ostopalvelut**-sivulta **Osta**.

6. Valitse **Maksa kuukausittain** tai **Maksa koko vuosi** haluamasi maksutavan mukaan.

7. Syötä käyttöoikeusmäärä, jonka haluat ostaa, kohdassa **Kuinka monta käyttäjää haluat?** . Valitse sitten **Maksa nyt** ostotapahtuman viimeistelemiseksi.

8. Vahvista ostoksesi siirtymällä kohtaan **Laskutus** > **Tuotteet ja Palvelut** ja etsi **Power BI Pro**.

9. Jos haluat lisätä käyttöoikeuksia myöhemmin, etsi **Power BI Pro** **Tuotteet ja palvelut** -sivulta ja valitse sitten **Lisää tai poista käyttöoikeuksia**.

## <a name="assign-licenses-in-the-microsoft-365-admin-center"></a>Käyttöoikeuksien määrittäminen Microsoft 365 -hallintakeskuksessa

Lisätietoja käyttöoikeuksien määrittämisestä Microsoft 365 ‑hallintakeskuksessa saat kohdasta [Käyttöoikeuksien määrittäminen käyttäjille](/office365/admin/manage/assign-licenses-to-users).

Vieraskäyttäjien osalta katso [Käyttöoikeuksien määrittäminen käyttäjille käyttöoikeussivulta](/office365/admin/manage/assign-licenses-to-users#assign-licenses-to-users-on-the-licenses-page). Ennen kuin määrität Pro-käyttöoikeuksia vieraskäyttäjille, ota yhteyttä Microsoft-tiliedustajaan varmistaaksesi, että noudatat Microsoft-sopimuksesi ehtoja.

## <a name="assign-licenses-in-the-azure-portal"></a>Käyttöoikeuksien määrittäminen Azure-portaalissa

Voit määrittää Power BI Pro -käyttöoikeuksia yksittäisille käyttäjätileille seuraavien ohjeiden mukaisesti:

1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com/).

2. Etsi **Azure Active Directory** ja valitse se.

3. Valitse **Hallitse**-kohdasta **Azure Active Directory** -resurssivalikosta **Käyttöoikeudet**.

4. Valitse **Kaikki tuotteet** **Käyttöoikeudet – yleiskatsaus** -resurssivalikosta ja valitse sitten **Power BI Pro**. Esiin tulee luettelo käyttäjistä, joilla on käyttöoikeus.

5. Valitse komentopalkista **+ Määritä**. Valitse **Määritä käyttöoikeus** -sivulla ensin käyttäjä ja valitse sitten **Määritysasetukset** Power BI Pro -käyttöoikeuden ottamiseksi käyttöön valitulle käyttäjätilille.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun olet määrittänyt käyttöoikeudet, lue lisää Power BI Prosta.

[Power BI -käyttöoikeudet organisaatiossasi](service-admin-licensing-organization.md)

[Kirjautuneena olevien Power BI -käyttäjien etsiminen](service-admin-access-usage.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
