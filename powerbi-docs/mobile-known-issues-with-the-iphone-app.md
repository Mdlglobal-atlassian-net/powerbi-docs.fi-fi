---
title: ”tietoliikennevirheitä” iOS-mobiilisovelluksissa – Power BI -ongelman korjaaminen
description: 'Tämä artikkeli saattaa auttaa, jos saat seuraavan ilmoituksen: ”Havaittiin tietoliikennevirheitä. Virheet saattavat liittyä WLAN-yhteytesi välityspalvelinasetuksiin.”'
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: maggies
ms.openlocfilehash: 3c54cb47744d5afc2c97ddd15ac77a326a1f9858
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/03/2018
ms.locfileid: "37598230"
---
# <a name="fixing-communication-failures-in-ios-mobile-apps---power-bi"></a>”tietoliikennevirheitä” iOS-mobiilisovelluksissa – Power BI -ongelman korjaaminen

| ![iPhone](media/mobile-known-issues-with-the-iphone-app/iphone-logo-50-px.png) | ![iPad](media/mobile-known-issues-with-the-iphone-app/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhonet |iPadit |

## <a name="we-encountered-communication-failures"></a>”Havaittiin tietoliikennevirheitä”
”Havaittiin tietoliikennevirheitä. Virheet saattavat liittyä WLAN-yhteytesi välityspalvelinasetuksiin. Ongelman saattaa ratkaista vaihtaminen toiseen WLAN-yhteyteen.”

Saatat saada virheilmoituksen, jos iPhonen tai iPadin internet-yhteys edellyttää, että pakollinen, eksplisiittinen HTTP-välityspalvelin määritetty joko manuaalisesti tai automaattisesti. Tällaisessa tapauksessa Power BI ‑sovellus ei toimi iOS-laitteessa.

### <a name="workaround"></a>Vaihtoehtoinen menetelmä
Vaihda iPhonen tai iPadin internet-yhteys sellaiseen, joka ei edellytä eksplisiittistä HTTP-välityspalvelinasetusta (eli sellaiseen, jonka HTTP-välityspalvelinasetukseksi on määritetty Ei käytössä).

## <a name="other-issues"></a>Muita ongelmia?
[Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/).

