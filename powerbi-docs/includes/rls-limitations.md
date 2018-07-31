## <a name="limitations"></a>Rajoitukset
Tässä on luettelo tämänhetkisistä rajoituksista pilvimallien rivitason suojaukselle.

* Jos sinulla on Power BI -palvelussa aiemmin määritettyjä rooleja ja sääntöjä, sinun on luotava ne uudelleen Power BI Desktopin sisällä.
* Voit määrittää rivitason suojauksen ainoastaan tietojoukoille, jotka on luotu käyttäen Power BI Desktop -asiakasta. Jos haluat ottaa rivitason suojauksen käyttöön tietojoukoille, jotka on luotu Excelillä, sinun on ensin muunnettava tiedostot PBIX-tiedostoiksi. [Lue lisää](../desktop-import-excel-workbooks.md)
* Vain ETL- ja DirectQuery-yhteyksiä tuetaan. Reaaliaikaisista yhteyksistä Analysis Servicesiin huolehditaan paikallisessa mallissa.
* Q&A:ta ja Cortanaa ei tällä hetkellä tueta rivitason suojauksen kanssa. Q&A-tekstiruutua ei näytetä raporttinäkymissä, jos kaikille malleille on määritetty rivitason suojaus. Tämä on suunnitteilla, mutta aikataulua ei ole.
* Minkä tahansa mallin kohdalla Azure AD -pääkohteiden (eli yksittäiset käyttäjät tai käyttöoikeusryhmät), jotka voidaan liittää käyttöoikeusrooleihin, enimmäismäärä on 1 000. Suurten käyttäjämäärien liittämiseksi rooleihin määritä käyttöoikeusryhmiä yksittäisten käyttäjien sijaan.

## <a name="known-issues"></a>Tunnetut ongelmat
Tunnemme ongelman, jossa näyttöön tulee virhesanoma, kun käyttäjä yrittää julkaista Power BI Desktopista kohteen, joka on julkaistu jo aiemmin. Tilanne on seuraavanlainen.

1. Annalla on tietojoukko, joka on julkaistu Power BI -palveluun ja jolle on määritetty rivitason suojaus.
2. Anna päivittää raportin Power BI Desktopissa ja julkaisee sen uudelleen.
3. Anna kohtaa virheen.

**Ratkaisu:** julkaise Power BI Desktop -tiedosto uudelleen Power BI-palvelusta, kunnes tämä ongelma on ratkaistu. Voit toimia näin valitsemalla **Nouda tiedot** > **Tiedostot**. 

