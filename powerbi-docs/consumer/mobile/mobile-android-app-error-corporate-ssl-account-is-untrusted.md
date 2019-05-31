---
title: Yrityksen SSL-varmenteeseen ei luoteta -ongelman korjaaminen
description: Kun kirjaudut sisään Power BI:n Android-sovellukseen, saatat nähdä viestin siitä, ettei todentaminen onnistunut, koska yrityksen SSL-varmenne ei ole luotettava
.": ''
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mshenhav
ms.openlocfilehash: de103412e21e0d26d20058e2d4e1fb9a8a5449bf
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61341342"
---
# <a name="fixing-corporate-ssl-certificate-is-untrusted---power-bi"></a>Yrityksen SSL-varmenne ei ole luotettava – Power BI -ongelman korjaaminen
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
Jos käytät mukautettua todennuspalvelinta, yrityksen todennuspalvelimen SSL-varmenne ei ehkä ole kelvollinen. Toimi organisaatiosi IT-osaston kanssa, ja testatkaa yrityksen todennuspalvelimen määritykset noudattamalla [tässä artikkelissa](https://support.microsoft.com/en-us/help/3203929/using-adal-to-authenticate-from-android-devices-fails-if-additional-ce) annettuja ohjeita.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Lataa Android-sovellus](http://go.microsoft.com/fwlink/?LinkID=544867) Androidin sovelluskaupasta.
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/) 

