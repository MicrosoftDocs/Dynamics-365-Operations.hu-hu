---
title: Könyvelési sémák létrehozása
description: Ez az útmutató bemutatja a könyvelési séma létrehozásának folyamatát.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ce96ccfb0dc3e4a723af967147dae93772c5b44f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553131"
---
# <a name="create-accrual-schemes"></a>Könyvelési sémák létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az útmutató bemutatja a könyvelési séma létrehozásának folyamatát. Ez a feladat az USMF bemutatócéget használja.

1. Ugorjon a Főkönyv > Naplóbeállítások > Könyvelési sémák pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Könyvelés azonosítója mezőbe.
4. A Könyvelési séma leírása mezőbe írja be az érték leírását.
5. A Levonás mezőben adja meg a kívánt értékeket.
    * A megadott fő számla felülírja a tartozási fő számlát a naplóbizonylat sorában, és ezt használja majd a rendszer a halasztás sztornírozásához is, a főkönyvi könyvelési tranzakciókon alapján.  
6. A Jóváírás mezőben adja meg a kívánt értékeket.
    * A megadott fő számla felülírja a jóváírási fő számlát a naplóbizonylat sorában, és ezt használja majd a rendszer a halasztás sztornírozásához is, a főkönyvi könyvelési tranzakciókon alapján.  
7. A Bizonylat mezőben válassza ki, hogyan szeretné a bizonylatot meghatározni a tranzakcióinak feladása során.
8. A Leírás mezőben adja meg a feladandó tranzakciók leírásához az értéket.
9. Az Időszak gyakorisága mezőben válassza ki, milyen gyakran történjenek a tranzakciók.
10. Adjon meg egy számot az Előfordulások száma időszak szerint mezőben.
11. A Tranzakciók feladása mezőben válassza ki, hogy mikor szeretné a tranzakciókat feladni, például a Havi értéket.

