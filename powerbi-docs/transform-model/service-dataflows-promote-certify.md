---
title: Tietovoiden ylentäminen tai sertifiointi (esiversio)
description: Lue ohjeet tietovoiden ylentämiseen tai sertifiointiin.
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/17/2020
ms.author: painbar
LocalizationGroup: Share your work
ms.openlocfilehash: 7634711e8d26c4f265752427c5086e0901b210d5
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "81268876"
---
# <a name="promote-or-certify-dataflows-preview"></a>Tietovoiden ylentäminen tai sertifiointi (esiversio)

Power BI tarjoaa kaksi tapaa, joilla voit kasvattaa arvokkaiden ja laadukkaiden tietovoiden näkyvyyttä: **ylentämisen** ja **sertifioinnin**.

* **Ylentäminen**: Ylentämisen avulla käyttäjät voivat tuoda esiin tietovoita, jotka ovat heidän mielestään arvokkaita ja hyödyllisiä muillekin. Tällä tavalla ylentäminen tukee tietovoiden leviämistä yhteistyön kautta organisaatioissa. Kuka tahansa tietovuon omistaja tai kuka tahansa työtilan jäsen, jolla on kirjoitusoikeudet työtilaan, jossa tietovuo sijaitsee, voi ylentää tietovuon, kun se on hänen mielestään tarpeeksi hyvä jaettavaksi.

* **Sertifiointi**: Sertifiointi tarkoittaa sitä, että valtuutettu tarkistaja tarkistaa tietovuon ja takaa, että se on luotettava tietolähde, joka on valmis käytettäväksi organisaatiossa. Power BI -järjestelmänvalvojan määrittämät tarkistajat päättävät, mitkä tietovuot sertifioidaan. Jos käyttäjä on sitä mieltä, että tietty tietovuo tulisi sertifioida, mutta hänellä ei ole oikeutta siihen, hänen tulisi ottaa yhteyttä vuokraajan järjestelmänvalvojaan.

  Tietovoiden sertifiointi on mahdollista vain, jos [Power BI -vuokraajan järjestelmänvalvoja on ottanut sen käyttöön](../admin/service-admin-setup-certification.md).

Tietovuon ylentämistä tai sertifiointia kutsutaan *tukemiseksi*. Power BI -raporttien tekijöillä on usein paljon erilaisia tietovoita valittavissaan, joten tukeminen auttaa heitä löytämään niistä luotettavat ja parhaimmat.

Tuetut tietovuot merkitään selkeästi monissa paikoissa Power BI:ssä, minkä ansiosta raporttien tekijät löytävät ne helposti etsiessään luotettavia tietoja. Tämän ansiosta järjestelmänvalvojat ja raporttien tekijät voivat myös seurata niiden käyttöä organisaatiossa.

Alla olevasta kuvasta näet, miten ylennetyt ja sertifioidut tietovuot tunnistetaan helposti Power Queryssa.

![Tuetut tietovuot korostettuna Power Queryssa](media/service-dataflows-promote-certify/powerbi-dataflow-endorsement-power-query.png)

Tämän artikkelin sisältö
* Esittelemme tietovuon ylentämistä (sen voi tehdä tietovuon omistaja tai kuka tahansa käyttäjä, jolla on jäsenoikeudet työtilaan, jossa tietovuo sijaitsee).
* Esittelemme tietovuon sertifioinnin (sen voi tehdä vuokraajan järjestelmänvalvojan määrittämä valtuutettu tietovoiden sertifioija).

Jos haluat lisätietoja tietovuon sertifioinnin määrittämisestä (vuokraajan järjestelmänvalvoja), lue ohjeartikkelin [Tietojoukkojen ja tietovoiden sertifioinnin määrittäminen](../admin/service-admin-setup-certification.md).


## <a name="promote-a-dataflow"></a>Tietojoukon ylentäminen

Jos haluat ylentää tietovuon, sinulla täytyy olla kirjoitusoikeudet työtilaan, jossa haluamasi tietovuo sijaitsee.

1. Siirry työtilassa tietojoukkojen luetteloon.
 
1. Valitse haluamasi tietovuon kohdalla **Lisää asetuksia** (...) ja valitse sitten **Asetukset**.

    ![Valitse kolme pistettä tietovuon kohdalla](media/service-dataflows-promote-certify/power-bi-dataflow-settings.png)

1. Laajenna tukemisen kohta ja valitse **Ylennetty**.

    ![Valitse Ylennetty > Käytä](media/service-dataflows-promote-certify/power-bi-dataflow-promoted-endorsement.png)

1. Valitse **Käytä**.

## <a name="certify-a-dataflow"></a>Tietovuon sertifiointi

Tämä osio on tarkoitettu käyttäjille, joille vuokraajan järjestelmänvalvoja on antanut oikeuden sertifioida tietovoita. Tietovoiden sertifiointi on vastuullinen tehtävä. Tässä osiossa käydään läpi sertifiointiprosessi.

1. Hanki kirjoitusoikeudet työtilaan, jossa sertifioitava tietovuo sijaitsee. Voit pyytää niitä tietovuon omistajalta tai keneltä tahansa, jolla on järjestelmänvalvojan oikeudet työtilaan. 

1. Tarkista tietovuo huolellisesti ja päätä, ansaitseeko se sertifioinnin.

1. Jos päätät sertifioida tietovuon, siirry työtilaan, jossa se sijaitsee.
 
1. Etsi haluamasi tietovuo ja valitse sen kohdalla **Lisää asetuksia** (...) ja sitten **Asetukset**.

    ![Valitse kolme pistettä tietojoukon tai tietovuon kohdalla](media/service-dataflows-promote-certify/power-bi-dataflow-settings.png)

1. Laajenna tukemisen kohta ja valitse **Sertifioitu**. 

    ![Napsauta lisätietolinkkiä](media/service-dataflows-promote-certify/service-certify-datasets-dataflows.png)

2. Valitse **Käytä**.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Tietojoukkojen ja tietovoiden sertifioinnin määrittäminen](../admin/service-admin-setup-certification.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)