---
title: Vevői kifizetések letétbe helyezése
description: Vevői kifizetések letétele.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f58cebce20e8516dc918e0bad1e020ffd7f791ee
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "313382"
---
# <a name="deposit-customer-payments"></a>Vevői kifizetések letétbe helyezése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Vevői kifizetések letétele. Ez a feladat az USMF bemutatócéget használja.

1. Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési napló pontra.
2. Kattintson az Új lehetőségre.
3. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A fizetési napló kiválasztása. 
5. Kattintson a Sorok pontra.
6. A Számla mezőben válassza ki azt a vevőt, akihez rögzíti a fizetést.
7. A Követel mezőbe írja be a fizetés összegét.
    * Az összeget üresen is hagyhatja, ilyenkor a rendszer kiszámítja, ha kiválasztja a kifizetett számlákat.  
8. Írjon be egy értéket a Fizetési hivatkozás mezőbe.
    * A kifizetési hivatkozás lehet a bevitt kifizetés csekkszáma. A kifizetési hivatkozás azért szükséges, hogy a kifizetés letéti jegyen is szerepeljen.  
9. Jelölje be a négyzetet a letéti jegy használatához.
    * Ha a kifizetésnek szerepelnie kell a letéten, ezt a beállítást állítsa az Igen lehetőségre.  
10. Kattintson az Új lehetőségre.
11. A Számla mezőben válassza ki a vevőt a következő fizetéshez.
12. Adja meg a fizetés összegét a Követel mezőben.
13. Írjon be egy értéket a Fizetési hivatkozás mezőbe.
14. Jelölje be a négyzetet a letéti jegy használatához.
15. Kattintson a Feladás lehetőségre.
    * Letéti jegyet csak akkor hozhat létre, ha feladta a kifizetéseket. Ez azért van így, hogy a kifizetés ne változhasson a letéti jegy létrehozása után.  
16. Kattintson a Funkciók elemre.
17. Kattintson a Letéti jegyre.
18. Kattintson az OK gombra.
    * Az első oldalon a letéti jegyet hozhatja létre.  
19. Kattintson az OK gombra.
    * A második lépésben kinyomtatja a letéti jegyet, de ez a lépés ne kötelező.  

