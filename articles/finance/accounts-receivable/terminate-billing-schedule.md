---
title: Számlázási ütemezések megszüntetése
description: Ez a témakör bemutatja, hogyan lehet megszüntetni a számlázási ütemezéseket és a számlázási ütemezési sorokat az előfizetéses számlázásban.
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
ms.openlocfilehash: df81cc888e893c6a4a127e1a43426a0a0b56f0d1
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470829"
---
# <a name="terminate-billing-schedules"></a>Számlázási ütemezések megszüntetése

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet megszüntetni a számlázási ütemezéseket és a számlázási ütemezési sorokat az előfizetéses számlázásban. Ha megszakít egy számlázási ütemezést, akkor az állapotának Aktív állapotúnak kell **lennie**. Nem lehet "Visszatartott" **állapotú**. Hasonlóképpen, ha megszakít egy számlázási ütemezési sort, akkor annak aktív állapotúnak kell **lennie**. A számlázási ütemezés fejlécének sorát nem befolyásolja, ha megszakít egy számlázási ütemezési sort.

A számlázási ütemezések és a számlázási ütemezések felmondani a következő helyek valamelyikét:

- A **Mind/Aktív számlázási ütemezések** listaoldal
- Adott számlázási ütemezés a Minden számlázási **ütemezés lapon**
- Adott számlázási ütemezési sor az Összes számlázási **ütemezés lapon**

> [!NOTE]
> Ha egyszerre több számlázási ütemezést szeretne megszüntetni, használja **a Tömeges felmondás feldolgozása lapot**.

## <a name="terminate-a-billing-schedule-or-line"></a>Számlázási ütemezés vagy sor megszüntetése

A számlázási ütemezések és a számlázási ütemezések sorának megszüntetéséhez kövesse ezeket a lépéseket.

1. Válasszon ki egy számlázási ütemezést vagy egy számlázási ütemezési sort, majd válassza a Felmondás **lehetőséget**. 
2. Állítsa be **a Felmondás dátuma**, **a Felmondás típusa** és az **Okkód mezőket**.
3. A Jóváírás beállítás **mezőjének** beállítása Jóváírás **kiadásra**.
4. Válassza a Munkaviszony **megszüntetése lehetőséget**.

A számlázási ütemezés állapota a kiválasztott felmondási típustól függően változik. Ha a Fennmaradó számla **felmondási** típust választotta, a számlázási ütemezés összes sorának állapota **Utolsó** számlázás. A számlázási ütemezés állapota az utolsó számla feldolgozásáig **aktív** marad. Az utolsó számla feldolgozása után az **állapot Megszakítva állapotúra módosul**. Ha az Ütemezés **beállítása felmondási** típust választotta, **akkor a számlázási ütemezés állapota azonnal Befejezve állapotúra frissül**.

## <a name="terminate-a-billing-schedule-or-line-and-apply-a-refund"></a>Számlázási ütemezés vagy sor megszüntetése és visszatérítés alkalmazása

A számlázási ütemezés vagy számlázási ütemezés sorának megszüntetéséhez és a visszatérítés alkalmazásához hajtsa végre a következő lépéseket.

1. Válasszon ki egy számlázási ütemezést vagy egy számlázási ütemezési sort, majd válassza a Felmondás **lehetőséget**.
2. Állítsa be **a Felmondás dátuma**, **a Felmondás típusa**, az **Okkód** és a Hitel beállítási **mezőket**.
3. Válassza a **Felmondás visszatérítéssel lehetőséget**. **Megjelenik a tömeges felmondás** feldolgozási lapja, amely a számlázási ütemezésnek megfelelő szűréssel jelenik meg.
4. Az előnézeti **nézet** kiválasztásával megtekintheti a számlázási ütemezések sorait, majd a Folyamatot **.**

A jóváírás feldolgozása után nyissa **meg** a Számlázási adatok megtekintése lapot, és tekintse át a számlázási ütemezéshez alkalmazott jóváírást. Ha a követel összeg nagyobb nullánál, a rendszer törli a jövőbeli nem számlázandó sorokat, és azokat olyan számlázási részletsorokkal helyettesíti, amelyek a számlázási ütemezésre alkalmazott jóváírás negatív összegeit mutatják.

### <a name="view-example"></a>Példa megtekintése

A számlázási ütemezések a következő adatokat tartalmazza:

- A kezdési dátum 2020. január 1..
- A záró dátum 2020. december 31..
- A számlázási időszak összege 100,00 havonta.
- Számlák vannak létrehozva a számlázási időszakokhoz januártól júliusig.
- A szerződés megszűnésének dátuma 2020. június 15.

A jóváírás-korrekció feldolgozásakor minden jövőbeli számlázási időszak (augusztustól decemberig) törlődik a **Számlázási adatok megtekintése lapról**. A jóváírás-helyesbítési sor a júliusi számlázási időszak után adódik hozzá:

- Június 16–július 31., 150,00 összegű követel összeggel

Ha a nemszámlázatlan bevétel funkciót használja, **a Nemszámlázandó** bevétel naplóbejegyzés könyvvizsgálati lapja a felmondási bejegyzéssel frissül.

## <a name="terminate-a-billing-schedule-or-line-without-applying-a-credit"></a>Számlázási ütemezés vagy sor megszüntetése jóváírás alkalmazása nélkül

Ha jóváírás alkalmazása nélkül felmondani egy számlázási ütemezést vagy számlázási ütemezést, kövesse ezeket a lépéseket.

1. Válasszon ki egy számlázási ütemezést vagy egy számlázási ütemezési sort, majd válassza a Felmondás **lehetőséget**.
2. A Munkaviszony megszűnésének **dátuma mező** beállítása.
3. A Felmondás típusa **mező** beállítása Nincs **módosítás**. A Jóváírás **beállítás mezője** automatikusan Nincs jóváírás **beállításra van állítva**.
3. Az Okkód **mező** beállítása.
4. Írja be **a szükséges** megjegyzéseket a Felmondás mezőbe.
5. Válassza a Munkaviszony **megszüntetése lehetőséget**. 

A felmondás feldolgozásakor a rendszer a munkaviszony megszűnésének dátuma utáni összes számlázási részletsort eltávolítja. (Ezek közé tartozik a felmondási dátumot tartalmazó sor.) Az elmondott sorokhoz nem lehet számlákat létrehozni. Ha a felmondást eltávolítják, **minden** elmondott sor visszakerül a Számlázási adatok megtekintése lapra, és elérhetővé válik számlázásra.

## <a name="fields"></a>Mezők

A **Számlázási adatok megtekintése** lap a következő mezőket tartalmazza.

| Mező | Leírás |
|-------|-------------| 
| Munkaviszony megszűnésének dátuma | Válassza ki azt a dátumot, amikor fel szeretné bontani a számlázási ütemezést vagy a számlázási ütemezési sort. |
| Felmondás típusa | <p>Válassza ki a felmondás típusát:</p><ul><li>**Ütemezés módosítása** – a sor számlázási időszakának megszakítása a felmondás napján, **és a sor állapotának módosítása Utolsó számlázás beállításra**. Ha a sorcikknek van halasztás-ütemezése, akkor a már nem felismerhető összeg megfordítása után korrigálja a program. Ha a számlázás kezdő dátuma a munkaviszony megszűnésének dátuma utánra kerül, a fennmaradó számlázási időszakok törlődnek.</li><li>**Fennmaradó számla** – a számlázási időszak bármely fennmaradó összegének hozzáadása a felmondási időszakhoz, **és a sor állapotának módosítása Utolsó számlázás állapotúra**. Ha a sorcikknek van halasztás-ütemezése, frissül a halasztás záró dátuma. Ha a számlázás kezdő dátuma a munkaviszony megszűnésének dátuma utánra van adva, a rendszer hozzáadja a számlázási időszakhoz a hátralévő számlázási időszakok teljes összegét, és eltávolítja a hátralévő számlázási időszakokat.</li><li>**Nincs módosítás** – a megadott felmondási dátumon lezárja a sor számlázási időszakát. Nem történt korrekció. Ha ez a felmondási típus be van jelölve, **·** **akkor** a Jóváírás beállítási mező beállítása Nincs jóváírás, **és** a Napi áthozat mező Nem beállításra **van állítva.** Ezután mindkét mező írásra elérhetővé válik, és nem módosítható.</li></ul> |
| Jóváírási lehetőség | <p>Válassza ki, hogyan történik a jóváírás alkalmazása számlázási ütemezési sor megszüntetése esetén:</p><ul><li>**Jóváírás-korrekció** – jóváírás-korrekció létrehozása számlázási ütemezéshez sor megszüntetése esetén. A jóváírás-korrekció a számlázási ütemezés jövőbeli számlázási időszakában jelenik meg. A kiigazítás a következő számlázási időszak számlaösszegét is automatikusan módosítja, amíg a jóváírást be nem fejezte a számlázási ütemezésre.</li><li>**Jóváírás kiállítása** – jóváírás létrehozása számlázási ütemezés vagy számlázási ütemezési sor megszüntetése esetén.</li><li>**Nincs jóváírás** – ne hozzon létre jóváírást vagy jóváírást, ha egy számlázási ütemezés vagy számlázási ütemezési sor megszűnik. Ez a lehetőség csak akkor érhető el, ha a Számlázási ütemezés megszüntetése beállítás **nélkül** típusú felmondást használ.</li></ul><p>Az alapértelmezett beállítás az Ismétlődő szerződés **számlázási paraméterei lapon** található.</p> |
| Okkód | A felmondás okkódja. |
| Ok leírása | Az okkód leírása. |
| Felmondási megjegyzések | Írja be a felmondásra vonatkozó megjegyzéseit. |

<!--## Additional information-->
