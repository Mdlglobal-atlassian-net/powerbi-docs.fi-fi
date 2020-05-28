---
title: Tietojoukkojen vaikutusanalyysi
description: Visualisoi ja analysoi tietojoukkojen muutosten vaikutusta jatkossa.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.date: 04/13/2020
ms.author: painbar
LocalizationGroup: ''
ms.openlocfilehash: dd7387bcb008d10ec8887ac777431b5423d43f4c
ms.sourcegitcommit: a7b142685738a2f26ae0a5fa08f894f9ff03557b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/28/2020
ms.locfileid: "84120335"
---
# <a name="dataset-impact-analysis"></a>Tietojoukkojen vaikutusanalyysi

Kun teet muutoksia tietojoukkoon tai harkitset niitä, on tärkeää kyetä arvioimaan niiden vaikutusta kyseistä tietojoukkoa käyttävissä raporteissa ja koontinäytöissä. **Tietojoukkojen vaikutusanalyysi** tarjoaa tietoja näihin arviointeihin.
* Siitä näet, moneenko työtilaan, raporttiin ja koontinäyttöön muutoksesi saattaa vaikuttaa. Vaikutusanalyysista voit myös siirtyä helposti työtiloihin, joissa kyseiset raportit ja koontinäytöt ovat, jotta voit tutkia asiaa tarkemmin.
* Näet, kuinka monta yksilöllistä kävijää ja näyttökertaa niillä kohteilla on, joihin muutos saattaa vaikuttaa. Näin voit arvioida muutoksen kokonaisvaikutusta. On esimerkiksi varmaan tärkeämpää tutkia muutoksen vaikutusta raportissa, jolla on 20 000 yksilöllistä kävijää, kuin muutoksen vaikutusta raportissa, jolla on kolme katselijaa.
* Vaikutusanalyysi tarjoaa helpon tavan ilmoittaa ihmisille tekemästäsi tai harkitsemastasi muutoksesta.

Tietojoukkojen vaikutusanalyysin voi avata helposti [tietojen siirtymänäkymässä](service-data-lineage.md).

## <a name="identifying-shared-datasets"></a>Jaettujen tietojoukkojen tunnistaminen

Voit suorittaa tietojoukkojen vaikutusanalyysin sekä jaetuille että jakamattomille tietojoukoille. Siitä on kuitenkin erityisesti hyötyä tietojoukoissa, jotka on jaettu työtilojen kesken ja joissa on paljon vaikeampaa saada selvää kuvaa riippuvuuksista kuin jakamattomissa tietojoukoissa, joissa riippuvuudet sijaitsevat samassa työtilassa kuin itse tietojoukko.

Tietojen siirtymänäkymässä näet jaettujen ja jakamattomien tietojoukkojen eron kuvakkeesta, joka näkyy tietojoukon kortin vasemmassa yläkulmassa.

![Jaetun ja jakamattoman tietojoukon kuvakkeet](media/service-dataset-impact-analysis/shared-unshared-icon.png)

## <a name="perform-dataset-impact-analysis"></a>Tietojoukkojen vaikutusanalyysin suorittaminen

Voit suorittaa vaikutusanalyysin mille tahansa työtilan tietojoukolle riippumatta siitä, onko se jaettu vai ei. Et voi suorittaa vaikutusanalyysia ulkoisille tietojoukoille, jotka näytetään siirtymänäkymässä, mutta jotka todellisuudessa sijaitsevat toisessa työtilassa. Jos haluat suorittaa vaikutusanalyysin ulkoiselle tietojoukolle, sinun täytyy siirtyä lähdetyötilaan.

Kun haluat suorittaa tietojoukon vaikutusanalyysin, napsauta vaikutusanalyysipainiketta tietojoukkokortissa.

![Tietojoukkojen vaikutusanalyysi -painike](media/service-dataset-impact-analysis/open-analysis-pane-button.png)

Vaikutusanalyysin sivupaneeli avautuu.

![Tietojoukkojen vaikutusanalyysin sivupaneeli](media/service-dataset-impact-analysis/service-impact-analysis-pane.png)

* **Vaikutusten yhteenvedosta** näet niiden työtilojen, raporttien ja koontinäyttöjen määrän, joihin muutos mahdollisesti vaikuttaa, sekä kaikkien kyseiseen tietojoukkoon liittyvien raporttien ja koontinäyttöjen näyttökertojen kokonaismäärän.
* **Yhteyshenkilöille ilmoittamisen** linkki avaa valintaikkunan, jossa voit luoda ja lähettää viestin tekemistäsi tietojoukon muutoksista niiden työtilojen yhteyshenkilöille, joihin muutos vaikuttaa. 
* **Käyttöerittelystä** näet kunkin työtilan näyttökertojen kokonaismäärän sen sisältämille raporteille ja koontinäytöille, joihin muutos saattaa vaikuttaa, sekä kunkin raportin ja koontinäytön katsojien kokonaismäärän ja näyttökertojen määrän. Alla on lisätietoja näistä näytettävistä tiedoista:
   * Katselijat: tämä on raportin tai koontinäytön katsoneiden käyttäjien määrä.
   * Katselukerrat: tämä on raportin tai koontinäytön katselukertojen määrä.

Käyttötiedot ovat tietoja edelliseltä 30 päivältä (nykyinen päivä pois lukien). Määrät sisältävät käytön liittyvien sovellusten kautta. Näiden tietojen avulla saat kuvan tietojoukon käytöstä vuokraajassa. Niiden avulla voit myös arvioida tietojoukkojen muutosten vaikutuksia.

## <a name="notify-contacts"></a>Ilmoita yhteyshenkilöille

Jos olet tehnyt tietojoukkoon muutoksen tai harkitset sitä, sinun kannattaa ehkä ilmoittaa siitä tarvittaville käyttäjille. Kun ilmoitat yhteyshenkilöille, järjestelmä lähettää sähköpostin niiden työtilojen [yhteystietoluettelossa](../collaborate-share/service-create-the-new-workspaces.md#create-a-contact-list) oleville, joihin muutos vaikuttaa. Nimesi näytetään sähköpostissa, joten yhteyshenkilöt voivat ottaa sinuun yhteyttä sähköpostitse. 

1. Napsauta vaikutusanalyysin sivupaneelissa **Ilmoita yhteyshenkilöille**. Yhteyshenkilöille ilmoittamisen valintaikkuna avautuu.

   ![Ilmoita yhteyshenkilöille -valintaikkuna](media/service-dataset-impact-analysis/notify-contacts-dialog.png)

1. Anna tekstiruutuun tietoja muutoksesta.
1. Kun viestin valmis, napsauta **Lähetä**.

> [!NOTE]
> Yhteyshenkilöille ilmoittaminen ei ole käytettävissä, jos tietojoukko, jonka vaikutusanalyysiä teet, sijaitsee perinteisessä työtilassa.

## <a name="privacy"></a>Tietosuoja

Jos haluat suorittaa tietojoukon vaikutusanalyysin, sinulla täytyy olla kirjoitusoikeudet tietojoukkoon. Vaikutusanalyysin sivupaneelissa näet vain niiden työtilojen, raporttien ja koontinäyttöjen oikeat nimet, joihin sinulla on käyttöoikeus. Niiden kohteiden kohdalla, joihin sinulla ei ole käyttöoikeutta, näytetään ilmoitus **rajoitetusta käytöstä**. Tämä johtuu siitä, että kohteiden nimet saattavat sisältää henkilötietoja.

Vaikka sinulla ei olisi joidenkin työtilojen käyttöoikeutta, näet kuitenkin niiden käytön yhteenvetotiedot. Ilmoituksesi yhteyshenkilöille lähetetään myös näiden työtilojen yhteystietoluettelossa oleville.

## <a name="impact-analysis-from-power-bi-desktop"></a>Vaikutusanalyysi Power BI Desktopista

Kun teet muutoksia tietojoukkoon Power BI Desktopissa ja julkaiset sitten tietojoukon uudelleen Power BI -palveluun, saat ilmoituksen siitä, kuinka moneen työtilaan, raporttiin ja koontinäyttöön tämä muutos voi vaikuttaa. Lisäksi sinulta kysytään, haluatko korvata tällä hetkellä julkaistun tietojoukon muokkaamallasi tietojoukolla. Ilmoitus sisältää myös linkin tietojoukon koko vaikutusanalyysiin Power BI -palvelussa, jossa näet lisää tietoja ja jossa voit ryhtyä toimiin muutosriskien ehkäisemiseksi.

![Tietojoukon vaikutusanalyysin ilmoitus Power BI Desktopista](media/service-dataset-impact-analysis/service-dataset-impact-analysis-desktop-warning.png)

> [!NOTE]
> Ilmoituksessa näytetyt tiedot ilmaisevat vain mahdollisia vaikutuksia: tämä ei välttämättä tarkoita sitä, että mikään olisi rikki. Usein tietojoukon muutoksilla ei ole kielteisiä vaikutuksia raportteihin ja koontinäyttöihin, mutta saat silti tämän ilmoituksen, josta saat tarkempia tietoja mahdollisista vaikutuksista.
>
>Ilmoituksessa näytetään työtilojen määrä vain, jos useat työtilat sisältävät raportteja ja koontinäyttöjä, joihin muutokset vaikuttavat.

## <a name="limitations"></a>Rajoitukset

* Käyttötietoja ei tällä hetkellä tueta perinteisissä tai henkilökohtaisissa työtiloissa.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Johdanto tietojoukkojen käyttöön eri työtiloissa (esikatselu)](../connect-data/service-datasets-across-workspaces.md)
* [Tietojen siirtymä](service-data-lineage.md)

