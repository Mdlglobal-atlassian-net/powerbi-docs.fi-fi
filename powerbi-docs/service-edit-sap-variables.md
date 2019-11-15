---
title: SAP-muuttujien muokkaus Power BI -palvelussa (esikatselu)
description: Azure ja Power BI
author: Sujata994
ms.author: sunaraya
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/12/2019
LocalizationGroup: Data from databases
ms.openlocfilehash: d78124045767323cca657fa41d4415ca2e929f3d
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73881922"
---
# <a name="edit-sap-variables-in-the-power-bi-service-preview"></a>SAP-muuttujien muokkaus Power BI -palvelussa (esikatselu)

Kun käytössä on SAP Business Warehouse tai SAP HANA ja DirectQuery, raporttien tekijät voivat nyt antaa käyttäjille luvan muokata SAP-muuttujia **Power BI -palvelun** Premium-työtiloissa.

![Muokkaa muuttujia -valintaikkuna](media/service-edit-sap-variables/sap-edit-variables-dialog.png)

Tässä asiakirjassa kuvataan Power BI -muuttujien muokkaamisvaatimukset, tämän esikatselutoiminnon ottaminen käyttöön ja muuttujien muokkaaminen Power BI -palvelussa.

## <a name="requirements-for-sap-edit-variables"></a>SAP-muokkausmuuttujien vaatimukset

SAP-muokkausmuuttujien käyttämiseen on joitakin vaatimuksia. Seuraavassa luettelossa kuvataan nämä vaatimukset.

**Uusi suodatuskokemus vaaditaan** – raportissa on oltava käytössä [uusi suodatuskokemus](power-bi-report-filter.md). Voit ottaa sen käyttöön raportissa seuraavasti Power BI Desktopissa:
- Valitse Power BI Desktopissa **Tiedosto** > **Asetukset ja vaihtoehdot** > **Asetukset**
- Valitse siirtymisruudussa **Nykyinen tiedosto** -kohdassa **Raportin asetukset**.
- Valitse **Suodatuskokemus**-kohdassa **Ota käyttöön päivitetty suodatinruutu**.

**DirectQuery-yhteydet vaaditaan**  – yhteys SAP-tietolähteeseen on muodostettava DirectQueryn avulla. Tuontiyhteyksiä ei tueta.

**Power BI Premium -tilaus vaaditaan** – SAP-muokkausmuuttujat toimivat tällä hetkellä vain Power BI Premium -tilauksissa.

**Kertakirjautuminen on määritettävä** – tämän toiminnon käyttö edellyttää, että kertakirjautuminen (SSO) on määritettävä. Lisätietoja on [kertakirjautumisen (SSO) yleiskatsauksessa](service-gateway-sso-overview.md).

**Uudet yhdyskäytäväbitit vaaditaan** – lataa uusin yhdyskäytävä ja päivitä nykyinen yhdyskäytäväsi. Lisätietoja on [palvelun yhdyskäytävässä](service-gateway-onprem.md).

**Moniulotteisuus vain SAP HANA:llw** – SAP HANA:lle SAP-muokkausmuuttujat toimivat vain moniulotteisissa malleissa. Ne eivät toimi suhteellisissa lähteissä.

**Ei tuettu maakohtaisissa pilvipalveluissa** – Power Query Online ei ole tällä hetkellä käytettävissä maakohtaisissa pilvipalveluissa; tästä syystä tätä ominaisuutta ei tueta maakohtaisissa pilvipalveluissa.

## <a name="how-to-enable-the-feature"></a>Ominaisuuden ottaminen käyttöön

Jotta **SAP-muokkausmuuttujat** voidaan ottaa käyttöön, Power BI Desktop on yhdistettävä SAP HANA- tai SAP BW -tietolähteeseen. Valitse sitten **Tiedosto > Asetukset ja vaihtoehdot > Asetukset** ja valitse vasemmanpuoleisen ruudun Nykyinen tiedosto -osasta **DirectQuery**. Kun valitset tämän, näet oikeanpuoleisessa ruudussa DirectQuery-asetukset ja valintaruudun, jossa voit **antaa käyttäjien muuttaa SAP-muuttujia raportissa (esikatselu)** seuraavan kuvan mukaisesti.

![DirectQuery-asetukset](media/service-edit-sap-variables/sap-preview-setting-in-desktop.png)

## <a name="use-sap-edit-variables-in-power-bi-desktop"></a>SAP-muokkausmuuttujien käyttäminen Power BI Desktopissa

Kun käytät SAP-muokkausmuuttujia Power BI Desktopissa, voit muokata muuttujia valitsemalla Muokkaa muuttujia -linkin valintanauhan **Muokkaa kyselyitä** -valikosta. Tämän jälkeen näyttöön avautuu seuraava valintaikkuna. Tämä ominaisuus on ollut käytettävissä Power BI Desktopissa jo jonkin aikaa. Raportin tekijät voivat valita raportin muuttujat seuraavan valintaikkunan avulla.

![Lisää kohteita](media/service-edit-sap-variables/sap-variables-add-items.png)

## <a name="use-sap-edit-variables-in-the-service"></a>SAP-muokkausmuuttujien käyttäminen palvelussa

Kun raportti on julkaistu Power BI -palvelussa, käyttäjät voivat tarkastella **Muokkaa muuttujia** -linkkiä uudessa suodatinruudussa. Jos julkaiset raportin ensimmäistä kertaa, Muokkaa muuttujia -linkin tuleminen näkyviin voi kestää jopa viisi minuuttia. Jos linkkiä ei näy, tietojoukko on päivitettävä manuaalisesti.
Se onnistuu seuraavasti:

1. Valitse Power BI -palvelussa **Tietojoukot**-välilehti työtilan sisältöluettelosta.

2. Etsi päivitettävä tietojoukko ja valitse **Päivitä**-kuvake.

    ![Muokkaa muuttujia](media/service-edit-sap-variables/sap-edit-variables-link.png)

3. Muokkaa muuttujia -linkin valitseminen tuo näkyviin **Muokkaa muuttujia** -valintaikkunan, jossa käyttäjät voivat ohittaa muuttujia. **Nollaa**-painikkeen valitseminen palauttaa muuttujat alkuperäisiin arvoihin, jotka olivat näkyvissä, kun tämä valintaikkuna avattiin.

    ![Muokkaa muuttujia -valintaikkuna](media/service-edit-sap-variables/sap-edit-variables-dialog.png)

4. **Muokkaa muuttujia** -valintaikkunassa tehdyt muutokset koskevat vain kyseistä käyttäjää (vastaava pysyvyys kuin muissa Power BI:n toiminnoissa). Kun valitaan **Palauta oletukset** seuraavan kuvan mukaisesti, raportti palautetaan takaisin raportin tekijän alkuperäiseen tilaan muuttujat mukaan luettuina.

    ![Palauta oletukset](media/service-edit-sap-variables/reset-to-default.png)

Kun julkaistua raporttia käsitellään Power BI -palvelussa, jossa on käytössä SAP HANA tai SAP BW ja **Muokkaa muuttujia** -toiminto, raportin omistaja voi muuttaa kyseisiä oletusarvoja. Raportin omistaja voi muuttaa muuttujia muokkaustilassa ja tallentaa raportin, jotta näistä asetuksista tulee kyseisen raportin *uudet oletusasetukset*. Kuka tahansa muu käyttäjä, joka käyttää raporttia omistajan tekemien muutosten jälkeen, näkee nämä uudet asetukset oletusasetuksina.

## <a name="issues-and-considerations"></a>Ongelmat ja huomioitavat seikat

Tällä hetkellä SAP-muokkausmuuttujia ei tueta sovelluksissa.

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja SAP HANA:sta, SAP BW:stä ja DirectQuerystä on seuraavissa artikkeleissa:

- [SAP HANA -käyttö Power BI Desktopissa](desktop-sap-hana.md)
- [DirectQuery ja SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)
- [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
- [DirectQueryn käyttäminen Power BI:ssä](desktop-directquery-about.md)