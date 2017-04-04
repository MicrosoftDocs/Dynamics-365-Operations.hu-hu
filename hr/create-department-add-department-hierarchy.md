---
title: "Részleg létrehozása és társítása a szervezeti hierarchiához"
description: "A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli. Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások). A részlegek segítségével hozhatók létre jelentések a működési területekről. A részlegeknek lehet eredménykimutatási felelőssége."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HierarchyDesigner, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ee51abe108b3bc0aabc764b991222db6d185e532
ms.lasthandoff: 03/31/2017


---

# <a name="create-a-department-and-associate-it-with-the-department-hierarchy"></a>Részleg létrehozása és társítása a szervezeti hierarchiához

A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli. Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások). A részlegek segítségével hozhatók létre jelentések a működési területekről. A részlegeknek lehet eredménykimutatási felelőssége.

Egy részleg költséghelyek egy csoportját is magában foglalhatja. A Beosztások hozzárendelhetők részlegekhez. Egy osztály létrehozásához kattintson a **az emberi erőforrások**&gt;**szervezeti egységek**&gt;**osztály**. Az alábbi táblázat ismerteti a rendelkezésre álló mezőket.

| Mező               | Leírás                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Név                | Adja meg a részleg nevét.                                                                                                                                                                                  |
| Részleg száma   | A rendszer automatikusan létrehozhat egy alapértelmezett értéket, ha egy számsorozat kódja hozzá van rendelve a **Szervezet száma** hivatkozáshoz a **Számsorozatok** lapon.                                                 |
| Keresési név         | Adja meg a részleg megkeresésére használt nevet vagy rövidítést.                                                                                                                                            |
| Feljegyzés                | Itt adjon meg további információkat.                                                                                                                                                                            |
| Hierarchiában        | A bejelölt jelölőnégyzet mutatja, ha a részleg szerepel a szervezeti hierarchiában. Ezen cikk későbbi részei tartalmaznak információkat azzal kapcsolatban, hogy miként lehet részleget adni a részleghierarchiához. |
| DUNS-szám         | A DUNS a Data Universal Numbering System számozási rendszer rövidítése. Ez egy a Dun & Bradstreet által kiállított kilencjegyű szám.                                                                                                     |
| Vezető             | Adja meg a részleget vezető személyt.                                                                                                                                                                    |
| Címek           | Adja meg a részleg címinformációit. Adja meg például annak az épületnek a levelezési címét, amelyben a részleg található.                                                                          |
| Kapcsolattartási adatok | Adja meg a részleg kapcsolattartási információit. Adja meg például a részleg ügyfélszolgálatának vagy recepciójának telefonszámát.                                                                                           |

Egy részleg hozzáadásához a részleghierarchiához, tegye a következőket.

1.  Kattintson a **az emberi erőforrások**&gt;**szervezeti egységek**&gt;**szervezeti hierarchia**.
2.  Kattintson a **Szerkesztés** lehetőségre, majd válassza ki a szervezetet, amely alá a részleg tartozik.
3.  Kattintson a **Beszúrás** lehetőségre, és válassza ki a **Részleget** a listából.
4.  A megjelenő listából válassza ki a részleget, amelyet hozzá kíván adni a hierarchiához.
5.  Mentse el a módosításokat. Egy üzenet, hogy a hierarchia egy piszkozatverzióját létrehoztak.
6.  Ha elkészült, kattintson a **a közzététel** a hierarchiatervezőben. Adhat meg dátumot jelzi, amikor a hierarchia közzé kell tenni. Ha például a következő naptári év kezdetén kell hozzáadni az új részleget, akkor állítsa a hatálybalépési dátumot a következő év január 1-re. A hierarchia módosításai ezen a dátumon lépnek hatályba.



