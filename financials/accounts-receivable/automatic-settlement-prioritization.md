---
title: "Automatikus kiegyenlítés és rangsorolás"
description: "Ez a cikk bemutatja, hogyan kerülnek rendezésre a tranzakciók akkor, hogyha az Esedékes számlák paraméterei oldal Automatikus rendezés opcióját választja. Bemutatja továbbá hogyan használható az automatikus kiegyenlítés a fizetési prioritással együtt."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14531
ms.assetid: e7837cf6-ec69-44b4-8d47-eba38d5c7b1f
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: a751973b49febd6925267d00fb1d2c72114f86b0
ms.lasthandoff: 03/31/2017


---

# <a name="automatic-settlement-and-prioritization"></a>Automatikus kiegyenlítés és rangsorolás

[!include[banner](../includes/banner.md)]


Ez a cikk bemutatja, hogyan kerülnek rendezésre a tranzakciók akkor, hogyha az Esedékes számlák paraméterei oldal Automatikus rendezés opcióját választja. Bemutatja továbbá hogyan használható az automatikus kiegyenlítés a fizetési prioritással együtt.

A kifizetések számlákkal, vagy egyéb tranzakciókkal történő kiegyenlítésekor két lehetőség közül választhat. Kiválaszthatja manuálisan a kiegyenlítendő tranzakciókat, vagy a Microsoft Dynamics 365 for Operations automatikusan kiválasztja a tranzakciókat az automatikus kiegyenlítési funkciót alkalmazva. Az automatikus kiegyenlítés feldolgozását testreszabhatja a **Kiegyenlítés rangsorolása** lehetőséggel. Ezek a beállítások részei a kiegyenlítési paraméterek modulnak, amelyek a **Kinnlevőségek paraméterei** lapon vannak meghatározva. A tranzakciók automatikus kiegyenlítési módjai eltérhetnek, attól függően, hogy milyen módszert használ az automatikus kiegyenlítéshez. A következő módszerek állnak rendelkezésre:

-   Felhasználó által definiált kiegyenlítési rangsor
-   alapértelmezett automatikus kiegyenlítés

Az alábbi szakaszok bemutatják, hogy az egyes módszerek esetén hogyan történik a tranzakciók kiegyenlítése.

## <a name="example-transactions"></a>Példák tranzakciókra
A cikk későbbi kiegyenlítési példái az alábbi tranzakciókon alapszanak. Minden tranzakció a 2050. vevőre vonatkozik.

| Tranzakció   | Dátum        | Összeg | Készpénzfizetési engedmény feltételei | Készpénzfizetési engedmény dátuma | Megjegyzések                                                                                                                                                                                      |
|---------------|-------------|--------|---------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1. számla     | Augusztus 15.   | 100,00 | 2%14, nettó 30        | Augusztus 29.          |                                                                                                                                                                                               |
| 2. számla     | Szeptember 1. | 250,00 | 2%14, nettó 30        | Szeptember 15.       |                                                                                                                                                                                               |
| 3. számla     | Október 15.  | 500,00 | 2% 14/ nettó 30        | Október 29.         |                                                                                                                                                                                               |
| Kamatlevél | Október 15.  | 7:00   |                     |                    | A kamatlevél az 1. és a 2. számlára vonatkozik. Az összeg kiszámolása során a 30 napja vagy annál régebben lejárt számlák esetében 2 százalékos kamat kerül felszámolásra. Példa: 0,02 × (100,00 + 250,00) = 7,00. |

## <a name="userdefined-settlement-priority"></a>Felhasználó által definiált kiegyenlítési rangsor
Ha a **Rangsor használata automatikus kiegyenlítésekhez** résznél az **Igen** lehetőséget adja meg a **Kinnlevőségek paraméterei** oldalon, a kiegyenlítési rangsor, amelyet a **Kiegyenlítési rangsor** lapon ad meg, használatos akkor, ha a tranzakció automatikus kiegyenlítésre vannak beállítva. Ebben a példában a következő kiegyenlítési rangsor van meghatározva:

1.  Tranzakció típusa
    -   Kifizetési illetékek
    -   Fizetési felszólítások
    -   Kamatlevelek
    -   Számlák

2.  Tranzakció dátuma, Növekvő sorrendben
3.  Bizonylat

Ha felad egy 700,00 értékű kifizetést október 25-én, a tranzakciók a következős sorrendben lesznek kiegyenlítve.

| Bizonylat       | Dátum       | Számla | Összeg a tranzakció pénznemében. | Kiegyenlítendő összeg | Egyenleg | Pénznem |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Kamatlevél | 2015/15/10 |         | 7:00                           | 7:00             | 0,00    | dollár      |
| 1. számla     | 2015/15/8  | 10001   | 100,00                         | 100,00           | 0,00    | dollár      |
| 2. számla     | 2015/1/9   | 10002   | 250,00                         | 250,00           | 0,00    | dollár      |
| 3. számla     | 2015/15/10 |         | 500,00                         | 343.00           | 157.00  | dollár      |

## <a name="default-automatic-settlement"></a>alapértelmezett automatikus kiegyenlítés
Ha nincsen felhasználó által definiált kiegyenlítési rangsor, a tranzakciók a határidejük alapján automatikusan kiválasztódnak kiegyenlítésre. A kiegyenlített tranzakcióknak, és az annak a kiegyenlítésére használt tranzakció pénznemének azonosnak kell lennie. Ha felad egy 700,00 értékű kifizetést október 25-én, a következő tranzakciók automatikusan ki lesznek jelölve kiegyenlítésre.

| Bizonylat       | Dátum       | Számla | Összeg a tranzakció pénznemében. | Kiegyenlítendő összeg | Egyenleg | Pénznem |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| 1. számla     | 2015/15/8  | 10001   | 100,00                         | 100,00           | 0,00    | dollár      |
| 2. számla     | 2015/1/9   | 10002   | 250,00                         | 250,00           | 0,00    | dollár      |
| 3. számla     | 2015/15/10 |         | 500,00                         | 350.00           | 150,00  | dollár      |
| Kamatlevél | 2015/15/10 |         | 7:00                           | 0,00             | 0,00    | dollár      |






