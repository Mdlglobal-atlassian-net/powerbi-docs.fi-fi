---
title: Power BI REST -ohjelmointirajapinnan rajoitukset
description: Power BI REST -ohjelmointirajapinnalla on seuraavat rajoitukset
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: df17563d384359fe33123ed87743754bb33bf04d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277967"
---
# <a name="power-bi-rest-api-limitations"></a>Power BI REST -ohjelmointirajapinnan rajoitukset  
  
**JULKAISE rivejä**  
  
* enintään 75 saraketta
* enintään 75 taulukkoa
* enintään 10 000 riviä yksittäistä JULKAISE rivejä -pyyntöä kohden  
* 1 000 000 riviä lisätty tuntia ja tietojoukkoa kohden  
* enintään 5 odottavaa JULKAISE rivejä -pyyntöä tietojoukkoa kohden  
* 120 JULKAISE rivejä -pyyntöä minuuttia ja tietojoukkoa kohden
* Jos taulukossa on vähintään 250 000 riviä, 120 JULKAISE rivejä -pyyntöä tuntia ja tietojoukkoa kohden    
* enintään 200 000 riviä tallennettu taulukkoa kohden FIFO-tietojoukossa  
* enintään 5 000 000 riviä tallennettu taulukkoa kohden ”ei mitään säilytyskäytännön” tietojoukossa  
* 4 000 merkkiä arvoa kohden merkkijonosarakkeelle JULKAISE rivejä -toiminnossa
  
## <a name="see-also"></a>Katso myös

[Azure AD -palvelun rajat ja rajoitukset](https://docs.microsoft.com/azure/active-directory/active-directory-service-limits-restrictions)   
[Power BI REST -ohjelmointirajapinnan yleiskatsaus](https://docs.microsoft.com/rest/api/power-bi/)