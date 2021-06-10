---
title: Könyvelési vagy jelentési pénznem módosítása
description: Ez a témakör azt ismerteti, hogyan módosítható a könyvelési vagy jelentési pénznem, illetve hogyan adható hozzá jelentési pénznem egy főkönyv beállításához.
author: kweekley
ms.date: 05/05/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0435deb009173684c7faaf5340e8095c019ec71c
ms.sourcegitcommit: 2cd82983357b32f70f4e4a0c15d4d1f69e08bd54
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085474"
---
# <a name="change-the-accounting-or-reporting-currency"></a>Könyvelési vagy jelentési pénznem módosítása

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan módosítható a könyvelési vagy jelentési pénznem, illetve hogyan adható hozzá jelentési pénznem egy főkönyv beállításához.

## <a name="symptom"></a>Tünet

Módosítani szeretné a könyvelési vagy jelentési pénznemet, illetve jelentési pénznemet hozzá szeretne adni egy főkönyv beállításához. Ez általában a következő forgatókönyvek esetén fordul elő:

- A jogi személy beállításakor helytelen könyvelési vagy jelentési pénznemet adtak meg. Most meg szeretné változtatni az adott pénznemet.
- A jelentési pénznemet a jogi személy létrehozásakor meghatározták, de a szervezet most el szeretné távolítani a jelentési pénznemet.
- A szervezet frissíti a szolgáltatást, vagy át szeretne települni a Microsoft Dynamics 365 Finance szolgáltatásba, és szeretné módosítani a könyvelési vagy jelentési pénznemet.

Egy olyan szervezet, amely korábban nem használta a kettős pénznem funkciót, el szeretné kezdeni használni. Ez a probléma általában a következő forgatókönyvek esetén fordul elő.

- A jogi személy beállításakor nem adtak meg jelentési pénznemet. (A jelentési pénznem megadása nem kötelező.) Most szeretne jelentési pénznemet hozzáadni.

## <a name="resolution"></a>Megoldás

A legfontosabb szempont az, hogy a főkönyv beállításánál a jogi személyben bármilyen tranzakciót (tényleges vagy költségvetési) feladtak-e. **A könyvelési vagy jelentési pénznem nem módosítható, és nem adható hozzá jelentési pénznem, ha a jogi személynél bármilyen tranzakciót (tényleges vagy költségvetési) feladtak.** Kövesse a következő szakaszok közül a megfelelő lépéseit, attól függően, hogy feladtak-e tranzakciókat.

### <a name="no-transactions-have-been-posted"></a>Nem adtak fel tranzakciókat

1. Abban a jogi személyben, amelyre vonatkozóan a pénznemeket frissíteni szeretné, lépjen a **Főkönyv \> Főkönyv beállítása \> Főkönyv** lehetőségre.
2. A **Főkönyv** lapon válassza a **Szerkesztés** lehetőséget.
3. A **Pénznem** gyorslapon válassza ki a jogi személyhez használni kívánt könyvelési pénznemet és jelentési pénznemet.
4. Válassza a **Mentés** lehetőséget.

Ha a **Főkönyv** oldalon nem elérhetők a könyvelési pénznemhez és a jelentési pénznemhez tartozó mezők, akkor legalább egy tranzakciót (tényleges vagy költségvetési) feladtak a jogi személyben. Ezért a pénznemek nem módosíthatók. Ebben az esetben kövesse a következő szakaszban található lépéseket.

### <a name="transactions-have-been-posted"></a>Feladtak tranzakciókat

**Ha feladtak tranzakciókat a jogi személyben, a könyvelési és jelentési pénznemek módosításának vagy hozzáadásának egyetlen módja egy új jogi személy létrehozása, amelyhez a megfelelő pénznemek tartoznak.** A folyamat megkönnyítése érdekében a rendszerben található adatkezelés segítségével átmásolhatja a beállítási rekordokat és alaprekordokat az aktuális jogi személyből az új jogi személybe.

A könyvelési és jelentési pénznemek változásai minden területre kiterjednek. Ezek nem csak a főkönyvet érintik, hanem minden részfőkönyvet is (Kinnlevőségek, Kötelezettségek, Készlet, Projekt stb.), az összes független szoftverszállítói (ISV) megoldást, valamint bármely olyan Ön által létrehozott bővítmény, amelyben összegeket tárolnak.

Az egyes összegek megkeresésének és más pénznemre való átváltásának folyamata hibákat tesz lehetővé. Ezért a mérnöki csapat nem hagy jóvá olyan parancsprogramokat, amelyek módosítanak vagy hozzáadnak könyvelési és jelentési pénznemeket. Ezenkívül ugyan korábban létezett olyan Microsoft Dynamics AX 2012-eszköz, amellyel módosítani lehetett és hozzá lehetett adni könyvelési és jelentési pénznemeket, az eszköz immár elavult az AX 2012 R3 és a Finance szolgáltatásra vonatkozóan is.

Kövesse ezeket a lépéseket a beállítási és alapadatok aktuális jogi személyből az új jogi személybe történő átmásolásához.

1. Menjen a **Munkaterületek \> Adatkezelés** lehetőségre.
2. Válassza a **Sablonok** lehetőséget az **Importálás/exportálás** csoportban.
3. Győződjön meg arról, hogy vannak rendelkezésre álló sablonok. Ha nem állnak rendelkezésre sablonok, válassza az **Alapértelmezett sablonok betöltése** lehetőséget, és várja meg, amíg létrejönnek a sablonok.
4. Lépjen vissza az **Adatkezelés** munkaterületre.
5. Válassza a **Másolás jogi személybe** lehetőséget.
6. Írja be a csoport nevét és leírását.
7. A **Forrásként megadott jogi személy** mezőben válassza ki azt a jogi személyt, amelyből adatokat szeretne másolni.
8. A **Célként megadott jogi személyek** gyorslapon válassza a **Jogi személyek létrehozása** lehetőséget az új jogi személy létrehozásához, amelybe bemásolhatja a forrásként megadott jogi személy adatait. Válassza a **Meglévő kiválasztása** lehetőséget az adatok meglévő jogi személybe történő másolásához.
9. Nem kötelező: Állítsa a **Számsorozatok másolása** mezőt **Igen** értékre. (Ez a lépés az adatok másolásakor ajánlott.)
10. A **Kiválasztott entitások** területen válassza a **Sablon hozzáadása** lehetőséget.
11. Válassza ki a használni kívánt sablonokat. Az új jogi személy számára javasolt sablonok közé tartozik a **025 – Főkönyv** és a **Pénzügyek**. Javasoljuk, hogy tekintse át az összes többi rendelkezésre álló sablont is annak megállapításához, hogy ezek közül bármelyik vonatkozik-e az Ön követelményeire.
12. Válassza a **Másolás jogi személybe** lehetőséget olyan kötegfolyamat elindításához, amely létrehozza a kijelölt entitásokat, és átmásolja őket a célként megadott jogi személybe.
13. A folyamat befejezése után, de még a tranzakciók feladása előtt lépjen a főkönyvbe, és frissítse a könyvelési és jelentési pénznemeket a témakörben korábban leírtak szerint.

Ha új jogi személyt hozott létre a könyvelési vagy jelentési pénznem módosítása érdekében, ellenőrizze, hogy a nyitó egyenlegeket a rendszer átváltotta a régi jogi személy pénznemeiről az új pénznemeire.

Az előző lépéseket bemutató videó megtekintését itt találja: [Másolás jogi személybe](https://community.dynamics.com/365/b/techtalks/posts/copy-into-legal-entity-october-24-2017).
