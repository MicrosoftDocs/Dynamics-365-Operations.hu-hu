---
title: Bevétel felosztása
description: Ez a témakör bemutatja, hogy hogyan használhatók a bevételfelosztások az előfizetéses számlázásban.
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
ms.openlocfilehash: 2a1bdff364039c6bf0cdfbc11f0979398934c52c
ms.sourcegitcommit: 836695c0e95d366ba993f34eee30f57191f356d8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2022
ms.locfileid: "8629698"
---
# <a name="revenue-allocation"></a>Bevétel felosztása

Ez a témakör bemutatja a számlázási ütemezés bevételfelosztási paramétereinek beállítását. A bevételfelosztásokat a számlázási ütemezés létrehozásakor állíthatja be és szerkesztheti. Ha egy aktív vagy megszakított **számlázási** ütemezés bevételfelosztási lapját nyitja meg, a mezők csak olvashatók.

## <a name="specify-the-revenue-allocation-for-a-billing-schedule"></a>A bevételfelosztás megadása számlázási ütemezéshez

A számlázási ütemezés bevételének felosztását a következő lépések szerint lehet megadni.

1. A Mind **/Aktív számlázási** ütemezések listaoldalon válasszon ki egy számlázási ütemezést vagy egy számlázási ütemezési sort.
2. A lap **tetején lévő Bevételfelosztás** lapon válassza a Bevétel felosztása **lehetőséget**.
3. A Többelem-elrendezéstípus **mezőben** válassza ki a többelem-elrendezés (MEA) típusát.
4. Adja meg **a** MEA-számot a Többelem-elrendezés száma mezőben. Ezt követően a Halasztott **szerződés bevétele számlamezőben** adja meg a halasztott szerződés bevételi számláját.

    Ha a Több elem elrendezéstípus **mezőjének** értéke **Egyetlen**, akkor **minden** **sorra** ugyanaz a Többelem típusú elrendezésszám és a Halasztott szerződés bevételszámla értékei vonatkoznak. Ha a Több elemelrendezés **típus** mezőjét Több **elemelrendezésre** állíthatja be, **·** **akkor minden sorhoz más-más elem elrendezésszámát és halasztott szerződési árbevételszámla-értékeit** állíthatja be.
    
    MeA-szám csak két vagy több cikkhez rendelhető hozzá. Egyetlen sornak nem lehet saját MEA száma.

5. Válassza a **Mentés** lehetőséget.

### <a name="fields"></a>Mezők

A **Többelem-elrendezés lap** a következő mezőket tartalmazza.

| Mező | Leírás |
|---|---| 
| Többelemes rendezés típusa | <p>Válassza ki a tranzakció MEA-típusát:</p><ul><li>**Többszörös** – a tranzakció sorai az MEA részei, vagy egynél több elrendezés létezik.</li><li>**Nincs** – a tranzakció olyan szokásos tranzakció, amely nem tartozik bevételhez.</li><li>**Egyetlen** – a tranzakcióban lévő összes cikk egyetlen MEA része.</li></ul> |
| Többelemes rendezés száma | <p>A sor MEA-száma Ez a mező akkor érhető el, ha **az Elem több típusú elrendezése** mező beállítása **Több**.</p><p>Ha ez a mező üres, és meA számot ad hozzá, **·** **·** **akkor** a program automatikusan frissíti az önálló eladási ár eredete és az önálló eladási ár mezőit a Cikk önálló eladási ára oldalon található értékek alapján. Csak az értékesítési rendelés más soraihoz rendelt MEA-számok érhetők el.</p> |
| Halasztott szerződéses bevételi számla | MeA szerződési számla létrehozásakor a naplóbejegyzések esetében használt számla megadása. Ez a mező csak ismétlődő szerződés számlázása esetén érhető el. |
| **Sorok** | |
| Változat száma | Az értékesítési rendelés változatszáma. |
| Cikkszám | Az értékesítési rendelésen cikkszám. |
| Számlázási gyakoriság | A bevételfelosztás gyakorisága: **napi, havi** **, negyedéves** **,** féléves **vagy** éves gyakorisággal **.** |
| Mennyiség | Az értékesítési rendelésen megadott érték. |
| Szerződés értéke | A szerződés értéke. |
| Többelemes rendezés száma | <p>A sor MEA-száma Ez a mező akkor érhető el, ha **az Elem több típusú elrendezése** mező beállítása **Több**.</p><p>Ha ez a mező üres, és meA számot ad hozzá, **·** **·** **akkor** a program automatikusan frissíti az önálló eladási ár eredete és az önálló eladási ár mezőit a Cikk önálló eladási ára oldalon található értékek alapján. Csak az értékesítési rendelés más soraihoz rendelt MEA-számok érhetők el. Ha ezek az értékek nincsenek beállítva a cikkhez, **a Többelems bevételfelosztási paraméterek lapon található** értékeket használja a rendszer.</p> | 
| Önálló eladási ára eredete | <p>Az önálló eladási ár eredete:</p><ul><li>**Összeg** – a önálló eladási ár olyan összeg, amelynél 0-nál nagyobb értéket ad meg. A rendszer szükség esetén átváltja az összeget a funkcionális és az eredeti pénznemek között.</li><li>**Eladási alapár** – az önálló eladási ár megegyezik a cikk értékesítési alapárával.</li><li>**Számlaár** – a különálló eladási ár megegyezik a cikk számlaárával.</li><li>**Cikk százaléka** – az önálló eladási ár százalékos értékként van megadva, és számítása a cikk ára alapján történik. Ha ez a beállítás be van jelölve, adja meg az alapértelmezett százalékot.</li><li>**Fennmaradó összeg felosztása** – *az* önálló eladási ár eredetének számítása a szülőcikk teljes szerződési értékeként történik – *a gyermekcikkek teljes önálló eladási ára*:</p><ul><li>*A szülőcikk teljes szerződési* értéke a nettó vagy számláolt összeg.</li><li>*A gyermekcikkek* önálló eladási ára az összes gyermekcikk kiterjesztett vagy szerződéses önálló eladási árának az összege, kivéve azt a gyermekcikket, amely ezt az önálló eladási árat használja.</li></ul><p>Ha a számított összeg negatív, az összeg 0 (nulla) lesz.</p><p>**Megjegyzés:** Ez a beállítás csak egy gyermek cikkre választható ki a bevétel felosztásában.</p></li><li>**Nincs** – az önálló eladási ár eredete a gyermek cikkeken alapul. Ez a beállítás olyan cikkekre vonatkozik, amelyek szülő cikkként vannak meghatározva egy bevétel felosztási sablonban. Ha a **Bevétel felosztása** jelölőnégyzet be van jelölve, ez a beállítás automatikusan be van jelölve, és a beállítás nem módosítható.</li><li>**Szülőszámla árának százaléka** – az önálló eladási ár eredete a szülő cikk számlázási árának százaléka. Ez a beállítás csak a bevétel felosztási sablonjának gyermek cikkeinél érhető el.</li><li>**Szülő normál árának százaléka** – a különálló eladási ár eredete a szülőcikk normál árának százaléka. Ez a beállítás csak a bevétel felosztási sablonjának gyermek cikkeinél érhető el. Amikor egy gyermekcikk beállítását a szülő alapár százalékáraról a szülő számla árának százalékára, vagy a szülő számla árának Százalék értékről a szülő alapár százaléka beállításra változott, akkor **a** **·** **·** **számított** értékek is frissülnek.</li></ul> |
| Önálló eladási ár | <p>A sor önálló eladási ára a tranzakció pénznemében.</p><p>Az Összeg mező értékét vagy **be** kell adni, vagy ki kell számítani.</p> |
| Szerződéses önálló eladási ár | A szerződés önálló eladási ára. |
| Fennmaradó szerződéses bevétel | A szerződés fennmaradó bevételi összege. Ez az összeg az összes olyan sor összege, amelyekhez még nem készült számla. |
| Teljes szerződésbevétel | A sor szerződéses bevételének teljes összege. Ez az összeg az összes sor összege, függetlenül attól, hogy a számlák létre vannak-e hozva számukra. |
| Halasztott szerződéses bevételi számla | <p>MeA szerződési számla létrehozásakor a naplóbejegyzések esetében használt számla megadása.</p><p>Ez a mező csak ismétlődő szerződés számlázása esetén érhető el.</p> |
| Hiba | A bevétel felosztása során előfordult hibák. |

## <a name="use-revenue-allocation-on-a-sales-order"></a>Bevételfelosztás használata értékesítési rendelésen

A következő lépések szerint használhatja az értékesítési rendelések bevételfelosztási funkcióját.

1. Hozzon létre **egy olyan értékesítési rendelést a Minden értékesítési rendelés** lapon, amely cikkeket tartalmaz.
2. A Számla lap **Bevétel foglalása csoportjában** **válassza a Bevétel felosztása** lehetőséget **.**
3. A Több elem **elrendezéstípus mezőjében** válassza ki a MEA-típust.
4. Adja meg **a** MEA-számot a Többelem-elrendezés száma mezőben.
5. Ha az **Több elem elrendezéstípus** mezője Több **beállításra** van állítva, válassza ki a kívánt sorokat, **majd válassza az Alkalmaz a kijelöltre lehetőséget**.
6. Válassza a **Mentés** lehetőséget.

Ha bevételi és kiadási halasztásokat használ, akkor a halasztás ütemezése automatikusan létrejön. A halasztás ütemezése az Összes halasztás **ütemezve lapon megtekinthető**.
