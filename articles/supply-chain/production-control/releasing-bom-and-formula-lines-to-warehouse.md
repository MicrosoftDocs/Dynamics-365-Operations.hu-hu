---
title: Az anyagjegyzék- és receptúrasorok kiadása a raktárba
description: Ez a témakör ismerteti a nyersanyag kiadásának folyamatát az anyagjegyzéksorok és receptúrasorok kiadásához a raktárba.
author: johanhoffmann
manager: tfehr
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm, ProdParmReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: ab0a6e7de02b4b69d3f7a129392a1057482f0c26
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826335"
---
# <a name="release-bom-and-formula-lines-to-the-warehouse"></a>Az anyagjegyzék- és receptúrasorok kiadása a raktárba

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti a nyersanyag kiadásának folyamatát az anyagjegyzéksorok és receptúrasorok kiadásához a raktárba. Amikor kiadunk egy anyagjegyzék- vagy receptúrasort a raktárba, a rendszer először azt határozza meg, hogy az anyagok már rendelkezésre állnak-e a termelés bemeneti helyén az üzemben, ahol az anyagot felhasználják a termelési folyamat során.

- Ha az anyag rendelkezésre áll a termelés bemeneti helyén, azonnal kitárolják a helyről, amint megérkezik a jelzés az anyagok raktárba való kiadására.
- Ha az anyag nem áll rendelkezésre a termelés bemeneti helyén, az anyag kiadása azt jelzi, hogy anyagot át kell helyezni a helyekről a raktárban a termelés bemeneti helyére. Az anyagot áthelyezik nyersanyag-kitárolásra raktári munkával. Ennek megfelelően be kell állítani nyersanyag-kitárolási raktárkezelési folyamatokat. További információkat lásd: [Feltöltés áttekintése](../warehousing/replenishment.md) és [Raktári munka ellenőrzése munkasablonok és helyutasítások használatával](../warehousing/control-warehouse-location-directives.md).

## <a name="methods-for-releasing-bom-and-formula-lines"></a>Anyagjegyzék- és receptúrasorok kiadásának módszerei

Beállítható, hogy az anyagjegyzék- és receptúrasorok kiadása a termelési rendelés vagy a kötegrendelés kiadásának részeként történjen. Másik megoldásként a kiadást egy kötegelt feladat is végezheti, vagy kézi beavatkozásként is végrehajtható.

Az anyagjegyzék- és receptúrasorok kiadásához használt módszert a **Termelési sor kiadása** paraméter vezérli. Itt találhatja meg ezt a paramétert: **Gyártásvezérlés** \> **Beállítás** \> **Termelési paraméterek**.

- **Anyagjegyzék- és receptúrasorok kiadása a termelési vagy a kötegrendelés kiadásának részeként** – ennél a módszernél egy termelési vagy kötegrendelés anyagjegyzék és receptúrasorait a rendelés kiadási folyamatának részeként adják ki. A termelési vagy kötegrendelés kiadásának részeként a termelési munkákat általában az üzem dolgozói számára adják ki, és kinyomtatják a termelési dokumentumokat. A folyamat során a rendelés állapota is megváltozik **Kiadva** állapotra.
- **Anyagjegyzék- és receptúrasorok kiadása kötegelt feladatként vagy manuális beavatkozásként** – ennél a módszernél az anyagjegyzék- és receptúrasorokat kizárólag az **Anyagjegyzék és receptúrasorok automatikus kiadása** kötegelt feladat részeként, vagy manuális beavatkozással lehet kiadni. Anyagjegyzék- és receptúrasorok manuális kiadásához válassza a **Kiadás raktárba** lehetőséget a termelési rendelés listája vagy a termelési rendelés részletei oldalon, a műveleti ablaktáblán.

Ha gyors áttekintést szeretne arról, hogy miként adható ki az anyagjegyzék és a receptúrasorok a termelésbe kötegelt feladat segítségével, nézze meg ezt a YouTube-videót: [Termeléskitárolás kiadása a raktárba kötegelve](https://www.youtube.com/watch?v=8urAJn50dQ8).

## <a name="releasing-the-bom-and-formula-lines-by-using-a-batch-job"></a>Anyagjegyzék- és receptúrasorok kiadása kötegelt feladat segítségével

Az **Anyagjegyzék és receptúrasorok automatikus kiadása** kötegelt feladat végighalad azokon a kiválasztott anyagjegyzék- és receptúrasorokon, amelyeknek van fennmaradó, kiadható mennyisége. A feladat csak a következő állapotú rendeléseket veszi figyelembe: **Kiadva**, **Elindítva** vagy **Készként jelentve**. Ha egy anyagjegyzék- vagy receptúrasornak van fennmaradó kiadható mennyisége, a feladat maximálisan akkora mennyiséget adhat ki, amennnyi a már ténylegesen lefoglalt mennyiség, és a fizikailag rendelkezésre álló mennyiség.

### <a name="example-of-a-batch-job-release"></a>Példa egy kötegelt feladattal való kiadásra

| Eset | Fennmaradó kiadható mennyiség | Fizikailag lefoglalt mennyiség | Fizikailag rendelkezésre álló mennyiség | A kötegelt feladat által kiadott mennyiség |
|----------|-------------------------------|------------------------------|-------------------------------|------------------------------------|
| 1        | 100                           | 20                           | 90                            | 100                                |
| 2        | 100                           | 20                           | 70                            | 90                                 |
| 3        | 100                           | 0                            | 90                            | 90                                 |
| 4        | 100                           | 0                            | 110                           | 100                                |
| 5        | 100                           | 20                           | 0                             | 20                                 |

### <a name="batch-job-setup"></a>Kötegelt feladat beállítása

Az **Anyagjegyzék- és receptúrasorok automatikus kiadása** kötegelt feladat lekérdezésében szűrési feltétel állítható be annak a megadására, hogy a feladat hány nappal előre keressen sorokat, amelyeknek van kiadatlan mennyisége. A feladat lekérdezésben a **Nyersanyag dátuma** mezőben használja a **(LessThanDate())** funkciót szűrőfeltételként.

A következő ábrán egy olyan termelési rendelés látható, amelyhez két munka tartozik, 10 és 20, amelyek lefedik az összeállítást és a csomagolást a termelési rendeléshez. Mindegyik feladat bizonyos anyagmennyiség felhasználására van beállítva. Az ábrán a kiadási időkorlátja, amelyet a zöld nyíl jelez az idő sora alatt, megegyezik a **(LessThanDate())** feltételnél megadott napok számával. A **(LessThanDate(2))** például azt jelzi, hogy a feladatnak csak két napos időkorláton belül kell kiadatlan mennyiségeket keresnie.

![Példa egy termelési rendelésre, amelyhez két kötegelt feladat tartozik](media/bach-job-setup.PNG)

## <a name="releasing-material-per-operation-number-or-in-proportion-to-the-amount-of-finished-goods"></a>Anyagok kiadása műveletszám szerint, vagy a késztermékek mennyiségének arányában

Ha az anyagok kiadása a **Termelési rendelés kiadásán** paraméter beállításának használatával történik, manuális kiadás esetén két lehetőség van az anyagkiadás vezérlésére:

- Anyagok kiadása műveletszám szerint.
- Anyagok kiadása a késztermékek mennyiségének arányában.

### <a name="release-material-per-operation-number"></a>Anyagok kiadása műveletszám szerint

Az anyag kiadását meghatározó műveletek szabályozására használja a **Kiadás raktárba** oldalt.

- Válassza ki a következőt: **Gyártásvezérlés** \> **Termelési rendelések** \> **Minden termelési rendelés**, válasszon termelési rendelést, majd a **Raktár** lapon jelölje be a **Kiadás raktárba** lehetőséget. Ezután használja a **Kezdő műveletszám** és a **Záró műveletszám** mezőt a műveletszámok tartományának meghatározásához.

A következő ábrán egy termelési rendelés látható, amelyhez két művelet tartozik, 10 és 20. Ebben a példában, ha a kiadást a 10-es műveletre korlátozza, csak az M9203 anyag kiadása történik meg.

![Példa anyag kiadására műveletszám szerint](media/two-operations.PNG)

Ha gyors áttekintést szeretne arról, hogyan lehet kiadni a késztermékek arányában anyagokat, nézze meg ezt a rövid -YouTube-videót [a termelési rendelés kiadási folyamatának fejlesztéseiről](https://www.youtube.com/watch?v=Rm3ojAz6Zu0).

### <a name="release-material-in-proportion-to-the-amount-of-finished-goods"></a>Anyagok kiadása a késztermékek mennyiségének arányában

Nyersanyagok kiadhatók késztermékek részleges mennyiségéhez vagy meghatározott egységben.

- Nyersanyagok kiadásához késztermékek részleges mennyiségéhez válassza ki a következőt: **Gyártásvezérlés** \> **Termelési rendelések** \> **Minden termelési rendelés**, válasszon termelési rendelést, majd a **Raktár** lapon jelölje be a **Kiadás raktárba** lehetőséget. Ezután írjon be egy mennyiséget a **Mennyiség** mezőbe.

    Létrehozunk például egy termelési rendelést, és 1000 darabra (db) ütemezzük. Az üzemirányítási felügyelő 100 darabra tervezi a termelést a következő műszakra, és csak az adott műszakra szeretne anyagokat kiadni. Ebben az esetben a felügyelő a **Mennyiség** mezőt használhatja az anyagok kiadására 100 darabhoz: ez a következő műszakra tervezett mennyiség.

- Nyersanyagok kiadásához adott egységben válassza ki a következőt: **Gyártásvezérlés** \> **Termelési rendelések** \> **Minden termelési rendelés**, válasszon termelési rendelést, majd a **Raktár** lapon jelölje be a **Kiadás raktárba** lehetőséget. Ezután használja az **Egység** mezőt a késztermék egységének a kiválasztásához, amelyhez anyagot szeretne felszabadítani.

    A rendelkezésre álló egységek a késztermék egység-szekvenciacsoportazonosítójában vannak meghatározva.

    Egy készterméknek például a következő egységátváltással rendelkezik a font (lbs.) és a raklap (PL) között: 1 PL = 100 lbs. Termelési rendelés létrehozásához 10 000 lbs. késztermékhez kiadhatja a nyersanyagokat annyi raklaphoz, amennyit gyártani tervez. Válassza a **PL** lehetőséget egységként, majd adjon meg egy megfelelő számot a **Mennyiség** mezőben.
