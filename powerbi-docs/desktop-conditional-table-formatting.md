---
title: Ehdollinen taulukkomuotoilu Power BI Desktopissa
description: Mukautetun muotoilun käyttö taulukoissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 70aa61d6a02bea1b7058a68b20718008ace1b8c8
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34480884"
---
# <a name="conditional-formatting-in-tables"></a>Ehdollinen muotoilu taulukoissa 
Taulukoiden ehdollisen muotoilun avulla voit määrittää mukautettuja solujen värejä, jotka perustuvat solujen arvoihin tai muihin arvoihin tai kenttiin. Voit käyttää myös liukuvärejä. Voit myös näyttää solun arvot tietopalkeilla. 

Ehdollisen muotoilun käyttämiseksi valitse alaspäin osoittava nuoli Power BI Desktopin **Visualisoinnit**-ruudun **Kentät**-kohdassa sen **Arvon** vierestä, jota haluat muotoilla (tai napsauta kenttää hiiren kakkospainikkeella). Voit hallita kenttien ehdollista muotoilua ainoastaan **Kenttien** **Arvot**-alueella.

![Ehdollinen muotoilu -valikko](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

Seuraavissa osissa kuvataan kukin kolmesta ehdollisen muotoilun vaihtoehdoista. Yksi tai useampi vaihtoehto voidaan liittää yhteen taulukon sarakkeeseen.

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
