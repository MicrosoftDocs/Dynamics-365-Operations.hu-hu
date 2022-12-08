---
title: Banki egyeztetés egyeztetési szabályainak beállítása
description: Ez a cikk bemutatja, hogyan állíthat be egyeztetési szabályokat és egyeztetési szabálykészleteket a bank egyeztetési folyamatának segítése érdekében. Az egyeztetési szabályok olyan kritériumok készletei, melyek a banki kivonat sorainak és banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során.
author: angelad116
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: kfend
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac5ab5e2bcb9a63bb52d5a74bd5e4b5db51ba603
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803937"
---
# <a name="set-up-bank-reconciliation-matching-rules"></a>Banki egyeztetés egyeztetési szabályainak beállítása

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan állíthat be egyeztetési szabályokat és egyeztetési szabálykészleteket a bank egyeztetési folyamatának segítése érdekében. Az egyeztetési szabályok olyan kritériumok készletei, melyek a banki kivonat sorainak és banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során.

Egyeztetési szabályokat és egyeztetési szabálykészleteket állíthat be a banki egyeztetési folyamat segítésére. Az egyeztetési szabály feltételek halmaza, amely a banki kivonatsorok és a Dynamics 365 Pénzügyi banki tranzakciósorok szűrésére használható az egyeztetési folyamat során. Használja az **Egyeztetési szabályok** oldalt az egyeztetési szabályok beállítása. Egynél több egyeztetési szabályt lehet beállítani, és ezután létrehozhat egyeztetési szabálykészletet az **Egyeztetési szabálykészletek** oldalon. 

> [!NOTE] 
> A banki egyeztetési szabályokat elektronikus banki kivonatok egyeztetésére használhatja egy továbbfejlesztett banki egyeztetés során. 

Az **Egyeztetési szabályok** oldalon kiválaszthatja, hogy mely műveletek és kiválasztási szempontok legyenek használatban, amikor az egyeztetési szabályt futtatja. A **Műveletek** mezőcsoportban válassza ki, milyen műveletet kell elvégezni az egyeztetési folyamatban az egyeztetési szabály futtatása során.  

Alapértelmezés szerint a egyeztetési szabályok megtalálják az első olyan banki dokumentumot, amely megfelel az egyeztetési szabály feltételeinek. Ha több banki dokumentum teljesíti a szabály feltételeit, akkor a manuális egyeztetést igénylő paramétert be lehet kapcsolni a **készpénz és a bank kezelése > Beállítások > Készpénz és banki egyeztetés paraméterei> Banki egyeztetés > Manuális egyeztetést megkövetelése, amikor a speciális banki egyeztetési szabályok több olyan dokumentumot találnak, amelyek megfelelnek az összegnek**.

> [!NOTE] 
> A választott beállítás határozza meg a megjelenő mezőket.

| Művelet | Leírás   | Kiválasztási feltételek művelet kiválasztásakor érhetőek el     |
|--------|---------------|----------------------------------------------------------|
| **Egyeztetés banki bizonylattal**       | Hozzon létre feltételeket, melyek meghatározzák a banki bizonylatok és a banki kivonatok sorainak egyeztetési módját az egyeztetési szabály futtatása során a **Banki egyeztetési munkalap** lapon. A tranzakciósorokat a gyorslapokon megadott kiegészítő kritériumok alapján választja ki a rendszer. | <ul><li>**1. lépés: Adja meg az egyeztetési szabályt** – A Finance banki tranzakciókhoz kapcsolódó banki kivonatok meghatározásához válasszon ki egy feltételt.</li><li> **2. lépés (nem kötelező): Válassza ki az egyeztetési szabályokkal szemben futtatandó kimutatássorokat**  Használjon szűrőt a szabályokkal szemben futattandó kimutatássorokon.</li></ul>                                       |
| **Sztornírozási kivonatsorok törlése** | Hozzon létre olyan feltételeket, melyek meghatározzák a sztornírozási kivonatsorok eltávolítását a **Banki egyeztetési munkalap** oldalon az egyeztetési szabály futtatása során. Ez a lehetőség használható akkor, amikor banki hiba jelentkezik, és két banki kivonatsor található az importált a banki kivonaton, és össze kell hangolni a sorokat. |<ul><li> **1. lépés**: **Sztornírozási kivonatsorok keresése** – Adjon meg kiválasztási kritériumokat a banki kivonat sztornírozási sorainak kiválasztásához. Ha például csak a csekkeket választja, **·**  **válassza** ki a Banki tranzakció kódját a Mező mezőben, válassza a pluszjelet (+) **a** Kezelő mezőben, **·**  **majd írja be a Csekkek értéket az Érték mezőbe.**  </li><li>**2. lépés: Eredeti kivonatsorok keresése** – Olyan kiválasztási feltételeket is hozzáadhat, melyek a banki bizonylatsorokat hozzáillesztik a banki kivonatsorokhoz. </li><li>**3. lépés: A Finance banki tranzakciók megkeresése** – Olyan kiválasztási feltételeket is hozzáadhat, melyek a Finance banki tranzakciókat hozzáillesztik a banki kivonatsorokhoz.</li></ul>  |
| **Új tranzakciók megjelölése**          | Hozzon létre olyan feltételeket, melyek meghatározzák az új tranzakciók megjelölését a **Banki egyeztetési munkalap** oldalon az egyeztetési szabály futtatása során.                                                                                                                                                                 | <ul><li>**1. lépés: Kivonatsorok keresése**– Adjon meg választás mezőket, amelyek a meghatározzák mely banki kivonatsorokat kell kiválasztani a **Banki egyeztetési munkalap** oldalon.</li><li> **2. lépés: Pénzügyek és műveletek keresése**  – kiválasztási feltételeket adhat meg a banki bizonylatsorok keresésére. Ha banki bizonylat nem áll rendelkezésre, egy bizonylat sor lesz megjelölve új tranzakcióként. </li></ul>         |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

