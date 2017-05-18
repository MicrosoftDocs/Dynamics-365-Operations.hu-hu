---
title: "Párhuzamos tevékenység beállítása munkafolyamatban"
description: "A párhuzamos tevékenység beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: ce3fca9d2dbca046232365b1375bfd920d5b10fd
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="configure-a-parallel-activity-in-a-workflow"></a>Párhuzamos tevékenység beállítása munkafolyamatban

[!include[banner](../includes/banner.md)]


A párhuzamos tevékenység beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben.

A párhuzamos tevékenység egy időben futó munkafolyamatágakból áll.

## <a name="name-a-parallel-activity"></a>Párhuzamos tevékenység elnevezése
A következő lépések segítségével elnevezheti a párhuzamos tevékenységet.
1.  Kattintson a jobb gombbal a párhuzamos tevékenységre, majd kattintson a **Tulajdonságok** lehetőségre a **Tulajdonságok** űrlap megnyitásához.
2.  A bal oldali panelen kattintson az **Alapbeállítások** gombra.
3.  Adja meg a párhuzamos tevékenység egyedi nevét a **Név** mezőben.
4.  Kattintson a **Bezárás** gombra.

## <a name="configure-the-branches-of-a-parallel-activity"></a>A párhuzamos tevékenység ágainak konfigurálása
Végezze el a következő lépéseket a párhuzamos tevékenység ágainak hozzáadása és konfigurálása érdekében.
1.  Kattintson duplán a párhuzamos tevékenységre a párhuzamos tevékenység ágainak megjelenítése érdekében.
2.  Ág hozzáadásához húzza az **Ág** elemet a **Munkafolyamat-elemek** területről a vászon egyik beillesztési pontjára. Az alábbi ábrán egy beillesztési pont látható.![Beillesztési pont](./media/workflow_insertionpoint.gif)
    | **Megjegyzés**                                                                                                         |
    |------------------------------------------------------------------------------------------------------------------|
    | Az ágának sorrendje nem számít, mivel a párhuzamos tevékenység ágai egyszerre futnak. |

3.  Az egyes ágak konfigurálásához lásd: [Párhuzamos ág beállítása](configure-parallel-branch-workflow.md).






