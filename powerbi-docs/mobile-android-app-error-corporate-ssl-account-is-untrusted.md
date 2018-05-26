---
title: 'Virhe: '
corporate: ''
ssl: ''
certificate: ''
is: ''
untrusted": ''
'-': ''
power: ''
bi": ''
description: Kun kirjaudut sisään Power BI:n Android-sovellukseen, saatat nähdä viestin siitä, ettei todentaminen onnistunut, koska yrityksen SSL-varmenne ei ole luotettava
.": ''
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 4ef29c0cab96e21045f30805d7445aa34d37697a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2017
---
# <a name="error-corporate-ssl-certificate-is-untrusted---power-bi"></a>Virhe: Yrityksen SSL-varmenne ei ole luotettava – Power BI
Kun kirjaudut sisään Microsoft Power BI:n Android-mobiilisovellukseen, saatat nähdä viestin siitä, ettei todentaminen onnistunut, koska laite ei luota yrityksen SSL-varmenteeseen. Viestissä kehotetaan ottamaan yhteyttä yrityksesi IT-järjestelmänvalvojaan. 

Tarvittavat toimenpiteet riippuvat Android-laitteen käyttöjärjestelmästä, mutta on olemassa muutamia muita ongelmia, jotka saattavat aiheuttaa kyseisen virheen.

## <a name="on-android-7-or-later"></a>Android 7 tai uudempi versio
Hae **Chrome**-nimiselle sovellukselle päivitys ja asenna se.

## <a name="on-android-6-and-earlier"></a>Android 6 tai vanhempi versio
Laitteesi tarvitsee ehkä System Webview ‑päivityksen. Sovellus saattaa olla valmiiksi asennettuna laitteeseesi, jolloin sinun ei ehkä tarvitse kuin valita **Update** (Päivitä).

Jos laitteeseen ei ole asennettu System Webview ‑sovellusta:

1. Sulje Power BI Android-laitteesta.
2. Avaa Google Play ‑kauppa ja hae **System Webview** ‑sovellus, jonka valmistaja on Google Inc.
3. Asenna sovellus.
4. Käynnistä Power BI-sovellus uudelleen ja kirjaudu sisään.

## <a name="time-zone-settings"></a>Aikavyöhykeasetukset
Laitteesi aikavyöhykeasetukset saattavat olla väärin. 

Tarkista ne valitsemalla **Asetukset** > **Järjestelmä** > **Päivämäärä ja kellonaika**.

## <a name="custom-authentication-server"></a>Mukautettu todennuspalvelin
Jos käytät mukautettua todennuspalvelinta, yrityksen todennuspalvelimen SSL-varmenne ei ehkä ole kelvollinen. Pyydä apua organisaatiosi IT-järjestelmänvalvojalta.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Lataa Android-sovellus](http://go.microsoft.com/fwlink/?LinkID=544867) Androidin sovelluskaupasta.
* Ilmenikö kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

