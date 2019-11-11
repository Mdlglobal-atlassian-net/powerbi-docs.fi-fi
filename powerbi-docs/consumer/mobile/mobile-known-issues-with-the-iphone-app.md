---
title: ”tietoliikennevirheitä” iOS-mobiilisovelluksissa – Power BI -ongelman korjaaminen
description: 'Tämä artikkeli saattaa auttaa, jos saat seuraavan ilmoituksen: ”Havaittiin tietoliikennevirheitä. Virheet saattavat liittyä WLAN-yhteytesi välityspalvelinasetuksiin.”'
author: mshenhav
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: mshenhav
ms.openlocfilehash: 14745d1f2b62845ca0eac549b100bf3e06f8f814
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879101"
---
# <a name="fixing-communication-failures-in-ios-mobile-apps---power-bi"></a>”tietoliikennevirheitä” iOS-mobiilisovelluksissa – Power BI -ongelman korjaaminen

| ![iPhone](./media/mobile-known-issues-with-the-iphone-app/iphone-logo-50-px.png) | ![iPad](./media/mobile-known-issues-with-the-iphone-app/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhonet |iPadit |

## <a name="we-encountered-communication-failures"></a>”Havaittiin tietoliikennevirheitä”
”Havaittiin tietoliikennevirheitä. Virheet saattavat liittyä WLAN-yhteytesi välityspalvelinasetuksiin. Ongelman saattaa ratkaista vaihtaminen toiseen WLAN-yhteyteen.”

Saatat saada virheilmoituksen, jos iPhonen tai iPadin internet-yhteys edellyttää, että pakollinen, eksplisiittinen HTTP-välityspalvelin määritetty joko manuaalisesti tai automaattisesti. Tällaisessa tapauksessa Power BI ‑sovellus ei toimi iOS-laitteessa.

### <a name="workaround"></a>Vaihtoehtoinen menetelmä
Vaihda iPhonen tai iPadin internet-yhteys sellaiseen, joka ei edellytä eksplisiittistä HTTP-välityspalvelinasetusta (eli sellaiseen, jonka HTTP-välityspalvelinasetukseksi on määritetty Ei käytössä).

## <a name="other-issues"></a>Muita ongelmia?
[Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/).

