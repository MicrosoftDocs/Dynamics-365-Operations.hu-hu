---
title: Új termék létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet új megosztott terméket létrehozni.
author: ShylaThompson
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bab383e4e1b33cbeeb0bbd7712e4907301057fd293c8334b45888be8f3d97277
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761806"
---
# <a name="create-a-new-product"></a>Új termék létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet új megosztott terméket létrehozni. Ezt az eljárást általában a termék tervező végzi. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.


## <a name="create-a-product"></a>Termék létrehozása
1. A Navigációs ablaktáblán ugorjon a **Modulok > Termékinformációk kezelése > Termékek > Termékek** lehetőségre.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Termékszám** mezőbe. Ha a számsorozatot nem állították be a termékszámra vonatkozóan, akkor manuálisan kell megadni.  
4. Írjon be egy értéket a **Terméknév** mezőbe. A Termék neve az alapértelmezett keresési név. Ez szükség szerint módosítható.  
5. Válassza ki az **OK** lehetőséget.

## <a name="set-up-dimension-groups"></a>Állítsa be a Dimenziócsoportok lehetőséget
1. A **Méretcsoportok** gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. A **Tárolási dimenziócsoport** mezőben adjon meg, vagy válasszon ki egy értéket. A tárolásidimenzió-csoport határozza meg, hogy mely tárolási dimenziót kell megadni termék minden egyes tranzakciójában és hogy hogyan követi nyomon a rendszer a készletben.  
3. A **Nyomon követési dimenziócsoport** mezőben adjon meg, vagy válasszon ki egy értéket. A tárolásidimenzió-csoport határozza meg, hogy mely nyomon követési dimenzióit kell megadni termék minden egyes tranzakciójában és hogy hogyan kezeli a rendszer a készletben.  
4. Válassza ki az **OK** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]