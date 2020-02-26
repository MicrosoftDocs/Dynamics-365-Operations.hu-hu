---
title: A felosztott rendeléskezelés (DOM) költségkonfigurációja
description: Ez a témakör a Dynamics 365 Commerce felosztott rendeléskezelés (DOM) funkciójára vonatkozó költségkonfigurációt részletezi.
author: josaw1
manager: AnnBe
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7644cb9800a418fd123b32a0257b787277fcb19f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004228"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a>A felosztott rendeléskezelés (DOM) költségkonfigurációja

[!include [banner](../includes/banner.md)]

A szervezeteknek számos költségösszetevőt kell figyelembe venniük annak meghatározására, hogy melyik a rendelés teljesítésének szempontjából optimális helyszín. Ezen költségösszetevők közé tartozik például a szállítási költség, a kezelési költség és a csomagolási költség. Ezeknek a költségeknek a kombinációját ki kell számítani a teljesítési helyszín meghatározása céljából.

A Dynamics 365 Commerce szolgáltatásban a felosztott rendeléskezelés (DOM) első ismétlésekor sor került a megrendelések teljesítési helyszínekhez való hozzárendelésének optimalizálására, a rendszer csak a távolságot vette figyelembe. Ugyan a távolság korrelálható a költséggel, ez nem egyezik meg a költséggel. Például egy 24 órán belüli szállítási módszer többe kerül, mint a háromnapos szállítás vagy a hétnapos szállítás ugyanakkora távolságra.

A költségkonfiguráció funkció segítségével a kiskereskedők meghatározhatják és konfigurálhatják a további költségösszetevőket, amelyeket az rendelési sorok teljesítése céljából optimális helyszín meghatározása céljából ki kell számítani és figyelembe kell venni.

Ha be van állítva a költségösszetevők konfigurálása, a DOM-feloldó csak ezeket a költségmeghatározásokat használja a rendelés teljesítése szempontjából optimális helyszín meghatározásakor. Nem veszi figyelembe a távolság-összetevőt költségként. Azonban ha nincs beállítva a költségösszetevők konfigurálása, a DOM-feloldó használja a távolság-összetevőt költségként a rendelés teljesítése szempontjából optimális helyszín meghatározásakor.

## <a name="set-up-cost-components"></a>Költségösszetevők beállítása

A rendszerben két fő költségösszetevő-típus határozható meg: **Szállítási** és **Egyéb**.

Mindkét típusú költségösszetevő több számítási alapot is támogat, ahogy az alábbi táblázatban látható.

<table>
<thead>
<tr>
<th>Költségösszetevő típusa</th>
<th>Számítás alapja</th>
</tr>
</thead>
<tbody>
<tr>
<td>Szállítás</td>
<td>
<ul>
<li>Egyszerű</li>
<li>Rétegzett</li>
</ul>
</td>
</tr>
<tr>
<td>Egyéb</td>
<td>
<ul>
<li>Értékesítési rendelés</li>
<li>Értékesítési sor</li>
<li>Helyszín</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a>Szállítási költségösszetevő típusa

Ez a szakasz bemutatja, hogy hogyan lehet beállítani a **Szállítási** költségösszetevő-típus és a számítási alap egyes kombinációit a szállítási költségekhez. Bemutatja azt is, hogy a DOM-feloldó miként alkalmazza az egyes kombinációkat.

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a>Költségösszetevő típusa = Szállítási és Számítási alap = Egyszerű

Ha a **Szállítási** költségösszetevő-típus és az **Egyszerű** számítási alap kombinációját alkalmazzák, akkor a szállítási módhoz tartozó szállítási költség egy állandó költségen vagy távolságon alapul.

Ehhez a kombinációhoz a következő mezőket kell beállítani:

- **Költségtényező** – Adja meg a költségtényező egyedi azonosítóját.
- **Leírás** – Adja meg a költségtényező nevét és leírását.
- **Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja. Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.
- **Aktív** – Azt jelzi, hogy a költségtényező aktív-e. A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.
- **Vállalat** – Adja meg azt a jogi személyt, amelyre vonatkozóan konfigurálja a költségtényezőt. A számítási feltétel minden sorának ugyanarra a jogi személyre kell vonatkoznia.
- **Szállítási módok** – Adja meg azokat a szállítási módokat, amelyhez kapcsolódóan konfigurálja a költséget.
- **Számítási típus** – Adja meg a költség számításának módját egy megadott szállítási mód esetén. A szolgáltatásban két számítási típus támogatott:

    - **Rögzített** – Állandó költség, amely az adott szállítási módhoz használatos. Ha ezt a számítási típust választja, akkor a **Költség** mező adja meg az állandó költséget.
    - **Távolságegység szerint** – A szállítási mód költségét a rendszer úgy számítja ki, hogy a **Költség** mezőben megadott költségértéket megszorozza a szállítási cím és a helyszínek közti távolsággal.

- **Költség** – Megadja a **Számítási típus** mezővel kapcsolatban használt költségértéket, amellyel kiszámítható a szállítási mód költsége.

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a>Költségösszetevő típusa = Szállítási és Számítási alap = Rétegzett

Ha a **Szállítási** költségösszetevő-típus és a **Rétegzett** számítási alap kombinációját alkalmazzák, akkor a szállítási módhoz tartozó szállítási költség egy állandó költségen vagy távolságon alapul. Ebben a kombinációban a távolság több távolság rétegzett tartományán alapul.

Ehhez a kombinációhoz a következő mezőket kell beállítani:

- **Költségtényező** – Adja meg a költségtényező egyedi azonosítóját.
- **Leírás** – Adja meg a költségtényező nevét és leírását.
- **Alapértelmezett költség** – Adja meg a szállítási módhoz használt költséget, ha a szállítási cím és a helyszín közti távolság nem esik a szállítási módhoz meghatározott rétegzett távolságok egyikébe sem.
- **Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja. Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.
- **Aktív** – Azt jelzi, hogy a költségtényező aktív-e. A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.
- **Vállalat** – Adja meg azt a jogi személyt, amelyre vonatkozóan konfigurálja a költségtényezőt. A számítási feltétel minden sorának ugyanarra a jogi személyre kell vonatkoznia.
- **Szállítási módok** – Adja meg azokat a szállítási módokat, amelyhez kapcsolódóan konfigurálja a költséget.
- **Távolság típusa** – Adja meg, hogy a rétegzett távolság meghatározása légi vagy közúti távolságra utal-e.
- **Távolságegységek** – Adja meg az egységet, amelyben a rétegzett távolság mérése történjen.
- **Távolság – alsó határ** – Adja meg a rétegzett távolság tartományának alsó határát.
- **Távolság – felső határ** – Adja meg a rétegzett távolság tartományának felső határát.
- **Számítási típus** – Adja meg a költség számításának módját egy megadott szállítási mód és rétegzett távolság esetén. A szolgáltatásban két számítási típus támogatott:

    - **Rögzített** – Állandó költség, amely az adott szállítási módhoz használatos. Ha ezt a számítási típust választja, akkor a **Költség** mező adja meg az állandó költséget.
    - **Távolságegység szerint** – A szállítási mód és a rétegzett távolság költségét a rendszer úgy számítja ki, hogy a **Költség** mezőben megadott költségértéket megszorozza a szállítási cím és a helyszínek közti távolsággal.

- **Költség** – Megadja a **Számítási típus** mezővel kapcsolatban használt költségértéket, amellyel kiszámítható a szállítási mód költsége.

> [!NOTE]
> - A rétegzett távolságok meghatározása során a rendszer ellenőrzi, hogy nincsenek-e hiányzó vagy egymást átfedő távolságok.
> - A szállítási módhoz használt távolságtípusnak az összes rétegzett távolság esetén meg kell egyeznie.

### <a name="other-cost-component-type"></a>Egyéb költségösszetevő-típus

Ez a szakasz bemutatja, hogy hogyan lehet beállítani az **Egyéb** költségösszetevő-típus és az egyéb költségtípus egyes kombinációit a nem szállítási költségekhez. Bemutatja azt is, hogy a DOM-feloldó miként alkalmazza az egyes kombinációkat.

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a>Költségösszetevő típusa = Egyéb és Egyéb költségtípus = Értékesítési rendelés

Az **Egyéb** költségösszetevő és az **Értékesítési rendelés** egyéb költségtípus kombinációja a nem szállítási költségek meghatározására használatos az értékesítési rendelés szintjén.

Ehhez a kombinációhoz a következő mezőket kell beállítani:

- **Költségtényező** – Adja meg a költségtényező egyedi azonosítóját.
- **Leírás** – Adja meg a költségtényező nevét és leírását.
- **Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja. Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.
- **Aktív** – Azt jelzi, hogy a költségtényező aktív-e. A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.
- **Költség** – Adja meg a nem szállítási költségek értékesítési rendelés szintjén vett költségértékét.

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a>Költségösszetevő típusa = Egyéb és Egyéb költségtípus = Értékesítési sor

Az **Egyéb** költségösszetevő és az **Értékesítési sor** egyéb költségtípus kombinációja a nem szállítási költségek meghatározására használatos az értékesítési rendelési sor szintjén.

Ehhez a kombinációhoz a következő mezőket kell beállítani:

- **Költségtényező** – Adja meg a költségtényező egyedi azonosítóját.
- **Leírás** – Adja meg a költségtényező nevét és leírását.
- **Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja. Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.
- **Aktív** – Azt jelzi, hogy a költségtényező aktív-e. A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.
- **Költség** – Adja meg a nem szállítási költségek értékesítési rendelési sor szintjén vett költségértékét.

#### <a name="cost-component-type--other-and-other-cost-type--location"></a>Költségösszetevő típusa = Egyéb és Egyéb költségtípus = Helyszín

Az **Egyéb** költségösszetevő és a **Helyszín** egyéb költségtípus kombinációja a nem szállítási költségek meghatározására használatos helyszínek csoportjára vagy egy egyéni helyszínre vonatkozóan.

Ehhez a kombinációhoz a következő mezőket kell beállítani:

- **Költségtényező** – Adja meg a költségtényező egyedi azonosítóját.
- **Leírás** – Adja meg a költségtényező nevét és leírását.
- **Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja. Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.
- **Aktív** – Azt jelzi, hogy a költségtényező aktív-e. A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.
- **Teljesítési csoport** – Adja meg a helyszíncsoportot, amellyel kapcsolatban meghatározza a nem szállítási költséget.
- **Teljesítési helyszín** – Adja meg a helyszínt, amellyel kapcsolatban meghatározza a nem szállítási költséget.

    > [!NOTE]
    > Nem adható meg teljesítési csoport és teljesítési helyszín ugyanabban a sorban helyszínalapú számítási feltétel esetén.

- **Költség** – Adja meg a nem szállítási költségek teljesítési csoport szintjén vagy teljesítési helyszín szintjén vett költségértékét.

> [!IMPORTANT]
> Ha azt szeretné, hogy a DOM futtatáskor figyelembe vegye ezeket a költségeket, hozzá kell adnia a költségtényezőt a megfelelő teljesítési profilhoz.
