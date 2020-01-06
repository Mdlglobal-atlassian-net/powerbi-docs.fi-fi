---
title: Tekstinä palautettujen sisäkkäisten arvojen vianmääritys Power BI -palvelussa
description: Lue, miten voit korjata merkkijonoksi muunnettavat sisäkkäiset arvot, kun käytössä on virheelliset tietolähteen tietosuoja-asetukset
author: cpopell
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 6/4/2019
ms.author: gepopell
LocalizationGroup: Reports
ms.openlocfilehash: ab40ca9c415dacf52f4d82eb2c157d57aef92f93
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "73871279"
---
# <a name="troubleshooting-nested-values-returned-as-text-in-power-bi-service"></a>Tekstinä palautettujen sisäkkäisten arvojen vianmääritys Power BI -palvelussa

## <a name="cause"></a>Syy

Aiemmin oli tapauksia, joissa Power BI -raportit päivittyivät normaalisti Desktopissa, mutta eivät Power BI -palvelussa. Tapauksiin liittyi “Arvon "[Taulukko]" muuntaminen taulukkotyyppiseksi” -virhesanomia ja sen kaltaisia sanomia. Eräs virheen aiheuttajista oli se, että kun tietosuojan palomuuri puskuroi tietolähdettä, sisäkkäiset ei-skalaariarvot (kuten taulukot, tietueet, luettelot ja funktiot) muunnetaan automaattisesti tekstiarvoiksi (kuten “[Taulukko]” tai “[tietue]”).

Nyt kun Power BI -palvelu tukee yksityisyystasojen asetusta (ja palomuurin poistamista kokonaan käytöstä), tällaiset virheet voidaan välttää [määrittämällä tietolähteiden tietosuoja-asetukset](https://powerbi.microsoft.com/blog/privacy-levels-for-cloud-data-sources/) Power BI -palvelussa ei-yksityisiksi.

Kesäkuun Power BI -versiosta lähtien sisäkkäistä taulukkoa/tietuetta/luetteloa/tms. puskuroiva palomuuri tuottaa seuraavan virhesanoman (sen sijaan, että arvot muunnettaisiin tekstiksi ilmoittamatta): 

`We cannot return a value of type Table in this context`

## <a name="effect-on-loadrefresh"></a>Vaikutus lataa/päivitä-toimintoon

Vaikka palomuurin puskurointi oli muutoksen taustalla, se vaikuttaa myös lataa/päivitä-toimintoon. Palomuurin puskuroinnin ongelmien korjaaminen edellytti sisäkkäisten taulukoiden/tietueiden/jne. toiminnan muuttamista Power BI -mallissa ja Excel-tietomalliin PQ for Excelissä. Aiemmin sisäkkäiset taulukot/tietueet/jne. ladattiin tekstinarvoina (esim. ”[Taulukko]” tai ”[Tietue]”). Nyt niitä pidetään virheitä, jotka aiheuttavat ladatussa taulukossa nolla-arvon ja virhemäärän kasvun lataamisen tuloksissa.

Koska tällaiset virheet esiintyvät ainoastaan lataa/päivitä-toiminnon aikana, ne eivät näy Power Query -editorissa.

### <a name="before"></a>Ennen

- Lataa/päivitä ilman virheitä
- Ladattu taulukko sisältää ”[Taulukko]”-, ”[Tietue]”- ym. arvoja
 

### <a name="after"></a>Jälkeen

- Lataa/päivitä, jossa virheitä
- Ladattu taulukko sisältää NULL-virheitä ”[Taulukko]”-, ”[Tietue]”- ym. arvojen sijaan
 

## <a name="resolution"></a>Ratkaisu

Yritätkö ladata saraketta, joka sisältää ei-skalaariarvoja (esim. taulukoita, luetteloita, tietueita jne.)?
Jos yrität, virheiden pitäisi poistua, kun poistat kyseisen sarakkeen.
Jos et voi poistaa saraketta, sinun pitäisi pystyä toistamaan vanha toiminta lisäämällä mukautettu sarake ja käyttämällä seuraavan esimerkin mukaista logiikkaa:

`if [MyColumn] is table then "[Table]" else if [MyColumn] is record then "[Record]" else if [MyColumn] is list then "[List]" else if [MyColumn] is function then "[Function]" else [MyColumn]`

Toistuuko ongelma Power BI Desktopissa, jos määrität kaikki tietolähteesi yksityisiksi tietosuoja-asetuksista?
Jos toistuu, ongelman pitäisi korjautua [määrittämällä tietolähteet ei-yksityisiksi ](https://powerbi.microsoft.com/blog/privacy-levels-for-cloud-data-sources/) Power BI -palvelun tietosuoja-asetuksista.
