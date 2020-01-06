---
title: Kapasiteettien määrittäminen ja hallinta Power BI Premiumissa
description: Lue, miten voit hallita Power BI Premiumia ja sallia sisällön käytön koko organisaatiossa.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/17/2019
LocalizationGroup: Premium
ms.openlocfilehash: e60aed5b538eab3b630f42a665d96256cc07879c
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "74700092"
---
# <a name="configure-and-manage-capacities-in-power-bi-premium"></a>Kapasiteettien määrittäminen ja hallinta Power BI Premiumissa

Power BI Premiumin hallinta edellyttää Premium-kapasiteettien luontia, hallintaa ja seurantaa. Tässä artikkelissa on vaiheittaiset ohjeet. Yleiskatsaus kapasiteetteihin on kohdassa [Premium-kapasiteettien hallinta](service-premium-capacity-manage.md).

Opi, miten voit hallita Power BI Premiumin ja Power BI Embeddedin kapasiteetteja, jotka tarjoavat sisällöllesi erillisiä resursseja.

![Power BI:n kapasiteettiasetukset-näyttö](media/service-admin-premium-manage/premium-capacity-management.png)

*Kapasiteetti* on Power BI Premium- ja Power BI Embedded -tuotteiden ytimessä. Se on ainoastaan sinun organisaatiosi käyttöön varattujen resurssien joukko. Varatun kapasiteetin avulla voit julkaista koontinäyttöjä, raportteja ja tietojoukkoja organisaatiosi käyttäjille ilman, että sinun tarvitsee ostaa käyttäjäkohtaisia käyttöoikeuksia heille. Se tarjoaa myös kapasiteettiin tallennetun sisällön luotettavan, tasalaatuisen suorituskyvyn. Lisätietoja on ohjeartikkelissa [Mikä Power BI Premium on ?](service-premium.md).

## <a name="manage-capacity"></a>Hallitse kapasiteettia

Kun olet ostanut kapasiteettisolmuja Office 365:ssä, sinun tulee määrittää kapasiteetti Power BI -hallintaportaalissa. Voit hallita Power BI Premium -kapasiteetteja portaalin **Kapasiteettiasetukset**-osiossa.

![Kapasiteettiasetukset hallintaportaalissa](media/service-admin-premium-manage/admin-portal-premium.png)

Voit hallita kapasiteettia valitsemalla kapasiteetin nimen. Tämä siirtää sinut kapasiteetin hallintanäyttöön.

![Siirry kapasiteetin määritysnäyttöön valitsemalla kapasiteetin nimi](media/service-admin-premium-manage/capacity-assignment.png)

Jos kapasiteetille ei ole määritetty työtiloja, näyttöön tulee viesti, jossa kerrotaan [työtilan määrittämisestä kapasiteetille](#assign-a-workspace-to-a-capacity).

### <a name="setting-up-a-new-capacity-power-bi-premium"></a>Uuden kapasiteetin määrittäminen (Power BI Premium)

Hallintaportaalissa näet, kuinka monta *näennäisydintä* (v-ydintä) olet käyttänyt ja montako ydintä sinulla on vielä jäljellä. V-ytimien kokonaismäärä määräytyy ostamasi Premium-SKU:iden perusteella. Esimerkiksi ostamalla P3:n ja P2:n saat käyttöösi 48 ydintä – 32 P3:sta ja 16 P2:sta.

![Power BI Premiumin käytetyt ja käytettävissä olevat v-ytimet](media/service-admin-premium-manage/admin-portal-v-cores.png)

Jos sinulla on käytettävissäsi v-ytimiä, määritä uusi kapasiteetti noudattamalla seuraavia ohjeita.

1. Valitse **Määritä uusi kapasiteetti**.

1. Anna kapasiteetillesi nimi.

1. Määritä tämän kapasiteetin järjestelmänvalvoja.

1. Valitse kapasiteetin koko. Käytettävissä olevat vaihtoehdot riippuvat siitä, montako v-ydintä käytettävissäsi on. Et voi valita vaihtoehtoa, joka on suurempi kuin käytettävissäsi oleva määrä.

    ![Käytettävissä olevat Premium-kapasiteettien koot](media/service-admin-premium-manage/premium-capacity-size.png)

1. Valitse **Määrittäminen**.

    ![Määritä uusi kapasiteetti](media/service-admin-premium-manage/set-up-capacity.png)

Tämän jälkeen kapasiteetin järjestelmänvalvojat sekä Power BI -järjestelmänvalvojat ja Office 365:n yleiset järjestelmänvalvojat näkevät kapasiteetin hallintaportaalissa.

### <a name="capacity-settings"></a>Kapasiteettiasetukset

1. Valitse Premium-kapasiteetin hallintaruudun **Toiminnot**-kohdassa oleva **hammaspyöräkuvake** tarkastellaksesi ja päivittääksesi asetuksia. 

    ![Kapasiteetin toiminnot kapasiteetin hallinnan alueella](media/service-admin-premium-manage/capacity-actions.png)

1. Voit tarkastella palvelun järjestelmänvalvojia, kapasiteetin SKU:ta/kokoa ja kapasiteetin sijaintia.

    ![Kapasiteettiasetukset](media/service-admin-premium-manage/capacity-settings.png)

1. Voit myös nimetä kapasiteetin uudelleen tai poistaa kapasiteetin.

    ![Kapasiteettiasetusten poisto- ja käyttöpainikkeet Power BI Premiumissa](media/service-admin-premium-manage/capacity-settings-delete.png)

> [!NOTE]
> Power BI Embeddedin kapasiteettiasetuksia hallitaan Microsoft Azure -portaalista.

### <a name="change-capacity-size"></a>Muuta kapasiteetin kokoa

Power BI -järjestelmänvalvojat ja Office 365:n yleiset järjestelmänvalvojat voivat muuttaa Power BI Premium -kapasiteetteja. Tämä vaihtoehto ei näy kapasiteetin järjestelmänvalvojille, jotka eivät ole Power BI -järjestelmänvalvojia tai Office 365:n yleisiä järjestelmänvalvojia.

1. Valitse **Muuta kapasiteetin kokoa**.

    ![Power BI Premium -kapasiteetin koon muuttaminen](media/service-admin-premium-manage/change-capacity-size.png)

1. **Muuta kapasiteetin kokoa** -näytön avulla voit suurentaa tai pienentää kapasiteettia.

    ![Avattava Power BI Premium -kapasiteetin koon muuttamisvalikko](media/service-admin-premium-manage/change-capacity-size2.png)

    Järjestelmänvalvojat voivat myös luoda solmuja, muuttaa niiden kokoa ja poistaa niitä niin kauan, kuin käytettävissä on riittävästi v-ytimiä.

    P-version SKU:ita ei voi päivittää EM-version SKU:iksi. Saat lisätietoja viemällä hiiren osoittimen käytöstä poistettujen asetusten päälle.

### <a name="manage-user-permissions"></a>Käyttäjien käyttöoikeuksien hallinta

Voit määrittää lisää kapasiteetin järjestelmänvalvojia sekä määrittää käyttäjät, joilla on *kapasiteetin määrittämisen* käyttöoikeudet. Käyttäjä, jolla on määrittämisen käyttöoikeudet, voi määrittää kapasiteettiin työtilan, jonka järjestelmänvalvoja hän on. Hän voi myös määrittää *Oman työtilansa*  kapasiteettiin. Käyttäjä, jolla on määrittämisen käyttöoikeudet, ei voi käyttää hallintaportaalia.

> [!NOTE]
> Power BI Embeddedin kapasiteetin järjestelmänvalvojat määritetään Microsoft Azure -portaalissa.

Laajenna **Käyttäjien käyttöoikeudet** -kohdassa oleva **Käyttäjät, joilla on määrityskäyttöoikeudet** -vaihtoehto ja lisää sitten haluamasi käyttäjät tai ryhmät.

![Kapasiteetin käyttäjän käyttöoikeudet](media/service-admin-premium-manage/capacity-user-permissions2.png)

## <a name="assign-a-workspace-to-a-capacity"></a>Työtilan määrittäminen kapasiteettiin

Kapasiteettiin voi määrittää työtilan kahdella tavalla: joko hallintaportaalin tai työtilan kautta.

### <a name="assign-from-the-admin-portal"></a>Hallintaportaalin kautta määrittäminen

Kapasiteetin järjestelmänvalvojat sekä Power BI -järjestelmänvalvojat ja Office 365:n yleiset järjestelmänvalvojat voivat joukkomäärittää työtiloja hallintaportaalin Premium-kapasiteetin hallintaosiosta. Kun hallitset kapasiteettia, näkyviin tulee **Työtilat**-osa, jonka avulla voit määrittää työtiloja.

![Työtilan määritysalue kapasiteetin hallinnassa](media/service-admin-premium-manage/capacity-manage-workspaces.png)

1. Valitse **Määritä työtilat**. Tämä vaihtoehto on käytettävissä useissa paikoissa.

1. Valitse haluamasi vaihtoehto **Käytä seuraavalle kohteelle** -asetukselle.

    ![Määritä työtilat](media/service-admin-premium-manage/assign-workspaces.png)

   | Valinta | Kuvaus |
   | --- | --- |
   | **Työtilat käyttäjien mukaan** | Kun määrität työtiloja käyttäjän tai ryhmän mukaan, kaikki kyseisten käyttäjien omistamat työtilat määritetään Premium-kapasiteettiin, mukaan lukien käyttäjän oma työtila. Kyseiset käyttäjät saavat automaattisesti työtilan määrittämisen käyttöoikeudet.<br>Tämä sisältää työtilat, jotka on jo määritetty eri kapasiteettiin. |
   | **Määritetyt työtilat** | Syötä sen työtilan nimi, joka tullaan määrittämään valitulle kapasiteetille. |
   | **Koko organisaation työtilat** | Koko organisaation työtilojen määrittäminen Premium-kapasiteettiin määrittää organisaatiosi kaikki työtilat ja Omat työtilat tähän Premium-kapasiteettiin. Lisäksi kaikki nykyiset ja tulevat käyttäjät voivat määrittää yksittäisiä työtiloja uudelleen tähän kapasiteettiin. |
   | | |

1. Valitse **Käytä**.

### <a name="assign-from-workspace-settings"></a>Määrittäminen työtilan asetuksien kautta

Voit myös määrittää työtilan Premium-kapasiteettiin kyseisen työtilan asetuksista. Jos haluat siirtää työtilan kapasiteettiin, sinulla on oltava kyseisen työtilan järjestelmänvalvojan oikeudet ja kyseisen kapasiteetin määrittämisen käyttöoikeudet. Huomaa, että työtilan järjestelmänvalvojat voivat aina poistaa työtilan Premium-kapasiteetista.

1. Muokkaa työtilaa valitsemalla kolme pistettä **(. . .)** ja valitsemalla sitten **Muokkaa työtilaa**.

    ![Muokkaa työtilaa kontekstivalikosta](media/service-admin-premium-manage/edit-app-workspace.png)

1. Laajenna **Lisäasetukset** **Muokkaa työtilaa** -osiosta.

1. Valitse kapasiteetti, johon haluat määrittää tämän työtilan.

    ![Kapasiteetin valinnan avattava valikko](media/service-admin-premium-manage/app-workspace-advanced.png)

1. Valitse **Tallenna**.

Tallentamisen jälkeen työtila ja kaikki sen sisältö siirretään Premium-kapasiteettiin. Tämä ei häiritse niiden käyttöä.

## <a name="power-bi-report-server-product-key"></a>Power BI -raporttipalvelimen tuoteavain

Power BI -raporttipalvelimen tuoteavain on saatavilla Power BI -hallintaportaalin **Kapasiteettiasetukset**-välilehdellä. Tämä on käytettävissä vain Yleisille järjestelmänvalvojille ja käyttäjille, joille on määritetty Power BI -palvelun järjestelmänvalvojan rooli, jos olet ostanut Power BI Premium -SKU:n.

![Power BI -raporttipalvelimen avain kapasiteettiasetuksissa](media/service-admin-premium-manage/pbirs-product-key.png)

Voit avata tuoteavaimen sisältävän valintaikkunan valitsemalla **Power BI -raporttipalvelimen avain** -kohdan. Voit kopioida sen ja käyttää sitä asennuksessa.

![Power BI -raporttipalvelimen tuoteavain](media/service-admin-premium-manage/pbirs-product-key-dialog.png)

Katso lisätietoja artikkelista [Power BI -raporttipalvelimen asentaminen](report-server/install-report-server.md).

## <a name="next-steps"></a>Seuraavat vaiheet

[Premium-kapasiteettien hallinta](service-premium-capacity-manage.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
