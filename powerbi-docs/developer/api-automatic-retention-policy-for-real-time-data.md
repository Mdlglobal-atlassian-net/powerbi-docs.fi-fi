---
title: Automaattista reaaliaikaisten tietojen säilytyskäytäntöä käyttävät Power BI -ohjelmointirajapinnat
description: Lue lisää Power BI -palvelun automaattisesta säilytyskäytännöstä
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 07726535246f8b115402373c315062151177d27c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61347303"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Automaattinen reaaliaikaisten tietojen säilytyskäytäntö

Power BI -palvelun automaattinen säilytyskäytäntö on kyselymerkkijonoparametri, jonka avulla oletussäilytyskäytäntö siistii automaattisesti vanhat tiedot samalla, kun uudet tiedot siirtyvät katkeamattomana vuona tietokantaan. Ensimmäisen säilytyskäytännön nimi on *first in first out (FIFO)* (ensimmäisenä sisään, ensimmäisenä ulos). Kun se on käytössä, tietoja kerätään taulukkoon 200 000 riviin asti. Kun tietojen määrä ylittää 200 000 riviä, vanhimmat rivit pudotetaan pois tietojoukosta. Näin taulukossa pidetään aina tietojen 200 000–210 000 uusinta riviä.  
  
<center>

![säilytyskäytäntö](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Säilytyskäytännöt tulevat käyttöön, kun luot tietojoukot. Sinun on ainoastaan lisättävä oletussäilytyskäytännön kyselyparametri POST-testitietojoukkojen kutsuun ja määrittää sen arvoksi *basicFIFO*.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}