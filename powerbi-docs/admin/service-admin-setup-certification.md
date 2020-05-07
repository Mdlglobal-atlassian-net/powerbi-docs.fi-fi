---
title: Tietojoukkojen ja tietovoiden sertifioinnin määrittäminen (esiversio)
description: Lue ohjeet tietojoukkojen ja tietovoiden sertifiointiprosessin määrittämiseen organisaatiossasi.
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/22/2020
ms.author: painbar
LocalizationGroup: Share your work
ms.openlocfilehash: 1fc33b48613335f4fba97921e3d528175eb2a47f
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "81267841"
---
# <a name="set-up-dataset-and-dataflow-certification-preview"></a>Tietojoukkojen ja tietovoiden sertifioinnin määrittäminen (esiversio)

Organisaatiosi voi sertifioida tietojoukot ja tietovuot, jotka ovat virallisia tärkeiden tietojen lähteitä.

Power BI -vuokraajan järjestelmänvalvojana sinun vastuullasi on sertifiointiprosessin määrittäminen organisaatiossasi. Tämä tarkoittaa seuraavia asioita:
* Sinun täytyy ottaa sertifiointi käyttöön vuokraajassasi.
* Sinun täytyy määrittää luettelo ryhmistä ja käyttäjistä, joilla on oikeus sertifioida tietojoukkoja ja tietovoita.
* Tietojoukoille sinun täytyy määrittää organisaation tietojoukkojen sertifiointikäytännön (jos sellainen on) URL-osoite.

Tietojoukkojen ja tietovoiden sertifiointi ovat osa tietojoukkojen ja tietovoiden *tukemista*. Saat lisätietoja [tietojoukkojen tukemisen](../service-datasets-promote.md) ja [tietovoiden tukemisen](../transform-model/service-dataflows-promote-certify.md) ohjeartikkeleista.


## <a name="set-up-certification"></a>Sertifioinnin määrittäminen

1. Siirry hallintaportaalissa vuokraaja-asetuksiin.
1. Laajenna vienti- ja jakoasetusten kohdasta Sertifiointi-kohta.

   ![Tietojoukkojen ja tietovoiden sertifioinnin määrittäminen](media/service-admin-setup-certification/service-admin-certification-setup-dialog.png)

1. Vaihda valitsin **Käytössä**-asetukseen.
1. Jos organisaatiosi on julkaissut tietojoukkojen sertifiointikäytännön, voit antaa sen URL-osoitteen tässä. Siitä tulee **lisätietolinkki** [tietovuon tukemisen asetusten valintaikkunan](../service-datasets-promote.md#request-dataset-certification) sertifiointiosioon. 
1. Määritä ryhmät ja käyttäjät, joilla on oikeus sertifioida tietojoukkoja ja tietovoita. Nämä valtuutetut sertifioijat voivat käyttää Sertifiointi-painiketta [tietojoukon](../service-datasets-promote.md#request-dataset-certification) tai [tietovuon](../transform-model/service-dataflows-promote-certify.md#certify-a-dataflow) tukemisen asetusten valintaikkunan sertifiointiosiossa.
1. Valitse **Käytä**.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Tietojoukkojen ylentäminen](../service-datasets-promote.md)
* [Tietojoukkojen sertifioiminen](../service-datasets-certify.md)
* [Tietojoukkojen ylentäminen](../transform-model/service-dataflows-promote-certify.md#promote-a-dataflow)
* [Tietojoukkojen sertifioiminen](../transform-model/service-dataflows-promote-certify.md#certify-a-dataflow)
* Onko sinulla kysymyksiä? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
