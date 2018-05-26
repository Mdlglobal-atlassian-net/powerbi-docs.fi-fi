## <a name="define-roles-and-rules-within-power-bi-desktop"></a>Roolien ja sääntöjen määrittäminen Power BI Desktopissa
Power BI Desktopissa voit määrittää rooleja ja sääntöjä. Kun julkaiset Power BI:ssä, myös roolimääritykset julkaistaan.

Voit määrittää tietoturvarooleja noudattamalla seuraavia ohjeita.

1. Tuo tietoja Power BI Desktop ‑raporttiin tai määritä DirectQuery-yhteys.
   
   > [!NOTE]
   > Power BI Desktopissa ei voi määrittää rooleja Analysis Services ‑liveyhteyksille. Se täytyy tehdä Analysis Services ‑mallin sisältä.
   > 
   > 
2. Valitse **Mallinnus**-välilehti.
3. Valitse **Roolien hallinta**.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)
4. Valitse **Luo**.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)
5. Anna roolille nimi. 
6. Valitse taulukko, johon haluat käyttää DAX-sääntöä.
7. Anna DAX-lausekkeet. Lausekkeen tulisi palauttaa joko arvo tosi tai epätosi. Esimerkki: [Entiteetin tunnus] = ”arvo”.
   
   > [!NOTE]
   > Voit käyttää lausekkeessa funktiota *username()*. Huomaa, että *username()* on Power BI Desktopissa muodossa *TOIMIALUE\käyttäjänimi*. Power BI -palvelussa se on käyttäjän UPN:n muodossa. Vaihtoehtoisesti voit käyttää funktiota *userprincipalname()* joka palauttaa käyttäjän aina täydellisen käyttäjätunnuksen muodossa.
   > 
   > 
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)
8. Kun olet luonut DAX-lausekkeen, voit vahvistaa sen valitsemalla lausekeruudun yläpuolelta valintamerkkikuvakkeen.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)
9. Valitse **Tallenna**.

Käyttäjille ei voi määrittää roolia Power BI Desktopista. Se on tehtävä Power BI -palvelusta. Voit ottaa käyttöön Power BI Desktopin dynaamiset suojausominaisuudet hyödyntämällä *username()*- tai *userprincipalname()*-DAX-funktioita, kun oikeat suhteet on määritetty.

