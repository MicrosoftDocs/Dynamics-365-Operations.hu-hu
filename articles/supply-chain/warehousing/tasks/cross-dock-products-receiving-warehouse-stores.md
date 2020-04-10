---
title: Termékek áttárolása a fogadó raktárból az üzletekbe
description: Ez az eljárás bemutatja, hogy mely lépésekkel hozhat létre és dolgozhat fel egy Áttárolást, amellyel termékeket oszthat el egy beszerzési rendelés bevételezési helyéről egy vagy több üzletbe.
author: ShylaThompson
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f297a9bbb8ad5d1cd701626783e7db75c94fa842
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148377"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>Termékek áttárolása a fogadó raktárból az üzletekbe

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogy mely lépésekkel hozhat létre és dolgozhat fel egy Áttárolást, amellyel termékeket oszthat el egy beszerzési rendelés bevételezési helyéről egy vagy több üzletbe. A felhasználó több konfigurációt is definiálhat, majd kérheti a rendszer javaslatát a termékek elosztására, vagy manuálisan megadhatja, hogy a termékek elosztása hová és az egyes üzletekbe milyen mennyiségben történjen. Az eljárás nem tartalmazza az Áttárolás lehetőségben használható adatok (például: feltöltési szabályok, szervezeti hierarchiák, üzletek súlya) beállítását. Az eljárás az USRT bemutatócéget használja.

1. Ugrás az összes beszerzési rendelésre.
2. Válasszon ki a listából egy beszerzési rendelést, majd a rendelés megnyitásához kattintson a hivatkozásra.
3. A műveleti ablaktáblán kattintson a Kiskereskedelem és Kereskedelem elemre.
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

