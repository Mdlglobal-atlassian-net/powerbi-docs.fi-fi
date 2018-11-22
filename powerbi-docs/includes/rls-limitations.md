## <a name="limitations"></a>Rajoitukset

Tässä on luettelo tämänhetkisistä rajoituksista pilvimallien rivitason suojaukselle.

* Jos määritit aiemmin roolit ja säännöt Power BI -palvelussa, sinun on luotava ne uudelleen Power BI Desktopissa.

* Voit määrittää rivitason suojauksen vain tietojoukoille, jotka on luotu Power BI Desktopin avulla. Jos haluat ottaa rivitason suojauksen käyttöön tietojoukoille, jotka on luotu Excelin avulla, sinun on ensin muunnettava tiedostosi Power BI Desktop (PBIX) -tiedostoiksi. [Lue lisää](../desktop-import-excel-workbooks.md)

* Vain ETL- ja DirectQuery-yhteyksiä tuetaan. Reaaliaikaisista yhteyksistä Analysis Servicesiin huolehditaan paikallisessa mallissa.

* Q&A:ta ja Cortanaa ei tällä hetkellä tueta rivitason suojauksen kanssa. Q&A-tekstiruutua ei näytetä raporttinäkymissä, jos kaikille malleille on määritetty rivitason suojaus. Tämä on suunnitteilla, mutta aikataulua ei ole.

## <a name="known-issues"></a>Tunnetut ongelmat

Tunnemme ongelman, jossa näyttöön tulee virheviesti, kun käyttäjä yrittää julkaista Power BI Desktopista raportin, joka on julkaistu jo aiemmin. Tilanne on seuraavanlainen.

1. Annalla on tietojoukko, joka on julkaistu Power BI -palveluun ja jolle on määritetty rivitason suojaus.

1. Anna päivittää raportin Power BI Desktopissa ja julkaisee sen uudelleen.

1. Anna kohtaa virheen.

**Vaihtoehtoinen menetelmä:** Julkaise Power BI Desktop -tiedosto uudelleen Power BI -palvelusta, kunnes tämä ongelma on ratkaistu. Voit toimia näin valitsemalla **Nouda tiedot** > **Tiedostot**.
