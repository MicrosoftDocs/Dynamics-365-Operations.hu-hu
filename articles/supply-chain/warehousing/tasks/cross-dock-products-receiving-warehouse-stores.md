--- 
title: "Termékek áttárolása a fogadó raktárból az üzletekbe"
description: "Ez az eljárás bemutatja, hogy mely lépésekkel hozhat létre és dolgozhat fel egy Áttárolást, amellyel termékeket oszthat el egy beszerzési rendelés bevételezési helyéről egy vagy több üzletbe."
author: BibiSp
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: daa42bb83d6b988e8fd18db6ad8386c67fd3e6e5
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>Termékek áttárolása a fogadó raktárból az üzletekbe

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy mely lépésekkel hozhat létre és dolgozhat fel egy Áttárolást, amellyel termékeket oszthat el egy beszerzési rendelés bevételezési helyéről egy vagy több üzletbe. A felhasználó több konfigurációt is definiálhat, majd kérheti a rendszer javaslatát a termékek elosztására, vagy manuálisan megadhatja, hogy a termékek elosztása hová és az egyes üzletekbe milyen mennyiségben történjen. Az eljárás nem tartalmazza az Áttárolás lehetőségben használható adatok (például: feltöltési szabályok, szervezeti hierarchiák, üzletek súlya) beállítását. Az eljárás az USRT bemutatócéget használja.

1. Ugrás az összes beszerzési rendelésre.
2. Válasszon ki a listából egy beszerzési rendelést, majd a rendelés megnyitásához kattintson a hivatkozásra.
3. A Művelet panelen kattintson a Kiskereskedelem elemre.
4. Kattintson az Áttárolás gombra.
5. Kattintson a Szerkesztés lehetőségre.
    * A kategória segítségével szűrhetőek a Sorok szakaszban lévő cikkek.  
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. Az Áttárolási mennyiség mezőbe írjon be egy értéket, amely megadja, hogy a kiválasztott termékből beszerzett mennyiség mekkora része kerüljön elosztásra.
8. A További áttárolási mennyiség mezőbe írjon be egy értéket, amely megadja, hogy az elérhető beszerzett termékekből milyen mennyiség kerüljön elosztásra.
9. Az Elosztás mezőbe írja be: „Hely súly”.
    * Más elosztási szabályok használatához kiválaszthatja a többi típust is.  
10. Válasszon ki egy értéket a Feltöltési hierarchia mezőben.
11. Válassza az Igen lehetőséget a Szortimentek figyelembevétele mezőben.
12. Kattintson a Mennyiségek kiszámítása gombra.
13. Kattintson a Rendelés létrehozása gombra.
14. Kattintson az Igen gombra.
15. A listában keressen meg és jelöljön ki egy raktárat, amely termékeket fogadott.
16. A kiválasztott raktár létrejött rendeléseinek megtekintéséhez kattintson a Rendelés gombra.


