---
ms.openlocfilehash: 26f4b82301915524b65d9d2d6b39d61b54ed0321
ms.sourcegitcommit: 8eeb784fd46321680367ac913ef976aeedaa7766
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/03/2020
ms.locfileid: "80621591"
---
Palvelun päänimi todentamismenetelmä, jonka avulla Azure AD -sovellus voi käyttää Power BI -palvelun sisältöä ja ohjelmointi rajapintoja.

Kun luot Azure Active Directory (Azure AD) -sovelluksen, luodaan [palvelun pääobjekti](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object). Palvelun pääobjekti, jota kutsutaan myös *palvelun päänimeksi*, antaa Azure AD:lle oikeuden sovelluksesi todentamiseen. Kun sovellus on todennettu, se voi käyttää Azure AD:n vuokraajaresursseja.

Todentamisessa palvelun päänimi käyttää Azure AD -sovelluksen *sovellustunnusta* ja jotakin seuraavista:
* Sovellussalaisuus
* Varmenne