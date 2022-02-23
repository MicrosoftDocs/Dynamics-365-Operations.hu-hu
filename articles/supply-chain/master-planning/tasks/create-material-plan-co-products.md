---
title: Társtermékek anyagfelhasználási tervének létrehozása
description: A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14de9a1085ac1cae88ad93c35385dd43c60ed4d1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429538"
---
# <a name="create-a-material-plan-for-co-products"></a>Társtermékek anyagfelhasználási tervének létrehozása

[!include [banner](../../includes/banner.md)]

A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek. Ez az eljárás az USP2 bemutatócéget használja.


## <a name="create-requirement-for-a-co-product"></a>Társtermék szükségletének létrehozása
1. Ugrás az Alapértelmezett irányítópultra.
2. Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.
3. Kattintson az Új elemre.
4. Kattintson az Értékesítési rendelés gombra.
5. Írjon be egy értéket a Vevői számla mezőbe.
    * Példa: US-001  
6. Kattintson az OK gombra.
7. A cikkmezőbe írjon egy értéket.
    * Példa: P6003  
8. Adjon meg egy számot a Mennyiség mezőben.
    * Példa: 50000  
9. Kattintson a Mentés gombra.

## <a name="create-a-material-plan-for-co-products"></a>Társtermékek anyagfelhasználási tervének létrehozása
1. Zárja be a lapot.
2. Zárja be a lapot.
3. Kattintson az Alaptervezés parancsra.
4. A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Példa: MasterPlan  
6. Kattintson a Futtatás elemre.
7. Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.
8. Kattintson a Szűrő parancsra.
9. A listából válassza ki a Mező = Cikkszám sort.
10. Érték beírása a Feltétel mezőbe.
    * Példa: P6003  
11. Kattintson az OK gombra.
12. Kattintson az OK gombra.
13. Kattintson a Tervezett rendelések elemre.
14. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a Cikkszám mezővel a „P6000” értéket beírva.
    * Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.  
15. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a szűrő által visszaadott sorok egyikét.  
16. A listában kattintson a kijelölt sorban lévő hivatkozásra.
17. Bontsa ki vagy csukja össze az Igénykövetés szakaszt.
18. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.  
19. Zárja be a lapot.

## <a name="create-requirement-for-a-co-product"></a>Társtermék szükségletének létrehozása
1. Ugrás az Alapértelmezett irányítópultra.
2. Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.
3. Kattintson az Új elemre.
4. Kattintson az Értékesítési rendelés gombra.
5. Írjon be egy értéket a Vevői számla mezőbe.
    * Példa: US-001  
6. Kattintson az OK gombra.
7. A cikkmezőbe írjon egy értéket.
    * Példa: P6003  
8. Adjon meg egy számot a Mennyiség mezőben.
    * Példa: 50000  
9. Kattintson a Mentés gombra.

## <a name="create-a-material-plan-for-co-products"></a>Társtermékek anyagfelhasználási tervének létrehozása
1. A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Példa: MasterPlan  
3. Kattintson a Futtatás elemre.
4. Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.
5. Kattintson a Szűrő parancsra.
6. A listából válassza ki a Mező = Cikkszám sort.
7. Érték beírása a Feltétel mezőbe.
    * Példa: P6003  
8. Kattintson az OK gombra.
9. Kattintson az OK gombra.
10. Kattintson a Tervezett rendelések elemre.
11. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a Cikkszám mezővel a „P6000” értéket beírva.
    * Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.  
12. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a szűrő által visszaadott sorok egyikét.  
13. A listában kattintson a kijelölt sorban lévő hivatkozásra.
14. Bontsa ki vagy csukja össze az Igénykövetés szakaszt.
15. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.  
16. Zárja be a lapot.
17. Kattintson az Alaptervezés parancsra.
18. Ugorjon az Alaptervezés > Beállítás > Alaptervezés paraméterei pontra.
19. Válassza a Nem lehetőséget Az összes tervezési folyamat letiltása mezőben.
20. Zárja be a lapot.

