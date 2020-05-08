---
ms.openlocfilehash: 8dc488a47ac2b5b4e7980b7404b2722b1120b6ab
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "77464368"
---
## <a name="validate-the-roles-within-power-bi-desktop"></a>Roolien vahvistaminen Power BI Desktopissa
Kun olet luonut roolit, voit testata niiden tuloksia Power BI Desktopissa.

1. Valitse **Mallinnus**-välilehdeltä **Näytä rooleina**. 

    ![Valitse Näytä rooleina](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    **Näytä rooleina** -ikkuna tulee näkyviin ja näet luomasi roolit.

    ![Näytä rooleina-ikkuna](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. Valitse luomasi rooli ja valitse sitten **OK**, jos haluat ottaa roolin käyttöön. 

   Raportit hahmontavat ainoastaan ne tiedot, jotka koskevat kyseistä roolia.

4. Voit myös valita **toisen käyttäjän** ja määrittää tietyn käyttäjän. 

    ![Valitse Toinen käyttäjä](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

   On parasta määrittää täydellinen käyttäjätunnus (UPN), koska sitä Power BI -palvelu ja Power BI -raporttipalvelin käyttävät.

   **Toinen käyttäjä** näyttää eri tuloksia Power BI Desktopissa ainoastaan, jos käytössäsi on dynaaminen tietoturva, joka perustuu DAX-lausekkeisiin. 

5. Valitse **OK**. 

   Raportit hahmonnetaan sen perusteella, mitä käyttäjä näkee.



