---
title: "Nyitott munkalista rendszercsoportosítása"
description: "Ez a témakör leírja, hogyan történik a nyitott munkalista szűrése egy mobileszközön."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: dbf0e49b1156c54cd37bbbe57ca564cdbc45fb2d
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017

---

# <a name="system-grouping-on-an-open-work-list"></a>Nyitott munkalista rendszercsoportosítása

[!include[banner](../includes/banner.md)]

Csoportosító rendszermező segítségével a mobileszköz menüpontjának szerkesztése nélkül szűrheti a nyitott munkalistát.
A rendszercsoportosítás alkalmazási köre egyetlen munkafejlécmező munkalistájának szűrése. A rendszercsoportosítás nem használható online szinten lévő mezők szűrésére.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Rendszercsoportosítás beállítása nyitott munkalistához
A következő lépésekkel beállíthatja a rendszercsoportosítást egy nyitott munkalistához.

-   Egy mobileszköz menüpontjában válassza a **Mód: közvetett** és a **Tevékenység kódja: nyitott munkalista megjelenítése** lehetőséget. Az alábbi lehetőségek válnak elérhetővé. Ezek a beállítások szükségesek a rendszercsoportosítás nyitott munkalistán történő működéséhez. 

| Lehetőség        | Leírás   | 
| ------------- | ------------- |
| Rendszercsoportosítás engedélyezése   | Lehetővé teszi a rendszercsoportosítást a kijelölt munkalista menüelemére vonatkozóan.| 
| Csoportosító rendszermező   | Csak akkor érhető el, ha a **Rendszer működésének ellenőrzése** értéke **Igen**. Válassza ki azt a mezőt, amely meghatározza, hogyan fogja a rendszer kitárolási munkát csoportosítani a dolgozók számára. Ha például bejelöli a **ShipmentId** mezőt, a dolgozó ellenőrzi a szállítmányazonosítót a kitárolási munka csoportosításához. A rendszer hozzárendeli a dolgozóhoz a szállítmány minden munkáját. Ez a mező azt igényli, hogy hozzon létre egy menüelemet a rendszer által csoportosított meglévő munka használatához. Használja a **Rendszercsoportosítási címke** mezőt, amely jelzi a dolgozónak, hogy mit olvasson be. |
| Csoportosító rendszercímke   | Csak akkor érhető el, ha a **Rendszer működésének ellenőrzése** értéke **Igen**. Írja be a szöveget, amely a dolgozót tájékoztatja arról, mit olvasson be, ha a kitárolási munka csoportosítva van a rendszerben. Például ha a **Szállítmányazonosító** mezőt használja egy szállítmány kitárolási munkájának csoportosítására, megadhatja a Szállítási azonosító értékét a mezőben. Ez a mező azt igényli, hogy hozzon létre egy menüelemet a rendszer által csoportosított meglévő munka használatához. A **Rendszercsoportosítás** mezőben ki kell választania a mezőt is, amely szerint a csoportosítás történik.|

