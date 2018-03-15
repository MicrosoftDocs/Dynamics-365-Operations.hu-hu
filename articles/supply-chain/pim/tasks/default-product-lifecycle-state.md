--- 
title: "Alapértelmezett termékéletciklus-állapot létrehozása"
description: "Ez az eljárás egy alapértelmezett termékéletciklus-állapot létrehozását mutatja be, valamint azt is, hogyan lehet társítani az alapértelmezett állapotot a kiadott termékekhez."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d445ea2f2362f146a1e3e7bcf747898dc2cc89ba
ms.openlocfilehash: 06a6c7c8fa767edf6fdf50c3c971b6d767f8755f
ms.contentlocale: hu-hu
ms.lasthandoff: 02/08/2018

---
# <a name="create-a-default-product-lifecycle-state"></a>Alapértelmezett termékéletciklus-állapot létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás egy alapértelmezett termékéletciklus-állapot létrehozását mutatja be, valamint azt is, hogyan lehet társítani az alapértelmezett állapotot a kiadott termékekhez.


## <a name="create-a-default-lifecycle-state"></a>Alapértelmezett életciklusállapot létrehozása
1. Válassza a Termékinformációk kezelése > Beállítás > Termékéletciklus állapota lehetőséget.
2. Kattintson az Új lehetőségre.
3. Az Állapot mezőben adjon meg egy értéket.
4. Az Alapértelmezett kiadáskor jogi személynek mezőben válassza az Igen lehetőséget.
5. A Leírás mezőben adjon meg egy értéket.
6. Az Aktív a tervezéshez mezőben várja a Nem lehetőséget.

> [!NOTE]
> Ha egy új kiadott terméket nem kell belefoglalni az alaptervezésbe, válassza a Nem lehetőséget. Ha szerepelnie kell az alaptervezésben, hagyja meg az alapértelmezett Igen értéken.  

## <a name="create-a-new-released-product"></a>Új kiadott termék létrehozása
1. Zárja be a lapot.
2. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
3. Kattintson az Új lehetőségre.
4. Írjon be egy értéket a Termékszám mezőbe.
5. Írjon be egy értéket a Terméknév mezőbe.
6. Írjon be egy értéket a Keresési név mezőbe.
7. Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
8. Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
9. A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.
10. A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.
11. Kattintson az OK gombra.

> [!NOTE]
> Az alapértelmezett termékéletciklus-állapot egy globális definíció.  

## <a name="change-the-product-to-an-active-state"></a>Termék aktív állapotra történő módosítása
1. A Termékéletciklus állapota mezőben adjon meg vagy válasszon ki egy értéket.

> [!NOTE]
> Tegyük fel, hogy beállította az aktív állapotot, és most kiválaszthatja az aktív állapotot, engedélyezve a termék használatát az alaptervezésben és az anyagjegyzékszintű számításban. Ennek természetesen csak akkor van értelme, ha a konzisztens tervezéshez szükséges összes termékrészlet meg van határozva.  


