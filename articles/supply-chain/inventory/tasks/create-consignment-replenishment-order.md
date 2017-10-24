---
title: "Új bizományosi feltöltési rendelés létrehozása"
description: "Ez az eljárás bemutatja a bizományosi feltöltési rendelés létrehozását, ahol nyomon követhetők a várható szállítások egy szállítótól a bizományosi készletbe."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f7f8005ec9e723c94d53e6ab81f04ee388c83faa
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-consignment-replenishment-order"></a>Új bizományosi feltöltési rendelés létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja a bizományosi feltöltési rendelés létrehozását, ahol nyomon követhetők a várható szállítások egy szállítótól a bizományosi készletbe. Azt is bemutatja, hogyan lehet rögzíteni a termékek átvételét úgy, hogy a bizományosi készlet szállító tulajdonában levő aktuális készletként legyen regisztrálva. Ezt az eljárást általában egy beszerzési szakember végzi el. Ezt az útmutatót használhatja az USMF bemutatócégen. Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.




## <a name="create-a-consignment-replenishment-order"></a>Új bizományosi feltöltési rendelés létrehozása
1. Ugrás a Beszerzés és forrás > Bizományos > Bizományosi feltöltési rendelések elemre.
2. Kattintson az Új lehetőségre.
3. Válassza az US-104 szállítót a Szállítói számla mezőben.
    * Ki kell jelölnie egy szállítót, amelyik tulajdonosként van regisztrálva a Készlettulajdonosok lapon.  
4. Kattintson az OK gombra.
5. Kattintson az Új sor hozzáadása lehetőségre.
6. A Cikkszám mezőbe írja be az M9211CI értéket.
    * Ki kell választania egy cikket, amelyik be van állítva a bizományosi készlethez.  
7. Adjon meg egy számot a Mennyiség mezőben.
8. Adjon meg egy dátumot a Kért kézbesítési dátum mezőben.
    * A kért és visszaigazolt dátumokat az MRP-kalkulátor használja az áruk várható beérkezéséhez.  
9. Adjon meg egy dátumot a Visszaigazolt szállítási dátum mezőben.
10. Bontsa ki a Soradatok szakaszt.
11. Kattintson a Készlet dimenziók lapra.
12. A tulajdonos megjelenítéséhez a Készletdimenziók tulajdonos mezőjében, frissítse a lapot.
    * A tulajdonosként most már a US-104 szállító szerepel.  

## <a name="check-the-inventory-transaction-status"></a>Ellenőrizze a készlettranzakció állapotát.
1. Kattintson a Készlet parancsra.
2. Kattintson a Tranzakciók elemre.
3. A listában jelölje meg a kiválasztott sort.
    * Figyelje meg, hogy a Fogadás mező most már a Megrendelve értékre van állítva.  
4. Zárja be a lapot.

## <a name="receive-items"></a>Cikkek átvétele
1. Kattintson a Termékbevételezés elemre.
2. Írjon be egy értéket a Külső termékbevételezés mezőbe.
3. A Mennyiség mezőben adjon meg egy számot, amely kisebb az ott látható számnál.
4. Kattintson az OK gombra.

## <a name="check-the-on-hand-inventory"></a>Ellenőrizze az aktuális készletet
1. Kattintson a Készlet parancsra.
2. Kattintson az Aktuális készlet elemre.
3. Kattintson az Áttekintés elemre.
    * A cikkek, amelyek a szállító tulajdonában álló bizományosi készletként érkeztek, aktuális készletként állnak rendelkezésre. A bizományosi feltöltési rendelés fennmaradó mennyisége a Megrendelve összesen mezőben jelenik meg.  
4. Zárja be a lapot.
5. Kattintson a Bezárás gombra.

