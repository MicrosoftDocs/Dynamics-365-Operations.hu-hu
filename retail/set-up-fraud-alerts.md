---
title: "Csalási figyelmeztetések beállítása"
description: "Ez a témakör ismerteti a szabályok beállítását az ügyfélszolgálati munkatársak figyelmeztetésére az esetleg csaló információról a rendelések feldolgozása során. Meghatározhat specifikus kódokat, hogy automatikusan vagy manuálisan várakoztassa a gyanús rendeléseket."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fabb7ee23e90feca818bebfa29c7048987193e4c
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-fraud-alerts"></a>Csalási figyelmeztetések beállítása

[!include[banner](includes/banner.md)]


Ez a témakör ismerteti a szabályok beállítását az ügyfélszolgálati munkatársak figyelmeztetésére az esetleg csaló információról a rendelések feldolgozása során. Meghatározhat specifikus kódokat, hogy automatikusan vagy manuálisan várakoztassa a gyanús rendeléseket. 

Mielőtt beállítja és használja a csalásellenőrzési szabályokat, engedélyeznie kell a csalásellenőrzést, és adja meg az alapvető csalásellenőrző értékeket a hívásközpont paramétereinél. A csalási szabályok két típusa a következő:

-   A **statikus szabályok** egy konkrét értéket használnak (például egy tiltólistára tett telefonszám).
-   A **dinamikus szabályok** változókból és feltételekből állhatnak.

Dinamikus szabály létrehozása előtt létre kell hoznia a változókat és a feltételeket, amelyek meghatározzák, kire vonatkozik a szabály, és a szabályt mikor kell alkalmazni. Például szeretne létrehozni egy olyan szabályt, amely megköveteli, hogy, ha a 1202-es vevő elhelyez egy értékesítési rendelést, amely 1000,00-et vagy többet ér, akkor az értékesítési rendelést várakoztatni kell addig, amíg a vevői kifizetés igazolható nem lesz. Ebben a példában a változók a 1202-es vevő és az 1000,00 összrendelés. A feltétel szerint ha a 1202-es vevő felad egy rendelést, és a rendelés teljes összege 1000,00 vagy több, az értékesítési rendelést várakoztatni kell, amíg a vevői kifizetés ellenőrzése megtörténik.



