---
title: Banki egyeztetési szabályok beállítása
description: Ez a témakör bemutatja, hogyan állíthat be egyeztetési szabályokat és egyeztetési szabálykészleteket a bank egyeztetési folyamatának segítése érdekében. Az egyeztetési szabályok olyan kritériumok készletei, melyek a banki kivonat sorainak és banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során.
author: ShylaThompson
manager: AnnBe
ms.date: 10/27/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32a416a79802a9f1d7a6e79705c3fd088124a141
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560428"
---
# <a name="set-up-bank-reconciliation-matching-rules"></a>Banki egyeztetési szabályok beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthat be egyeztetési szabályokat és egyeztetési szabálykészleteket a bank egyeztetési folyamatának segítése érdekében. Az egyeztetési szabályok olyan kritériumok készletei, melyek a banki kivonat sorainak és banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során.

Egyeztetési szabályokat és egyeztetési szabálykészleteket állíthat be a banki egyeztetési folyamat segítésére. Az egyeztetési szabály olyan kritériumok készlete, mely a banki kivonat sorainak és Microsoft Dynamics 365 for Finance and Operations banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során. Használja az **Egyeztetési szabályok** oldalt az egyeztetési szabályok beállítása. Egynél több egyeztetési szabályt lehet beállítani, és ezután létrehozhat egyeztetési szabálykészletet az **Egyeztetési szabálykészletek** oldalon. 

> [!NOTE] 
> A banki egyeztetési szabályokat elektronikus banki kivonatok egyeztetésére használhatja egy továbbfejlesztett banki egyeztetés során. 

Az **Egyeztetési szabályok** oldalon kiválaszthatja, hogy mely műveletek és kiválasztási szempontok legyenek használatban, amikor az egyeztetési szabályt futtatja. A **Műveletek** mezőcsoportban válassza ki, milyen műveletet kell elvégezni az egyeztetési folyamatban az egyeztetési szabály futtatása során.  

> [!NOTE] 
> A választott beállítás határozza meg a megjelenő mezőket.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Művelet**                         |                                                                                                                                                                                                                                                                                                               | **Kiválasztási feltételek művelet kiválasztásakor érhetőek el**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Egyeztetés banki bizonylattal**       | Hozzon létre feltételeket, melyek meghatározzák a banki bizonylatok és a banki kivonatok sorainak egyeztetési módját az egyeztetési szabály futtatása során a **Banki egyeztetési munkalap** lapon. A tranzakciósorokat a gyorslapokon megadott kiegészítő kritériumok alapján választja ki a rendszer.                                | **1. lépés: Adja meg az egyeztetési szabályt** – A Finance and Operations banki tranzakciókhoz kapcsolódó banki kivonatok meghatározásához válasszon ki feltételeket. **2. lépés (nem kötelező): Válassza ki az egyeztetési szabályokkal szemben futtatandó kimutatássorokat**  Használjon szűrőt a szabályokkal szemben futattandó kimutatássorokon.                                                                                                                                                                                                                                                                                                               |
| **Sztornírozási kivonatsorok törlése** | Hozzon létre olyan feltételeket, melyek meghatározzák a sztornírozási kivonatsorok eltávolítását a **Banki egyeztetési munkalap** oldalon az egyeztetési szabály futtatása során. Ez a lehetőség használható akkor, amikor banki hiba jelentkezik, és két banki kivonatsor található az importált a banki kivonaton, és össze kell hangolni a sorokat. | **1. lépés**: **Sztornírozási kivonatsorok keresése** – Adjon meg kiválasztási kritériumokat a banki kivonat sztornírozási sorainak kiválasztásához. Például csak a csekkek kiválasztásához válassza ki a **Banki tranzakció kódja** elemet a Mező mezőben, válassza ki a plusz jelet (+) az **Kezelő** mezőben, és írja be a **Csekkek** szót az Érték mezőbe. **2. lépés: Eredeti kivonatsorok keresése** – Olyan kiválasztási feltételeket is hozzáadhat, melyek a banki bizonylatsorokat hozzáillesztik a banki kivonatsorokhoz. **3. lépés: A Finance and Operations banki tranzakciók megkeresése**– Olyan kiválasztási feltételeket is hozzáadhat, melyek a Finance and Operations banki tranzakciókat hozzáillesztik a banki kivonatsorokhoz. |
| **Új tranzakciók megjelölése**          | Hozzon létre olyan feltételeket, melyek meghatározzák az új tranzakciók megjelölését a **Banki egyeztetési munkalap** oldalon az egyeztetési szabály futtatása során.                                                                                                                                                                 | **1. lépés: Kivonatsorok keresése**– Adjon meg választás mezőket, amelyek a meghatározzák mely banki kivonatsorokat kell kiválasztani a **Banki egyeztetési munkalap** oldalon. **2. lépés: A Finance and Operations** megkeresése – Hozzáadhat kiválasztási feltételeket a bankibizonylat-sorok keresésére. Ha banki bizonylat nem áll rendelkezésre, egy bizonylat sor lesz megjelölve új tranzakcióként.                                                                                                                                                                                                                                             |








