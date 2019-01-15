---
title: Ehdollinen taulukkomuotoilu Power BI Desktopissa
description: Mukautetun muotoilun käyttö taulukoissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/06/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 4b45c6708f2f4c1ec0f8df2a330dcbb683210926
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54292037"
---
# <a name="conditional-formatting-in-tables"></a>Ehdollinen muotoilu taulukoissa 
Taulukoiden ehdollisen muotoilun avulla voit määrittää mukautettuja solujen värejä, jotka perustuvat solujen arvoihin tai muihin arvoihin tai kenttiin. Voit käyttää myös liukuvärejä. Voit myös näyttää solun arvot tietopalkeilla. 

Ehdollisen muotoilun käyttämiseksi valitse alaspäin osoittava nuoli Power BI Desktopin **Visualisoinnit**-ruudun **Kentät**-kohdassa sen **Arvon** vierestä, jota haluat muotoilla (tai napsauta kenttää hiiren kakkospainikkeella). Voit hallita kenttien ehdollista muotoilua ainoastaan **Kenttien** **Arvot**-alueella.

![Ehdollinen muotoilu -valikko](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

Seuraavissa osioissa kuvataan kutakin näistä ehdollisen muotoilun vaihtoehdoista. Yksi tai useampi vaihtoehto voidaan liittää yhteen taulukon sarakkeeseen.

> [!NOTE]
> Taulukkoon käytetty ehdollinen muotoilu ohittaa kaikki ehdollisesti muotoilluissa soluissa käytetyt mukautetut taulukkotyylit.

Jos haluat poistaa ehdollisen muotoilun visualisoinnista, napsauta kenttää uudelleen hiiren kakkospainikkeella, valitse **Poista ehdollinen muotoilu** ja valitse sitten poistettavan muotoilun tyyppi.

![Poista ehdollinen muotoilu -valikko](media/desktop-conditional-table-formatting/table-formatting-1-remove.png)

## <a name="background-color-scales"></a>Taustaväriasteikot

Kun valitset **Ehdollisen muotoilun** ja sitten **Taustaväriasteikot**, seuraava valintaikkuna tulee näyttöön.

![Taustaväriasteikot-valintaikkuna](media/desktop-conditional-table-formatting/table-formatting-1-default-dialog.png)

Voit valita värien perusteena toimivan tietomallin kentän asettamalla **Värien peruste** -määritteen kyseiseen kenttään. Lisäksi voit määrittää valitulle kentälle koostetyypin **Yhteenveto**-arvolla. Väritettävä kenttä on määritetty **Väritettävä**-kentässä, jotta pysyt kärryillä. Voit määrittää ehdollisen muotoilun teksti- ja päivämääräkenttiin. Muista valita muotoilun perustaksi numeerinen arvo.

![Kenttään perustuva väri](media/desktop-conditional-table-formatting/table-formatting-1-apply-color-to.png)

Jos haluat erillisiä väriarvoja valituille alueille, valitse **Väri sääntöjen mukaan**. Jos haluat käyttää väriasteikkoa, jätä **Väri sääntöjen mukaan** valitsematta. 

![Taustaväriasteikot-valintaikkuna](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-dialog.png)

### <a name="color-by-rules"></a>Väri sääntöjen mukaan

Kun valitset **Väri sääntöjen mukaan** -asetuksen, voit antaa yhden tai useamman arvoalueen, joista kukin vastaa valittua väriä.  Kukin arvo alkaa *Jos-arvo* -ehdolla, *ja*-arvoehdolla ja värillä.

![Väri sääntöjen mukaan -arvoalue](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-if-value.png)

Taulukkosolut, joissa kunkin alueen arvot on täytetty annetulla värillä. Seuraavassa kuvassa on kolme sääntöä.

![Väri sääntöjen mukaan -esimerkki](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules.png)

Esimerkkitaulukko näyttää nyt tältä:

![Esimerkkitaulukko, joka sisältää värin sääntöjen mukaan](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-table.png)


### <a name="color-minimum-to-maximum"></a>Värin vähimmäis- ja enimmäisarvo

Voit määrittää *vähimmäis-* ja *enimmäis*arvot ja niiden värit. Jos valitset **Erkautuva**-valinnan, voit määritellä myös valinnaisen *Keski*arvon.

![Erkautuva-painike](media/desktop-conditional-table-formatting/table-formatting-1-diverging.png)

Esimerkkitaulukko näyttää nyt tältä:

![Esimerkkitaulukko, jossa on erkautuvia värejä](media/desktop-conditional-table-formatting/table-formatting-1-diverging-table.png)

## <a name="font-color-scales"></a>Fonttiväriasteikot

Kun valitset **Ehdollisen muotoilun** ja sitten **Fonttiväriasteikot**, seuraava valintaikkuna tulee näyttöön. Tämä valintaikkuna on samantapainen kuin **Taustaväriasteikot**-valintaikkuna, mutta sen kautta voit muuttaa fontin väriä solun taustavärin sijaan.

![Fonttiväriasteikot-valintaikkuna](media/desktop-conditional-table-formatting/table-formatting-2-diverging.png)

Esimerkkitaulukko näyttää nyt tältä:

![Esimerkkitaulukko, jossa on fonttiväriasteikkoja](media/desktop-conditional-table-formatting/table-formatting-2-table.png)

## <a name="data-bars"></a>Tietopalkit

Kun valitset **Ehdollisen muotoilun** ja sitten **Tietopalkit**, seuraava valintaikkuna tulee näyttöön. 

![Tietopalkit-valintaikkuna](media/desktop-conditional-table-formatting/table-formatting-3-default.png)

Oletuksena **Näytä vain palkki** -asetusta ei ole valittu, jolloin taulukkosolu näyttää sekä palkin että todellisen arvon.

![Esimerkkitaulukko, jossa on tietopalkkeja ja arvoja](media/desktop-conditional-table-formatting/table-formatting-3-default-table.png)

Jos **Näytä vain palkki** -asetus on valittu, taulukkosolussa näkyy vain palkki.

![Esimerkkitaulukko, jossa on vain tietopalkkeja](media/desktop-conditional-table-formatting/table-formatting-3-default-table-bars.png)

## <a name="color-formatting-by-field-value"></a>Värin muotoileminen kentän arvon mukaan

Voit käyttää mittayksikköä tai värin määrittävää saraketta joko tekstiarvon tai heksadesimaalikoodin mukaan, ja soveltaa tätä väriä taulukon tai matriisivisualisoinnin fonttiväriin. Voit myös luoda mukautetun logiikan tiettyä kenttää varten, ja antaa tämän logiikan soveltaa haluttua väriä fonttiin tai taustaan.

Esimerkiksi seuraavassa taulukossa on kuhunkin tuotemalliin liittyvä väri. 

![ProductName-kenttä värin nimen kanssa](media/desktop-conditional-table-formatting/conditional-table-formatting_01.png)

Jos haluat muotoilla tätä solua sen kentän arvon mukaan, valitse **Ehdollinen muotoilu** -valintaikkuna napsauttamalla hiiren kakkospainikkeella tämän visualisoinnin *Väri*-saraketta ja valitsemalla valikosta **Taustaväri**. 

![Taustavärin valitseminen valikosta](media/desktop-conditional-table-formatting/conditional-table-formatting_02.png)

Valitse avautuvassa valintaikkunassa **Kentän arvo** avattavasta **Muotoiluperuste**-luetteloalueesta seuraavassa kuvassa esitetyllä tavalla.

![Muotoiluperuste-kentän arvo](media/desktop-conditional-table-formatting/conditional-table-formatting_03.png)

Voit toistaa tämän prosessin fonttivärille ja visualisoinnin tulos on yhtenäinen väri **Väri**-sarakkeessa seuraavassa näytössä esitetyn mukaisesti.

![Muotoiluperuste-kentän arvo](media/desktop-conditional-table-formatting/conditional-table-formatting_04.png)

Voit myös luoda liiketoimintalogiikan perusteella DAX-laskutoimituksen, joka tulostaa eri heksadesimaalikoodit haluamiesi ehtojen mukaan. Tämä on yleensä helpompaa kuin useiden sääntöjen luominen ehdollisen muotoilun valintaikkunassa. Tarkastele *ColorKPI*-kenttää seuraavassa esimerkkikuvassa.

![DAX-laskutoimitukset](media/desktop-conditional-table-formatting/conditional-table-formatting_05.png)

Voit sitten määrittää kenttäarvon **taustavärille** seuraavalla tavalla.

![Kentän värin määrittäminen KPI:n mukaan](media/desktop-conditional-table-formatting/conditional-table-formatting_06.png)

Voit sitten saada seuraavan matriisin kaltaiset tulokset.

![Matriisivisualisointi KPI-arvoon perustuvan värin kanssa](media/desktop-conditional-table-formatting/conditional-table-formatting_07.png)

Voit luoda monia muita variaatioita käyttämällä mielikuvitustasi ja joitakin DAX-laskutoimituksia.

## <a name="next-steps"></a>Seuraavat vaiheet
Katso lisätietoja seuraavasta artikkelista:  

* [Vinkkejä värimuotoiluun Power BI:ssä](visuals/service-tips-and-tricks-for-color-formatting.md)  

