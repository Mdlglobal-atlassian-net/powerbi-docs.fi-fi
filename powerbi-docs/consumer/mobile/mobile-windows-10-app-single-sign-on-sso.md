---
title: Kertakirjautuminen Power BI -mobiilin Windows-sovelluksessa
description: Lue lisää kertakirjautumisesta Power BI -mobiilin Windows-sovellukseen. Kertakirjautuminen tarkoittaa, että voit käyttää liiketoiminnan hoitamisessa tarvitsemiasi sovelluksia ja resursseja kirjautumalla sisään vain kerran yhdellä käyttäjätilillä.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 09/17/2018
ms.author: maggies
ms.openlocfilehash: f13b6e0a6583bcb66da0fb0a27188c83c4bf6806
ms.sourcegitcommit: 698b788720282b67d3e22ae5de572b54056f1b6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/17/2018
ms.locfileid: "45975031"
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
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

