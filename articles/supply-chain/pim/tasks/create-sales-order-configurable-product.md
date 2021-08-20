---
title: Értékesítési rendelés létrehozása konfigurálható termékhez
description: Ez az eljárás azt szemlélteti, hogy hogyan lehet egy konfigurációs sablont alkalmazni egy értékesítési rendelésben szereplő termékre.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f128518af01911a29ae297670883ef425f9117d65cc952cc1ffdb044c4ce085f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781902"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Értékesítési rendelés létrehozása konfigurálható termékhez

[!include [banner](../../includes/banner.md)]

Ez az eljárás azt szemlélteti, hogy hogyan lehet egy konfigurációs sablont alkalmazni egy értékesítési rendelésben szereplő termékre. Ebben a példában a D0006 hangszórómodellt használjuk a USMF bemutatócég esetében. Ezt az eljárást jellemzően az értékesítésirendelés-feldolgozó használja.

## <a name="create-a-sales-order"></a>Értékesítési rendelés létrehozása

1. Ugrás az **Értékesítés és marketing \> Munkaterületek \> Értékesítési rendelés feldolgozása és lekérdezése** elemre.
1. Válassza az **Új** lehetőséget.
1. Válassza ki az **Értékesítési rendelés** lehetőséget.
1. A **Vevői számla** mezőben válassza a következőt: *US-001*. 
1. Válassza ki az **OK** lehetőséget.
1. A **Cikkszám** mezőben válassza ki a *D0006* cikkszámot.
    * Ehhez a feladathoz ki kell választania egy konfigurálható terméket.  
1. Kattintson a **Termék és készlet** menüpontra.
1. Válassza a **Sor konfigurálása** elemet.
    * Vegye figyelembe, hogy az ár megváltozott a kiválasztott beállítás alapján, és a **Kábel is a része** mező értéke most már *Igaz*.  
    * Tekintse meg az alapértelmezett árat és kábelhez kiválasztott beállításokat.  
1. Válassza a **Rakománysablon** lehetőséget.
    * Ez a példa azt mutatja be, hogyan alkalmazhat egy sablont egy előre definiált konfiguráció kiválasztásához. Ha feladat-útmutatóként használja ezt az eljárást, és szeretné megtekinteni a többi rendelkezésre álló attribútumértéket, kattintson a **Feloldás** gombra.  
1. Válassza ki az **OK** lehetőséget.
1. Válassza ki az **OK** lehetőséget.
1. Bontsa ki a **Sorrészletek** szakaszt.
1. Válassza ki a **Termék** fület.
    * A cikk konfigurációja most már látható a termék méretei alatt.  
1. Zárja be a lapot.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]