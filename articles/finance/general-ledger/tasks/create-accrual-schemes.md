---
title: Elhatárolási sémák létrehozása
description: Ez a témakör bemutatja, hogyan kell könyvelési sémát létrehozni.
author: aprilolson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41ea75b5c54f43efd4d5b9ef194e6394fc50bccc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815140"
---
# <a name="create-accrual-schemes"></a>Elhatárolási sémák létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan kell könyvelési sémát létrehozni. Ez a feladat az USMF bemutatócéget használja.

1. Nyissa meg a **Navigációs ablak > Modulok > Főkönyv > Napló beállítása > Könyvelési sémák** elemet.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Könyvelés azonosítója** mezőbe.
4. A **Könyvelési séma leírása** mezőbe írja be az érték leírását.
5. A **Levonás** mezőben adja meg a kívánt értékeket. A megadott fő számla felülírja a tartozási fő számlát a naplóbizonylat sorában, és ezt használja majd a rendszer a halasztás sztornírozásához is, a főkönyvi könyvelési tranzakciókon alapján.  
6. A **Jóváírás** mezőben adja meg a kívánt értékeket. A megadott fő számla felülírja a jóváírási fő számlát a naplóbizonylat sorában, és ezt használja majd a rendszer a halasztás sztornírozásához is, a főkönyvi könyvelési tranzakciókon alapján.  
7. A **Bizonylat** mezőben válassza ki, hogyan szeretné a bizonylatot meghatározni a tranzakcióinak feladása során.
8. A **Leírás** mezőben adja meg a feladandó tranzakciók leírásához az értéket.
9. Az **Időszak gyakorisága** mezőben válassza ki, milyen gyakran történjenek a tranzakciók.
10. Adjon meg egy számot az **Előfordulások száma időszak szerint** mezőben.
11. A **Tranzakciók feladása** mezőben válassza ki, hogy mikor szeretné a tranzakciókat feladni, például a **Havi** értéket.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]