---
title: Párhuzamos tevékenységek beállítása munkafolyamatban
description: A párhuzamos tevékenység beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8043e2854ccc8db0128969ffe36a5517a12c37ac
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693354"
---
# <a name="configure-parallel-activities-in-a-workflow"></a>Párhuzamos tevékenységek beállítása munkafolyamatban

[!include [banner](../includes/banner.md)]

A párhuzamos tevékenység beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben.

A párhuzamos tevékenység egy időben futó munkafolyamatágakból áll.

## <a name="name-a-parallel-activity"></a>Párhuzamos tevékenység elnevezése

A következő lépések segítségével elnevezheti a párhuzamos tevékenységet.

1. Kattintson a jobb gombbal a párhuzamos tevékenységre, majd kattintson a **Tulajdonságok** lehetőségre a **Tulajdonságok** űrlap megnyitásához.
2. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
3. Adja meg a párhuzamos tevékenység egyedi nevét a **Név** mezőben.
4. Kattintson a **Bezárás** gombra.

## <a name="configure-the-branches-of-a-parallel-activity"></a>A párhuzamos tevékenység ágainak konfigurálása

Végezze el a következő lépéseket a párhuzamos tevékenység ágainak hozzáadása és konfigurálása érdekében.

1. Kattintson duplán a párhuzamos tevékenységre a párhuzamos tevékenység ágainak megjelenítése érdekében.
2. Ág hozzáadásához húzza az **Ág** elemet a **Munkafolyamat-elemek** területről a vászon egyik beillesztési pontjára. Az alábbi ábrán egy beillesztési pont látható.

    ![Beillesztési pont](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > Az ágának sorrendje nem számít, mivel a párhuzamos tevékenység ágai egyszerre futnak.

3. Az egyes ágak konfigurálása: [Párhuzamos ágak konfigurálása munkafolyamatban](configure-parallel-branch-workflow.md).
