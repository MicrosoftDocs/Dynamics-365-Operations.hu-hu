---
title: Fő számlaadatok a Kintlevőségek rendszerben, szállítói számla használatával
description: Ez a feladat-útmutató segít Önnek szállítói számla létrehozásában egy beszerzési rendelésből, valamint a beszerzési rendelés, nyugta és számla egyeztetési eredményeinek megtekintésében (háromirányú egyeztetés).
author: abruer
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 74065fa3177c8add29e64ce0f77461df036c8fe5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979313"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a>Fő számlaadatok a Kintlevőségek rendszerben, szállítói számla használatával

[!include [banner](../../includes/banner.md)]

Ez a feladat-útmutató segít Önnek szállítói számla létrehozásában egy beszerzési rendelésből, valamint a beszerzési rendelés, nyugta és számla egyeztetési eredményeinek megtekintésében (háromirányú egyeztetés).


## <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása
1. A navigációs ablaktáblán nyissa meg a **Modulok > Kötelezettségek > beszerzési rendelések > Összes beszerzési rendelés** pontot.
2. Kattintson az **Új** elemre.
3. A **Szállítói számla** mezőben kattintson a legördülő gombra a keresés megnyitásához.
4. Keressen egy szállítót. Például görgessen le a US-104 lehetőségre.
5. US-104 szállító kiválasztása.
6. Kattintson az **OK** gombra.
7. A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához.
8. Készletcikk kiválasztása. Példábul válassza ki az 1000 cikkszámot.
9. Bontsa ki a **Soradatok** gyorslapot.
10. Kattintson a **Beállítás** lapra. Felülírhatja az egyeztetési irányelvet egyeztetés nélkülire, kétirányú egyeztetésre vagy háromirányú egyeztetésre.  
11. A Művelet panelen kattintson a **Beszerzés** elemre.
12. Kattintson a **Megerősítés** gombra.

## <a name="receive-the-products"></a>A termékek bevételezése
1. A Művelet panelen kattintson a **Fogadás** elemre.
2. Kattintson a **Termékbevételezés** lehetőségre.
3. A **Termékbevételezés** mezőbe írja be a termékbevételezés számát. Például írja be, hogy PR123.
4. Kattintson az **OK** gombra a termékbevételezés feladásához.
5. Zárja be a lapot.

## <a name="create-a-vendor-invoice"></a>Szállítói számla létrehozása
1. A navigációs ablaktáblán nyissa meg a **Modulok > Kötelezettségek > Beszerzési rendelések > Bevételezett, de nem számlázott beszerzési rendelések** pontot.
2. Válassza ki a létrehozott beszerzési rendelést.
3. A Műveleti ablaktáblán kattintson a **Számla** elemre.
4. Kattintson a **Számla** pontra.
5. A **Szám** mezőben adja meg a számlaszámot.
6. A **Számla leírása** mezőben adjon meg egy értéket.
7. Adjon meg egy dátumot a **Számla dátuma** mezőben.
8. Írjon be 1200 értéket az **Egységár** mezőbe.
9. Kattintson az **Új sor hozzáadása** elemre.
10. A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához.
11. Keresse meg a listában a telepítési költség cikkszámát. Például az S0001 elem
12. Válassza ki a telepítési költség cikkszámát. Vegye figyelembe, hogy egyeztetés a módosítások óta nem lett végrehajtva.  
13. Kattintson az **Egyeztetési állapot frissítése** lehetőségre.
14. A Művelet panelen kattintson az **Áttekintés** lehetőségre.
15. Kattintson a **Részletek egyeztetése** elemre. A szolgáltatásokkal rendelkező új sorokat nem kell egyeztetni, ezért az állapotuk „Kihagyva” marad.  
16. Válassza ki a termékbevételezést a bevételezett készletcikkhez. A termékbevételezés sora egyeztetve lett, de eltérés található az árban vagy a mennyiségben, ezért sikertelen.  
17. Adjon meg egy számot az **Egységár** mezőben. Most, hogy az egységár megegyezik, az állapot Sikeres értékre frissül. Ha az irányelve megengedi az eltéréseket, vagy az egyeztetés csak egy figyelmeztetés, akkor ettől függetlenül fel tudja adni a számlát.  
18. Zárja be a lapot.
19. Kattintson a **Bejegyzés** lehetőségre.
20. Zárja be az űrlapot. Ne felejtse, hogy a beszerzési rendelés már nem bevételezettként, hanem nem számlázottként van listázva.  

