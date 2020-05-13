---
title: Mitä Power BI -mallisovellukset ovat?
description: Tämä artikkeli on Power BI -mallisovellusten ohjelman yleiskatsaus. Opi kehittämään Power BI -sovelluksia, niin että koodausta tarvitaan vain vähän tai ei ollenkaan, ja ota sovellukset käyttöön keille tahansa Power BI -asiakkaille.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/04/2020
ms.author: painbar
ms.openlocfilehash: 3c508578b6438b0edfc3b4c9dfb7b724418894dd
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83307976"
---
# <a name="what-are-power-bi-template-apps"></a>Mitä Power BI -mallisovellukset ovat?

Power BI:n uusien *mallisovellusten* avulla Power BI -kumppanit voivat kehittää Power BI -sovelluksia käyttäen vain vähän tai ei lainkaan koodausta, minkä lisäksi sovellukset voidaan ottaa käyttöön kenelle tahansa Power BI -asiakkaalle.  Tämä artikkeli on Power BI -mallisovellusten ohjelman yleiskatsaus.

Power BI -kumppanina voit luoda valmista sisältöä asiakkaillesi ja julkaista sen itse.  

Voit kehittää mallisovelluksia, joiden avulla asiakkaasi voivat yhdistää ja alustaa tiedot omiin tileihinsä. Toimialueen asiantuntijoina he voivat avata tietojen lukituksen siten, että ne ovat helposti heidän yrityskäyttäjiensä käytettävissä.  

Voit lähettää mallisovelluksia kumppanikeskukseen. Sen jälkeen sovellukset tulevat julkisesti saataville [Power BI -sovellusten Marketplaceen](https://app.powerbi.com/getdata/services) ja [Microsoft AppSourceen](https://appsource.microsoft.com/?product=power-bi). Tässä on korkean tason katsaus julkisen mallisovelluksen luomistoimintoon.

## <a name="power-bi-apps-marketplace"></a>Power BI -sovellusten Marketplace

Power BI -mallisovellusten ansiosta Power BI Pro- ja Power BI Premium -käyttäjät saavat heti merkityksellisiä tietoja valmiiksi pakattujen koontinäyttöjen ja raporttien kautta, jotka voidaan yhdistää reaaliaikaisiin tietolähteisiin. Monet Power BI -sovellukset ovat jo saatavilla [Power BI -sovellusten Marketplacessa](https://app.powerbi.com/getdata/services).

|  |
|     :---:      |
| [![Microsoft Project -verkkosovellus](./media/service-template-apps-overview/project-web.png)](https://app.powerbi.com/groups/me/getapps/services/pbi_msprojectonline.pbi-microsoftprojectwebapp) [![Microsoft 365:n käyttöanalytiikan verkkosovellus](./media/service-template-apps-overview/microsoft365-usage-analytics.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics) [![Dynamic 365 Business Central – Sales -verkkosovellus](./media/service-template-apps-overview/dynamics-sales.png)](https://app.powerbi.com/groups/me/getapps/services/microsoftdynsmb.businesscentral_sales) [![Microsoft Forms Pro Customer Satisfaction -verkkosovellus](./media/service-template-apps-overview/forms-pro.png)](https://app.powerbi.com/groups/me/getapps/services/msfp.formsprocustomersatisfaction) |
|  |

## <a name="process"></a>Prosessi
Mallisovelluksen yleinen kehittämis- ja lähettämisprosessi koostuu useista vaiheista. Jotkin vaiheet voivat koostua useammasta kuin yhdestä samanaikaisesta toiminnosta.


| Vaihe | Power BI Desktop |  |Power BI -palvelu  |  |Kumppanikeskus  |
|---|--------|--|---------|---------|---------|
| **Yksi** | Luo tietomalli ja raportti .pbix-tiedostoon |  | Luo työtila. Tuo .pbix-tiedosto. Luo täydentävä koontinäyttö  |  | Rekisteröidy kumppanina |
| **Kaksi** |  |  | Luo testipaketti ja suorita sisäinen vahvistus        |  | |
| **Kolme** | |  | Ylennä testipaketti esituotantoon, niin että se vahvistetaan Power BI -vuokraajan ulkopuolella, ja lähetä se AppSourceen  |  | Luo esituotantopaketilla Power BI -mallisovellustarjous ja aloita vahvistusprosessi |
| **Neljä** | |  | Ylennä esituotantopaketti tuotannoksi |  | Julkaise |

## <a name="before-you-begin"></a>Alkutoimet

Mallisovelluksen luomista varten tarvitaan oikeus mallisovelluksen luomiseen. Lisätietoja on Power BI:n hallintaportaalin kohdassa Mallisovelluksen asetukset. 

Jotta voit julkaista mallisovelluksen Power BI -palveluun ja AppSourceen, sinun on täytettävä [kumppanikeskuksen julkaisijaksi ryhtymisen](https://docs.microsoft.com/azure/marketplace/become-publisher) ehdot.
 
## <a name="high-level-steps"></a>Ylätason vaiheet

Tässä ovat ylätason vaiheet. 

1. [Tarkista edellytykset](#requirements) ja varmista, että täytät ne. 

2. Luo raportti Power BI Desktopissa. Käytä parametreja, niin että voit tallentaa raportin tiedostona, jota muut voivat käyttää. 

3. Luo mallisovellukselle työtila Power BI -palvelun vuokraajassasi (app.powerbi.com). 

4. Tuo .pbix-tiedosto ja lisää sovellukseesi sisältöä, kuten koontinäyttö. 

5. Luo testipaketti, niin että voit itse testata mallisovellusta organisaatiossasi. 

6. Ylennä testisovellus esituotantoon, niin että voit lähettää sovelluksen vahvistettavaksi AppSourcessa sekä testata oman vuokraajasi ulkopuolella. 

7. Lähetä sisältö [kumppanikeskukseen](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-power-bi-app-offer) julkaisua varten. 

8. Määritä tarjouksesi käyttöönottotilaksi “Live” AppSourcessa ja siirrä sovelluksesi tuotantoon Power BI:ssä.

9. Voit nyt alkaa kehittää samassa työtilassa seuraavaa versiota esituotannossa. 

## <a name="requirements"></a>Vaatimukset

Mallisovelluksen luomista varten tarvitaan oikeus mallisovelluksen luomiseen. Lisätietoja on Power BI:n [hallintaportaalin kohdassa Mallisovelluksen asetukset](../admin/service-admin-portal.md#template-apps-settings).

Jotta voit julkaista mallisovelluksen Power BI -palveluun ja AppSourceen, sinun on täytettävä [kumppanikeskuksen julkaisijaksi ryhtymisen](https://docs.microsoft.com/azure/marketplace/become-publisher) ehdot.
 > [!NOTE] 
 > Mallisovellusten lähetyksiä hallitaan [kumppanikeskuksessa](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-power-bi-app-offer). Käytä samaa Microsoftin kehittäjäkeskuksen rekisteröintitiliä sisäänkirjautumiseen. Sinulla pitäisi olla vain yksi Microsoft-tili AppSource-tarjouksia varten. Tilien ei tulisi olla palvelu- tai tarjouskohtaisia.

## <a name="tips"></a>Vinkkejä 

- Varmista, että sovelluksesi sisältää mallitietoja, niin että kaikki voivat aloittaa käytön yhdellä napsautuksella. 
- Tutki sovellustasi huolellisesti asentamalla se omassa vuokraajassasi ja toissijaisessa vuokraajassa. Varmista, että asiakkaat näkevät vain sen, mitä haluat heidän näkevän. 
- Käytä AppSourcea verkkosäilönä, joka isännöi sovellustasi. Näin kaikki Power BI:n käyttäjät voivat löytää sovelluksesi. 
- Harkitse useamman kuin yhden mallisovelluksen tarjoamista erillisiä ainutkertaisia skenaarioita varten. 
- Ota käyttöön tietojen mukauttaminen; tue esimerkiksi mukautettua yhteyttä ja asennusohjelman määrittämiä parametreja.

Lisää ehdotuksia on artikkelissa [Vihjeitä mallisovellusten luomiseen Power BI:ssä](service-template-apps-tips.md).

## <a name="known-limitations"></a>Tunnetut rajoitukset

| Ominaisuus | Tunnettu rajoitus |
|---------|---------|
|Sisältö:  Tietojoukot   | Tarkalleen yhden tietojoukon tulee olla käytössä. Vain Power BI Desktopissa luodut tietojoukot (.pbix-tiedostot) sallitaan. <br>Ei tueta: Tietojoukkoja, jotka ovat peräisin muista mallisovelluksista, työtilojen välisiä tietojoukkoja, sivuttuja raportteja (.rdl-tiedostot), Excel-työkirjoja |
|Sisältö: Koontinäytöt | Reaaliaikaisia ruutuja ei sallita (toisin sanoen push-ilmoituksia tai tietojoukkojen suoratoistoa ei tueta) |
|Sisältö: Tietovuot | Ei tueta: Tietovuot |
|Tiedostojen sisällöt | Vain PBIX-tiedostot sallitaan. <br>Ei tueta: .rdl-tiedostot (sivutetut raportit), Excel-työkirjat   |
| Tietolähteet | Pilvipohjaista ajoitettua tietojen päivittämistä tukevat tietolähteet sallitaan. <br>Ei tueta: <li> DirectQuery</li><li>Reaaliaikaiset yhteydet (Azure AS ei käy)</li> <li>Paikalliset tietolähteet (henkilökohtaiset yhdyskäytävät ja yritysyhdyskäytävät eivät ole tuettuja)</li> <li>Reaaliaikainen (push-tietojoukkoa ei tueta)</li> <li>Yhdistelmämallit</li></ul> |
| Tietojoukko: työtilojen välinen | Työtilojen välisiä tietojoukkoja ei sallita  |
| Kyselyparametrit | Ei tueta: Tyyppiä ”Any” tai ”Binary” olevat parametrit estävät tietojoukon päivitystoiminnon |
| Power BI:n visualisoinnit | Vain julkisesti käytettävissä olevia Power BI -visualisointeja tuetaan. [Organisaation Power BI -visualisointeja](../developer/visuals/power-bi-custom-visuals-organization.md) ei tueta. |
| Maakohtaiset pilvipalvelut | Mallisovellukset eivät ole käytettävissä itsenäisissä pilvipalveluissa |

## <a name="support"></a>Tuki
Saat tukea kehityksen aikana osoitteesta [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support). Valvomme ja hallinnoimme tätä sivustoa aktiivisesti. Asiakastapaukset ohjataan nopeasti oikealle tiimille.

## <a name="next-steps"></a>Seuraavat vaiheet

[Mallisovelluksen luonti](service-template-apps-create.md)
