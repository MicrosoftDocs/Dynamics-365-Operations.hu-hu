--- 
title: "Alvállalkozói munkacella létrehozása a lean manufacturing szolgáltatáshoz"
description: "A lean manufacturing feladatokhoz alvállalkozásba adott munka modellezése érdekében létre kell hoznia egy olyan munkacellát, amely a munkát nyújtó szállítóhoz van társítva."
author: cvocph
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fc8dc0bc29c6bdb662c46808491abf5395f0be5d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a>Alvállalkozói munkacella létrehozása a lean manufacturing szolgáltatáshoz

[!include[task guide banner](../../includes/task-guide-banner.md)]

A lean manufacturing feladatokhoz alvállalkozásba adott munka modellezése érdekében létre kell hoznia egy olyan munkacellát, amely a munkát nyújtó szállítóhoz van társítva. Az alvállalkozói munkacella a szállítóhoz a Szállító típusa erőforrásának társításán keresztül kapcsolódik. Ha ezt a felvételt lejátssza az USMF bemutató vállalat esetében, kiválaszthatja az 1002-es azonosítóval és az 1-es hellyes rendelkező szállítói számlát.


## <a name="create-a-vendor-resource"></a>Szállítói erőforrás létrehozása
1. Ugrás az Erőforrások parancsra.
2. Kattintson az Új lehetőségre.
3. Érték beírása az Erőforrás mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Válassza a Szállító lehetőséget a Típus mezőben.
6. A Szállító mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.

## <a name="create-the-resource-group"></a>Erőforráscsoport létrehozása
1. Ugrás az erőforráscsoportokra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket az Erőforráscsoport mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Válassza ki azt a helyet, amelyhez a munkacellát kell hozzárendelni. Elméletben a hely a szállító által üzemeltetett egyetlen hely is lehet. Azonban a legtöbb esetben a rendszer csak hozzárendeli az alvállalkozói erőforrásokat ahhoz a helyhez, amely megrendeli az alvállalkozói munkát. Vegye figyelembe, hogy az alvállalkozói munkacellák bemeneti és kimeneti raktárainak ugyanazon a helyen kell lenniük.  
6. Érték beírása a Telephely mezőbe.
7. @SysTaskRecorder:_RequestClose
8. Jelölje be a Munkacella jelölőnégyzetet, vagy törölje a jelet.
9. A Bemenő raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Válassza ki azt a raktárt és helyet, amelyet a szállító által kezelt munkacellaanyagok előkészítéséhez használ. A legtöbb esetben a rendszer a raktárt és a helyet szállítónként egy külön raktár és munkacellánként egy hely segítségével modellezi.  
10. A Bemeneti hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
11. A Kimenő raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Határozza meg azt a raktárt és helyet, ahol az anyagot feladták a munkacella alvállalkozói tevékenységeinek feladásakor. A raktár és a hely a szállító helyén is lehet, ha a szállító jelenti a kanbanfeladatokat. Másik lehetőségként a raktár és a hely a termelési folyamat következő lépéséhez társított fogadó hely is lehet.  
12. A Kimeneti hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
13. Bontsa ki vagy csukja össze a Naptárak szakaszt.
14. Kattintson a Hozzáadás gombra.
15. A Naptár mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
    * Társítsa a munkacella munkanaptárát az erőforráscsoporttal. Kritikus erőforrások esetén javasoljuk, hogy a pontos munkaidőt és a munkacella vagy a szállító helyének kapcsolódó kapacitásait megjelenítő konkrét naptárakat határozzon meg.  
16. Bontsa ki vagy csukja össze az Erőforrások szakaszt.
17. Kattintson a Hozzáadás gombra.
    * Az alvállalkozói erőforráscsoportnak rendelkeznie kell a Szállító típusa társított erőforrásával, amely összeköti az erőforráscsoportot a szállítói számlával.  
18. Az Erőforrás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Válassza ki vagy írja be az előző alfeladatban létrehozott szállítói erőforrást.  
19. Bontsa ki vagy csukja össze a Munkacella-kapacitás adatok szakaszt.
20. Kattintson a Hozzáadás gombra.
    * A munkacellának meghatározott kapacitással kell rendelkeznie. Ebben a példában a termelési kapacitás egy szokásos munkanapon 100 munkadarab.  
21. A Termelési folyamatmodell mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
22. Válassza ki valamelyik lehetőséget az Kapacitásidőszak mezőben.
23. Írjon be egy számot az Átlagos teljesítmény mezőbe.
24. Az Egység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
25. ResolveChanges az Egység.


