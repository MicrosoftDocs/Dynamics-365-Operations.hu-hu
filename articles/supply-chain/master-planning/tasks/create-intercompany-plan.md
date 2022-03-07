---
title: Vállalatközi terv létrehozása
description: Ez az eljárás bemutatja, hogyan lehet létrehozni egy vállalatközi tervet.
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ef1484e6925427454f819a5effdc911f762b48b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578272"
---
# <a name="create-an-intercompany-plan"></a>Vállalatközi terv létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet létrehozni egy vállalatközi tervet. Ez az eljárás az USMF bemutatócéget használja.

## <a name="set-up-an-intercompany-planning-group"></a>Vállalatközi tervezőcsoport beállítása

1. A **Navigációs ablaktáblán** lépjen a **Modulok > Alaptervezés > Beállítás > Vállalatközi tervezőcsoportok** elemre.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrjön a Név mezőben a „10” érték megadásával.
3. A listában jelölje meg a kiválasztott sort.
4. Válassza a **Törlés** lehetőséget. Ez a lépés szükséges a vállalatközi tervezési futtatás lerövidítéséhez.   A vállalatközi tervezés az tervezési csoport összes vállalatára lefuttatja az alaptervezést, a legalacsonyabb ütemezési sorrendtől kezdve.  
5. Válassza ki az **Igen** lehetőséget.
6. Zárja be a lapot.

## <a name="create-an-intercompany-master-plan"></a>Vállalatközi alapterv létrehozása

1. A **Navigációs ablaktáblán** lépjen a **Modulok > Alaptervezés > Munkaterületek > Alaptervezés** elemre.
2. Válassza a **Vállalatközi alaptervezés** lehetőséget.  
3. A **Vállalatközi tervezőcsoport** mezőben válassza a legördítő nyilat a keresőlista megnyitásához.
4. A listában válassza ki a kiválasztott sorból a hivatkozást. Válassza ki a 10. vállalatközi tervezőcsoportot.  
5. A **Vállalatközi tervezési ismétlések száma** mezőbe írja be a „2” értéket. A 10. vállalatközi tervezőcsoportnak két tagja van. Annak érdekében, hogy propagálja a késedelmeket a forrásvállalattól (USMF) a vevő vállalathoz (DEMF), a vállalatközi két alkalommal kell lefuttatni, mindkét vállalatnál. Az első iteráció propagálja az igényt és azonosítja a késedelmeket a forrásvállalatnál (USMF). A második iterációs propagálja a késedelmeket a USMF és a DEMF között.  
6. Az **Első ismétlés** mezőben válassza az „Újbóli létrehozás” lehetőséget.
7. A **További ismétlések** mezőben válassza az „Újbóli létrehozás” lehetőséget.
8. Adjon meg egy számot a **Szálak száma** mezőben. Ez a párhuzamos tervezésre használt szálak számát jelenti.  
9. Válassza ki az **OK** lehetőséget.

## <a name="view-the-result-of-the-plan"></a>A terv eredményének megtekintése

1. A **Konstrukció** mezőben válassza a legördítő nyilat a keresőlista megnyitásához.
2. A listában válassza ki a kiválasztott sorból a hivatkozást. Válassza a StaticPlan hivatkozást. A USMF vállalatban kell lennie.  
3. **Tervezett rendelések** kiválasztása.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]