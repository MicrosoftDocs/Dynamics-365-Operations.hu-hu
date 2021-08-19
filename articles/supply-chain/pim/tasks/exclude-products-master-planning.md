---
title: Termékéletciklus-állapot létrehozása a termékek kizárásához az alaptervezésből
description: Ez az eljárás bemutatja, hogyan hozzon létre új termékéletciklus-állapotot, amely kizárja a termékeket az Alaptervezésből és anyagjegyzékszint-számításból.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1050aeb3f7acf9902f86aac60dae7fe89bbd847016c95e2acce3e539812c7023
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772520"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Termékéletciklus-állapot létrehozása a termékek kizárásához az alaptervezésből

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan hozzon létre új termékéletciklus-állapotot, amely kizárja a termékeket az Alaptervezésből és anyagjegyzékszint-számításból.


## <a name="create-an-obsolete-state"></a>Elavult állapot létrehozása
1. Válassza a Termékinformációk kezelése > Beállítás > Termékéletciklus állapota lehetőséget.
2. Kattintson az Új lehetőségre.
3. Az Állapot mezőben adjon meg egy értéket.
4. Az Aktív a tervezéshez mezőben várja a Nem lehetőséget.
5. A Leírás mezőben adjon meg egy értéket.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>Elavult állapot társítása kiadott termékhez
1. Zárja be a lapot.
2. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
3. Rekordok kereséséhez használja a gyorsszűrőt. Végezzen szűrést a Keresési név mezőben az „M00” értékkel.
4. Kattintson a Szerkesztés lehetőségre.
5. A listában jelölje meg a kiválasztott sort.
6. A Termékéletciklus állapota mezőben adjon meg vagy válasszon ki egy értéket.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]