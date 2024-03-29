---
title: Munkafolyamatok létrehozása – áttekintés
description: Ez a cikk bemutatja a munkafolyamatok létrehozásához szükséges műveleteket.
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "195583"
- intro-internal
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: 1343061ba06d13e68a98b05c013867af0a4d07a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864486"
---
# <a name="create-workflows-overview"></a>Munkafolyamatok létrehozása – áttekintés

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Ez a cikk bemutatja a munkafolyamatok létrehozásához szükséges műveleteket.

## <a name="open-the-workflow-editor"></a>A munkafolyamat-szerkesztő megnyitása

A modul, amelyben éppen dolgozik, meghatározza a létrehozható munkafolyamatokok típusát. Ezekkel a lépésekkel válassza ki a létrehozni kívánt munkafolyamat-típust, és nyissa meg a munkafolyamat-szerkesztőt.

1. Nyissa meg a modult, amelyhez új munkafolyamatot szeretne létrehozni. Például egy beszerzési igénylés munkafolyamatának létrehozásához kattintson a **Beszerzés és forrás** lehetőségre.
2. Kattintson a **Beállítás** &gt; **\[Modulnév\]-munkafolyamatok** elemre.
3. A megjelenő listaoldalon a műveleti ablaktáblán kattintson az **Új** lehetőségre.
4. A **Munkafolyamat létrehozása** oldalon válassza ki a létrehozandó munkafolyamatot, majd kattintson a **Munkafolyamat létrehozása** pontra. A munkafolyamat-szerkesztő megjelenik. A következő eljárásokkal lehet a munkafolyamatot megtervezni.

## <a name="drag-workflow-elements-onto-the-canvas"></a>Munkafolyamat-elemek áthúzása a vászonra

**A munkafolyamat elemei** terület tartalmazza a munkafolyamathoz hozzáadható elemeket. A munkafolyamat elemeinek hozzáadásához húzza azokat a vászonra.

## <a name="connect-the-elements"></a>Az elemek összekapcsolása

A munkafolyamat két elemének összekötéséhez tartsa az egérmutatót az egyik elem fölött, amíg a csatlakozási pontok meg nem jelennek. Kattintson az egyik csatlakozási pontra, és húzza a másik elemhez. Ügyeljen arra, hogy minden elemet összekössön.

## <a name="configure-the-properties-of-the-workflow"></a>A munkafolyamat tulajdonságainak beállítása

Az alábbi lépések segítségével állítsa be a munkafolyamat tulajdonságait.

1. Kattintson a vászonra, és győződjön meg arról, hogy nincs munkafolyamat-elem kiválasztva.
2. Kattintson a **Tulajdonságok** lehetőségre a **Tulajdonságok** lap megnyitásához az adott munkafolyamatra vonatkozóan.
3. Hajtsa végre az eljárásokat a Munkafolyamat-tulajdonságok [konfigurálása cikkében](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>A munkafolyamat elemeinek beállítása

Konfigurálja a vászonra áthúzott elemeket. Ha további tudnivalókat szeretne az egyes munkafolyamat-elemek beállításáról, tekintse át az alábbi témaköröket:

- [Manuális feladatok konfigurálása munkafolyamatban](configure-manual-task-workflow.md)
- [Automatizált feladatok konfigurálása munkafolyamatban](configure-automated-task-workflow.md)
- [Jóváhagyási folyamatok konfigurálása munkafolyamatban](configure-approval-process-workflow.md)
- [Jóváhagyási lépések konfigurálása munkafolyamatban](configure-approval-step-workflow.md)
- [Manuális döntések konfigurálása munkafolyamatban](configure-manual-decision-workflow.md)
- [Feltételes döntések konfigurálása munkafolyamatban](configure-conditional-decision-workflow.md)
- [Párhuzamos ágak konfigurálása munkafolyamatban](configure-parallel-activity-workflow.md)
- [Párhuzamos ág konfigurálása](configure-parallel-branch-workflow.md)
- [Sortétel munkafolyamatainak konfigurálása](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Hibák vagy figyelmeztetések feloldása

A **Hibák és figyelmeztetések** ablaktáblán a munkafolyamat-szerkesztő alján a munkafolyamathoz generált üzenetek jelennek meg. A hibaüzenettel vagy figyelmeztetéssel érintett elem megkereséséhez kattintson duplán a hibára vagy a figyelmeztetésre. Az összes hibát és figyelmeztetést fel kell oldania, mielőtt aktiválhatja a munkafolyamatot.

## <a name="save-and-activate-the-workflow"></a>A munkafolyamat mentése és aktiválása

Ha készen áll a munkafolyamat mentésére és aktiválására, kövesse az alábbi lépéseket.

1. Kattintson a **Mentés és bezárás** gombra a munkafolyamat-szerkesztő bezárásához, és a **Munkafolyamat mentése** lap megnyitásához.
2. Írja be a munkafolyamat változtatásaihoz kapcsolódó megjegyzéseket, majd kattintson az **OK** gombra.
3. Ha az összes hibát és figyelmeztetést feloldotta, megjelenik a **Munkafolyamat aktiválása** lap. Válasszon a következő lehetőségek közül:

    - A munkafolyamat aktuális verziójának aktiválásához kattintson az **Új verzió aktiválása** lehetőségre. Ha egy munkafolyamat aktív, akkor a felhasználók dokumentumokat küldhetnek feldolgozásra.
    - Ha nem szeretné aktiválni ezt a verziót, kattintson a **Ne aktiválja az új verziót** lehetőségre. A munkafolyamatot később is aktiválhatja.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]