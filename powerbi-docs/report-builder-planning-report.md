---
title: Raportin suunnittelu Power BI:n raportin muodostimessa
description: Power BI:n sivutetun raportin muodostimen avulla voit luoda erilaisia sivutettuja raportteja. Raportista tulee hyödyllinen ja helppotajuinen, kun käytät hetken sen suunnitteluun.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 79113505-1ce8-4f8c-9260-d861838f7813
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fd4a318d7a61f6f2298de6b9d5d23ad2ae063d28
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840506"
---
# <a name="planning-a-report-in-power-bi-report-builder"></a>Raportin suunnittelu Power BI:n raportin muodostimessa
  Power BI:n sivutetun raportin muodostimen avulla voit luoda erilaisia sivutettuja raportteja. Voit esimerkiksi luoda raportteja, joissa näytetään myyntitietojen yhteenveto tai niiden tarkka katsaus, toimintaraportteja tai raporttinäkymiä. Voit myös luoda raportteja, joissa hyödynnetään monipuolista tekstin muotoiltua. Tällaisia ovat esimerkiksi myyntitilaukset, tuoteluettelot ja lomakekirjeet. Kaikki nämä raportit on luotu käyttäen samojen peruselementtien yhdistelmiä raportin muodostimessa. Raportista tulee hyödyllinen ja helppotajuinen, kun käytät hetken sen suunnitteluun. Ennen kuin aloitat, pohdi hetki seuraavia asioita:  
  
## <a name="in-what-format-do-you-want-the-report-to-appear"></a>Missä muodossa haluat raportin näkyvän?
  
Voit hahmontaa raportteja verkkoselaimessa, kuten Power BI -portaalissa, tai vedä ne muussa muodossa, kuten Excel, Word tai PDF. Raportin lopullinen muoto on huomioitava, koska osa ominaisuuksista ei ole käytettävissä kaikissa vientimuodoissa. 
  
## <a name="in-what-structure-do-you-want-to-present-the-data"></a>Millainen rakenne esiteltäville tiedoille halutaan?
  
Voit valita esitettäville tiedoille taulukkomuotoisen, matriisi- (muistuttaa välilehtien välistä tai pivot-taulukkoraporttia) tai kaaviorakenteisen tai vapaamuotoisen rakenteen tai jonkin näiden yhdistelmän. Lisätietoja on kohdassa [Taulukot, matriisit ja luettelot Power BI -raportin muodostimessa](report-builder-tables-matrices-lists.md).  
  
## <a name="how-do-you-want-your-report-to-look"></a>Miltä haluat raportin näyttävän?
  
Raportin muodostin tarjoaa paljon raporttikohteita, joita voit lisätä raporttiin tehdäksesi siitä helpomman lukea, korostaaksesi tärkeitä tietoja, auttaaksesi yleisöä siirtymään raportissa ja niin edelleen. Kun tiedät, miltä haluat raportin näyttävän, voit päättää, tarvitsetko tekstiruutuja, suorakulmioita, kuvia, rivejä tai muita raporttikohteita. Ehkä haluat näyttää tai piilottaa kohteita, lisätä asiakirjan rakenneruudun, sisällyttää porautumisraportteja tai aliraportteja tai linkittää muita raportteja.   
  
## <a name="should-the-data-be-filtered"></a>Onko tiedot suodatettava?
  
Ehkä haluat tarkentaa raportin koskemaan tiettyjä käyttäjiä tai paikkoja tai jotain ajanjaksoa. Voit suodattaa raportin tietoja noutamalla ja näyttämällä vain haluamasi tiedot parametrien avulla. Lisätietoja on kohdassa [Raporttiparametrit Power BI -raportin muodostimessa](paginated-reports-parameters.md).  
  
## <a name="do-you-need-to-create-calculations"></a>Onko sinun luotava laskutoimituksia? 
  
     Sometimes, your data source and datasets do not contain the exact fields that you need for your report. In that situation, you might have to create your own calculated fields. For example, you might want to multiply the price per unit times the quantity to get a line item sales amount. Expressions are also used to provide conditional formatting and other advanced features. For more information, see [Expressions in Power BI Report Builder](report-builder-expressions.md).  
  
## <a name="do-you-want-to-hide-report-items-initially"></a>Haluatko piilottaa raporttikohteet aluksi?
  
Mieti, haluatko tietoalueiden, ryhmien tai sarakkeiden olevan aluksi piilossa, kun raportti avataan. Voit esimerkiksi esittää alussa yhteenvetotaulukon ja porautua sen jälkeen yksityiskohtaisiin tietoihin. 
  
## <a name="how-are-you-going-to-deliver-your-report"></a>Miten aiot toimittaa raportin?  
  
     You can save your report to your local computer and continue to work on it, or run it locally for your own information. However, to share your report with others, you need to save the report to Power BI. Saving it to Power BI lets others run it whenever they want to. Alternatively, you can set up a subscription and e-mail delivery of the report to other individuals. You can have the report delivered in a specific export format if you prefer. 
  
## <a name="next-steps"></a>Seuraavat vaiheet

- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
