---
title: "Banki egyeztetési szabályok beállítása"
description: "Ez a cikk bemutatja, hogyan állíthat be egyeztetési szabályokat és egyeztetési szabálykészleteket a bank egyeztetési folyamatának segítése érdekében. Az egyeztetési szabályok olyan kritériumok készletei, melyek a banki kivonat sorainak és banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: e4c07a6afb90535c57f372d5b850919b5b34aaa4
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bank-reconciliation-matching-rules"></a>Banki egyeztetési szabályok beállítása

Ez a cikk bemutatja, hogyan állíthat be egyeztetési szabályokat és egyeztetési szabálykészleteket a bank egyeztetési folyamatának segítése érdekében. Az egyeztetési szabályok olyan kritériumok készletei, melyek a banki kivonat sorainak és banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során.

Egyeztetési szabályokat és egyeztetési szabálykészleteket állíthat be a banki egyeztetési folyamat segítésére. Egy egyeztetési szabály egy banki kivonat sorainak és a Microsoft Dynamics 365 banki műveletek tranzakciósorok szűrése az egyeztetés során használt feltételek. Használja az **Egyeztetési szabályok** oldalt az egyeztetési szabályok beállítása. Egynél több egyeztetési szabályt lehet beállítani, és ezután létrehozhat egyeztetési szabálykészletet az **Egyeztetési szabálykészletek** oldalon. 

> [!NOTE] 
> Banki egyeztetési szabályok használják, ha az előleg banki egyeztetés segítségével egyezteti az elektronikus banki kivonat. 

Az **Egyeztetési szabályok** oldalon kiválaszthatja, hogy mely műveletek és kiválasztási szempontok legyenek használatban, amikor az egyeztetési szabályt futtatja. A a **műveletek** mezőcsoportban, válasszon a műveletet, amely az egyeztetés során az egyeztetési szabály futtatásakor történik.  

> [!NOTE] 
> A választott beállítás határozza meg, hogy a megjelenő mezők.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Művelet**                         |                                                                                                                                                                                                                                                                                                               | **Kiválasztási feltételek művelet kiválasztásakor érhetőek el**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Egyeztetés banki bizonylattal **       | Hozzon létre feltételeket, melyek meghatározzák a banki bizonylatok és a banki kivonatok sorainak egyeztetési módját az egyeztetési szabály futtatása során a **Banki egyeztetési munkalap** lapon. A tranzakciósorokat a gyorslapokon megadott kiegészítő kritériumok alapján választja ki a rendszer.                                | **1. lépés: Határozza meg az egyeztetési szabály** – adja meg, mely bankszámlakivonatok kell nem feleltethető meg Dynamics 365 műveletek banki tranzakciókhoz criterias kiválasztása. **2. lépés (nem kötelező): Válassza ki az egyeztetési szabályokkal szemben futtatandó kimutatássorokat**  Használjon szűrőt a szabályokkal szemben futattandó kimutatássorokon.                                                                                                                                                                                                                                                                                                               |
| **Sztornírozási kivonatsorok törlése ** | Hozzon létre olyan feltételeket, melyek meghatározzák a sztornírozási kivonatsorok eltávolítását a **Banki egyeztetési munkalap** oldalon az egyeztetési szabály futtatása során. Ez a lehetőség használható akkor, amikor banki hiba jelentkezik, és két banki kivonatsor található az importált a banki kivonaton, és össze kell hangolni a sorokat. | **1. lépés**:** Sztornírozási kivonatsorok keresése **– Adjon meg kiválasztási kritériumokat a banki kivonat sztornírozási sorainak kiválasztásához. Például csak a csekkek kiválasztásához válassza ki a **Banki tranzakció kódja** elemet a Mező mezőben, válassza ki a plusz jelet (+) az **Kezelő** mezőben, és írja be a **Csekkek** szót az Érték mezőbe. **2. lépés: Eredeti kivonatsorok keresése** – Olyan kiválasztási feltételeket is hozzáadhat, melyek a banki bizonylatsorokat hozzáillesztik a banki kivonatsorokhoz. ** 3. lépés: Dynamics 365 található műveletek banki tranzakciók ** – Dynamics 365 műveletek banki tranzakciók banki utasítás sorok megfelelő kiválasztási szempontokat is hozzáadhat. |
| **Mark new transactions**          | Hozzon létre olyan feltételeket, melyek meghatározzák az új tranzakciók megjelölését a **Banki egyeztetési munkalap** oldalon az egyeztetési szabály futtatása során.                                                                                                                                                                 | **1. lépés: Kivonatsorok keresése **– Adjon meg választás mezőket, amelyek a meghatározzák mely banki kivonatsorokat kell kiválasztani a **Banki egyeztetési munkalap** oldalon. ** 2. lépés: Dynamics 365 található műveletek banki tranzakciók ** – keresés banki bizonylat sorokhoz kiválasztási szempontokat is hozzáadhat. Ha banki bizonylat nem áll rendelkezésre, egy bizonylat sor lesz megjelölve új tranzakcióként.                                                                                                                                                                                                                                             |

 





