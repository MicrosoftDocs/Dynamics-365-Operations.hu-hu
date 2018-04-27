--- 
title: "Társtermékek anyagfelhasználási tervének létrehozása"
description: "A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-material-plan-for-co-products"></a>Társtermékek anyagfelhasználási tervének létrehozása

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

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
1. Kattintson az Alaptervezés parancsra.
2. A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Példa: MasterPlan  
4. Kattintson a Futtatás elemre.
5. Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.
6. Kattintson a Szűrő parancsra.
7. A listából válassza ki a Mező = Cikkszám sort.
8. Érték beírása a Feltétel mezőbe.
    * Példa: P6003  
9. Kattintson az OK gombra.
10. Kattintson az OK gombra.
11. Kattintson a Tervezett rendelések elemre.
12. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a Cikkszám mezővel a „P6000” értéket beírva.
    * Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.  
13. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a szűrő által visszaadott sorok egyikét.  
14. A listában kattintson a kijelölt sorban lévő hivatkozásra.
15. Bontsa ki vagy csukja össze az Igénykövetés szakaszt.
16. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.  
17. Zárja be a lapot.


