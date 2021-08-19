---
title: Termékbevételezések és számlázás hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani az termékbevételezések és számlázás használata során felmerülő problémákat.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: e85556c7b86cfc8c78d3bcd53a7b99bb0bbddf3a2a45e6fe6329560c834633af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718924"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a>Termékbevételezések és számlázás hibaelhárítása

Ez a témakör azt mutatja be, hogyan lehet javítani az termékbevételezések és számlázás használata során felmerülő problémákat.

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Nem tudok egynél több számlát feladni egy olyan beszerzésirendelés-sorhoz, amelyen kategória alapú cikkek szerepelnek.

A mennyiséget kötelező megadni, ha számlákat szeretne feladni. Ha tehát egy sor teljes mennyisége csak részlegesen lett kiszámlázva, akkor egy másik számlával nem számlázhatja a fennmaradó összeget.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>A beszerzési rendelés visszaigazolásakor egy „Objektumhivatkozás nincs beállítva” hiba vagy „Kivétel történt a meghívás célja felől” kivétel jelenik meg szállítói számla feladása során.

Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.

A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget. A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Egyetlen beszerzési rendelésbe nem tudok több terméknyugtát egyesíteni.

Egyetlen beszerzési rendelésbe nem lehet több terméknyugtát összesíteni, ha a különböző szállítólevél-sorok különböző könyvelési dátumokkal rendelkeznek.

A Microsoft Dynamics 365 Supply Chain Management korábbi verzióiban a konszolidációt ebben a helyzetben engedélyezett volt. Ez a gyakorlat azonban hibákhoz vezethet. A létrejövő beszerzésirendelés-sorok könyvelési dátuma nem térhet el azon terméknyugta-sorok könyvelés dátumától, amelyek alapján ezeket a beszerzésirendelés-sorokat létrehozták. (A beszerzési rendelés sorainak könyvelési dátuma megegyezik a beszerzési rendelés fejlécében szereplő könyvelési dátummal.) Ezért a több nyugta egyetlen beszerzési rendelésbe történő konszolidációja már nem engedélyezett.

A könyvelési dátum például költségvetési foglalások és kötelezettségvállalások esetén használatos. Ezért a termék bevételezéséről a beszerzési rendelésre való áttérés során meg kell őrizni.

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a>A termékbevételezés törlése esetén a tranzakciók feladása felfüggesztett főkönyvi számlára történhet.

### <a name="issue-description"></a>Probléma leírása

Ha egy termékbevételezés érvénytelenítve van, a rendszer lehetővé teszi a tranzakciók feladását a felfüggesztett főkönyvi számlákra, még akkor is, ha a fő számlákat felfüggesztették.

### <a name="reproduce-the-issue"></a>A hiba reprodukálása

A következő eljárás bemutatja a hiba reprodukálásának egyik módját.

1. A **Kötelezettségek paraméterei** lap **Általános** lapján győződjön meg arról, hogy a **Termékbevételezés feladása a főkönyvben** beállítás *Igen* értékre van állítva.
1. Hozzon létre egy beszerzési rendelést, és adjon hozzá egy *1000* mennyiséget tartalmazó rendelési sort a termékhez.
1. Erősítse meg a beszerzési rendelést.
1. Adja fel a termékbevételezést, és ellenőrizze a bizonylatokat.
1. Függessze fel a kapcsolódó fő számlákat: *200140* és *140200*.
1. Vonja vissza feladott termékbevételezést.
1. Figyelje meg, hogy a tranzakciók feladhatók a felfüggesztett főkönyvi számlákra.

### <a name="issue-resolution"></a>Probléma megoldása

A tranzakciókat fel lehet adni a felfüggesztett főkönyvi számlákra, ha a termékbevételezéseket érvénytelenítik, mert ez a viselkedés lehetővé teszi a megfelelő feladásokat.

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a>A termék bevételezési bizonylatának száma akkor is fel lesz használva, ha a termék bevételezése során nem készül pénzügyi bizonylat.

Ha a **Kötelezettség elhatárolása termékbevételezéskor** beállítás értéke *Nem* cikkmodell-csoporthoz, akkor nem történik feladás a főkönyvbe. A program azonban egy fizikai eseményt rögzít egy analitikába történő könyvelés céljából, és az eseményhez bizonylatszámot kell megadni. Ez a bizonylatszám a készlettranzakciókban hivatkozott bizonylatszám.

Azt ajánljuk, hogy a **Kötelezettség elhatárolása termékbevételezéskor** beállítás *Igen* értékre állítsa , a következő blogbejegyzésben leírtak szerint: [Vegyes költségek feladása terméknyugta időpontjában](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>A Feladás főkönyvi költségszámlára beállítás nincs bekapcsolva.

### <a name="issue-description"></a>Probléma leírása

Ez a probléma egy beszerzési rendelés számlázásakor fordul elő, ha a **Feladás főkönyvi költségszámlára** beállítás *Igen* értékre van állítva a **Számla** lapon a **Kötelezettségek paramétere** oldalon.

### <a name="reproduce-the-issue"></a>A hiba reprodukálása

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

### <a name="issue-resolution"></a>Probléma megoldása

Ez a számlák és a számlázási csoportok paraméter-beállításaitól függ. A további tudnivalókat lásd a következő blogbejegyzésben: [Könyvelés beszerzési díj és készlet változásához](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]