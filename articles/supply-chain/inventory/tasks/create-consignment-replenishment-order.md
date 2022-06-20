---
title: Új bizományosi feltöltési rendelés létrehozása
description: Ez a cikk bemutatja a bizományosi feltöltési rendeléseket, amelyek segítségével nyomon követhető a szállítótól a bizományosi készletbe várható szállítás.
author: yufeihuang
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31a1d0a7d322b17d3d80dd9fade2b037dd148d9f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859373"
---
# <a name="create-a-consignment-replenishment-order"></a>Új bizományosi feltöltési rendelés létrehozása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja a bizományosi feltöltési rendeléseket, amelyek segítségével nyomon követhető a szállítótól a bizományosi készletbe várható szállítás. Azt is bemutatja, hogyan lehet rögzíteni a termékek átvételét úgy, hogy a bizományosi készlet szállító tulajdonában levő aktuális készletként legyen regisztrálva. Ezt az eljárást általában egy beszerzési szakember végzi el. Ezt az útmutatót használhatja az USMF bemutatócégen. Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.

## <a name="create-a-consignment-replenishment-order"></a>Új bizományosi feltöltési rendelés létrehozása
1. Navigációs ablaktáblán ugorjon a **Modulok > Beszerzés és forrás > Szállítás > Bizományosi feltöltési rendelések** elemre.
2. Válassza az **Új** lehetőséget.
3. Válassza ki a **Szállítói számla** mezőben az **US-104** szállítót (tulajdonosként bejegyzett szállítót kell kiválasztani a **készlet tulajdonosai** lapon). 
4. Válassza ki az **OK** lehetőséget.
5. Válassza a **Sor hozzáadása** lehetőséget.
6. Írja be a **cikkszám** mezőbe ezt: `M9211CI` (ki kell választania egy olyan elemet, amely be van állítva a szállítmány készletéhez).
7. Adjon meg egy számot a **Mennyiség** mezőben.
8. Adjon meg egy dátumot a **Kért kézbesítési dátum** mezőben. A kért és visszaigazolt dátumokat az MRP-kalkulátor használja az áruk várható beérkezéséhez.  
9. Adjon meg egy dátumot a **Visszaigazolt szállítási dátum** mezőben.
10. Bontsa ki a **Sorrészletek** szakaszt.
11. Válassza a **Készletdimenziók** lapot.
12. A tulajdonos megjelenítéséhez a **Készletdimenziók tulajdonos** mezőjében, frissítse a lapot. A tulajdonosként most már a US-104 szállító szerepel.  

## <a name="check-the-inventory-transaction-status"></a>Ellenőrizze a készlettranzakció állapotát.
1. Válassza a **Készlet** lehetőséget.
2. Válassza a **Tranzakciók** lehetőséget.
3. A kívánt sorban figyelje meg, hogy a **Fogadás** mező most már a **Megrendelve** értékre van állítva.  
4. Zárja be a lapot.

## <a name="receive-items"></a>Cikkek átvétele
1. Válassza ki a **Termékbevételezés** elemet.
2. Írjon be egy értéket a **Külső termékbevételezés** mezőbe.
3. A **Mennyiség** mezőben adjon meg egy számot, amely kisebb az ott látható számnál. 
4. Válassza ki az **OK** lehetőséget.

## <a name="check-the-on-hand-inventory"></a>Ellenőrizze az aktuális készletet
1. Válassza a **Készlet** lehetőséget.
2. Válassza az **Aktuális készlet** elemet.
3. Válassza az **Áttekintés** elemet. A cikkek, amelyek a szállító tulajdonában álló bizományosi készletként érkeztek, aktuális készletként állnak rendelkezésre. A bizományosi feltöltési rendelés fennmaradó mennyisége a **Megrendelve összesen** mezőben jelenik meg.  
4. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]