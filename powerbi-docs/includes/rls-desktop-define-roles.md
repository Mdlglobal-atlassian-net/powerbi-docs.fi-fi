---
ms.openlocfilehash: 240045c05a35a6583b537b785c6639a39c6aa9d4
ms.sourcegitcommit: ac63b08a4085de35e1968fa90f2f49ea001b50c5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/18/2019
ms.locfileid: "58051677"
---
## <a name="define-roles-and-rules-in-power-bi-desktop"></a>Roolien ja sääntöjen määrittäminen Power BI Desktopissa
Power BI Desktopissa voit määrittää rooleja ja sääntöjä. Kun julkaiset Power BI:ssä, myös roolimääritykset julkaistaan.

Voit määrittää käyttöoikeusroolit seuraavien ohjeiden mukaisesti.

1. Tuo tietoja Power BI Desktop ‑raporttiin tai määritä DirectQuery-yhteys.
   
   > [!NOTE]
   > Power BI Desktopissa ei voi määrittää rooleja reaaliaikaisille Analysis Services -yhteyksille. Ne täytyy määrittää Analysis Services -mallin sisältä.
   > 
   > 
1. Valitse **Mallinnus**-välilehti.
2. Valitse **Roolien hallinta**.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)
4. Valitse **Luo**.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)
5. Anna roolille nimi. 
6. Valitse taulukko, johon haluat käyttää DAX-sääntöä.
7. Anna DAX-lausekkeet. Lausekkeen tulisi palauttaa joko arvo tosi tai epätosi. Esimerkki: [Entiteetin tunnus] = ”arvo”.
   
   > [!NOTE]
   > Voit käyttää lausekkeessa funktiota *username()*. Huomaa, että *username()* on Power BI Desktopissa muodossa *TOIMIALUE\käyttäjänimi*. Power BI -palvelussa ja Power BI -raporttipalvelimessa se ilmoitetaan täydellisenä käyttäjätunnuksena. Vaihtoehtoisesti voit käyttää funktiota *userprincipalname()*, joka palauttaa aina käyttäjän täydellisen käyttäjätunnuksen, *username\@contoso.com*.
   > 
   > 
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)
8. Kun olet luonut DAX-lausekkeen, voit vahvistaa sen valitsemalla lausekeruudun yläpuolelta valintamerkkikuvakkeen.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)
9. Valitse **Tallenna**.

Käyttäjille ei voi määrittää roolia Power BI Desktopissa. Voit määrittää ne Power BI -palvelussa. Voit ottaa käyttöön Power BI Desktopin dynaamiset suojausominaisuudet hyödyntämällä *username()*- tai *userprincipalname()*-DAX-funktioita, kun oikeat suhteet on määritetty. 

