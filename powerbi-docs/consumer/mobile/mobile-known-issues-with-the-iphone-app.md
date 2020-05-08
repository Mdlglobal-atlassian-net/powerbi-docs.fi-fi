---
title: ”tietoliikennevirheitä” iOS-mobiilisovelluksissa – Power BI -ongelman korjaaminen
description: 'Tämä artikkeli saattaa auttaa, jos saat seuraavan ilmoituksen: ”Havaittiin tietoliikennevirheitä. Virheet saattavat liittyä WLAN-yhteytesi välityspalvelinasetuksiin.”'
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: painbar
ms.openlocfilehash: 0162d78fd4358f415ac52ea70bd3460d3c28b722
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79114908"
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

