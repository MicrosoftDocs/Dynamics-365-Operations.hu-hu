--- 
title: "Beszerzésirendelés-kiadás létrehozása beszerzési szerződésből"
description: "Ez az eljárás bemutatja, hogyan lehet használni egy beszerzési szerződést, amikor beszerzési rendelést hoz létre."
author: mkirknel
manager: AnnBe
ms.date: 12/04/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ee4bec20fa2449aaa961ab19891a002702174446
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-purchase-release-order-from-a-purchase-agreement"></a>Beszerzésirendelés-kiadás létrehozása beszerzési szerződésből

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet használni egy beszerzési szerződést, amikor beszerzési rendelést hoz létre. A beszerzési szerződést a beszerzési rendelés létrehozásakor kell alkalmazni, mivel az általános feltételeket át kell másolni a beszerzési rendelés fejlécébe. Általában ez a feladatot egy beszerzési ügynök végzi el. Az útmutató előfeltétele a szállító és a cikkek hatályos beszerzési megállapodása egy termékmennyiségi kötelezettséggel. Ugyanezt az eljárást akkor is használhatja, ha a beszerzési szerződés más típusú kötelezettségvállalásokra vonatkozik. Ezt az útmutatót lefuttathatja az USMF bemutatócégen. Az USMF használata esetén az útmutatóhoz szükséges előfeltételek beállításához futtathatja a „Beszerzési szerződés létrehozása” útmutatót.


## <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása
1. Nyissa meg a Beszerzési rendelések előkészítési munkaterületét.
2. Kattintson az Új beszerzési rendelés elemre.
3. A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Az Általános szakasz bővítésének átváltása.
7. A Beszerzési szerződés mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A szállítóhoz rendelt összes rendelkezésre álló megállapodás itt van felsorolva. Keresse meg használni kívánt effektív megállapodást.  
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Kattintson az Igen gombra.
10. Kattintson az OK gombra.

## <a name="add-a-line"></a>Sor hozzáadása
1. A cikkmezőbe írjon egy értéket.
    * Ha adott készlet vagy a helydimenziók vannak a kötelezettségvállaláson, akkor meg kell adni ugyanazokat az értékeket a beszerzésirendelés-soron a megállapodás használatához.  
2. A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A hely már ki lehet töltve az alapértelmezett értékekkel a rendelésből, vagy a szállítótól. Ha ez a helyzet, hagyja ki ezt a lépést.  
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Adjon meg egy számot a Mennyiség mezőben.
    * Ellenőrizze, hogy az árat átmásolta-e a kötelezettségvállalásból.  

## <a name="look-up-the-commitment"></a>A kötelezettségvállalás megkeresése
1. Kattintson a Sor frissítése elemre.
2. Kattintson a Csatolt elemre.
    * Itt kaphat részleteket a beszerzési szerződésről. Például láthatja az árat, és azt, hogy az ár és engedmény rögzített-e, azaz ha az árat és az engedményt a beszerzési rendelésen egy másik értékre módosítja, mint a kötelezettségvállaláson, a rendszer eltávolítja a hivatkozást, hogy a beszerzésirendelés-sor ne feleljen meg a kötelezettségvállalásnak. Látható az is, hogy a Maximum betartatása beállítás meg van-e adva, ami azt jelenti, hogy a kötelezettségvállaláson szereplő mennyiség nem lépheti túl a kötelezettségvállalást teljesítő beszerzések összegét.  
3. Zárja be a lapot.

## <a name="look-up-the-purchase-agreement"></a>Beszerzési szerződés megkeresése
1. A Művelet panelen kattintson az Általános elemre.
2. Kattintson a Beszerzési szerződés elemre.
3. Zárja be a lapot.
4. Zárja be a lapot.

