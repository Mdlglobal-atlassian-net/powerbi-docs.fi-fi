---
title: Power BI Pro -käyttöoikeuksien hankinta ja määritys
description: Lue, miten voit ostaa ja määrittää Power BI Pro -käyttöoikeuksia, jotta käyttäjät voivat käyttää sisältöä ja tehdä yhteistyötä työtovereiden kanssa Power BI -palvelussa.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: quickstart
ms.date: 12/18/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 01eb30857b0b76f96e7e18115d92fb1d68dbef0c
ms.sourcegitcommit: 02b05932a119527f255e1eacc745a257044e392f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/19/2019
ms.locfileid: "75223839"
---
# <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Power BI Pro -käyttöoikeuksien hankinta ja määritys

Power BI Pro on yksilöllinen käyttöoikeus, jonka avulla käyttäjät voivat lukea ja käsitellä raportteja sekä koontinäyttöjä, joita muut käyttäjät ovat julkaisseet Power BI -palvelussa, sekä jakaa sisältöä ja tehdä yhteistyötä muiden Power BI Pro -käyttäjien kanssa. Vain käyttäjät, joilla on Power BI Pro -käyttöoikeus, voivat julkaista tai jakaa sisältöä muiden käyttäjien kanssa tai käyttää muiden käyttäjien luomaa sisältöä, ellei kyseistä sisältöä isännöidä Power BI Premium -ominaisuudessa. Lisätietoja on [Power BI:n hinnoittelusivulla](https://powerbi.microsoft.com/pricing/) kohdassa _Power BI:n ominaisuuksien vertailu_.

## <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Power BI Pro -käyttöoikeuksien hankinta ja määritys

Tässä artikkelissa kerrotaan, miten voit ostaa Power BI Pro -käyttöoikeuksia Microsoft 365 -hallintakeskuksesta, ja esitellään kaksi vaihtoehtoa, joiden avulla järjestelmänvalvojat voivat määrittää käyttöoikeudet yksittäiselle käyttäjälle: Microsoft 365 -hallintakeskus ja Azure-portaali (valitse yksi vaihtoehto).

### <a name="prerequisites"></a>Edellytykset

Jotta voit ostaa ja määrittää käyttöoikeuksia Microsoft 365 -hallintakeskuksessa, sinun on oltava **[yleisen järjestelmänvalvojan tai laskutuksen järjestelmänvalvojan](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)** roolissa Microsoft 365:ssä.

Jos haluat määrittää käyttöoikeudet Azure-portaalissa, sinulla on oltava Azure-tilaus, jota Power BI käyttää Azure Active Directory -hauissa.

### <a name="purchase-licenses-in-microsoft-365"></a>Käyttöoikeuksien ostaminen Microsoft 365:ssä

Näiden ohjeiden avulla voit ostaa Power BI Pro -käyttöoikeuksia Microsoft 365 -hallintakeskuksessa:

1. Avaa [Microsoft 365 -hallintakeskus](https://portal.office.com/adminportal/home#/homepage).

2. Valitse siirtymisruudussa **Laskutus** ja sitten **Tilaukset**.

3. Valitse **Tilaukset**-sivun oikeassa yläkulmassa **Lisää tilauksia**.

4. Etsi haluamasi tilaustarjous:

    - Valitse **Enterprise Suitesta** **Office 365 Enterprise E5**.

    - Valitse **Muut palvelupaketit** -kohdasta **Power BI Pro**.

5. Vie hiiren kohdistin kolmen pisteen ( **. . .** ) päälle haluamassasi tilauksessa ja valitse **Osta nyt**.

6. Valitse **Maksa kuukausittain** tai **Maksa koko vuosi** haluamasi laskutustavan mukaan.

7. Anna haluamasi käyttöoikeusmäärä kohdassa **Kuinka monta käyttäjää haluat?** , valitse **Siirry maksamaan** ja viimeistele ostos.

8. Varmista, että hankittu tilaus näkyy nyt **Tilaukset**-sivulla.

9. Jos haluat lisätä enemmän käyttöoikeuksia alkuperäisen ostoksen jälkeen, valitse **Tilaukset**-sivulta **Power BI Pro** -vaihtoehto ja valitse sitten **Muokkaa käyttöoikeuksien määrää**.

### <a name="assign-licenses-in-the-microsoft-365-admin-center"></a>Käyttöoikeuksien määrittäminen Microsoft 365 -hallintakeskuksessa

Lisätietoja käyttöoikeuksien määrittämisestä Microsoft 365 ‑hallintakeskuksessa saat kohdasta [Käyttöoikeuksien määrittäminen käyttäjille](/office365/admin/manage/assign-licenses-to-users).

Vierailevien käyttäjien osalta katso [Käyttöoikeuksien määrittäminen käyttäjille käyttöoikeussivulta](/office365/admin/manage/assign-licenses-to-users#assign-licenses-to-users-on-the-licenses-page). Ennen kuin määrität Pro-käyttöoikeuksia vieraskäyttäjille, ota yhteyttä Microsoft-tiliedustajaan varmistaaksesi, että se noudattaa Microsoft-sopimuksesi ehtoja.

### <a name="assign-licenses-in-the-azure-portal"></a>Käyttöoikeuksien määrittäminen Azure-portaalissa

Voit määrittää Power BI Pro -käyttöoikeuksia yksittäisille käyttäjätileille seuraavien ohjeiden mukaisesti:

1. Avaa [Azure-portaali](https://portal.azure.com/).

2. Etsi **Azure Active Directory** ja valitse se.

3. Valitse **Azure Active Directory** -kohdassa **Käyttöoikeudet**.

4. Valitse **Käyttöoikeudet**-kohdassa **Kaikki tuotteet** ja valitse sitten **Power BI Pro**. Näin näet luettelon kaikista käyttäjistä, joilla on käyttöoikeus.

5. Jos haluat lisätä Power BI Pro -käyttöoikeuden käyttäjätilille, valitse **Määritä**.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun olet määrittänyt käyttöoikeudet, lue lisää Power BI Prosta.

[Power BI -käyttöoikeudet organisaatiossasi](service-admin-licensing-organization.md)

[Kirjautuneena olevien Power BI -käyttäjien etsiminen](service-admin-access-usage.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
