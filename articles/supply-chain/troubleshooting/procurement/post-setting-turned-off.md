---
title: A Feladás főkönyvi költségszámlára beállítás nincs bekapcsolva
description: Ez a probléma egy beszerzési rendelés számlázásakor fordul elő, ha a „Feladás főkönyvi költségszámlára” beállítás engedélyezve van a „Számla” lapon a „Kötelezettségek paraméterei” oldalon.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 592444958dad4624fdc9098dc58df0a2e49e63de
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476572"
---
# <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>A Feladás főkönyvi költségszámlára beállítás nincs bekapcsolva

## <a name="symptoms"></a>Tünetek

Ez a probléma egy beszerzési rendelés számlázásakor fordul elő, ha a **Feladás főkönyvi költségszámlára** beállítás *Igen* értékre van állítva a **Számla** lapon a **Kötelezettségek paramétere** oldalon.

## <a name="reproduce-the-issue"></a>A hiba reprodukálása

A következő eljárás bemutatja a hiba reprodukálásának egyik módját.

1. Ugorjon a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei pontra**.
1. A **Számla** lapon állítsa a **Feladás főkönyvi költségszámlára** beállítást *Igen* értékre.
1. Nyissa meg a **Készletkezelés \> Beállítás \> Feladás \> Feladás** menüt.
1. Győződjön meg róla, hogy a **Beszerzési rendelés** lapon törölte a termékre vonatkozó beszerzési kiadások összes sorát.
1. Nyissa meg a következőt: **Kötelezettségek \> Beszerzési rendelések \> Minden beszerzési rendelés**.
1. Beszerzési rendelés létrehozása A **Szállítói számla** mezőben válassza ki az *1001 Acme irodai kellék* lehetőséget.
1. Adjon hozzá egy beszerzési rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *D0011 lézeres projektor*
    - **Telephely:** *1*
    - **Raktár:** *11*
    - **Mennyiség:** *4*

1. A Műveleti ablaktáblán a **Vásárlás** lapján a **Művelet** csoportban válassza a **Megerősítés** lehetőséget.
1. A Művelet panel **Bevételezés** lapján, a **Generálás** csoportban válassza a **Termékbevételezés** lehetőséget.
1. A **Termékbevételezés feladása** párbeszédpanel **Termékbevételezés** mezőjébe írjon be egy tetszőleges számot, majd kattintson az **OK** gombra.
1. A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban válassza a **Számla** lehetőséget.
1. A **Szám** mezőbe írjon be egy tetszőleges számot a számla sorszámaként.
1. Az egyeztetési állapotot frissítése, és adja fel.
1. Figyelje meg, hogy a következő hibaüzenet jelenik meg, amikor egy beszerzési rendelésből generál egy számlát: „A számlatípus a Beszerzési kiadás tranzakciótípushoz a termékhez nem létezik.”

## <a name="resolution"></a>Megoldás

Ez a számlák és a számlázási csoportok paraméter-beállításaitól függ. A további tudnivalókat lásd a következő blogbejegyzésben: [Könyvelés beszerzési díj és készlet változásához](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).
