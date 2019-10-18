---
title: Vevői kifizetések letétbe helyezése
description: Vevői kifizetések letétele.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 595d1b609ae83af8f1581caeff9ef7d3892a6207
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178140"
---
# <a name="deposit-customer-payments"></a>Vevői kifizetések letétbe helyezése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Vevői kifizetések letétele. Ez a feladat az USMF bemutatócéget használja.

1. Válassza a **Navigációs ablaktábla >Modulok > Kinnlévőségek > Kifizetések > Kifizetési napló** elemet.
2. Válassza az **Új** lehetőséget.
3. A **Név** mezőben válassza ki a **CustPay** elemet a legördülő menüből.
4. **Sorok** kiválasztása.
5. A **Számla** mezőben válassza ki azt a vevőt, akihez rögzíti a fizetést.
6. A **Követel** mezőbe írja be a fizetés összegét. Az összeget üresen is hagyhatja, ilyenkor a rendszer kiszámítja, ha kiválasztja a kifizetett számlákat.  
7. Írjon be egy értéket a **Fizetési hivatkozás** mezőbe. A kifizetési hivatkozás lehet a bevitt kifizetés csekkszáma. A kifizetési hivatkozás azért szükséges, hogy a kifizetés letéti jegyen is szerepeljen.  
8. Jelölje be a négyzetet a letéti jegy használatához. Ha a kifizetésnek szerepelnie kell a letéten, ezt a beállítást állítsa az Igen lehetőségre.  
9. Válassza az **Új** lehetőséget.
10. A **Számla** mezőben válassza ki a vevőt a következő fizetéshez.
11. Adja meg a fizetés összegét a **Követel** mezőben.
12. Írjon be egy értéket a **Fizetési hivatkozás** mezőbe.
13. Jelölje be a négyzetet a **Letéti jegy használatához**.
14. Válassza a **Feladás** parancsot. Letéti jegyet csak akkor hozhat létre, ha feladta a kifizetéseket. Ez azért van így, hogy a kifizetés ne változhasson a letéti jegy létrehozása után.  
15. Válassza a **Funkciók** lehetőséget.
16. Válassza a **Letéti jegy** lehetőséget.
17. Válassza ki az **OK** lehetőséget. Az első oldalon a letéti jegyet hozhatja létre.  
18. Válassza ki az **OK** lehetőséget. A második lépésben kinyomtatja a letéti jegyet, de ez a lépés ne kötelező.  

