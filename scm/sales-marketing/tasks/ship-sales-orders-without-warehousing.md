--- 
title: "Értékesítési rendelések szállítása raktározás nélkül"
description: "Ez az útmutató bemutatja, hogyan lehet egy értékesítési rendelést frissíteni, ha a termékeket kiszállították a vevőhöz."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ab2b52b91bcaef57996ae35120e8713aac5852e7
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="ship-sales-orders-without-warehousing"></a>Értékesítési rendelések szállítása raktározás nélkül

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az útmutató bemutatja, hogyan lehet egy értékesítési rendelést frissíteni, ha a termékeket kiszállították a vevőhöz. Ez az útmutató olyan teljesítési folyamatra használható, amely nincs beállítva raktárkezelésre (sem alap, sem speciális raktározásra), és ezért szükséges regisztrálni termék kitárolást szállítás előtt. Ezt a folyamatot saját adatokkal, vagy az USMF bemutatócég adataival is futtathatja. Mindkét esetben, mielőtt elkezdi a feladatot, hozzon létre egy értékesítési rendelést egy raktározott termékre, amelynek mennyisége több, mint 1. A feladás hibájának elkerülése érdekében ellenőrizze, hogy a termék készleten lévő mennyisége a webhelyen és a megrendeléshez kiválasztott raktárban elegendő a megrendelés teljesítéséhez.


## <a name="post-packing-slip-for-an-order"></a>Egy rendelés szállítólevelének feladása
1. Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.
2. A listában keresse meg és válassza ki a megrendelést, amelyet ehhez a feladathoz hozott létre.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. A műveleti ablaktáblán kattintson a Választáás elemre, majd válassza ki a csomag elemet.
5. Kattintson A szállítólevél feladása lehetőségre.
6. Bontsa ki vagy csukja össze a Paraméterek szakaszt.
7. A Mennyiség mezőben válassza a „Mind” lehetőséget.
    * Egyéb lehetőségek a következők: Szállítás és Kitárolt. Ha a rendelési sort részlegesen kell szállítani és a rendelési sor Szállítás most mezőjében érték van megadva, válassza ki a Szállítás most lehetőséget. Ha a szervezete teljesítési folyamatában a kitárolás külön folyamatként szerepel, amelyet egy kitárolási lista kezel és regisztrál, válassza a Kitárolt lehetőséget.  
    * Ellenőrizze, hogy a Feladás értéke Igen.  
8. Állítsa a Szállítólevél nyomtatása pontot Igenre.
    * Az Áttekintés lapon található az ehhez a feladáshoz létrehozandó szállítólevelek listája. Ha egy egyedülálló rendelést szállít, általában egy szállítólevél van. Azonban ha a megrendelés sorai több oldalról kerülnek szállításra, a feladást automatikusan a megfelelő számú dokumentumra bontja a rendszer. Ez egy kötelező feltétel, nem lehet megváltoztatni. Ehhez hasonlóan a feladási is több dokumentumra oszlik, ha a rendelési sorok eltérő szállítási címekkel rendelkeznek, és a szállítási irányelv előírja a felosztást.  
9. A Sorok lapon válassza ki a szállítandó rendelési sort.
10. A Frissítés mezőben írjon be egy számot, amely kisebb, mint az eredeti mennyiség.
11. Kattintson az OK gombra.
12. Kattintson az Igen gombra.
13. Zárja be a lapot.
14. A Művelet ablaktáblában kattintson a Beállítások elemre.
15. Kattintson a Nézetváltás elemre.
16. Kattintson a Fejlécnézet gombra.
    * Ha a rendelés összes sora teljesen kiszállított, a megrendelés állapota Nyitottról Szállítottra változik.  
    * Ebben a példában a rendelési sort részben kiszállították. Ezért a megrendelés állapota Nyitott marad.     
    * A Dokumentum állapota mezőbe Szállítólevél van beállítva, mert legalább egy rendelési sor szállított.  
17. A Művelet panelen kattintson az Általános elemre.
18. Kattintson a Sormennyiség lehetőségre.
19. Zárja be a lapot.
20. A Művelet panelen kattintson a Kitárolás és csomagolás elemre.
21. Kattintson a Szállítólevél lehetőségre.
    * A Szállítólevél napló oldal tartalmazza az összes szállítólevél dokumentumot, amely az adott megrendeléshez lett létrehozva. Ellenőrizheti a dokumentumok részleteit és kinyomtathatja őket.  


