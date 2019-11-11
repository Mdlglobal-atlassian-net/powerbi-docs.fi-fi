---
title: Kertakirjautuminen Power BI -mobiilin Windows-sovelluksessa
description: Lue lisää kertakirjautumisesta Power BI:n Windows-mobiilisovellukseen. Kertakirjautuminen tarkoittaa, että voit käyttää liiketoiminnan hoitamisessa tarvitsemiasi sovelluksia ja resursseja kirjautumalla sisään vain kerran yhdellä käyttäjätilillä.
author: mshenhav
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 09/17/2018
ms.author: mshenhav
ms.openlocfilehash: 4ec2e43843d37f0966070d39e08ae0ab6160dbf8
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73876666"
---
# <a name="single-sign-on-in-the-power-bi-mobile-windows-app"></a>Kertakirjautuminen Power BI:n Windows-mobiilisovelluksessa

Lue lisää kertakirjautumisesta Power BI:n Windows-mobiilisovellukseen. Kertakirjautuminen tarkoittaa, että voit käyttää liiketoiminnan hoitamisessa tarvitsemiasi sovelluksia ja resursseja kirjautumalla sisään vain kerran yhdellä käyttäjätilillä. Kun olet kirjautunut sisään, voit käyttää kyseisiä sovelluksia ilman, että todennusta täytyy tehdä uudelleen. 

Koska Power BI Windows -sovellus on integroitu Azure Active Directoryyn, voit käyttää ensisijaista organisaatiotiliäsi toimialueeseen liitettyihin laitteisiin kirjautumisen lisäksi myös kirjautumisessa sisään Power BI -palveluun. Jos tarkastelet Power BI:tä s Windows -puhelimella, voit varmistaa, että Power BI:tä varten käyttämäsi tili on määritetty työpaikan tai oppilaitoksen tilinä laitteen asetuksissa.  

Kertakirjautuminen on käytettävissä vain Windows-laitteissa, joita Windows Azure Active Directory hallitsee. 

## <a name="sign-in-with-sso"></a>Kertakirjautumisen käyttäminen

Sisäänkirjautumisen yksinkertaistamiseksi kun asennat sovelluksen ensimmäisen kerran, sovellus yrittää automaattisesti tehdä todennuksen Power BI -palveluun kertakirjautumista käyttämällä. Vain jos tämä prosessi ei onnistu, sovellus pyytää sinua antamaan Power BI -tunnistetietosi.  

Jos käytät jo Power BI -mobiilisovellusta Windowsille, kun päivität sovelluksen uuteen versioon, voit käyttää myös kertakirjautumista. Kirjaudu ulos sovelluksesta, sulje se ja avaa se uudelleen. Kun sovellus avautuu uudelleen, se yrittää automaattisesti käyttää nykyisiä Windows-tunnistetietojasi todennuksen tekemiseksi Power BI -palveluun. 

Jos et halua käyttää nykyisen aktiivisen Windows-istunnon tunnistetietojasi Power BI:n kirjautumiseen, valitse **Asetukset**, kirjaudu ulos ja kirjaudu sisään eri tunnistetiedoilla. 
 
## <a name="next-steps"></a>Seuraavat vaiheet

- [Windows 10:n Power BI -mobiilisovelluksen käytön aloittaminen](mobile-windows-10-phone-app-get-started.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

