---
title: Munkaidősablonok készítése
description: A munkaidősablonok határozzák meg az egész hét munkaóráit, és ezek segítségével hozhatók létre munkaidők egy adott időszakra.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ef913777c8e2aa14af21e28ed56362e31b3d70a1a52e988a90ad94f59b77b70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741261"
---
# <a name="create-working-time-templates"></a>Munkaidősablonok készítése

[!include [banner](../../includes/banner.md)]

A munkaidősablonok határozzák meg az egész hét munkaóráit, és ezek segítségével hozhatók létre munkaidők egy adott időszakra. Ez az eljárás bemutatja, hogyan definiálhat munkaidősablonokat a munkaidő-ütemezési tulajdonságok segítségével a munkaidő-intervallumok kategorizálásához. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.

1. Ugorjon a **Munkaterületek > Erőforrás életciklusa kezelése** elemre.
1. Válassza a **Munkaidősablonok** lehetőséget.

## <a name="create-working-time-template"></a>Munkaidősablon létrehozása

1. Válassza az **Új** lehetőséget.
1. Írjon be egy értéket a **Munkidősablon** mezőbe.
1. Írjon be egy értéket a **Név** mezőbe.
1. Bontsa ki a **Hétfő** szakaszt.
1. Válassza a **Hozzáadás** lehetőséget.
1. A **Kezdés** mezőben adjon meg egy időpontot.
    * Adja meg az időt, amikor a munka reggel elkezdődik.  
1. A **Befejezés** mezőben adjon meg egy időpontot.
    * Adja meg a dolgozók ebédszünetének időpontját.  
1. Válassza a **Hozzáadás** lehetőséget.
1. A **Kezdés** mezőben adjon meg egy időpontot.
    * Adja meg, hogy mikor folytatódik a munka ebéd után.  
1. A **Befejezés** mezőben adjon meg egy időpontot.
    * A munkanap végének meghatározása.  

## <a name="replicate-working-times-to-all-week-days"></a>Munkaidők átmásolása minden hétköznapra

1. Válassza a **Másolási nap** parancsot.
    * Másolja át a munkaidők definícióit hétfőről keddre.  
1. Válassza ki az **OK** lehetőséget.
1. Válassza a **Másolási nap** parancsot.
    * Másolja át a munkaidők definícióit hétfőről szerdára.  
1. Válasszon egy lehetőséget a **Befejező hétköznap** mezőben.
1. Válassza ki az **OK** lehetőséget.
1. Válassza a **Másolási nap** parancsot.
    * Másolja át a munkaidők definícióit hétfőről csütörtökre.  
1. Válasszon egy lehetőséget a **Befejező hétköznap** mezőben.
1. Válassza ki az **OK** lehetőséget.
1. Válassza a **Másolási nap** parancsot.
    * Másolja át a munkaidők definícióit hétfőről péntekre.  
1. Válasszon egy lehetőséget a **Befejező hétköznap** mezőben.
1. Válassza ki az **OK** lehetőséget.

## <a name="define-time-slots-for-special-operations"></a>Időközök meghatározása speciális műveletekhez

1. Bontsa ki a **Péntek** szakaszt.
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
1. A **Tulajdonság** mezőben adjon meg vagy válasszon ki egy értéket.
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
1. A **Tulajdonság** mezőben adjon meg vagy válasszon ki egy értéket.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Hétvégek megjelölése zárt felvételhez

1. Bontsa ki a **Szombat** szakaszt.
1. A *Lezárt felvétel* mezőben válassza az **Igen** lehetőséget.
1. Bontsa ki a **Vasárnap** szakaszt.
1. A *Lezárt felvétel* mezőben válassza az **Igen** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]