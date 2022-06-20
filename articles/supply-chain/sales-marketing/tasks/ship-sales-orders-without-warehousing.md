---
title: Értékesítési rendelések szállítása raktározás nélkül
description: Ez a cikk azt mutatja be, hogyan lehet frissíteni az értékesítési rendeléseket, amikor termékeket szállítanak ki a vevőnek.
author: Henrikan
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0144be929045b385c58dd29f6241330fc1092f0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862482"
---
# <a name="ship-sales-orders-without-warehousing"></a>Értékesítési rendelések szállítása raktározás nélkül

[!include [banner](../../includes/banner.md)]

Ez a cikk azt mutatja be, hogyan lehet frissíteni az értékesítési rendeléseket, amikor termékeket szállítanak ki a vevőnek. Ez az útmutató olyan teljesítési folyamatra használható, amely nincs beállítva raktárkezelésre (sem alap, sem speciális raktározásra), és ezért szükséges regisztrálni termék kitárolást szállítás előtt. Ezt a folyamatot saját adatokkal, vagy az USMF bemutatócég adataival is futtathatja. Mindkét esetben, mielőtt elkezdi a feladatot, hozzon létre egy értékesítési rendelést egy raktározott termékre, amelynek mennyisége több, mint 1. A feladás hibájának elkerülése érdekében ellenőrizze, hogy a termék készleten lévő mennyisége a webhelyen és a megrendeléshez kiválasztott raktárban elegendő a megrendelés teljesítéséhez.

## <a name="post-packing-slip-for-an-order"></a>Egy rendelés szállítólevelének feladása
1. A navigációs ablakban ugorjon a **Modulok > Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés** pontra.
2. A listában keresse meg és válassza ki a megrendelést, amelyet ehhez a feladathoz hozott létre.
3. A Műveleti ablaktáblán válassza ki a **Kitárolás és csomagolás** elemet.
4. Válassza ki a **Szállítólevél feladása** elemet.
5. Bontsa ki vagy csukja össze a **Paraméterek** szakaszt.
6. A **Mennyiség** mezőben válassza a **Mind** lehetőséget.
    - Egyéb lehetőségek a következők: **Szállítás most** és **Kitárolt**. Ha a rendelési sort részlegesen kell szállítani és a rendelési sor **Szállítás most** mezőjében van érték, válassza ki a **Szállítás most** lehetőséget. Ha a szervezete teljesítési folyamatában a kitárolás külön folyamatként szerepel, amelyet egy kitárolási lista kezel és regisztrál, válassza a **Kitárolt** lehetőséget.  
    - Ellenőrizze, hogy a **Feladás** értéke **Igen**-re van-e állítva.  
7. Állítsa a **Szállítólevél nyomtatása** lehetőséget **Igen** értékre. Az **Áttekintés** lapon található az ehhez a feladáshoz létrehozandó szállítólevelek listája. Ha egy egyedülálló rendelést szállít, általában egy szállítólevél van. Azonban ha a megrendelés sorai több oldalról kerülnek szállításra, a feladást automatikusan a megfelelő számú dokumentumra bontja a rendszer. Ez egy kötelező feltétel, nem lehet megváltoztatni. Ehhez hasonlóan a feladási is több dokumentumra oszlik, ha a rendelési sorok eltérő szállítási címekkel rendelkeznek, és a szállítási irányelv előírja a felosztást.  
8. A **Sorok** lapon válassza ki a szállítandó rendelési sort.
9. A **Frissítés** mezőben adjon meg egy számot, amely kisebb, mint az eredeti mennyiség.
10. Válassza ki az **OK** lehetőséget.
11. Válassza ki az **Igen** lehetőséget.
12. Zárja be a lapot.
13. A műveleti ablaktáblán válassza ki a **Beállítások** elemet.
14. Válassza ki a **Nézetváltás** lehetőséget.
15. Válassza ki a **Fejlécnézet** elemet.
    - Ha a rendelés összes sora teljesen kiszállított, a megrendelés állapota Nyitottról Szállítottra változik.  
    - Ebben a példában a rendelési sort részben kiszállították. Ezért a megrendelés állapota Nyitott marad.     
    - A **Dokumentum állapota** mezőben a Szállítólevél érték van beállítva, mert legalább egy rendelési sor ki van szállítva.  
16. A Művelet ablaktáblán válassza ki az **Általános** elemet.
17. Válassza ki a **Sor mennyisége** elemet.
18. Zárja be a lapot.
19. A Műveleti ablaktáblán válassza ki a **Kitárolás és csomagolás** elemet.
20. Válassza ki a **Szállítólevél** lehetőséget. A **Szállítólevél naplója** oldal tartalmazza az összes olyan szállítólevelet, amely az adott megrendeléshez lett létrehozva. Ellenőrizheti a dokumentumok részleteit és kinyomtathatja őket.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]