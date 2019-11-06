---
title: Párhuzamos tevékenységek beállítása munkafolyamatban
description: A párhuzamos tevékenység beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11b541c3e159b2c38e4dd2fa9f2ad08e4c1e4500
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178188"
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

3. Az egyes ágak konfigurálásához lásd: [Párhuzamos ág beállítása](configure-parallel-branch-workflow.md).