---
title: Automaattista reaaliaikaisten tietojen säilytyskäytäntöä käyttävät Power BI -ohjelmointirajapinnat
description: Lue lisää Power BI -palvelun automaattisesta säilytyskäytännöstä
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 3ac4c28b3f07cb1a19e241089b54ee4594a7a7dd
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/14/2020
ms.locfileid: "79378290"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Automaattinen reaaliaikaisten tietojen säilytyskäytäntö

Power BI -palvelun automaattinen säilytyskäytäntö on kyselymerkkijonoparametri, jonka avulla oletussäilytyskäytäntö siistii automaattisesti vanhat tiedot samalla, kun uudet tiedot siirtyvät katkeamattomana vuona tietokantaan. Ensimmäisen säilytyskäytännön nimi on *first in first out (FIFO)* (ensimmäisenä sisään, ensimmäisenä ulos). Kun se on käytössä, tietoja kerätään taulukkoon 200 000 riviin asti. Kun tietojen määrä ylittää 200 000 riviä, vanhimmat rivit pudotetaan pois tietojoukosta. Näin taulukossa pidetään aina tietojen 200 000–210 000 uusinta riviä.  
  
<center>

![säilytyskäytäntö](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Säilytyskäytännöt tulevat käyttöön, kun luot tietojoukot. Sinun on ainoastaan lisättävä oletussäilytyskäytännön kyselyparametri POST-testitietojoukkojen kutsuun ja määritettävä sen arvoksi *basicFIFO*.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}