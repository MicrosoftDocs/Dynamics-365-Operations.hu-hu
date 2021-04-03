---
title: Részlegek létrehozása és társítása a szervezeti hierarchiához
description: A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli. Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások). A részlegek segítségével hozhatók létre jelentések a működési területekről. A részlegeknek lehet eredménykimutatási felelőssége.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HierarchyDesigner, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 723e46f98545e80551da9f79b6aeffc3eca48830
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466014"
---
# <a name="create-departments-and-include-them-in-the-department-hierarchy"></a>Részlegek létrehozása és társítása a szervezeti hierarchiához

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli. Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások). A részlegek segítségével hozhatók létre jelentések a működési területekről. A részlegeknek lehet eredménykimutatási felelőssége.

Egy részleg költséghelyek egy csoportját is magában foglalhatja. A Beosztások hozzárendelhetők részlegekhez. Részleg létrehozásához kattintson az **Emberi erőforrások** &gt; **Részlegek** &gt; **Részleg** elemre. Az alábbi táblázat bemutatja a rendelkezésre álló mezőket.

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

1.  Kattintson az **Emberi erőforrások** &gt; **Részlegek** &gt; **Részlegek hierarchiája** menüpontra.
2.  Kattintson a **Szerkesztés** lehetőségre, majd válassza ki a szervezetet, amely alá a részleg tartozik.
3.  Kattintson a **Beszúrás** lehetőségre, és válassza ki a **Részleget** a listából.
4.  A megjelenő listából válassza ki a részleget, amelyet hozzá kíván adni a hierarchiához.
5.  Mentse el a módosításokat. Egy üzenet fog kapni arról, hogy létrejött-e a hierarchia egy vázlatverziója.
6.  Ha elkészült, kattintson a **Közzététel** lehetőségre a hierarchiatervezőben. Megadhat egy hatályba lépési dátumot, amely azt jelzi, hogy mikor kell közzétenni a hierarchiát. Ha például a következő naptári év kezdetén kell hozzáadni az új részleget, akkor állítsa a hatálybalépési dátumot a következő év január 1-re. A hierarchia módosításai ezen a dátumon lépnek hatályba.

## <a name="steps-for-creating-a-department"></a>A részleg létrehozásának lépései
Lásd az [Új részlegek meghatározása](../fin-and-ops/hr/tasks/define-new-departments.md) cikket az új osztály létrehozásának lépésről lépésre útmutatójához. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]