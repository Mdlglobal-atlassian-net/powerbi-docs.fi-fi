---
title: 'Ulkopuolinen palvelu: Facebook-yhdistin Power BI Desktopille'
description: 'Ulkopuolinen palvelu: Facebook-yhdistin Power BI Desktopille'
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/20/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 882cddf7728a27e78056a35c14fde20f00678e33
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "77527698"
---
# <a name="use-the-facebook-connector-for-power-bi-desktop"></a>Power BI Desktopin Facebook-yhdistimen käyttö
**Power BI Desktopin** Facebook-yhdistin on riippuvainen Facebook Graph ‑ohjelmointirajapinnasta. Siksi sen ominaisuudet ja käytettävyys voivat vaihdella ajan mittaan.

Voit katsella [opetusohjelman Power BI Desktopin Facebook-yhdistimestä](desktop-tutorial-facebook-analytics.md).

> [!IMPORTANT]
> **Facebook-tietoliittimen poistamista koskeva ilmoitus:** Tietojen tuominen ja päivittäminen Facebookista Exceliin lakkaa toimimasta oikein huhtikuun alussa 2020. Voit käyttää Facebookin *Hae ja muunna (Power Query)* -liitintä siihen asti. Kyseisen ajankohdan jälkeen et voi muodostaa yhteyttä Facebookiin ja saat virhesanoman. Suosittelemme tarkistamaan tai poistamaan olemassa olevat Facebook-liitintä käyttävät *Hae ja muunna (Power Query)* -kyselyt mahdollisimman pian odottamattomien tulosten välttämiseksi.


Facebook poisti Graph-ohjelmointirajapinnan version 1.0 käytöstä 30.4.2015. Power BI käyttää Graph-ohjelmointirajapintaa Facebook-yhdistimen taustalla, jotta voit muodostaa yhteyden tietoihisi ja analysoida niitä.

Kyselyt, jotka on luotu ennen 30.4.2015, eivät välttämättä enää toimi tai saattavat palauttaa vähemmän tietoja. 30.4.2015 jälkeen Power BI käyttää versiota 2.8 kaikissa Facebook-ohjelmointirajapinnan kutsuissa. Jos kyselysi on luotu ennen 30.4.2015 ja et ole käyttänyt sitä sen jälkeen, sinun on todennäköisesti tehtävä todennus uudelleen, jotta voit hyväksyä pyytämämme uudet käyttöoikeudet.

Vaikka pyrimmekin julkaisemaan päivityksiä tehtyjen muutosten mukaan, ohjelmointirajapinta saattaa muuttua tavalla, joka vaikuttaa luotujen kyselyjen tuloksiin. Tiettyjä kyselyjä ei ehkä enää tueta joissain tapauksissa. Tämän riippuvuuden vuoksi emme voi taata tekemiesi kyselyjen tuloksia tätä yhdistintä käytettäessä.

Lisätietoja Facebook-ohjelmointirajapinnan muutoksesta saat [täältä](https://developers.facebook.com/docs/apps/changelog#v2_0).

