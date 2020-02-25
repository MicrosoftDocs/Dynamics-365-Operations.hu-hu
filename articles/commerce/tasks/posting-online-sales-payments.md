---
title: Online értékesítések és kifizetések feladása
description: Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bf7f72be22539271649aa7f5541735b3d24dab66
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022764"
---
# <a name="posting-of-online-sales-and-payments"></a>Online értékesítések és kifizetések feladása

[!include[task guide banner](../includes/task-guide-banner.md)]

Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz.

Az online értékesítés és fizetések feladása két szakaszból áll.

- Az online kereskedelmi tranzakcióadatok lekérése a központból.
- A rendelések szinkronizálása az értékesítési rendelések központban történő létrehozásához.

Az online tranzakcióadatok lekérése történhet manuálisan, P-feladat futtatásával, vagy ismétlődő kötegelt feladat létrehozásával.

### <a name="manually-running-the-p-job"></a>P-feladat manuális futtatása

1. Ugorjon a következő oldalra: Összes munkaterület >Retail és Commerce infromatika pontra.
2. Kattintson az Elosztási ütemezés elemre.
3. Válassza a P-0001 lehetőséget.
4. Szükség esetén módosítsa a csatorna-adatbázis-csoportokat.
5. Kattintson a Futtatás most elemre.
6. Kattintson az Igen gombra.

### <a name="scheduling-a-recurring-p-job"></a>Ismétlődő P-feladat ütemezése

1. Ugorjon a következő oldalra: Összes munkaterület >Retail és Commerce infromatika pontra.
2. Kattintson az Elosztási ütemezés elemre.
3. Válassza a P-0001 lehetőséget.
4. Kattintson a Kötegelt feladat létrehozása elemre.
5. Kattintson a Futtatás a háttérben elemre.
5. Engedélyezze a Kötegelt feldolgozást.
6. Kattintson az Ismétlődés elemre.
7. Válassza a Nincs záró dátum lehetőséget.
8. A Szám mezőbe írja be a futások közötti időszakot (percben). Ez általában 5-10 perc.
9. Kattintson az OK gombra.
10. Kattintson az OK gombra.

A rendelések vagy manuálisan, a „Rendelések szinkronizálása” feladat futtatásával, vagy ismétlődő kötegelt feladat létrehozásával szinkronizálhatók.

### <a name="manually-running-order-synchronization"></a>A rendelés szinkronizálásának manuális futtatása 

A „Rendelések szinkronizálása” feladat manuális futtatásához hajtsa végre a következő lépéseket.

1. Ugorjon az Összes munkaterület > Áruház pénzügyei oldalra.
2. Kattintson Rendelések szinkronizálása lehetőségre.
3. A Szervezeti hierarchia mezőben válassza ki a „Áruházak régiók szerint” lehetőséget.
    * Válasszon ki egy bizonyos online üzletet vagy egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.  
    * Kattintson a nyílra a kiválasztás hozzáadásához.  
4. Kattintson a Futtatás a háttérben lapra.
5. A kötegelt feldolgozás letiltása
6. Kattintson az Ismétlődésre.
7. Adja meg a Befejezés ezt követően beállítást
8. A Befejezés ezt követően mezőbe írja be az 1 értéket.
9. Kattintson az OK gombra.
10. Kattintson az OK gombra.

### <a name="scheduling-recurring-order-synchronization"></a>Ismétlődő rendelés szinkronizálásának ütemezése

Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz. Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.

1. Ugorjon az Összes munkaterület > Áruház pénzügyei oldalra.
2. Kattintson Rendelések szinkronizálása lehetőségre.
3. A Szervezeti hierarchia mezőben válassza ki a „Áruházak régiók szerint” lehetőséget.
    * Válasszon ki egy bizonyos online üzletet vagy egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.  
    * Kattintson a nyílra a kiválasztás hozzáadásához.  
4. Kattintson a Futtatás a háttérben lapra.
5. Engedélyezze a Kötegelt feldolgozást
6. Kattintson az Ismétlődésre.
7. Válassza a Nincs záró dátum lehetőséget.
8. A Szám mezőbe írja be a futások közötti időszakot (percben). Ez általában 2-20 perc.
9. Kattintson az OK gombra.
10. Kattintson az OK gombra.

## <a name="data-entities-involved-in-the-process"></a>A folyamatban érintett adatentitások

- RetailTransactionTable
- RetailTransactionAddressTrans
- RetailTransactionInfocodeTrans
- RetailTransactionTaxTrans
- RetailTransactionSalesTrans
- RetailTransactionTaxMeasure
- RetailTransactionDiscountTrans
- RetailTransactionTaxTransGTE
- RetailTransactionMarkupTrans
- RetailTransactionPaymentTrans
- RetailTransactionAttributeTrans
