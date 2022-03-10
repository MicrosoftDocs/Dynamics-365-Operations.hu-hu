---
title: Alapértelmezett termékéletciklus-állapot létrehozása
description: Ez az eljárás egy alapértelmezett termékéletciklus-állapot létrehozását mutatja be, valamint azt is, hogyan lehet társítani az alapértelmezett állapotot a kiadott termékekhez.
author: t-benebo
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a628ed2b609f48c22076f409889c212e4d9463ac
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578200"
---
# <a name="create-a-default-product-lifecycle-state"></a>Alapértelmezett termékéletciklus-állapot létrehozása

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]