---
title: Munkafolyamatok létrehozása – áttekintés
description: Ez a témakör a munkafolyamat létrehozásának lépéseit mutatja be.
author: sericks007
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: 2168b33c8495eab61ec0c8262b042cd16420031c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190097"
---
# <a name="create-workflows-overview"></a>Munkafolyamatok létrehozása – áttekintés

[!include [banner](../includes/banner.md)]

Ez a témakör a munkafolyamat létrehozásának lépéseit mutatja be.

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
3. Kövesse [A munkafolyamat elemeinek beállítása](configure-workflow-properties.md) pontban leírt eljárásokat.

## <a name="configure-the-elements-of-the-workflow"></a>A munkafolyamat elemeinek beállítása

Konfigurálja a vászonra áthúzott elemeket. Ha további tudnivalókat szeretne az egyes munkafolyamat-elemek beállításáról, tekintse át az alábbi témaköröket:

- [Manuális feladat konfigurálása](configure-manual-task-workflow.md)
- [Automatizált feladat konfigurálása](configure-automated-task-workflow.md)
- [Jóváhagyási folyamat konfigurálása](configure-approval-process-workflow.md)
- [Jóváhagyási lépés konfigurálása](configure-approval-step-workflow.md)
- [Manuális döntés konfigurálása](configure-manual-decision-workflow.md)
- [Feltételes döntés konfigurálása](configure-conditional-decision-workflow.md)
- [Párhuzamos tevékenység konfigurálása](configure-parallel-activity-workflow.md)
- [Párhuzamos ág beállítása](configure-parallel-branch-workflow.md)
- [Sortétel munkafolyamatának beállítása](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Hibák vagy figyelmeztetések feloldása

A **Hibák és figyelmeztetések** ablaktáblán a munkafolyamat-szerkesztő alján a munkafolyamathoz generált üzenetek jelennek meg. A hibaüzenettel vagy figyelmeztetéssel érintett elem megkereséséhez kattintson duplán a hibára vagy a figyelmeztetésre. Az összes hibát és figyelmeztetést fel kell oldania, mielőtt aktiválhatja a munkafolyamatot.

## <a name="save-and-activate-the-workflow"></a>A munkafolyamat mentése és aktiválása

Ha készen áll a munkafolyamat mentésére és aktiválására, kövesse az alábbi lépéseket.

1. Kattintson a **Mentés és bezárás** gombra a munkafolyamat-szerkesztő bezárásához, és a **Munkafolyamat mentése** lap megnyitásához.
2. Írja be a munkafolyamat változtatásaihoz kapcsolódó megjegyzéseket, majd kattintson az **OK** gombra.
3. Ha az összes hibát és figyelmeztetést feloldotta, megjelenik a **Munkafolyamat aktiválása** lap. Válasszon a következő lehetőségek közül:

    - A munkafolyamat aktuális verziójának aktiválásához kattintson az **Új verzió aktiválása** lehetőségre. Ha egy munkafolyamat aktív, akkor a felhasználók dokumentumokat küldhetnek feldolgozásra.
    - Ha nem szeretné aktiválni ezt a verziót, kattintson a **Ne aktiválja az új verziót** lehetőségre. A munkafolyamatot később is aktiválhatja.