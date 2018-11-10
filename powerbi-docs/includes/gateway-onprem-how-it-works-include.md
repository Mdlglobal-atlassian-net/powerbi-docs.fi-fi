## <a name="how-the-gateway-works"></a>Yhdyskäytävän toiminta
![Paikallisen-yhdyskäytävän-toiminta](./media/gateway-onprem-how-it-works-include/on-prem-data-gateway-how-it-works.png)

Tarkastellaan ensin, mitä tapahtuu, kun käyttäjä käyttää paikalliseen tietolähteeseen liitettyä elementtiä. 

> [!NOTE]
> Power BI:n kohdalla yhdyskäytävälle on määritettävä tietolähde.

1. Pilvipalvelu luo kyselyn sekä salatut tunnistetiedot paikalliselle tietolähteelle, ja nämä lähetetään jonoon yhdyskäytävän käsiteltäväksi.
2. Yhdyskäytävän pilvipalvelu analysoi kyselyn ja lähettää pyynnön [Azuren Palveluväylään](/azure/service-bus-messaging/service-bus-messaging-overview/).
3. Paikallinen tietoyhdyskäytävä tekee kyselyn Azuren palveluväylään odottavia pyyntöjä varten.
4. Yhdyskäytävä saa kyselyn, purkaa salauksen tunnistetiedot ja muodostaa yhteyden tietolähteisiin kyseisillä tunnistetiedoilla.
5. Yhdyskäytävä lähettää kyselyn tietolähteeseen suoritusta varten.
6. Tulokset lähetetään tietolähteestä takaisin yhdyskäytävään ja sitten pilvipalveluun. Sitten palvelu ottaa tulokset käyttöön.

