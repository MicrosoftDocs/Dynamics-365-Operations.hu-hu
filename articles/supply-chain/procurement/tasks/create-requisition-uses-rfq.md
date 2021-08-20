---
title: Olyan igénylés létrehozása, amely ajánlatkérést használ
description: Ez a témakör ismeteti, hogy hogyan lehet egy ajánlatkérési folyamat árral és a szállítóval kapcsolatos információit a beszerzési igényléshez hozzáadni.
author: kamaybac
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 65c6c7b718b3538ebd0096cd173c933b9d750da1102b0c32d73200f4428026a5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776338"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Olyan igénylés létrehozása, amely ajánlatkérést használ

[!include [banner](../../includes/banner.md)]

Ez a témakör ismeteti, hogy hogyan lehet egy ajánlatkérési folyamat árral és a szállítóval kapcsolatos információit a beszerzési igényléshez hozzáadni. A példában szereplő útmutatót az USMF bemutatócég használhatja, és rendszergazdaként kell bejelentkeznie ahhoz, hogy végrehajthassa az összes lépést. Általában a beszerzési szakemberek hajtják végre a példában szereplő útmutatót.


## <a name="create-a-requisition"></a>Igénylés létrehozása
1. A navigációs panelen ugorjon a **Modulok >Beszerzés és forrás > Beszerzési igénylések > Beszerzési igénylések általam létrehozva pontra**.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Név** mezőbe.
4. Adja meg a dátumot az **Igényelt dátum** mezőben.
5. Adja meg a dátumot a **Könyvelés dátuma** mezőben.
6. Válassza ki az **OK** lehetőséget.
7. Az **Ok** mezőben adjon meg vagy válasszon ki egy értéket.
8. Válassza a **Sor hozzáadása** lehetőséget.
9. Válasszon ki egy kategóriát a **Beszerzési kategória** mezőben a fa struktúrában, és kattintson az **OK** gombra.
10. Írjon be egy értéket a **Terméknév** mezőbe.
11. Adjon meg egy számot a **Mennyiség** mezőben.
12. Az **Egység** mezőben adjon meg vagy válasszon ki egy értéket.
13. Válassza a **Mentés** lehetőséget.
14. A **Munkafolyamat** gombra kattintva megnyithatja a legördülő párbeszédablakot.
15. Válassza a **Beküldés** lehetőséget.
16. Zárja be a lapot.
17. Válassza a **Beküldés** lehetőséget.

## <a name="reassign-a-workflow-task"></a>Munkafolyamat-feladat ismételt hozzárendelése
A következő feladat egy Ajánlatkérés létrehozása annak érdekében, hogy ajánlatot kapjon a szállítótól a termékre. Az USMF bemutató adatokban az igénylési munkafolyamat egy olyan szabály szerint van beállítva, hogy ha a szállító nincs bejelölve, vagy az egységár értéke 0 soronként, akkor a rendszer a feladatot hozzárendeli egy adott dolgozóhoz, azért, hogy az létrehozzon egy Ajánlatkérést. Az útmutató folytatásához a feladatot ismét hozzá kell rendelni egy másik felhasználóhoz (saját magához). Csak úgy teheti meg ezt, ha Rendszergazdaként jelentkezik be.  

1. A **Munkafolyamat** gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. Válassza az **Előzmények megtekintése** elemet.
3. Frissítse a lapot..
4. Bontsa ki a **Nyomkövetési részletek** szakaszt.
5. Válassza ki a „Sor munkafolyamata aktiválva ekkor:” értékkel kezdődő sort a fa struktúrában.
6. Válassza a **Munkafolyamat részleteinek megtekintése** elemet.
7. Bontsa ki a **Munkatételek** szakaszt.
8. Válassza ki az **Ismételt hozzárendelés** lehetőséget.
9. Válassza ki a **Rendszergazdát** a **Felhasználó** mezőben.
10. Válassza ki az **Ismételt hozzárendelés** lehetőséget.
11. Zárja be a két lapot.

## <a name="create-an-rfq"></a>Ajánlatkérés létrehozása

1. Frissítse a lapot..
2. Válassza az **Ajánlatkérés** elemet.
3. Válassza ki az **USMF** lehetőséget a **Vevő jogi személy** mezőben. Ugyanazt a jogi személyt kell kiválasztania, mint aki az igénylés sorában szerepel.  
4. A listában jelölje meg a kiválasztott sort. Ha a beszerzési igénylésben több sorral rendelkezett, válassza ki az összes olyan sort, amelyet hozzá kíván adni az ajánlatkéréshez.  
5. Válassza ki az **OK** lehetőséget.
6. Frissítse a lapot..
7. Nyissa meg az Adatterület lehetőséget, majd bontsa ki a **Kapcsolódó dokumentumok** szakaszt.
8. Kattintson az Ajánlatkérés mezőben szereplő hivatkozásra az újonnan létrehozott **Ajánlatkérés** megnyitásához.
9. Válassza ki a **Fejléc** elemet.
10. Válassza a **Hozzáadás** lehetőséget.
11. A **Szállítószámla** mezőben adjon meg vagy válasszon ki egy értéket.
12. Válassza a **Hozzáadás** lehetőséget.
13. A **Szállítószámla** mezőben adjon meg vagy válasszon ki egy értéket.
14. Válassza a **Küldés** lehetőséget.
15. Válassza ki az **OK** lehetőséget.
16. Válassza a **Válasz megadása** parancsot.
17. A Műveleti ablaktáblán kattintson a **Válasz** elemre.
18. Válassza az **Adatok másolása a válaszba** elemet. Ez olyan adatokat másol a válaszhoz az ajánlatkérésből, mint például a mennyiség vagy a dátumok.  
19. Adjon meg egy számot az **Egységár** mezőben. Ez a szállítótól kapott ár. További információkat is meg kell adnia a szállítóról.  
20. Válassza az **Elfogadás** lehetőséget.
21. Válassza ki az **OK** lehetőséget.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Győződjön meg arról, hogy átkerült az ár és a szállító az igényléshez.
1. Zárja be a lapot.
2. **Sorok** kiválasztása.
3. Válassza ki a **Kapcsolódó információ** elemet.
4. Válassza a **Beszerzési igénylés** elemet.
5. Válassza ki azt a sort, amelyet a rendszer átvitt az Ajánlatkéréshez. Győződjön meg arról, hogy átmásolták az árat és a szállítót az igényléshez.  
6. A **Munkafolyamat** gombra kattintva megnyithatja a legördülő párbeszédablakot.
7. Válassza a Kész lehetőséget
8. Válassza az oldalt.
9. Válassza a Kész lehetőséget



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]