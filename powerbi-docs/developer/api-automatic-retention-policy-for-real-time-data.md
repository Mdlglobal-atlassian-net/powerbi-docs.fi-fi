---
title: Automaattista reaaliaikaisten tietojen säilytyskäytäntöä käyttävät Power BI -ohjelmointirajapinnat
description: Lue lisää Power BI -palvelun automaattisesta säilytyskäytännöstä
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 9b5923c7bd92b1fe53ebb7ab9416aca8cece3cfa
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54294376"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Automaattinen reaaliaikaisten tietojen säilytyskäytäntö

Power BI -palvelun automaattinen säilytyskäytäntö on kyselymerkkijonoparametri, jonka avulla oletussäilytyskäytäntö siistii automaattisesti vanhat tiedot samalla, kun uudet tiedot siirtyvät katkeamattomana vuona tietokantaan. Ensimmäisen säilytyskäytännön nimi on *basic first in first out (perus-FIFO)*. Kun se on käytössä, tietoja kerätään taulukkoon 200 000 riviin asti. Kun tietojen määrä ylittää 200 000 riviä, vanhimmat rivit putoavat pois tietojoukosta. Näin taulukossa pidetään aina tietojen 200 000–210 000 uusinta riviä.  
  
<center>

![säilytyskäytäntö](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Säilytyskäytännöt tulevat käyttöön, kun luot tietojoukot. Sinun on ainoastaan lisättävä defaultRetentionPolicy-kyselyparametri POST-testitietojoukkojen kutsuun ja määrittää sen arvoksi *basicFIFO*.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}