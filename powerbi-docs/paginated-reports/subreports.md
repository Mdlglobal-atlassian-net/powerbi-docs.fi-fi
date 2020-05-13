---
title: Aliraportit Power BI:n sivutetuissa raporteissa
description: Tässä artikkelissa kerrotaan Power BI -palvelun sivutetuissa raporteissa tuetuista tietolähteistä ja siitä, miten yhteys muodostaa yhteyden Microsoft Azuren SQL-tietokannan tietolähteisiin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 04/29/2020
ms.openlocfilehash: 784e3fd3883adb9fc5b773cc730b992135d7ef8b
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83272806"
---
# <a name="subreports-in-power-bi-paginated-reports"></a>Aliraportit Power BI:n sivutetuissa raporteissa

*Aliraportti* on sivutettu raporttikohde, joka näyttää toisen sivutetun raportin pääsivutetun raportin rungon sisällä. Käsitteellisesti raportin aliraportti on samanlainen kuin verkkosivun kehys. Sen avulla voit upottaa raportin raporttiin. Voit käyttää mitä tahansa raporttia aliraporttina. Tallennat aliraporttina näkyvän raportin samassa Premium-työtilassa kuin pääraportin. Voit suunnitella pääraportin välittämään parametreja aliraporttiin. Aliraportti voi toistua tietoalueiden sisällä käyttäen parametria, jolla suodatetaan tietoja kunkin aliraportin esiintymän osalta.  
  
 ![Sivutetun raportin aliraportti](media/subreports/paginated-report-subreport.png "Sivutettujen raporttien aliraportit")  
  
 Tässä kuvassa myyntitilausten pääraportissa näkyvät yhteystiedot tulevat itse asiassa yhteyshenkilöiden aliraportista.  
  
Voit luoda ja muokata sivutettuja raporttimääritysten (.rdl) tiedostoja Power BI:n raportin muodostimessa. Voit ladata SQL Server Reporting Services -palveluun tallennettuja osaraportteja Premium-työtilaan Power BI-palvelussa. Pääraportit ja aliraportit on julkaistava samaan työtilaan. Asenna [Power BI:n raportin muodostin](https://go.microsoft.com/fwlink/?linkid=2086513).
  
## <a name="work-with-report-builder-and-the-power-bi-service"></a>Raportin muodostimen ja Power BI -palvelun käsitteleminen

Power BI -raportin muodostin voi käyttää sivutettuja raportteja tietokoneessasi (eli paikallisissa raporteissa) tai Power BI-palvelun raporteissa.  Kun avaat raportin muodostinta ensimmäistä kertaa, sinua pyydetään kirjautumaan Power BI -tilillesi. Jos näin ei tapahdu, valitse oikeasta yläkulmasta **Kirjaudu sisään**.

:::image type="content" source="media/subreports/report-builder-sign-in.png" alt-text="Kirjautuminen Power BI:iin":::

Kun olet kirjautunut sisään, näet **Power BI Service** -vaihtoehdon Power BI - raportin muodostimessa sekä **Avaa** ja **Tallenna** -asetukset **Tiedosto**-valikossa. Kun valitset **Power BI Service**-vaihtoehdon raportin tallentamista varten, luot reaaliaikaisen yhteyden Power BI -raportin muodostimen ja Power BI -palvelun välille. 

:::image type="content" source="media/subreports/report-builder-subreport-open-service.png" alt-text="Avaaminen Power BI -palvelusta":::

## <a name="save-a-local-report-to-the-power-bi-service"></a>Paikallisen raportin tallentaminen Power BI -palveluun

Ennen kuin voit lisätä aliraportin pääraporttiin, luo ensin kaksi raporttia ja tallenna ne samaan Power BI Premium -työtilaan. 

1. Jos haluat avata aiemmin luodun paikallisen raportin, valitse **Tiedosto**-valikosta **Avaa** > **Tämä tietokone** ja valitse .rdl-tiedosto.  

2. Valitse **Tiedosto**-valikosta **Tallenna nimellä** > **Power BI -palvelu**.  Katso lisätietoja kohdasta [Sivutetun raportin julkaiseminen Power BI -palveluun](paginated-reports-save-to-power-bi-service.md).

    > [!NOTE]
    > Voit myös ladata raportin aloittamalla Power BI -palvelun. Lisätietoja on samassa artikkelissa [Sivutetun raportin julkaiseminen Power BI -palveluun](paginated-reports-save-to-power-bi-service.md).

3. Valitse **Tallenna nimellä** -valintaikkunassa Power BI Premium -työtila, johon voit tallentaa sivutetut raporttisi.  Premium-työtilan nimen vieressä on ![Premium-vinoneliökuvake](media/subreports/report-builder-premium-diamond.png).

    :::image type="content" source="media/subreports/report-builder-subreport-save-as-service.png" alt-text="Tallenna nimellä Power BI -palveluun":::

4. Valitse **Tallenna**.

## <a name="add-a-subreport-to-a-report"></a>Aliraportin lisääminen raporttiin

Nyt kun olet tallentanut molemmat raportit samaan Premium-työtilaan, voit lisätä sellaisen toiseen aliraporttina. Aliraportin voi lisätä kahdella tavalla. 

1. Valitse **Lisää**-valintanauhasta **Aliraportti**-painike tai napsauta hiiren kakkospainikkeella raportin piirtoalustaa ja valitse **Lisää** > **aliraportti**.

    :::image type="content" source="media/subreports/report-builder-insert-subreport.png" alt-text="Aliraportin liittäminen raporttiin":::

    **Aliraportin ominaisuudet** -valintaikkuna avautuu.  

2. Valitse **Selaa**-painike > siirry raporttiin, jota haluat käyttää aliraporttina > määritä aliraportin nimi **Nimi**-tekstiruudussa.

3. Määritä muut ominaisuudet tarvittaessa, mukaan lukien [parametrit](#use-parameters-in-subreports).

## <a name="use-parameters-in-subreports"></a>Parametrien käyttö aliraporteissa  
 Jos haluat siirtää pääraportin parametrit aliraporttiin, määritä raporttiparametri raportissa, jota käytät aliraporttina. Kun sijoitat aliraportin pääraporttiin, voit valita raporttiparametrin ja arvon, joka siirretään pääraportista raporttiparametriin aliraportissa.  
  
> [!NOTE]  
> Aliraportista valitsemasi parametri on *raportti*parametri, ei *kysely*parametri.  
  
 Voit sijoittaa aliraportin raportin pääleipätekstiin tai tietoalueeseen. Jos sijoitat aliraportin tietoalueelle, aliraportti toistuu jokaisessa tietoalueen ryhmän tai rivin esiintymässä. Voit siirtää arvon ryhmästä tai riviltä aliraporttiin. Käytä aliraporttiarvo-ominaisuudessa kenttälauseketta kentälle, joka sisältää aliraporttiparametrille siirrettävät arvot.  
  
 Lisätietoja parametrien ja aliraporttien käsittelemisestä on [Aliraportin ja parametrien lisääminen](https://docs.microsoft.com/sql/reporting-services/report-design/add-a-subreport-and-parameters-report-builder-and-ssrs) SQL Server Reporting Services -ohjeaiheessa.  

## <a name="preview-paginated-reports-in-report-builder"></a>Raportin muodostimessa sivutettujen raporttien esikatselu

Voit esikatsella raportteja raportin muodostimessa.

- Valitse **Aloitus**-valintanauhassa **Suorita**. 

Koska raportin muodostin on suunnittelutyökalu, raportin esikatselu voi näyttää erilaisilta kuin raportin hahmontaminen Power BI-palvelusta.

### <a name="notes-about-previewing"></a>Huomautuksia esikatselusta

- Raportin muodostin ei tallenna raporteissa käytettävien tietolähteiden tunnistetietoja.  Raportin muodostin kysyy kutakin tunnistejoukkoa esikatselun aikana.  
- Jos raportin tietolähteet ovat paikallisia, sinun on määritettävä yhdyskäytävä sen jälkeen, kun raportti on tallennettu Power BI -työtilaan.
- Jos raportin muodostin havaitsee virheen esikatselun aikana, se palauttaa yleisviestin.  Jos virheen korjaaminen on vaikeaa, harkitse raportin hahmontamista Power BI -palvelussa.  

## <a name="considerations"></a>Huomioitavaa

### <a name="maintaining-the-connection"></a>Yhteyksien ylläpito

Raportin muodostin ei pysy yhteydessä Power BI:iin, kun tiedosto suljetaan.  On mahdollista käsitellä paikallista pääraporttia, joka sisältää Power BI -työtilaan tallennettuja aliraportteja. Muista tallentaa pääraportti Power BI -työtilaan ennen raportin sulkemista.  Jos näin ei toimita, saatat saada "not found"-sanoman esikatselun aikana, koska Power BI -palveluun ei ole reaaliaikaista yhteyttä.  Siirry siinä tapauksessa aliraporttiin ja valitse sen ominaisuudet.  Avaa aliraportti uudelleen Power BI -palvelussa.  Tämä muodostaa yhteyden uudelleen, ja kaikkien muiden aliraporttien on oltava kunnossa.

### <a name="renaming-a-subreport"></a>Aliraportin nimeäminen uudelleen

Jos nimeät aliraportin uudelleen työtilassa, sinun on korjattava nimiviittaus pääraportissa. Muussa tapauksessa aliraporttia ei voi hahmontaa. Pääraportti hahmontaa edelleen aliraportin kohteen sisällä olevan virhesanoman kanssa.

## <a name="migrate-large-reports"></a>Suurten raporttien siirtäminen

Jos siirrät suuria raportteja Power BI:lle, harkitse [RdlMigration-työkalun](../guidance/migrate-ssrs-reports-to-power-bi.md)käyttämistä.  RdlMigration-työkalu on päivitetty käsittelemään päällekkäisiä aliraporttien nimiä.  Aliraporttien päällekkäisiä nimiä voi ilmetä, kun kahdella tai useammalla raportilla on sama nimi, mutta ne sijaitsevat eri alikansioissa.  Jos nimiä ei määritetä yksilöllisesti, vain ensimmäinen aliraportti tunnistetaan.

Jos haluat käyttää raportin muodostinta suurten raporttien siirtämiseen, suosittelemme, että käytät ensin aliraportteja. Tallenna jokainen Power BI -työtilaan raporttien päällekkäisten nimien estämiseksi.

## <a name="share-reports-with-subreports"></a>Aliraportteja sisältävien raporttien jakaminen

Kuten olemme todenneet, pääraportin ja-aliraporttien on oltava samassa työtilassa. Muussa tapauksessa aliraporttia ei voi hahmontaa. Kun jaat pääraportin, sinun on jaettava myös aliraportit. Jos jaat pääraportin sovelluksessa, varmista, että sisällytät myös kyseisen sovelluksen aliraportit. Jos jaat pääraportin käyttäjien tai käyttäjäryhmän kanssa suoraan, varmista, että jaat myös kunkin aliraportin samoilla käyttäjä- tai käyttäjäryhmäasetuksilla.
  
## <a name="next-steps"></a>Seuraavat vaiheet

[Aliraporttien vianmääritys Power BI:n sivutetuissa raporteissa](subreports-troubleshoot.md)

[Sivutetun raportin tarkasteleminen Power BI -palvelussa](../consumer/paginated-reports-view-power-bi-service.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
