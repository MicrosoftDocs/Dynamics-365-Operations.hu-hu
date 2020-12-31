---
title: Lízingcsoport létrehozása
description: Ez a témakör ismerteti a lízingcsoport beállítását. Új lízingcsoportok létrehozásához lízingcsoportokra van szükség.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f8512a59d0e9935090f97a0f0237bfefc8473955
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444177"
---
# <a name="create-a-lease-group"></a>Lízingcsoport létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti a lízingcsoport beállítását. Új lízingcsoportok létrehozásához lízingcsoportokra van szükség. A lízingkönyvek az egyes lízingcsoportokhoz vannak társítva. A lízingkönyvek határozzák meg az egyes lízingek alapértelmezett könyveit. A **Lízing feladás paraméterek** lapon adott számlákat rendelhet egy lízingcsoporthoz.

## <a name="create-a-lease-book-and-add-a-lease-group"></a>Lízingkönyv létrehozása és lízingcsoport hozzáadása

1. Nyissa meg az **Eszközlízing \> Beállítás \> Lízingcsoportok** lehetőséget.
2. Jelölje be a Műveleti ablaktáblán az **Új** lehetőséget a lízingcsoport létrehozásához. A program sort ad hozzá a rácshoz.
3. Az új sorban a **Lízingcsoport** mezőben adjon meg egy értéket.
4. A **Leírás** mezőben adjon meg egy értéket.

Az imént megadott adatok hozzáadódnak a **Lízingcsoport** mezőhöz a **Lízing hozzáadása** lapon.

## <a name="associate-a-book-with-a-lease-group"></a>Könyv társítása lízingcsoporthoz

Miután létrehozta a lízingcsoportokat, minden csoporthoz könyveket rendelhet. Amikor létrehoz egy lízinget, és hozzárendeli egy lízingcsoporthoz, a rendszer minden olyan könyvhöz létrehoz ütemezési készletet, amely az adott lízingsoporthoz van társítva.

> [!NOTE]
> A könyveket be kell állítani, mielőtt egy lízingcsoporthoz rendelhetők lennének.

1. Nyissa meg az **Eszközlízing \> Beállítás \> Lízingcsoport** lehetőséget.
2. Jelöljön ki egy lízingcsoportot, majd válassza a **Könyvek** lehetőséget.
3. Válassza az **Új** lehetőséget, majd a **Könyv típusa** mezőben válassza ki a lízingcsoporthoz hozzárendelni kívánt könyvet. Több könyvet is hozzárendelhet egy lízingcsoporthoz, ha a lízinget különböző módon kell elszámolni.
