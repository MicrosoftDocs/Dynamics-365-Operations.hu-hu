---
title: A legfontosabb számlaadatok a kötelezettségkezelési rendszerbe számlagyűjtő használatával
description: Ez a témakör azt ismerteti, hogyan lehet a számlajegyzék segítségével számlákat létrehozni.
author: abruer
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc3f1107a9564120aae77a75e6232879bf3c51af
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858425"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>A legfontosabb számlaadatok a kötelezettségkezelési rendszerbe számlagyűjtő használatával

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet a számlajegyzék segítségével számlákat létrehozni. Ezután egyeztesse a számlát egy beszerzési rendeléssel a számlagyűjtő segítségével, majd véglegesítse a költséget a szállítói számla oldalon.


## <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása
1. A navigációs ablaktáblán nyissa meg a **Modulok > Kötelezettségek > beszerzési rendelések > Beszerzési rendelések** pontot.
2. Új beszerzési rendelés létrehozásához kattintson az **Új** elemre.
3. A **Szállítói számla** mezőben nyissa meg válasszon egy beszállítót a legördülő listához. Válassza ki például az **1001**-es szállítót.
4. Válassza ki az **OK** lehetőséget.
5. A **Cikkszám** mezőben válassza ki a kívánt szolgáltatási cikkszámot a legördülő listából. Válassza például a **S0001-t**. A nettó összeg 75,00.  Ezt az összeget szeretnénk viszontlátni a számlán is.  
6. A Műveleti ablaktáblán válassza ki a **Beszerzés** lehetőséget.
7. Válassza ki a **Megerősítés** elemet.

## <a name="create-and-post-and-invoice"></a>Számla létrehozása és feladása
1. Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlajegyzék** elemre.
2. Válassza az **Új** lehetőséget.
3. Nyissa meg a keresőlistát a használni kívánt számlajegyzék nevének kiválasztásához.
4. Válassza ki a használni kívánt számlajegyzék nevét.
5. Kattintson a **Sorokra** a jegyzék megnyitásához, adjon meg költségsorokat.
6. A keresőben válasszon egy szállítót. Válassza ki például az **1001**-es szállítót.
7. A **Számla** mezőben adja meg a számlaszámot.
8. Írjon egy értéket a **Leírás** mezőbe.
9. A **Hitelkeret** mezőben adjon meg egy számot.
10. A **Beszerzési rendelés** mezőben nyissa meg a legördülő listát a korábban létrehozott beszerzési rendelés kiválasztásához.
11. A **Jóváhagyó** mezőben jelöljön ki egy jóváhagyót a legördülő listából, majd a **Kiválasztás** gombra kattintva válassza ki a jóváhagyót.
12. Válassza a **Feladás** parancsot.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>A számlafolyamat befejezéséhez nyisson meg egy számlát a gyűjtőből, és válassza ki hozzá a megfelelő beszerzési rendelést.
1. Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlagyűjtő** elemre.
2. Kattintson a **Beszerzési rendelés** elemre, ha szállítói számlát kíván létrehozni a számlajegyzékből.
3. Válassza ki a megtekinteni kívánt számlát.
4. Az egyeztetés befejezéséhez kattintson az **Egyeztetési állapot frissítése** elemre.
5. A műveleti ablaktáblán válassza ki a **Beállítások** elemet.
6. Válassza ki a **Nézetváltás** lehetőséget.
7. Válassza a **Rácsnézet** elemet.
8. Válassza a **Feladás** parancsot.
9. Zárja be a lapot.
10. A Navigációs ablaktáblán válassza a **Modulok > Kötelezettségek > Szállítók > Beszállítók** elemet.
11. Válassza ki a beszerzési rendeléshez tartozó szállítót. Válassza ki például az **1001**-es szállítót.
12. A műveleti ablaktáblán válassza a **Szállító** lehetőséget.
13. Válassza a **Tranzakciók** lehetőséget.
14. Válassza ki a létrehozott számlát. A számlajegyzék-elhatárolás sztornírozásra, illetve a megfelelő költségszámlára feladásra került.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
