---
title: Rivitason suojaus Power BI:n upotetussa sisällössä
description: Lue ohjeet, miten voit upottaa Power BI -sisältöä sovellukseesi.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: nishalit
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 11/04/2019
ms.openlocfilehash: 4db1f887c1dd889a06c02643a0270cc24ab9c45f
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "74311498"
---
# <a name="implementing-row-level-security-in-embedded-paginated-reports-preview"></a>Rivitason suojauksen toteuttaminen upotetuissa sivutetuissa raporteissa (esikatselu)

Kun upotat sivutetun raportin, voit määrittää, mitä tietoja näytetään. Tämä mahdollistaa näytettyjen tietojen räätälöinnin käyttäjäkohtaisesti. Jos sinulla on esimerkiksi Power BI:n sivutettu raportti, joka sisältää yleisiä myyntituloksia, voit upottaa sen niin, että vain tietyn alueen myyntitulokset ovat käytettävissä.

Tämä ominaisuus tarjoaa turvallisen tavan näyttää tietojen alijoukko niin, että muut tiedot eivät vaarannu. Se muistuttaa [rivitason suojaus (RLS)](embedded-row-level-security.md) -ominaisuutta, joka tarjoaa turvallisen tavan näyttää tiedot Power BI -raporteissa (joita ei ole sivutettu), koontinäytöillä, ruuduissa ja tietojoukoissa.  

> [!Note]
> Tämä ominaisuus toimii asiakkaille upotettujen sivutettujen raporttien kanssa.

## <a name="configuring-a-parameter-to-filter-the-dataset"></a>Parametrin määrittäminen tietojoukon suodattamiseksi

Kun otat rivitason suojauksen käyttöön Power BI -sivutetulle raportille, sinun on määritettävä [parametri](../report-builder-parameters.md)**UserID**-määritteelle. Tämä parametri rajoittaa tietojoukosta vedettyjä tietoja ennen raportin upottamista.

Kun olet määrittänyt parametrin **UserID:lle**, käytä [Reports GenerateTokenForCreateInGroup](https://docs.microsoft.com/rest/api/power-bi/embedtoken/reports_generatetokenforcreateingroup)-ohjelmointirajapintaa upotetun suojaustunnuksen saamiseksi.

## <a name="use-userid-as-a-filter-at-report-or-query-level"></a>UserID-tunnuksen käyttäminen suodattimen raportti- tai kyselytasolla

Voit käyttää **UserId**-tunnusta *suodattimena* tai *kyselynä* tietolähteenä[Power BI Paginated Report Builderissa](../report-builder-power-bi.md).

### <a name="using-the-filter"></a>Suodattimen käyttö

1. Valitse **Tietojoukon ominaisuudet** -ikkunan vasemmasta ruudusta **Suodatin**.

    ![Power BI Report Builder -suodatin](media/embedded-paginated-reports-secure-data/filter.png)

2. Valitse avattavasta **Lauseke**-valikosta parametri, jota haluat käyttää tietojen suodattamiseen.

     ![Power BI Report Builder -lausekkeet](media/embedded-paginated-reports-secure-data/expression.png)

3. Napsauta **Arvo**-toimintopainiketta. 

    ![Power BI Report Builder -arvo](media/embedded-paginated-reports-secure-data/function.png)

4. Valitse **Lauseke**-ikkunassa **Luokka**-luettelosta **Sisäiset kentät**.

    ![Power BI Report Builder -lausekkeet](media/embedded-paginated-reports-secure-data/built-in-fields.png)

5. Valitse **Kohde**-luettelosta **UserID** ja valitse **OK**.

    ![Power BI Report Builder UserID -tunnus](media/embedded-paginated-reports-secure-data/userid.png)

6. Tarkista **Tietojoukon ominaisuudet**-ikkunassa, että lauseke on *valitsemasi parametri = UserID*ja valitse **OK**.

    ![Power BI Report Builder -tietojoukon ominaisuudet](media/embedded-paginated-reports-secure-data/verify.png)

### <a name="using-a-query"></a>Kyselyn käyttäminen

1. Valitse **Tietojoukon ominaisuudet** -ikkunan vasemmasta ruudusta **Parametrit** ja napsauta **Lisää**.

    ![Power BI Report Builder -parametrit](media/embedded-paginated-reports-secure-data/parameters.png)

2. Anna kohdassa **Parametrin nimi** **\@UserID**ja lisää kohtaan **Parametrin arvo** **[&UserID]** .

    ![Power BI Report Builder -parametrin nimi](media/embedded-paginated-reports-secure-data/parameter-name.png) 

3. Valitse vasemmasta ruudusta **Kysely**ja lisää **UserID**-parametri kyselysi osaksi ja valitse **OK**.
    > [!NOTE]
    > Parametrin värinä alla olevassa esimerkkikuvassa käytetään (Wyalefintable. Color = @UserID). Tarvittaessa on mahdollista luoda monimutkaisempi kysely.

    ![Power BI Report Builder -kyselyiden muokkaaminen](media/embedded-paginated-reports-secure-data/query-edit.png)

## <a name="passing-the-configured-parameter-using-the-embed-token"></a>Määritetyn parametrin syöttäminen upotustunnuksen avulla

Kun upotat sivutetun raportin asiakkaitasi varten, [Reports GenerateTokenForCreateInGroup](https://docs.microsoft.com/rest/api/power-bi/embedtoken/reports_generatetokenforcreateingroup) -ohjelmointirajapintaa käytetään upotustunnuksen muodostamiseen. Tämän tunnuksen avulla voidaan myös suodattaa joitakin tietoja, jotka on vedetty ulos sivutetun raportin kautta.

Jos haluat paljastaa vain osan tiedoista, määritä `username` kenttään tiedot, jotka haluat näyttää. Jos esimerkiksi sivutetussa raportissa, jossa on väriparametri, syötät *vihreä*`username`-kenttään, upotustunnus rajoittaa upotetut tiedot näyttämään vain tiedot, joissa on *vihreä*-arvo värisarakkeessa.

```JSON
{
    "accessLevel": "View",
    "reportId": "cfafbeb1-8037-4d0c-896e-a46fb27ff229",
    "identities": [
            {
                    // Replace the 'username' with a paginated report parameter
                    "username":     "...",
                    "reports: [
                        "cfafbeb1-8037-4d0c-896e-a46fb27ff229"
                    ]
            }
    ]
}
```
