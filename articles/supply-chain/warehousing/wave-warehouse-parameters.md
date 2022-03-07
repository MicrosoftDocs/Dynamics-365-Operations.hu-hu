---
title: Raktári paraméterek hullámfeldolgozáshoz
description: Ez a témakör leírja, hogyan állíthatja be a hullám feldolgozásához szükséges raktárparamétereket. A hullámfeldolgozással több munkarendelés kitárolási munkáját egyetlen hullámba csoportosíthatja.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: cd7961ae8f4237bcee7ae4c53365d24ab03c5aa9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572218"
---
# <a name="warehouse-parameters-for-wave-processing"></a>Raktári paraméterek hullámfeldolgozáshoz

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan állíthatja be a hullám feldolgozásához szükséges raktárparamétereket. A hullámfeldolgozással több munkarendelés kitárolási munkáját egyetlen hullámba csoportosíthatja.

A hullámfeldolgozás alkalmazásához adja meg a következőket a **Raktárkezelési paraméterek** lapon:

- Hogy kötegelt feldolgozással feldolgozhatók-e a hullámok.
- Hogy egy naplófájlban gyűjti-e az adatokat a hullámok feldolgozása során.

## <a name="set-up-warehouse-management-parameters-for-wave-processing"></a>Raktárkezelési paraméterek beállítása hullámfeldolgozáshoz

A hullámfeldolgozáshoz szükséges raktárparaméterek beállításához kövesse az alábbi lépéseket:

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Raktárkezelési paraméterek** elemre.

1. A **Hullámfeldolgozás** gyorslapon tegye a következő beállításokat:

    - **Hullámfeldolgozás kötegelt csoportja** – Válassza ki hullámok kötegfeladattal való feldolgozásához használandó kötegcsoportot. A kötegcsoport határozza meg, melyik kiszolgálón futnak a kötegfeladatok.
    - **Hullámok kötegelt feldolgozása** – annak kiválasztása, hogy engedélyezi-e a hullámok automatikus feldolgozását kötegelt feladattal. Párhuzamos feldolgozás csak *Igen* beállítással használható. A kötegelt feladatot a **Hullámok feldolgozása** oldalon lehet beállítani. (Lásd még a megjegyzést a lista végén.)
    - **Hullám előrehaladási naplójának létrehozása** – Válassza ki, hogy a rendszernek létre kell-e hoznia egy naplórekordot minden alkalommal, amikor egy cikk és a dimenziói felosztása megkezdődik és véget ér. Ezt a naplót csak akkor engedélyezze, ha szüksége van rá, például a kezdeti tesztelés vagy a hibaelhárítás során. További információ: [Hullámfelosztás](wave-allocation-method.md).
    - **Hullámfeldolgozási előzménynapló létrehozása** – Válassza ki, hogy a hullámra vonatkozó információkat automatikusan menti-e egy naplófájlban a hullám feldolgozása után, beleértve a függőben lévő felosztások párhuzamos feldolgozása során is. Ezt általában csak hibaelhárítás közben engedélyezze, mert többletterhelést jelent. A napló megtekintéséhez lépjen a **Raktárkezelés \> Kimenő hullámok \> Hullámfeldolgozási előzmények naplója** részre. További információ: [Hullámlétrehozás és feldolgozás](wave-processing.md).
    - **Tárolóra bontás előzménynaplójának létrehozása** – Itt adhatja meg, hogy a hullám feldolgozása után automatikusan mentse-e a naplófájlban lévő hullámok tárolóra bontási adatait. A napló megtekintéséhez lépjen a **Raktárkezelés \> Csomagolási és tárolóra bontás \> Tárolóra bontási előzmények** részre.
    - **Várakozás zárolásra (ms)** – Adja meg azt az időt (ezredmásodpercben), amennyit egy felosztási lépésnek várakoznia kell egy olyan rendszererőforrásra, amelyet amely egy másik felosztási lépés zárolt. Ha ez az idő letelik, a hullám feldolgozása nem történik meg, és a rendszer egy hibaüzenetet jelenít meg.

1. A **Kiadás a raktárba** gyorslapon tegye a következő beállítást:

    - **Hiba köteg sikertelensége esetén** – Válassza ki, hogy hibát hoz-e létre, ha a raktár kötegelt feldolgozás kiadása sikertelen. Ha ez engedélyezve van, a sikertelen feladatok *Hiba* állapottal végződnek. Ha ez le van tiltva, a sikertelen feladatok *Lezárult* állapottal végződnek.

> [!NOTE]
> A hullám feldolgozásához használt hullámsablonban megadhatja a hullámfeldolgozást automatizáló beállításokat. Ha ütemezést állít be a kötegelt feladathoz, akkor az időzítést össze kell hangolnia a hullámsablonjában megadott automatizálási beállításokkal. További információ: [Hullámsablon létrehozása](wave-templates.md).
>
> Ha a *Szállításkezelés* és a *Speciális raktárkezelés* modulokat is használja, akkor meghatározhatja, hogy hullámfeldolgozáskor sor kerüljön-e a rakományok konszolidálására. Ez például akkor hasznos, ha több kisebb rakomány szállítható ki egyszerre. Ha egy hullám feldolgozásakor össze szeretné konszolidálni a rakományokat, a **Rakományok** lapon jelölje be a **Rakomáynok konszolidálása hullámfeldolgozás közben** jelölőnégyzetet.</P>

## <a name="set-up-full-or-partial-reservation-for-production-waves"></a>Teljes vagy részleges foglalás beállítása termelési hullámokhoz

Az értékesítési és a kanban rendelésekhez, a készletet a rendelés raktárból történő kiadása előtt le kell foglalni. Ellenkező esetben a cikkek vagy a felosztási sorok nem dolgozhatók fel a hullámban. A termelési rendelések azonban egy kicsit rugalmasabbak. A termelési rendelésekhez a következőket állíthatja be:

- Engedje, hogy a termelési megrendeléseket akkor is ki lehessen adni a raktárból, ha nem foglalható le minden anyag. Ha ezt a lehetőséget választja, akkor manuálisan meg kell ismételnie a raktárba kiadás folyamatát, amikor további anyagok rendelkezésre állnak. Ez például hasznos, ha a termelés megkezdéséhez szükséges anyagok rendelkezésére állnak, a további anyagok beérkezésére pedig tud várni.
- Minden anyagot le kell foglalni, mielőtt egy megrendelést ki lehet adni a raktárba.

Teljes foglalás megköveteléséhez illetve részleges foglalás engedélyezéséhez tegye a következőket:

1. Ugorjon a **Gyártásvezérlés** \> **Beállítás** \> **Gyártásvezérlési paraméterek** pontra.
1. Az **Általános** lap **Kiadás raktárba** mezőjében jelölje ki az alapértelmezett beállítást.
