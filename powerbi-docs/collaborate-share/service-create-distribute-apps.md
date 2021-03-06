---
title: Julkaise sovellus Power BI:ssä
description: Lue, miten voit julkaista uusia sovelluksia, jotka ovat koontinäyttöjen ja raporttien kokoelmia, joissa on sisäänrakennetut siirtymiskomennot.
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/23/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 08b9585195e805548546e832915e07f0e02265f5
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348271"
---
# <a name="publish-an-app-in-power-bi"></a>Julkaise sovellus Power BI:ssä

Power BI:ssä voit luoda virallisia paketoituja sisältöjä ja sitten jakaa laajalle yleisölle *sovelluksena*. Voit luoda sovelluksia *työtiloissa*, joissa voit työstää Power BI -sisältöä yhdessä työtovereiden kanssa. Sen jälkeen voit julkaista valmiit sovellukset suurelle määrälle ihmisiä organisaatiossasi. 

![Power BI -sovellukset](media/service-create-distribute-apps/power-bi-new-apps.png)

Yrityskäyttäjät tarvitsevat usein monia Power BI -koontinäyttöjä ja raportteja yrityksensä pyörittämisessä. Power BI -sovelluksilla voit luoda kokoelmia koontinäytöistä ja raporteista ja julkaista nämä kokoelmat sovelluksina koko organisaatiolle tai tietyille ihmisille tai ryhmille. Jos olet raporttien luoja tai järjestelmänvalvoja, sovellukset tekevät näiden kokoelmien käyttöoikeuksien hallinnasta helpompaa.

Yrityskäyttäjät saavat sovelluksesi käyttöönsä eri tavoin:

- He voivat etsiä ja asentaa sovelluksen Microsoft AppSourcesta.
- Voit lähettää heille suoran linkin.
- Voit asentaa sen automaattisesti työtovereittesi Power BI -tileille, jos Power BI -järjestelmänvalvojasi antaa sinulle luvan.
- Power BI ei lähetä sähköpostia sisäisille käyttäjille, kun jaat sovelluksen tai päivität sovellusta. Jos jaat sen ulkoisille käyttäjille, kyseiset käyttäjät saavat suoran linkin sähköpostiviestin välityksellä. 

Voit luoda sovelluksen, jossa on omat sisäänrakennetut siirtymiskomennot, jolloin käyttäjät voivat vaivattomasti löytää sisältösi. He eivät voi muokata sovelluksen sisältöä. He voivat käyttää sitä joko Power BI -palvelussa tai jossakin mobiilisovelluksista. He voivat suodattaa, korostaa ja lajitella tiedot itse. He saavat päivitykset automaattisesti, ja sinä voit määrittää, kuinka usein tiedot päivitetään. Voit myös antaa heille muodostamisoikeuden yhteyden muodostamiseksi pohjana oleviin tietojoukkoihin ja kopioiden luomiseksi raporteista sovelluksessa. Lue lisätietoja [muodostamisoikeudesta](../connect-data/service-datasets-build-permissions.md).

## <a name="licenses-for-apps"></a>Sovellusten käyttöoikeudet
Sovelluksen luomiseen tai päivittämiseen tarvitaan Power BI Pro -käyttöoikeus. Sovelluksen *kuluttajilla* on kaksi vaihtoehtoa.

* **Vaihtoehto 1** Tämän sovelluksen työtila *ei* ole Power BI Premium -kapasiteetissa: Kaikilla käyttäjillä pitää olla Power BI Pro -käyttöoikeudet sovelluksesi näkemiseksi. 
* **Vaihtoehto 2** Tämän sovelluksen työtila *on* Power BI Premium -kapasiteetissa: Organisaatiosi yrityskäyttäjät ilman Power BI Pro -käyttöoikeutta voivat tarkastella sovelluksen sisältöä. He eivät kuitenkaan voi kopioida raportteja tai luoda raportteja pohjana olevien tietojoukkojen perusteella. Lisätietoja on artikkelissa [Mikä on Power BI Premium?](../admin/service-premium-what-is.md)

## <a name="publish-your-app"></a>Sovelluksen julkaiseminen
Kun työtilasi raporttinäkymät ja raportit ovat valmiita, voit valita, mitkä raporttinäkymät ja raportit haluat julkaista. Julkaise ne sitten sovelluksena. 

1. Määritä työtilan luettelonäkymässä, mitkä koontinäytöt ja raportit haluat **sisällyttää sovellukseen**.

    ![Julkaistavan koontinäytön valinta](media/service-create-distribute-apps/power-bi-apps-incude-dashboard.png)

    Jos päätät olla sisällyttämättä raporttia, jossa on siihen liittyvä koontinäyttö, näet raportin vieressä varoituksen. Voit silti julkaista sovelluksen, mutta siihen liittyvässä koontinäytössä ei ole kyseisen raportin ruutuja.

    ![Työhön liittyvää koontinäyttöä koskeva varoitus](media/service-create-distribute-apps/power-bi-apps-report-warning.png)

2. Valitse **Julkaise sovellus** -painike työtilan oikeasta yläkulmasta, jos haluat luoda ja julkaista sovelluksen kyseisestä työtilasta.
   
    ![Julkaise sovellus](media/service-create-distribute-apps/power-bi-apps-publish-button.png)

3. Kirjoita **Asennus**-kohtaan nimi ja kuvaus, jotta ihmisten on helpompi löytää sovellus. Voit mukauttaa sovellusta määrittämällä sille haluamasi teemavärin. Voit myös lisätä linkin tukisivustoon.
   
    ![Sovelluksen luominen](media/service-create-distribute-apps/power-bi-apps-build-your-apps.png)

4. Kohdassa **Siirtyminen** valitset sovelluksen osana julkaistavan sisällön. Sitten lisäät sovelluksen siirtymisen järjestääksesi sisällön osiin. Lue lisätietoja tämän artikkelin kohdasta [Suunnittele sovelluksen siirtymistoiminnot](#design-the-navigation-experience).
   
    ![Siirtyminen sovelluksessa](media/service-create-distribute-apps/power-bi-apps-navigation.png)

5. **Käyttöoikeus**-kohdassa päätät, keillä on sovelluksen käyttöoikeus ja mitä he voivat sovelluksella tehdä. 

    - [Perinteisissä työtiloissa](service-create-workspaces.md): kaikki organisaatiosi henkilöt, tietyt henkilöt tai Azure Active Directory:n (Azure AD) käyttöoikeusryhmät.
    - [Uusissa työtilakokemuksissa](service-create-the-new-workspaces.md): tietyt henkilöt, Azure AD -käyttöoikeusryhmät ja jakeluluettelot ja Office 365 -ryhmät. Kaikille työtilan käyttäjille annetaan automaattisesti työtilan sovelluksen käyttöoikeudet.
    - Voit antaa sovelluksen käyttäjien muodostaa yhteyden sovelluksen pohjana oleviin tietojoukkoihin muodostamisoikeuden avulla. He näkevät nämä tietojoukot etsiessään jaettuja tietojoukkoja. Lisätietoja [luvan myöntämisestä käyttäjille sovelluksen tietojoukkoihin yhdistämistä varten](#allow-users-to-connect-to-datasets) on tässä artikkelissa.
    - Muodostamisoikeudet saaneilla käyttäjillä voi olla myös oikeus kopioida raportteja tästä sovelluksesta toiseen työtilaan. Lisätietoja [luvan myöntämisestä käyttäjille sovelluksessa olevien raporttien kopioimista varten](#allow-users-to-copy-reports) on tässä artikkelissa.
    
    >[!IMPORTANT]
    >Jos sovellus käyttää muissa työtiloissa olevia tietojoukkoja, sinun on varmistettava, että sovelluksen käyttäjille on pohjana olevien tietojoukkojen käyttöoikeudet.
    >

6. Voit asentaa sovelluksen automaattisesti vastaanottajille, jos Power BI -järjestelmänvalvojasi on ottanut asetuksen käyttöön sinulle Power BI -hallintaportaalissa. Lue lisää [sovelluksen asentamisesta automaattisesti](#automatically-install-apps-for-end-users) tästä artikkelista.

    ![Sovelluskäyttöoikeudet](media/service-create-distribute-apps/power-bi-apps-permissions.png)

7. Kun valitset kohdan **Julkaise sovellus**, näet sanoman, että sovellus on valmis julkaistavaksi. **Jaa sovellus** -valintaikkunassa voit kopioida URL-osoitteen, joka on suora linkki tähän sovellukseen.
   
    ![Sovellus on valmis](media/service-create-distribute-apps/power-bi-apps-success.png)

Voit lähettää kyseisen suoran linkin henkilöille, joille olet jakanut sen, tai he voivat löytää sovelluksesi Sovellukset-välilehdestä siirtymällä kohtaan **Lataa ja etsi lisää sovelluksia AppSourcesta**. Lisätietoja [sovellusominaisuudesta yrityskäyttäjille](../consumer/end-user-apps.md).

## <a name="change-your-published-app"></a>Julkaistun sovelluksen muuttaminen
Kun olet julkaissut sovelluksesi, voit halutessasi muuttaa tai päivittää sitä. Sen päivittäminen on helppoa, jos olet järjestelmänvalvoja tai uuden työtilan jäsen. 

1. Avaa kyseistä sovellusta vastaava työtila. 
   
    ![Työtilan avaaminen](media/service-create-distribute-apps/power-bi-apps-open-workspace.png)

2. Tee koontinäytöihin tai raportteihin haluamasi muutokset.
 
    Työtila on valmistelualueesi, joten tekemiäsi muutoksia ei lähetetä reaaliaikaisesti sovellukseen ennen sen julkaisemista uudelleen. Tämän avulla voit tehdä muutoksia ilman, että ne vaikuttaisivat julkaistuun sovellukseen.  
 
    > [!IMPORTANT]
    > Jos poistat raportin ja päivität sovellusta ja vaikka lisäisit raportin takaisin sovellukseen, sovelluksen kuluttajat menettävät kaikki mukautukset, kuten kirjanmerkit, kommentit ja niin edelleen.  
 
3. Siirry takaisin työtilan sisältöluetteloon ja valitse **Päivitä sovellus** oikeasta yläkulmasta.
   
1. Päivitä **Asennus**, **Siirtyminen** ja **Käyttöoikeudet** mikäli tarpeen ja valitse sitten **Päivitä sovellus**.
   
Henkilöt, joille olet sovelluksen julkaissut, näkevät automaattisesti sovelluksen päivitetyn version. 

## <a name="design-the-navigation-experience"></a>Suunnittele siirtymistoiminnot
**Uusi siirtymisen muodostin** -asetuksen avulla voit luoda sovellukseen mukautetun siirtymisen. Mukautetun siirtymisen ansiosta käyttäjät voivat etsiä ja käyttää sisältöä helpommin sovelluksessa. Aiemmin luoduissa sovelluksissa tämä asetus on poissa käytöstä, ja uusissa sovelluksissa asetus on oletusarvoisesti käytössä.

Kun asetus on poistettu käytöstä, voit valita **sovelluksen aloitussivuksi** joko **tietyn sisällön**, esimerkiksi koontinäytön tai raportin tai valita **Ei mitään**, jolloin käyttäjälle näytetään tavallinen luettelo sisällöstä.

Kun otat käyttöön **Uusi siirtymisen muodostin** -asetuksen, voit suunnitella mukautetun siirtymisen. Oletusarvon mukaan sovellukseen sisällyttämäsi raportit, koontinäytöt ja Excel-työkirjat on merkitty jäsentämättömään luetteloon. 

![Siirtyminen sovelluksessa](media/service-create-distribute-apps/power-bi-apps-navigation.png)

Voit mukauttaa sovelluksessa siirtymistä seuraavilla tavoilla:

* Nimikkeiden uudelleen järjestäminen ylös- ja alas-nuolta käyttämällä. 
* Kohteiden nimeäminen uudelleen kohdissa **Raportin tiedot**, **Koontinäytön tiedot**, ja **Työkirjan tiedot**.
* Eräiden kohteiden piilottaminen siirtymisruudusta.
* **Uusi**-asetuksen käyttäminen **osien** lisäämiseksi ryhmään liittyvään sisältöön.
* **Uusi**-asetuksen käyttäminen **linkin** lisäämiseksi ulkoiseen resurssiin siirtymisruutuun. 

Kun lisäät **linkin** kohdassa **Linkin tiedot**, voit valita, mihin linkki avautuu. Oletuksena linkki avautuu **nykyiseen välilehteen**, mutta voit valita vaihtoehdon **Uusi välilehti** tai **Sisältöalue**. 

### <a name="considerations-for-using-the-new-navigation-builder-option"></a>Huomioitavaa uuden siirtymisen muodostimen käytöstä
Tässä yleisiä asioita, jotka tulisi pitää mielessä uutta siirtymisen muodostinta käytettäessä:

* Raporttisivut näkyvät sovelluksen siirtymisalueella laajennettavana osana. Kun raportissa on yksi näkyvä sivu, vain raportin nimi näytetään. Raportin nimen napsauttaminen siirtymisruudussa avaa raportin ensimmäisen sivun. 

    > [!NOTE]
    > Raportissasi voi olla vain yksi näkyvä sivu, koska olet määrittänyt siirtymisen muille sivuille, joilla on painikkeita tai porautumistoimintoja.

* Jos otat uuden siirtymisen muodostimen pois käytöstä ja sitten julkaiset tai päivität sovelluksen, menetät tekemäsi mukautukset. Esimerkiksi osat, järjestykset, linkit ja mukautetut siirtymiskohteiden nimet menetetään.
* Käytettävissä on vaihtoehto, jolla sovelluksen muodostin jätetään käyttämättä.

Kun lisäät linkkejä sovelluksen siirtymisruutuun ja valitset Sisältöalue-asetuksen:
* Varmista, että linkki voidaan upottaa. Jotkin palvelut estävät sisältöjensä upottamisen kolmansien osapuolten sivustoihin, kuten Power BI:hin.
* Power BI -palvelun sisällön kuten raporttien tai koontinäyttöjen upottamista muihin työtiloihin ei tueta. 
* Upota Power BI -raporttipalvelimen sisältö sen alkuperäisen upotus-URL-osoitteen kautta paikallisesta käyttöönotosta. Hanki URL-osoite seuraamalla artikkelissa [Power BI -raporttipalvelimen URL:n luominen](https://docs.microsoft.com/power-bi/report-server/quickstart-embed#create-the-power-bi-report-url) kerrottuja vaiheita. Huomaa, että normaalit todentamissäännöt ovat voimassa, joten sisällön tarkasteleminen vaatii VPN-yhteyden paikalliseen palvelimeen. 
* Upotetun sisällön yläosassa näytetään suojausvaroitus, joka ilmaisee, ettei sisältö ole Power BI:ssä.

## <a name="automatically-install-apps-for-end-users"></a>Sovellusten asentaminen automaattisesti käyttäjille
Jos järjestelmänvalvoja antaa sinulle oikeudet, voit asentaa sovelluksia automaattisesti *työntämällä* ne käyttäjille. Työntötoiminto helpottaa oikeiden sovellusten jakamista oikeille henkilöille tai ryhmille. Sovelluksesi tulee näkyviin automaattisesti käyttäjien Sisältösovellukset-luetteloon. Heidän ei tarvitse etsiä sovellusta Microsoft AppSourcesta tai napsauttaa asennuslinkkiä. Katso Power BI -hallintaportaalin artikkelista, miten järjestelmänvalvojat ottavat käyttöön [sovellusten työntämisen käyttäjille](../admin/service-admin-portal.md#push-apps-to-end-users).

### <a name="how-to-push-an-app-automatically-to-end-users"></a>Miten voit työntää sovelluksen automaattisesti käyttäjille
Kun järjestelmänvalvoja on antanut sinulle oikeudet, voit halutessasi **asentaa sovelluksen automaattisesti**. Kun valitset ruudun ja valitset **Julkaise sovellus** (tai **Päivitä sovellus**), sovellus työnnetään kaikille käyttäjille tai ryhmille, jotka on määritetty sovelluksen **Käyttöoikeudet**-osassa **Käyttöoikeus**-välilehdessä.

![Sovellusten lähettämisen käyttöön ottaminen](media/service-create-distribute-apps//power-bi-apps-access.png)

### <a name="how-users-get-the-apps-that-you-push-to-them"></a>Näin käyttäjät saavat sovellukset, jotka lähetät heille
Kun olet työntänyt sovelluksen, se näkyy automaattisesti heidän Sovellukset-luettelossaan. Näin voit järjestää sovellukset, jotka tietyillä käyttäjillä tai tehtävärooleilla organisaatiossasi on oltava käytettävissään.

![Sovellusten lähettämisen käyttöön ottaminen](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

### <a name="considerations-for-automatically-installing-apps"></a>Huomioon otettavaa sovellusten automaattisesta asentamisesta
Sovelluksia lähetettäessä käyttäjille kannattaa ottaa huomioon seuraavat asiat:

* Sovelluksen asentaminen käyttäjille automaattisesti voi viedä aikaa. Useimmat sovellukset asennetaan käyttäjille välittömästi, mutta sovellusten työntäminen voi viedä aikaa.  Se riippuu sovelluksessa olevien kohteiden määrästä ja käyttöoikeudet omistavien käyttäjien määrästä. Suosittelemme sovellusten lähettämistä ruuhka-aikojen ulkopuolella, jolloin on paljon aikaa ennen kuin käyttäjät tarvitsevat sovelluksia. Varmista useilta käyttäjiltä, ennen kuin lähetät tiedon laajalle käyttäjäkunnalle sovelluksen saatavuudesta.

* Päivitä selain. Ennen kuin lähetetty sovellus näkyy Sovellukset-luettelossa, käyttäjän pitää ehkä päivittää tai sulkea ja avata selaimensa uudelleen.

* Jos käyttäjät eivät heti näe sovellusta Sovellukset-luettelossa, heidän tulee päivittää tai sulkea ja avata selaimensa uudelleen.

* Pyri siihen, ettet lähetä liikaa sovelluksia käyttäjille. Varo, ettet lähetä liian monia sovelluksia, jotta käyttäjäsi havaitsevat, että esiasennetut sovellukset heille hyödyllisiä. Kannattaa rajoittaa sitä, kuka voi lähettää sovelluksia käyttäjille, jotta ajoitukset voidaan paremmin koordinoida. Muodosta yhteyspiste organisaatiossasi niiden sovellusten saamiseen, jotka on julkaistu käyttäjille.

* Vieraskäyttäjät, jotka eivät ole hyväksyneet kutsua, eivät saa asennuksia automaattisesti asennettuina.  

## <a name="allow-users-to-connect-to-datasets"></a>Salli käyttäjien muodostaa yhteys tietojoukkoihin

Kun valitset asetuksen, joka antaa **käyttäjille oikeuden yhdistää sovelluksen pohjana oleviin tietojoukkoihin**, sovelluksen käyttäjät saavat pohjana olevan tietojoukon *muodostamisoikeudet*. Tämän oikeuden avulla he voivat suorittaa useita keskeisiä toimintoja:

- [Sovelluksen tietojoukkoja voi käyttää](../connect-data/service-datasets-across-workspaces.md) raporttien pohjana.
- Näitä tietojoukkoja voi hakea Power BI Desktopissa ja Power BI -palvelun tietojen noutotoiminnossa.
- Raportteja ja koontinäyttöjä voi luoda näiden tietojoukkojen perusteella.

Kun poistat tämän asetuksen valinnan, sovellukseen lisäämäsi uudet käyttäjät eivät enää saa muodostamisoikeutta. Sovelluksen olemassa olevilla käyttäjillä pohjana olevien tietojoukkojen oikeudet eivät muutu. Voit poistaa muodostamisoikeuden manuaalisesti sovellusten käyttäjiltä, jotka eivät enää tarvitse niitä. Lue lisätietoja [muodostamisoikeudesta](../connect-data/service-datasets-build-permissions.md).

## <a name="allow-users-to-copy-reports"></a>Salli käyttäjien kopioida raportteja

Jos valitset **Salli käyttäjien luoda sovelluksessa olevien raporttien kopioita** -asetuksen, käyttäjät voivat tallentaa minkä tahansa sovelluksessa olevista raporteista Omaan työtilaansa tai mihin tahansa muuhun työtilaan. Käyttäjät tarvitsevat kopion luomiseen Pro-käyttöoikeuden, vaikka alkuperäinen raportti olisi Premium-kapasiteetin työtilassa. Tämän jälkeen he voivat mukauttaa raporttia tarpeidensa mukaan. **Salli kaikkien käyttäjien yhdistää sovelluksen pohjana oleviin tietojoukkoihin muodostamisoikeuksien avulla** -asetus on valittava ensin. Valitsemalla nämä vaihtoehdot otat käyttöön uuden [Raporttien kopioiminen muista työtiloista](../connect-data/service-datasets-copy-reports.md) -toiminnon.

## <a name="unpublish-an-app"></a>Sovelluksen julkaisun peruuttaminen
Kuka tahansa työtilan jäsen voi peruuttaa sovelluksen julkaisun.

>[!IMPORTANT]
>Jos peruutat sovelluksen julkaisun, sovelluksen käyttäjät menettävät omat muokkauksensa. He menettävät kaikki sovelluksen sisältöön liittyvät omat kirjanmerkit, kommentit ja tilaukset. Peruuta sovelluksen julkaisu vain, jos sinun on poistettava sovellus.
> 

* Valitse työtilassa kolme pistettä ( **...** ) oikeasta yläkulmasta > **Peruuta sovelluksen julkaisu**.
  
    ![Peruuta sovelluksen julkaisu](media/service-create-distribute-apps/power-bi-app-unpublish.png)

Tämä toiminto poistaa sovelluksen asennuksen kaikilta, joille se on julkaistu eivätkä he enää pysty käyttämään sitä. Se ei poista työtilaa tai sen sisältöä.

## <a name="view-your-published-app"></a>Julkaistun sovelluksen tarkasteleminen

Kun sovelluksen kuluttajat avaavat sovelluksesi, he näkevät luomasi siirtymisruudun Power BI:n siirtymisruudun sijaan. Sovelluksen siirtymäruutu luetteloi määrittämiesi osien raportit ja koontinäytöt. Siinä luetellaan myös jokaisen raportin yksittäiset sivut pelkän raportin nimen sijaan. Voit laajentaa ja kutistaa vasemman navigointiruudun valikkorivin nuolten avulla.

![Sovellus, jossa voi siirtyä](media/service-create-distribute-apps/power-bi-new-apps-navigation.png)

Koko näytön tilassa voit näyttää tai piilottaa siirtymisruudun valitsemalla vaihtoehdon kulmassa.

![Siirtyminen koko näytön tilassa](media/service-create-distribute-apps/full-screen-app-show-navigation.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset
Sovellusten julkaisemisessa muistettavat asiat:

* Käyttöoikeussivu ei muuta muiden työtilojen tietojoukkojen käyttöoikeuksia. Näyttöön tulee varoitus, joka muistuttaa sinua kyseisten tietojoukkojen käyttöoikeuksien myöntämisestä erikseen. Paras käytäntö on ottaa yhteyttä tietojoukon omistajaan ennen sovelluksen luomista. Siten voit varmistaa, että kyseisen tietojoukon käyttöoikeuksien antaminen kaikille sovelluksesi käyttäjille sopii omistajalle. 
* Sovelluksen käyttöoikeusluettelossa voi olla enintään 100 käyttäjää tai ryhmää. Voit silti antaa yli 100 käyttäjälle sovelluksen käyttöoikeuden. Voit tehdä tämän käyttämällä vähintään kahta käyttäjäryhmää, jotka sisältävät kaikki halutut käyttäjät.
* Työtilan uusi käyttökokemus on, että jos sovelluksen käyttöoikeusluetteloon lisätyllä käyttäjällä on jo sovelluksen käyttöoikeus työtilan kautta, häntä näy sovelluksen käyttöoikeusluettelossa.  
* Kun käytät Power BI -palvelun uutta ulkoasua, tukisivuston URL-osoite näkyy kohteen tietokortissa. Lue lisää [Power BI:n uudesta ulkoasusta](../consumer/service-new-look.md).
* Sovelluksissa on asetus, joka sallii käyttäjien jakaa sovelluksen ja sovelluksen pohjana olevat tietojoukot jakamisoikeuden avulla. Uusissa sovelluksissa tämä asetus on oletusarvoisesti poissa käytöstä. Suosittelemme, että otat tämän asetuksen pois käytöstä olemassa olevissa sovelluksissasi ja päivität pohjana olevien tietojoukkojen käyttöoikeudet. Asetus on otettu käyttöön olemassa olevia sovelluksia varten, koska sovellukset suunniteltiin alun perin korvaamaan sisältöpaketteja, joilla oli tämä toiminto.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Luo työtila](service-create-workspaces.md)
* [Asenna ja käytä sovelluksia Power BI:ssä](../consumer/end-user-apps.md)
* [Power BI -sovellukset ulkoisille palveluille](../connect-data/service-connect-to-services.md)
* [Power BI -hallintaportaali](https://docs.microsoft.com/power-bi/service-admin-portal)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
