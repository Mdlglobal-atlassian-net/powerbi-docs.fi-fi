---
title: 'Pikaopas: Power BI Pro -käyttöoikeuksien määrittäminen Azuressa'
description: Lue, miten Power BI Pro -käyttöoikeudet määritetään niin, että käyttäjät voivat käyttää kaikkea sisältöä ja kaikkia ominaisuuksia Power BI -palvelussa.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: quickstart
ms.date: 05/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: d092fc26f913028f7ce30ab6b2f860d75c5db2b7
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34294429"
---
# <a name="quickstart-assign-power-bi-pro-licenses-in-azure"></a>Pikaopas: Power BI Pro -käyttöoikeuksien määrittäminen Azuressa

Power BI Pro on yksittäinen käyttöoikeus, joka sallii kaiken sisällön ja kaikkien ominaisuuksien käytön Power BI -palvelussa, eli myös sisällön jakamisen ja yhteistyön muiden Pro-käyttäjien kanssa. Vain Pro-käyttäjät voivat julkaista ja käyttää sisältöä sovelluksen työtiloista, jakaa koontinäyttöjä sekä tilata koontinäyttöjä ja raportteja. Tässä artikkelissa kerrotaan, miten voit määrittää Power BI Pro -käyttöoikeudet Azuressa. Lisäksi voit [määrittää käyttöoikeuksia Office 365:ssä](service-admin-assigning-power-bi-pro-licenses.md).


## <a name="prerequisites"></a>Edellytykset

Sinulla on oltava Azure-tilaus, jota Power BI käyttää Active Directory -hauissa.

Sinun on [ostettava ainakin yksi käyttöoikeus](service-admin-purchasing-power-bi-pro.md) ennen aloittamista.


## <a name="assign-licenses-to-individual-user-accounts"></a>Käyttöoikeuksien määrittäminen yksittäisille käyttäjätileille

Voit määrittää Power BI Pro -käyttöoikeuksia yksittäisille käyttäjätileille seuraavien ohjeiden mukaisesti:

1. Avaa [Azure-portaali](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0). 

2. Valitse vasemmassa siirtymispalkissa **Azure Active Directory**.

    ![Azure Active Directory](media/service-admin-assigning-power-bi-pro-licenses-azure/service-assigning-power-bi-pro-licenses-01.png)

3. Valitse **Azure Active Directory** -kohdassa **Käyttöoikeudet**.

    ![Käyttöoikeudet](media/service-admin-assigning-power-bi-pro-licenses-azure/service-assigning-power-bi-pro-licenses-02.png)

4. Valitse **Käyttöoikeudet**-kohdassa **Kaikki tuotteet** ja valitse sitten **Power BI Pro**. Näin näet luettelon kaikista käyttäjistä, joilla on käyttöoikeus.

    ![Käyttöoikeudet – Kaikki tuotteet](media/service-admin-assigning-power-bi-pro-licenses-azure/service-assigning-power-bi-pro-licenses-03.png)

5. Jos haluat lisätä Power BI Pro -käyttöoikeuden uudelle käyttäjätilille, valitse **Määritä**.

    ![Käyttöoikeuden määritys](media/service-admin-assigning-power-bi-pro-licenses-azure/service-assigning-power-bi-pro-licenses-04.png)


## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun olet määrittänyt käyttöoikeudet, lue lisää Power BI Prosta.

[Power BI Pro organisaatiossasi](service-admin-power-bi-pro-in-your-organization.md)

[Kirjautuneiden Power BI -käyttäjien etsiminen](service-admin-access-usage.md)

Ilmenikö muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)