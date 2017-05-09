---
title: "Szállítási ütemezések"
description: "A szállítási ütemezések lehetővé teszik a rendeléssor mennyiségének nyomon követését, amikor több szállítást használ egyetlen értékesítési rendeléshez, értékesítési ajánlathoz vagy beszerzési rendeléshez."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: fbada697060c823b0afdb72d1c0cfd8703f4d527
ms.lasthandoff: 03/31/2017


---

# <a name="delivery-schedules"></a>Szállítási ütemezések

[!include[banner](../includes/banner.md)]


A szállítási ütemezések lehetővé teszik a rendeléssor mennyiségének nyomon követését, amikor több szállítást használ egyetlen értékesítési rendeléshez, értékesítési ajánlathoz vagy beszerzési rendeléshez.

A szállítási ütemezés akkor használatos, ha egy rendeléshez vagy ajánlati sorhoz tartozó teljes mennyiséget több részletben kell szállítani. Az egyes szállítmányokat szállítási sorok jelölik. Két vagy több szállítási sor alkot egy szállítási ütemezést. A szállítási sorok különböző szállítási dátumokkal, mennyiségekkel, szállítási módokkal és tárolási dimenziókkal rendelkezhetnek, például hely és raktár.  

**Példa szállítási ütemezésre**

|                                   |                                          |
|-----------------------------------|------------------------------------------|
| Teljes rendelés (eredeti rendelési sor) | 600 szék                               |
| Kért kézbesítési ütemezés       | Havonta 100 szék                     |
| Kért kézbesítési időkeret | 6 hónapon keresztül, minden hónap első napján |

Ebben az esetben a vevő a 600 szék kiszállítását 100 darabos kötegekben kérte, 6 hónap alatt A szállítási követelmények nyomon követéséhez szállítási ütemezést kell létrehozni. A szállítási ütemezés lapon hat külön szállítás sort kell létrehozni. Minden egyes kézbesítési sor 100 széket tartalmaz, és jelzi az adott 100 szék szállítási dátumát. Ebben az esetben minden sor hat egymást követő hónapig minden hónap elsején lesz elindítva.  

A szállítási ütemezés létrehozásakor az eredeti rendelési sor típusa automatikusan a **Rendeléssor több szállítással** lehetőségre módosul. Egy ilyen típusú sorra a rendszer kereskedelmi sorként hivatkozik és egy ikon jelzi. A kézbesítési sort egy másik ikon jelzi. Ha módosítja egy kézbesítési sorban mennyiségét, a kereskedelmi sor a szállítási ütemezés teljes mennyiségére frissül. Ha egy kereskedelmi megállapodás egy teljes engedményt határozott meg a rendeléshez, a szállítási ütemezés biztosítja, hogy a rendelés jogosult legyen a teljes rendelési engedményre, akkor is, ha a rendelés több kiszállításra oszlik.  

A szállítási ütemezéssel rendelkező rendeléseket a rendszer a szállítási sorok szerint dolgozza fel. A feldolgozás magában foglalja a csomagjegyzékek, termékbevételezések és a számlázás feladását.  

A szállítási ütemezéssel rendelkező rendelések és árajánlatok nyomtatott anyagai csak a szállítási sorokat tartalmazzák. Nem mutatják az eredeti sorokat (kereskedelmi sorokat). **Megjegyzés:** Ezen kívül csak a szállítási sorok jelennek meg a rendszerben a műveletek végrehajtása során:

-   Feladás
-   Oldalak másolása
-   Tallózással keresse meg a listalapokat és jelentéseket

Ha megerősíti az értékesítési ajánlatokat, az ebből származó értékesítési jelentések az egész szállítási ütemezést mutatják, még a több kiszállításból álló rendelési sorokat is. Ezenkívül a teljes szállítási ütemezés megjelenik az összes fő lapon, például értékesítési rendelések, értékesítési ajánlatok és beszerzési rendelések lapokon.




