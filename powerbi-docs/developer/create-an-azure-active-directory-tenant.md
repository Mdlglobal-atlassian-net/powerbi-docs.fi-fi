---
title: Luo Azure Active Directory -vuokraaja käytettäväksi Power BI:n kanssa
description: Opettele luomaan uusi Azure Active Directory (Azure AD) -vuokraaja käytettäväksi mukautetun sovelluksesi kanssa Power BI REST -ohjelmointirajapintojen avulla.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 11/30/2017
ms.openlocfilehash: eb5befbfc5e96867f0f4cf27eafd62829fb488f4
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762141"
---
# <a name="create-an-azure-active-directory-tenant-to-use-with-power-bi"></a>Luo Azure Active Directory -vuokraaja käytettäväksi Power BI:n kanssa

Opettele luomaan uusi Azure Active Directory (Azure AD) -vuokraaja käytettäväksi mukautetun sovelluksesi kanssa Power BI REST -ohjelmointirajapintojen avulla.

Vuokraaja on organisaation edustaja Azure Active Directoryssä. Se on Azure AD -palvelun erityinen esiintymä, jonka organisaatio saa käyttöön ja omistaa, kun se liittyy Microsoftin pilvipalveluun, kuten Azure, Microsoft Intune tai Office 365. Kukin Azure AD -vuokraaja on yksilöllinen ja erillinen muista Azure AD -vuokraajista.

Kun sinulla on Azure AD -vuokraaja, voit määrittää sovelluksen ja myöntää oikeuksia, jotta sovelluksesi voi hyödyntää Power BI REST -ohjelmointirajapintoja.

Organisaatiollasi saattaa jo olla Azure AD -vuokraaja, jota voit käyttää sovellustasi varten. Voit käyttää kyseistä vuokraajaa sovellukseen liittyviin tarpeisiisi tai luoda uuden vuokraajan erityisesti omaa sovellustasi varten. Tässä artikkelissa käsitellään uuden vuokraajan luomista.

## <a name="create-an-azure-active-directory-tenant"></a>Azure Active Directory -vuokraajan luominen

Jotta voit integroida Power BI:n mukautettuun sovellukseesi, sinun on määritettävä sovellus Azure AD:ssä. Sitä varten tarvitset hakemiston Azure AD:ssä. Tämä on vuokraajasi. Jos organisaatiollasi ei vielä ole vuokraajaa, koska siellä ei käytetä Power BI:tä tai Office 365:tä, [sinun on luotava sellainen](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant). Voit myös joutua luomaan sellaisen, jos et halua sovelluksesi sekoittuvan organisaatiosi vuokraajan kanssa. Näin saat pidettyä asiat erillään.

Tai ehkä haluat luoda vuokraajan testaustarkoituksiin.

Jos haluat luoda uuden Azure AD -vuokraajan, toimi seuraavasti.

1. Selaa [Azure-portaaliin](https://portal.azure.com) ja kirjaudu sisään tilillä, jolla on Azure-tilaus.

2. Valitse **plus-kuvake (+)** ja hae *Azure Active Directory*.

    ![Plus-kuvake (+)](media/create-an-azure-active-directory-tenant/new-directory.png)

3. Valitse hakutuloksista **Azure Active Directory**.

    ![ADD-haku](media/create-an-azure-active-directory-tenant/new-directory2.png)

4. Valitse **Luo**.

5. Anna **organisaation nimi** sekä **alkuperäinen toimialuenimi**. Valitse sitten **Luo**. Tämä luo hakemistosi.

    ![Organisaatio ja toimialue](media/create-an-azure-active-directory-tenant/organization-and-domain.png)

   > [!NOTE]
   > Alkuperäinen toimialueesi on osa toimialuetta onmicrosoft.com. Voit lisätä muita toimialuenimiä myöhemmin. Hakemistolle eli vuokraajalle voi olla määritetty useita toimialueita.

6. Kun hakemisto on luotu, valitse tietoruutu hallitaksesi uutta hakemistoasi.

Hakemisto on nyt luotu. Seuraavaksi halutaan lisätä käyttäjä vuokraajaan.

## <a name="create-some-users-in-your-azure-active-directory-tenant"></a>Joidenkin käyttäjien luominen Azure Active Directory -vuokraajaan

Nyt kun meillä on hakemisto, luodaan vähintään kaksi käyttäjää. Yksi, joka on vuokraajan yleinen järjestelmänvalvoja ja toinen, joka on pääkäyttäjä upottamista varten. Ajattele tätä eräänlaisena palvelutilinä.

1. Varmista Azure-portaalissa, että käytössä on Azure Active Directory -pikaikkuna.

    ![](media/create-an-azure-active-directory-tenant/aad-flyout.png)

    Jos ei ole, valitse Azure Active Directory -kuvake vasemmalta palveluriviltä.

    ![](media/create-an-azure-active-directory-tenant/aad-service.png)
2. Valitse **Hallinta**-kohdasta **Käyttäjät ja ryhmät**.

    ![](media/create-an-azure-active-directory-tenant/users-and-groups.png)
3. Valitse **Kaikki käyttäjät** ja sitten **+ Uusi käyttäjä**.
4. Anna nimi ja käyttäjänimi tälle käyttäjälle. Tämä on vuokraajan yleinen järjestelmänvalvoja. Haluat lisäksi muuttaa kohdan **Hakemiston rooli** vaihtoehtoon *Yleinen järjestelmänvalvoja*. Voit myös näyttää tilapäisen salasanan. Kun olet valmis, valitse **Luo**.

    ![](media/create-an-azure-active-directory-tenant/global-admin.png)

5. Haluat tehdä saman uudelleen vuokraajasi tavalliselle käyttäjälle. Tätä voidaan käyttää myös upottamisen päätilillesi. Tällä kertaa annamme sen olla kohdassa **Hakemiston rooli** *Käyttäjä*. Merkitse salasana muistiin. Valitse sitten **Luo**.

    ![](media/create-an-azure-active-directory-tenant/pbiembed-user.png)
6. Rekisteröidy Power BI:hin käyttäjätilillä, jonka loit vaiheessa 5. Voit tehdä sen siirtymällä osoitteeseen [powerbi.com](https://powerbi.microsoft.com/get-started/) ja valitsemalla **Kokeile ilmaiseksi** kohdassa *Power BI - pilviyhteistyö ja jakaminen*.

    ![](media/create-an-azure-active-directory-tenant/try-powerbi-free.png)

    Kun rekisteröidyt, sinua pyydetään kokeilemaan Power BI Pro:ta ilmaiseksi 60 päivän ajan. Voit päättää tehdä niin, jolloin sinusta tulee pro-käyttäjä. Nyt voit myös alkaa kehittää upotettua ratkaisua, jos se on mitä haet.

   > [!NOTE]
   > Varmista, että rekisteröidyt sillä sähköpostiosoitteella, jonka ilmoitit käyttäjätilille.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun sinulla on Azure AD -vuokraaja, voit käyttää vuokraajaa kohteiden testaamiseen Power BI:ssä ja/tai voit siirtyä eteenpäin upottamaan Power BI -koontinäyttöjä ja -raportteja sovellukseesi. Kohteiden upottamista koskevia lisätietoja varten katso [Power BI -koontinäyttöjen, -raporttien ja -ruutujen upottaminen](embedding-content.md).

[Mikä on Azure AD -hakemisto?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)  
[Azure Active Directory -vuokraajan hankkiminen](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)