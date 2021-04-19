---
title: Tervezési optimalizálás hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani a Tervezési optimalizálás használata során felmerülő problémákat.
author: ChristianRytt
ms.date: 05/07/2020
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
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2100235fadabe6af87849aab7d9ec55d85ea66fa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812883"
---
# <a name="troubleshoot-planning-optimization"></a>Tervezési optimalizálás hibaelhárítása 

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet javítani a Tervezési optimalizálás használata során felmerülő gyakori problémákat.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>A Tervezési optimalizálás beépülő modul telepítése nem fejeződött be

A Tervezési optimalizálás egy Lifecycle Services (LCS) rendszerrel kompatibilis, 2. vagy magasabb (nem OneBox környezet) szintű, magas rendelkezésre állású környezetet igényel a Dynamics 365 Supply Chain Management 10.0.7-es vagy újabb verziójával. Ha OneBox környezetben próbálja meg telepíteni a bővítményt, a telepítés nem fog befejeződni.

**Javítás**: Szakítsa meg a telepítést, és használjon egy magas rendelkezésre állású, 2. vagy magasabb szintű (nem Onebox) környezetet.

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>A kötegelt feladatok tervezése meghiúsul, amikor a Tervezési optimalizálás engedélyezve van.

A Tervezési optimalizálás engedélyezése esetén a beépített alaptervezési motor automatikusan le van tiltva. A meglévő alaptervezett kötegelt feladatok, amelyeket a beépített Supply Chain Management tervezési morothoz hoztak létre, meghiúsulnak, ha elindulnak, miközben a Tervezési optimalizálás engedélyezve van. Egy hibaüzenet jelenik meg, például *Ez a művelet olyan alaptervezést aktivált, amely nem támogatott, ha a Tervezési optimalizálás engedélyezve van*.

**Javítás**: Szakítsa meg az összes olyan alaptervezési kötegelt feladatot, amelyek a beépített Supply Chain Management-tervezési motorhoz lett létrehozva.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>A Tervezési optimalizálás eredményei eltérnek a korábbi eredményektől

A Tervezés optimalizálás néhány területen eltér a beépített alaptervezési konstrukciótól. Ez a függő szolgáltatások miatt is történhet.

**Javítás**: Futtassa a Tervezési optimalizálás illeszkedési elemzését, majd elemezze az eredményeket a vonatkozó dokumentációval összevetve, hogy megértsék a hatásait. További tájékoztatás: [Tervezésoptimalizálás illeszkedési elemzése](planning-optimization-fit-analysis.md).

## <a name="cant-enable-planning-optimization"></a>A Tervezési optimalizálás nem engedélyezhető?

A **Kapcsolat állapota** állapotnak **Csatlakoztatva** értékűnek kell lennie ahhoz, hogy a **Tervezési optimalizálás használata** beállításnak az **Igen** értéket adja meg. További tájékoztatás: [Első lépések a Tervezésoptimalizálással](get-started.md).

**Javítás**: Győződjön meg arról, hogy a Tervezési optimalizálás beépülő modul telepítése sikeresen befejeződött.

## <a name="error-message-is-shown-during-ctp"></a>Hibaüzenet jelenik meg a CTP során

Ha megpróbálja futtatni az ígérhető (CTP) elemet egy értékesítési rendelésből, amikor a Tervezési optimalizálás engedélyezve van, akkor a következő hibaüzenet jelenik meg: *A művelet olyan alaptervezést aktivált, amely nem támogatott, ha a Tervezés optimalizálása engedélyezve van*.

Ez a termelési rendelések támogatásának részeként tervezett függő funkcióhoz kapcsolódik.

**Javítás:** Kerülje a CTP-számításokat, amikor a Tervezési optimalizálás engedélyezve van, amíg elérhetővé nem válik a CTP-támogatás.

## <a name="additional-resources"></a>További erőforrások

[Tervezési optimalizálás kezdő lépései](get-started.md)

[Tervezési optimalizálás igazítási elemzése](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]