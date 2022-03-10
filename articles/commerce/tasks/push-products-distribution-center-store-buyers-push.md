---
title: " Termékek elosztása az elosztási központból az üzletbe a központi elosztás használatával"
description: Ez az eljárás bemutatja, hogy mely lépésekkel hozhat létre és dolgozhat fel egy Központi elosztást, amellyel termékeket oszthat el egyetlen helyről egy vagy több üzletbe.
author: BrianShook
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBuyersPush, InventLocationIdLookup, InventItemIdLookupSimple, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 30d82e4b282bac2ea888971ad5c6298adfa8332b
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779620"
---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a> Termékek elosztása az elosztási központból az üzletbe a központi elosztás használatával

[!include [banner](../includes/banner.md)]

Ez az eljárás bemutatja, hogy mely lépésekkel hozhat létre és dolgozhat fel egy Központi elosztást, amellyel termékeket oszthat el egyetlen helyről egy vagy több üzletbe. A felhasználó több konfigurációt is definiálhat, majd kérheti a rendszer javaslatát a termékek elosztására, vagy manuálisan megadhatja, hogy a termékek elosztása hová és az egyes üzletekbe milyen mennyiségben történjen. Ez az eljárás nem tartalmazza a Központi elosztás lehetőségben használható adatok (például: feltöltési szabályok, szervezeti hierarchiák, üzletek súlya) beállítását. Ez az eljárás az USRT bemutatócéget használja.

1. Nyissa meg a következőt: Központi elosztás.
2. Kattintson az Új lehetőségre.
3. A Leírás mezőben adjon meg egy értéket.
4. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
5. A Raktár mezőben adjon meg vagy válasszon ki egy raktárt, amelyben termékek aktuális készletei találhatók.
6. Kattintson a Hozzáadás gombra.
7. A listában jelölje meg a kiválasztott sort.
8. A Cikkszám mezőben adjon meg, vagy válasszon ki egy terméket.
9. Kattintson a Hozzáadás gombra.
10. A listában jelölje meg a kiválasztott sort.
11. A Cikkszám mezőben adjon meg, vagy válasszon ki egy termékváltozatot.
    * Termékváltozat megadásakor minden egyes változathoz létrejönnek sorok.  
12. Jelöljön meg egy sort a listán.
13. A Központilag elosztott mennyiség mezőbe írja be, hogy a kiválasztott termékből mennyit kíván elosztani.
14. A További központilag elosztandó mennyiség mezőben adja meg azoknak a termékeknek a mennyiségét, amelyekből rendelkezésre áll elosztható mennyiség.
15. Az Elosztás mezőbe írja be: „Hely súly”.
    * Más elosztási szabályok használatához kiválaszthatja a többi típust is.  
16. Válasszon ki egy értéket a Feltöltési hierarchia mezőben.
17. Válassza az Igen lehetőséget a Szortimentek figyelembevétele mezőben.
18. Kattintson a Mennyiségek kiszámítása gombra, majd ellenőrizze a Raktár szakasz soraihoz adott mennyiségeket.
19. Kattintson a Rendelés létrehozása gombra.
20. Kattintson az Igen gombra.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]