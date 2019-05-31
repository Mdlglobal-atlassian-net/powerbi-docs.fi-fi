---
ms.openlocfilehash: eb7cba03daee47f6772fc46be50419731b41765e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61193842"
---
## <a name="validate-the-roles-within-power-bi-desktop"></a>Roolien vahvistaminen Power BI Desktopissa
Kun olet luonut roolit, voit testata niiden tuloksia Power BI Desktopissa.

1. Valitse **Näytä rooleina**. 

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    Näet luomasi roolit **Näytä rooleina** -näkymässä.

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. Valitse luomasi rooli >**OK**, jos haluat ottaa roolin käyttöön. Raportit hahmontavat ainoastaan ne tiedot, jotka koskevat kyseistä roolia. 

4. Voit myös valita **toisen käyttäjän** ja määrittää tietyn käyttäjän. On parasta määrittää täydellinen käyttäjätunnus (UPN), koska sitä Power BI -palvelu ja Power BI -raporttipalvelin käyttävät.

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

1. Valitse **OK**, jolloin raportit hahmonnetaan sen perusteella, mitä käyttäjä näkee. 

**Toinen käyttäjä** näyttää eri tuloksia Power BI Desktopissa ainoastaan, jos käytössäsi on dynaaminen tietoturva, joka perustuu DAX-lausekkeisiin. 

