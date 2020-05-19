---
title: Käyttöönottojaksojen parhaat käytännöt
description: Power BI:n käyttöönottojaksojen parhaat käytännöt
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.date: 05/06/2020
ms.openlocfilehash: e76d820e804a19db148e0db4c2702e002ee2c017
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83275911"
---
# <a name="deployment-pipelines-best-practices-preview"></a>Käyttöönottojaksojen parhaat käytännöt (esiversio)

Tässä artikkelissa annetaan ohjeita BI-luojille, jotka hallinnoivat sisältöään koko sen elinkaaren ajan. Siinä keskitytään käyttöönottojaksojen hyödyntämiseen BI-sisällön elinkaaren hallintatyökaluna.

Artikkeli on jaettu neljään osaan:

* **Sisällön valmistelu** – valmistele sisältösi elinkaaren hallintaa varten.

* **Kehitys** – opi parhaita tapoja luoda sisältöä käyttöönottojaksojen kehitysvaiheessa.

* **Testaa** – tutustu käyttöönottojaksojen testivaiheen käyttöön, jotta voit testata ympäristöäsi.

* **Tuotanto** – käytä käyttöönottojaksojen tuotantovaihetta, kun sisältösi on käytettävissä kulutusta varten.

## <a name="content-preparation"></a>Sisällön valmistelu

Valmistele sisältösi jatkuvaa hallintaa varten koko sen elinkaaren ajaksi. Muista tutustua tämän osan tietoihin ennen kuin teet jonkin seuraavista:

* sisällön julkaiseminen tuotantoon

* tietyn työtilan käyttöönottojakson käytön aloittaminen

* työn julkaiseminen

### <a name="treat-each-workspace-as-a-complete-package-of-analytics"></a>kunkin työtilan käsitteleminen täydellisenä analytiikkapakettina

Ihannetapauksessa työtilan tulee sisältää kokonaisnäkymä yhdestä näkökulmasta (kuten osasto, liiketoimintayksikkö, projekti tai vertikaali) organisaatiossasi. Tämä helpottaa eri käyttäjien käyttöoikeuksien hallintaa, ja sen avulla koko työtilan sisältöjulkaisuja voidaan hallita suunnitellun aikataulun mukaisesti.  

Jos käytät [keskitettyjä tietojoukkoja](../connect-data/service-datasets-across-workspaces.md), joita käytetään koko organisaatiossa, kahdentyyppisten työtilojen luomista suositellaan:

* **Mallinnus- ja tietotyötilat** – nämä työtilat sisältävät kaikki keskitetyt tietojoukot

* **Raportoinnin työtilat** – nämä työtilat sisältävät kaikki riippuvaiset raportit ja koontinäytöt

### <a name="plan-your-permission-model"></a>Käyttöoikeusmallin suunnitteleminen

Käyttöönottojakso on Power BI -objekti, jolla on omat [käyttöoikeudet](deployment-pipelines-process.md#permissions). Lisäksi jakso sisältää työtiloja, joilla on omat käyttöoikeudet.

Jos haluat ottaa käyttöön turvallisen ja helpon työnkulun, voit suunnitella, kuka pääsee käsiksi jakson kuhunkin osaan. Huomioon otettavia seikkoja ovat seuraavat:

* Kenellä on oltava jakson käyttöoikeus?

* Mitä toimintoja jakson käyttöoikeuden saaneet käyttäjät voivat suorittaa jokaisessa vaiheessa?

* Kuka tarkistaa sisällön testivaiheessa?

* Tuleeko testivaiheen tarkistajilla olla pääsy jaksoon?

* Kuka valvoo käyttöönottoa tuotantovaiheeseen?

* Minkä työtilan määrität?

* Mihin vaiheeseen olet määrittämässä työtilaasi?

* Onko määritettävän työtilan käyttöoikeuksiin tehtävä muutoksia?

### <a name="connect-different-stages-to-different-databases"></a>Eri vaiheiden yhdistäminen eri tietokantoihin

Tuotantotietokannan tulee aina olla vakaa ja käytettävissä. On parempi, että sitä ei ylikuormita BI-sisällöntuottajien kehitys- tai testitietojoukkoja varten luomilla kyselyillä. Luo erilliset tietokannat kehitystä ja testausta varten. Tämä auttaa suojaamaan tuotantotiedot, eikä se ylikuormita kehitystietokantaa koko tuotantotietojen määrällä, mikä voi hidastaa järjestelmää.

>[!NOTE]
>Jos organisaatiossa käytetään [jaettuja keskitettyjä tietojoukkoja](../connect-data/service-datasets-share.md), voit ohittaa tämän suosituksen.

### <a name="use-parameters-in-your-model"></a>Parametrien käyttö mallissa

Koska et voi muokata tietojoukkojen tietolähteitä Power BI -palvelussa, suosittelemme käyttämään [parametreja](https://docs.microsoft.com/power-query/power-query-query-parameters), kun haluat tallentaa yhteyden tiedot, kuten esiintymien nimet ja tietokantojen nimet, sen sijaan, että käyttäisit staattista yhteysmerkkijonoa. Tämän ansiosta voit hallita yhteyksiä Power BI -palvelun verkkoportaalin kautta tai [käyttämällä ohjelmointirajapintoja](https://docs.microsoft.com/rest/api/power-bi/datasets/updateparametersingroup) myöhemmässä vaiheessa.

Käyttöönottojaksoissa voit määrittää parametrisääntöjä, jotka määrittävät tietyt arvot kehitys-, testi- ja tuotantovaiheille.

Jos et käytä parametreja yhteysmerkkijonossa, voit määrittää tietolähdesääntöjä ja määrittää yhteysmerkkijonon tiettyä tietojoukkoa varten. Kaikki tietolähteet eivät kuitenkaan tue tätä käyttöönottojaksoissa. Jos haluat varmistaa, että voit määrittää sääntöjä tietolähteelle, katso [Tietojoukon sääntöjen rajoitukset](deployment-pipelines-get-started.md#dataset-rule-limitations).

Parametreilla on lisäkäyttötarkoituksia, kuten muutosten tekeminen kyselyihin, suodattimiin ja raportissa näkyvään tekstiin.

## <a name="development"></a>Kehitys

Tässä osiossa on ohjeita käyttöönottojaksojen käyttöönottovaiheen käsittelemiseen.

### <a name="use-power-bi-desktop-to-edit-your-reports-and-datasets"></a>Raporttien ja tietojoukkojen muokkaaminen Power BI Desktopin avulla

Harkitse Power BI Desktopin käyttämistä paikallisena kehitysympäristönä. Power BI Desktopin avulla voit kokeilla, tutkia ja tarkistaa raportteja ja tietojoukkoja. Kun työ on tehty, voit ladata uuden versiosi kehitysvaiheeseen. Seuraavista syistä on suositeltavaa muokata .pbix-tiedostoja Desktopissa (Power BI -palvelun sijasta):

* On helpompaa tehdä yhteistyötä muiden sisällöntuottajien kanssa samassa .pbix-tiedostossa, jos kaikki muutokset tehdään samalla työkalulla.

 * Online-muutosten tekeminen, .pbix-tiedoston lataaminen ja sen lataaminen uudelleen luo raportteja ja tietojoukkokopioita.

* Versionhallinnan avulla voit pitää .pbix-tiedostot ajan tasalla.

### <a name="version-control-for-pbix-files"></a>Versionhallinta .pbix-tiedostoja varten

Jos haluat hallita raporttiesi ja tietojoukkojesi versiohistoriaa, käytä [Power BI:n automaattista synkronointia OneDriveen](../connect-data/service-connect-to-files-in-app-workspace-onedrive-for-business.md). Tämä pitää tiedostot päivitettyinä uusimpaan versioon. Sen avulla voit myös hakea vanhempia versioita tarvittaessa.

>[!NOTE]
>Käytä automaattista synkronointia OneDriven (tai minkä tahansa muun säilön) kanssa vain .pbix-tiedostoissa käyttöönottojaksojen kehitysvaiheessa. Älä synkronoi .pbix-tiedostoja käyttöönottojaksojen testaus- ja tuotantovaiheissa. Se aiheuttaa ongelmia sisällön käyttöönotossa jakson kautta.

### <a name="separate-modeling-development-from-report-and-dashboard-development"></a>Erillinen mallinnuskehitys raportin ja koontinäytön kehityksestä

Yritystason käyttöönotoissa suositellaan erottamaan tietojoukon kehitys raporttien ja koontinäyttöjen kehityksestä. Jos haluat korottaa muutokset vain raporttiin tai tietojoukkoon, käytä käyttöönottojaksoissa valikoivan käyttöönoton asetusta.  

Tämän lähestymistavan pitäisi alkaa Power BI Desktopista, jossa luodaan erillinen .pbix-tiedosto tietojoukoille ja raporteille. Voit esimerkiksi luoda tietojoukon .pbix-tiedoston ja ladata sen kehitysvaiheeseen. Myöhemmin raportin tekijät voivat luoda uuden .pbix-tiedoston vain raporttia varten ja [yhdistää sen julkaistuun tietojoukkoon](../connect-data/service-datasets-discover-across-workspaces.md) reaaliaikaisen yhteyden välityksellä. Tämän tekniikan ansiosta eri luojat voivat työstää mallinnuksia ja visualisointeja erikseen sekä ottaa ne käyttöön tuotannossa itsenäisesti.

[Jaettujen tietojoukkojen](../connect-data/service-datasets-share.md) ansiosta voit käyttää tätä menetelmää myös työtiloissa.

### <a name="manage-your-models-using-xmla-readwrite-capabilities"></a>Omien mallien hallinta käyttämällä XMLA-luku- ja kirjoitustoimintoja

Kun mallinnuskehitys erotetaan raportin ja koontinäytön kehityksestä, voit käyttää lisätoimintoja, kuten lähteen hallintaa, eroavien muutosten yhdistämistä ja automatisoituja prosesseja. Nämä muutokset tulee tehdä kehitysvaiheessa, jotta viimeistelty sisältö voidaan ottaa käyttöön testi- ja tuotantovaiheissa. Tämän avulla muutokset käyvät läpi yhtenäisen prosessin muiden riippuvaisten kohteiden kanssa ennen kuin ne otetaan käyttöön tuotantovaiheessa.

Voit erottaa mallinnuskehityksen visualisoinneista hallitsemalla [jaettua tietojoukkoa](../connect-data/service-datasets-share.md) ulkoisessa työtilassa käyttäen XMLA:n luku- ja kirjoitusominaisuuksia. Jaettu tietojoukko voi muodostaa yhteyden eri työtiloissa oleviin useisiin raportteihin, joita hallitaan useissa jaksoissa.

## <a name="test"></a>Testaa

Tässä osiossa on ohjeita käyttöönottojaksojen testivaiheen käsittelemiseen.

### <a name="simulate-your-production-environment"></a>Tuotantoympäristön simulointi

Sen lisäksi, että tarkistetaan uusien raporttien tai koontinäyttöjen ulkoasu, on myös tärkeää nähdä, miten ne toimivat loppukäyttäjän näkökulmasta. Käyttöönottojaksojen testivaiheen avulla voit simuloida todellista tuotantoympäristöä testausta varten.

Varmista, että nämä kolme tekijää tarkistetaan testiympäristössä:

* Tietojen määrä

* Käyttömäärä

* Vastaava kapasiteetti kuin tuotannossa

Testauksessa voit käyttää samaa kapasiteettia kuin tuotantovaiheessa. Tämä voi kuitenkin tehdä tuotannosta epävakaan kuormitustestauksen aikana. Jos haluat välttää epävakaan tuotannon, käytä testauksessa toista kapasiteettia, joka on resursseiltaan samankaltainen kuin tuotantokapasiteetti. Lisäkustannusten välttämiseksi voit käyttää [Azuren A-kapasiteetteja](../developer/embedded/azure-pbie-create-capacity.md) ja maksaa vain testausajasta.

![käyttöönottojaksojen parhaiden käytäntöjen kaavio](media/deployment-pipelines-best-practices/deployment-pipelines-best-practices-diagram.png)

### <a name="use-dataset-rules-with-a-real-life-data-source"></a>Tietojoukon sääntöjen käyttäminen oikean tietolähteen kanssa

Jos käytät testivaihetta todellisten tietojen käytön simulointiin, on suositeltavaa erottaa kehitys- ja testitietolähteet toisistaan. Kehitystietokannan kannattaa olla suhteellisen pieni, ja testitietokannan on oltava mahdollisimman samankaltainen kuin tuotantotietokannan. Käytä [tietolähdesääntöjä](deployment-pipelines-get-started.md#step-4---create-dataset-rules) tietolähteiden vaihtamiseen testivaiheessa.

Tietolähteestä tuotavien tietojen määrän hallitseminen kannattaa, jos käytät testivaiheessa tuotantotietolähdettä. Voit tehdä tämän lisäämällä parametrin tietolähdekyselyyn Power BI Desktopissa. Hallitse tuotavien tietojen määrää parametrisäännöillä tai muokkaa parametrin arvoa.
Voit myös käyttää tätä lähestymistapaa, jos et halua ylikuormittaa kapasiteettiasi.

### <a name="measure-performance"></a>Mittaa suorituskykyä

Kun simuloit tuotantovaihetta, [tarkista raportin lataus ja sen vaikutukset](../guidance/monitor-report-performance.md) sekä selvitä, vaikuttavatko tekemäsi muutokset niihin.

Sinun täytyy myös [seurata kapasiteetin kuormitusta](../admin/service-admin-premium-monitor-capacity.md), jotta löydät äärimmäiset kuormitukset ennen kuin ne päätyvät tuotantoon.  

>[!NOTE]
>Kapasiteetin kuormitusta kannattaa seurata uudelleen sen jälkeen, kun päivitykset on otettu käyttöön tuotantovaiheessa.

### <a name="check-related-items"></a>Liittyvien kohteiden tarkistus

Tietojoukkojen tai raporttien muutokset voivat vaikuttaa aiheeseen liittyviin aikoihin. Tarkista testauksen aikana, että muutoksesi eivät vaikuta olemassa olevien, päivitetyistä kohteista riippuvaisten kohteiden suorituskykyyn tai riko niitä.

Löydät aiheeseen liittyvät kohteet helposti käyttämällä työtilan [historiatietonäkymää](../collaborate-share/service-data-lineage.md).

### <a name="test-your-app"></a>Sovelluksen testaaminen

Jos jaat sisältöä käyttäjille sovelluksen kautta, tarkista sovelluksen uusi versio ennen kuin se on tuotannossa. Koska jokaisella käyttöönottojakson vaiheella on oma työtilansa, voit helposti julkaista ja päivittää sovelluksia kehitys- ja testivaiheissa. Sen ansiosta voit testata sovellusta loppukäyttäjän näkökulmasta.

>[!IMPORTANT]
>Käyttöönottoprosessi ei sisällä sovelluksen sisällön tai asetusten päivittämistä. Jos haluat ottaa muutokset käyttöön sisällössä tai asetuksissa, sinun on päivitettävä sovellus manuaalisesti asianomaisessa jakson vaiheessa.

## <a name="production"></a>Tuotanto

Tässä osiossa on ohjeita käyttöönottojaksojen tuotantovaihetta varten.

### <a name="manage-who-can-deploy-to-production"></a>Sen hallitseminen, ketkä voivat ottaa käyttöön tuotantoon

Koska käyttöönottoa tuotantoon tulee käsitellä huolellisesti, hyvä käytäntö on antaa vain tiettyjen ihmisten hallita tätä arkaluontoista toimintoa. Luultavasti haluat kuitenkin, että kaikki tietyn työtilan BI-luojat voivat käyttää jaksoa. Tätä voidaan hallita käyttämällä tuotannon [työtilan käyttöoikeuksia](deployment-pipelines-process.md#permissions).  

Jotta sisältö voidaan käyttöön vaiheiden välillä, käyttäjillä on oltava kummassakin vaiheessa joko jäsenen tai järjestelmänvalvojan oikeudet. Varmista, että vain henkilöillä, joiden haluat ottavan tuotannon käyttöön, on tuotantotyötilan käyttöoikeudet. Muilla käyttäjillä voi olla tuotantotyötilan osallistujan tai katselijan rooleja. He pystyvät näkemään jakson sisällön, mutta he eivät voi ottaa sitä käyttöön.

Lisäksi sinun kannattaa rajoittaa jakson käyttöä ottamalla käyttöön jakson käyttöoikeudet vain käyttäjille, jotka ovat mukana sisällön luontiprosessissa.

### <a name="set-rules-to-ensure-production-stage-availability"></a>Tuotantovaiheen käytettävyyden varmistaminen sääntöjen avulla

[Tietojoukkosäännöt](deployment-pipelines-get-started.md#step-4---create-dataset-rules) ovat tehokas tapa varmistaa, että tuotannossa olevat tiedot ovat aina yhteydessä ja käyttäjien käytettävissä. Kun tietojoukkosääntöjä otetaan käyttöön, käyttöönotot voidaan suorittaa, kun sinulla on varmuus siitä, että käyttäjät näkevät tarvittavat tiedot häiriöittä.

Varmista, että määrität tuotannon tietojoukkosäännöt tietojoukolle määritettyjä tietolähteitä ja parametreja varten.

### <a name="update-the-production-app"></a>Tuotantosovelluksen päivittäminen

Käyttöönotto jaksossa päivittää työtilan sisällön, mutta se ei päivitä liitettyä sovellusta automaattisesti. Jos käytät sisällön jakeluun sovellusta, muista päivittää sovellus tuotantoon käyttöönoton jälkeen, jotta loppukäyttäjät voivat välittömästi käyttää uusinta versiota.  

### <a name="quick-fixes-to-content"></a>Sisällön pikakorjaukset

Jos tuotannossa on virheitä, jotka on korjattava nopeasti, älä lataa uutta .pbix-versiota suoraan tuotantovaiheeseen tai tee online-muutos Power BI -palvelussa. Käyttöönotto taaksepäin testi- ja kehitysvaiheisiin ei ole mahdollista, kun kyseisissä vaiheissa on jo sisältöä. Lisäksi korjauksen käyttöönotto testaamatta sitä ensin on huono käytäntö. Siksi oikea tapa käsitellä tätä ongelmaa on ottaa korjaus käyttöön kehitysvaiheessa ja siirtää se sitten muihin käyttöönottojakson vaiheisiin. Tämän avulla voidaan tarkistaa korjauksen toimivuus ennen kuin se otetaan käyttöön tuotannossa. Käyttöönotto jakson läpi kestää vain muutaman minuutin.

## <a name="next-steps"></a>Seuraavat vaiheet

>[!div class="nextstepaction"]
>[Käyttöönottojaksojen esittely](deployment-pipelines-overview.md)

>[!div class="nextstepaction"]
>[Käyttöönottojaksojen käytön aloittaminen](deployment-pipelines-get-started.md)

>[!div class="nextstepaction"]
>[Tutustu käyttöönottojaksojen prosessiin](deployment-pipelines-process.md)

>[!div class="nextstepaction"]
>[Käyttöönottojaksojen vianmääritys](deployment-pipelines-troubleshooting.md)
