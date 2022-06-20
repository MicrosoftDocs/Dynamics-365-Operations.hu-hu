---
title: Tervezési feladat visszavonása
description: Ez a cikk bemutatja, hogyan lehet visszavonni egy olyan aktív tervezési feladatot, amely a Tervezés optimalizálási funkciót használja.
author: t-benebo
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 0474c50157295d9ecd2341b700c07f4fbf1ed51f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900941"
---
# <a name="cancel-a-planning-job"></a>Tervezési feladat visszavonása

[!include [banner](../../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management rendszerben érvényteleníthetők az olyan aktív tervezési feladatok, amelyek a Tervezés optimalizálása funkciót használják. Ha a párbeszédpanelen a **Mégse** lehetőséget választja, amikor a tervezésoptimalizálási feladat közvetlenül a felhasználói felületről indul el, (nem a háttérben), akkor ez nem törli a tervezési optimalizációs feladatot. Még ha figyelmeztetés jelenik meg, mint a "művelet visszavonva", akkor is a következő lépések végrehajtásával kell megszüntetni egy tervezési feladatot a tervezési optimalizációval.


Aktív tervezési feladat érvénytelenítéséhez hajtsa végre az alábbi lépéseket. 

> [!NOTE]
> Csak egy aktív feladat érvényteleníthető.

1. Lépjen az **Alaptervezés \> Beállítás \> Tervek** részre.
2. Válassza ki a tervezés futtatásához megfelelő tervet.
3. Válassza az **Előzmények** lehetőséget.
4. Válassza ki az érvényteleníteni kívánt tervezési feladatot.
5. Válassza a **Mégse** lehetőséget.

A feladat állapota mindaddig **Megszakítás** lesz, amíg a Tervezés optimalizálása szolgáltatás meg nem erősíti, hogy a feladat érvénytelenítve lett. Ezt követően az állapot **Megszakítva** lesz.

> [!NOTE]
> Az állapot változásainak megjelenítéséhez a **Frissítés** gombra kattintva frissíteni kell az oldalt.

## <a name="additional-resources"></a>További erőforrások

[Tervezési optimalizálás áttekintése](planning-optimization-overview.md)

[Tervezési optimalizálás indítása](get-started.md)

[A tervezésoptimalizálása illeszkedési elemzése](planning-optimization-fit-analysis.md)

[Tervelőzmények és tervezési naplók megtekintése](plan-history-logs.md)

[Szűrők alkalmazása egy tervre](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]