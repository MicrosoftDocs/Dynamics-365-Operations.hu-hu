---
title: Cikkek fedezeti szabályainak meghatározása
description: Ez az eljárás az USMF bemutatócéget használja.
author: ShylaThompson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 680d7c9339b089a4da82bef18bae3af41e23af30
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845173"
---
# <a name="define-coverage-rules-for-items"></a>Cikkek fedezeti szabályainak meghatározása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás bemutatja, hogyan tud fedezeti szabályokat létrehozni és egy adott cikk fedezeti beállításait felülírni. Azt is bemutatja, hogyan kell megadni az alapértelmezett készletbeállításokat.


## <a name="create-a-coverage-group"></a>Fedezetcsoport létrehozása
1. Nyissa meg a **Navigációs ablak > Modulok > alaptervezés > Beállítások> Fedezeti csoportok** elemet.
2. Kattintson az **Új** elemre.
3. Írjon be egy értéket a **Fedezeti csoport** mezőbe.
4. Írjon be egy értéket a **Név** mezőbe.
5. Írjon be egy értéket a **Naptár** mezőbe. Válassza ki azt a naptárat, amely alapján az ebben a csoportban szereplő cikkek esetében az alaptervezés a feltöltési javaslatokat létrehozza.  
6. A **Fedezet kódja** mezőben válasszon ki egy lehetőséget. Jelölje be az eljáráshoz szükséges „követelményeket”.  
7. A **Fedezet időkorlátja (napok)** mezőben, írja be: '90'. Az ebben a csoportban szereplő cikkek esetében az alaptervezés legfeljebb 90 napos jövőbeni időszakra szóló feltöltési javaslatokat hoz létre.  
8. A **Negatív napok** mezőbe írja be az „1” értéket.
9. A **Pozitív napok** mezőbe írja be az „1” értéket.
10. Bontsa ki vagy zárja be az **Egyéb** szakaszt.
11. A **Biztonsági időtartalék napban** szakaszban a **Követelmény dátumához hozzáadott bevételezési időtartalék** mezőbe írja be az „1” értéket. Ha például a bevételezési különbözet 1 napra van állítva, és a beszerzési rendelési sor május 15-re van bevételezésre ütemezve, az alapütemezés május 16-ra számítja ki a korrigált bevételezési dátumot.  
12. A **Követelmény dátumából levont kiadási időtartalék** mezőbe írja be az „1” értéket. Ha például a kiadási különbözet 1 napra van állítva, és az értékesítési rendelési sor május 15-re van kiszállításra ütemezve, az alapütemezés május 14-re számítja ki a korrigált kiadási dátumot.  
13. Az **Újrarendelési időtartalék hozzáadva a cikkátfutási időhöz** mezőbe írja be az „1” értéket.
14. Kattintson a **Mentés** gombra.

## <a name="create-a-new-product"></a>Új termék létrehozása
1. Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.
2. Kattintson az **Új** elemre.
3. Írjon be egy értéket a **Termékszám** mezőbe.
4. Írjon be egy értéket a **Terméknév** mezőbe.
5. A **Cikkmodellcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A kívánt rekord megkeresése és kijelölése a listán
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. A **Cikkcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
9. A kívánt rekord megkeresése és kijelölése a listán
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
11. A **Tárolási dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
12. A kívánt rekord megkeresése és kijelölése a listán
13. A listában kattintson a kijelölt sorban lévő hivatkozásra.
14. A **Nyomon követési dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
15. Keresse meg és jelölje ki a kívánt rekordot a listán.
16. A listában kattintson a kijelölt sorban lévő hivatkozásra.
17. Kattintson az **OK** gombra.

## <a name="setup-default-order-settings"></a>Alapértelmezett rendelésbeállítások beállítása
1. A **Művelet panelen** kattintson a **Tervezés** elemre.
2. Kattintson a **Rendelésbeállításai** alatta az **Alapértelmezett rendelés beállításai**elemre.
3. A **Beszerzési rendelés** alatta az **Alapértelmezett telephely** mezőbe írja be azt a telephelyet amelyet alapértelmezettként használtak a beszerzési rendelések létrehozásakor.
4. Az **Alapértelmezett raktár** mezőjébe írja be azt a helyet, ahol a cikket tárolják.
5. Bontsa ki vagy csukja össze a **Készlet** szakaszt.
6. A **Többszörös** mezőbe írja be 10 értéket.
7. A **Minimális rendelési mennyiség** mezőbe írja be a „10” értéket.
8. A **Maximális rendelési mennyiség** mezőbe írja be a „100” értéket.
9. A **Standard rendelési mennyiség** mezőbe írja be a „10” értéket.
10. Adjon meg egy számot az **Beszerzési átfutási idő** mezőben.
11. Jelölje be törölje a **Munkanapok** jelölőnégyzetet.
12. Kattintson a **Mentés** gombra.
13. Az **Alapértelmezett rendeléstípus** mezőben válassza ki a „Beszerzési rendelés” elemet.
14. Kattintson a **Mentés** gombra.
15. Zárja be a lapot. Zárja be az Alapértelmezett rendelésbeállítások oldalt.  

## <a name="add-an-item-to-a-coverage-group"></a>Cikk felvétele egy fedezetcsoportba
1. Bontsa ki vagy zárja be a **Terv** szakaszt.
2. A **Fedezeti csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. Keresse meg a létrehozott **Fedezeti csoportot** a listában.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="create-item-coverage-rules"></a>Cikkfedezet szabályainak létrehozása
1. A **Művelet panelen** kattintson a **Tervezés** elemre.
2. A **Fedezet**területen kattintson a **Cikkfedezeti**elemre.
3. Kattintson az **Új** elemre.
4. Kattintson az **Általános** fülre.
5. Jelölje be a négyzetet a fejlécben a **Fedezeticsoport** beállítások felülbírálatában.
6. A **Fedezet időkorlátja (napok)** mezőbe, írja be: '60'. Annak ellenére, hogy a fedezeti csoport Követelményeket 90 nappal előre megtervezik, ezt a cikket 60 nappal előre fogják tervezni.  
7. A **Negatív napok** mezőbe írja be az „2” értéket.
8. A **Pozitív napok** mezőbe írja be az „2” értéket.
9. Kattintson az **Átfutási idő** fülre.
10. Jelölje be a **Vásárlás** fejlécén lévő jelölőnégyzetet.
11. A **Beszerzés ideje** mezőbe írja be, hogy „5”.
12. Kattintson a **Mentés** gombra.

