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
ms.openlocfilehash: f5f1f2c8e3e43e36d837ebf989422b0dca7819d6
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741176"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]