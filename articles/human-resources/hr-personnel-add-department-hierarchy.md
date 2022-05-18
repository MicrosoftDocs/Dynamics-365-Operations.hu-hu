---
title: Részlegek létrehozása és társítása a szervezeti hierarchiához
description: A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli. Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások).
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HierarchyDesigner, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: cdc0440c02d0e66eaa89bfd875d8c8edf8d99c96
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688601"
---
# <a name="create-departments-and-include-them-in-the-department-hierarchy"></a>Részlegek létrehozása és társítása a szervezeti hierarchiához


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli. Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások). A részlegek segítségével hozhatók létre jelentések a működési területekről. A részlegeknek lehet eredménykimutatási felelőssége.

Egy részleg költséghelyek egy csoportját is magában foglalhatja. A Beosztások hozzárendelhetők részlegekhez. Részleg létrehozásához kattintson az **Emberi erőforrások** &gt; **Részlegek** &gt; **Részleg** elemre. Az alábbi táblázat bemutatja a rendelkezésre álló mezőket.

| Mező               | Leírás                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Név**                | Adja meg a részleg nevét.                                                                                                                                                                                  |
| **Részleg száma**   | A rendszer automatikusan létrehozhat egy alapértelmezett értéket, ha egy számsorozat kódja hozzá van rendelve a **Szervezet száma** hivatkozáshoz a **Számsorozatok** lapon.                                                 |
| **Keresési név**         | Adja meg a részleg megkeresésére használt nevet vagy rövidítést.                                                                                                                                            |
| **Feljegyzés**                | Itt adjon meg további információkat.                                                                                                                                                                            |
| **Hierarchiában**        | A bejelölt jelölőnégyzet mutatja, ha a részleg szerepel a szervezeti hierarchiában. Ezen cikk későbbi részei tartalmaznak információkat azzal kapcsolatban, hogy miként lehet részleget adni a részleghierarchiához. |
| **DUNS-szám**         | A DUNS a Data Universal Numbering System számozási rendszer rövidítése. Ez egy a Dun & Bradstreet által kiállított kilencjegyű szám.                                                                                                     |
| **Vezető**             | Adja meg a részleget vezető személyt.                                                                                                                                                                    |
| **Címek**           | Adja meg a részleg címinformációit. Adja meg például annak az épületnek a levelezési címét, amelyben a részleg található.                                                                          |
| **Kapcsolattartási adatok** | Adja meg a részleg kapcsolattartási információit. Adja meg például a részleg ügyfélszolgálatának vagy recepciójának telefonszámát.                                                                                           |

Egy részleg hozzáadásához a részleghierarchiához, tegye a következőket.

1.  Kattintson az **Emberi erőforrások** &gt; **Részlegek** &gt; **Részlegek hierarchiája** menüpontra.
2.  Kattintson a **Szerkesztés** lehetőségre, majd válassza ki a szervezetet, amely alá a részleg tartozik.
3.  Kattintson a **Beszúrás** lehetőségre, és válassza ki a **Részleget** a listából.
4.  A megjelenő listából válassza ki a részleget, amelyet hozzá kíván adni a hierarchiához.
5.  Mentse el a módosításokat. Egy üzenet fog kapni arról, hogy létrejött-e a hierarchia egy vázlatverziója.
6.  Ha elkészült, kattintson a **Közzététel** lehetőségre a hierarchiatervezőben. Megadhat egy hatályba lépési dátumot, amely azt jelzi, hogy mikor kell közzétenni a hierarchiát. Ha például a következő naptári év kezdetén kell hozzáadni az új részleget, akkor állítsa a hatálybalépési dátumot a következő év január 1-re. A hierarchia módosításai ezen a dátumon lépnek hatályba.

## <a name="steps-for-creating-a-department"></a>A részleg létrehozásának lépései
Lásd az [Új részlegek meghatározása](./hr-personnel-define-departments.md) cikket az új osztály létrehozásának lépésről lépésre útmutatójához. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
