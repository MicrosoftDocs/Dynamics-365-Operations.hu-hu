---
title: "Előlegre jogosult tranzakciói"
description: "Ismerje meg, hogyan dolgozhat a Microsoft Dynamics 365 for Finance and Operationsben előlegre jogosultak tranzakcióival."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorkerAdvHolderTableListPage_RU
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 262554
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 3e1fbb37c75052f10fdac3d3361e2c93c3c8a56c
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="advance-holder-transactions"></a>Előlegre jogosult tranzakciói

[!INCLUDE [banner](../includes/banner.md)]

Ismerje meg, hogyan dolgozhat a Microsoft Dynamics 365 for Finance and Operationsben előlegre jogosultak tranzakcióival.

Ezen előlegre jogosult dolgozók számára tranzakciókat előlegrejogosult-fiókok segítségével lehet feladni. A minden előlegre jogosultnál megadott dolgozói azonosító használható az előlegre jogosultak összes tranzakciójának nyomon követésére. Ez a szám számlaszámként hívható le az előlegre jogosultak tranzakcióihoz a **Főkönyvi naplók** és **Előlegre jogosult tranzakciói** oldalakon.

## <a name="create-and-post-a-purchase-order-with-advance-holder-details"></a>Beszerzési rendelés létrehozása és feladása az előlegre jogosultak részletes adataival
A beszerzési rendelésekkel kapcsolatos általános tudnivalókért lásd: [Beszerzési rendelések áttekintése](../../supply-chain/procurement/purchase-order-overview.md). Előlegjogosulti adatokat tartalmazó szállítói számla létrehozása és feladása esetén az előlegre jogosult egyenlegei alkalmazotti egyenlegszámlára kerülnek feladásra a szállítói egyenlegszámla helyett. Előlegre jogosult részleteinek beszerzési rendeléshez történő hozzáadásához tegye a következőket:

-   Az **Ár és engedmény** szakasz **Fizetési feltételek** mezőjében válassza ki a fizetési feltételeket. <!---For more information about **Terms of payment**, see [Define vendor payment terms](../accounts-payable/tasks/define-vendor-payment-terms.md).--> Olyan fizetési feltételt válasszon ki, amelynél a **Kezdő előlegre jogosult** lehetőség ki van választva a **Fizetési feltételek** oldalon. Előlegre jogosultak számára fizetési feltételek beállításával kapcsolatos további tudnivalókért lásd: [Előlegre jogosultak](emea-advance-holders.md).
-   Az **Ár és engedmény** gyorslap **Előlegre jogosult** mezőjében válassza ki az előlegre jogosultat a beszerzési rendeléshez.

A beszerzési rendelés feladási folyamata két szállítói tranzakciót hoz létre ellentétes összegekkel és egy előlegrejogosult-tranzakcióval. Előlegjogosulti adatok nélkül csak egy szállítói tranzakció jön létre.

## <a name="settle-advance-holder-balances-via-a-bank"></a>Előlegre jogosultak egyenlegeinek banki kiegyenlítése
Előlegre jogosultak egyenlegeinek banki kiegyenlítésekor az előlegre jogosultak egyenlegeit lezáró naplóbejegyzések a főkönyvben jönnek létre. A naplóhoz tartozó kódot és a bankot a **Kötelezettségek paraméterei** oldal **Előlegre jogosultak** szakaszában állíthatja be. További információ: [Előlegre jogosultak](emea-advance-holders.md). Előlegre jogosultak egyenlegének banki lezárásához nyissa meg a **Kötelezettségek** &gt; **Előlegre jogosultak** &gt; **Előlegre jogosultak** elemet. Kattintson az **Egyenleg** gombra a műveleti ablaktáblában, majd kattintson a **Zárás bankon keresztül** elemre. Adja meg az alábbi adatokat a **Zárás bankon keresztül** oldalon.

| Mező                    | Leírás |
|------------------------------|-------------------|
| **Fizetés dátuma**          | Adja meg a fizetés feladásának dátumát.|
| **Átutalandó összeg** | Adja meg a zárás közbeni egyenleget. Az **Egyenleg** képernyő **Összeg** mezőjében jelzett összeg alapértelmezés szerint látható. |
| **Automatikus**                | Jelölje be az **Automatikus** jelölőnégyzetet a **Kötelezettségek paraméterei** oldalon előre beállított napló létrehozásához és feladásához.|

## <a name="settle-advance-holder-balances-via-cash"></a>Előlegre jogosultak egyenlegeinek készpénzes kiegyenlítése
Előlegre jogosultak egyenlegeinek készpénzes kiegyenlítésekor az előlegre jogosultak egyenlegeit lezáró naplóbejegyzések egy bizonylatnaplóban jönnek létre. A naplóhoz tartozó kódot és a készpénzt a **Kötelezettségek paraméterei** oldal **Előlegre jogosultak** lapján állíthatja be. További információ: [Előlegre jogosultak](emea-advance-holders.md). Előlegre jogosultak egyenlegének készpénzes lezárásához nyissa meg a **Kötelezettségek** &gt; **Előlegre jogosultak** &gt; **Előlegre jogosultak** elemet. Kattintson az **Egyenleg** gombra a műveleti ablaktáblában, majd kattintson a **Zárás készpénzen keresztül** elemre. Adja meg az alábbi adatokat a **Zárás készpénzen keresztül** oldalon.

| Mező                    | Leírás
|------------------------------|-----------------|
| **Fizetés dátuma**          | Adja meg a fizetés feladásának dátumát.|
| **Átutalandó összeg** | Adja meg a zárás közbeni egyenleget. Az **Egyenleg** képernyő **Összeg** mezőjében jelzett összeg alapértelmezés szerint látható. |
| **Automatikus**                | Jelölje be az **Automatikus** jelölőnégyzetet a **Kötelezettségek paraméterei** oldalon előre beállított napló automatikus létrehozásához és feladásához.     |

A bizonylatnapló feldolgozása után, amennyiben az **Átutalandó összeg** mezőben lévő összeg negatív volt, az egyenlegek lezárásakor az előlegre jogosultakhoz kifizetési pénztárbizonylat jön létre. Amennyiben az **Átutalandó összeg** mezőben lévő összeg pozitív volt, bevételezési pénztárbizonylat jön létre.

## <a name="additional-resources"></a>További erőforrások

- [Előleg alkalmazotthoz (Kelet-Európa)](tasks/advance-payment-employee.md)


