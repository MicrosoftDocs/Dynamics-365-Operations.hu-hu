---
title: Értékesítési rendelés létrehozása konfigurálható termékhez
description: Ez az eljárás azt szemlélteti, hogy hogyan lehet egy konfigurációs sablont alkalmazni egy értékesítési rendelésben szereplő termékre.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 882198bf07233867b54579b986f93f5c1b46c1b6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564201"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Értékesítési rendelés létrehozása konfigurálható termékhez

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás azt szemlélteti, hogy hogyan lehet egy konfigurációs sablont alkalmazni egy értékesítési rendelésben szereplő termékre. Ebben a példában a D0006 hangszórómodellt használjuk a USMF bemutatócég esetében. Ezt az eljárást jellemzően az értékesítésirendelés-feldolgozó használja.


## <a name="create-a-sales-order"></a>Értékesítési rendelés létrehozása
1. Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.
2. Kattintson az Új lehetőségre.
3. Kattintson az Értékesítési rendelés gombra.
4. A Vevői számla mezőben válassza a következőt: US-001. 
5. Kattintson az OK gombra.
6. A Cikkszám mezőben válassza ki a D0006 értéket.
    * Ehhez a feladathoz ki kell választania egy konfigurálható terméket.  
7. Kattintson a Termék és készlet menüpontra.
8. Kattintson a Sor konfigurálására.
    * Vegye figyelembe, hogy az ár megváltozott a kiválasztott beállítás alapján, és a Kábel is a része mező értéke most már Igaz.  
    * Tekintse meg az alapértelmezett árat és kábelhez kiválasztott beállításokat.  
9. Kattintson a Rakománysablonra.
    * Ez a példa azt mutatja be, hogyan alkalmazhat egy sablont egy előre definiált konfiguráció kiválasztásához. Ha feladat-útmutatóként használja ezt az eljárást, és szeretné megtekinteni a többi rendelkezésre álló attribútumértéket, kattintson a Feloldás gombra.  
10. Kattintson az OK gombra.
11. Kattintson az OK gombra.
12. Bontsa ki a Soradatok szakaszt.
13. Kattintson a Termék fülre.
    * A cikk konfigurációja most már látható a termék méretei alatt.  
14. Zárja be a lapot.

## <a name="select-the-product-configuration"></a>Válassza ki a termékkonfigurációt.

