---
title: Referencia-kamatláb beállítása
description: Ez a témakör ismerteti a referencia-kamatlábak beállítását. A referencia-kamatláb szükségesek, ha a szervezet referencia-kamatlábakkal társítja a lízingdíjakat.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 16b83102aa76f46473138f89ea487e71668a188c
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444174"
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