---
title: Tietolähteen hallinta - Analysis Services
description: Paikallisen yhdyskäytävän ja kyseiseen yhdyskäytävään kuuluvien tietolähteiden hallinta. Tämä koskee Analysis Services -palveluita sekä monidimensioisessa että taulukkotilassa.
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: arthii
LocalizationGroup: Gateways
ms.openlocfilehash: 2c71f26949f19ed1beb29a162c18dc36ed689c21
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565342"
---
# <a name="manage-your-data-source---analysis-services"></a>Tietolähteen hallinta - Analysis Services

[!INCLUDE [gateway-rewrite](../includes/gateway-rewrite.md)]

Kun [paikallinen tietoyhdyskäytävä on asennettu](/data-integration/gateway/service-gateway-install), sinun on [lisättävä tietolähteitä](service-gateway-data-sources.md#add-a-data-source), joita voidaan käyttää kyseisen yhdyskäytävän kanssa. Tässä artikkelissa perehdytään siihen, miten käsitellään yhdyskäytäviä ja SQL Server Analysis Services (SSAS) -tietolähteitä, joita käytetään joko ajoitetussa päivityksessä tai reaaliaikaisissa yhteyksissä.

Jos haluat lisätietoja reaaliaikaisen yhteyden määrittämisestä Analysis Servicesiin, [katso tämä video.](https://www.youtube.com/watch?v=GPf0YS-Xbyo&feature=youtu.be)

> [!NOTE]
> Jos sinulla on Analysis Services -tietolähde, sinun on asennettava yhdyskäytävä sellaisessa tietokoneessa, joka on liitetty samaan toimialuepuuryhmään tai toimialueeseen kuin Analysis Services -palvelin.

## <a name="add-a-data-source"></a>Tietolähteen lisääminen

Lisätietoja tietolähteen lisäämisestä on artikkelissa [Tietolähteen lisääminen](service-gateway-data-sources.md#add-a-data-source). Valitse **tietolähteen tyypiksi** **Analysis Services**, jos olet muodostamassa yhteyttä monidimensioiseen tai taulukkomuotoiseen palvelimeen.

![Analysis Services -tietolähteen lisääminen](media/service-gateway-enterprise-manage-ssas/datasourcesettings2-ssas.png)

Täytä sitten tietolähteen tiedot, jotka sisältävät **palvelimen** ja **tietokannan**. Yhdyskäytävä käyttää antamaasi **käyttäjänimeä** ja **salasanaa** muodostaessaan yhteyden Analysis Services -esiintymään.

> [!NOTE]
> Käyttämälläsi Windows-tilillä on oltava palvelimen järjestelmänvalvojan oikeudet esiintymään, johon olet muodostamassa yhteyttä. Jos tämän tilin salasanalle on määritetty vanhentumisaika, käyttäjät saattavat kohdata yhteysvirheen, jos salasanaa ei päivitetä tietolähteessä. Lisätietoja tunnistetietojen tallentamisesta on artikkelissa [Salattu tunnistetietojen tallentaminen pilvipalveluun](service-gateway-data-sources.md#store-encrypted-credentials-in-the-cloud).

![Tietolähdeasetusten täyttäminen](media/service-gateway-enterprise-manage-ssas/datasourcesettings3-ssas.png)

Kun kaikki kohdat on täytetty, valitse **Lisää.** Voit nyt käyttää tätä tietolähdettä ajoitettuihin päivityksiin tai reaaliaikaisiin yhteyksiin paikallisessa Analysis Services -esiintymässä. *Yhteyden muodostaminen onnistui* -teksti tulee näkyviin, jos yhteys muodostettiin onnistuneesti.

![Yhteyden tilan näyttäminen](media/service-gateway-enterprise-manage-ssas/datasourcesettings4.png)

### <a name="advanced-settings"></a>Lisäasetukset

Vaihtoehtoisesti voit määrittää tietolähteellesi yksityisyystason. Tällä asetuksella hallinnoidaan sitä, miten tietoja voidaan yhdistää. Sitä käytetään vain ajoitetussa päivityksessä. Tietosuojatason asetus ei koske reaaliaikaisia yhteyksiä. Lisätietoja tietolähteen yksityisyystasoista on artikkelissa [Yksityisyystasot (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Yksityisyystason määrittäminen](media/service-gateway-enterprise-manage-ssas/datasourcesettings9.png)

## <a name="user-names-with-analysis-services"></a>Käyttäjänimet ja Analysis Services

<iframe width="560" height="315" src="https://www.youtube.com/embed/Qb5EEjkHoLg" frameborder="0" allowfullscreen></iframe>

Aina, kun käyttäjä on vuorovaikutuksessa Analysis Servicesiin yhdistetyn raportin kanssa, käytössä oleva käyttäjänimi välitetään yhdyskäytävään ja sitten paikalliseen Analysis Services -palvelimeen. Analysis Servicesiin välitetään käyttäjätietona Power BI:hin kirjautumisessa käytetty sähköpostiosoite. Yhteys välittää sen [EffectiveUserName](/analysis-services/instances/connection-string-properties-analysis-services#bkmk_auth)-ominaisuutena. 

Tämän sähköpostiosoitteen on vastattava paikallisen Active Directory -toimialueeseen määritettyä täydellistä käyttäjätunnusta (UPN). Täydellinen käyttäjätunnus on Active Directory -tilin ominaisuus. Windows-tilin on oltava käytössä Analysis Services -roolissa. Kirjautuminen ei onnistu, jos Active Directorysta ei löydy vastaavuutta. Lisätietoja Active Directorystä ja käyttäjien nimeämisestä on kohdassa [Käyttäjän nimeämisen määritteet](/windows/win32/ad/naming-properties).

Voit myös [liittää Power BI -kirjautumisnimen paikallisen hakemiston täydelliseen käyttäjätunnukseen](service-gateway-enterprise-manage-ssas.md#map-user-names-for-analysis-services-data-sources).

## <a name="map-user-names-for-analysis-services-data-sources"></a>Käyttäjänimien yhdistäminen Analysis Services -tietolähteitä varten

<iframe width="560" height="315" src="https://www.youtube.com/embed/eATPS-c7YRU" frameborder="0" allowfullscreen></iframe>

Power BI mahdollistaa käyttäjänimien yhdistämisen Analysis Services -tietolähteitä varten. Voit määrittää sääntöjä, joiden avulla Power BI:n kautta kirjautunut käyttäjänimi yhdistetään Analysis Services -yhteydellä EffectiveUserNamelle välitettyyn nimeen. Käyttäjänimien yhdistämistoiminto on kätevä tapa kiertää ongelma, jos Azure Active Directory (Azure AD) -käyttäjänimesi ei vastaa paikallisen Active Directoryn täydellistä käyttäjätunnusta. Jos sähköpostiosoite on esimerkiksi nancy@contoso.onmicrsoft.com, sen voi yhdistää käyttäjänimeen nancy@contoso.com, ja tämä arvo välitetään yhdyskäytävään.

Voit liittää Analysis Services -palveluissa käyttämiäsi käyttäjänimiä kahdella eri tavalla:

* Manuaalinen käyttäjänimen uudelleenliittäminen
* Paikallisen Active Directory -ominaisuuden valinta täydellisten Azure AD -käyttäjänimien uudelleenyhdistämiseksi Active Directory -käyttäjiin (Active Directory -valinnan liittäminen)

Manuaalinen liittäminen on mahdollista toisella lähestymistavalla, mutta se vie paljon aikaa ja sen ylläpito on vaikeaa. Se on erityisen vaikeaa silloin, kun kuvioiden vastaavuus ei riitä. Esimerkiksi kun Azure AD- ja paikallisen Active Directoryn toimialuenimet eroavat toisistaan tai kun käyttäjätilien nimet ovat erilaiset Azure AD:n ja Active Directoryn välillä. Tämän vuoksi manuaalista liittämistä toisella menetelmällä ei suositella.

Menetelmät on kuvattu järjestyksessä kahdessa seuraavassa osassa.

### <a name="manual-user-name-remapping"></a>Manuaalinen käyttäjänimen uudelleenliittäminen

Voit määrittää UPN-säännöt Analysis Services -tietolähteille. Mukautetuista säännöistä on apua, jos Power BI -palvelun kirjautumisnimet eivät vastaa paikallisen hakemistosi täydellisiä käyttäjätunnuksia. Jos kirjaudut esimerkiksi Power BI:hin tunnuksella john@contoso.com, mutta paikallisen hakemiston täydellinen käyttäjänimi on john@contoso.local, voit määrittää liittämissäännön, joka john@contoso.local välitetään Analysis Servicesille.

Voit siirtyä UPN-liittämisnäyttöön seuraavasti.

1. Valitse hammaspyöräkuvake ja valitse **Yhdyskäytävien hallinta**.
2. Laajenna yhdyskäytävä, joka sisältää Analysis Services -tietolähteen. Jos et ole luonut Analysis Services -tietolähdettä, voit tehdä sen tässä vaiheessa.
3. Valitse tietolähde ja valitse sitten **Käyttäjät**-välilehti.
4. Valitse **Käyttäjänimien liittäminen**.

    ![UPN-liittämisnäyttö](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names_02.png)

Näyttöön tulee vaihtoehtoja sääntöjen lisäämiseksi ja testaamiseksi tietylle käyttäjälle.

> [!NOTE]
> Saatat vahingossa muuttaa käyttäjää, jolle muutoksia ei ollut tarkoitus tehdä. Jos esimerkiksi **Korvaa (alkuperäinen arvo)** on contoso.com ja **Korvaava (uusi nimi)** on @contoso.local, kaikki käyttäjät, joiden kirjautumisnimi sisältää @contoso.com, korvataan arvolla @contoso.local. Jos **Korvaa (alkuperäinen nimi)** on dave@contoso.com ja **Korvaava (uusi nimi)** on dave@contoso.local, käyttäjä, jonka kirjautumistunnus on v-dave@contoso.com, lähetetään nimellä v-dave@contoso.local.

### <a name="active-directory-lookup-mapping"></a>Active Directory -valinnan liittäminen

Voit suorittaa paikallisen Active Directory -ominaisuuksien valinnan yhdistääksesi uudelleen täydelliset Azure AD -käyttäjätunnukset täydelliset Active Directory -käyttäjiin tämän osan ohjeiden avulla. Katsotaan aluksi, miten tämä toimii.

Power BI -palvelussa tapahtuu seuraavaa:

* Jokaisen Power BI Azure AD -käyttäjän paikalliselle SSAS-palvelimelle lähettämän kyselyn mukana toimitetaan UPN-merkkijono, kuten:      firstName.lastName@contoso.com

> [!NOTE]
> Power BI -tietolähteessä määriteltyjä manuaalisia UPN-käyttäjäliitoksia sovelletaan *ennen* käyttäjänimen merkkijonon lähettämistä paikalliseen tietoyhdyskäytävään.

Toimi mukautettuja käyttäjän yhdistämismäärityksiä sisältävän paikallisen tietoyhdyskäytävän kanssa seuraavasti.

1. Etsi Active Directory, jossa haku suoritetaan. Voit käyttää automaattista tai määritettävissä olevaa.
2. Etsi Active Directory -henkilön määrite, kuten sähköposti, Power BI -palvelusta. Määrite perustuu saapuvaan UPN-merkkijonoon, kuten firstName.lastName@contoso.com.
3. Jos Active Directory -haku epäonnistuu, se yrittää käyttää välitettyä täydellistä käyttäjätunnusta SSAS:n EffectiveUser-arvona.
4. Jos Active Directory -haku onnistuu, se hakee kyseisen Active Directory -henkilön UserPrincipalName-arvon.
5. Se välittää UserPrincipalName-sähköpostiosoitteen EffectiveUser-arvoksi SSAS:lle, esim. Alias@corp.on-prem.contoso.

Yhdyskäytävän määrittäminen Active Directory -haun suorittamiseen:

1. [Lataa ja asenna uusin yhdyskäytävä](/data-integration/gateway/service-gateway-install).

2. Yhdyskäytävässä määritä paikallinen tietoyhdyskäytäväpalvelu suoritettavaksi toimialuetilin kanssa paikallisen palvelutilin sijaan. Muussa tapauksessa Active Directory -haku ei toimi oikein suorituspalvelussa. Siirry tietokoneessa [paikallisen tietoyhdyskäytävän sovellukseen](/data-integration/gateway/service-gateway-app) ja valitse **Palvelun asetukset** > **Palvelutilin vaihtaminen**. Varmista, että sinulla tämän yhdyskäytävän palautusavain, sillä sinun on palautettava se samalla tietokoneella, ellet halua luoda uutta yhdyskäytävää. Yhdyskäytäväpalvelu on käynnistettävä uudelleen, jotta muutos tulee voimaan.

3. Siirry järjestelmänvalvojana yhdyskäytävän asennuskansioon, *C:\Program Files\On-premises data gateway* varmistaaksesi, että sinulla on kirjoitusoikeudet. Avaa *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*-tiedosto.

4. Muokkaa seuraavaa kahta määritysarvoa omiin Active Directory -käyttäjiisi sovellettavien *omien* Active Directory -käyttäjien määritysten mukaan. Seuraavat määritysarvot ovat esimerkkejä. Määritä Active Directory -määrityksiin perustuvat arvot. Määritysten kirjainkoko on merkitsevä, joten varmista, että ne vastaavat Active Directoryn arvoja.

    ![Azure AD -asetukset](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names_03.png)

    Jos ADServerPath-määritykselle ei ole annettu arvoa, yhdyskäytävä käyttää yleistä luetteloa. Voit myös määrittää useita arvoja ADServerPath-määritykselle. Erota arvot toisistaan puolipisteellä seuraavan esimerkin mukaisesti:

    ```xml
    <setting name="ADServerPath" serializeAs="String">
        <value> >GC://serverpath1; GC://serverpath2;GC://serverpath3</value>
    </setting>
    ```

    Yhdyskäytävä jäsentää ADServerPath-määrityksen arvot vasemmalta oikealle, kunnes vastaavuus löytyy. Jos vastaavuutta ei löydy, yhdyskäytävä käyttää alkuperäistä 	täydellistä käyttäjätunnusta. Varmista, että yhdyskäytäväpalvelua (PBIEgwService) käyttävällä tilillä on kyselyoikeudet kaikkiin Active Directory -palvelimiin, jotka on sisällytetty ADServerPath-määritykseen.

    Yhdyskäytävä tukee seuraavien esimerkkien mukaisia, kahdenlaisia ADServerPath-määrityksiä:

    **WinNT**

    ```xml
    <value="WinNT://usa.domain.corp.contoso.com,computer"/>
    ```

    **GC**

    ```xml
    <value> GC://USA.domain.com </value>
    ```

5. Käynnistä paikallinen tietoyhdyskäytäväpalvelu uudelleen, jotta määritysten muutokset tulevat voimaan.

### <a name="work-with-mapping-rules"></a>Liittämisen sääntöjen käsitteleminen

Voit luoda yhdistämissäännön kirjoittamalla **Alkuperäisen nimen** ja **Uuden nimen** arvot ja valitsemalla sitten **Lisää**.

| Kenttä | Description |
| --- | --- |
| Korvaa (alkuperäinen nimi) |Sähköpostiosoite, jota käytit Power BI:hin kirjautumiseen. |
| Korvaava (uusi nimi) |Korvaava arvo. Korvaamisen tulos lähetetään EffectiveUserName-arvona Analysis Services -yhteyttä muodostettaessa. |

![Yhdistämissäännön luominen](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names-effective-user-names.png)

Kun valitset kohteen luettelosta, voit muuttaa sen järjestystä käyttämällä kaksoisnuolikuvaketta. Voit myös poistaa merkinnän.

![Kohteiden järjestäminen uudelleen listassa](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names-entry-selected.png)

### <a name="use-a-wildcard"></a>Yleismerkin käyttäminen

Voit käyttää yleismerkkejä (*) **Korvaa (alkuperäinen nimi)** -merkkijonossa. Sitä voidaan käyttää vain itsenäisesti (ei minkään muun merkkijonon osan kanssa). Yleismerkkiä käyttämällä voit valita kaikki käyttäjät ja välittää tietolähteelle yhden arvon. Tästä on hyötyä, kun haluat kaikkien organisaatiosi käyttäjien käyttävän samaa käyttäjää paikallisessa ympäristössäsi.

### <a name="test-a-mapping-rule"></a>Liittämissäännön testaaminen

Voit vahvistaa, millä alkuperäinen nimi korvataan, antamalla arvon **Alkuperäinen nimi** -kenttään. Valitse **Testaa sääntöä**.

![Liittämissäännön testaaminen](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-test-mapping-rule.png)

> [!NOTE]
> Palvelulla kestää joitain minuutteja aloittaa tallennettujen sääntöjen käyttö. Sääntö toimii selaimessa heti.

### <a name="limitations-for-mapping-rules"></a>Liittämissääntöjä koskevat rajoitukset

Liittäminen koskee tiettyä määritettävää tietolähdettä. Se ei ole yleinen asetus. Jos sinulla on useita Analysis Services -tietolähteitä, sinun on liitettävä kunkin tietolähteen käyttäjät erikseen.

## <a name="authentication-to-a-live-analysis-services-data-source"></a>Todentaminen – reaaliaikainen Analysis Services -tietolähde

Aina, kun käyttäjä on vuorovaikutuksessa Analysis Servicesin kanssa, käytössä oleva käyttäjänimi välitetään yhdyskäytävään ja paikalliseen Analysis Services -palvelimeen. Analysis Servicesiin välitetään käyttäjätietona täydellinen käyttäjätunnus, joka on yleensä pilvipalveluun kirjautumisessa käytetty sähköpostiosoite. Täydellinen käyttäjätunnus välitetään EffectiveUserName-yhteysominaisuudessa. 

Tämän sähköpostiosoitteen on vastattava paikallisen Active Directory -toimialueen määritettyä täydellistä käyttäjätunnusta. Täydellinen käyttäjätunnus on Active Directory -tilin ominaisuus. Windows-tilin on oltava käytössä Analysis Services -roolissa, jotta palvelinta voi käyttää. Kirjautuminen ei onnistu, jos Active Directorysta ei löydy vastaavuutta.

Analysis Services-voi myös tehdä suodatuksia tämän tilin perusteella. Suodatus voidaan tehdä joko roolipohjaisessa suojauksessa tai rivitason suojauksessa.

## <a name="role-based-security"></a>Roolipohjainen suojaus

Malleissa käytetään käyttäjärooleihin perustuvaa suojausta. Roolit määritetään tietyn malliprojektin luomisvaiheessa SQL Server Data Tools -liiketoimintatietotyökaluissa tai mallin käyttöönoton jälkeen SQL Server Management Studion avulla. Rooleihin kuuluu jäseniä Windows käyttäjänimen tai Windows-ryhmän mukaan. Roolit määrittävät käyttäjän oikeudet suorittaa kyselyitä tai toimintoja mallissa. Useimmilla käyttäjillä on rooli, joka antaa lukuoikeudet. Muut roolit on tarkoitettu järjestelmänvalvojille, ja ne antavat oikeuden käsitellä kohteita sekä hallita tietokantafunktioita ja muita rooleja.

## <a name="row-level-security"></a>Rivitason suojaus

Rivitason suojaus tarkoittaa nimenomaan Analysis Services -palvelun rivitason suojausta. Mallit voivat tarjota dynaamista rivitason suojausta. Taulukkomalleihin ei vaadita dynaamista suojausta – toisin kuin rooleja, joita käyttäjille on määritettävä vähintään yksi. Ylätasolla dynaaminen suojaus määrittää käyttäjän tietojenlukuoikeuden suoraan tietyn taulukon tietylle riville. Kuten roolitkin, dynaaminen rivitason suojaus perustuu käyttäjän Windows-käyttäjänimeen.

Käyttäjän mahdollisuus suorittaa kyselyjä ja tarkastella mallitietoja määräytyy seuraavien asioiden mukaan:

- heidän Windows-käyttäjätiliinsä määritettyjen roolien perusteella
- mahdollisen dynaamisen rivitason suojauksen perusteella.

Tässä artikkelissa ei käsitellä roolipohjaisen ja dynaamisen rivitason suojauksen ottamista käyttöön malleissa. Lisätietoja on MSDN:n artikkeleissa, jotka käsittelevät [rooleja (SSAS – taulukkomuoto)](/analysis-services/tabular-models/roles-ssas-tabular) ja [käyttöoikeusrooleja (Analysis Services – monidimensionaaliset tiedot)](/analysis-services/multidimensional-models/olap-logical/security-roles-analysis-services-multidimensional-data). Jos haluat ymmärtää taulukkomallin suojausta mahdollisimman perusteellisesti, lataa ja lue [Taulukkomuotoisten liiketoimintatietojen semanttisen mallin suojaamista käsittelevä tekninen raportti](https://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Securing%20the%20Tabular%20BI%20Semantic%20Model.docx).

## <a name="what-about-azure-ad"></a>Entä Azure AD?

Microsoft-pilvipalveluissa käyttäjät todennetaan [Azure AD:n](/azure/active-directory/fundamentals/active-directory-whatis) avulla. Azure AD on vuokraaja, joka sisältää käyttäjänimet ja käyttöoikeusryhmät. Yleensä kirjautumisessa käytetty sähköpostiosoite on sama kuin tilin täydellinen käyttäjätunnus.

## <a name="what-is-the-role-of-my-local-active-directory-instance"></a>Mikä on paikallisen Active Directory -esiintymäni rooli?

Jotta Analysis Services voi selvittää, onko siihen yhteyden muodostavalla käyttäjällä roolinsa perusteella oikeus lukea tietoja, palvelimen on muunnettava käytössä oleva käyttäjänimi, joka välitetään Azure AD:stä yhdyskäytävään ja Analysis Services -palvelimeen. Analysis Services -palvelin välittää käytössä olevan käyttäjänimen Windows Active Directoryn toimialueen ohjauskoneeseen (DC). Active Directoryn toimialueen ohjauskone vahvistaa sitten, että käytössä oleva käyttäjänimi on kelvollinen täydellinen käyttäjätunnus paikallisella tilillä. Se palauttaa kyseisen käyttäjän Windows-käyttäjänimen takaisin Analysis Services -palvelimeen.

EffectiveUserName-ominaisuutta ei voi käyttää sellaisessa Analysis Services -palvelimessa, jota ei ole liitetty toimialueelle. Analysis Services -palvelimen on oltava liitetty toimialueelle kirjautumisvirheiden välttämiseksi.

## <a name="how-do-i-tell-what-my-upn-is"></a>Mistä tiedän, mikä täydellinen käyttäjätunnukseni on?

Et välttämättä tiedä täydellistä käyttäjätunnustasi etkä ehkä ole toimialueen järjestelmänvalvoja. Voit selvittää tilisi täydellisen käyttäjätunnuksen työasemaltasi seuraavan komennon avulla.

    whoami /upn

Tulos näyttää samalta kuin sähköpostiosoite, mutta kyseessä on toimialuetilisi täydellinen käyttäjätunnus. Jos käytät Analysis Services -tietolähdettä reaaliaikaisiin yhteyksiin eikä täydellinen käyttäjätunnus vastaa Power BI:hin kirjautuessa käyttämääsi sähköpostiosoitetta, tutustu [käyttäjänimien liittämiseen](#map-user-names-for-analysis-services-data-sources).

## <a name="synchronize-an-on-premises-active-directory-with-azure-ad"></a>Paikallisen Active Directoryn synkronoiminen Azure AD:n kanssa

Jos aiot käyttää reaaliaikaisia Analysis Services -yhteyksiä, paikallisten Active Directory -tilien on vastattava Azure AD:tä. Eri tilien täydellisten käyttäjätunnusten on vastattava toisiaan.

Pilvipalvelut tuntevat vain Azure AD:n tilit. Vaikka olisit lisännyt tilin paikalliseen Active Directoryyn, sillä ei ole merkitystä. Sitä ei voi käyttää, jos sitä ei ole Azure AD:ssä. Voit yhdistää paikallisen Active Directoryn tilit Azure AD:hen eri tavoin:

- Voit lisätä tilejä Azure AD:hen manuaalisesti.

   Voit luoda tilin Azure-portaalissa tai Microsoft 365 -hallintakeskuksessa, ja tilin nimi vastaa paikallisen Active Directoryn tilin täydellistä käyttäjätunnusta.

- Voit synkronoida paikalliset tilit Azure AD -vuokraajan kanssa [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-sync-whatis) -työkalun avulla.

   Azure AD Connect -työkalulla voidaan synkronoida hakemistot ja määrittää todentaminen. Vaihtoehtoja ovat salasanan hajautuksen synkronointi, läpivientitodentaminen ja liittoutuminen. Jos et ole vuokraajan järjestelmänvalvoja tai paikallisen toimialueen järjestelmänvalvoja, sinun on pyydettävä IT-järjestelmänvalvojaasi tekemään määritykset.

   Azure AD Connectin käyttäminen varmistaa, että Azure AD:n ja paikallisen Active Directoryn täydelliset käyttäjätunnukset vastaavat toisiaan.

> [!NOTE]
> Tilien synkronointi Azure AD Connect -työkalun avulla luo uusia tilejä Azure AD -vuokraajaan.

## <a name="use-the-data-source"></a>Tietolähteen käyttäminen

Kun tietolähde on luotu, se on käyttäjien saatavilla joko reaaliaikaisten yhteyksien tai ajoitetun päivityksen välityksellä.

> [!NOTE]
> Palvelimen ja tietokannan nimien pitää täsmätä paikallisen tietoyhdyskäytävän Power BI Desktopin ja tietolähteen kanssa.

Yhdyskäytävän tietojoukon ja tietolähteen välinen linkki perustuu palvelimen ja tietokannan nimiin. Näiden nimien on vastattava toisiaan. Jos esimerkiksi Power BI Desktopissa palvelimen nimelle annetaan IP-osoite, samaa IP-osoitetta tulee käyttää myös yhdyskäytävän kokoonpanon tietolähteessä. Jos käytät Power BI Desktopissa nimeä *PALVELIN\ESIINTYMÄ*, sitä on käytettävä myös yhdyskäytävälle määritetyn tietolähteen sisällä.

Tämä vaatimus koskee sekä reaaliaikaisia yhteyksiä että ajoitettuja päivityksiä.

### <a name="use-the-data-source-with-live-connections"></a>Tietolähteen käyttö reaaliaikaisissa yhteyksissä

Palvelimen ja tietokannan nimen on täsmättävä Power BI Desktopissa ja yhdyskäytävälle määritetyssä tietolähteessä. Varmista myös, että käyttäjä on mainittu tietolähteen **Käyttäjät**-välilehdellä, jotta voit julkaista tietojoukkoja reaaliaikaisella yhteydellä. Reaaliaikaisten yhteyksien valinta tapahtuu Power BI Desktopissa, kun tuot tietoja ensimmäisen kerran.

Raporttisi alkaa toimia, kun olet julkaissut tietojoukot Power BI Desktopissa tai **Nouda tiedot** -ominaisuudella. Yhdyskäytävässä luodun tietolähteen luomisen jälkeen voi kestää useita minuutteja, ennen kuin yhteyttä voidaan käyttää.

### <a name="use-the-data-source-with-scheduled-refresh"></a>Tietolähteen käyttö ajoitetun päivityksen kanssa

Jos sinut on lisätty yhdyskäytävän sisällä määritellyn tietolähteen **Käyttäjät**-välilehdelle ja jos palvelimen ja tietokannan nimet täsmäävät, näet yhdyskäytävän yhtenä, ajoitetun päivityksen kanssa käytettävänä vaihtoehtona.

![Käyttäjien näyttäminen](media/service-gateway-enterprise-manage-ssas/powerbi-gateway-enterprise-schedule-refresh.png)

### <a name="limitations-of-analysis-services-live-connections"></a>Reaaliaikaisten Analysis Services -yhteyksien rajoitukset

Voit käyttää reaaliaikaista yhteyttä taulukkomuotoisiin tai moniulotteisiin esiintymiin.

| **Palvelinversio** | **Pakollinen SKU** |
| --- | --- |
| 2012 SP1 CU4 tai uudempi versio |Business Intelligence- ja Enterprise SKU |
| 2014 |Business Intelligence- ja Enterprise SKU |
| 2016 |Standard SKU tai uudempi versio |

* Solutason muotoilu- ja käännösominaisuuksia ei tueta.
* Toiminnot ja nimetyt joukot eivät näy Power BI:ssä. Voit silti muodostaa yhteyden monidimensiollisiin kuutioihin, jotka sisältävät myös toimintoja ja nimettyjä joukkoja, ja luoda visualisointeja ja raportteja.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Paikallisen tietoyhdyskäytävän vianmääritys](/data-integration/gateway/service-gateway-tshoot)
* [Yhdyskäytävien vianmääritys – Power BI](service-gateway-onprem-tshoot.md)

Onko sinulla kysyttävää? Kokeile [Power BI -yhteisöä](https://community.powerbi.com/).
