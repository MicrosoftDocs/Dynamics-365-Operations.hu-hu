---
title: Használja a biztonsági készlet naplót, hogy frissítse a minimális fedezetet
description: Ez az eljárás bemutatja, hogyan számolja ki a minimális fedezet javaslatokat a már meglévő tranzakciók alapján és ezután frissítse a cikkfedezetet a javaslatokkal.
author: ChristianRytt
manager: tfehr
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d69daf3d307ba72ff6017d91849e3d22bd0bd85
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429748"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>Használja a biztonsági készlet naplót, hogy frissítse a minimális fedezetet

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan számolja ki a minimális fedezet javaslatokat a már meglévő tranzakciók alapján és ezután frissítse a cikkfedezetet a javaslatokkal. Ebben az esetben a biztonsági készlet naplóját használja. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként. Ez a feladat a termeléstervezőnek van fenntartva, hogy segítse a minimális fedezet fenntartását.


## <a name="create-a-new-safety-stock-journal-name"></a>Hozzon létre egy új biztonsági készlet napló nevet
1. A **Navigációs ablaktáblán** lépjen az **Alaptervezés > Beálítás > Biztonsági készlet naplójának nevei** elemre.
2. Kattintson az **Új** elemre.
3. A **Név** mezőbe írja be: „Anyag”.
4. A **Leírás** mezőbe írja be: „Anyag”.
5. Zárja be a lapot.

## <a name="create-a-safety-stock-journal"></a>Hozzon létre egy biztonsági készlet naplót
1. A **Navigációs ablaktáblán** lépjen az **Alaptervezés > Alaptervezés > Futtatás > Biztonsági készlet számítása** elemre.
2. Kattintson az **Új** elemre.
3. A **Név** mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki a létrehozott biztonsági napló nevet, például Anyag.  
4. Kattintson a **Sorok létrehozása** lehetőségre.
5. Adjon meg egy dátumot a **Kezdő dátum** mezőben.  
6. Adjon meg egy dátumot a **Záró dátum** mezőben.
7. Kattintson az **OK** gombra. Ez hoz létre sorokat a készlettranzakciókkal rendelkező dimenziókhoz.  

## <a name="calculate-proposal"></a>Javaslat számítása
1. Kattintson a **Javaslat számítása** pontra.
2. Válassza az **Átlagos kiadás használata az átfutási idő alatt** lehetőséget.
3. A **Szorzótényező** értékét állítsa „10”-re. A Multiply tényező a javaslat beállításához használható. Mivel a bemutató adatokban csak néhány tranzakció van, Önnek kell majd beállítania a tényezőt, hogy reális javaslatot kapjon.  
4. Kattintson az **OK** gombra. Görgessen le, hogy megtalálja M0002 és M0003 értékeket. Tekintse meg a **Kiszámított minimum** mennyiségoszlopot.   

## <a name="update-minimum-quantity"></a>Frissítse a minimum mennyiséget
1. Az **Új minimális mennyiség** mezőben adjon meg egy számot. Frissítse az Új minimum mennyiségét, hogy az megegyezzen a Számított minimális mennyiséggel. Ha a Számított minimum értéke nulla, megadhatja jövőbeli kívánt értékét. Például megadhatja a Kiszámított minimum mennyiséget ebbe a mezőbe az M0002-höz, akié a 12-es raktár.  
2. Keresse meg és jelölje ki a kívánt rekordot a listán. Például kiválaszthatja az M0002-őt, akié a 12-es raktár.  
3. Az **Új minimális mennyiség** mezőben adjon meg egy számot. Frissítse az Új minimum mennyiségét, hogy az megegyezzen a Számított minimális mennyiséggel. Ha a Számított minimum értéke nulla, megadhatja jövőbeli kívánt értékét.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Vigye fel az új minimum mennyiséget és ellenőrizze az eredményt
1. Kattintson a **Bejegyzés** lehetőségre.
2. Kattintson az **OK** gombra.
3. Kattintson a **Cikkszám** mezőben található hivatkozásra.
4. Kattintson a **Cikkszám** mezőben található hivatkozásra.
5. A **Művelet panelen** kattintson a Tervezés elemre.
6. Kattintson a **Cikkfedezet** elemre. Fontos megjegyezni, hogy a **Minimális mennyiség** frissült, így most már a biztonsági készlet naplójában szereplő minimum mennyiséget tükrözi.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]