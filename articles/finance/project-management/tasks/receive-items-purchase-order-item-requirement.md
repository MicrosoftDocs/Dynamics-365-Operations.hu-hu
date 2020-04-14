---
title: Cikkek átvétele cikkszükségletből származó beszerzési rendelés alapján
description: Ez a cikk bemutatja, hogyan lehet cikkeket átvenni beszerzési rendeléssel egy cikkszükségletből.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f288a47f952a30d98a4a5b96409dc53f880d41d
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139057"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a>Cikkek átvétele cikkszükségletből származó beszerzési rendelés alapján

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet cikkeket átvenni beszerzési rendeléssel egy cikkszükségletből.

Ha cikktranzakció helyett cikkszükségletet használ, közvetlenül a cikk tényleges felhasználása előttre tervezheti a szállítást, beszerzési rendelést hozhat létre, a cikket szerepeltetheti a kereskedelmi megállapodási keretrendszerben, és a cikkszükségletet szerepeltetheti a gyártástervezésben. 

Ez a feladat az USSI-adatkészletet használja.

1. A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Projektek > Minden projekt** részre.
2. A listában válassza ki a kívánt sorból a hivatkozást.
3. A Műveleti ablaktáblán kattintson a **Tervezés** elemre.
4. Válassza a **Cikkszükséglet** lehetőséget.
5. Válassza az **Új** lehetőséget.
6. Az új sorban adjon meg, vagy válasszon ki egy értéket a **Cikkszám** mezőben.
7. Adjon meg egy számot a **Mennyiség** mezőben.
8. Válassza a **Mentés** lehetőséget.
9. A műveleti ablaktáblán válassza a **Kezelés** lehetőséget.
10. Válassza a **Funkciók** lehetőséget.
11. Válassza a **Beszerzési rendelés létrehozása** lehetőséget.
12. Jelölje be **Az összes belefoglalása** jelölőnégyzetet.
13. A **Szállítószámla** mezőben adjon meg vagy válasszon ki egy értéket.
14. Válassza ki az **OK** lehetőséget.
15. A navigációs ablaktáblán nyissa meg a **Modulok > Kötelezettségek > beszerzési rendelések > Összes beszerzési rendelés** pontot.
16. A listában válassza ki a kívánt sorból a hivatkozást.
17. A Műveleti ablaktáblán válassza ki a **Beszerzés** lehetőséget.
18. Válassza ki a **Megerősítés** elemet.
19. A Művelet ablaktáblán válassza ki a **Bevételezés** elemet.
20. Válassza ki a **Termékbevételezés** elemet.
21. Írjon be egy értéket a **Termékbevételezés** mezőbe.
22. Válassza ki az **OK** lehetőséget.

