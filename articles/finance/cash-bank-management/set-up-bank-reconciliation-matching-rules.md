---
title: Banki egyeztetési szabályok beállítása
description: Ez a témakör bemutatja, hogyan állíthat be egyeztetési szabályokat és egyeztetési szabálykészleteket a bank egyeztetési folyamatának segítése érdekében. Az egyeztetési szabályok olyan kritériumok készletei, melyek a banki kivonat sorainak és banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során.
author: panolte
manager: AnnBe
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39b03bd0834b5142d21a4ab17a7d7ad18c4a574b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231518"
---
# <a name="set-up-bank-reconciliation-matching-rules"></a>Banki egyeztetési szabályok beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthat be egyeztetési szabályokat és egyeztetési szabálykészleteket a bank egyeztetési folyamatának segítése érdekében. Az egyeztetési szabályok olyan kritériumok készletei, melyek a banki kivonat sorainak és banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során.

Egyeztetési szabályokat és egyeztetési szabálykészleteket állíthat be a banki egyeztetési folyamat segítésére. Az egyeztetési szabály olyan kritériumok készlete, mely a banki kivonat sorainak és Dynamics 365 Finance banki bizonylat sorainak szűrésére szolgálnak az egyeztetési folyamat során. Használja az **Egyeztetési szabályok** oldalt az egyeztetési szabályok beállítása. Egynél több egyeztetési szabályt lehet beállítani, és ezután létrehozhat egyeztetési szabálykészletet az **Egyeztetési szabálykészletek** oldalon. 

> [!NOTE] 
> A banki egyeztetési szabályokat elektronikus banki kivonatok egyeztetésére használhatja egy továbbfejlesztett banki egyeztetés során. 

Az **Egyeztetési szabályok** oldalon kiválaszthatja, hogy mely műveletek és kiválasztási szempontok legyenek használatban, amikor az egyeztetési szabályt futtatja. A **Műveletek** mezőcsoportban válassza ki, milyen műveletet kell elvégezni az egyeztetési folyamatban az egyeztetési szabály futtatása során.  

Alapértelmezés szerint a egyeztetési szabályok megtalálják az első olyan banki dokumentumot, amely megfelel az egyeztetési szabály feltételeinek. Ha több banki dokumentum teljesíti a szabály feltételeit, akkor a manuális egyeztetést igénylő paramétert be lehet kapcsolni a **készpénz és a bank kezelése > Beállítások > Készpénz és banki egyeztetés paraméterei> Banki egyeztetés > Manuális egyeztetést megkövetelése, amikor a speciális banki egyeztetési szabályok több olyan dokumentumot találnak, amelyek megfelelnek az összegnek**.

> [!NOTE] 
> A választott beállítás határozza meg a megjelenő mezőket.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Művelet**                         |                                                                                                                                                                                                                                                                                                               | **Kiválasztási feltételek művelet kiválasztásakor érhetőek el**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Egyeztetés banki bizonylattal**       | Hozzon létre feltételeket, melyek meghatározzák a banki bizonylatok és a banki kivonatok sorainak egyeztetési módját az egyeztetési szabály futtatása során a **Banki egyeztetési munkalap** lapon. A tranzakciósorokat a gyorslapokon megadott kiegészítő kritériumok alapján választja ki a rendszer.                                | **1. lépés: Adja meg az egyeztetési szabályt** – A Finance banki tranzakciókhoz kapcsolódó banki kivonatok meghatározásához válasszon ki egy feltételt. **2. lépés (nem kötelező): Válassza ki az egyeztetési szabályokkal szemben futtatandó kimutatássorokat**  Használjon szűrőt a szabályokkal szemben futattandó kimutatássorokon.                                                                                                                                                                                                                                                                                                               |
| **Sztornírozási kivonatsorok törlése** | Hozzon létre olyan feltételeket, melyek meghatározzák a sztornírozási kivonatsorok eltávolítását a **Banki egyeztetési munkalap** oldalon az egyeztetési szabály futtatása során. Ez a lehetőség használható akkor, amikor banki hiba jelentkezik, és két banki kivonatsor található az importált a banki kivonaton, és össze kell hangolni a sorokat. | **1. lépés**: **Sztornírozási kivonatsorok keresése** – Adjon meg kiválasztási kritériumokat a banki kivonat sztornírozási sorainak kiválasztásához. Például csak a csekkek kiválasztásához válassza ki a **Banki tranzakció kódja** elemet a Mező mezőben, válassza ki a plusz jelet (+) az **Kezelő** mezőben, és írja be a **Csekkek** szót az Érték mezőbe. **2. lépés: Eredeti kivonatsorok keresése** – Olyan kiválasztási feltételeket is hozzáadhat, melyek a banki bizonylatsorokat hozzáillesztik a banki kivonatsorokhoz. **3. lépés: A Finance banki tranzakciók megkeresése** – Olyan kiválasztási feltételeket is hozzáadhat, melyek a Finance banki tranzakciókat hozzáillesztik a banki kivonatsorokhoz. |
| **Új tranzakciók megjelölése**          | Hozzon létre olyan feltételeket, melyek meghatározzák az új tranzakciók megjelölését a **Banki egyeztetési munkalap** oldalon az egyeztetési szabály futtatása során.                                                                                                                                                                 | **1. lépés: Kivonatsorok keresése**– Adjon meg választás mezőket, amelyek a meghatározzák mely banki kivonatsorokat kell kiválasztani a **Banki egyeztetési munkalap** oldalon. **2. lépés: A Finance and Operations** megkeresése – Hozzáadhat kiválasztási feltételeket a bankibizonylat-sorok keresésére. Ha banki bizonylat nem áll rendelkezésre, egy bizonylat sor lesz megjelölve új tranzakcióként.                                                                                                                                                                                                                                             |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]