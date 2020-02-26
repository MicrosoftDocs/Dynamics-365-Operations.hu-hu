---
title: Tárolómodul
description: Ez a témakör a tárolómodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 93c16da0988cc955835231bdd1f7342f19063f85
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025528"
---
# <a name="container-module"></a>Tárolómodul


[!include [banner](includes/banner.md)]

Ez a témakör a tárolómodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A tárolómodul egy modul, amely a többi modult tárolja. A tárolómodul elsődleges célja, hogy a számára beállított tulajdonságokon keresztül meghatározza a benne tárolt modulok elrendezését. Ezek a modulok például egymás mellett kétoszlopos, háromoszlopos, négyoszlopos vagy hatoszlopos elrendezésében jelenhetnek meg. A tárolók szélességére korlátozódhatnak, vagy kitölthetik a képernyőt. Minden tárolómodulhoz hozzáadhat egy fejlécet is.

A tárolómoduloknak három típusa támogatott: tároló, tároló 2 hellyel és tároló 3 hellyel. Bármilyen típusú modult el lehet helyezni ezekben a tárolókban. 

> [!NOTE] 
> Javasoljuk, hogy a modulokat mindig tárolómodulban helyezze el, hogy azok a konténerek szélességére korlátozódjanak.

## <a name="examples-of-container-modules-in-e-commerce"></a>Példák az e-kereskedelmi tárolómoduljaira

- A webhely szerzője háromoszlopos elrendezést szeretne, ahol három modul egymás mellett jelenik meg. A webhely szerzője ezért egy 3 helyes tároló típusú tárolómodult használ.
- A webhely szerzője hatoszlopos elrendezést szeretne, ahol hat modul egymás mellett jelenik meg. A webhely szerzője ezért olyan típusú tárolót használ, amely hat oszloppal rendelkezik.
- A webhely szerzője egy modult szeretne elhelyezni a képernyőn, de nem akarja, hogy az kitöltse a képernyőt. A webhely szerzője ezért hozzáad egy modult egy tárolómodulhoz, és a tároló **Szélesség** tulajdonságát a **Tárolóhoz igazított** értékre állítja be.

## <a name="container-module-properties"></a>Tárolómodul tulajdonságai

| Tulajdonság neve     | Értékek | Leírás |
|-------------------|--------|-------------|
| Címsor           | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A tároló számára opcionális fejlécet lehet megadni. Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja. A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében. |
| Szélesség             | **Tárolóhoz igazított** vagy **Képernyő kitöltése** | Ha az érték **Tárolóhoz igazított** (az alapértelmezett érték), akkor a tárolóban lévő modulok a tároló szélességére korlátozódnak. Ha az érték **Képernyő kitöltése**, akkor a modulok nem korlátozódnak a tároló szélességére, hanem kitölthetik akár a képernyőt is. |
| Oszlopok száma | **1**, **2**, **3**, **4**, **6** vagy **12** | Ez a tulajdonság határozza meg a tároló oszlopainak számát. Egy tároló legfeljebb 12 oszlopot tartalmazhat. |

## <a name="container-with-2-slots"></a>2 helyes tároló

A 2 helyes típusú tárolót kétoszlopos elrendezésre optimalizálták. Az ilyen típusú tároló két hellyel rendelkezik, hogy lehetővé tegye a benne található modulok egymás melletti megjelenítését.

További tulajdonságok használhatók a különböző megtekintési területek (mobileszközök, táblagépek, számítógépek stb.) elrendezésének optimalizálása céljából. Minden megtekintési terület számára megadható az egyes oszlopok szélessége. A következő oszlopszélesség-beállítások állnak rendelkezésre:

- **75%/25%** – Az első modulhoz 75 százalékos oszlopszélesség tartozik, a második modulhoz pedig 25 százalékos. **25%/75%**-os beállítás is elérhető.
- **50%/50%** – Mindkét modulban egyenlő az oszlopszélesség.
- **67%/33%** – Az első modulhoz 67 százalékos oszlopszélesség tartozik, a második modulhoz pedig 33 százalékos. **33%/67%**-os beállítás is elérhető.
- **100%** – Mindkét modulhoz teljes oszlopszélesség tartozik. Ennek megfelelően a modulok egy oszlopban, egymás felett helyezkednek el. Annak ellenére, hogy ez az egyoszlopos elrendezés ellentétes a 2 helyes típusú tároló céljával, előnyösebb lehet bizonyos megtekintési területek esetében (például a különösen kis megtekintési területtel rendelkező mobileszközök esetében).

### <a name="container-with-2-slots-properties"></a>2 helyes tároló tulajdonságai

| Tulajdonság neve                   | Értékek | Leírás |
|---------------------------------|--------|-------------|
| Címsor                         | Fejlécszöveg és fejléccímke | A tároló számára opcionális fejlécet lehet megadni. |
| Különlegesen kis méretű megtekintési terület konfigurációja | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** vagy **100%** | Ez a tulajdonság határozza meg a különösen kis méretű megtekintési területek elrendezését. |
| Kis méretű megtekintési terület konfigurációja   | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** vagy **100%** | Ez a tulajdonság határozza meg a kis méretű megtekintési területek (például a mobileszközökön) elrendezését. |
| Közepes méretű megtekintési terület konfigurációja  | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** vagy **100%** | Ez a tulajdonság határozza meg a közepes méretű megtekintési területek (például a táblagépeken) elrendezését. |
| Nagy méretű megtekintési terület konfigurációja   | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** vagy **100%** | Ez a tulajdonság határozza meg a nagy méretű megtekintési területek (például a számítógépeken) elrendezését. |

## <a name="container-with-3-slots"></a>3 helyes tároló

A 3 modulhelyes típusú tárolót háromoszlopos elrendezésre optimalizálták.

További tulajdonságok használhatók a különböző megtekintési területek elrendezésének optimalizálása céljából. Minden megtekintési terület számára megadható az egyes oszlopok szélessége. A következő oszlopszélesség-beállítások állnak rendelkezésre:

- **33%/33%/33%** – Mindhárom modulban egyenlő az oszlopszélesség.
- **50%/25%/25%** – Az első modulhoz 50 százalékos oszlopszélesség tartozik, a fennmaradó két modulhoz pedig 25 százalékos. **25%/50%/25%** és **25%/25%/50%**-os lehetőség is elérhető.
- **16%/16%/67%** – Az első két modulhoz 16 százalékos oszlopszélesség tartozik, a harmadik modulhoz pedig 67 százalékos. **16%/67%/16%** és **67%/16%/16%**-os lehetőség is elérhető.

### <a name="container-with-3-slots-properties"></a>3 helyes tároló tulajdonságai

| Tulajdonság neve                   | Értékek | Leírás |
|---------------------------------|--------|-------------|
| Címsor                         | Fejlécszöveg és fejléccímke | A tároló számára opcionális fejlécet lehet megadni. |
| Különlegesen kis méretű megtekintési terület konfigurációja | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** vagy **67%/16%/16%** | Ez a tulajdonság határozza meg a különösen kis méretű megtekintési területek elrendezését. |
| Kis méretű megtekintési terület konfigurációja   | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** vagy **67%/16%/16%** | Ez a tulajdonság határozza meg a kis méretű megtekintési területek (például a mobileszközökön) elrendezését. |
| Közepes méretű megtekintési terület konfigurációja  | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** vagy **67%/16%/16%** | Ez a tulajdonság határozza meg a közepes méretű megtekintési területek (például a táblagépeken) elrendezését. |
| Nagy méretű megtekintési terület konfigurációja   | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** vagy **67%/16%/16%** | Ez a tulajdonság határozza meg a nagy méretű megtekintési területek (például a számítógépeken) elrendezését. |

## <a name="add-a-container-module-to-a-page"></a>Tárolómodul hozzáadása egy oldalhoz

A tárolómodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **tárolósablon** nevű oldalsablont. 
1. Adja hozzá a **Törzs** tárolóhelyen az **Alapértelmezett oldal** modult.
1. Fejezze be a sablon szerkesztését, és tegye közzé.
1. A most létrehozott tárolósablon használatával hozzon létre egy **tárolólap** nevű lapot.
1. Az új lap **Fő** helyén adjon hozzá egy tárolómodult.
1. A tárolómodul tulajdonságlapján adja meg az **Oszlopok száma** tulajdonságnak az **1**, a **Szélesség** tulajdonságnak pedig a **Tároló kitöltése** értéket.
1. Vegyen fel egy tartalomblokkmodult a tárolómodulba.
1. A szövegblokkmodul tulajdonságlapján konfigurálja a címsort, a képet és az elrendezést.
1. Mentse a lapot, és tekintse meg az előnézetét. Egy olyan funkciómodult kell látnia, amely a tárolómodul szélességének felel meg.
1. A tárolómodul tulajdonságlapján módosítsa az **Oszlopok száma** tulajdonságot **3** értékre.
1. A tárolómodulban adjon hozzá két további tartalomblokkmodult.
1. Mentse a lapot, és tekintse meg az előnézetét. Most három egymás mellett megjelenő tartalomblokkmodult kell látnia.
1. Miután elérte a kívánt elrendezést, fejezze be az oldal szerkesztését, és tegye közzé a lapot.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Forgótármodul](add-carousel.md)

[Szövegblokk modul](add-content-rich-block.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
