---
title: Julkaise Power BI-sovellus
description: Opi julkaisemaan uusia sovelluksia, jotka ovat-koontinäyttöjä ja raportteja, joissa sisäinen siirtymistä.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: f3f933a3e3af2ef1d7864b379e9b8b5520d505ff
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65941565"
---
# <a name="publish-an-app-in-power-bi"></a>Julkaise Power BI-sovellus

Power BI-voit luoda paketoida virallisesti sisällön ja jakaa sen kuin laajalle yleisölle *sovelluksen*. Voit luoda sovelluksia *sovellustyötiloissa*, joissa voit työstää Power BI -sisältöä yhdessä työtovereiden kanssa. Sen jälkeen voit julkaista valmiit sovellukset suurelle määrälle ihmisiä organisaatiossasi. 

![Power BI -sovellukset](media/service-create-distribute-apps/power-bi-new-apps.png)

Yrityskäyttäjät tarvitsevat usein monia Power BI -koontinäyttöjä ja raportteja yrityksensä pyörittämisessä. Power BI -sovelluksilla voit luoda kokoelmia koontinäytöistä ja raporteista ja julkaista nämä sovellukset koko organisaatiolle tai tietyille ihmisille tai ryhmille. Jos olet raporttien luoja tai järjestelmänvalvoja, sovellukset tekevät näiden kokoelmien käyttöoikeuksien hallinnasta helpompaa.

Käyttäjät voivat saada sovelluksesi muutamalla eri tavalla:

- He voivat etsiä ja asentaa sovelluksesi Microsoft AppSource
- Voit lähettää heille suoran linkin.
- Voit asentaa sen automaattisesti työtovereittesi Power BI -tileille, jos Power BI -järjestelmänvalvojasi antaa sinulle luvan.

Voit luoda sovelluksen oma sisäinen siirtyminen jotta käyttäjät voivat vaivattomasti niiden sisällön. Niitä ei voi muokata sovelluksen sisältöä. He voivat käsitellä sitä joko Power BI-palvelussa tai mobiilisovelluksissa – – suodatusta, korostusta ja lajitella tiedot itse. He saavat päivitykset automaattisesti, ja sinä voit määrittää, kuinka usein tiedot päivitetään. Lisätietoja [sovellusominaisuudesta yrityskäyttäjille](consumer/end-user-apps.md).

## <a name="licenses-for-apps"></a>Sovellusten käyttöoikeudet
Voit luoda tai päivittää sovelluksen, sinun on Power BI Pro-käyttöoikeus. Sovelluksen *kuluttajien*, on kaksi vaihtoehtoa.

* Vaihtoehto 1: Kaikilla käyttäjillä pitää olla **Power BI Pro** -käyttöoikeudet sovelluksesi näkemiseksi. 
* Vaihtoehto 2: Jos sovellustyötilan sijaitsee Power BI Premium-kapasiteettiin, organisaatiosi ilmaiskäyttäjät sovelluksen sisältöä voi tarkastella. Lisätietoja on artikkelissa [Mikä on Power BI Premium?](service-premium.md)

## <a name="publish-your-app"></a>Sovelluksen julkaiseminen
Kun työtilasi raporttinäkymät ja raportit ovat valmiita, voit valita, mitkä raporttinäkymät ja raportit haluat julkaista. Julkaise ne sitten sovelluksena. 

1. Työtilan luettelonäkymässä päättää, mitkä koontinäytöt ja raportit haluat **sisältyy sovellukseen**.

     ![Julkaistavan koontinäytön valinta](media/service-create-distribute-apps/power-bi-apps-incude-dashboard.png)

     Jos et halua sisältää raportti, jossa on Aiheeseen liittyvä raporttinäkymä, näet raportin vieressä varoituksen. Voit silti julkaista sovelluksen, mutta siihen liittyvästä koontinäytöstä ei ole kyseisen raportin ruudut.

     ![Työhön liittyvää koontinäyttöä koskeva varoitus](media/service-create-distribute-apps/power-bi-apps-report-warning.png)

2. Valitse **Julkaise sovellus** painiketta oikeassa yläkulmassa Aloita luominen ja julkaiseminen sovelluksen työtilasta.
   
     ![Julkaise sovellus](media/service-create-distribute-apps/power-bi-apps-publish-button.png)

3. Valitse **asennus**, täytä nimi ja kuvaus, jotka löytyvät sovelluksen. Voit määrittää teeman väri mukauttamiseksi. Voit myös lisätä linkin tuki-sivustoon.
   
     ![Sovelluksesi](media/service-create-distribute-apps/power-bi-apps-build-your-apps.png)

4. Valitse **Siirtyminen**, voit valita julkaistaan osana sovellusta sisältöä. Sitten voit lisätä app siirtyminen, järjestää sisältöä osioissa. Katso [suunnitella sovelluksen siirtymistoiminnot](#design-the-navigation-experience-for-your-app) Lisätietoja tässä artikkelissa.
   
     ![Sovelluksen siirtyminen](media/service-create-distribute-apps/power-bi-apps-navigation.png)

5. Valitse **Access**, päättää, joilla on sovelluksen käyttöoikeus. 
    - - [Perinteinen työtilat](service-create-workspaces.md): kaikki organisaatiolle tai tietyille henkilöille ja Azure Active Directory (AAD)-käyttöoikeusryhmät.
    - Tässä [uuden kokemuksen työtilat](service-create-the-new-workspaces.md): tietyille henkilöille, AAD-käyttöoikeusryhmät ja jakeluluettelot ja Office 365-ryhmiä.

6. Jos sinulla on oikeudet, voit asentaa sovelluksen automaattisesti vastaanottajille. Power BI -järjestelmänvalvoja voi ottaa tämän asetuksen käyttöön Power BI -hallintaportaalissa. Lue lisää [sovelluksen asentaminen automaattisesti](#automatically-install-apps-for-end-users) tässä artikkelissa.

     ![Sovelluksen käyttöoikeudet](media/service-create-distribute-apps/power-bi-apps-permissions.png)

7. Kun valitset **Julkaise sovellus**, näet sanoman, että sovellus on valmis julkaistavaksi. Tässä **Jaa sovellus** valintaikkunasta voit kopioida URL-osoite, joka on suora linkki tähän sovellukseen.
   
     ![Sovellus on valmis](media/service-create-distribute-apps/power-bi-apps-success.png)

Voit lähettää suoran linkin henkilöt, joille olet jakanut sen, että he voivat löytää sovelluksesi sovellukset-välilehdessä siirtymällä **Lataa ja Etsi lisää sovelluksia appsourcesta**. Lisätietoja [sovellusominaisuudesta yrityskäyttäjille](consumer/end-user-apps.md).

## <a name="change-your-published-app"></a>Julkaistun sovelluksen muuttaminen
Kun olet julkaissut sovelluksesi, voit halutessasi muuttaa tai päivittää sitä. On helppo Jos olet järjestelmänvalvoja tai uuden sovelluksen työtilan jäsen. 

1. Avaa kyseistä sovellusta vastaava sovelluksen työtila. 
   
     ![Työtilan avaaminen](media/service-create-distribute-apps/power-bi-apps-open-workspace.png)

2. Tee haluamasi muutokset koontinäyttöjä tai raportteja.
 
     Sovelluksen työtila on valmistelualueesi, joten tekemiäsi muutoksia ei lähetetä reaaliaikaisesti sovellukseen ennen sen julkaisemista uudelleen. Tämän avulla voit tehdä muutoksia ilman, että ne vaikuttaisivat julkaistuun sovellukseen.  
 
    > [!IMPORTANT]
    > Jos poistat raportin ja päivittää sovellusta, vaikka voit lisätä raportin takaisin sovelluksen, sovelluksen käyttäjät menettää kaikki mukautukset, kuten kirjanmerkkejä, kommentteja ja niin edelleen.  
 
3. Siirry takaisin sovelluksen työtilan sisältöluetteloon ja valitse **Päivitä sovellus** oikeassa yläkulmassa.
   
1. Päivitä **asennus**, **Siirtyminen**, ja **käyttöoikeudet**, jos sinulla on ja valitse sitten **Päivitä sovellus**.
   
Henkilöt, joille olet sovelluksen julkaissut, näkevät automaattisesti sovelluksen päivitetyn version. 

## <a name="design-the-navigation-experience-for-your-app"></a>Suunnittele sovelluksen siirtymistoiminnot
**Uusi siirtyminen muodostin** vaihtoehdon avulla voit luoda mukautetun navigoinnin sovelluksessa. Mukautettu siirtyminen ansiosta käyttäjät voivat etsiä ja käyttää sisältöä sovelluksen. Nykyiset sovellukset on tämä asetus käytöstä ja sovellusten oletusarvoisiksi oleminen-vaihtoehtoa.

Kun asetus on poistettu käytöstä, voit valita **sovelluksen aloitussivu** on joko **tietty sisältö**, esimerkiksi koontinäytön tai raportin tai valitse **ei mitään** näyttämään perustason luettelo käyttäjän sisältö.

Kun otat käyttöön **uusi siirtyminen muodostin**, voit suunnitella mukautettu siirtyminen. Oletusarvon mukaan raporttien, koontinäyttöjen ja Excel-työkirjojen sisältyvät sovelluksesi on merkitty luettelona. 

![Sovelluksen siirtyminen](media/service-create-distribute-apps/power-bi-apps-navigation.png)

Voit mukauttaa sovelluksen siirtymistä mukaan:
* Nimikkeiden ylös / alas nuolta. 
* Kohteiden nimeäminen uudelleen **raportin tiedot**, **koontinäytön tiedot**, ja **työkirjan tiedot**.
* Piilottaminen eräät siirtymisruudussa.
* Käyttämällä **uusi** mahdollisuus lisätä **osia** ryhmään Aiheeseen liittyvä sisältö.
* Käyttämällä **uusi** mahdollisuus lisätä **linkki** ulkoiseen resurssiin, vasemmassa siirtymisruudussa. 

Kun lisäät **linkki**- **linkki tiedot** voit valita mihin linkki avaa. Oletuksena linkeistä avaaminen **nykyinen välilehti**, mutta voit valita **uudessa välilehdessä**, tai **sisällön alueen**. 

### <a name="considerations-for-using-the-new-navigation-builder-option"></a>Huomioitavaa uusi siirtyminen builder-vaihtoehto
Pidä mielessä, kun uusi siirtyminen muodostimella Yleiset asiat:
* Raporttisivujen näkyvät sovelluksen siirtyminen alueen laajennettavia osassa
* Jos uusi siirtyminen muodostin käytöstä ja julkaista tai päivittää sovelluksesi, menetät tekemäsi mukautukset. Esimerkiksi osia, järjestys, linkit ja kohteista omia nimiä menetetään kaikki.

Kun lisäät linkit sovelluksen siirtymisen ja valitsemalla sisältöalue-vaihtoehdon:
* Varmista, että linkki voidaan upottaa. Jotkin palvelut estä niiden kolmansien osapuolten sivustoille, kuten Power BI-sisällön upottaminen.
* Upottaminen Power BI-palvelun sisältösi kuten raportteihin tai koontinäyttöihin muut työtilat ei tueta. 
* Upota Power BI-raporttipalvelimen sisällön kautta sen alkuperäisen upottaminen URL-osoite käytössä paikallisen käyttöönoton. Käytä vaiheita [luominen Power BI raporttipalvelimen URL](https://docs.microsoft.com/power-bi/report-server/quickstart-embed#creating-the-power-bi-report-server-report-url) saat URL-osoite. Huomaa, että säännöllisesti todentamisen sääntöjä sovelletaan, niin sisällön tarkasteleminen vaatii VPN-yhteyden paikalliseen palvelimeen. 
* Upotettua sisältöä yläosassa näytetään Suojausvaroitus ilmaista Power BI-sisältö ei ole.



## <a name="automatically-install-apps-for-end-users"></a>Sovellusten asentaminen automaattisesti käyttäjille
Jos järjestelmänvalvoja antaa sinulle oikeudet, voit asentaa sovelluksia automaattisesti *lähettäminen* ne käyttäjille. Push-toiminto helpompaa jakaa oikeat sovellukset oikeille henkilöille tai ryhmille. Sovelluksesi näkyy automaattisesti loppuun käyttäjien sovellusten sisällön luettelo. Heidän ei tarvitse löytämilläni Microsoft AppSource-tai asennuksen-linkkiä. Katso, miten järjestelmänvalvojien ottaa [sovellusten lähettäminen käyttäjille](service-admin-portal.md#push-apps-to-end-users) Power BI-järjestelmänvalvojan portaalin artikkelissa.

### <a name="how-to-push-an-app-automatically-to-end-users"></a>Miten voit lähettää sovelluksen automaattisesti käyttäjille
Kun järjestelmänvalvoja on antanut sinulle oikeudet, voit halutessasi **asentaa sovelluksen automaattisesti**. Kun valintaruutu ja valitse **Julkaise sovellus** (tai **Päivitä sovellus**), sovelluksen siirtämisen kaikkien käyttäjien tai ryhmien määritetty **käyttöoikeudet** osasta sovelluksen**Access** välilehti.

![Sovellusten lähettämisen käyttöön ottaminen](media/service-create-distribute-apps//power-bi-apps-access.png)

### <a name="how-users-get-the-apps-that-you-push-to-them"></a>Miten käyttäjät saavat sovellukset, jotka olet lähettänyt heille
Kun olet lähettänyt sovelluksen, se näkyy niiden sovellusten luettelo automaattisesti. Tällä tavalla voit järjestää oltava käytettävissään sovelluksia kyseisen tietyille käyttäjille tai työn roolit-organisaation haluat on käytettävissään.

![Sovellusten lähettämisen käyttöön ottaminen](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

### <a name="considerations-for-automatically-installing-apps"></a>Huomioon otettavaa sovellusten automaattisesta asentamisesta
Sovelluksia lähetettäessä käyttäjille kannattaa ottaa huomioon seuraavat asiat:

* Sovelluksen asentaminen käyttäjille automaattisesti voi viedä aikaa. Useimmat sovellukset välittömästi Asenna käyttäjät, mutta lähettämisen sovelluksia voi viedä aikaa.  Se riippuu sovelluksessa olevien kohteiden määrästä ja käyttöoikeudet omistavien käyttäjien määrästä. Suosittelemme sovellusten lähettämistä ruuhka-aikojen ulkopuolella, jolloin on paljon aikaa ennen kuin käyttäjät tarvitsevat sovelluksia. Varmista useilta käyttäjiltä, ennen kuin lähetät tiedon laajalle käyttäjäkunnalle sovelluksen saatavuudesta.

* Päivitä selaimen sivu. Ennen kuin lähetetty sovellus näkyy Sovellukset-luettelossa, käyttäjän pitää ehkä päivittää tai sulkea ja avata selaimensa uudelleen.

* Jos käyttäjät heti näe sovellusta sovellukset-luettelossa, ne tulee päivittää tai sulkea ja avata selaimensa uudelleen.

* Pyri siihen, ettet lähetä liikaa sovelluksia käyttäjille. Varo, ettet lähetä liian monia sovelluksia, jotta käyttäjäsi havaitsevat, että esiasennetut sovellukset heille hyödyllisiä. Kannattaa rajoittaa sitä, kuka voi lähettää sovelluksia käyttäjille, jotta ajoitukset voidaan paremmin koordinoida. Muodostaa yhteyspisteen hankkimiseen sovelluksia organisaation käyttäjille siirtämisen.

* Vieraskäyttäjät, jotka eivät ole hyväksyneet kutsua eivät saa asennuksia automaattisesti asennettuina.  

## <a name="unpublish-an-app"></a>Sovelluksen julkaisun peruuttaminen
Kuka tahansa sovelluksen työtila jäsen voi peruuttaa sovelluksen julkaisun.

>[!IMPORTANT]
>Jos peruutat sovelluksen julkaisun, sovelluksen käyttäjät menettävät omat muokkauksensa. Hän menettää omat kirjanmerkit, kommentteja tai sovelluksen sisällön valmistelualueita liitetyt. Peruuta sovelluksen julkaisu vain, jos sinun on poistettava sovellus.
> 
> 

* Valitse sovelluksen työtilassa kolme pistettä ( **...** ) oikeasta yläkulmasta > **Peruuta sovelluksen julkaisu**.
  
     ![Peruuta sovelluksen julkaisu](media/service-create-distribute-apps/power-bi-app-unpublish.png)

Tämä toiminto poistaa sovelluksen asennuksen kaikilta, joille se on julkaistu eivätkä he enää pysty käyttämään sitä. Se ei poista sovelluksen työtilaa tai sen sisältöä.

## <a name="view-your-published-app"></a>Tarkastele julkaistun sovelluksen

Kun sovelluksen käyttäjät avaavat sovelluksen, he näkevät siirtymistä luomasi sijaan standard Power BI vasemmassa siirtymisruudussa. Sovelluksen siirtymistä luettelo raporttien ja koontinäyttöjen olet määrittänyt osia. Siinä luetellaan yksittäiset sivut raporttien, sen sijaan, vain raporttinimi.

![Sovelluksen siirtyminen](media/service-create-distribute-apps/power-bi-new-apps-navigation.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Sovelluksen työtilan luominen](service-create-workspaces.md)
* [Asenna ja käytä sovelluksia Power BI:ssä](consumer/end-user-apps.md)
* [Power BI -sovellukset ulkoisille palveluille](service-connect-to-services.md)
* [Power BI -hallintaportaali](https://docs.microsoft.com/power-bi/service-admin-portal)
* Ilmenikö kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
