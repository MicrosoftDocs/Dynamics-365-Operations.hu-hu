---
title: Leírási napló létrehozása vevőhöz
description: Az útmutató bemutatja, hogyan állíthatja be a leírások paramétereit, majd hogyan írhat le tranzakciókat a Beszedések lapról, a Nyitott vevői számlák lapról és a Vevő lapról.
author: ShivamPandey-msft
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21aaeda413e767fed1815423b0262127c6692bb6
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775299"
---
# <a name="create-a-write-off-journal-for-a-customer"></a>Leírási napló létrehozása vevőhöz

[!include [banner](../../includes/banner.md)]

Az útmutató bemutatja, hogyan állíthatja be a leírások paramétereit, majd hogyan írhat le tranzakciókat a Beszedések lapról, a Nyitott vevői számlák lapról és a Vevő lapról. Ez a feladat az USMF bemutatócéget használja.


## <a name="set-up-the-write-off-parameters"></a>Leírási paraméterek beállítása
1. Ugorjon ide: **Navigációs ablaktábla >Modulok > Követelések és beszedések > Beállítás > Kinnlevőségek paraméterei**.
2. Kattintson a **Beszedések** lapra.
3. Bontsa ki vagy csukja össze a **Veszteségleírás** szakaszt.
    - A **leírási napló** egy általános napló, amely tartalmazza majd a létrehozott leírási tranzakciókat.  
    - Minden leíráshoz társíthat okkódot. Ezt a beállítást felülírhatja a leírás alkalmával.  
    - Állítsa a **Külön áfa** beállítást Igenre, ha el szeretné különíteni az áfát a leírás eredeti tranzakciójától.  
4. Zárja be a lapot.
5. Ugorjon a **Követelések és beszedések > Beállítás > Vevői feladási profilok pontra**. A leírási számla költségszámlaként vagy foglaláshelyesbítésként jelenik meg az általános naplóban.
6. Zárja be a lapot.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Vevői egyenleg leírása a korosított egyenlegek oldalról
1. Ugorjon a **Hitelezés és beszedés > Beszedés > Korosított egyenlegek** elemre.
2. Jelölje meg a leírni kívánt vevő sorát. Jelölje meg például a Birch Company nevet tartalmazó sort.
3. A **Művelet panelen** kattintson a **Beszed** elemre.
4. Kattintson a **Leírás** gombra.
5. Kattintson az **OK** gombra.
6. Zárja be a lapot.
7. Nyissa meg a **Navigációs ablak > Modulok > Főkönyv > Naplóbejegyzések > Általános naplók** elemet.
8. Válassza ki a leírást tartalmazó napló cikkszámát. Egy sor jön létre a vevői egyenleg visszaállításához. Egy vagy több sor jön létre a leírás leírási számlára való feladásához.  
9. Zárja be a lapot.


## <a name="write-off-transactions-from-the-collections-page"></a>Tranzakciók írása a beszedési lapon
1. Ugorjon a **Hitelezés és beszedés > Beszedés > Korosított egyenlegek** elemre.
2. Válassza ki a vevő nevét, akinél a leírni kívánt tranzakciók vannak. Válassza ki például a Cave Wholesales (US-004) lehetőséget.
3. Jelölje meg az első tranzakció sorát.
4. Jelölje meg a második tranzakció sorát.
5. Kattintson a **Leírás** gombra.
6. Az **Okra vonatkozó megjegyzés** mezőbe írja be a „Behajthatatlan tartozások” okot.
7. Kattintson az **OK** gombra.
8. Zárja be a lapot.
9. Zárja be a lapot.
10. Ugorjon a **Főkönyv > Naplóbejegyzések > Általános naplók** pontra.
11. Válassza ki a leírást tartalmazó napló cikkszámát. Egy sor jön létre a vevői egyenleg visszaállításához. Egy vagy több sor jön létre a leírás leírási számlára való feladásához.  
12. Zárja be a lapot.


## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Számla leírása a nyitott vevői számlák lapról
1. Ugorjon a következőre: **Navigációs panel > Kinnlévőségek > Számlák > Nyitott vevői számlák**.
2. Jelölje meg a sort számlázásra. Jelölje meg például a CIV-000667 sort.
3. A **Művelet panelen** kattintson a **Számla** elemre.
4. Kattintson a **Leírás** gombra.
5. Kattintson az **OK** gombra.
6. Zárja be a lapot.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Egy vevő egyenlegének leírása a vevői lapon
1. Ugorjon a **Kinnlevőségek > Vevők > Minden vevő** pontra.
2. Válasszon ki egy vevőt. Válassza ki a például az US-001 (Contoso Retail San Diego) lehetőséget.
3. A **Művelet panelen** kattintson a **Beszed** elemre.
4. Kattintson a **Leírás** gombra.
5. Kattintson az **OK** gombra.
6. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
