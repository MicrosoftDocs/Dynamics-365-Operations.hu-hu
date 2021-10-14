---
title: Visszatérítés-kezelési ajánlatok
description: Ez a témakör bemutatja, hogyan lehet Visszatérítés-kezelési ajánlatot létrehozni. Az ajánlatok a visszatérítések és jogdíjak kiszámítására szolgáló különböző módszerek és alapok ellenőrzésére használhatók. Ezek magukban foglalják a belefoglalások és kizárások szabályait.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 18d03ad89942997d8b5e794bb8d79a67821ef2c4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580552"
---
# <a name="rebate-management-deals"></a>Visszatérítés-kezelési ajánlatok

[!include [banner](../includes/banner.md)]

A visszatérítés-kezelési ajánlatok a visszatérítések és jogdíjak kiszámítására szolgáló különböző módszerek és alapok ellenőrzésére használhatók. Ezek magukban foglalják a belefoglalások és kizárások szabályait. A visszatérítés-kezelési ajánlatoknak három típusa van: vevői visszatérítések, vevői jogdíjak és szállítói visszatérítések. Mindhárom típus hasonló beállításokat használ. Ez a témakör rámutat a különbségekre, ahol vannak ilyenek.

## <a name="create-a-deal"></a>Ajánlat létrehozása

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési ajánlatok \> Minden visszatérítés-kezelési ajánlat** részre. Az **Összes visszatérítés-kezelési ajánlat** listaoldalon mindhárom típusú ajánlatot létrehozhatja és kezelheti.

    Alteratív megoldásként hajtsa végre az alábbi lépések egyikét. A megjelenő listaoldal minden esetben ugyanazokat a beállításokat tartalmazza, mint az **Összes visszatérítés-kezelési ajánlat** listaoldal, de szűrve van, hogy csak egy típusú ajánlat jelenjen meg.

    - Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési ajánlatok \> Vevői visszatérítési ajánlatok** részre, csak vevői visszatérítési ajánlatok létrehozásához.
    - Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési ajánlatok \> Vevői jogdíjajánlatok** részre, csak vevői jogdíjajánlatok létrehozásához.
    - Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési ajánlatok \> Szállítói visszatérítési ajánlatok** részre, csak szállítói visszatérítési ajánlatok létrehozásához.

1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Új ajánlat létrehozása** párbeszédpanelen adja meg a következő mezőket:

    - **Visszatérítés-kezelési ajánlat** – Ha [beállított egy számsorozatot](rebate-management-parameters.md) a visszatérítési ajánlatokhoz, ez a mező automatikusan egyedi, rendszer által generált azonosítóra lesz állítva. Egyéb esetben meg kell adnia egy egyedi azonosítót.
    - **Leírás** – Adja meg az ajánlat leírását.
    - **Modul** – Válassza ki, hogy az ajánlat milyen típusú partnerre vonatkozik (*Vevő* vagy *Szállító*). Attól függően, hogy milyen oldalról indult el, előfordulhat, hogy ez a mező automatikusan be van állítva a kiválasztott ajánlattípus alapján. Ebben az esetben a mező írásvédett.
    - **Típus** – Válassza ki az ajánlat típusát (*Visszatérítés* vagy *Jogdíj*). Attól függően, hogy milyen oldalról indult el, előfordulhat, hogy ez a mező automatikusan be van állítva a kiválasztott ajánlattípus alapján. Ebben az esetben a mező írásvédett.
    - **Egyeztetés a következő szerint:** – Válassza ki, hogyan kell kiszámítani és egyeztetni az ajánlatot:

        - *Ajánlat* – Egyetlen visszatérítést kell feldolgozni az ajánlat összes visszatérítése és levonása esetében.
        - *Sor* – A visszatérítéseket az ajánlat minden sorában fel kell dolgozni.

    - **Feladási profil** – Válassza ki azt a [feladási profilt](rebate-management-posting.md), amelyet azokhoz a tranzakciókhoz használ, ahol az ajánlat érvényes. Ez a mező csak akkor használható, ha a **Egyeztetés a következő szerint:** mező *Ajánlat* értékre van beállítva. Ha *Sor* értékre van beállítva, a profilt később rendeli hozzá az ajánlathoz hozzáadott minden sorhoz.
    - **Feladási profil garanciához** – Válassza ki azt a [feladási profilt](rebate-management-posting.md), amelyet a garanciális tranzakciókhoz használ. A garanciatranzakciókhoz csak akkor van szükség feladási profilokra, ha a garancia jogdíjra vonatkozik. Ellenkező esetben, bár a feladási profil nem kötelező, ha nincs megadva feladási profil, hiba jelenik meg a garanciák feladásakor. Ez a mező csak akkor használható, ha a **Típus** mező *Jogdíj* értékre van beállítva. 
    - **Visszatérítési kimenet** – Válassza ki, hogyan kell megfizetni a visszatérítést vagy a jogdíjat:

        - *Pénzügyi* – Hozzon létre egy szabadszöveges számlabizonylatot vagy kötelezettségekre vonatkozó terhelési bizonylatot, a pénzek későbbi kifizetéséhez vagy bevételezéséhez. Ne feledje, hogy a fedezetek **felhasználhatók** a visszatérítésekkel, ahol ez a lehetőség ki van jelölve. Ez a beállítás az egyetlen elérhető lehetőség, ha a **Típus** mező *Jogdíj* értékre van beállítva.
        - *Cikk* – Értékesítési rendelés létrehozása cikkekhez az ajánlat beállítása szerint. Ezen az értékesítési rendelésen minden cikkhez 0 (nulla) ár van hozzárendelve. Ne feledje, hogy a fedezetek **nem használhatók fel** a visszatérítésekkel, ahol ez a lehetőség ki van jelölve.

    - **Visszatérítés pénzneme** – Válassza ki azt a pénznemet, amely a visszatérítés, levonás vagy jogdíj kifizetésekor használatos.
    - **Bizonylatjegyzetek** – Szükség szerint írja be az ügylettel kapcsolatos megjegyzéseket.
    - **Kumulatív garancia** – Ezt a beállítást csak akkor állíthatja *Igen* értékre, ha a **Típus** mező *Jogdíj* értékre van állítva. Ez a beállítás befolyásolja a garantált levonási kifizetések kiszámítását. Egy példa:

        - Az ajánlat garanciája az, hogy olyan értéket ad el, amely negyedévente 10 000 USD kifizetéshez vezet.
        - Az árukat értékesítő szervezet olyan értéket értékesít, amely 12 000 USD csökkentési kifizetést eredményez az 1. negyedévben. Az eredmény egy 12 000 USD összegű jogdíj, amelyet kifizetnek, levonva a 10 000 USD összegű garanciát.
        - Ha a **Kumulatív garancia** opció *Igen* értékre van állítva, az 1. negyedévre fizetett további 2000 USD jogdíj a 2. negyedévre vonatkozik. Ezért a vevő számára 8000 USD garantált (a 10 000 USD garancia mínusz a 2000 USD további fizetés).
        - A 2. negyedévben olyan értékesítéseket regisztrál, amelyek 5000 USD összegű jogdíjat eredményeznek.
        - A rendszer azonosítja a 3000 USD kifizetést (a 8000 USD garancia mínusz az 5000 USD jogdíjkifizetés).
        - Ha a **Kumulatív garancia** beállítás *Nem* értékű, a teljes 10 000 USD garantált minden negyedévben. Ez a garancia 5000 USD javasolt fizetésnek felel meg a 2. negyedévben (a 10 000 USD garancia, mínusz az 5000 USD jogdíjkifizetés).

1. Válassza az **OK** gombot az ajánlat létrehozásához és a párbeszédpanel bezárásához.

Ez az eljárás létrehozza az új ajánlat fejlécszintjét. Ezután sorokat ad hozzá az ajánlathoz.

## <a name="add-lines-to-a-deal"></a>Sorok hozzáadása az ajánlathoz

Miután létrehozott egy ajánlatot az előző szakaszban leírtak szerint, megnyithatja azt a listaoldalról. Ezután sorokat adhat hozzá az ajánlat vevőinek vagy szállítóinak, cikkének, időkereteinek, alapjának és számítási módszereinek azonosításához. Egy ajánlatnak egy vagy több sora lehet. Ha egy ajánlatnak több sora van, általában azonos típusúak, vagy ugyanazok a paraméterek vannak társítva hozzájuk. Amíg nem ad hozzá sorokat az ajánlathoz, az ajánlat valójában nem fog semmit sem tenni.

1. Nyissa meg a megfelelő visszatérítési ajánlatok listaoldalát az előző szakaszban leírtak szerint.
1. Keresse meg és nyissa meg azt az ajánlatot, amellyel dolgozni akar.
1. A **Visszatérítéskezelés** gyorslapon válasszon az alábbi gombok közül, ha ajánlatsort szeretne hozzáadni a rácshoz:

    - **Sor hozzáadása** – Új, üres ajánlatsor hozzáadása.
    - **Sor másolása** – Ha egy meglévő ajánlatsor hasonlít a hozzáadni kívánt ajánlatsorra, akkor ezt a gombot választva másolhatja annak egy példányát. Az új ajánlatsor tartalmazza a kapcsolódó Visszatérítéskezelési részletek összes beállítását. Ezután szerkesztheti a beállításokat. Például általában frissíti a cikk-kapcsolatot és a visszatérítési százalékot.

1. A következő mezőket állítsa be az új ajánlatsorhoz:

    - **Visszatérítés-kezelési szám** – Ha [beállított egy számsorozatot](rebate-management-parameters.md) a Visszatérítés-kezelési számokhoz, ez a mező automatikusan egyedi, rendszer által generált azonosítóra lesz állítva. Egyéb esetben meg kell adnia egy egyedi azonosítót.
    - **Típus** – Az ajánlat típusa, amelyre a sor vonatkozik (*Visszatérítés* vagy *Jogdíj*). Az érték a fejlécből lesz átmásolva, és nem módosítható.
    - **Leírás** – Adja meg az ajánlatsor leírását.
    - **Vállalat** – Válassza ki azt a vállalatot (jogi személyt), amelyre az ajánlatsor vonatkozik. A feldolgozás során a felhasználók csak az éppen használt vállalathoz rendelt ajánlatsorokat dolgozhatják fel. A **Vevői visszatérítési ajánlatok** listaoldala többvállalatos nézetet biztosít a felhasználó biztonsági hozzáférése alapján. A visszatérítéseket azonban csak az éppen használt vállalathoz szerkesztheti és dolgozhatja fel.
    - **Számlakód** – Válassza ki azoknak a vevőknek vagy szállítóknak a hatókörét, akikre az ajánlatsor vonatkozik:

        - *Tábla* – Az ajánlatsor egy adott vevőre vagy szállítóra vonatkozik.
        - *Csoport* – Az ajánlatsor vevők vagy szállítók egy csoportjára vonatkozik. További információért a csoportok beállításáról lásd: [Visszatérítés-kezelési csoportok](rebate-management-groups.md).
        - *Mind* – Az ajánlatsor minden vevőre vagy szállítóra vonatkozik.

    - **Számlakapcsolat** – Ha kiválasztotta a *Tábla* lehetőséget a **Számlakód** mezőben, válassza ki a vevőt vagy a szállítót, akire az ajánlat vonatkozik. Ha a *Csoport* lehetőséget választotta, válassza ki a vevői vagy szállítói csoportot. Ha a *Mind* lehetőséget választotta, ez a mező nem érhető el.
    - **Cikk-kód** – Válassza ki azoknak a cikkeknek a hatókörét, amelyekre az ajánlatsor vonatkozik:

        - *Tábla* – Az ajánlatsor egy adott cikkre vonatkozik.
        - *Csoport* – Az ajánlatsor cikkek egy csoportjára vonatkozik. További információért a csoportok beállításáról lásd: [Visszatérítés-kezelési csoportok](rebate-management-groups.md).
        - *Összes*– Az ajánlatsor az összes cikkre vonatkozik.

    - **Cikk-kapcsolat** – Ha kiválasztotta a *Tábla* lehetőséget a **Cikk-kód** mezőben, válassza ki a cikket, amelyre az ajánlatsor vonatkozik. Ha a *Csoport* lehetőséget választotta, válassza ki a cikkcsoportot. Ha a *Mind* lehetőséget választotta, ez a mező nem érhető el.
    - **Egységtípus** – Az üzletorra vonatkozó egységtípus kiválasztása (*Készletegység* vagy *Tényleges súly egysége*). A régebbi rekordoknál előfordulhat, hogy a mező üres. Ebben az esetben a *Készletegység* érték lesz feltételezve.
    - **(Készletkezelési paraméterek)** – Az ajánlatsor fennmaradó mezőiben adja meg az ajánlatban szereplő cikkek meghatározásához használt készletkezelési paraméterek értékeit (például a cikk mérete, színe, stílusa, telephelye és raktára). A dimenziók hozzáadásához vagy eltávolításához válassza a **Dimenziók megjelenítése** lehetőséget a műveletpanelen.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Ha tovább szeretné korlátozni azokat a cikkeket, amelyekre az ajánlatsor vonatkozik, jelölje ki a sort, majd a **Visszatérítés-kezelés** gyorslapon válassza a **Szűrő** lehetőséget egy szabványos **Lekérdezés** párbeszédpanel megnyitásához.
1. Minden egyes hozzáadott ajánlatsorhoz állítsa be a számítás részleteit és egyéb részleteket a **Visszatérítés-kezelési részletek** gyorslapon, a következő szakaszban leírtak szerint.

## <a name="add-rebate-management-details-to-a-deal-line"></a>Visszatérítés-kezelés részleteinek hozzáadása ajánlatsorhoz

Az ajánlat minden sorában be kell állítania a részleteket a **Visszatérítés-kezelési részletek** gyorslapon. Először válassza ki az ajánlatsort a **Visszatérítés-kezelés** gyorslapon. Ezután állítsa be az ajánlatsor értékeit a **Visszatérítés-kezelési részletek** gyorslap különböző lapjainak használatával. A következő alfejezetek ismertetik az egyes lapok használatát.

### <a name="settings-on-the-general-tab"></a>Az Általános lap beállításai

A **Visszatérítés-kezelési részletek** gyorslap **Általános** lapján beállíthatja a kiválasztott ajánlatsor számítási módszerét és alapját. Ez a beállítás határozza meg, hogy szükség van-e minimális vásárlásra, az ajánlatsorhoz társított könyvelési profilokra és a számítás részleteire. Az alábbi táblázat bemutatja a rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Számítási mód | Válassza ki azt a módszert, amely akkor használható, ha a kijelölt ajánlatsort más ajánlatsorokkal (*Lépcsőzetes*, *Összegző*, *Görgetett* vagy *Összeg*) kombinálja. Ennek a mezőnek az értéke drámaian befolyásolhatja a visszatérítési számítások eredményét. Az egyes módszerek és példák teljes leírását, amelyek megmutatják, hogy ez hogyan befolyásolja a visszatérítés kiszámítását, a témakör későbbi szakaszában az [Ajánlatsorok számítási módszerei](#calc-methods) című részben olvashat. |
| Alap | Adja meg, hogy a visszatérítést mennyiség (azaz a vásárolt vagy eladott egységek teljes száma) vagy érték (azaz a vásárolt vagy eladott áruk teljes ára) alapján alkalmazza-e. |
| Tranzakció típusa | <p>Válassza ki azt a pontot a folyamatban, ahol a számításnak be kell következnie:</p><ul><li>*Rendelés* – A számítás alapjaként a megrendelt mennyiséget vagy értéket használja.</li><li>*Kiszállított* – A számítás alapjaként a kiszállított mennyiséget vagy értéket használja.</li><li>*Számla* – A számítás alapjaként a számlázott mennyiséget vagy értéket használja.</li></ul> |
| Egység | Ha az **Alap** mezőben a *Mennyiség* lehetőséget választotta, válassza ki azt az egységet, amelyben a mennyiséget meg kell adni. |
| Minimális összeg | Adja meg az időszakonként fizetendő minimális összeget. Negatív értéket adhat meg a negatív visszatérítési összegek engedélyezéséhez, ha a jóváírások meghaladják az időszak értékesítését. |
| Visszatérítés-csökkentési elv | Válassza ki az ajánlatsorra vonatkozó [visszatérítés-csökkentési elvet](rebate-reduction-principle.md). |
| Változat száma | Ha az ajánlatsor olyan cikkre vonatkozik, amely változatokkal rendelkezik, válassza ki azt a változatot, amelyre az ajánlatsor vonatkozik. |
| Szállítói visszatérítés alapja | <p>Ez a mező csak szállítói visszatérítéseknél jelenik meg (ez azt jelenti, hogy azok az ajánlatok, ahol a **Modul** mező *Szállító* értékre van állítva). Válassza ki a szállítói visszatérítés alapját:</p><ul><li>*Beszerzési rendelés* – A szállító által kapott visszatérítés a beszerzési rendelés mennyiségétől vagy értékétől függ.</li><li>*Értékesítési rendelés* – A szállító csak az áru eladása után kap visszatérítést. A visszatérítés az értékesítési rendelés mennyiségétől vagy értékétől függ.</li></ul> |
| Ár alapja | <p>Ez a mező csak szállítói visszatérítéseknél jelenik meg (azok az ajánlatok, ahol a **Modul** mező *Szállító* értékre van állítva). Ha az *Értékesítési rendelés* lehetőséget választotta a **Szállítói visszatérítés alapja** mezőben, válassza ki a megfelelő áralapot:</p><ul><li><p>*FIFO* – A visszatérítés kiszámításához futtatni kell a **FIFO beszerzési ár számítása** ismétlődő feladatot. (A feladat futtatásához lépjen a **Visszatérítés-kezelés \> Időszakos feladatok \> FIFO beszerzési ár számítása** lehetőségre.) Az eladott készlet értékének kiszámításához az először be, először ki (FIFO) szabályt kerül használatra. Ezt az értéket fogja használni a szállítói visszatérítések kiszámításához. Egy példa:</p><ul><li>**Eladott készlet:** 1000 egység egyenként 3,00 USD áron = 3000 USD</li><li>**Aktuális vételár a FIFO alapján:** 2,00 USD</li><li>**Munkaszámítás:** *Eladott egységek* × *Aktuális vételár* = 1000 × 2,00 USD = 2000 USD</li></ul></li><li><p>*Utolsó beszerzési ár* – Az utolsó beszerzési tranzakció értékét használja a rendszer a szállítói visszatérítések kiszámításához. Egy példa:</p><ul><li>**Eladott készlet:** 1000 egység egyenként 3,00 USD áron = 3000 USD</li><li>**Utolsó beszerzési ár:** 2,00 USD</li><li>**Munkaszámítás:** *Eladott egységek* × *Utolsó beszerzési ár* = 1000 × 2,00 USD = 2000 USD</li></ul></li><li><p>*Átlagos beszerzési ár* – Az utolsó *X* hónap súlyozott átlaga lesz használva a szállítói visszatérítések kiszámításához. Ha ezt a lehetőséget választja, akkor a hónapok számát kell megadnia a **Hónapok száma** mezőben (ez csak akkor érhető el, ha az **Ár alapja** mezőben az *Átlagos beszerzési ár* érték van beállítva). Egy példa:</p><ul><li>**Eladott készlet:** 1000 egység egyenként 3,00 USD áron = 3000 USD</li><li>**Átlagos beszerzési ár:** 2,00 USD</li><li>**Munkaszámítás:** *Eladott egységek* × *Átlagos beszerzési ár* = 1000 × 2,00 USD = 2000 USD</li></ul></li><li><p>*Eladási ár* – Az eladási ár alapján számítja ki a rendszer a szállítói visszatérítéseket. Egy példa:</p><ul><li>**Eladott készlet:** 1000 egység egyenként 3,00 USD áron = 3000 USD</li><li>**Átlagos beszerzési ár:** 2,00 USD</li><li>**Munkaszámítás:** *Eladott egységek* × *Eladási ár* = 1000 × 3,00 USD = 3000 USD</li></ul></li></ul> |
| Hónapok száma | Ez a mező csak szállítói visszatérítéseknél jelenik meg (azok az ajánlatok, ahol a **Modul** mező *Szállító* értékre van állítva). Ha az **Ár alapja** mezőben az *Átlagos beszerzési ár* lehetőséget választotta, adja meg, hogy hány hónapot kell használni. |
| Feladási profil | Válassza ki a kiválasztott ajánlatsorra vonatkozó [feladási profilt](rebate-management-posting.md). Ez a profil csak akkor használatos, ha az ajánlatfejléc **Egyeztetés a következő szerint:** mezőjének beállítása *Sor*. Ha az **Egyeztetés a következő szerint:** mezőben az *Ajánlat* érték van megadva, akkor a program mindig az ajánlatfejlécben beállított feladási profilt használja. Ha az ajánlatsoron nincs megadva feladási profil, az ajánlatfejlécben megadott feladási profil kerül használatra. |
| Garancia feladási profilja | Ez a mező a **Feladási profil** mezőhöz hasonlóan működik, de csak a jogdíjakra vonatkozik. |
| Kifizetés típusa | Az ajánlathoz kiválasztott feladási profil fizetési típusa. |
| Összeg áfával | Válassza ki, hogy a tranzakció tartalmazza-e az áfát. Az áfa tartalmazásának csak akkor van jelentősége, ha az **Alap** mező értéke *Érték*. A számla összege lesz az áfát tartalmazó összeg. Ha a visszatérítés számítása százalékos értéken alapul, a rendszer megszorozza a visszatérítés százalékos arányát az adóval növelt összeggel. Ne feledje, hogy a számítás az ajánlatsorból származó áfaértéket használja. |
| Jóváírásokkal együtt | <p>Válassza az *Igen* lehetőséget, ha a jóváírásokat is beleveszi a visszatérítés kiszámításába.</p><p>Ha *Igen* értékre állítja ezt a beállítást, a hatás a **Tranzakciótípus** mező értékétől függően eltérő lehet:</p><ul><li>Ha a **Tranzakciótípus** mező beállítása *Számla*, a számítás figyelembe veszi a jóváírásokat. Ez a konfiguráció a szokásos konfiguráció.</li><li>Ha a **Tranzakciótípus** mező értéke *Rendelés*, a számítás a negatív értékeket és a nyitott visszárurendeléseket is figyelembe fogja venni.</li></ul> |
| Engedményes összeg | Akkor válassza az *Igen* beállítást, ha a számítást a cikk vagy cikkek kedvezményes összegének alapján számítja, abban az esetben, ha sorengedmények vannak megadva. |
| Csak a kifizetett számlák | Állítsa *Igen* beállításra, ha a számításban csak a teljesen kifizetett számlákat kell figyelembe venni. (Más szóval a részlegesen kifizetett számlákra nem lehet visszatérítéseket számítani.) Ez a lehetőség csak akkor érhető el, ha a **Tranzakciótípus** mező beállítása *Számla*. |
| Szabad szöveg tartalmazása | Válassza az *Igen* lehetőséget, ha a szabadszöveges számlákat is beleveszi a visszatérítés kiszámításába. A szabadszöveges számlák csak olyan ajánlatsorok esetén foglalhatók bele, amelyekben a **Cikk-kód** mező beállítása *Mind*. |
| Kiegyenlítési kedvezmény tartalmazása | A visszatérítés első kiegyenlítési kedvezménnyel való csökkentéséhez állítsa *Igen* beállításra. A feltételezés az, hogy a szervezet az első kiegyenlítési kedvezményt veszi figyelembe. Válassza a *Nem* lehetőséget, ha engedélyezni szeretné a kiegyenlítési kedvezmény későbbi felhasználását. |
| Dokumentum megjegyzései | A visszatérítési tranzakció naplósoraiban tranzakciószövegeként használt megjegyzések beírása. |

### <a name="settings-on-the-dates-tab"></a>Beállítások a Dátumok lapon

A **Visszatérítés-kezelés** gyorslap **Dátumok** lapján megadott beállítások határozzák meg az **Általános** lapon megadott számítások gyakoriságát és időzítését. Ezek határozzák meg, hogyan történik a számítás a feldolgozás során.

Ezen a lapon megadhatja azokat a dátumtartományokat, amelyekre a kiválasztott ajánlatsor érvényes, valamint a számítási gyakoriságot. Megadhatja azt is, hogy feladja-e a rendszer a garanciát, és hogy mikor.

Az eszköztár gombjaival hozzáadhat dátumsorokat a rácshoz, illetve eltávolíthatja azokat. Ha több dátumsor létezik, az érvényes dátumtartományok nem fedhetik át egymást. Ellenkező esetben az ajánlat mentésekor hibaüzenet jelenik meg.

Az alábbi táblázat bemutatja az egyes sorokhoz rendelkezésre álló dátummezőket.

| Mező | Leírás |
|---|---|
| Kezdő dátum | Adja meg az első dátumot, amelyre a dátumsor vonatkozik. Ha az ajánlat fejlécében meg van adva a „kezdő” és „záró” dátum, akkor a program minden új dátumsor alapértelmezett értékeként használja őket. |
| Záró dátum | Adja meg az utolsó dátumot, amelyre a dátumsor vonatkozik. Ha az ajánlat fejlécében meg van adva a „kezdő” és „záró” dátum, akkor a program minden új dátumsor alapértelmezett értékeként használja őket. |
| / | Adja meg, hogy milyen gyakran kell számítani az ajánlatsort. Itt egy egész számot írjon be, majd válasszon egy egységet az **Összesítés alapja** mezőben. Például minden a második héten való számításához állítsa be a **Gyakoriság** mezőt *2* értékre, az **Összesítés alapja** mezőt pedig *Hét* értékre. |
| Összesítés alapja | Válassza ki a **Gyakoriság** beállításra vonatkozó egységet. Válassza ki az *Élettartam* lehetőséget, ha az ajánlatsor teljes élettartama alatt ki kell számítani. Válassza ki a *Testreszabott időszak* lehetőséget a főkönyvben meghatározott időszak kiválasztásához. Ebben az esetben az **Időszaktípus** mezőt is be kell állítania. |
| Időszak típusa | Ez a mező csak akkor használható, ha az **Összesítés alapja** mező *Testreszabott időszak* értékre van beállítva. A kiválasztásra elérhető értékek a főkönyvben meghatározott időszaktípusokból állnak. |
| A hét első napja | A hetek adott időszakra vonatkozó azonosításának meghatározása. Ez a mező csak akkor használható, ha az **Összesítés alapja** mező *Hét* értékre van beállítva. |
| Igénylés gyakorisága | Annak megadása, hogy milyen gyakran igényelhető visszatérítési pénzösszeg az ajánlatsor esetében. Itt egy egész számot írjon be, majd válasszon egy egységet az **Igénylés alapja** mezőben. |
| Igénylés alapja | Válassza ki az **Igénylés gyakorisága** beállításra vonatkozó egységet. Válassza az *Élettartam* lehetőséget, ha az igényeket csak egyszer engedélyezi az ajánlatsor teljes élettartama alatt. Válassza ki a *Testreszabott időszak* lehetőséget a főkönyvben meghatározott időszak kiválasztásához. Ebben az esetben az **Igénylés időszaktípusa** mezőt is be kell állítania. |
| Igénylés időszaktípusa | Ez a mező csak akkor használható, ha az **Igénylés alapja** mező *Testreszabott időszak* értékre van beállítva. A kiválasztásra elérhető értékek a főkönyvben meghatározott időszaktípusokból állnak. |
| Feldolgozás feladáskor | Jelölje be ezt a jelölőnégyzetet, ha a feladáskor fel kell dolgozni az igényléssort. Ez a beállítás csak olyan ajánlatsorok esetén érhető el, ahol az **Általános** lap **Tranzakciótípus** mezőjének beállítása *Kiszállítva* vagy *Számla*. Fedezet esetében a fedezet a szállítólevél vagy a számla generálásakor adja fel a fedezetet. |
| Garancia gyakorisága | Ez a mező csak jogdíjajánlatokra vonatkozik. Adja meg, hogy milyen gyakran kell kiszámolni a jogdíj garanciáját az **Összesítés alapja** által megadott időszakban. Itt egy egész számot írjon be, majd válasszon egy fizetési időt a **Garancia fizetése** mezőben. |
| Garancia fizetése | <p>Ez a mező csak jogdíjajánlatokra vonatkozik. A garanciaszámítás gyakoriságának meghatározására a **Garancia gyakorisága** mezővel együtt működik. Válasszon a következő értékek közül:</p><ul><li><p>*Időszak kezdete* – A garancia a dátumsorhoz meghatározott megállapodás szerinti időszak elején lesz kifizetve. A teljes garancia először feldolgozásra kerül. Csak a garantált összeget meghaladó jogdíjak értékét lehet jogdíjként feladni. Egy példa:</p><ul><li>**Garancia minimuma:** 10 000 USD két hónap alatt.</li><li>**1. hónap:** 10 000 USD garanciaként fel lett adva, és 0 USD lett feladva jogdíjként.</li><li>**2. hónap:** 2000 USD lett feladva jogdíjként, és 0 USD lett feladva garanciaként.</li><li>**Munkaszámítás:** *Fennmaradó garancia* – *Feladott jogdíjak* = 0 USD – 2000 USD = -2000 USD.</li></ul><p>Mivel 2000 USD jogdíjfizetés szükséges, ezért a rendszer létrehoz egy naplót 2000 USD-ről.</p><p>**Megjegyzés:** A garanciát az első időszakra vonatkozó levonási fedezettel együtt kell kiszámítani és feladni.</p></li><li><p>*Időszak vége* – A garancia csak a levonási megállapodás végén kerül kifizetésre, a dátumsoron meghatározottak szerint. Egy példa:</p><ul><li>**Garancia minimuma:** 10 000 USD két hónap alatt.</li><li>**1. hónap:** 5000 USD kerül feladásra jogdíjként, és egy napló jön létre.</li><li>**2. hónap:** 7000 USD kerül feladásra jogdíjként, és egy napló jön létre.</li><li>**Munkaszámítás:** Mivel a jogdíjak meghaladják a garancia összegét, 0 USD kerül feladásra a garanciára.</li></ul><p>**Megjegyzés:** A garanciát csak az utolsó időszakra vonatkozó levonásokkal és visszatérítési tranzakciókkal együtt lehet kiszámítani és feladni.</p></li></ul> |
| Garancia minimum | Ez a mező csak jogdíjajánlatokra vonatkozik. Adja meg a jogdíjra vonatkozó garancia minimális összegét az ajánlat fejlécén megadott pénznemben. |

### <a name="settings-on-the-lines-tab"></a>Beállítások a Sorok lapon

A **Visszatérítés-kezelési részletek** gyorslap **Sorok** lapján megadhatja a kiválasztott ajánlatsor számítási sorait. Minden számítási sor létrehoz egy mennyiségi vagy értékküszöböt, valamint egy kapcsolódó kompenzációs összeget vagy cikkeket. Az **Általános** lap **Alap** mezője határozza meg, hogy az egyes számítási sorok mennyiségen vagy értéken alapulnak-e.

Az eszköztár gombjaival hozzáadhat számítási sorokat a rácshoz, illetve eltávolíthatja azokat. Tetszőleges számú számítási sor lehet. Ha azonban több számítási sor létezik, a „kezdő” és „záró” mennyiség- vagy értéktartományok nem fedhetik egymást.

Az alábbi táblázat bemutatja az egyes sorokhoz rendelkezésre álló számítási mezőket.

| Mező | Leírás |
|---|---|
| Kezdő mennyiség/érték | Adja meg azt a minimális mennyiséget vagy értéket, amelyre a számítási sor vonatkozik. |
| Záró mennyiség/érték | Adja meg azt a maximális mennyiséget vagy értéket, amelyre a számítási sor vonatkozik. |
| Visszatérítés-kezelési módszerek | <p>Ez a mező csak olyan ajánlatokhoz érhető el, ahol a fejléc **Visszatérítési kimenet** mezője *Pénzügyi* értékre van beállítva. Válassza ki a visszatérítés kiszámítására használt módszert:</p><ul><li>*Rögzített* – A sorhoz rögzített árösszeget használnak.</li><li>*Százalék* – Az értékesítés összegének egy százaléka kerül felhasználásra.</li><li>*Arány* – A rendelésenkénti rögzített árösszeg kerül felhasználásra.</li></ul><p>**Fontos:** Javasoljuk, hogy a **Sorok** lap minden számítási sorában ugyanazt a módszert használja. Ha új módszerre van szükség, hozzon létre egy új ajánlatsort. Ne feledje, hogy a **Visszatérítés-kezelés** gyorslap **Sor másolása** gombja segítségével új ajánlatsort hozhat létre egy meglévő ajánlatsorból.</p><p>**Megjegyzés:** Ha a **Visszatérítési kimenet** mező *Cikk* értékre van állítva, akkor ez a mező mindig *Rögzített*. A cikkek megadásáról a táblázatot követő szövegben talál további információt. |
| Visszatérítés-kezelési mennyiség | Ez a mező csak olyan ajánlatokhoz érhető el, ahol a fejléc **Visszatérítési kimenet** mezője *Pénzügyi* értékre van beállítva. Adja meg a visszatérítés kiszámításához használható összeget a **Visszatérítés-kezelési módszer** mezőben kiválasztott módszer alapján. |

Amint az az előző táblázatban is szerepel, az olyan ajánlatoknál, ahol a fejléc **Visszatérítési kimenet** mezője *Cikk* értékre van állítva, meg kell adnia a **Sorok** lap minden számítási sorához a cikkeket. A cikkek megadásához kövesse az alábbi lépéseket.

1. A **Sorok** lapon hozza létre a szükséges számítási sort, ha nem létezik, és jelölje ki.
1. Ha az ügylet nem lett mentve a számítási sor létrehozása óta, válassza a **Mentés** lehetőséget a Művelet panelen.
1. A **Sorok** lapon válassza a **Cikkek** lehetőséget.
1. A **Cikkek** oldalon, a Műveletablak gombjaival cikkeket adhat hozzá a rácshoz, vagy szükség szerint eltávolíthat cikkeket. Az egyes sorokhoz állítsa be a következő mezőket:

    - **Cikkszám** – Válassza ki a megadott cikket.
    - **(Egyéb dimenziók)** – Ha több dimenziót kell használnia a cikk meghatározásához (például cikk-konfiguráció, méret, szín, stílus, hely vagy raktár), adja meg őket. A lehetséges dimenziók hozzáadásához vagy eltávolításához válassza a **Dimenziók megjelenítése** lehetőséget a Művelet panelen.
    - **Mennyiség** – Adja meg azt a mennyiséget, amely a kiválasztott számítási sor küszöbértékének elérése után lesz megadva.
    - **Egység** – Válassza ki azt az egységet, amelyben a **Mennyiség** érték meg van adva.
    - **Több** – Ez a mező a **Mennyiség** mezővel együtt működik. Egy cikksoron például a **Mennyiség** mezőt *2* értékre, a **Több** mezőt pedig *100* értékre állíthatja. Ha ezután a teljes értékesítési rendelés mennyisége 150, a két cikk ingyenes lesz (kettő 100 egységenként).

### <a name="settings-on-the-inventory-dimensions-tab"></a>Beállítások a Készletdimenziók lapon

A **Visszatérítés-kezelés részletei** gyorslap **Készletdimenziók** lapján látható a kiválasztott ajánlatsorhoz megadott termék összes rendelkezésre álló dimenzióértéke. Olyan dimenziókat tartalmaz, amelyek nem jelennek meg a **Visszatérítés-kezelés** gyorslapon. Csak a kijelölt termékre vonatkozó dimenziók értékeit szerkesztheti.

A **Visszatérítés-kezelő** gyorslapon további dimenziókat adhat hozzá a rácshoz, ha a Művelet panelen a **Dimenziók megjelenítése** lehetőséget választja.

## <a name="calculation-methods-for-deal-lines"></a><a name="calc-methods"></a>Az ajánlatsorok számítási módszerei

Minden alkalommal, amikor az előző szakaszban leírtak szerint be szeretné állítani az ajánlatsorok egyikének részleteit, ki kell választania ennek a sornak a számítási módszerét. Ez a szakasz ismerteti az egyes számítási módszereket, és példákat mutat be arra, hogy az egyes módszerek hogyan számítják ki a rendelések és ajánlatsorok teljes visszatérítését. Ezekben a példákban a rendelések és az ajánlatsorok azonosak. Csak a számítási módszerek különböznek.

### <a name="stepped-calculation-method"></a>Lépcsőzetes számítási módszer

A lépcsőzetes számítási módszer lépésről lépésre végzi a számítást, ahol minden ajánlatsor fokozatosan hozzájárul a visszatérítéshez, amíg el nem éri az értékesítési mennyiséget vagy értéket. A lépések alapulhatnak az eladott áruk mennyiségén vagy értékén, a **Visszatérítés-kezelési részletek** gyorslap **Általános** lapján található **Alap** mező beállításaitól függően.

Például egy ajánlatsor úgy van beállítva, hogy a **Számítási módszer** mező *Lépcsőzetes* értékű, az **Alap** mező értéke pedig *Érték*. Olyan számítási sorokat tartalmaz, amelyek a következő visszatérítéseket biztosítják:

- **A sor:** 10 százalék, legfeljebb 1000 USD
- **B sor:** 25 százalék, legfeljebb 2500 USD

Ha a megvásárolt vagy eladott áruk értéke 2000 USD, az ebből eredő 350 USD visszatérítést a következőképpen számítják ki:

- **Visszatérítés (A):** *Küszöbérték (A)* × *Százalék (A)* = 1000 USD × 10 százalék = 100 USD
- **Visszatérítés (B):** (*Eladott érték* – *Küszöbérték (A)*) × *Százalék (B)* = (2000 USD – 1000 USD) × 25 százalék = 250 USD
- **Teljes visszatérítés:** *Visszatérítés (A)* + *Visszatérítés (B)* = 100 USD + 250 USD = 350 USD

Ha az **Alap** mező értéke *Érték* helyett *Mennyiség*, a lépcsőzetes számítási módszer hasonló módon működik. Az első lépés kerül felhasználásra az azonosított mennyiséghez a második lépés eléréséig. Ezután a második lépés kerül felhasználásra az első lépés feletti minden mennyiséghez a harmadik lépés eléréséig. Ez a folyamat ezután az összes további lépésen keresztül folytatódik.

### <a name="cumulative-calculation-method"></a>Halmozott számítási mód

A halmozott számítási módszer csak egy számítási sort használ a visszatérítés kiszámításához. Ha több számítási sor áll rendelkezésre az ajánlatsorhoz, a teljes mennyiséghez vagy értékhez az elért legnagyobb értékű vagy legnagyobb mennyiségű számítási sort használja a rendszer. A többi számítási módszerhez hasonló halmozott módszer a **Visszatérítés-kezelés részletei** gyorslap **Általános** lapján található **Alap** mező beállítását használja annak meghatározására, hogy az értékesítési mennyiség vagy az eladási érték használható-e a visszatérítések kiszámításához.

Például egy ajánlatsor úgy van beállítva, hogy a **Számítási módszer** mező *Halmozott* értékű, az **Alap** mező értéke pedig *Érték*. Olyan számítási sorokat tartalmaz, amelyek a következő visszatérítéseket biztosítják:

- **A sor:** 10 százalék, legfeljebb 1000 USD
- **B sor:** 25 százalék, legfeljebb 2500 USD

Ha a megvásárolt vagy eladott áruk értéke 2000 USD, a számítás csak a B sort használja. Az ebből eredő 500 USD visszatérítést a következőképpen számítják ki:

- **Teljes visszatérítés:** *Eladott érték* × *Visszatérítés (B)* = 2000 USD × 25 százalék = 500 USD

### <a name="rolling-calculation-method"></a>Görgetett számítási módszer

A görgetett számítási mód kiszámítja az ajánlat összes lehetséges számítási sorát. Ha több számítási sor van, és ezek közül többet elér a mennyiség, akkor a program az elért számítási sorokat alkalmazza, de felső küszöbértékek vonatkoznak minden egyes százalékra. A többi számítási módszerhez hasonló görgetett módszer a **Visszatérítés-kezelés részletei** gyorslap **Általános** lapján található **Alap** mező beállítását használja annak meghatározására, hogy az értékesítési mennyiség vagy az eladási érték használható-e a visszatérítések kiszámításához.

Például egy ajánlatsor úgy van beállítva, hogy a **Számítási módszer** mező *Görgetett* értékű, az **Alap** mező értéke pedig *Érték*. Olyan számítási sorokat tartalmaz, amelyek a következő visszatérítéseket biztosítják:

- **A sor:** 10 százalék, legfeljebb 1000 USD
- **B sor:** 25 százalék, legfeljebb 2500 USD

Ha a megvásárolt vagy eladott áruk értéke 2,000 USD, az ebből eredő 600 USD visszatérítést a következőképpen számítják ki:

- **Visszatérítés (A):** *Küszöbérték (A)* × *Százalék (A)* = 1000 USD × 10 százalék = 100 USD
- **Visszatérítés (B):** *Eladott érték* × *Százalék (B)* = 2000 USD × 25 százalék = 500 USD
- **Teljes visszatérítés:** *Visszatérítés (A)* + *Visszatérítés (B)* = 100 USD + 500 USD = 600 USD

### <a name="total-calculation-method"></a>Összesített számítási módszer

Az összesített számítási módszer az összes számítási sort használja a visszatérítés kiszámításához. Az összesített mennyiséget alkalmazza minden egyes elért számítási sor visszatérítésének kiszámítására, és minden számítási sor a százalékát a teljes összegre alkalmazza. A többi számítási módszerhez hasonló összesített módszer a **Visszatérítés-kezelés részletei** gyorslap **Általános** lapján található **Alap** mező beállítását használja annak meghatározására, hogy az értékesítési mennyiség vagy az eladási érték használható-e a visszatérítések kiszámításához.

Például egy ajánlatsor úgy van beállítva, hogy a **Számítási módszer** mező *Összesített* értékű, az **Alap** mező értéke pedig *Érték*. Olyan számítási sorokat tartalmaz, amelyek a következő visszatérítéseket biztosítják:

- **A sor:** 10 százalék, legfeljebb 1000 USD
- **B sor:** 25 százalék, legfeljebb 2500 USD

Ha a megvásárolt vagy eladott áruk értéke 2,000 USD, az ebből eredő 700 USD visszatérítést a következőképpen számítják ki:

- **Visszatérítés (A):** *Eladott érték* × *Százalék (A)* = 2000 USD × 10 százalék = 200 USD
- **Visszatérítés (B):** *Eladott érték* × *Százalék (B)* = 2000 USD × 25 százalék = 500 USD
- **Teljes visszatérítés:** *Visszatérítés (A)* + *Visszatérítés (B)* = 200 USD + 500 USD = 700 USD
