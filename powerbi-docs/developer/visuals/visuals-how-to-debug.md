---
title: Power BI -visualisointien virheenkorjaus
description: Tässä artikkelissa kuvataan Power BI -visualisointien virheenkorjaustapoja.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 02/14/2020
ms.openlocfilehash: 9469127ea28b0370edebd4c044bd929ff22c488f
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "81675704"
---
# <a name="how-to-debug-power-bi-visuals"></a>Power BI -visualisointien virheenkorjaus

Tällä sivulla esitellään vinkkejä virheenkorjaukseen visualisointia luotaessa. Tässä artikkelissa on virheenkorjauksen perusvaiheet, ja siinä esitellään edustan vakiosovellusten ja Power BI -visualisointien virheenkorjauksen erot.
Artikkelin lukemisen jälkeen osaat korjata Power BI -visualisoinnit käyttämällä keskeytyskohtia, lokipoikkeuksia ja sieppauspoikkeuksia Chromessa ja Edgessä.

## <a name="using-breakpoints"></a>Keskeytyskohtien käyttäminen

Koska visualisoinnin JavaScript ladataan kokonaan uudelleen aina, kun visualisointi päivitetään, lisäämäsi keskeytyskohdat häviävät, kun korjattava visualisointi päivitetään. Voit kiertää ongelman käyttämällä koodissa `debugger`-lausekkeita. Automaattinen uudelleenlataus kannattaa poistaa käytöstä, kun `debugger`ia käytetään koodissa.

```typescript
public update(options: VisualUpdateOptions) {
    console.log('Visual update', options);
    debugger;
    this.target.innerHTML = `<p>Update count: <em>${(this.updateCount</em></p>`;
}
```


## <a name="showing-exceptions"></a>Poikkeusten näyttäminen

Kun käsittelet visualisointia, huomaat, että Power BI -palvelu ”syö” kaikki virheet. Tämä on Power BI:n tarkoituksellinen ominaisuus, joka estää virheellisesti käyttäytyviä visualisointeja tekemästä koko sovelluksesta epävakaan.

Voit kiertää ongelman lisäämällä koodin, joka havaitsee ja kirjaa poikkeukset, tai määrittämällä virheenkorjauksen keskeytymään, kun virheitä havaitaan.


## <a name="log-exceptions"></a>Poikkeusten kirjaaminen

Jos haluat kirjata poikkeuksia Power BI -visualisoinnissa, lisää visualisointiin seuraava koodi määrittämään poikkeuksen kirjaamisen decorator-elementti.

```typescript
export function logExceptions(): MethodDecorator {
    return function (target: Object, propertyKey: string, descriptor: TypedPropertyDescriptor<any>): TypedPropertyDescriptor<any> {
        return {
            value: function () {
                try {
                    return descriptor.value.apply(this, arguments);
                } catch (e) {
                    console.error(e);
                    throw e;
                }
            }
        }
    }
}
```
Tämän jälkeen voit käyttää tätä decorator-elementtiä missä tahansa funktiossa, niin näet virheiden kirjauksen.

```typescript
@logExceptions()
public update(options: VisualUpdateOptions) {
```

## <a name="break-on-exceptions"></a>Keskeytys poikkeuksien ilmetessä

Voit myös määrittää selaimen keskeytymään, kun poikkeuksia havaitaan. Näin koodin suorittaminen pysäytetään aina, kun tapahtuu virhe, joten voit tehdä virheenkorjauksen toimenpiteet.

### <a name="edge"></a>Edge

1. Avaa kehittäjien työkalut (F12).
2. Siirry **Virheenkorjaus**-välilehteen.
3. Napsauta **keskeytys poikkeuksien ilmetessä** -kuvaketta (kuusikulmio, jossa on taukosymboli).
4. Valitse **Keskeytys kaikkien poikkeuksien ilmetessä**.

![Tietoroolikentät](media/visuals-how-to-debug/how-to-debug-edge.png)

## <a name="chrome"></a>Chrome

1. Avaa kehittäjien työkalut (F12).
2. Siirry **Lähteet**-välilehteen.
3. Napsauta **keskeytys poikkeuksien ilmetessä** -kuvaketta (stop-merkki, jossa on taukosymboli).
4. Valitse **Keskeytys havaittujen poikkeusten ilmetessä** -valintaruutu.

![Tietoroolikentät](media/visuals-how-to-debug/how-to-debug-chrome.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Power BI -visualisointien vianmääritys](power-bi-custom-visuals-troubleshoot.md)
* Saat lisätietoja ja vastauksia kysymyksiisi [Power BI -visualisointien usein kysytyistä kysymyksistä](power-bi-custom-visuals-faq.md#organizational-power-bi-visuals)
