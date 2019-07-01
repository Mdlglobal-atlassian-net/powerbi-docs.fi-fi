---
title: Power BI -mallisovelluksen päivittäminen, poistaminen ja purkaminen
description: Mallisovelluksen päivittämistä, poistamista ja purkamista koskevat ohjeet.
author: teddybercovitz
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/10/2019
ms.author: tebercov
ms.openlocfilehash: 273734493c761739f9780e6a7fe6e781900723f9
ms.sourcegitcommit: 7d52401f50944feaaa112c84113ee47f606dbf68
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/13/2019
ms.locfileid: "67125874"
---
# <a name="update-delete-and-extract-template-app"></a>Mallisovelluksen päivittäminen, poistaminen ja purkaminen

Kun sovelluksesi on nyt tuotantoympäristössä, voit aloittaa alusta testausvaiheessa häiritsemättä tuotantoympäristössä olevaa sovellusta.
## <a name="update-your-app"></a>Päivitä sovelluksesi


1. Valitse **Julkaisun hallinta** -ruudussa **Luo sovellus**.
2. Suorita sovelluksen luontiprosessi uudelleen.
3. Kun olet määrittänyt **tuotemerkkiohjeet**, **sisällön**, **hallinnan** ja **käyttöoikeudet**, voit uudelleen valita **Luo sovellus** -vaihtoehdon.
4. Valitse **Sulje** ja palaa **Julkaisun hallintaan**.

   Näkyvillä on nyt kaksi versiota: tuotantoympäristössä oleva versio sekä testausvaiheessa oleva uusi versio.

    ![Mallisovelluksen kaksi versiota](media/service-template-apps-update-extract-delete/power-bi-template-app-update.png)

5. Kun olet valmis korottamaan sovelluksesi esituotantoon niin, että sen testausta voidaan jatkaa oman vuokraajasi ulkopuolella, palaa Julkaisun hallinta -ruutuun ja valitse **Testaus**-kohdan vierestä **Korota sovellus**.
6. Linkkisi on nyt aktiivinen. Lähetä se uudelleen pilvikumppaniportaaliin (CPP) [Power BI -sovellustarjouksen päivitys](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-update-existing-offer) -kohdan ohjeiden mukaisesti.
7. Tarjous on **julkaistava** CPP:ssä ja vahvistettava uudelleen.

>[!NOTE]
>Korota sovellus tuotantovaiheeseen vasta, kun pilvikumppaniportaali on hyväksynyt sovelluksen ja olet julkaissut sen.

## <a name="extract-workspace"></a>Työtilan purkaminen
Purkutoiminnon ansiosta on nyt entistäkin helpompi palata takaisin mallisovelluksen edelliseen versioon. Erityinen sovellusversio puretaan erilaisista julkaisun vaiheista uuteen työtilaan seuraavasti:

1. Paina Julkaisun hallinta -ruudussa Lisää **(...)**  ja sitten **Pura**.

    ![pura mallisovellusversio](media/service-template-apps-update-extract-delete/power-bi-template-app-extract.png) ![pura mallisovellusversio](media/service-template-apps-update-extract-delete/power-bi-template-app-extract-dialog.png)
2. Kirjoita valintaikkunaan puretun työtilan nimi. uusi työtila lisätään.

Uuden työtilan versiotiedot nollataan, ja voit jatkaa mallisovelluksen kehittämistä ja jakamista juuri puretusta työtilasta.

## <a name="delete-template-app-version"></a>Mallisovellusversion poistaminen
Mallisovelluksen työtila on aktiivisen hajautetun mallisovelluksen lähde. Mallisovelluksen käyttäjien suojaamiseksi työtilaa ei voida poistaa, ellei työtilasta ole ensin poistettu kaikkia luotuja sovellusversioita.
Sovellusversion poistaminen poistaa myös sovelluksen URL-osoitteen, joka ei enää toimi.

1. Paina Julkaisun hallinta -ruudussa kolmea pistettä **(...)**  ja sitten **Poista**.
 ![Poista mallisovellusversio](media/service-template-apps-update-extract-delete/power-bi-template-app-delete.png)
 ![Poista mallisovellusversio](media/service-template-apps-update-extract-delete/power-bi-template-app-delete-dialog.png)

>[!NOTE]
>Varmista, ettet poista asiakkaiden tai **AppSourcen** käyttämiä sovellusversioita tai ne eivät enää toimi.

## <a name="next-steps"></a>Seuraavat vaiheet

Ohjeaiheessa [Mallisovellusten asentaminen, mukauttaminen ja jakaminen organisaatiossa](service-template-apps-install-distribute.md) voit selvittää, miten asiakkaasi käsittelevät mallisovellusta.

Lisätietoja sovelluksen jakamisesta on kohdassa [Power BI -sovellustarjous](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).
