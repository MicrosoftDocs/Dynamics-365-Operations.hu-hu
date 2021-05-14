---
title: Társtermékek anyagfelhasználási tervének létrehozása
description: A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b51e4b4d00da2babb5128d8c4c22139b0c1853d4
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920729"
---
# <a name="create-a-material-plan-for-co-products"></a>Társtermékek anyagfelhasználási tervének létrehozása

[!include [banner](../../includes/banner.md)]

A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek. Ez az eljárás az USP2 bemutatócéget használja.

## <a name="create-requirement-for-a-co-product"></a>Társtermék szükségletének létrehozása

1. Ugrás az **Értékesítés és marketing \> Munkaterületek \> Értékesítési rendelés feldolgozása és lekérdezése** elemre.
1. Válassza az **Új** lehetőséget.
1. Válassza ki az **Értékesítési rendelés** lehetőséget.
1. Írjon be egy értéket a **Vevői számla** mezőbe.
    * Példa: US-001  
1. Válassza ki az **OK** lehetőséget.
1. A **Cikkszám** mezőbe írjon egy értéket.
    * Példa: P6003  
1. Adjon meg egy számot a **Mennyiség** mezőben.
    * Példa: 50000  
1. Válassza a **Mentés** lehetőséget.

## <a name="create-a-material-plan-for-co-products"></a>Társtermékek anyagfelhasználási tervének létrehozása

1. Zárja be a lapot.
1. Zárja be a lapot.
1. Válassza a **Alaptervezés** lehetőséget.
1. A **Konstrukció** mezőben válassza a legördítő nyilat a keresőlista megnyitásához.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
    * Példa: MasterPlan  
1. Válassza a **Futtatás** parancsot.
1. Bontsa ki vagy csukja össze a **Belefoglalandó rekordok** részt.
1. Válassza ki a **Szűrő** elemet.
1. A listából válassza ki a **Mező** = *Cikkszám* sort.
1. Adjon meg egy értéket a **Feltétel** mezőben.
    * Példa: P6003  
1. Válassza ki az **OK** lehetőséget.
1. Válassza ki az **OK** lehetőséget.
1. **Tervezett rendelések** kiválasztása.
1. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a **Cikkszám** mezővel a „P6000” értéket beírva.
    * Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.  
1. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a szűrő által visszaadott sorok egyikét.  
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. Bontsa ki a **Igénykövetés** szakaszt.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
    * A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.  
1. Zárja be a lapot.

## <a name="create-a-second-requirement-for-a-co-product"></a>Társtermék második követelményének létrehozása

1. Ugrás az **Értékesítés és marketing \> Munkaterületek \> Értékesítési rendelés feldolgozása és lekérdezése** elemre.
1. Válassza az **Új** lehetőséget.
1. Válassza ki az **Értékesítési rendelés** lehetőséget.
1. Írjon be egy értéket a **Vevői számla** mezőbe.
    * Példa: US-001  
1. Válassza ki az **OK** lehetőséget.
1. A **Cikkszám** mezőbe írjon egy értéket.
    * Példa: P6003  
1. Adjon meg egy számot a **Mennyiség** mezőben.
    * Példa: 50000  
1. Válassza a **Mentés** lehetőséget.

## <a name="create-a-second-material-plan-for-co-products"></a>Társtermékek második anyagfelhasználási tervének létrehozása

1. A **Konstrukció** mezőben válassza a legördítő nyilat a keresőlista megnyitásához.
2. A listában válassza ki a kiválasztott sorból a hivatkozást.
    * Példa: MasterPlan  
3. Válassza a **Futtatás** parancsot.
4. Bontsa ki vagy csukja össze a **Belefoglalandó rekordok** részt.
5. Válassza ki a **Szűrő** elemet.
6. A listából válassza ki a **Mező** = *Cikkszám* sort.
7. Adjon meg egy értéket a *Feltétel* mezőben.
    * Példa: P6003  
8. Válassza ki az **OK** lehetőséget.
9. Válassza ki az **OK** lehetőséget.
10. **Tervezett rendelések** kiválasztása.
11. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a **Cikkszám** mezővel a „P6000” értéket beírva.
    * Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.  
12. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a szűrő által visszaadott sorok egyikét.  
13. A listában válassza ki a kiválasztott sorból a hivatkozást.
14. Bontsa ki vagy csukja össze az **Igénykövetés** szakaszt.
15. A listában válassza ki a kiválasztott sorból a hivatkozást.
    * A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.  
16. Zárja be a lapot.
17. Válassza a **Alaptervezés** lehetőséget.
18. Ugorjon az **Alaptervezés \> Beállítás \> Alaptervezés paraméterei** pontra.
19. Válassza a *Nem* lehetőséget **Az összes tervezési folyamat letiltása** mezőben.
20. Zárja be a lapot.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]