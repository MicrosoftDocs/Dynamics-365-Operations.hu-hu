---
title: Új termék létrehozása
description: Ez a feladat bemutatja, hogy hogyan lehet az új megosztott terméket létrehozni.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a603d89749242a4c6039ab83da286ec6ab727d8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "328539"
---
# <a name="create-a-new-product"></a>Új termék létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat bemutatja, hogy hogyan lehet az új megosztott terméket létrehozni. Ezt az eljárást általában a termék tervező végzi. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.

1. Ugorjon a Termékinformációk kezelése > Termékek > Termékek pontra.

## <a name="create-a-product"></a>Termék létrehozása
1. Kattintson az Új lehetőségre.
2. Írjon be egy értéket a Termékszám mezőbe.
    * Ha a számsorozatot nem állították be a termékszámra vonatkozóan, akkor manuálisan kell megadni.  
3. Írjon be egy értéket a Terméknév mezőbe.
    * A Termék neve az alapértelmezett keresési név. Ez szükség szerint módosítható.  
4. Kattintson az OK gombra.

## <a name="set-up-dimension-groups"></a>Állítsa be a Dimenziócsoportok lehetőséget
1. A Méretcsoportok gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.
    * A tárolásidimenzió-csoport határozza meg, hogy mely tárolási dimenziót kell megadni termék minden egyes tranzakciójában és hogy hogyan követi nyomon a rendszer a készletben.  
3. A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.
    * A tárolásidimenzió-csoport határozza meg, hogy mely nyomon követési dimenzióit kell megadni termék minden egyes tranzakciójában és hogy hogyan kezeli a rendszer a készletben.  
4. Kattintson az OK gombra.

