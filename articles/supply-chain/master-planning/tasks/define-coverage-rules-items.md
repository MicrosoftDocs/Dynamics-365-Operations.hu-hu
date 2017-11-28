--- 
title: "Cikkek fedezeti szabályainak meghatározása"
description: "Ez az eljárás az USMF bemutatócéget használja."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
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
ms.sourcegitcommit: 76334f7ee4efe33df4a86aaa11a59748387cec89
ms.openlocfilehash: fe92393cc264df68f084db6974f7d4607d37d3ab
ms.contentlocale: hu-hu
ms.lasthandoff: 11/02/2017

---
# <a name="define-coverage-rules-for-items"></a>Cikkek fedezeti szabályainak meghatározása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás bemutatja, hogyan tud fedezeti szabályokat létrehozni és egy adott cikk fedezeti beállításait felülírni. Azt is bemutatja, hogyan kell megadni az alapértelmezett készletbeállításokat.


## <a name="create-a-coverage-group"></a>Fedezetcsoport létrehozása
1. Ugrás a Fedezetcsoportokra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Fedezeti csoport mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. Írjon be egy értéket a Naptár mezőbe.
    * Válassza ki azt a naptárat, amely alapján az ebben a csoportban szereplő cikkek esetében az alaptervezés a feltöltési javaslatokat létrehozza.  
6. A Fedezet kódja mezőben válasszon ki egy lehetőséget.
    * Jelölje be az eljáráshoz szükséges követelményeket.  
7. A fedezet időkorlátja (napok) mezőben, írja be: '90'.
    * Az ebben a csoportban szereplő cikkek esetében az alaptervezés legfeljebb 90 napos jövőbeni időszakra szóló feltöltési javaslatokat hoz létre.  
8. A Negatív napok mezőbe írja be az „1” értéket.
9. A Pozitív napok mezőbe írja be az „1” értéket.
10. Bontsa ki vagy zárja be az Egyéb szakaszt.
11. A Követelmény dátumához hozzáadott bevételezési időtartalék mezőbe írja be az „1” értéket.
    * Ha például a bevételezési különbözet 1 napra van állítva, és a beszerzési rendelési sor május 15-re van bevételezésre ütemezve, az alapütemezés május 16-ra számítja ki a korrigált bevételezési dátumot.  
12. A Követelmény dátumából levont kiadási időtartalék mezőbe írja be az „1” értéket.
    * Ha például a kiadási különbözet 1 napra van állítva, és az értékesítési rendelési sor május 15-re van kiszállításra ütemezve, az alapütemezés május 14-re számítja ki a korrigált kiadási dátumot.  
13. Az Újrarendelési időtartalék hozzáadva a cikkátfutási időhöz mezőbe írja be az „1” értéket.
14. Kattintson a Mentés gombra.

## <a name="create-a-new-product"></a>Új termék létrehozása
1. Ugrás a Kiadott termékek elemre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Termékszám mezőbe.
4. Írjon be egy értéket a Terméknév mezőbe.
5. A Cikkmodellcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A kívánt rekord megkeresése és kijelölése a listán
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. A Cikkcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
9. A kívánt rekord megkeresése és kijelölése a listán
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
11. A Tárolási dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
12. A kívánt rekord megkeresése és kijelölése a listán
13. A listában kattintson a kijelölt sorban lévő hivatkozásra.
14. A Nyomon követési dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
15. Keresse meg és jelölje ki a kívánt rekordot a listán.
16. A listában kattintson a kijelölt sorban lévő hivatkozásra.
17. Kattintson az OK gombra.

## <a name="setup-default-order-settings"></a>Alapértelmezett rendelésbeállítások beállítása
1. A Művelet panelen kattintson a Terv elemre.
2. Kattintson az Alapértelmezett rendelésbeállítások elemre.
3. A Beszerzési telephely mezőbe írja be azt a telephelyet, amelyet alapértelmezettként használtak a beszerzési rendelések létrehozásakor.
4. A Készletező hely mezőjébe írja be azt a helyet, ahol a cikket tárolják.
5. Bontsa ki vagy csukja össze a Készlet szakaszt.
6. Adja meg a Több értékeként a „10”-et.
7. Min. rendelt mennyiség beállítása „10”-re.
8. Maximális beállítása. rendelt mennyiség beállítása „100”-re.
9. Szokásos rendelési mennyiség beállítása „10”-re.
10. Adjon meg egy számot az Beszerzési átfutási idő mezőben.
11. Jelölje be törölje a Munkanapok jelölőnégyzetet.
12. Kattintson a Mentés gombra.
13. Az Alapértelmezett rendeléstípus mezőben válassza ki a „Beszerzési rendelés” elemet.
14. Kattintson a Mentés gombra.
15. Zárja be a lapot.
    * Zárja be az Alapértelmezett rendelésbeállítások oldalt.  

## <a name="add-an-item-to-a-coverage-group"></a>Cikk felvétele egy fedezetcsoportba
1. Bontsa ki vagy zárja be a Terv szakaszt.
2. A Fedezeti csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. Keresse meg a létrehozott fedezeti csoportot a listában.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="create-item-coverage-rules"></a>Cikkfedezet szabályainak létrehozása
1. A Művelet panelen kattintson a Terv elemre.
2. Kattintson a cikkfedezet elemre.
3. Kattintson az Új lehetőségre.
4. Kattintson az Általános fülre.
5. Jelölje be a négyzetet a fejlécben a Fedezeticsoport-beállítások felülbírálatában.
6. A fedezet időkorlátja (napok) mezőbe, írja be: '60'.
    * Annak ellenére, hogy a fedezeti csoport Követelményeket 90 nappal előre megtervezik, ezt a cikket 60 nappal előre fogják tervezni.  
7. A Negatív napok mezőbe írja be a „2” értéket.
8. A Pozitív napok mezőbe írja be a „2” értéket.
9. Kattintson az Átfutási idő fülre.
10. Jelölje be a Vásárlás fejlécén lévő jelölőnégyzetet.
11. A Beszerzés ideje mezőbe írja be, hogy „5”.
12. Kattintson a Mentés gombra.


