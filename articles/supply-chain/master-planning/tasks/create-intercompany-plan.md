---
title: Vállalatközi terv létrehozása
description: Ez az eljárás bemutatja, hogyan lehet létrehozni egy vállalatközi tervet.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 194bb78eed5a673030f7cead031cf286cddbe77c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845209"
---
# <a name="create-an-intercompany-plan"></a>Vállalatközi terv létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet létrehozni egy vállalatközi tervet. Ez az eljárás az USMF bemutatócéget használja.


## <a name="set-up-an-intercompany-planning-group"></a>Vállalatközi tervezőcsoport beállítása 
1. Menjen a Vállalatközi tervezőcsoportokhoz.
    * Alaptervezés > Beállítás > Vállalatközi tervezőcsoportok  
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrjön a Név mezőben a „10” érték megadásával.
3. A listában jelölje meg a kiválasztott sort.
4. Kattintson a Törlés gombra.
    * Ez a lépés szükséges a vállalatközi tervezési futtatás lerövidítéséhez.   A vállalatközi tervezés az tervezési csoport összes vállalatára lefuttatja az alaptervezést, a legalacsonyabb ütemezési sorrendtől kezdve.  
5. Kattintson az Igen gombra.
6. Zárja be a lapot.

## <a name="create-an-intercompany-plan"></a>Vállalatközi terv létrehozása
1. Kattintson a Vállalatközi alaptervezés lehetőségre.
    * Ez az Alaptervezés munkaterületen található.  
2. A Vállalatközi tervezőcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válassza ki a 10. vállalatközi tervezőcsoportot.  
4. A Vállalatközi tervezési ismétlések száma mezőbe írja be a „2” értéket.
    * A 10. vállalatközi tervezőcsoportnak két tagja van. Annak érdekében, hogy propagálja a késedelmeket a forrásvállalattól (USMF) a vevő vállalathoz (DEMF), a vállalatközi két alkalommal kell lefuttatni, mindkét vállalatnál. Az első iteráció propagálja az igényt és azonosítja a késedelmeket a forrásvállalatnál (USMF). A második iterációs propagálja a késedelmeket a USMF és a DEMF között.  
5. Az Első ismétlés mezőben válasszon egy lehetőséget.
6. Az Első ismétlés mezőben válassza az „Újbóli létrehozás” lehetőséget.
7. A További ismétlések mezőben válassza az „Újbóli létrehozás” lehetőséget.
8. Adjon meg egy számot a Szálak száma mezőben.
    * Ez a párhuzamos tervezésre használt szálak számát jelenti.  
9. Kattintson az OK gombra.

## <a name="view-the-result-of-the-plan"></a>A terv eredményének megtekintése
1. A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Kattintson a StaticPlan hivatkozására. A USMF vállalatban kell lennie.  
3. Kattintson a Tervezett rendelések elemre.

