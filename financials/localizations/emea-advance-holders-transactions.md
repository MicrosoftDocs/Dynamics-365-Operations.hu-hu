---
title: "Előlegre jogosult tranzakciói"
description: "Útmutató a Microsoft Dynamics 365 műveletek előlegre jogosult tranzakcióinak dolgozni."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorkerAdvHolderTableListPage_RU
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 262554
ms.assetid: 84ff97bb-ae21-4d6d-8160-9325f64134ce
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: c819fbbb4a68dd5b8b192416fedb34827bbf3823
ms.lasthandoff: 03/31/2017


---

# <a name="advance-holder-transactions"></a>Előlegre jogosult tranzakciói

Útmutató a Microsoft Dynamics 365 műveletek előlegre jogosult tranzakcióinak dolgozni.

Előlegre jogosultak előlegre jogosult fiókok segítségével lehet feladni a munkavállalók tranzakciók. A megadott minden előlegre jogosult munkavállaló azonosító minden előlegre jogosult tranzakcióinak nyomon követésére használható. Ezt a számot a Számlaszám az előlegre jogosult tranzakcióinak olvassa a **a főkönyvi naplók** és **előlegre jogosult tranzakciói** lapok.

## <a name="create-and-post-a-purchase-order-with-advance-holder-details"></a>Hozza létre és könyvelje a beszerzési rendelés előleg jogosultja részletes
Beszerzési rendelésekkel kapcsolatos általános tudnivalókért tanulmányozza [beszerzési rendelés áttekintése](/manufacturing/procurement/purchase-order-overview). Szállítói számla létrehozása és könyvelt előleg jogosultja részletes, ha az előleg jogosultja egyenlegek az alkalmazott mérlegszámlára helyett a szállítói egyenleg számlára könyveli. Előlegre jogosult részletek hozzáadása egy beszerzési rendelés, tegye a következőket:

-   A a **a fizetési feltételek** mezőjében a **ár- és** szakaszban, jelölje be a fizetési feltételek. <!---For more information about **Terms of payment**, see [Define vendor payment terms](http://ax.help.dynamics.com/en/wiki/define-vendor-payment-terms/).-->Jelölje be a fizetési feltétel, amelynek a **az előlegre jogosulttól** jelölve a **a fizetési feltételek** oldalon. Előlegre jogosultak a fizetési feltételek beállításával kapcsolatos további tudnivalókért lásd: [előlegre jogosultak](emea-advance-holders.md).
-   A a **előlegre jogosult** mezőjében a **ár- és** gyorslapon jelölje be az előleg jogosultja a beszerzési rendelés.

A beszerzési rendelések feladási folyamatot hoz létre, két ellentétes összegeket szállítói tranzakciók és egy előlegre jogosult tranzakcióra. Előleg jogosultja részletek nélkül csak egy szállítói tranzakció jön létre.

## <a name="settle-advance-holder-balances-via-a-bank"></a>Előlegre jogosult egyenlegeinek kiegyenlítése egy banki átutalással
Előleg jogosultja egyenlegek a banki átutalással egyenlíti ki, ha az előleg jogosultja egyenlegek záró naplóbejegyzéseinek a főkönyvi naplóban jönnek létre. Állíthatja be a kódot a napló és a bank a **előlegre jogosultak** a szakasz a **kötelezettségek paramétereinek** oldalon. További tudnivalókért lásd: [előlegre jogosultak](emea-advance-holders.md). Előlegre jogosult egyenlege a banki átutalással lezárásához nyissa meg a **kötelezettségek**&gt;**előlegre jogosultak**&gt;**előlegre jogosultak**. Kattintson a **mérleg** a műveletpanel gombra, majd a **szoros banki átutalással**. Adja meg az alábbi adatokat a **szoros banki átutalással** oldalon.

| Mező                    | Leírás |
|------------------------------|-------------------|
| **Date of payment**          | A dátum, amely a kifizetést kell feladni.|
| **Átutalandó összeg** | A közben a záró egyenleg összegét adja meg. A jelzett összeg a **összeg** mezőjében a **mérleg** alapértelmezés szerint megjelenik a képernyőn. |
| **Automatic**                | Válassza ki a **automatikus** készletet hozhat létre, és a napló könyvelése jelölőnégyzetet a **fizetendő paramétereinek** oldalon.|

## <a name="settle-advance-holder-balances-via-cash"></a>Készpénzes előlegre jogosult egyenlegeinek kiegyenlítése
Ha az előleg jogosultjának egyenlegek készpénzes egyenlíti ki, az előleg jogosultja egyenlegek záró naplóbejegyzéseinek bizonylat a naplóban jönnek létre. Állíthatja be a kódot a napló és a pénz a **előlegre jogosultak** fülre, a **fizetendő paramétereinek** oldalon. További tudnivalókért lásd: [előlegre jogosultak](emea-advance-holders.md). Előlegre jogosult egyenlege készpénzes lezárásához nyissa meg a **kötelezettségek**&gt;**előlegre jogosultak**&gt;**előlegre jogosultak**. Kattintson a **mérleg** a műveletpanel gombra, majd a **készpénzes szoros**. Adja meg az alábbi adatokat a **készpénzes szoros** oldalon.

| Mező                    | Leírás
|------------------------------|-----------------|
| **Date of payment**          | A dátum, amely a kifizetést kell feladni.|
| **Átutalandó összeg** | A közben a záró egyenleg összegét adja meg. A jelzett összeg a **összeg** mezőjében a **mérleg** alapértelmezés szerint megjelenik a képernyőn. |
| **Automatic**                | Válassza ki a **automatikus** készlet jelölőnégyzetet, ha a napló létrehozása és feladása automatikusan egy, a **fizetendő paramétereinek** oldalon.     |

A slip után napló feldolgozása, ha az összeg a **átutalandó összeg** mező negatív volt, a készpénz-kifizetési bizonylathoz keletkezik az előlegre jogosult az egyenlegek bezárásakor. Ha az összeg a **átutalandó összeg** mezőben pozitív volt, a bevételezési pénztárbizonylat jön létre.


