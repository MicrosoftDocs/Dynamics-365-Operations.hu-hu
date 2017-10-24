--- 
title: "Leírási napló létrehozása vevőhöz"
description: "Az útmutató bemutatja, hogyan állíthatja be a leírások paramétereit, majd hogyan írhat le tranzakciókat a Beszedések lapról, a Nyitott vevői számlák lapról és a Vevő lapról."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 19a816f04283ce4f200de7396617313e45e057db
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-write-off-journal-for-a-customer"></a>Leírási napló létrehozása vevőhöz

[!include[task guide banner](../../includes/task-guide-banner.md)]

Az útmutató bemutatja, hogyan állíthatja be a leírások paramétereit, majd hogyan írhat le tranzakciókat a Beszedések lapról, a Nyitott vevői számlák lapról és a Vevő lapról. Ez a feladat az USMF bemutatócéget használja.


## <a name="set-up-the-write-off-parameters"></a>Leírási paraméterek beállítása
1. Ugorjon a Követel és beszedések > Beállítás > Kinnlevőségek paraméterei pontra.
2. Kattintson a Beszedések lapra.
3. Bontsa ki vagy csukja össze a Leírás szakaszt.
    * A leírási napló egy általános napló, amely tartalmazza majd a létrehozott leírási tranzakciókat.  
    * Minden leíráshoz társíthat okkódot. Ezt a beállítást felülírhatja a leírás alkalmával.  
    * Állítsa ezt a beállítást Igenre, ha el szeretné különíteni az áfát a leírás eredeti tranzakciójától.  
4. Zárja be a lapot.
5. Ugorjon a Követel és beszedések > Beállítás > Vevői feladási profilok pontra.
    * A leírási számla költségszámlaként vagy foglaláshelyesbítésként jelenik meg az általános naplóban   
6. Zárja be a lapot.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Vevői egyenleg leírása a korosított egyenlegek oldalról
1. Ugorjon a Hitelezés és beszedés > Beszedés > Korosított egyenlegek pontra.
2. Jelölje meg a leírni kívánt vevő sorát. Jelölje meg például a Birch Company nevet tartalmazó sort.
3. A Művelet panelen kattintson a Beszed elemre.
4. Kattintson a „Leírás” gombra.
5. Kattintson az OK gombra.
6. Zárja be a lapot.
7. Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.
8. Válassza ki a leírást tartalmazó napló cikkszámát.
    * Egy sor jön létre a vevői egyenleg visszaállításához. Egy vagy több sor jön létre a leírás leírási számlára való feladásához.  
9. Zárja be a lapot.
10. Zárja be a lapot.

## <a name="write-off-transactions-from-the-collections-form"></a>Írja le a tranzakciókat a beszedések képernyőről.
1. Ugorjon a Hitelezés és beszedés > Beszedés > Korosított egyenlegek pontra.
2. Válassza ki a vevő nevét, akinél a leírni kívánt tranzakciók vannak. Válassza ki például a Cave Wholesales (US-004) lehetőséget.
3. Jelölje meg az első tranzakció sorát.
4. Jelölje meg a második tranzakció sorát.
5. Kattintson a „Leírás” gombra.
6. Az Okra vonatkozó megjegyzés mezőbe írja be a „Behajthatatlan tartozások” okot.
7. Kattintson az OK gombra.
8. Zárja be a lapot.
9. Zárja be a lapot.
10. Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.
11. Válassza ki a leírást tartalmazó napló cikkszámát.
    * Egy sor jön létre a vevői egyenleg visszaállításához. Egy vagy több sor jön létre a leírás leírási számlára való feladásához.  
12. Zárja be a lapot.
13. Zárja be a lapot.

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Számla leírása a nyitott vevői számlák lapról
1. Ugorjon a Kinnlévőségek > Számlák > Nyitott vevői számlák pontra.
2. Jelölje meg a sort számlázásra. Jelölje meg például a CIV-000667 sort.
3. A Művelet panelen kattintson a Számla lehetőségre.
4. Kattintson a „Leírás” gombra.
5. Kattintson az OK gombra.
6. Zárja be a lapot.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Egy vevő egyenlegének leírása a vevői lapon
1. Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.
2. Válasszon ki egy vevőt. Válassza ki a például az US-001 (Contoso Retail San Diego) lehetőséget.
3. A Művelet panelen kattintson a Beszed elemre.
4. Kattintson a „Leírás” gombra.
5. Kattintson az OK gombra.
6. Zárja be a lapot.


