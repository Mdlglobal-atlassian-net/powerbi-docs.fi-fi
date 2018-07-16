---
title: Power BI:n lisääminen Office 365 -kumppanille ei onnistu
description: Power BI:tä ei voi lisätä Office 365:n syndikointikumppanille. Syndikoitu malli on Office 365:n käyttämä ostamisen malli.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 09/05/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: a86b1d6823a1d889b47015d1213a9a056c537703
ms.sourcegitcommit: 627918a704da793a45fed00cc57feced4a760395
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/10/2018
ms.locfileid: "37926647"
---
# <a name="unable-to-add-power-bi-to-office-365-partner-subscription"></a>Power BI:tä ei voi lisätä Office 365 -kumppanitilaukseen
Office 365:n avulla yritykset voivat myydä Office 365:n paketoituna ja yhdistettynä omiin ratkaisuihinsa, jotta loppuasiakkaat saavat yhden yksittäisen yhteyspisteen ostamiseen, laskutukseen ja tukeen.

Jos olet kiinnostunut hankkimaan Power BI:n Office 365 -tilauksen rinnalle, ota yhteyttä kumppaniisi. Jos kumppanisi ei tarjoa Power BI:tä, käytettävissä on useita vaihtoehtoja.

1. Voit ostaa palvelun toisesta kanavasta joko suoraan Microsoftilta tai toiselta kumppanilta. Tämä vaihtoehto ei ole käytettävissä kaikille asiakkaille kumppanisuhteesta riippuen. Voit tarkistaa asian valitsemalla **Office 365 -hallintaportaali** > **Laskutus** > **Tilaukset**. Jos näet **Tilaukset**-kohdan, voit hankkia palvelun suoraan Microsoftilta tai voit ottaa yhteyttä kumppaniin, jonka valikoimassa on Power BI.
   
    ![](media/service-admin-syndication-partner/billingsub.png)
2. Jos et näe **Tilaukset**-kohtaa **Laskutus**-kohdassa, et voi ostaa suoraan Microsoftilta tai toiselta kumppanilta. 
   
   ![](media/service-admin-syndication-partner/billing.png)

Jos et voi ostaa Power BI:tä suoraan, käytettävissä on joitakin vaihtoehtoja sen mukaan, millaisesta Power BI -tilauksesta olet kiinnostunut.

[Power BI (ilmainen)](#power-bi-free)

[Power BI Pro ja Premium](#power-bi-pro-and-premium)

## <a name="power-bi-free"></a>Power BI (ilmainen)
Jos olet tyytyväinen Power BI:n ilmaisversioon, voit rekisteröityä ilmaiseen palveluun. Oletusarvoisesti yksittäiset rekisteröitymiset, joita kutsutaan myös ad-hoc-tilauksiksi, on poistettu käytöstä. Kun yrität rekisteröityä Power BI:hin, näyttöön tulee sanoma, joka ilmaisee, että IT-osastosi on poistanut Microsoft Power BI:hin rekisteröitymisen käytöstä.

    Your IT department has turned off signup for Microsoft Power BI.

![](media/service-admin-syndication-partner/sorry.png)

Jotta ad-hoc-tilaukset voidaan ottaa käyttöön, voit ottaa yhteyttä kumppaniisi ja pyytää, että tilaukset otetaan käyttöön. Jos olet vuokraajan järjestelmänvalvoja ja tiedät, miten voit hyödyntää Azure Active Directoryn PowerShell-komentoja, voit ottaa ad-hoc-tilaukset käyttöön itse. [Lue lisää](https://technet.microsoft.com/library/jj151815.aspx)

1. Sinun on ensin kirjauduttava Azure Active Directoryyn käyttämällä Office 365 -tunnistetietojasi. Ensimmäisellä rivillä pyydetään syöttämään tunnistetiedot. Toinen rivi muodostaa yhteyden Azure Active Directoryyn.
   
        $msolcred = get-credential
        connect-msolservice -credential $msolcred
   
    ![](media/service-admin-syndication-partner/aad-signin.png)
2. Kun olet kirjautunut sisään, voit ottaa ilmaiset rekisteröitymiset käyttöön lähettämällä seuraavan komennon.
   
        Set-MsolCompanySettings -AllowAdHocSubscriptions $true

## <a name="power-bi-pro-and-premium"></a>Power BI Pro ja Premium
Jos haluat ostaa Power BI Pro- tai Power BI Premium -tilauksen, joudut tekemään yhteistyötä kumppanisi kanssa käytettävissä olevien vaihtoehtojen selvittämistä varten.

* Kumppani voi lisätä Power BI:n portfolioonsa, jotta voit ostaa palvelun heiltä.
* Kumppani voi siirtää sinut malliin, jossa voit ostaa Power BI:n suoraan Microsoftilta tai toiselta kumppanilta, jonka valikoimassa on Power BI.

## <a name="next-steps"></a>Seuraavat vaiheet
[Azure AD:n hallitseminen Windows PowerShellin avulla](https://technet.microsoft.com/library/jj151815.aspx)  
[Power BI Premium – mikä se on?](service-premium.md)

Ilmenikö muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

