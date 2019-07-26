---
title: Tietolähteen hallinta - Analysis Services
description: Paikallisen tietoyhdyskäytävän ja kyseiseen yhdyskäytävään kuuluvien tietolähteiden hallinta. Tämä koskee Analysis Services -palveluita sekä Multidimensioisessa että Taulukkotilassa.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 93475f6476f8baad73229473bd3ce60db68a320b
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271629"
---
# <a name="manage-your-data-source---analysis-services"></a>Tietolähteen hallinta - Analysis Services

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Kun [paikallinen tietoyhdyskäytävä on asennettu](/data-integration/gateway/service-gateway-install), sinun on [lisättävä tietolähteitä](service-gateway-data-sources.md#add-a-data-source), joita voidaan käyttää kyseisen yhdyskäytävän kanssa. Tässä artikkelissa perehdytään siihen, miten käsitellään yhdyskäytäviä ja Analysis Services -tietolähteitä, joita käytetään joko ajoitetussa päivityksessä tai reaaliaikaisissa yhteyksissä.

Jos haluat lisätietoja reaaliaikaisen yhteyden määrittämisestä Analysis Servicesiin, [katso tämä video.](https://www.youtube.com/watch?v=GPf0YS-Xbyo&feature=youtu.be)

> [!NOTE]
> Jos sinulla on Analysis Services -tietolähde, sinun on asennettava yhdyskäytävä sellaisessa tietokoneessa, joka on liitetty samaan toimialuepuuryhmään tai toimialueeseen kuin Analysis Services -palvelin.

## <a name="add-a-data-source"></a>Tietolähteen lisääminen

Lisätietoja tietolähteen lisäämisestä on artikkelissa [Tietolähteen lisääminen](service-gateway-data-sources.md#add-a-data-source). Valitse **tietolähteen tyypiksi** Analysis Services, jos olet muodostamassa yhteyttä Multidimensioiseen tai Taulukkomuotoiseen palvelimeen.

![Analysis Services -tietolähteen lisääminen](media/service-gateway-enterprise-manage-ssas/datasourcesettings2-ssas.png)

Täytä sitten tietolähteen tiedot, jotka sisältävät **palvelimen** ja **tietokannan**. Yhdyskäytävä käyttää kirjoittamaasi **Käyttäjänimeä** ja **salasanaa** muodostaessaan yhteyden Analysis Services -esiintymään.

> [!NOTE]
> Käyttämälläsi Windows-tilillä on oltava palvelimen järjestelmänvalvojan oikeudet esiintymään, johon olet muodostamassa yhteyttä. Jos tämän tilin salasanalle on määritetty vanhentumisaika, käyttäjät saattavat kohdata yhteysvirheen, jos salasanaa ei päivitetä tietolähteessä. Lisätietoja tunnistetietojen tallentamisesta on artikkelissa [Salattu tunnistetietojen tallentaminen pilvipalveluun](service-gateway-data-sources.md#storing-encrypted-credentials-in-the-cloud).

![Tietolähdeasetusten täyttäminen](media/service-gateway-enterprise-manage-ssas/datasourcesettings3-ssas.png)

Valitse **Lisää**, kun kaikki kohdat on täytetty. Voit nyt käyttää tätä tietolähdettä ajoitettuihin päivityksiin tai reaaliaikaisiin yhteyksiin paikallisessa Analysis Services -esiintymässä. *Yhteyden muodostaminen onnistui* -teksti tulee näkyviin, jos yhteys muodostettiin onnistuneesti.

![Yhteyden tilan näyttäminen](media/service-gateway-enterprise-manage-ssas/datasourcesettings4.png)

### <a name="advanced-settings"></a>Lisäasetukset

Vaihtoehtoisesti voit määrittää tietolähteellesi yksityisyystason. Tällä hallinnoidaan sitä, miten tietoja voidaan yhdistää. Tätä käytetään vain ajoitetussa päivityksessä. Se ei koske reaaliaikaisia yhteyksiä. Lisätietoja tietolähteen yksityisyystasoista on artikkelissa [Yksityisyystasot (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Yksityisyystason määrittäminen](media/service-gateway-enterprise-manage-ssas/datasourcesettings9.png)

## <a name="usernames-with-analysis-services"></a>Käyttäjänimet ja Analysis Services

<iframe width="560" height="315" src="https://www.youtube.com/embed/Qb5EEjkHoLg" frameborder="0" allowfullscreen></iframe>

Aina, kun käyttäjä on vuorovaikutuksessa Analysis Servicesiin yhdistetyn raportin kanssa, käytössä oleva käyttäjänimi välitetään yhdyskäytävään ja paikalliseen Analysis Services -palvelimeen. Analysis Servicesiin välitetään käyttäjätietona Power BI:hin kirjautumisessa käytetty sähköpostiosoite. Yhteys välittää tämän [EffectiveUserName](https://msdn.microsoft.com/library/dn140245.aspx#bkmk_auth)-ominaisuutena. Tämän sähköpostiosoitteen on vastattava paikallisen Active Directory -toimialueeseen määritettyä täydellistä käyttäjätunnusta (UPN). Täydellinen käyttäjätunnus on Active Directory -tilin ominaisuus. Windows-tilin on oltava käytössä Analysis Services -roolissa. Kirjautuminen ei onnistu, jos Active Directorysta ei löydy vastaavuutta. Lisätietoja Active Directorystä ja käyttäjien nimeämisestä on kohdassa [Käyttäjän nimeämisen määritteet](https://msdn.microsoft.com/library/ms677605.aspx).

Voit myös [liittää Power BI -kirjautumisnimen paikallisen hakemiston täydelliseen käyttäjätunnukseen](service-gateway-enterprise-manage-ssas.md#mapping-usernames-for-analysis-services-data-sources).

## <a name="mapping-usernames-for-analysis-services-data-sources"></a>Käyttäjänimien yhdistäminen Analysis Services -tietolähteitä varten

<iframe width="560" height="315" src="https://www.youtube.com/embed/eATPS-c7YRU" frameborder="0" allowfullscreen></iframe>

Power BI mahdollistaa käyttäjänimien yhdistämisen Analysis Services -tietolähteitä varten. Voit määrittää sääntöjä, joiden avulla Power BI:n kautta kirjautunut käyttäjänimi yhdistetään Analysis Services -yhteydellä EffectiveUserNamelle välitettyyn nimeen. Käyttäjänimien yhdistämistoiminto on kätevä tapa kiertää ongelma, jos Azure Active Directory -käyttäjänimesi ei vastaa paikallisen Active Directoryn täydellistä käyttäjätunnusta. Jos sähköpostiosoite on esimerkiksi nancy@contoso.onmicrsoft.com, sen voi yhdistää käyttäjänimeen nancy@contoso.com, ja tämä arvo välitetään yhdyskäytävään.

Voit liittää Analysis Services -palveluissa käyttämiäsi käyttäjänimiä kahdella eri tavalla:

* Manuaalinen käyttäjänimen uudelleenliittäminen
* Paikallisen Active Directory -ominaisuuden valinta täydellisten AAD-käyttäjänimien liittämiseksi Active Directory -käyttäjiin (AD-valinnan liittäminen)

Manuaalinen liittäminen on mahdollista toisella lähestymistavalla, mutta se vie paljon aikaa ja sen ylläpito on vaikeaa. Se on erityisen vaikeaa silloin, kun kuvioiden vastaavuus ei riitä, esim. kun AAD- ja paikallisen AD:n toimialuenimet eroavat toisistaan tai kun käyttäjätilien nimet ovat erilaiset AAD:n ja AD:n välillä. Tämän vuoksi manuaalista liittämistä toisella menetelmällä ei suositella.

Menetelmät on kuvattu järjestyksessä kahdessa seuraavassa osassa.

### <a name="manual-user-name-re-mapping"></a>Manuaalinen käyttäjänimen uudelleenliittäminen

Voit määrittää mukautetut täydellisten käyttäjänimien (UPN) säännöt Analysis Services -tietolähteille. Tästä on apua, jos Power BI -palvelun kirjautumisnimet eivät vastaa paikallisen hakemistosi täydellisiä käyttäjätunnuksia. Jos kirjaudut esimerkiksi Power BI:hin tunnuksella john@contoso.com, mutta paikallisen hakemiston täydellinen käyttäjänimi on john@contoso.local, voit määrittää liittämissäännön, joka john@contoso.local välitetään Analysis Servicesille.

Voit siirtyä UPN-liittämisnäyttöön seuraavasti.

1. Valitse **hammaspyöräkuvake** ja valitse **Yhdyskäytävien hallinta**.
2. Laajenna yhdyskäytävä, joka sisältää Analysis Services -tietolähteen. Jos et ole luonut Analysis Services -tietolähdettä, voit tehdä sen tässä vaiheessa.
3. Valitse tietolähde ja valitse sitten **Käyttäjät**-välilehti.
4. Valitse **Käyttäjänimien liittäminen**.

    ![UPN-liittämisnäyttö](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names_02.png)

Näyttöön tulee vaihtoehtoja sääntöjen lisäämiseksi ja testaamiseksi tietylle käyttäjälle.

> [!NOTE]
> Saatat vahingossa muuttaa käyttäjää, jolle muutoksia ei ollut tarkoitus tehdä. Jos esimerkiksi **Korvaa (alkuperäinen arvo)** on <em>@contoso.com</em> ja **Korvaava (uusi nimi)** on <em>@contoso.local</em>, kaikki käyttäjät, joiden kirjautumisnimi sisältää <em>@contoso.com</em>, korvataan arvolla <em>@contoso.local</em>. Jos **Korvaa (alkuperäinen nimi)** on <em>dave@contoso.com</em> ja **Korvaava (uusi nimi)** on <em>dave@contoso.local</em>, käyttäjä, jonka kirjautumistunnus on v-dave@contoso.com, lähetetään nimellä v-dave<em>@contoso.local</em>.

### <a name="ad-lookup-mapping"></a>AD-valinnan liittäminen

Voit suorittaa paikallisen AD-ominaisuuksien valinnan liittääksesi täydelliset AAD-käyttäjätunnukset täydelliset Active Directory -käyttäjiin tämän osan ohjeiden avulla. Katsotaan aluksi, miten tämä toimii.

**Power BI -palvelussa** tapahtuu seuraavaa:

* Jokaisen Power BI AAD -käyttäjän paikalliselle SSAS-palvelimelle lähettämän kyselyn mukana toimitetaan UPN-merkkijono, kuten:      firstName.lastName@contoso.com

> [!NOTE]
> Power BI -tietolähteessä määriteltyjä manuaalisia UPN-käyttäjäliitoksia sovelletaan *ennen* käyttäjänimen merkkijonon lähettämistä paikalliseen tietoyhdyskäytävään.

Toimi mukautettuja käyttäjän yhdistämismäärityksiä sisältävän paikallisen tietoyhdyskäytävän kanssa seuraavasti:

1. Etsi Active Directory -hakemisto, josta haluat tehdä haun (automaattisen tai määritettävän).
2. Etsi AD-henkilön määrite (kuten *sähköposti*) saapuvan UPN-merkkijonon perusteella (”firstName.lastName@contoso.com”) **Power BI -palvelusta**.
3. Jos AD-haku epäonnistuu, se yrittää käyttää välitettyä täydellistä käyttäjätunnusta SSAS:n EffectiveUser-arvona.
4. Jos AD-haku onnistuu, se hakee kyseisen AD-henkilön *UserPrincipalName*-arvon.
5. Se välittää *UserPrincipalName*-sähköpostiosoitteen *EffectiveUser-arvoksi* SSAS:lle, esim. <em>Alias@corp.on-prem.contoso</em>.

Yhdyskäytävän määrittäminen AD-haun suorittamiseen:

1. [Lataa ja asenna uusin yhdyskäytävä](/data-integration/gateway/service-gateway-install).

2. Yhdyskäytävässä sinun on määritettävä **paikallinen tietoyhdyskäytäväpalvelu** suoritettavaksi toimialuetilin kanssa (paikallisen palvelutilin sijaan – muussa tapauksessa AD-haku ei toimi oikein suorituspalvelussa). Siirry tietokoneessa [paikallisen tietoyhdyskäytävän sovellukseen](/data-integration/gateway/service-gateway-app) ja valitse **Palvelun asetukset > Palvelutilin vaihtaminen**. Varmista, että sinulla tämän yhdyskäytävän palautusavain, sillä sinun on palautettava se samalla tietokoneella, ellet halua luoda uutta yhdyskäytävää. Yhdyskäytäväpalvelu on käynnistettävä uudelleen, jotta muutos tulee voimaan.

3. Siirry yhdyskäytävän asennuskansioon *C:\Program Files\On-premises data gateway* järjestelmänvalvojana varmistaaksesi, että sinulla on kirjoitusoikeudet, ja avaa tiedosto *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*.

4. Muokkaa seuraavaa kahta määritysarvoa omiin AD-käyttäjiisi sovellettavien *omien* Active Directory -käyttäjien määritysten mukaan. Alla olevat määritysarvot ovat vain esimerkkejä – sinun on määritettävä ne Active Directory -määritystesi mukaisesti. Määritysten kirjainkoko on merkitsevä, joten varmista, että ne vastaavat Active Directoryn arvoja.

    ![Azure Active Directory -asetukset](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names_03.png)

    Jos ADServerPath-määritykselle ei ole annettu arvoa, yhdyskäytävä käyttää Yleistä luetteloa. Voit myös määrittää useita arvoja ADServerPath-määritykselle. Erota arvot toisistaan puolipisteellä seuraavan esimerkin mukaisesti.

    ```xml
    <setting name="ADServerPath" serializeAs="String">
        <value> >GC://serverpath1; GC://serverpath2;GC://serverpath3</value>
    </setting>
    ```

    Yhdyskäytävä jäsentää ADServerPath-määrityksen arvot vasemmalta oikealle, kunnes vastaavuus löytyy. Jos vastaavuutta ei löydy, yhdyskäytävä käyttää alkuperäistä 	täydellistä käyttäjätunnusta. Varmista, että yhdyskäytäväpalvelua (PBIEgwService) käyttävällä tilillä on kyselyoikeudet kaikkiin AD-palvelimiin, jotka on sisällytetty ADServerPath-määritykseen.

    Yhdyskäytävä tukee seuraavien esimerkkien mukaisia, kahdenlaisia ADServerPath-määrityksiä.

    **WinNT**

    ```xml
    <value="WinNT://usa.domain.corp.contoso.com,computer"/>
    ```

    **GC**

    ```xml
    <value> GC://USA.domain.com </value>
    ```

5. Käynnistä **paikallinen tietoyhdyskäytävä**palvelu uudelleen, jotta määritysten muutokset tulevat voimaan.

### <a name="working-with-mapping-rules"></a>Liittämisen sääntöjen käsitteleminen

Voit luoda yhdistämissäännön kirjoittamalla **Alkuperäisen nimen** ja **Uuden nimen** arvot ja valitsemalla sitten **Lisää**.

| Kenttä | Kuvaus |
| --- | --- |
| Korvaa (alkuperäinen nimi) |Sähköpostiosoite, jolla olet kirjautunut Power BI:hin. |
| Korvaava (uusi nimi) |Korvaava arvo. Korvaamisen tulos lähetetään *EffectiveUserName*-arvona Analysis Services -yhteyttä muodostettaessa. |

![Yhdistämissäännön luominen](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names-effective-user-names.png)

Kun valitset kohteen luettelosta, voit muuttaa sen järjestystä käyttämällä **kaksoisnuolikuvaketta** tai **Poistaa** sen kirjauksen.

![Kohteiden järjestäminen uudelleen listassa](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names-entry-selected.png)

### <a name="using-wildcard-"></a>.Yleismerkkien (*) käyttö

Voit käyttää yleismerkkejä **Korvaa (alkuperäinen nimi)** -merkkijonossa. Sitä voidaan käyttää vain itsenäisesti (ei minkään muun merkkijonon osan kanssa). Tämän avulla voit valita kaikki käyttäjät ja välittää tietolähteelle yhden arvon. Tästä on hyötyä, kun haluat kaikkien organisaatiosi käyttäjien käyttävän samaa käyttäjää paikallisessa ympäristössäsi.

### <a name="test-a-mapping-rule"></a>Liittämissäännön testaaminen

Voit vahvistaa, millä alkuperäinen nimi korvataan, antamalla arvon **Alkuperäinen nimi** -kenttään ja valitsemalla **Testaa sääntöä**.

![Yhdistämissäännön testaaminen](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-test-mapping-rule.png)

> [!NOTE]
> Palvelulla kestää joitain minuutteja aloittaa tallennettujen sääntöjen käyttö. Selaimella sääntö on heti voimassa.

### <a name="limitations-for-mapping-rules"></a>Liittämissääntöjä koskevat rajoitukset

Liittämissäännöt koskevat tiettyä määritettävää tietolähdettä. Se ei ole yleinen asetus. Jos sinulla on useita Analysis Services -tietolähteitä, sinun on liitettävä kunkin tietolähteen käyttäjät erikseen.

## <a name="authentication-to-a-live-analysis-services-data-source"></a>Todentaminen – reaaliaikainen Analysis Services -tietolähde

Aina, kun käyttäjä on vuorovaikutuksessa Analysis Servicesin kanssa, käytössä oleva käyttäjänimi välitetään yhdyskäytävään ja paikalliseen Analysis Services -palvelimeen. Analysis Servicesiin välitetään käyttäjätietona täydellinen käyttäjätunnus (UPN) eli yleensä pilvipalveluun kirjautumisessa käytetty sähköpostiosoite. Täydellinen käyttäjätunnus välitetään EffectiveUserName-yhteysominaisuudessa. Tämän sähköpostiosoitteen on vastattava paikallisen Active Directory -toimialueen määritettyä täydellistä käyttäjätunnusta. Täydellinen käyttäjätunnus on Active Directory -tilin ominaisuus. Windows-tilin on oltava käytössä Analysis Services -roolissa, jotta palvelinta voi käyttää. Kirjautuminen ei onnistu, jos Active Directorysta ei löydy vastaavuutta.

Analysis Services-voi myös tehdä suodatuksia tämän tilin perusteella. Suodatus voidaan tehdä joko roolipohjaisessa suojauksessa tai rivitason suojauksessa.

## <a name="role-based-security"></a>Roolipohjainen suojaus

Malleissa käytetään käyttäjärooleihin perustuvaa suojausta. Roolit määritetään tietyn malliprojektin luomisvaiheessa SQL Server Data Tools -liiketoimintatietotyökaluissa (SSDT-BI) tai mallin käyttöönoton jälkeen SQL Server Management Studion (SSMS) avulla. Rooleihin kuuluu jäseniä Windows käyttäjänimen tai Windows-ryhmän mukaan. Roolit määrittävät käyttäjän oikeudet suorittaa kyselyitä tai toimintoja mallissa. Useimmilla käyttäjillä on rooli, joka antaa lukuoikeudet. Muut roolit on tarkoitettu järjestelmänvalvojille, ja ne antavat oikeuden käsitellä kohteita sekä hallita tietokantafunktioita ja muita rooleja.

## <a name="row-level-security"></a>Rivitason suojaus

Rivitason suojaus tarkoittaa nimenomaan Analysis Services -palvelun rivitason suojausta. Mallit voivat tarjota dynaamista rivitason suojausta. Taulukkomalleihin ei vaadita dynaamista suojausta – toisin kuin rooleja, joita käyttäjille on määritettävä vähintään yksi. Ylätasolla dynaaminen suojaus määrittää käyttäjän tietojenlukuoikeuden suoraan tietyn taulukon tietylle riville. Kuten roolitkin, dynaaminen rivitason suojaus perustuu käyttäjän Windows-käyttäjänimeen.

Käyttäjän mahdollisuus suorittaa kyselyjä ja tarkastella mallitietoja määräytyy ensiksi heidän Windows-käyttäjätiliinsä määritettyjen roolien perusteella ja toiseksi mahdollisen dynaamisen rivitason suojauksen perusteella.

Tässä artikkelissa ei käsitellä roolipohjaisen ja dynaamisen rivitason suojauksen ottamista käyttöön malleissa. Lisätietoja on MSDN:n artikkeleissa, jotka käsittelevät [rooleja (SSAS – taulukkomuoto)](https://msdn.microsoft.com/library/hh213165.aspx) ja [käyttöoikeusrooleja (Analysis Services – monidimensionaaliset tiedot)](https://msdn.microsoft.com/library/ms174840.aspx). Jos haluat ymmärtää taulukkomallin suojausta mahdollisimman perusteellisesti, lataa ja lue [Taulukkomuotoisten liiketoimintatietojen semanttisen mallin suojaamista käsittelevä tekninen raportti](https://msdn.microsoft.com/library/jj127437.aspx).

## <a name="what-about-azure-active-directory"></a>Entä Azure Active Directory?

Microsoft-pilvipalveluissa käyttäjät todennetaan [Azure Active Directoryn](/azure/active-directory/fundamentals/active-directory-whatis) avulla. Azure Active Directory on vuokraaja, joka sisältää käyttäjänimet ja käyttöoikeusryhmät. Yleensä kirjautumisessa käytetty sähköpostiosoite on sama kuin tilin täydellinen käyttäjätunnus.

Mikä on käyttäjän oman paikallisen Active Directoryn rooli?

Jotta Analysis Services voi selvittää, onko siihen yhteyden muodostavalla käyttäjällä roolinsa perusteella oikeus lukea tietoja, palvelimen on muunnettava käytössä oleva käyttäjänimi, joka välitetään AAD:stä yhdyskäytävään ja Analysis Services -palvelimeen. Analysis Services -palvelin välittää käytössä olevan käyttäjänimen Windows Active Directoryn toimialueen ohjauskoneeseen (DC). Active Directoryn toimialueen ohjauskone vahvistaa, että käytössä oleva käyttäjänimi on kelvollinen täydellinen käyttäjätunnus paikallisella tilillä, ja palauttaa kyseisen käyttäjän Windows-käyttäjänimen takaisin Analysis Services -palvelimeen.

EffectiveUserName-ominaisuutta ei voi käyttää sellaisessa Analysis Services -palvelimessa, jota ei ole liitetty toimialueelle. Analysis Services -palvelimen on oltava liitetty toimialueelle kirjautumisvirheiden välttämiseksi.

### <a name="how-do-i-tell-what-my-upn-is"></a>Mistä tiedän, mikä täydellinen käyttäjätunnukseni on?

Et välttämättä tiedä täydellistä käyttäjätunnustasi etkä ehkä ole toimialueen järjestelmänvalvoja. Voit selvittää tilisi täydellisen käyttäjätunnuksen työasemaltasi seuraavan komennon avulla.

    whoami /upn

Tulos näyttää samalta kuin sähköpostiosoite, mutta kyseessä on toimialuetilisi täydellinen käyttäjätunnus. Jos käytät Analysis Services -tietolähdettä reaaliaikaisiin yhteyksiin eikä se vastaa Power BI:hin kirjautuessa käyttämääsi sähköpostiosoitetta, tutustu [käyttäjänimien liittämiseen](#mapping-usernames-for-analysis-services-data-sources).

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Paikallisen Active Directoryn synkronoiminen Azure Active Directoryn kanssa

Paikallisten Active Directory -tilien on hyvä vastata Azure Active Directorya, jos aiot käyttää reaaliaikaisia Analysis Services -yhteyksiä. Eri tilien täydellisten käyttäjätunnusten on nimittäin vastattava toisiaan.

Pilvipalvelut tuntevat vain Azure Active Directoryn tilit. Vaikka olisit lisännyt tilin paikalliseen Active Directoryyn, sitä ei voi käyttää, jos sitä ei ole Azure Active Directoryssa. Voit yhdistää paikallisen Active Directoryn tilit Azure Active Directoryyn eri tavoin.

1. Voit lisätä tilejä Azure Active Directoryyn manuaalisesti.

   Voit luoda tilin Azure-portaalissa tai Microsoft 365 -hallintakeskuksessa, ja tilin nimi vastaa paikallisen Active Directoryn tilin täydellistä käyttäjätunnusta.

2. Voit synkronoida paikalliset tilit Azure Active Directory -vuokraajan kanssa [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-sync-whatis) -työkalun avulla.

   Azure AD Connect -työkalulla voidaan synkronoida hakemistot ja määrittää todentaminen, mukaan lukien salasanan hajautuksen synkronointi, läpivientitodentaminen ja liittoutuminen. Jos et ole vuokraajan järjestelmänvalvoja tai paikallisen toimialueen järjestelmänvalvoja, sinun on pyydettävä IT-järjestelmänvalvojaasi tekemään määritykset.

Azure AD Connectin käyttäminen varmistaa, että AAD:n ja paikallisen Active Directoryn täydelliset käyttäjätunnukset vastaavat toisiaan.

> [!NOTE]
> Tilien synkronointi Azure AD Connect -työkalun avulla luo uusia tilejä AAD-vuokraajaan.

## <a name="using-the-data-source"></a>Tietolähteen käyttö

Kun olet luonut tietolähteen, sitä voi käyttää joko reaaliaikaisissa yhteyksissä tai ajoitetun päivityksen kautta.

> [!NOTE]
> Palvelimen ja tietokannan nimien pitää täsmätä paikallisen tietoyhdyskäytävän Power BI Desktopin ja tietolähteen kanssa.

Yhdyskäytävän tietojoukon ja tietolähteen välinen linkki perustuu palvelimen ja tietokannan nimiin. Näiden on täsmättävä. Jos esimerkiksi Power BI Desktopissa palvelimen nimelle annetaan IP-osoite, samaa IP-osoitetta tulee käyttää myös yhdyskäytävän kokoonpanon tietolähteessä. Jos käytät Power BI Desktopissa nimenä *PALVELIN\ESIINTYMÄ*, yhdyskäytävälle määritetyn tietolähteen sisällä on käytettävä samaa nimeä.

Tämä koskee sekä reaaliaikaisia yhteyksiä että ajoitettuja päivityksiä.

### <a name="using-the-data-source-with-live-connections"></a>Tietolähteen käyttö reaaliaikaisissa yhteyksissä

Palvelimen ja tietokannan nimen on täsmättävä Power BI Desktopissa ja yhdyskäytävälle määritetyssä tietolähteessä. Varmista myös, että käyttäjä on mainittu tietolähteen **Käyttäjät**-välilehdellä, jotta voit julkaista tietojoukkoja reaaliaikaisella yhteydellä. Reaaliaikaisten yhteyksien valinta tapahtuu Power BI Desktopissa, kun tuot tietoja ensimmäisen kerran.

Raporttisi alkaa toimia, kun olet julkaissut tietojoukot Power BI Desktopissa tai **Nouda tiedot** -ominaisuudella. Yhdyskäytävässä luodun tietolähteen luomisen jälkeen voi kestää useita minuutteja, ennen kuin yhteyttä voidaan käyttää.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Tietolähteen käyttö ajoitetun päivityksen kanssa

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
* Toiminnot ja Nimetyt joukot eivät näy Power BI:ssä, mutta voit silti muodostaa yhteyden monidimensiollisiin kuutioihin, jotka sisältävät myös toimintoja ja nimettyjä joukkoja, ja luoda visualisointeja ja raportteja.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Paikallisen tietoyhdyskäytävän vianmääritys](/data-integration/gateway/service-gateway-tshoot)
* [Yhdyskäytävien vianmääritys – Power BI](service-gateway-onprem-tshoot.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

