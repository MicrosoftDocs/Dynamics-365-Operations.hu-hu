--- 
title: "Használja a biztonsági készlet naplót, hogy frissítse a minimális fedezetet"
description: "Ez az eljárás bemutatja, hogyan számolja ki a minimális fedezet javaslatokat a már meglévő tranzakciók alapján és ezután frissítse a cikkfedezetet a javaslatokkal."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d278b20724006ec3b3aa557738e8b130ca2bba15
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>Használja a biztonsági készlet naplót, hogy frissítse a minimális fedezetet

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan számolja ki a minimális fedezet javaslatokat a már meglévő tranzakciók alapján és ezután frissítse a cikkfedezetet a javaslatokkal. Ebben az esetben a biztonsági készlet naplóját használja. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként. Ez a feladat a termeléstervezőnek van fenntartva, hogy segítse a minimális fedezet fenntartását.


## <a name="create-a-new-safety-stock-journal-name"></a>Hozzon létre egy új biztonsági készlet napló nevet
1. Menjen a Biztonsági készlet naplók neveihez.
2. Kattintson az Új lehetőségre.
3. A Név mezőbe írja be: típus „Anyag”.
4. A Leírás mezőbe írja be: típus „Anyag”.
5. Zárja be a lapot.

## <a name="create-a-safety-stock-journal"></a>Hozzon létre egy biztonsági készlet naplót
1. Menjen a Biztonsági készlet számításához.
2. Kattintson az Új lehetőségre.
3. A Név mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a létrehozott biztonsági napló nevet, például Anyag.  
4. Kattintson a Sorok létrehozása lehetőségre.
5. Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.
    * Állítsa a dátumot erre: „2015-01-02”.  
6. Adja meg a dátumot a „Záró dátum” mezőben.
    * Állítsa a dátumot erre: „2015-12-30”.  
7. Kattintson az OK gombra.
    * Ez hoz létre sorokat a készlettranzakciókkal rendelkező dimenziókhoz.  

## <a name="calculate-proposal"></a>Javaslat számítása
1. Kattintson a Javaslat számítására.
2. Válassza az Átlagos kiadás használata az átfutási idő alatt lehetőséget.
3. A szorzótényezőt állítsa „10”-re.
    * A Multiply tényező a javaslat beállításához használható. Mivel a bemutató adatokban csak néhány tranzakció van, Önnek kell majd beállítania a tényezőt, hogy reális javaslatot kapjon.  
4. Kattintson az OK gombra.
    * Görgessen le, hogy megtalálja M0002 és M0003 értékeket. Tekintse meg a Kiszámított minimum mennyiség oszlopot.   

## <a name="update-minimum-quantity"></a>Frissítse a minimum mennyiséget
1. Az Új minimum mennyiség mezőben adjon meg egy számot.
    * Frissítse az Új minimum mennyiségét, hogy az megegyezzen a Számított minimális mennyiséggel. Ha a Számított minimum értéke nulla, megadhatja jövőbeli kívánt értékét. Például megadhatja a Kiszámított minimum mennyiséget ebbe a mezőbe az M0002-höz, akié a 12-es raktár.  
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Például kiválaszthatja az M0002-őt, akié a 12-es raktár.  
3. Az Új minimum mennyiség mezőben adjon meg egy számot.
    * Frissítse az Új minimum mennyiségét, hogy az megegyezzen a Számított minimális mennyiséggel. Ha a Számított minimum értéke nulla, megadhatja jövőbeli kívánt értékét.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Vigye fel az új minimum mennyiséget és ellenőrizze az eredményt
1. Kattintson a Feladás lehetőségre.
2. Kattintson az OK gombra.
3. Kattintson a Cikkszám mezőben található hivatkozásra.
4. Kattintson a Cikkszám mezőben található hivatkozásra.
5. A Művelet panelen kattintson a Terv elemre.
6. Kattintson a cikkfedezet elemre.
    * Fontos megjegyezni, hogy a minimum mennyiséget frissítettük, így most már a biztonsági készlet naplójában szereplő minimum mennyiséget tükrözi.  


