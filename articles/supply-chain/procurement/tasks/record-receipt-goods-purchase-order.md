---
title: Az áruk bevételezésének rögzítése a beszerzési rendelésen
description: Ez a cikk bemutatja, hogyan lehet közvetlenül a beszerzési rendelésen rögzíteni a cikkek bevételezését.
author: GalynaFedorova
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22baf6d0f6db04b3c6ce3c09ee8cb286e9a1e590
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882460"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Az áruk bevételezésének rögzítése a beszerzési rendelésen

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet közvetlenül a beszerzési rendelésen rögzíteni a cikkek bevételezését. Ezen kívül lehetséges az is, hogy rögzítsen árubeérkezést a raktárban, amit majd később rögzíthet a beszerzési rendelésre. A feladatot általában a beszerzési ügynök, vagy a fizetendő számla koordinátor végzi el. Az útmutatóban mutatott példa használható az USMF demo adatok cégben. A példa tartalmazza az egyszerű beszerzési rendelés létrehozásához szükséges lépéseket, így feladat segédletként használhatja a folyamat során. Ha az eljárás alatt a saját adatait használja, az **Árubeérkeztetés** részfeladattal kell kezdenie.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Új beszerzési rendelés készítése áru bevételezéshez
1. Ugorjon a **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Beszerzési rendelések > Összes beszerzési rendelés** elemre.
2. Válassza az **Új** lehetőséget.
3. Adja meg az `US-101` értéket a **Szállítói számla** mezőben.
4. Válassza ki az **OK** lehetőséget.
5. Adja meg az `M0001` értéket a **Cikkszám** mezőben.
6. Adja meg az `5` értéket a **Mennyiség** mezőben.
7. A Műveleti ablaktáblán válassza ki a **Beszerzés** lehetőséget.
8. Válassza ki a **Megerősítés** elemet.

## <a name="record-receipt-of-goods"></a>Áruk bevételezésének rögzítése
1. A Művelet ablaktáblán válassza ki a **Bevételezés** elemet.
2. Válassza ki a **Termékbevételezés** elemet. A **Mennyiség** mező segítségével kiválaszthat különböző lehetőségeket ahhoz a mennyiséghez, amelyet szeretne beérkeztetni. Ha például a mennyiség korábban már regisztrálva lett a raktárban, akkor kiválaszthatja a **Regisztrált mennyiség** lehetőséget. Ebben a példában használja a **Megrendelt mennyiség** elemet.
3. Bontsa ki az **Áttekintés** szakaszt.
4. Adjon meg egy értéket a **Termékbevételezés** mezőben. Ezzel a mezővel lehet megadni olyan hivatkozást, ami bizonylatként lesz használva a termék bevételezési naplójához.  
5. Bontsa ki a **Sorok** szakaszt.
6. Állítsa a **Mennyiség** lehetőséget „4-re”. Itt is manuálisan adhatja meg a mennyiséget, ami a rendelés minden sorához tartozó bevételezett mennyiség.  
7. Válassza ki az **OK** lehetőséget. Az áruk most már beérkezettként szerepelnek a beszerzési rendelésen és egy termékbevételezési napló lett létrehozva ennek a dokumentálására. A Termék-bevételezési művelet segítségével áttekintheti a beszerzési rendeléshez létrehozott naplókat, és láthatja, hogy mi érkezett és mikor.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]