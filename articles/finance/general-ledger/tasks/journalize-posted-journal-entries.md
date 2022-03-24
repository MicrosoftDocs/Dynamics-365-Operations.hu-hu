---
title: Feladott naplóbejegyzések naplózása
description: Az eljárás bemutatja, hogyan naplózhatók a feladott naplóbejegyzések.
author: aprilolson
ms.date: 03/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8fca167563b14c825ebe29874c6488ddfb4d9a
ms.sourcegitcommit: 06acdfbccd7bd213a2397ea7b85d104f01914437
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/10/2022
ms.locfileid: "8400875"
---
# <a name="journalize-posted-journal-entries"></a>Feladott naplóbejegyzések naplózása

[!include [banner](../../includes/banner.md)]

A főkönyvben a naplózási folyamat segítségével csoportosítani és jelenteni lehet a feladott bizonylatbejegyzéseket a főkönyvben. A megadott feltételek alapján a feldolgozás létrehozza azon **bizonylatok** listáját, amelyek egyedi számsorozatot és hivatkozásként a főkönyvi napló számát használják.

A következő lépések szerint naplózhatja a feladott naplóbejegyzéseket. Ez az eljárás az **USMF bemutatóadat-vállalatot** használja.

1. Menjen a **Főkönyv** \> **Főkönyv beállítás** \> **Főkönyv paraméterei** pontra.
2. A Kiterjesztett főkönyvi **napló** mezőben válasszon ki egy értéket. Ha az Igen lehetőséget **választja**, a jelentés kimenete eltérő lesz.
3. Válassza ki, hogy az időszak lezárható-e, ha a naplózási folyamatot még nem futtatták le. Ha az Igen **lehetőséget** választja, az időszakot nem lehet lezárni, amíg az adott időszak naplózási folyamata be nem fejeződött.
4. Zárja be a lapot.
5. Menjen a Főkönyv **időszakos** \> **feladatai –** \> **Naplózás,** és válassza a Szűrő **lehetőséget.**
6. Válassza ki a definiálni kívánt szűrési feltételek sorát.
7. A Feltételek **mezőben** adja meg vagy válassza ki a szűrési feltételeket.
8. Válassza az **OK** lehetőséget az oldal bezárásához.
9. A **naplózási folyamat az OK** gombra való beállításának kiválasztásával indítódik el. A folyamat befejezése után létrejön egy jelentés.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
