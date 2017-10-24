---
title: "Csalási figyelmeztetések beállítása"
description: "Ez a témakör ismerteti a szabályok beállítását az ügyfélszolgálati munkatársak figyelmeztetésére az esetleg csaló információról a rendelések feldolgozása során. Meghatározhat specifikus kódokat, hogy automatikusan vagy manuálisan várakoztassa a gyanús rendeléseket."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 09d80015298c3d0219b6ffb290dc456990536a62
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-fraud-alerts"></a>Csalási figyelmeztetések beállítása

[!include[banner](includes/banner.md)]


Ez a témakör ismerteti a szabályok beállítását az ügyfélszolgálati munkatársak figyelmeztetésére az esetleg csaló információról a rendelések feldolgozása során. Meghatározhat specifikus kódokat, hogy automatikusan vagy manuálisan várakoztassa a gyanús rendeléseket. 

Mielőtt beállítja és használja a csalásellenőrzési szabályokat, engedélyeznie kell a csalásellenőrzést, és adja meg az alapvető csalásellenőrző értékeket a hívásközpont paramétereinél. A csalási szabályok két típusa a következő:

-   A **statikus szabályok** egy konkrét értéket használnak (például egy tiltólistára tett telefonszám).
-   A **dinamikus szabályok** változókból és feltételekből állhatnak.

Dinamikus szabály létrehozása előtt létre kell hoznia a változókat és a feltételeket, amelyek meghatározzák, kire vonatkozik a szabály, és a szabályt mikor kell alkalmazni. Például szeretne létrehozni egy olyan szabályt, amely megköveteli, hogy, ha a 1202-es vevő elhelyez egy értékesítési rendelést, amely 1000,00-et vagy többet ér, akkor az értékesítési rendelést várakoztatni kell addig, amíg a vevői kifizetés igazolható nem lesz. Ebben a példában a változók a 1202-es vevő és az 1000,00 összrendelés. A feltétel szerint ha a 1202-es vevő felad egy rendelést, és a rendelés teljes összege 1000,00 vagy több, az értékesítési rendelést várakoztatni kell, amíg a vevői kifizetés ellenőrzése megtörténik.




