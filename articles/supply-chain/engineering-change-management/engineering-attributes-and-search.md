---
title: Mérnöki attribútumok és mérnöki attribútumkeresés
description: Ez a cikk bemutatja, hogy a mérnöki attribútumok használatával lehet megadni az összes nem szabványos jellemzőt, hogy minden alapterméket regisztrálni lehet a rendszerben. Azt is elmagyarázza, hogyan használhatja a mérnöki attribútumkeresést a termékek egyszerű megtalálásához a regisztrált jellemzők alapján.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductAttributeSearch, EngChgMaintainAttributeInheritance, EngChgAttribute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4b25ab0bfda08b7aa091de8c6833007c586b9c87
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852563"
---
# <a name="engineering-attributes-and-engineering-attribute-search"></a>Mérnöki attribútumok és mérnöki attribútumkeresés

[!include [banner](../includes/banner.md)]

Használja a mérnöki attribútumokat az összes nem szabványos jellemző megadására annak érdekében, hogy az összes terméktörzsi adat regisztrálható legyen a rendszerben. Ezután a mérnöki attribútumkeresést használhatja a termékek egyszerű megtalálásához a regisztrált jellemzők alapján.

## <a name="create-engineering-attributes-and-attribute-types"></a>Mérnöki attribútumok és attribútumtípusok létrehozása

A mérnöki termékek általában számos olyan jellemzővel és tulajdonsággal rendelkeznek, amelyeket rögzíteni kell. Bár a tulajdonságok egy részét a szabványos termékmezők használatával is regisztrálhatja, szükség szerint új mérnöki tulajdonságokat is létrehozhat. Megadhatja saját *mérnöki attribútumait*, és a termékdefiníció részévé teheti őket.

Minden mérnöki attribútumnak *attribútumtípushoz* kell tartoznia. Ez a követelmény azért létezik, mert minden mérnöki attribútumnak olyan *adattípussal* kell rendelkeznie, amely meghatározza az általa birtokolható értéktípusokat. A mérnöki attribútumtípus lehet szabványos típus (például szabad szöveg, egész szám vagy tizedes) vagy egyéni típus (például olyan szöveg, amely meghatározott választható értékkészlettel rendelkezik). Az egyes attribútumtípusokat tetszőleges számú mérnöki attribútummal használhatja fel újra.

### <a name="set-up-engineering-attribute-types"></a>Mérnöki attribútumtípusok beállítása

Mérnöki attribútumtípus megtekintéséhez, létrehozásához vagy szerkesztéséhez kövesse az alábbi lépéseket.

1. Nyissa meg a **Mérnöki módosítások kezelése \> Beállítás \> Attribútumok \> Attribútumtípusok** lehetőséget.
1. Jelöljön ki egy meglévő attribútumtípust a listapanelen, vagy válassza az **Új** lehetőséget a Művelet panelen egy új attribútumtípus létrehozásához.
1. Állítsa be a következő mezőket:

    - **Attribútumtípus neve** – Adja meg az attribútumtípus nevét.
    - **Típus** – Válasszon ki egy szabványos adattípust (*Pénznem*, *DateTime*, *Decimális*, *Egész*, *Szöveg*, *Logikai* vagy *Hivatkozás*).
    - **Rögzített lista** – Ez a beállítás csak akkor érhető el, ha a **Szöveg** mezőt *Szöveg* értékre állítja. Állítsa *Igen* értékre az ilyen típusú attribútumok számára meghatározott értékek meghatározásához. Ebben az esetben egy legördülő lista jön létre. Az **Érték** gyorslapon az ehhez az attribútumtípushoz rendelkezésre álló értékeket hozhatja létre. Állítsa ezt a beállítást *Nem* értékre, hogy a felhasználók bármilyen értéket megadhassanak. Ebben az esetben egy beviteli mező jön létre.
    - **Értéktartomány** – Ez a beállítás csak akkor érhető el, ha a **Típus** mezőt *Egész*, *Decimális* vagy *Pénznem* értékre állítja. Állítsa *Igen* értékre az ilyen típusú attribútumokhoz elfogadott minimális és maximális értékek meghatározásához. A **Tartomány** gyorslapon megállapíthatja a minimális és maximális értékeket, valamint (pénznem esetén) a megadott korlátokra vonatkozó pénznemet. Állítsa ezt a beállítást *Nem* értékre. 
    - **Mértékegység** – Ez a mező csak akkor érhető el, ha a **Típus** mezőt *Egész* vagy *Decimális* értékre állítja. Válassza ki az attribútumtípusra vonatkozó mértékegységet. Ha nincs szükség mértékegységre, hagyja üresen ezt a mezőt.

### <a name="set-up-engineering-attributes"></a>Mérnöki attribútumok beállítása

Mérnöki attribútum megtekintéséhez, létrehozásához vagy szerkesztéséhez kövesse az alábbi lépéseket.

1. Nyissa meg a **Mérnöki módosítások kezelése \> Beállítás \> Attribútumok \> Mérnöki attribútumok** lehetőséget.
1. Jelöljön ki egy meglévő attribútumot a listapanelen, vagy válassza az **Új** lehetőséget a Művelet panelen egy új attribútum létrehozásához.
1. Állítsa be a következő mezőket:

    - **Név** – Adjon meg egy nevet az attribútumnak. Ez a név csak a **Mérnöki attribútumok** lapon jelenik meg. A rendszer minden más részén a **Felhasználóbarát név** mező értéke általában az attribútum azonosítására szolgál.
    - **Attribútumtípus** – Az előző szakaszban megadott attribútumtípusok egyikének kiválasztása.
    - **Felhasználóbarát név** – Adjon meg egy nevet, amely azonosítja az attribútumot a rendszerben (kivéve a **Mérnöki attribútumok** lapon). 
    - **Leírás** – Adja meg az attribútumok leírását.
    - **Súgószöveg** – Írja be a súgó szövegét, amely megmondja a többi felhasználónak, hogy mire való az attribútum.
    - **Alapértelmezett érték** – Adja meg az attribútum alapértelmezett értékét. A megjelenő beállítások a kiválasztott attribútumtípustól függenek.
    - **Pénznem** – Ha a kiválasztott attribútumtípus pénznem, válassza ki azt a pénznemet, amelyet az attribútum elfogad, és amelyben megjelennek az értékek.

1. Ha a kiválasztott attribútumtípus egész szám vagy tizedes, a **Tartomány** gyorslap jelenik meg. Ezen a gyorslapon állítsa be a következő mezőket szükség szerint:

    - **Tűréshatár művelete** – Válassza ki, hogyan reagáljon a rendszer, ha a felhasználó a megadott tartományon kívüli értéket ad meg. Ha a *Figyelmeztetés* lehetőséget választja, figyelmeztetés jelenik meg, de a felhasználó mentheti az értéket. Ha a *Nem engedélyezett* lehetőséget választja, figyelmeztetés jelenik meg, és az érték nem menthető, amíg a felhasználó ki nem javítja.
    - **Minimum** – Adja meg a minimális ajánlott vagy elfogadott értéket.
    - **Maximum** – Adja meg a maximális ajánlott vagy elfogadott értéket.

### <a name="engineering-attribute-inheritance"></a>Tervezésiattribútum-öröklődés

Termékstruktúrák, például anyagjegyzékek vagy receptúrák esetén a kiválasztott attribútumok átadhatók az alárendelt elemektől a fölérendelt elemeknek. Ezt a folyamatot "fordított öröklődésnek" nevezhetjük.

#### <a name="turn-engineering-attribute-inheritance-on-or-off"></a>Attribútumöröklődés be- és kikapcsolása

Ehhez a funkcióhoz a mérnöki *változáskezelés* *és* a Jobb attribútumöröklődés a rendszer számára is be kell kapcsolva lennie. A funkciók be- és kikapcsolása a [Műszaki változáskezelés témakörében található](product-engineering-overview.md).

#### <a name="attribute-inheritance-example"></a>Példa attribútumok öröklődésére

Az élelmiszer-termékekhez, például a répatortához a rendszernek rögzítenie kell minden egyes allergént, amit a termék tartalmaz. A répatorta úgy modellezhető a rendszerben, mint egy receptúrával rendelkező tervezési termék. Ez a receptúra tartalmazza a süteményhez szükséges összetevőit, így például a lisztet, a tejet, a répát és a magvakat. Ebben a példában a vállalat két modellt biztosít a répatortához: egyet, amely tartalmaz laktózt és egy másikat, amelyik nem.

A laktózt tartalmazó sütemény az alábbi attribútumokkal rendelkezik az összetevők szintjén:

- Összetevő "liszt": attribútum "glutén" = igen
- Összetevő "tej": attribútum " laktóz" = igen
- Összetevő: "magvak": attribútum "magvak" = igen

A laktózt nem tartalmazó sütemény laktózmentes tejet tartalmaz, és az alábbi attribútumokkal rendelkezik az összetevők szintjén:

- Összetevő "liszt": attribútum "glutén" = igen
- Összetevő "tej": attribútum "laktóz" = nem
- Összetevő: "magvak": attribútum "magvak" = igen

Mivel ezek a termékek többnyire hasonlóak, ezért érdemes a gyermekekből (a két változatból) ezeket az attribútumokat átvinni a szülő termékbe (alap répatorta). Ennek a "fordított öröklésnek" a megvalósításához használhatja az *Attribútumöröklődés* funkciót. Ez a funkció minden egyes [tervezési funkcióhoz](engineering-versions-product-category.md) definiálva van.

## <a name="connect-engineering-attributes-to-an-engineering-product-category"></a>Mérnöki attribútumok összekapcsolása mérnöki termékkategóriával

Egyes mérnöki attribútumok minden termékre vonatkoznak, míg mások az egyes termékekre vagy termékkategóriákra vonatkoznak. Például az elektromos attribútumok nem szükségesek a mechanikus termékekhez. Ezért a *mérnöki termékkategóriákat* állíthat be. A mérnöki termékkategóriák olyan mérnöki attribútumok gyűjteményét határozzák meg, amelyeknek az adott kategóriába tartozó termékek definíciójának részeinek kell lenniük. Meghatározhatja azt is, hogy mely mérnöki attribútumok kötelezőek, és hogy van-e alapértelmezett érték.

A mérnöki termékkategóriák használatával, valamint az attribútumok kategóriákhoz kapcsolásával kapcsolatos további tudnivalókat lásd: [Mérnöki verziók és mérnöki termékkategóriák](engineering-versions-product-category.md).

## <a name="set-attribute-values-for-engineering-attributes"></a>Attribútum megadása a tervezési attribútumok számára

A mérnöki termékkategóriához kapcsolódó mérnöki attribútumok akkor jelennek meg, amikor új mérnöki terméket hoz létre, amely az adott kategórián alapul. Ekkor az attribútumok értékeit is megadhatja. Később ezek az értékek a **Mérnöki verzió** lapon módosíthatók, illetve a mérnöki módosítási rendelésben a mérnöki módosítások kezelése részeként is megadhatók. További tájékoztatást [A mérnöki termékek módosításának kezelése](engineering-change-management.md) részben talál.

## <a name="create-an-engineering-product"></a>Mérnöki termék létrehozása

Egy mérnöki termék létrehozásához nyissa meg a **Kiadott termékek** lapot. Ezután a művelet ablaktáblán a **Termék** lapon az **Új** csoportban válassza a **Mérnöki termék** lehetőséget.

Meg kell adnia azt a mérnöki kategóriát, amelyhez a termék tartozik. A kategória beállítja a termék alapértelmezett értékeit és jellemzőit. A termékre vonatkozó attribútumokat is beállítja. A kategória kiválasztása után a program beállítja az attribútumok értékét. Ezt követően módosíthatja ezeket az értékeket.

## <a name="search-for-products-by-using-engineering-attribute-values"></a>Termékek keresése a mérnöki attribútumok értékei alapján

A mérnöki attribútumkeresés használatával termékeket kereshet a mérnöki attribútumok értékének megkeresésével. Ezért a jellemzőik alapján könnyedén megtalálhatja a mérnöki termékeket. A termékeket egy mérnöki termékkategóriába tartozó termékek között, illetve az összes mérnöki termék között lehet keresni.

A keresés elérhető a termék alapadatainak oldalain és a tranzakciós cikkek között a rendszerben, például az értékesítési rendeléseken. A tranzakciós cikkeknél a **Mérnöki attribútumkeresés** oldalon lehet keresni egy terméket. Ezt követően a **Hozzáadás új sorként** gombbal felveheti a terméket az értékesítésirendelés-sorokba. A keresési eredményekben szereplő termékek közvetlenül is hozzáadhatók a rendeléshez.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
