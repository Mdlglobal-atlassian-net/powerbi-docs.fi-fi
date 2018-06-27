---
title: Q&A Power BI Embeddedissä
description: Power BI Embedded tarjoaa keinon sisällyttää Q&A:n sovellukseen. Käyttäjäsi voivat siis esittää kysymyksiä luonnollisella kielellä.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/20/2017
ms.author: maghan
ms.openlocfilehash: d1fd42f059f8050662adc80018748d11c1e73e2b
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34813752"
---
# <a name="qa-in-power-bi-embedded"></a>Q&A Power BI Embeddedissä
Power BI Embedded tarjoaa keinon sisällyttää Q&A:n sovellukseen. Käyttäjäsi voivat siis esittää kysymyksiä luonnollisella kielellä ja saada vastauksia välittömästi visualisointien muodossa esimerkiksi kaavioina.

![Q&A:n vuorovaikutteinen kysymys upotetussa kehyksessä](media/qanda/embedded-qanda.gif)

Q&A:n upottamisessa sovellukseen on valittavana kaksi tilaa: **vuorovaikutteinen** ja **vain tulos**. **Vuorovaikutteinen**-tilassa voit kirjoittaa kysymykset ja saada ne näkymään visualisoinnissa. Jos kyseessä on tallennettu kysymys tai asetettu kysymys, jonka haluat näyttää, voit käyttää **vain tulos** -tilaa lisäämällä kysymyksen upotetussa määritystiedostossa.

Tässä on esimerkki JavaScript-koodista.

```
// Embed configuration used to describe the what and how to embed.
// This object is used when calling powerbi.embed within the JavaScript API.
// You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
var config= {
    type: 'qna',
    tokenType:   models.TokenType.Embed | models.TokenType.Aad,
    accessToken: access token value,
    embedUrl:    https://app.powerbi.com/qnaEmbed (groupId to be appended as query parameter if required),
    datasetIds:  array of requested data set ids (at the moment we support only one dataset),
    viewMode:    models.QnAMode.Interactive | models.QnAMode.ResultOnly,
    question:    optional parameter for Explore mode (QnAMode.Interactive) and mandatory for Render Result mode (QnAMode.ResultOnly)
};

// Get a reference to the embedded QNA HTML element
var qnaContainer = $('#qnaContainer')[0];

// Embed the QNA and display it within the div container.
var qna = powerbi.embed(qnaContainer, config);
```

## <a name="set-question"></a>Asetettu kysymys
Jos käytit asetetussa kysymyksessä **tulostilaa**, voit syöttää lisäkysymyksiä kehykseen ja saada vastauksen näkyviin heti edellisen tuloksen tilalle. Uusi visualisointi hahmonnetaan vastaamaan uutta kysymystä.

Esimerkki tämän käytöstä on usein kysyttyjen kysymysten luettelo. Käyttäjä voi käydä läpi kysymyksiä ja saada niihin vastauksen saman upotetun osan sisällä.

**JS SDK -käytön koodikatkelma:**  

```        
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

qna.setQuestion("This year sales")
    .then(function (result) {
        …….
    })
    .catch(function (errors) {
        …….
    });
```

## <a name="visual-rendered-event"></a>Visualisoinnilla hahmonnettu tapahtuma
**Vuorovaikutteinen**-tilassa sovellus voi saada ilmoituksen tietojen muutostapahtumasta aina, kun hahmonnettu visualisointi muuttuu syötetyn kyselyn tuloksen päivittämiseksi, kun sitä kirjoitetaan.

Kun kuuntelet *visualRendered*-tapahtumaa, voit tallentaa kysymyksiä myöhempää käyttöä varten. 

**JS SDK -käytön koodikatkelma:**  

```
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

// qna.off removes a given event listener if it exists.
qna.off("visualRendered");

// qna.on will add an event listener.
qna.on("visualRendered", function(event) {
     …….
});
```

## <a name="embed-token"></a>Upotustunnus
Aloita Q&A-osa luomalla upotustunnus tietojoukosta. Lisätietoja on artikkelissa [Tunnuksen luominen](https://docs.microsoft.com/rest/api/power-bi/embedtoken).

## <a name="next-steps"></a>Seuraavat vaiheet
Jos haluat kokeilla Q&A:n upotusta, tutustu [JavaScript-upotuksen malliin](https://microsoft.github.io/PowerBI-JavaScript/demo/).

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

