---
ms.openlocfilehash: 27d6db6cf8ad8ebd7b2c957954ceec34b83681d0
ms.sourcegitcommit: cde65bb8b1bed1ee8cf512651afeb829ddc155de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/19/2020
ms.locfileid: "77464371"
---
## <a name="define-roles-and-rules-in-power-bi-desktop"></a>Roolien ja sääntöjen määrittäminen Power BI Desktopissa
Power BI Desktopissa voit määrittää rooleja ja sääntöjä. Kun julkaiset Power BI:ssä, myös roolimääritykset julkaistaan.

Voit määrittää käyttöoikeusroolit seuraavien ohjeiden mukaisesti.

1. Tuo tietoja Power BI Desktop ‑raporttiin tai määritä DirectQuery-yhteys.
   
   > [!NOTE]
   > Power BI Desktopissa ei voi määrittää rooleja reaaliaikaisille Analysis Services -yhteyksille. Ne täytyy määrittää Analysis Services -mallin sisältä.
   > 
   > 
2. Valitse **Mallinnus**-välilehdeltä **Roolien hallinta**.
   
   ![Valitse Roolien hallinta](./media/rls-desktop-define-roles/powerbi-desktop-security.png)
3. Valitse **Roolien hallinta** -ikkunassa **Luo**.
   
   ![Valitse Luo](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)
4. Anna roolille nimi **Roolit**-kohdassa. 
5. Valitse **Taulukot**-kohdassa taulukko, johon haluat käyttää DAX-sääntöä.
6. Kirjoita DAX-lausekkeet **Taulukkosuodattimen DAX-lauseke** -ruutuun. Tämä lauseke palauttaa arvon tosi tai epätosi. Esimerkiksi: ```[Entity ID] = “Value”```.
      
   ![Roolien hallinta -ikkuna](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)

   > [!NOTE]
   > Voit käyttää lausekkeessa funktiota *username()* . Huomaa, että *username()* on Power BI Desktopissa muodossa *TOIMIALUE\käyttäjänimi*. Power BI -palvelussa ja Power BI -raporttipalvelimessa se ilmoitetaan täydellisenä käyttäjätunnuksena. Vaihtoehtoisesti voit käyttää funktiota *userprincipalname()* , joka palauttaa aina käyttäjän täydellisen käyttäjätunnuksen, *username\@contoso.com*.
   > 
   > 

7. Kun olet luonut DAX-lausekkeen, vahvista se valitsemalla lausekeruudun yläpuolelta valintamerkkikuvake.
      
   ![Vahvista DAX-lauseke](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)
   
   > [!NOTE]
   > Tässä lausekeruudussa voit erotella DAX-funktioiden argumentit pilkuilla, vaikka käyttäisit aluekohtaisia asetuksia, joissa yleensä käytetään puolipisteitä erottimina (esimerkiksi Ranska tai Saksa). 
   >
   >
   
8. Valitse **Tallenna**.

Käyttäjille ei voi määrittää roolia Power BI Desktopissa. Voit määrittää ne Power BI -palvelussa. Voit ottaa käyttöön Power BI Desktopin dynaamiset suojausominaisuudet hyödyntämällä *username()* - tai *userprincipalname()* -DAX-funktioita, kun oikeat suhteet on määritetty. 

