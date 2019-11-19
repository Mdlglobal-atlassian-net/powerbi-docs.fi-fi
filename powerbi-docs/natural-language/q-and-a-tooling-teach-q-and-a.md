---
title: Opeta Q&A:ta ymmärtämään kysymyksiä ja termejä Power BI:n Q&A:ssa
description: Tietojen tutkiminen Power BI Q&A:n avulla
author: mohaali
manager: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/17/2019
ms.author: mohaali
LocalizationGroup: Ask questions of your datadefintion
ms.openlocfilehash: b6ae234991414f6971a656b43584710bde82dfaa
ms.sourcegitcommit: 26123c6bb24c8174beb390f4e06fb938d31238ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/22/2019
ms.locfileid: "72717579"
---
# <a name="teach-qa-to-understand-questions-and-terms-in-power-bi-qa"></a>Opeta Q&A:ta ymmärtämään kysymyksiä ja termejä Power BI:n Q&A:ssa

Q&A-määrityksen osassa **Opeta Q&A:ta** voit harjoittaa Q&A:ta ymmärtämään luonnollisen kielen kysymyksiä ja termejä, joita ei ole tunnistettu. Aloita lähettämällä kysymys, joka sisältää sanan tai sanoja, joita Q&A ei tunnistanut. Q&A pyytää sinua sitten määrittämään kyseisen termin. Anna joko suodatin tai kentän nimi, joka vastaa sitä, mitä kyseinen sana merkitsee. Q&A tulkitsee sitten alkuperäisen kysymyksen uudelleen. Jos olet tyytyväinen tuloksiin, tallenna ne.

> [!NOTE]
> Opeta Q&A:ta -toiminto tukee vain tuontitilaa. Se ei myöskään vielä tue yhdistämistä paikalliseen tai Azure Analysis Servicesin tietolähteeseen. Tämä rajoitus poistetaan seuraavissa Power BI -julkaisuversioissa.

## <a name="start-to-teach-qa"></a>Aloita Q&A:n opettaminen

1. Valitse Power BI Desktopissa **Mallinnus**-valintanauhassa **Q&A-määritys** > **Opeta Q&A:ta**.

    ![Opeta Q&A:ta -toiminnon synonyymi punainen](media/qna-tooling-teach-synonym-red.png)

2. Kirjoita lause, joka sisältää termin, jota Q&A ei tunnista, ja valitse **Lähetä**.

3. Valitse punaisella alleviivattu sana. 

    Q&A tarjoaa ehdotuksia ja kehottaa sinua antamaan termin oikean määritelmän. 
    
3. Anna määritelmä kohtaan **Määritä termit, joita Q&A ei ymmärtänyt**.

    ![Opeta Q&A:ta -toiminnon synonyymin esikatselu](media/qna-tooling-teach-fixpreview.png)

4. Esikatsele päivitettyä visualisointia valitsemalla **Tallenna**.

5. Anna seuraava kysymys tai sulje toiminto valitsemalla **X**.

Raporttisi käyttäjät eivät näe tätä muutosta, ennen kuin julkaiset raportin uudelleen palvelussa.

## <a name="define-nouns-and-adjectives"></a>Substantiivien ja adjektiivien määrittäminen

Voit opettaa Q&A:lle kahdentyyppisiä termejä:

- Substantiivit
- Adjektiivit

### <a name="define-a-noun-synonym"></a>Määritä substantiivin synonyymi

Kun käsittelet tietoja, sinulla voi usein olla kenttien nimiä, joihin voisi viitata myös vaihtoehtoisilla nimillä. Esimerkki tällaisesta nimestä on ”Myynti”. Myyntiin voidaan viitata muillakin sanoilla tai ilmauksilla, kuten ”tuotto”. Jos sarakkeen nimi on "Myynti" ja raportin käyttäjät kirjoittavat ”tuotto”, Q&A ei välttämättä osaa valita oikeaa saraketta vastatakseen kysymykseen. Tässä tapauksessa haluat kertoa Q&A:lle, että ”myynti” ja ”tuotto” viittaavat samaan asiaan.

Q&A tunnistaa automaattisesti, kun tunnistamaton sana on substantiivi, käyttäen Microsoft Officen tietoja. Jos Q&A havaitsee substantiivin, näet seuraavan kehotteen:

- <your term> **viittaa kohteeseen** 

Täytä ruutuun termisi tiedot.

![Opeta Q&A:ta -toiminnon synonyymin kehote](media/qna-tooling-synonym-prompt.png)

Jos annat synonyymiksi jotain muuta kuin tietomallin kentän, saatat saada epätoivottuja tuloksia.

### <a name="define-an-adjective-filter-condition"></a>Adjektiivin suodatusehtojen määrittäminen

Joskus saatat haluta määrittää termejä, jotka toimivat pohjana olevien tietojen ehtona. Esimerkki tällaisesta on ”Loistavat julkaisijat”. ”Loistava” voi olla ehto, joka valitsee vain julkaisijoita, jotka ovat julkaisseet tietyn määrän tuotteita. Q&A yrittää havaita adjektiiveja ja näyttää eri kehotteen:

- <field name>, **joilla on**  

Täytä ruutuun ehto.

![Opeta Q&A:ta -toiminnon synonyymin kehote](media/qna-tooling-adjectives.png)

Esimerkkejä ehdoista, joita voit määrittää:

- ”Maa”, joka on ”USA”
- ”Maa”, joka ei ole ”USA”
- ”Paino” > 2 000
- ”Paino = 2 000
- ”Paino” < 2 000

Voit määrittää vain yhden ehdon työkalujen kautta. Jos haluat määrittää monimutkaisempia ehtoja, luo DAX-toiminnolla laskettu sarake ja luo sitten yksi ehto tälle lasketulle sarakkeelle työkalujen avulla. Mittareita ei tueta. Käytä sen sijaan laskettuja sarakkeita.

## <a name="manage-terms"></a>Hallitse termejä

Kun olet antanut määritelmät, voit palata katsomaan kaikkia tekemiäsi korjauksia ja halutessasi muokata tai poistaa niitä. 

1. Siirry**Q&A-määritys**-valikossa osioon **Hallitse termejä**.

2. Poista termit, joita et enää halua. Tällä hetkellä et voi muokata termejä. Jos haluat määrittää termin uudelleen, poista se ja määritä se uudelleen.

    ![Q&A:n termien hallinta](media/qna-manage-terms.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Luonnollisen kielen moduulin parantamiseen on olemassa joitain parhaita käytäntöjä. Katso lisätietoja seuraavasta artikkelista:

* [Q&A:n parhaat käytännöt](q-and-a-best-practices.md)
