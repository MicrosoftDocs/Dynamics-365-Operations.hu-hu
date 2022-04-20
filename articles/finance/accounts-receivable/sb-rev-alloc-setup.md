---
title: Több elem bevételfelosztásának beállítása
description: Ez a témakör azt ismerteti, hogyan lehet beállítani az előfizetési számlázási elem bevételfelosztásának paramétereit.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: e422b16d1c4505b2837bb282918ecada902b806e
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2022
ms.locfileid: "8566564"
---
# <a name="set-up-multiple-element-revenue-allocation"></a>Több elem bevételfelosztásának beállítása

A több elemből származó bevételfelosztás révén különböző sablonokat állíthat be, amelyek a bevétel több cikkre történő kiszámításához és felosztáséhez használhatók. Ez a funkció segítséget nyújt a 606-os (ASC 606) és/vagy nemzetközi pénzügyi jelentési standard (IFRS 15) könyvelési szabványok (Codification Topic) betartásában.

## <a name="multiple-element-revenue-allocation-parameters"></a>Több elem bevételfelosztási paraméterei

A Több elemből **származó bevételfelosztási paraméterek** lapon beállíthatja a több elem bevételfelosztásának paramétereit.

### <a name="standalone-selling-price-origin"></a>Önálló eladási ára eredete

Az **önálló eladási ár eredete** mező határozza meg, hogy honnan származik az önálló eladási ár. Az értéket a Cikk **önálló** eladási ár lapján és a tranzakcióban is frissítheti. Az alábbi lehetőségek közül választhat.

| Beállítás | Leírás |
|--------|-------------|
| Összeg | A önálló eladási ár olyan összeg, amelynél 0-nál nagyobb értéket ad meg. A rendszer szükség esetén átváltja az összeget a funkcionális és az eredeti pénznemek között. |
| Eladási alapár | A különálló eladási ár megegyezik a cikk értékesítési alapárával. |
| Számlán szereplő ár | A különálló eladási ár megegyezik a cikk számlaárával. |
| Cikk százaléka | A különálló eladási ár százalékos értékként van megadva, és számítása a cikk ára alapján történik. Ha ezt a lehetőséget választja, adja meg az alapértelmezett százalékot. |
| Fennmaradó összeg felosztása | <p>A különálló *eladási* *ár eredetének számítása a szülőcikk teljes szerződési értéke – a gyermekcikkek önálló eladási ára összesen:*</p><ul><li>*A szülőcikk teljes szerződési* értéke a nettó vagy számláolt összeg.</li><li>*A gyermekcikkek* önálló eladási ára az összes gyermekcikk kiterjesztett vagy szerződéses önálló eladási árának az összege, kivéve azt a gyermekcikket, amely ezt az önálló eladási árat használja.</li></ul><p>Ha a számított összeg negatív, az összeg 0 (nulla) lesz.</p><p>**Megjegyzés:** Ez a beállítás csak egy gyermek cikkre választható ki a bevétel felosztásában.</p> |
| Nincs | A különálló eladási ár eredete a gyermekelemeken alapul. Ez a beállítás olyan cikkekre vonatkozik, amelyek szülő cikkként vannak meghatározva egy bevétel felosztási sablonban. Ha a **Bevétel felosztása** jelölőnégyzet be van jelölve, ez a beállítás automatikusan be van jelölve, és a beállítás nem módosítható. |
| Szülő számlaár százaléka | A önálló eladási ár eredete a szülő cikk számlázási árának bizonyos százaléka. Az alapértelmezett érték megváltoztatható. Ez a beállítás csak a bevétel felosztási sablonjának gyermek cikkeinél érhető el. |
| Szülő normál ár százaléka | A önálló eladási ár eredete a szülőcikk normál árának bizonyos százaléka. Az alapértelmezett érték megváltoztatható. Ez a beállítás csak a bevétel felosztási sablonjának gyermek cikkeinél érhető el. Ez az alapértelmezett beállítás a gyermekelemek esetén. Amikor egy gyermekcikk beállítását a szülő alapár százalékáraról a szülő számla árának százalékára, vagy a szülő számla árának Százalék értékről a szülő alapár százaléka beállításra változott, akkor **a** **·** **·** **számított** értékek is frissülnek. |

### <a name="account-for-revenue-allocation-rounding-differences"></a>Számla a bevételfelosztás kerekítési különbözeteihez

A **bevételfelosztás kerekítési eltérési** számlája mező azt a számlát határozza meg, amely a szerződéses bevétel összegének kerekítési korrekcióit rögzíti. Ismétlődő szerződés számlázása esetén érhető el.

## <a name="item-standalone-selling-price"></a>Cikk önálló eladási ára

A Cikk **önálló eladási** ár lapján lehet megadni a cikk eredetét és önálló eladási árát. Az ezen a lapon megadott **értékeket** használja a rendszer alapértelmezett értékként a Bevételfelosztás lapon több elem bevételfelosztása és ismétlődő szerződés számlázása esetén.

### <a name="specify-item-standalone-selling-price"></a>Cikk önálló eladási árának megadása

A cikkek önálló árának megadásához kövesse az alábbi lépéseket.

1. A Cikk önálló **eladási** ára oldalon, **az** Önálló eladási ár eredete mezőben válassza ki a önálló eladási ár eredetét.
2. Kövesse az alábbi lépéseket attól függően, **hogy milyen értéket választott az Önálló eladási ár eredete mezőben**:

    * Ha a Cikk Százaléka **beállítást választotta**, adja meg a százalékos értéket a Százalék **mezőben**.
    * Ha az Összeg beállítást **választotta, adja meg az összeget az** Önálló eladási ár mezőben **.**

2. A listához hozzáadni kívánt cikkekhez válassza a Hozzáadás **lehetőséget**.
3. A Cikk-kód **mezőben** válassza ki a cikk-kódot. A Cikk-kapcsolat **mezőben** válassza ki a cikk-kapcsolatot. Az olyan cikkeknél, amelyeknél **nincs** bejelölve a Bevétel felosztása jelölőnégyzet, a cikkkód és a cikk-kapcsolat kiválasztott kombinációjának egyedinek kell lennie.
4. Ha szükséges **, módosítsa az önálló eladási ár eredete,** **·** **önálló eladási ár vagy Százalék mező alapértelmezett értékét.**
5. Válassza a Hozzáadás elemet minden olyan szülőelemhez, amely fel szeretné adni a **listára**.
6. A Cikk-kód **mezőben** válassza ki a cikk-kódot. A Cikk-kapcsolat **mezőben** válassza ki a cikk-kapcsolatot.
7. Jelölje be **a Bevétel felosztása** jelölőnégyzetet.
8. A Cikk-kapcsolat **mezőben** válassza ki a cikk-kapcsolatot. A lista a szülőcikkhez és az összes gyermek cikkhez frissül.
9. A gyermekcikk esetében **módosítsa az önálló eladási ár eredetének, a szülő alapár százalékának,** **·** **·** **a szülőszámla árának százalékában vagy a Fennmaradó összeg felosztása mező értékét.**
10. Ha egyszerre több elemet szeretne hozzáadni, válassza a Cikkek **hozzáadása lehetőséget**.
11. A lekérdezés frissítése a hozzáadni kívánt cikktartomány kiválasztásához.
12. Válassza **az OK** elemet, tekintse át a hozzáadott cikkek listáját, és válassza az **OK elemet**.

### <a name="fields"></a>Mezők

A **Cikk önálló eladási ára** lap a következő mezőket tartalmazza.

| Mező | Leírás |
|-------|-------------|
| Önálló eladási ára eredete | <p>Válassza ki az önálló eladási ár eredetét:</p><ul><li>**Összeg** – a önálló eladási ár olyan összeg, amelynél 0-nál nagyobb értéket ad meg. A rendszer szükség esetén átváltja az összeget a funkcionális és az eredeti pénznemek között.</li><li>**Eladási alapár** – az önálló eladási ár megegyezik a cikk értékesítési alapárával.</li><li>**Számlaár** – a különálló eladási ár megegyezik a cikk számlaárával.</li><li>**Cikk százaléka** – az önálló eladási ár százalékos értékként van megadva, és számítása a cikk ára alapján történik. Ha ezt a lehetőséget választja, adja meg az alapértelmezett százalékot.</li></ul>**Fennmaradó összeg felosztása** – *az* önálló eladási ár eredetének számítása a szülőcikk teljes szerződési értékeként történik – *a gyermekcikkek teljes önálló eladási ára*:</p><ul><li>*A szülőcikk teljes szerződési* értéke a nettó vagy számláolt összeg.</li><li>*A gyermekcikkek* önálló eladási ára az összes gyermekcikk kiterjesztett vagy szerződéses önálló eladási árának az összege, kivéve azt a gyermekcikket, amely ezt az önálló eladási árat használja.</li></ul><p>Ha a számított összeg negatív, az összeg 0 (nulla) lesz.</p><p>**Megjegyzés:** Ez a beállítás csak egy gyermek cikkre választható ki a bevétel felosztásában.</p></li><li>**Nincs** – az önálló eladási ár eredete a gyermek cikkeken alapul. Ez a beállítás olyan cikkekre vonatkozik, amelyek szülő cikkként vannak meghatározva egy bevétel felosztási sablonban. Ha a **Bevétel felosztása** jelölőnégyzet be van jelölve, ez a beállítás automatikusan be van jelölve, és a beállítás nem módosítható.</li><li>**Szülőszámla árának százaléka** – az önálló eladási ár eredete a szülő cikk számlázási árának százaléka. Az alapértelmezett érték megváltoztatható. Ez a beállítás csak a bevétel felosztási sablonjának gyermek cikkeinél érhető el.</li><li>**Szülő normál árának százaléka** – a különálló eladási ár eredete a szülőcikk normál árának százaléka. Az alapértelmezett érték megváltoztatható. Ez a beállítás csak a bevétel felosztási sablonjának gyermek cikkeinél érhető el. Ez az alapértelmezett beállítás a gyermekelemek esetén. Amikor egy gyermekcikk beállítását a szülő alapár százalékáraról a szülő számla árának százalékára, vagy a szülő számla árának Százalék értékről a szülő alapár százaléka beállításra változott, akkor **a** **·** **·** **számított** értékek is frissülnek.</li></ul> |
| Önálló eladási ár | A cikk önálló eladási árának meghatározása. Ez a mező akkor érhető el, ha **az Önálló eladási ár eredete** mező beállítása **Összeg**. |
| Százalék | Az önálló eladási ár százalékos meghatározása. Ez a mező akkor érhető el, ha **az önálló** **eladási** ár eredete mező beállítása a cikk százaléka, **·** **a szülő számla árának százaléka vagy a szülő szokásos ár százaléka.** |
| Bevételfelosztás | <p>Annak megadása, hogy a sor bevétel-felosztást használ-e:</p><ul><li>**Kiválasztva** – a Cikkkapcsolat mezőben csak azok a **cikkek választhatók ki, amelyekhez bevétel felosztási sablon van beállítva**. Ez a jelölőnégyzet csak a bevétel felosztási sablonjának szülő cikkeit jelölheti be.</li><li>**Törölve** – a cikk olyan normál cikk, amely nem használja fel a bevétel felosztását.</li></ul> |
| Kapcsolat | Ez a szimbólum jelzi, hogy a cikk szülő vagy gyermek cikk-e a bevétel felosztásában. |
| Cikk kódja | <p>Válassza ki a cikk kódját: **tábla** vagy **csoport**.</p><p>Ha a **Bevétel** felosztása jelölőnégyzet be van jelölve, ez **a** mező Tábla értékre van állítva, és az érték nem módosítható.</p> |
| Cikk-kapcsolat | <p>Válasszon egy cikkszámot.</p><p>Ha a Bevétel **felosztása** jelölőnégyzet be van jelölve, csak azok a szülő cikkek érhetők el kiválasztásra, amelyek bevétel felosztási sablonja be van állítva. Ha ki van választva a szülő cikk, a lista automatikusan frissül a szülőcikk gyermekelemével.</p> |
| Szülő cikk | A szülő cikk mezőben a cikkszám látható. A bevétel felosztása alatt lévő gyermek cikkeknél a szülő cikk cikkszáma látható. |

## <a name="mea-templates"></a>MEA-sablonok

**A MEA-sablonok** lapon hozhat létre és szerkeszthet több meA sablon-elrendezést. Ezek az elosztási elemek a **Bevétel** felosztása lapon használhatók a cikkek csoportosítására.

### <a name="create-a-template"></a>Sablon létrehozása

A MEA-sablon beállítását a következő lépések szerint hajtsa végre.

1. Válassza az **Új lehetőséget a MEA-sablonok** **lapon**.
1. **A MEA sablonazonosító** mezőbe írjon be egy egyedi azonosítót.
1. Adjon meg egy leírást a **Leírás** mezőben.
1. Válassza ki a **Halasztott szerződés bevétele számla** mezőben azt a számlát, amely a meA-szerződés számlája létrehozásakor naplóbejegyzések esetén használható. Ez a mező akkor érhető el, ha az ismétlődő szerződés számlázása engedélyezve van és van használva.
1. Válassza a **Mentés** lehetőséget.
