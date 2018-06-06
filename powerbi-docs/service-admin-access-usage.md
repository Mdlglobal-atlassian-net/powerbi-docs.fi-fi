---
title: Kirjautuneena olevien Power BI -käyttäjien etsiminen
description: Jos olet vuokraajan järjestelmänvalvoja ja haluat nähdä, kuka on kirjautuneena sisään Power BI:hin, voit katsoa sen Azure Active Directory ‑käyttöoikeudella käyttöraporteista.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 50ace772c24b2a9e706e82ca16ddcb36d8b6b60c
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34722197"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Kirjautuneena olevien Power BI -käyttäjien etsiminen
Jos olet vuokraajan järjestelmänvalvoja ja haluat nähdä, kuka on kirjautuneena sisään Power BI:hin, voit katsoa sen Azure Active Directory ‑käyttöoikeudella käyttöraporteista.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

Pääset tarkastelemaan toimintaraporttia sekä [uuden](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins) että [perinteisen](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) Azure Active Directory (Azure AD) ‑portaalin kautta. Edellä olevalla videolla käsitellään esimerkkinä perinteistä portaalia, mutta tässä artikkelissa puhutaan uudesta portaalista.

> [!NOTE]
> Toimintaraportti sisältää sekä Power BI:n maksuttomat käyttäjät että Power BI Pro ‑käyttäjät, mutta siinä ei mainita kumpi käyttöoikeus kullakin käyttäjällä on.
> 
> 

## <a name="requirements"></a>Vaatimukset
Kirjautumisen toimintaraportin tarkastelu edellyttää, että seuraavat ehdot täyttyvät.

* Yleisen järjestelmänvalvojan, suojauksenvalvojan tai suojauksenlukijan roolissa olevilla käyttäjillä on tietoihin käyttöoikeus.
* Kuka tahansa käyttäjä (ei järjestelmänvalvoja) pystyy näkemään omat kirjautumisensa.
* Vuokraajalla on oltava vuokraajaan liitetty Azure AD Premium ‑käyttöoikeus, jotta se voi nähdä kirjautumistoimintaraportin kokonaisuudessaan.

## <a name="using-the-azure-portal-to-view-sign-ins"></a>Kirjautumisten tarkastelu Azure-portaalin kautta
Voit tarkastella kirjautumistoimintoja Azure AD-portaalista.

1. Siirry **Azure-portaaliin** ja valitse **Azure Active Directory**.
2. Valitse **Toiminta**-kohdasta **Sisäänkirjautumiset**.
   
    ![](media/service-admin-access-usage/azure-portal-sign-ins.png)
3. Valitse Sovellus-kenttään suodattimeksi joko **Microsoft Power BI** tai **Power BI Gateway** ja valitse **Käytä**.
   
    **Microsoft Power BI** vastaa palvelun kirjautumistoimintaa, kun taas **Power BI Gateway** vastaa paikallisen tietoyhdyskäytävän tiettyjä kirjautumisia.
   
    ![](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Tietojen vieminen
Voit viedä kirjautumistiedot kahdella eri tavalla. Voit joko ladata CSV-tiedoston tai käyttää PowerShelliä.

### <a name="download-csv"></a>CSV-tiedoston lataaminen
Valitse toimintanäkymän työkaluriviltä **Lataa**. Toiminto lataa suodattimien mukaiset tiedot csv-tiedostona.

![](media/service-admin-access-usage/download-sign-in-data-csv.png)

### <a name="powershell"></a>PowerShell
Voit viedä kirjautumistiedot myös PowerShellin avulla. Azure AD:n ohjeissa on saatavilla siihen [malli](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script).

> [!NOTE]
> Jotta PowerShell-malli toimisi, muista noudattaa [Azure AD:n raportointi-API:n käyttämisen edellytyksiä](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-prerequisites).
> 
> 

## <a name="data-retention"></a>Tietojen säilytys
Kirjautumiseen liittyviä tietoja voidaan pitää käytettävissä enintään 30 päivän ajan. Lisätietoja on artikkelissa [Azure Active Directoryn raporttien säilytyskäytännöt](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention).

## <a name="next-steps"></a>Seuraavat vaiheet
[Kirjautumisen toimintaraportit Azure Active Directory ‑portaalissa (uusi portaali)](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins)  
[Käyttöraporttien tarkastelu (perinteinen portaali)](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports#view-or-download-a-report)  
[PowerShell-komentosarjamalli kirjautumiseen](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script)  
[Azure Active Directoryn raporttien säilytyskäytännöt](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention)  
[Valvonnan käyttö organisaatiossa](service-admin-auditing.md)  
[Laajennetun Pro-kokeiluversion aktivointi](service-extended-pro-trial.md)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

