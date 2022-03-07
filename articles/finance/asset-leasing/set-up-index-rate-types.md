---
title: Referencia-kamatláb beállítása
description: Ez a témakör ismerteti a referencia-kamatlábak beállítását. A referencia-kamatláb szükségesek, ha a szervezet referencia-kamatlábakkal társítja a lízingdíjakat.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRateType
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 40f230a9d69a142b18eb27a2d5e420dbadc600d2
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880960"
---
# <a name="set-up-index-rates"></a>Referencia-kamatláb beállítása

[!include [banner](../includes/banner.md)]

Ha a lízingfizetések indextől függenek, az referencia-kamatláb-típusok hozzáadhatók és karbantarthatók a rendszerben. Ha át szeretné értékelni a lízingkifizetéseket a **Referencia-kamatláb típusa** oldalról, az referencia-kamatláb átértékelési folyamat az átértékelés dátumától számított legutóbbi referencia-kamatlábat használja.

Referencia-kamatláb-típusok és referencia-kamatlábak hozzáadásához kövesse az alábbi lépéseket.

1. Nyissa meg az **Eszközlízing \> Beállítás \> Referencia-kamatláb típusa** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. A megfelelő mezőkben adja meg a díj típusát és a referencia-kamatláb nevét.
4. Új referencia-kamatláb érték hozzáadásához jelölje ki a referencia-kamatláb típusát, majd a **Hozzáadás** lehetőséget.
5. Válassza ki a díj kezdő dátumát, és válassza ki a díjértéket.

**Referencia-kamatláb értékkülönbség** vagy **Referencia-kamatláb érték** lehetőséget kell választania referencia-kamatláb-módszerként.

- Válassza ki a **Referencia-kamatláb értékkülönbség** módszerét az új lízingkifizetés kiszámításához a kezdő dátum referencia-kamatlába és a legutóbbi referencia-kamatláb közötti különbség alapján. A referencia-kamatláb az **Referencia-kamatláb (%)** mezőben van meghatározva.
- Válassza ki a **Referencia-kamatláb érték** módszerét a lízingkifizetés kiszámításához a **Referencia-kamatláb (%)** mezőben megadott százalék használatával.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
