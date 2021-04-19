---
title: Nyitott munkalista rendszercsoportosítása
description: Ez a témakör leírja, hogyan történik a nyitott munkalista szűrése egy mobileszközön.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a4faa358fc598859bf3b226b48b57594317f37d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831098"
---
# <a name="system-grouping-on-an-open-work-list"></a>Nyitott munkalista rendszercsoportosítása

[!include [banner](../includes/banner.md)]

Csoportosító rendszermező segítségével a mobileszköz menüpontjának szerkesztése nélkül szűrheti a nyitott munkalistát.
A rendszercsoportosítás alkalmazási köre egyetlen munkafejlécmező munkalistájának szűrése. A rendszercsoportosítás nem használható online szinten lévő mezők szűrésére.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Rendszercsoportosítás beállítása nyitott munkalistához
A következő lépésekkel beállíthatja a rendszercsoportosítást egy nyitott munkalistához.

-   Egy mobileszköz menüpontjában válassza a **Mód: közvetett** és a **Tevékenység kódja: nyitott munkalista megjelenítése** lehetőséget. Az alábbi lehetőségek válnak elérhetővé. Ezek a beállítások szükségesek a rendszercsoportosítás nyitott munkalistán történő működéséhez. 

|        Lehetőség         |                                                                                                                                                                                                                                                                         Leírás                                                                                                                                                                                                                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Rendszercsoportosítás engedélyezése |                                                                                                                                                                                                                                                 Lehetővé teszi a rendszercsoportosítást a kijelölt munkalista menüelemére vonatkozóan.                                                                                                                                                                                                                                                  |
| Csoportosító rendszermező | Csak akkor érhető el, ha a <strong>Rendszer működésének ellenőrzése</strong> értéke <strong>Igen</strong>. Válassza ki azt a mezőt, amely meghatározza, hogyan fogja a rendszer kitárolási munkát csoportosítani a dolgozók számára. Ha például bejelöli a <strong>ShipmentId</strong> mezőt, a dolgozó ellenőrzi a szállítmányazonosítót a kitárolási munka csoportosításához. A rendszer hozzárendeli a dolgozóhoz a szállítmány minden munkáját. Ez a mező azt igényli, hogy hozzon létre egy menüelemet a rendszer által csoportosított meglévő munka használatához. Használja a <strong>Rendszercsoportosítási címke</strong> mezőt, amely jelzi a dolgozónak, hogy mit olvasson be. |
| Csoportosító rendszercímke |                       Csak akkor érhető el, ha a <strong>Rendszer működésének ellenőrzése</strong> értéke <strong>Igen</strong>. Írja be a szöveget, amely a dolgozót tájékoztatja arról, mit olvasson be, ha a kitárolási munka csoportosítva van a rendszerben. Például ha a <strong>Szállítmányazonosító</strong> mezőt használja egy szállítmány kitárolási munkájának csoportosítására, megadhatja a Szállítási azonosító értékét a mezőben. Ez a mező azt igényli, hogy hozzon létre egy menüelemet a rendszer által csoportosított meglévő munka használatához. A <strong>Rendszercsoportosítás</strong> mezőben ki kell választania a mezőt is, amely szerint a csoportosítás történik.                       |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]