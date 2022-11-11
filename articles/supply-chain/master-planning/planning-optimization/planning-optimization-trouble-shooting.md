---
title: Tervezési optimalizálás hibaelhárítása
description: Ez a témakör azt ismerteti, hogyan lehet kijavítani a tervezési optimalizálás során esetleg felmerülő problémákat.
author: t-benebo
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
ms.author: benebotg
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 37c38ab9cec8ae3c9d4decf8043b43ea2251083e
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739729"
---
# <a name="troubleshoot-planning-optimization"></a>Tervezési optimalizálás hibaelhárítása 

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet kijavítani a tervezési optimalizálás során esetleg felmerülő gyakori problémákat.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>A Tervezési optimalizálás beépülő modul telepítése nem fejeződött be

A Tervezési optimalizálás egy Lifecycle Services (LCS) rendszerrel kompatibilis, 2. vagy magasabb (nem OneBox környezet) szintű, magas rendelkezésre állású környezetet igényel a Dynamics 365 Supply Chain Management 10.0.7-es vagy újabb verziójával. Ha OneBox környezetben próbálja meg telepíteni a bővítményt, a telepítés nem fog befejeződni.

**Javítás**: Szakítsa meg a telepítést, és használjon egy magas rendelkezésre állású, 2. vagy magasabb szintű (nem Onebox) környezetet.

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>A kötegelt feladatok tervezése meghiúsul, amikor a Tervezési optimalizálás engedélyezve van.

Ha engedélyezi a tervezési optimalizálást, a rendszer automatikusan letiltja az elavult alaptervezési motort. Az elavult alaptervezési motorhoz létrehozott alaptervezési kötegelt feladatok sikertelenek lesznek, ha akkor aktiválódnak, amikor engedélyezve van a Tervezési optimalizálás funkció. Egy hibaüzenet jelenik meg, például *Ez a művelet olyan alaptervezést aktivált, amely nem támogatott, ha a Tervezési optimalizálás engedélyezve van*.

**Javítás**: Az elavult alaptervezési motorhoz létrehozott összes alaptervezési kötegelt feladat megszakítása.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>A Tervezési optimalizálás eredményei eltérnek a korábbi eredményektől

Egyes területek esetében a tervezési optimalizálás különbözik az elavult alaptervezési motortervtől. Ez a függő szolgáltatások miatt is történhet.

**Javítás**: Futtassa a Tervezési optimalizálás illeszkedési elemzését, majd elemezze az eredményeket a vonatkozó dokumentációval összevetve, hogy megértsék a hatásait. További tájékoztatás: [Tervezésoptimalizálás illeszkedési elemzése](planning-optimization-fit-analysis.md).

## <a name="cant-enable-planning-optimization"></a>A Tervezési optimalizálás nem engedélyezhető?

A **Kapcsolat állapota** állapotnak **Csatlakoztatva** értékűnek kell lennie ahhoz, hogy a **Tervezési optimalizálás használata** beállításnak az **Igen** értéket adja meg. További tájékoztatás: [Első lépések a Tervezésoptimalizálással](get-started.md).

**Javítás**: Győződjön meg arról, hogy a Tervezési optimalizálás beépülő modul telepítése sikeresen befejeződött.

## <a name="error-message-is-shown-during-ctp"></a>Hibaüzenet jelenik meg a CTP során

Ha megpróbálja futtatni az ígérhető (CTP) elemet egy értékesítési rendelésből, amikor a Tervezési optimalizálás engedélyezve van, akkor a következő hibaüzenet jelenik meg: *A művelet olyan alaptervezést aktivált, amely nem támogatott, ha a Tervezés optimalizálása engedélyezve van*.

Ez a termelési rendelések támogatásának részeként tervezett függő funkcióhoz kapcsolódik.

**Javítás:** Kerülje a CTP-számításokat, amikor a Tervezési optimalizálás engedélyezve van, amíg elérhetővé nem válik a CTP-támogatás.

## <a name="additional-resources"></a>További erőforrások

- [Az alaptervezés első lépések](get-started.md)
- [A Tervezési optimalizálás igazítási elemzése](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]